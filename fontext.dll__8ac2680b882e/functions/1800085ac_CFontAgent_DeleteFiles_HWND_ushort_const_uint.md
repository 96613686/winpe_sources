# CFontAgent::_DeleteFiles(HWND__ *,ushort const * *,uint)

- ea: `0x1800085ac`
- end: `0x1800087c9`
- name: `?_DeleteFiles@CFontAgent@@IEAAJPEAUHWND__@@PEAPEBGI@Z`
- size: `541`
- prototype: `__int64 __fastcall(CFontAgent *__hidden this, HWND, const unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x1800081a0`
- `0x180008200`

## callees

- `0x180008404`
- `0x1800085ac`
- `0x1800134d8`
- `0x180013880`
- `0x1800139f4`
- `0x180031070`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000870b`
- `msvcrt!swprintf_s` at `0x18000870b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008778`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000864c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800086b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008716`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000864c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800086b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008716`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008663`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180008663`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000866c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000866c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000873b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000876e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000873b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000876e`

## pseudocode

```c
__int64 __fastcall CFontAgent::_DeleteFiles(CFontAgent *this, HWND a2, const unsigned __int16 **a3, unsigned int a4)
{
  signed int DeletedFontsDirectory; // ebx
  __int64 v8; // rcx
  int v9; // r12d
  unsigned int v10; // edi
  int v11; // eax
  unsigned int i; // r15d
  const WCHAR *v13; // r14
  DWORD FileAttributesW; // eax
  unsigned int v15; // r9d
  __int64 v16; // rax
  int v17; // edi
  WCHAR *v18; // rax
  wchar_t *v19; // r12
  signed int LastError; // eax
  signed int v21; // eax
  __int64 v22; // [rsp+20h] [rbp-E0h]
  LPCWSTR pszDir; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR FileName[256]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v25[8]; // [rsp+230h] [rbp+130h] BYREF

  if ( !a4 )
    return 0;
  DeletedFontsDirectory = 0;
  v9 = PathIsInFontsDirectory(1, *a3);
  v10 = 0;
  LODWORD(v22) = v9;
  do
  {
    if ( DeletedFontsDirectory < 0 )
      break;
    v11 = CFontAgent::_CheckDeletePermision((CFontAgent *)v8, a3[v10]);
    v8 = 2147942405LL;
    if ( !v11 )
      DeletedFontsDirectory = -2147024891;
    ++v10;
  }
  while ( v10 < a4 );
  for ( i = 0; i < a4; ++i )
  {
    if ( DeletedFontsDirectory < 0 )
      break;
    v13 = a3[i];
    FileAttributesW = GetFileAttributesW(v13);
    if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
      SetFileAttributesW(v13, FileAttributesW & 0xFFFFFFFE);
    if ( !DeleteFileW(v13) )
    {
      pszDir = 0;
      DeletedFontsDirectory = GetDeletedFontsDirectory(v9, &pszDir);
      if ( DeletedFontsDirectory < 0 )
      {
        FileName[0] = 0;
      }
      else
      {
        DeletedFontsDirectory = PathAppendFileToDirectory(FileName, pszDir, v13, v15);
        if ( DeletedFontsDirectory >= 0 )
        {
          if ( GetFileAttributesW(FileName) != -1 )
          {
            v16 = -1;
            do
              ++v16;
            while ( FileName[v16] );
            v17 = 1;
            v18 = &FileName[v16];
            v19 = v25;
            if ( v18 < v25 )
              v19 = v18;
            do
            {
              swprintf_s(v19, 4u, L"%d", (unsigned int)v17, v22);
              if ( GetFileAttributesW(FileName) == -1 )
                break;
              ++v17;
            }
            while ( v17 <= 999 );
            v9 = v22;
          }
          if ( MoveFileExW(v13, FileName, 0) )
            goto LABEL_37;
          LastError = GetLastError();
          DeletedFontsDirectory = LastError;
          if ( LastError > 0 )
            DeletedFontsDirectory = (unsigned __int16)LastError | 0x80070000;
          if ( DeletedFontsDirectory >= 0 )
          {
LABEL_37:
            if ( v9 && !MoveFileExW(FileName, 0, 4u) )
            {
              v21 = GetLastError();
              DeletedFontsDirectory = v21;
              if ( v21 > 0 )
                DeletedFontsDirectory = (unsigned __int16)v21 | 0x80070000;
            }
          }
        }
      }
    }
  }
  return (unsigned int)DeletedFontsDirectory;
}

```

