# I_UrlCacheEnum

- ea: `0x1800052d0`
- end: `0x1800058eb`
- name: `I_UrlCacheEnum`
- size: `1563`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005b30`
- `0x180005f10`

## callees

- `0x1800052d0`
- `0x180005900`
- `0x1800077b0`
- `0x18000a990`
- `0x18001bb18`
- `0x180026552`
- `0x18002656a`
- `0x1800265b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800056c1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800056c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000540a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000584c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000585c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000540a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000584c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000585c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000568c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000568c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000567b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000567b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800054f0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800054f0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180005578`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180005578`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005419`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005419`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000538c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800053a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000538c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800053a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005402`

## pseudocode

```c
__int64 __fastcall I_UrlCacheEnum(
        _WORD *Src,
        _WORD *a2,
        char a3,
        __int64 a4,
        unsigned int (__fastcall *a5)(_DWORD *, _QWORD, _WIN32_FIND_DATAW *, __int64))
{
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r13
  char *v10; // r15
  char *v11; // r12
  __int64 FirstFileW; // r14
  DWORD v13; // edi
  unsigned int v14; // esi
  DWORD v15; // ebx
  DWORD v16; // ebx
  size_t v18; // rbx
  __int64 v19; // r8
  char *v20; // rax
  __int64 v21; // rdx
  const wchar_t *v22; // r9
  char *v23; // rcx
  __int64 v24; // rdi
  DWORD v25; // eax
  DWORD LastError; // eax
  __int64 i; // rbx
  HANDLE FileW; // rax
  DWORD v29; // eax
  bool v30; // cf
  _DWORD *v31; // rbx
  _DWORD *v32; // rcx
  _WIN32_FIND_DATAW *p_FindFileData; // r8
  unsigned int v34; // ebx
  int v35; // [rsp+40h] [rbp-C0h]
  int v36; // [rsp+44h] [rbp-BCh]
  HANDLE hObject; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __int128 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+90h] [rbp-70h]
  HLOCAL hMem; // [rsp+98h] [rbp-68h]
  _DWORD v45[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-58h]
  int v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v49[4]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v50; // [rsp+E0h] [rbp-20h]
  __int128 *v51; // [rsp+E8h] [rbp-18h]
  _WORD *v52; // [rsp+F0h] [rbp-10h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF
  _WORD v54[40]; // [rsp+350h] [rbp+250h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( Src )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( (unsigned int)v8 > 0x21 )
      LODWORD(v8) = 33;
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v9 = (unsigned int)(v7 + 9);
  v35 = v7 + 8;
  v10 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v7 + 75));
  if ( !v10 )
    SetLastError(0x8007000E);
  v11 = (char *)LocalAlloc(0, 2LL * (unsigned int)(v7 + 74));
  if ( !v11 )
    SetLastError(0x8007000E);
  if ( !v10 || !v11 )
  {
    FirstFileW = -1;
    goto LABEL_15;
  }
  v18 = 2LL * (unsigned int)v7;
  memcpy_0(v10, Src, v18);
  *(_OWORD *)&v10[v18] = *(_OWORD *)L"MetaData";
  *(_WORD *)&v10[2 * (unsigned int)(v9 - 1)] = 92;
  if ( (_DWORD)v8 )
    memcpy_0(&v10[2 * v9], a2, 2LL * (unsigned int)v8);
  v19 = 2147483646;
  v20 = &v10[2 * (unsigned int)(v8 + v9)];
  v21 = 2;
  v22 = L"*";
  do
  {
    if ( !v19 )
      break;
    if ( !*v22 )
      break;
    *(_WORD *)v20 = *v22++;
    v20 += 2;
    --v19;
    --v21;
  }
  while ( v21 );
  v23 = v20 - 2;
  if ( v21 )
    v23 = v20;
  *(_WORD *)v23 = 0;
  FirstFileW = (__int64)FindFirstFileW((LPCWSTR)v10, &FindFileData);
  if ( FirstFileW == -1 )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
      LastError = 2;
    SetLastError(LastError);
