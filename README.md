# Modelagem de Dados em Grafos de um Serviço de Streaming

- Essa modelagem de dados em grafos, foi desenvolvida no <b>Neo4j</b>.<br>
- Nós criados:<br>
  10 Gêneros, 10 Diretores, 10 Atores, 5 Filmes, 5 Séries, 10 Usuários<br>

- Abaixo está o script Cyper: <br><br>
CREATE CONSTRAINT unique_user_id IF NOT EXISTS FOR (u:User) REQUIRE u.userId IS UNIQUE;<br>
CREATE CONSTRAINT unique_movie_id IF NOT EXISTS FOR (m:Movie) REQUIRE m.movieId IS UNIQUE;<br>
CREATE CONSTRAINT unique_series_id IF NOT EXISTS FOR (s:Series) REQUIRE s.seriesId IS UNIQUE;<br>
CREATE CONSTRAINT unique_actor_id IF NOT EXISTS FOR (a:Actor) REQUIRE a.actorId IS UNIQUE;<br>
CREATE CONSTRAINT unique_director_id IF NOT EXISTS FOR (d:Director) REQUIRE d.directorId IS UNIQUE;<br>
CREATE CONSTRAINT unique_genre_id IF NOT EXISTS FOR (g:Genre) REQUIRE g.genreId IS UNIQUE;<br>


