Config Tailwind With CLI (NodeJS)

Instal plugin VSCODE:
- Tailwind Css IntelliSense
- Live Preview
- PostCss Language Support

Asumsi sudah install Nodejs D Sistem:
- npm init -y (-y default configurasi)
- npm install -D tailwindcss postcss autoprefixer -> instal tailwind dkk
  (untuk versi nodejs 16 ke atas tidak perlu mengetik/ install postcss dan autoprefixer karana sudah otomatis di install tailwindnya)
- npx tailwindcss init -> file config tailwind

file input.css:
@tailwind - akan bisa di baca ketika sudah menginstal plugin postcss di vscode

Kemuadian tambahkan pada file input.css:
@tailwind base; - reset css dari browsernya
@tailwind components; - meminta component dalam librarynya (container,grid system dll)
@tailwind utilities; - memanggil class utilities yang akan di pakai

config path content pada file tailwind.config.js:
- content: ['./public/**/*.{html,js}']
- pada path :
	** - cek apapun folder di dalamnya
	*  - apapun filenya yang di tampilkan dalam kurung kurawal

build
npx tailwindcss -i ./src/css/input.css -o ./public/css/style.css --watch

Untuk menghilangkan class di style.css yang tidak terpakai
- restart builder
- save file config tailwindcssnya

Agar tidak mengetik script builder tailwindcss yang panjang:
- letakan script (npx tailwindcss -i ./src/css/input.css -o ./public/css/style.css --watch)
  di file package.json pada bagian script :
  "dev" : "npx tailwindcss -i ./src/css/input.css -o ./public/css/style.css --watch"
  
Untuk memperkecil file style.css / output builder setelah selesai (final) mendevlop ketik script:
- npx tailwindscss -o ./public/css/final.css --minify
- Dan jangan lupa ubah link pada tag <link> untuk file cssnya di index htmlnya