LABEL_15:
    v13 = GetLastError();
    v14 = 0;
    if ( !v10 )
      goto LABEL_17;
    goto LABEL_16;
  }
  memcpy_0(v11, Src, v18);
  v14 = 1;
  *(_QWORD *)&v11[v18] = *(_QWORD *)L"Content";
  *(_DWORD *)&v11[v18 + 8] = *(_DWORD *)L"ent";
  *(_WORD *)&v11[v18 + 12] = aContent[6];
  *(_WORD *)&v11[2 * (v35 - 1)] = 92;
  do
  {
    v24 = -1;
    do
      ++v24;
    while ( FindFileData.cFileName[v24] );
    if ( (FindFileData.dwFileAttributes & 0x10) == 0
      && !FindFileData.nFileSizeHigh
      && FindFileData.nFileSizeLow
      && FindFileData.cFileName[0]
      && (unsigned int)v24 < 0x42 )
    {
      if ( (a3 & 1) != 0 )
      {
        if ( !a5(0, 0, 0, a4) )
          goto LABEL_15;
      }
      else
      {
        v36 = 0;
        if ( (a3 & 2) == 0 || (v36 = 1, a5(0, 0, &FindFileData, a4)) )
        {
          memcpy_0(&v10[2 * v9], FindFileData.cFileName, 2LL * (unsigned int)(v24 + 1));
          memcpy_0(&v11[2 * v35], FindFileData.cFileName, 2LL * (unsigned int)(v24 + 1));
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            FileW = CreateFileW((LPCWSTR)v10, 0x80000000, 1u, 0, 3u, 0x80u, 0);
            hObject = FileW;
            if ( FileW != (HANDLE)-1LL )
              break;
            v29 = GetLastError();
            if ( v29 == 32 )
            {
              v30 = (unsigned int)i < 6;
            }
            else
            {
              if ( v29 != 5 )
              {
                if ( v29 == 3 )
                  v29 = 2;
LABEL_56:
                SetLastError(v29);
                goto LABEL_36;
              }
              v30 = (_DWORD)i == 0;
            }
            if ( !v30 )
              goto LABEL_56;
            Sleep(*((_DWORD *)qword_18002BA20 + i));
          }
          if ( FileW )
          {
            memset_0(v45, 0, 0x58u);
            v43 = 0;
            v40 = 0;
            v41 = 0;
            v42 = 0;
            v31 = I_UrlCacheReadAndValidateMetaDataFile(hObject, &v48, v49, 0, &v40);
            hMem = v31;
            I_UrlCacheCloseHandle(hObject);
            if ( v31 )
            {
              v45[0] = 88;
              v45[1] = v31[1];
              v46 = *((_QWORD *)v31 + 2);
              v47 = v31[2];
              v32 = v31 + 6;
              v49[1] = v10;
              v49[2] = v11;
              if ( !v31[7] )
                v32 = 0;
              v49[3] = v32;
              if ( v31[17] || v31[18] || v31[19] )
                v50 = v31 + 16;
              else
                v50 = 0;
              if ( *((_WORD *)v31 + 42) )
              {
                v41 = 0;
                v51 = &v41;
                v43 = 0;
                v42 = 0;
                LODWORD(v41) = 40;
                DWORD1(v41) = v31[21];
                *((_QWORD *)&v41 + 1) = *((_QWORD *)v31 + 11);
                LODWORD(v42) = v31[24];
                LODWORD(v43) = v31[26];
                *((_QWORD *)&v42 + 1) = v40;
              }
              else
              {
                v51 = 0;
              }
              if ( (unsigned int)v24 <= 0x20 )
              {
                v52 = 0;
              }
              else
              {
                memcpy_0(v54, FindFileData.cFileName, 2LL * (unsigned int)(v24 - 32));
                if ( 2 * (unsigned __int64)(unsigned int)(v24 - 32) >= 0x44 )
                  _report_rangecheckfailure();
                v54[(unsigned int)(v24 - 32)] = 0;
                v52 = v54;
              }
              p_FindFileData = &FindFileData;
              if ( !v36 )
                p_FindFileData = 0;
              v34 = a5(v45, 0, p_FindFileData, a4);
              operator delete(hMem);
              if ( !v34 )
                goto LABEL_15;
            }
          }
        }
      }
    }