CREATE <br>
  // 10 Gêneros<br>
  (:Genre {genreId: 'g1', name: 'Ação'}),<br>
  (:Genre {genreId: 'g2', name: 'Comédia'}),<br>
  (:Genre {genreId: 'g3', name: 'Drama'}),<br>
  (:Genre {genreId: 'g4', name: 'Ficção Científica'}),<br>
  (:Genre {genreId: 'g5', name: 'Suspense'}),<br>
  (:Genre {genreId: 'g6', name: 'Romance'}),<br>
  (:Genre {genreId: 'g7', name: 'Fantasia'}),<br>
  (:Genre {genreId: 'g8', name: 'Terror'}),<br>
  (:Genre {genreId: 'g9', name: 'Documentário'}),<br>
  (:Genre {genreId: 'g10', name: 'Animação'}),<br>
  
  // 10 Diretores<br>
  (:Director {directorId: 'd1', name: 'Christopher Nolan', nationality: 'Britânico', birthYear: 1970}),<br>
  (:Director {directorId: 'd2', name: 'Steven Spielberg', nationality: 'Americano', birthYear: 1946}),<br>
  (:Director {directorId: 'd3', name: 'Ava DuVernay', nationality: 'Americana', birthYear: 1972}),<br>
  (:Director {directorId: 'd4', name: 'Pedro Almodóvar', nationality: 'Espanhol', birthYear: 1949}),<br>
  (:Director {directorId: 'd5', name: 'Bong Joon-ho', nationality: 'Sul-Coreano', birthYear: 1969}),
  (:Director {directorId: 'd6', name: 'Quentin Tarantino', nationality: 'Americano', birthYear: 1963}),<br>
  (:Director {directorId: 'd7', name: 'Greta Gerwig', nationality: 'Americana', birthYear: 1983}),<br>
  (:Director {directorId: 'd8', name: 'Martin Scorsese', nationality: 'Americano', birthYear: 1942}),<br>
  (:Director {directorId: 'd9', name: 'Denis Villeneuve', nationality: 'Canadense', birthYear: 1967}),<br>
  (:Director {directorId: 'd10', name: 'Jane Campion', nationality: 'Neozelandesa', birthYear: 1954}),<br>
  
  // 10 Atores<br>
  (:Actor {actorId: 'a1', name: 'Leonardo DiCaprio', birthYear: 1974, nationality: 'Americano'}),<br>
  (:Actor {actorId: 'a2', name: 'Meryl Streep', birthYear: 1949, nationality: 'Americana'}),<br>
  (:Actor {actorId: 'a3', name: 'Chadwick Boseman', birthYear: 1976, nationality: 'Americano'}),<br>
  (:Actor {actorId: 'a4', name: 'Viola Davis', birthYear: 1965, nationality: 'Americana'}),<br>
  (:Actor {actorId: 'a5', name: 'Joaquin Phoenix', birthYear: 1974, nationality: 'Americano'}),<br>
  (:Actor {actorId: 'a6', name: 'Scarlett Johansson', birthYear: 1984, nationality: 'Americana'}),<br>
  (:Actor {actorId: 'a7', name: 'Tom Hanks', birthYear: 1956, nationality: 'Americano'}),<br>
  (:Actor {actorId: 'a8', name: 'Zendaya', birthYear: 1996, nationality: 'Americana'}),<br>
  (:Actor {actorId: 'a9', name: 'Timothée Chalamet', birthYear: 1995, nationality: 'Americano'}),<br>
  (:Actor {actorId: 'a10', name: 'Florence Pugh', birthYear: 1996, nationality: 'Britânica'}),<br>
  
  // 5 Filmes<br>
  (:Movie {
    movieId: 'm1',
    title: 'A Origem',
    year: 2010,
    duration: 148,
    rating: 'PG-13',
    description: 'Um ladrão que rouba segredos corporativos através do uso da tecnologia de compartilhamento de sonhos.'
  }),<br>
  (:Movie {
    movieId: 'm2',
    title: 'Parasita',
    year: 2019,
    duration: 132,
    rating: 'R',
    description: 'Uma família pobre se infiltra na casa de uma família rica, gerando consequências inesperadas.'
  }),<br>
  (:Movie {
    movieId: 'm3',
    title: 'Duna',
    year: 2021,
    duration: 155,
    rating: 'PG-13',
    description: 'Paul Atreides viaja ao planeta mais perigoso do universo para garantir o futuro de sua família e seu povo.'
  }),<br>
  (:Movie {
    movieId: 'm4',
    title: 'O Poderoso Chefão',
    year: 1972,
    duration: 175,
    rating: 'R',
    description: 'O patriarca idoso de uma dinastia do crime organizado transfere o controle de seu império clandestino para seu filho relutante.'
  }),<br>
  (:Movie {
    movieId: 'm5',
    title: 'Barbie',
    year: 2023,
    duration: 114,
    rating: 'PG-13',
    description: 'Barbie e Ken estão tendo o momento de suas vidas no colorido e aparentemente perfeito mundo de Barbie Land.'
  }),<br><br>
  
  // 5 Séries<br>
  (:Series {
    seriesId: 's1',
    title: 'Stranger Things',
    startYear: 2016,
    endYear: null,
    seasons: 4,
    rating: 'TV-14',
    description: 'Um grupo de crianças enfrenta forças sobrenaturais em sua pequena cidade.'
  }),<br>
  (:Series {
    seriesId: 's2',
    title: 'The Crown',
    startYear: 2016,
    endYear: 2023,
    seasons: 6,
    rating: 'TV-MA',
    description: 'A vida da Rainha Elizabeth II e os eventos que moldaram o século XX.'
  }),<br>
  (:Series {
    seriesId: 's3',
    title: 'Breaking Bad',
    startYear: 2008,
    endYear: 2013,
    seasons: 5,
    rating: 'TV-MA',
    description: 'Um professor de química diagnosticado com câncer começa a fabricar metanfetamina para garantir o futuro da família.'
  }),<br>
  (:Series {
    seriesId: 's4',
    title: 'Game of Thrones',
    startYear: 2011,
    endYear: 2019,
    seasons: 8,
    rating: 'TV-MA',
    description: 'Nobres famílias lutam pelo controle do Trono de Ferro dos Sete Reinos de Westeros.'
  }),<br>
  (:Series {
    seriesId: 's5',
    title: 'The Mandalorian',
    startYear: 2019,
    endYear: null,
    seasons: 3,
    rating: 'TV-PG',
    description: 'Um solitário caçador de recompensas trabalha nos confins da galáxia, longe da autoridade da Nova República.'
  }),<br>
  
  // 10 Usuários
  (:User {
    userId: 'u1',
    name: 'Ana Silva',
    email: 'ana@email.com',
    joinDate: date('2022-01-15'),
    subscription: 'Premium',
    country: 'Brasil'
  }),<br>
  (:User {
    userId: 'u2',
    name: 'Carlos Santos',
    email: 'carlos@email.com',
    joinDate: date('2021-03-22'),
    subscription: 'Basic',
    country: 'Portugal'
  }),<br>
  (:User {
    userId: 'u3',
    name: 'Mariana Oliveira',
    email: 'mariana@email.com',
    joinDate: date('2023-02-10'),
    subscription: 'Premium',
    country: 'Brasil'
  }),<br>
  (:User {
    userId: 'u4',
    name: 'João Pereira',
    email: 'joao@email.com',
    joinDate: date('2020-11-05'),
    subscription: 'Family',
    country: 'Portugal'
  }),<br>
  (:User {
    userId: 'u5',
    name: 'Beatriz Costa',
    email: 'beatriz@email.com',
    joinDate: date('2022-07-18'),
    subscription: 'Premium',
    country: 'Brasil'
  }),<br>
  (:User {
    userId: 'u6',
    name: 'Rafael Alves',
    email: 'rafael@email.com',
    joinDate: date('2021-09-30'),
    subscription: 'Basic',
    country: 'Brasil'
  }),<br>
  (:User {
    userId: 'u7',
    name: 'Camila Rodrigues',
    email: 'camila@email.com',
    joinDate: date('2023-04-12'),
    subscription: 'Premium',
    country: 'Portugal'
  }),<br>
  (:User {
    userId: 'u8',
    name: 'Lucas Lima',
    email: 'lucas@email.com',
    joinDate: date('2020-05-25'),
    subscription: 'Family',
    country: 'Brasil'
  }),<br>
  (:User {
    userId: 'u9',
    name: 'Juliana Fernandes',
    email: 'juliana@email.com',
    joinDate: date('2022-12-01'),
    subscription: 'Basic',
    country: 'Portugal'
  }),<br>
  (:User {
    userId: 'u10',
    name: 'Pedro Martins',
    email: 'pedro@email.com',
    joinDate: date('2021-06-14'),
    subscription: 'Premium',
    country: 'Brasil'
  });<br>