## disassembly

```asm
0x1800085ac  push    rbp
0x1800085ae  push    rbx
0x1800085af  push    rsi
0x1800085b0  push    rdi
0x1800085b1  push    r12
0x1800085b3  push    r13
0x1800085b5  push    r14
0x1800085b7  push    r15
0x1800085b9  lea     rbp, [rsp-158h]
0x1800085c1  sub     rsp, 258h
0x1800085c8  mov     rax, cs:__security_cookie
0x1800085cf  xor     rax, rsp
0x1800085d2  mov     [rbp+190h+var_50], rax
0x1800085d9  xor     r14d, r14d
0x1800085dc  mov     esi, r9d
0x1800085df  mov     r13, r8
0x1800085e2  test    r9d, r9d
0x1800085e5  jnz     short loc_1800085EE
0x1800085e7  xor     eax, eax
0x1800085e9  jmp     loc_1800087A6
0x1800085ee  mov     rdx, [r8]; unsigned __int16 *
0x1800085f1  mov     ecx, 1; int
0x1800085f6  mov     ebx, r14d
0x1800085f9  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x1800085fe  movzx   r12d, al
0x180008602  mov     edi, r14d
0x180008605  mov     dword ptr [rsp+290h+var_270], r12d
0x18000860a  test    esi, esi
0x18000860c  jz      short loc_18000862E
0x18000860e  test    ebx, ebx
0x180008610  js      short loc_18000862E
0x180008612  mov     edx, edi
0x180008614  mov     rdx, [r13+rdx*8+0]; unsigned __int16 *
0x180008619  call    ?_CheckDeletePermision@CFontAgent@@IEAAHPEBG@Z; CFontAgent::_CheckDeletePermision(ushort const *)
0x18000861e  test    eax, eax
0x180008620  mov     ecx, 80070005h
0x180008625  cmovz   ebx, ecx
0x180008628  inc     edi
0x18000862a  cmp     edi, esi
0x18000862c  jb      short loc_18000860E
0x18000862e  mov     r15d, r14d
0x180008631  test    esi, esi
0x180008633  jz      loc_1800087A4
0x180008639  test    ebx, ebx
0x18000863b  js      loc_1800087A4
0x180008641  mov     eax, r15d
0x180008644  mov     r14, [r13+rax*8+0]
0x180008649  mov     rcx, r14; lpFileName
0x18000864c  call    cs:__imp_GetFileAttributesW
0x180008652  cmp     eax, 0FFFFFFFFh
0x180008655  jz      short loc_180008669
0x180008657  test    al, 1
0x180008659  jz      short loc_180008669
0x18000865b  and     eax, 0FFFFFFFEh
0x18000865e  mov     rcx, r14; lpFileName
0x180008661  mov     edx, eax; dwFileAttributes
0x180008663  call    cs:__imp_SetFileAttributesW
0x180008669  mov     rcx, r14; lpFileName
0x18000866c  call    cs:__imp_DeleteFileW
0x180008672  xor     edi, edi
0x180008674  test    eax, eax
0x180008676  jnz     loc_180008798
0x18000867c  lea     rdx, [rsp+290h+pszDir]; unsigned __int16 **
0x180008681  mov     [rsp+290h+pszDir], rdi
0x180008686  mov     ecx, r12d; int
0x180008689  call    ?GetDeletedFontsDirectory@@YAJHPEAPEBG@Z; GetDeletedFontsDirectory(int,ushort const * *)
0x18000868e  mov     ebx, eax
0x180008690  test    eax, eax
0x180008692  js      loc_18000878F
0x180008698  mov     rdx, [rsp+290h+pszDir]; pszDir
0x18000869d  lea     rcx, [rsp+290h+FileName]; pszDest
0x1800086a2  mov     r8, r14; pszPath
0x1800086a5  call    ?PathAppendFileToDirectory@@YAJPEAGPEBG1I@Z; PathAppendFileToDirectory(ushort *,ushort const *,ushort const *,uint)
0x1800086aa  mov     ebx, eax
0x1800086ac  test    eax, eax
0x1800086ae  js      loc_180008798
0x1800086b4  lea     rcx, [rsp+290h+FileName]; lpFileName
0x1800086b9  call    cs:__imp_GetFileAttributesW
0x1800086bf  cmp     eax, 0FFFFFFFFh
0x1800086c2  jz      short loc_180008730
0x1800086c4  lea     rcx, [rsp+290h+FileName]
0x1800086c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800086cd  inc     rax
0x1800086d0  cmp     [rcx+rax*2], di
0x1800086d4  jnz     short loc_1800086CD
0x1800086d6  lea     rcx, [rsp+290h+FileName]
0x1800086db  mov     edi, 1
0x1800086e0  lea     rax, [rcx+rax*2]
0x1800086e4  lea     rcx, [rbp+190h+var_60]
0x1800086eb  cmp     rax, rcx
0x1800086ee  lea     r12, [rbp+190h+var_60]
0x1800086f5  cmovb   r12, rax
0x1800086f9  mov     r9d, edi
0x1800086fc  lea     r8, aD; "%d"
0x180008703  mov     edx, 4; BufferCount
0x180008708  mov     rcx, r12; Buffer
0x18000870b  call    cs:__imp_swprintf_s
0x180008711  lea     rcx, [rsp+290h+FileName]; lpFileName
0x180008716  call    cs:__imp_GetFileAttributesW
0x18000871c  cmp     eax, 0FFFFFFFFh
0x18000871f  jz      short loc_18000872B
0x180008721  inc     edi
0x180008723  cmp     edi, 3E7h
0x180008729  jle     short loc_1800086F9
0x18000872b  mov     r12d, dword ptr [rsp+290h+var_270]
0x180008730  xor     r8d, r8d; dwFlags
0x180008733  lea     rdx, [rsp+290h+FileName]; lpNewFileName
0x180008738  mov     rcx, r14; lpExistingFileName
0x18000873b  call    cs:__imp_MoveFileExW
0x180008741  test    eax, eax
0x180008743  jnz     short loc_18000875E
0x180008745  call    cs:__imp_GetLastError
0x18000874b  mov     ebx, eax
0x18000874d  test    eax, eax
0x18000874f  jle     short loc_18000875A
0x180008751  movzx   ebx, ax
0x180008754  or      ebx, 80070000h
0x18000875a  test    ebx, ebx
0x18000875c  js      short loc_180008798
0x18000875e  test    r12d, r12d
0x180008761  jz      short loc_180008798
0x180008763  xor     edx, edx; lpNewFileName
0x180008765  lea     rcx, [rsp+290h+FileName]; lpExistingFileName
0x18000876a  lea     r8d, [rdx+4]; dwFlags
0x18000876e  call    cs:__imp_MoveFileExW
0x180008774  test    eax, eax
0x180008776  jnz     short loc_180008798
0x180008778  call    cs:__imp_GetLastError
0x18000877e  mov     ebx, eax
0x180008780  test    eax, eax
0x180008782  jle     short loc_180008798
0x180008784  movzx   ebx, ax
0x180008787  or      ebx, 80070000h
0x18000878d  jmp     short loc_180008798
0x18000878f  xor     r14d, r14d
0x180008792  mov     [rsp+290h+FileName], r14w
0x180008798  inc     r15d
0x18000879b  cmp     r15d, esi
0x18000879e  jb      loc_180008639
0x1800087a4  mov     eax, ebx
0x1800087a6  mov     rcx, [rbp+190h+var_50]
0x1800087ad  xor     rcx, rsp; StackCookie
0x1800087b0  call    __security_check_cookie
0x1800087b5  add     rsp, 258h
0x1800087bc  pop     r15
0x1800087be  pop     r14
0x1800087c0  pop     r13
0x1800087c2  pop     r12
0x1800087c4  pop     rdi
0x1800087c5  pop     rsi
0x1800087c6  pop     rbx
0x1800087c7  pop     rbp
0x1800087c8  retn
```