LABEL_36:
    ;
  }
  while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
  v25 = GetLastError();
  v13 = v25;
  if ( v25 != 18 )
  {
    SetLastError(v25);
    goto LABEL_15;
  }
LABEL_16:
  v15 = GetLastError();
  LocalFree(v10);
  SetLastError(v15);
LABEL_17:
  if ( v11 )
  {
    v16 = GetLastError();
    LocalFree(v11);
    SetLastError(v16);
  }
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  SetLastError(v13);
  return v14;
}

```

## disassembly

```asm
0x1800052d0  push    rbp
0x1800052d2  push    rbx
0x1800052d3  push    rsi
0x1800052d4  push    r12
0x1800052d6  push    r13
0x1800052d8  push    r14
0x1800052da  push    r15
0x1800052dc  lea     rbp, [rsp-2B0h]
0x1800052e4  sub     rsp, 3B0h
0x1800052eb  mov     rax, cs:__security_cookie
0x1800052f2  xor     rax, rsp
0x1800052f5  mov     [rbp+2E0h+var_40], rax
0x1800052fc  mov     rax, [rbp+2E0h+arg_20]
0x180005303  mov     r14, rdx
0x180005306  mov     [rsp+3E0h+var_398], r8d
0x18000530b  mov     rsi, rcx
0x18000530e  xor     edx, edx; Val
0x180005310  mov     [rsp+3E0h+var_388], rax
0x180005315  mov     r8d, 250h; Size
0x18000531b  mov     [rsp+3E0h+var_390], r9
0x180005320  lea     rcx, [rbp+2E0h+FindFileData]; void *
0x180005324  call    memset_0
0x180005329  test    rsi, rsi
0x18000532c  jz      loc_18000582F
0x180005332  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005339  nop     dword ptr [rax+00000000h]
0x180005340  inc     rbx
0x180005343  cmp     word ptr [rsi+rbx*2], 0
0x180005348  jnz     short loc_180005340
0x18000534a  mov     [rsp+3E0h+arg_10], rdi
0x180005352  test    r14, r14
0x180005355  jz      loc_180005840
0x18000535b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180005362  inc     rdi
0x180005365  cmp     word ptr [r14+rdi*2], 0
0x18000536b  jnz     short loc_180005362
0x18000536d  cmp     edi, 21h ; '!'
0x180005370  ja      loc_180005836
0x180005376  lea     r13d, [rbx+9]
0x18000537a  xor     ecx, ecx; uFlags
0x18000537c  lea     edx, [r13+42h]
0x180005380  lea     r12d, [rbx+8]
0x180005384  add     rdx, rdx; uBytes
0x180005387  mov     [rsp+3E0h+var_3A0], r12d
0x18000538c  call    cs:__imp_LocalAlloc
0x180005392  mov     r15, rax
0x180005395  test    rax, rax
0x180005398  jz      loc_180005847
0x18000539e  lea     edx, [r12+42h]
0x1800053a3  xor     ecx, ecx; uFlags
0x1800053a5  add     rdx, rdx; uBytes
0x1800053a8  call    cs:__imp_LocalAlloc
0x1800053ae  mov     r12, rax
0x1800053b1  test    rax, rax
0x1800053b4  jz      loc_180005857
0x1800053ba  test    r15, r15
0x1800053bd  jnz     loc_180005453
0x1800053c3  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800053ca  call    cs:__imp_GetLastError
0x1800053d0  mov     edi, eax
0x1800053d2  xor     esi, esi
0x1800053d4  test    r15, r15
0x1800053d7  jz      short loc_1800053F2
0x1800053d9  call    cs:__imp_GetLastError
0x1800053df  mov     rcx, r15; hMem
0x1800053e2  mov     ebx, eax
0x1800053e4  call    cs:__imp_LocalFree
0x1800053ea  mov     ecx, ebx; dwErrCode
0x1800053ec  call    cs:__imp_SetLastError
0x1800053f2  test    r12, r12
0x1800053f5  jz      short loc_180005410
0x1800053f7  call    cs:__imp_GetLastError
0x1800053fd  mov     rcx, r12; hMem
0x180005400  mov     ebx, eax
0x180005402  call    cs:__imp_LocalFree
0x180005408  mov     ecx, ebx; dwErrCode
0x18000540a  call    cs:__imp_SetLastError
0x180005410  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180005414  jz      short loc_18000541F
0x180005416  mov     rcx, r14; hFindFile
0x180005419  call    cs:__imp_FindClose
0x18000541f  mov     ecx, edi; dwErrCode
0x180005421  call    cs:__imp_SetLastError
0x180005427  mov     rdi, [rsp+3E0h+arg_10]
0x18000542f  mov     eax, esi
0x180005431  mov     rcx, [rbp+2E0h+var_40]
0x180005438  xor     rcx, rsp; StackCookie
0x18000543b  call    __security_check_cookie
0x180005440  add     rsp, 3B0h
0x180005447  pop     r15
0x180005449  pop     r14
0x18000544b  pop     r13
0x18000544d  pop     r12
0x18000544f  pop     rsi
0x180005450  pop     rbx
0x180005451  pop     rbp
0x180005452  retn
0x180005453  test    r12, r12
0x180005456  jz      loc_1800053C3
0x18000545c  mov     ecx, ebx
0x18000545e  mov     rdx, rsi; Src
0x180005461  lea     rbx, [rcx+rcx]
0x180005465  mov     rcx, r15; void *
0x180005468  mov     r8, rbx; Size
0x18000546b  call    memcpy_0
0x180005470  lea     eax, [r13-1]
0x180005474  movups  xmm0, xmmword ptr cs:aMetadata; "MetaData"
0x18000547b  movups  xmmword ptr [rbx+r15], xmm0
0x180005480  mov     word ptr [r15+rax*2], 5Ch ; '\'
0x180005487  test    edi, edi
0x180005489  jz      short loc_18000549D
0x18000548b  mov     r8d, edi
0x18000548e  lea     rcx, [r15+r13*2]; void *
0x180005492  add     r8, r8; Size
0x180005495  mov     rdx, r14; Src
0x180005498  call    memcpy_0
0x18000549d  lea     eax, [rdi+r13]
0x1800054a1  mov     r8d, 7FFFFFFEh
0x1800054a7  lea     rax, [r15+rax*2]
0x1800054ab  mov     edx, 2
0x1800054b0  lea     r9, asc_180029120; "*"
0x1800054b7  test    r8, r8
0x1800054ba  jz      short loc_1800054D9
0x1800054bc  movzx   ecx, word ptr [r9]
0x1800054c0  test    cx, cx
0x1800054c3  jz      short loc_1800054D9
0x1800054c5  mov     [rax], cx
0x1800054c8  add     r9, 2
0x1800054cc  add     rax, 2
0x1800054d0  dec     r8
0x1800054d3  sub     rdx, 1
0x1800054d7  jnz     short loc_1800054B7
0x1800054d9  test    rdx, rdx
0x1800054dc  lea     rcx, [rax-2]
0x1800054e0  lea     rdx, [rbp+2E0h+FindFileData]; lpFindFileData
0x1800054e4  cmovnz  rcx, rax
0x1800054e8  xor     eax, eax
0x1800054ea  mov     [rcx], ax
0x1800054ed  mov     rcx, r15; lpFileName
0x1800054f0  call    cs:__imp_FindFirstFileW
0x1800054f6  mov     r14, rax
0x1800054f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800054fd  jz      loc_1800055E6
0x180005503  mov     r8, rbx; Size
0x180005506  mov     rdx, rsi; Src
0x180005509  mov     rcx, r12; void *
0x18000550c  call    memcpy_0
0x180005511  movsd   xmm0, qword ptr cs:aContent; "Content"
0x180005519  mov     esi, 1
0x18000551e  movsd   qword ptr [rbx+r12], xmm0
0x180005524  mov     eax, dword ptr cs:aContent+8; "ent"
0x18000552a  mov     [rbx+r12+8], eax
0x18000552f  movzx   eax, word ptr cs:aContent+0Ch; "t"
0x180005536  mov     [rbx+r12+0Ch], ax
0x18000553c  mov     eax, [rsp+3E0h+var_3A0]
0x180005540  dec     eax
0x180005542  mov     word ptr [r12+rax*2], 5Ch ; '\'
0x180005549  nop     dword ptr [rax+00000000h]
0x180005550  lea     rax, [rbp+2E0h+FindFileData.cFileName]
0x180005554  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000555b  nop     dword ptr [rax+rax+00h]
0x180005560  inc     rdi
0x180005563  cmp     word ptr [rax+rdi*2], 0
0x180005568  jnz     short loc_180005560
0x18000556a  mov     eax, [rbp+2E0h+FindFileData.dwFileAttributes]
0x18000556d  test    al, 10h
0x18000556f  jz      short loc_1800055A0
0x180005571  lea     rdx, [rbp+2E0h+FindFileData]; lpFindFileData
0x180005575  mov     rcx, r14; hFindFile
0x180005578  call    cs:__imp_FindNextFileW
0x18000557e  test    eax, eax
0x180005580  jnz     short loc_180005550
0x180005582  call    cs:__imp_GetLastError
0x180005588  mov     edi, eax
0x18000558a  cmp     eax, 12h
0x18000558d  jz      loc_1800053D9
0x180005593  mov     ecx, eax; dwErrCode
0x180005595  call    cs:__imp_SetLastError
0x18000559b  jmp     loc_1800053CA
0x1800055a0  cmp     [rbp+2E0h+FindFileData.nFileSizeHigh], 0
0x1800055a4  jnz     short loc_180005571
0x1800055a6  cmp     [rbp+2E0h+FindFileData.nFileSizeLow], 0
0x1800055aa  jz      short loc_180005571
0x1800055ac  xor     eax, eax
0x1800055ae  cmp     ax, [rbp+2E0h+FindFileData.cFileName]
0x1800055b2  jz      short loc_180005571
0x1800055b4  cmp     edi, 42h ; 'B'
0x1800055b7  jnb     short loc_180005571
0x1800055b9  mov     eax, [rsp+3E0h+var_398]
0x1800055bd  test    sil, al
0x1800055c0  jz      loc_180005867
0x1800055c6  mov     r9, [rsp+3E0h+var_390]
0x1800055cb  xor     r8d, r8d
0x1800055ce  mov     rax, [rsp+3E0h+var_388]
0x1800055d3  xor     edx, edx
0x1800055d5  xor     ecx, ecx
0x1800055d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055dc  test    eax, eax
0x1800055de  jz      loc_1800053CA
0x1800055e4  jmp     short loc_180005571
0x1800055e6  call    cs:__imp_GetLastError
0x1800055ec  cmp     eax, 3
0x1800055ef  jz      short loc_1800055FE
0x1800055f1  mov     ecx, eax; dwErrCode
0x1800055f3  call    cs:__imp_SetLastError
0x1800055f9  jmp     loc_1800053CA
0x1800055fe  mov     eax, 2
0x180005603  jmp     short loc_1800055F1
0x180005605  mov     r9, [rsp+3E0h+var_390]
0x18000560a  lea     r8, [rbp+2E0h+FindFileData]
0x18000560e  mov     rax, [rsp+3E0h+var_388]
0x180005613  xor     edx, edx
0x180005615  xor     ecx, ecx
0x180005617  mov     [rsp+3E0h+var_39C], esi
0x18000561b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005620  test    eax, eax
0x180005622  jz      loc_180005571
0x180005628  lea     ebx, [rdi+1]
0x18000562b  add     rbx, rbx
0x18000562e  lea     rcx, [r15+r13*2]; void *
0x180005632  mov     r8, rbx; Size
0x180005635  lea     rdx, [rbp+2E0h+FindFileData.cFileName]; Src
0x180005639  call    memcpy_0
0x18000563e  mov     eax, [rsp+3E0h+var_3A0]
0x180005642  lea     rdx, [rbp+2E0h+FindFileData.cFileName]; Src
0x180005646  mov     r8, rbx; Size
0x180005649  lea     rcx, [r12+rax*2]; void *
0x18000564d  call    memcpy_0
0x180005652  xor     ebx, ebx
0x180005654  mov     [rsp+3E0h+hTemplateFile], 0; hTemplateFile
0x18000565d  xor     r9d, r9d; lpSecurityAttributes
0x180005660  mov     [rsp+3E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180005668  mov     r8d, esi; dwShareMode
0x18000566b  mov     edx, 80000000h; dwDesiredAccess
0x180005670  mov     [rsp+3E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180005678  mov     rcx, r15; lpFileName
0x18000567b  call    cs:__imp_CreateFileW
0x180005681  mov     [rsp+3E0h+hObject], rax
0x180005686  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000568a  jnz     short loc_1800056CF
0x18000568c  call    cs:__imp_GetLastError
0x180005692  cmp     eax, 20h ; ' '
0x180005695  jz      short loc_1800056B2
0x180005697  cmp     eax, 5
0x18000569a  jz      short loc_1800056CB
0x18000569c  cmp     eax, 3
0x18000569f  jz      loc_18000587C
0x1800056a5  mov     ecx, eax; dwErrCode
0x1800056a7  call    cs:__imp_SetLastError
0x1800056ad  jmp     loc_180005571
0x1800056b2  cmp     ebx, 6
0x1800056b5  jnb     short loc_1800056A5
0x1800056b7  lea     rax, qword_18002BA20
0x1800056be  mov     ecx, [rax+rbx*4]; dwMilliseconds
0x1800056c1  call    cs:__imp_Sleep
0x1800056c7  inc     ebx
0x1800056c9  jmp     short loc_180005654
0x1800056cb  cmp     ebx, esi
0x1800056cd  jmp     short loc_1800056B5
0x1800056cf  test    rax, rax
0x1800056d2  jz      loc_180005571
0x1800056d8  xor     edx, edx; Val
0x1800056da  lea     rcx, [rbp+2E0h+var_340]; void *
0x1800056de  mov     r8d, 58h ; 'X'; Size
0x1800056e4  call    memset_0
0x1800056e9  mov     rcx, [rsp+3E0h+hObject]; hFile
0x1800056ee  lea     r8, [rbp+2E0h+var_320]
0x1800056f2  xor     eax, eax
0x1800056f4  lea     rdx, [rbp+2E0h+var_328]
0x1800056f8  xorps   xmm0, xmm0
0x1800056fb  mov     [rbp+2E0h+var_350], rax
0x1800056ff  mov     [rsp+3E0h+var_378], rax
0x180005704  xor     r9d, r9d
0x180005707  lea     rax, [rsp+3E0h+var_378]
0x18000570c  mov     qword ptr [rsp+3E0h+dwCreationDisposition], rax; __int64
0x180005711  movups  [rsp+3E0h+var_370], xmm0
0x180005716  movups  [rbp+2E0h+var_360], xmm0
0x18000571a  call    I_UrlCacheReadAndValidateMetaDataFile
0x18000571f  mov     rcx, [rsp+3E0h+hObject]; hObject
0x180005724  mov     rbx, rax
0x180005727  mov     [rbp+2E0h+hMem], rax
0x18000572b  call    I_UrlCacheCloseHandle
0x180005730  test    rbx, rbx
0x180005733  jz      loc_180005571
0x180005739  mov     [rbp+2E0h+var_340], 58h ; 'X'
0x180005740  xor     eax, eax
0x180005742  mov     ecx, [rbx+4]
0x180005745  mov     [rbp+2E0h+var_33C], ecx
0x180005748  mov     rcx, [rbx+10h]
0x18000574c  mov     [rbp+2E0h+var_338], rcx
0x180005750  mov     ecx, [rbx+8]
0x180005753  mov     [rbp+2E0h+var_330], ecx
0x180005756  lea     rcx, [rbx+18h]
0x18000575a  mov     [rbp+2E0h+var_318], r15
0x18000575e  mov     [rbp+2E0h+var_310], r12
0x180005762  cmp     [rcx+4], eax
0x180005765  cmovz   rcx, rax
0x180005769  lea     rax, [rbx+40h]
0x18000576d  mov     [rbp+2E0h+var_308], rcx
0x180005771  cmp     dword ptr [rax+4], 0
  ... truncated ...
```