// Filmes por gênero (cada filme pode ter múltiplos gêneros)<br>
MATCH (m:Movie {movieId: 'm1'}), (g:Genre {genreId: 'g4'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm1'}), (g:Genre {genreId: 'g5'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm1'}), (g:Genre {genreId: 'g7'}) CREATE (m)-[:IN_GENRE]->(g);<br>

MATCH (m:Movie {movieId: 'm2'}), (g:Genre {genreId: 'g3'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm2'}), (g:Genre {genreId: 'g2'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm2'}), (g:Genre {genreId: 'g2'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm2'}), (g:Genre {genreId: 'g5'}) CREATE (m)-[:IN_GENRE]->(g);<br>

MATCH (m:Movie {movieId: 'm3'}), (g:Genre {genreId: 'g4'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm3'}), (g:Genre {genreId: 'g7'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm3'}), (g:Genre {genreId: 'g1'}) CREATE (m)-[:IN_GENRE]->(g);<br>

MATCH (m:Movie {movieId: 'm4'}), (g:Genre {genreId: 'g3'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm4'}), (g:Genre {genreId: 'g5'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm4'}), (g:Genre {genreId: 'g1'}) CREATE (m)-[:IN_GENRE]->(g);<br>

MATCH (m:Movie {movieId: 'm5'}), (g:Genre {genreId: 'g2'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm5'}), (g:Genre {genreId: 'g7'}) CREATE (m)-[:IN_GENRE]->(g);<br>
MATCH (m:Movie {movieId: 'm5'}), (g:Genre {genreId: 'g6'}) CREATE (m)-[:IN_GENRE]->(g);<br>

// Séries por gênero<br>
MATCH (s:Series {seriesId: 's1'}), (g:Genre {genreId: 'g7'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's1'}), (g:Genre {genreId: 'g5'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's1'}), (g:Genre {genreId: 'g8'}) CREATE (s)-[:IN_GENRE]->(g);<br>

MATCH (s:Series {seriesId: 's2'}), (g:Genre {genreId: 'g3'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's2'}), (g:Genre {genreId: 'g9'}) CREATE (s)-[:IN_GENRE]->(g);<br>

MATCH (s:Series {seriesId: 's3'}), (g:Genre {genreId: 'g3'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's3'}), (g:Genre {genreId: 'g5'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's3'}), (g:Genre {genreId: 'g1'}) CREATE (s)-[:IN_GENRE]->(g);<br>

MATCH (s:Series {seriesId: 's4'}), (g:Genre {genreId: 'g7'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's4'}), (g:Genre {genreId: 'g1'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's4'}), (g:Genre {genreId: 'g3'}) CREATE (s)-[:IN_GENRE]->(g);<br>

MATCH (s:Series {seriesId: 's5'}), (g:Genre {genreId: 'g4'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's5'}), (g:Genre {genreId: 'g1'}) CREATE (s)-[:IN_GENRE]->(g);<br>
MATCH (s:Series {seriesId: 's5'}), (g:Genre {genreId: 'g7'}) CREATE (s)-[:IN_GENRE]->(g);<br>


MATCH (m:Movie {movieId: 'm1'}), (d:Director {directorId: 'd1'}) CREATE (d)-[:DIRECTED {year: 2010}]->(m);<br>
MATCH (m:Movie {movieId: 'm2'}), (d:Director {directorId: 'd5'}) CREATE (d)-[:DIRECTED {year: 2019}]->(m);<br>
MATCH (m:Movie {movieId: 'm3'}), (d:Director {directorId: 'd9'}) CREATE (d)-[:DIRECTED {year: 2021}]->(m);<br>
MATCH (m:Movie {movieId: 'm4'}), (d:Director {directorId: 'd8'}) CREATE (d)-[:DIRECTED {year: 1972}]->(m);<br>
MATCH (m:Movie {movieId: 'm5'}), (d:Director {directorId: 'd7'}) CREATE (d)-[:DIRECTED {year: 2023}]->(m);<br>


// Atores em filmes<br>
MATCH (m:Movie {movieId: 'm1'}), (a:Actor {actorId: 'a1'}) CREATE (a)-[:ACTED_IN {role: 'Dom Cobb', year: 2010}]->(m);<br>
MATCH (m:Movie {movieId: 'm1'}), (a:Actor {actorId: 'a6'}) CREATE (a)-[:ACTED_IN {role: 'Ariadne', year: 2010}]->(m);<br>

MATCH (m:Movie {movieId: 'm2'}), (a:Actor {actorId: 'a3'}) CREATE (a)-[:ACTED_IN {role: 'Kim Ki-woo', year: 2019}]->(m);<br>

MATCH (m:Movie {movieId: 'm3'}), (a:Actor {actorId: 'a9'}) CREATE (a)-[:ACTED_IN {role: 'Paul Atreides', year: 2021}]->(m);<br>
MATCH (m:Movie {movieId: 'm3'}), (a:Actor {actorId: 'a10'}) CREATE (a)-[:ACTED_IN {role: 'Princess Irulan', year: 2021}]->(m);<br>
MATCH (m:Movie {movieId: 'm3'}), (a:Actor {actorId: 'a5'}) CREATE (a)-[:ACTED_IN {role: 'Emperor Shaddam IV', year: 2021}]->(m);<br>

MATCH (m:Movie {movieId: 'm4'}), (a:Actor {actorId: 'a1'}) CREATE (a)-[:ACTED_IN {role: 'Michael Corleone', year: 1972}]->(m);<br>
MATCH (m:Movie {movieId: 'm4'}), (a:Actor {actorId: 'a2'}) CREATE (a)-[:ACTED_IN {role: 'Kay Adams', year: 1972}]->(m);<br>

MATCH (m:Movie {movieId: 'm5'}), (a:Actor {actorId: 'a6'}) CREATE (a)-[:ACTED_IN {role: 'Barbie', year: 2023}]->(m);<br>
MATCH (m:Movie {movieId: 'm5'}), (a:Actor {actorId: 'a9'}) CREATE (a)-[:ACTED_IN {role: 'Ken', year: 2023}]->(m);<br>

// Atores em séries
MATCH (s:Series {seriesId: 's1'}), (a:Actor {actorId: 'a10'}) CREATE (a)-[:ACTED_IN {role: 'Maxine', year: 2022}]->(s);<br>
MATCH (s:Series {seriesId: 's2'}), (a:Actor {actorId: 'a2'}) CREATE (a)-[:ACTED_IN {role: 'Rainha Elizabeth II', year: 2016}]->(s);<br>
MATCH (s:Series {seriesId: 's3'}), (a:Actor {actorId: 'a5'}) CREATE (a)-[:ACTED_IN {role: 'Walter White', year: 2008}]->(s);<br>
MATCH (s:Series {seriesId: 's4'}), (a:Actor {actorId: 'a4'}) CREATE (a)-[:ACTED_IN {role: 'Daenerys Targaryen', year: 2011}]->(s);<br>
MATCH (s:Series {seriesId: 's5'}), (a:Actor {actorId: 'a8'}) CREATE (a)-[:ACTED_IN {role: 'Chani', year: 2019}]->(s);<br>


// Usuários assistindo filmes<br>
MATCH (u:User {userId: 'u1'}), (m:Movie {movieId: 'm1'})<br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-05-10'), watchTime: 148, platform: 'Web'}]->(m);<br>

MATCH (u:User {userId: 'u2'}), (m:Movie {movieId: 'm2'}) <br>
CREATE (u)-[:WATCHED {rating: 4, date: date('2023-06-15'), watchTime: 132, platform: 'Mobile'}]->(m);<br>

MATCH (u:User {userId: 'u3'}), (m:Movie {movieId: 'm3'}) <br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-07-20'), watchTime: 155, platform: 'TV'}]->(m);<br>

MATCH (u:User {userId: 'u4'}), (m:Movie {movieId: 'm4'}) <br>
CREATE (u)-[:WATCHED {rating: 3, date: date('2023-08-05'), watchTime: 175, platform: 'Web'}]->(m);<br>

MATCH (u:User {userId: 'u5'}), (m:Movie {movieId: 'm5'}) <br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-09-12'), watchTime: 114, platform: 'Mobile'}]->(m);<br>

// Usuários assistindo séries<br>
MATCH (u:User {userId: 'u6'}), (s:Series {seriesId: 's1'}) <br>
CREATE (u)-[:WATCHED {rating: 4, date: date('2023-10-01'), episodesWatched: 8, season: 1, platform: 'TV'}]->(s);<br>

MATCH (u:User {userId: 'u7'}), (s:Series {seriesId: 's2'}) <br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-10-05'), episodesWatched: 10, season: 2, platform: 'Web'}]->(s);<br>

MATCH (u:User {userId: 'u8'}), (s:Series {seriesId: 's3'}) <br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-10-10'), episodesWatched: 62, season: 5, platform: 'Mobile'}]->(s);<br>

MATCH (u:User {userId: 'u9'}), (s:Series {seriesId: 's4'}) <br>
CREATE (u)-[:WATCHED {rating: 4, date: date('2023-10-15'), episodesWatched: 73, season: 8, platform: 'TV'}]->(s);<br>

MATCH (u:User {userId: 'u10'}), (s:Series {seriesId: 's5'}) <br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-10-20'), episodesWatched: 24, season: 3, platform: 'Web'}]->(s);<br>

// Relacionamentos adicionais para enriquecer o grafo - múltiplos usuários assistindo o mesmo conteúdo<br>
MATCH (u:User {userId: 'u1'}), (s:Series {seriesId: 's5'}) <br>
CREATE (u)-[:WATCHED {rating: 4, date: date('2023-10-25'), episodesWatched: 16, season: 2, platform: 'Mobile'}]->(s);<br>

MATCH (u:User {userId: 'u2'}), (m:Movie {movieId: 'm1'}) <br>
CREATE (u)-[:WATCHED {rating: 4, date: date('2023-10-18'), watchTime: 148, platform: 'TV'}]->(m);<br>

MATCH (u:User {userId: 'u3'}), (s:Series {seriesId: 's1'}) <br>
CREATE (u)-[:WATCHED {rating: 5, date: date('2023-11-01'), episodesWatched: 25, season: 3, platform: 'Web'}]->(s);<br>

MATCH (u:User {userId: 'u4'}), (m:Movie {movieId: 'm3'}) <br>
CREATE (u)-[:WATCHED {rating: 4, date: date('2023-11-05'), watchTime: 155, platform: 'Mobile'}]->(m);<br>

MATCH (u:User {userId: 'u5'}), (s:Series {seriesId: 's2'}) <br>
CREATE (u)-[:WATCHED {rating: 3, date: date('2023-11-10'), episodesWatched: 6, season: 1, platform: 'TV'}]->(s);<br>


// Verificar a contagem de nós por tipo<br>
MATCH (n) <br>
RETURN labels(n) as NodeType, count(*) as Count
ORDER BY Count DESC;<br>

// Verificar relacionamentos por tipo
MATCH ()-[r]->() <br>
RETURN type(r) as RelationshipType, count(*) as Count
ORDER BY Count DESC;<br>

// Consulta: Conteúdo mais bem avaliado<br>
MATCH (u:User)-[w:WATCHED]->(content)<br>
WHERE w.rating >= 4<br>
RETURN content.title as Title, labels(content) as Type, <br>
       avg(w.rating) as AverageRating, count(w) as NumberOfViews<br>
ORDER BY AverageRating DESC<br>
LIMIT 10;<br>

// Consulta: Recomendações baseadas em gênero<br>
MATCH (u:User {userId: 'u1'})-[:WATCHED]->(content)-[:IN_GENRE]->(g:Genre)<-[:IN_GENRE]-(similar)<br>
WHERE NOT EXISTS ((u)-[:WATCHED]->(similar))<br>
RETURN g.name as PreferredGenre, similar.title as Recommendation, labels<br>(similar) as Type<br>
LIMIT 10;<br>

// Consulta: Atores mais populares (com mais conteúdo assistido)<br>
MATCH (a:Actor)-[:ACTED_IN]->(content)<-[:WATCHED]-(u:User)<br>
RETURN a.name as Actor, count(DISTINCT u) as UserCount, count(DISTINCT content)<br> as ContentCount<br>
ORDER BY UserCount DESC<br>
LIMIT 10;<br>

// Consulta: Diretores mais assistidos<br>
MATCH (d:Director)-[:DIRECTED]->(m:Movie)<-[:WATCHED]-(u:User)<br>
RETURN d.name as Director, count(DISTINCT u) as UserCount, count(DISTINCT m) as MovieCount<br>
ORDER BY UserCount DESC<br>
LIMIT 10;<br>

// Consulta: Conteúdo por gênero<br>
MATCH (g:Genre)<-[:IN_GENRE]-(content)<br>
RETURN g.name as Genre, labels(content) as ContentType, count(*) as ContentCount
ORDER BY Genre, ContentType;

// Mensagem de sucesso
RETURN "Banco de dados populado com sucesso!" as Status,
       "Estatísticas: 10 Usuários, 5 Filmes, 5 Séries, 10 Atores, 10 Diretores,<br> 10 Gêneros" as Details;<br>

### O resultado do grafo é essa imagem abaixo:
![Profile_ico][def]

[def]: images/visualisation.png