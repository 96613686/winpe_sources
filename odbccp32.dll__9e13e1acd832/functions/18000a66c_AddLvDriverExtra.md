# AddLvDriverExtra

- ea: `0x18000a66c`
- end: `0x18000aa3d`
- name: `AddLvDriverExtra`
- size: `977`
- prototype: `__int64 __fastcall(HWND, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000aa50`

## callees

- `0x1800017c0`
- `0x180002940`
- `0x180002e14`
- `0x180002e4c`
- `0x180005210`
- `0x1800052b8`
- `0x180005aec`
- `0x18000a378`
- `0x18000a66c`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `msvcrt!calloc` at `0x18000a6c6`
- `msvcrt!calloc` at `0x18000a6c6`
- `USER32!CharUpperBuffW` at `0x18000a75f`
- `USER32!CharUpperBuffW` at `0x18000a75f`
- `USER32!SendMessageW` at `0x18000a96c`
- `USER32!SendMessageW` at `0x18000a99c`
- `USER32!SendMessageW` at `0x18000a9cc`
- `USER32!SendMessageW` at `0x18000aa03`
- `USER32!SendMessageW` at `0x18000a96c`
- `USER32!SendMessageW` at `0x18000a99c`
- `USER32!SendMessageW` at `0x18000a9cc`
- `USER32!SendMessageW` at `0x18000aa03`
- `KERNEL32!FindClose` at `0x18000a926`
- `KERNEL32!FindClose` at `0x18000a926`
- `KERNEL32!GetThreadLocale` at `0x18000a8f5`
- `KERNEL32!GetThreadLocale` at `0x18000a8f5`
- `KERNEL32!GetDateFormatW` at `0x18000a915`
- `KERNEL32!GetDateFormatW` at `0x18000a915`
- `KERNEL32!FileTimeToSystemTime` at `0x18000a8e4`
- `KERNEL32!FileTimeToSystemTime` at `0x18000a8e4`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18000a8d1`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18000a8d1`
- `KERNEL32!FindFirstFileW` at `0x18000a897`
- `KERNEL32!FindFirstFileW` at `0x18000a897`

## pseudocode

```c
__int64 __fastcall AddLvDriverExtra(HWND a1, const wchar_t *a2, int a3)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  char *v7; // rbx
  int v8; // eax
  wchar_t *v9; // rcx
  __int64 v10; // rdx
  int FileVersion; // eax
  __int16 v12; // r11
  wchar_t *v13; // r15
  wchar_t *v14; // r12
  HANDLE FirstFileW; // rbx
  LCID ThreadLocale; // eax
  HWND v17; // rsi
  LPWSTR lpDateStr; // [rsp+20h] [rbp-E0h]
  int cchDate[2]; // [rsp+28h] [rbp-D8h]
  struct _FILETIME LocalFileTime; // [rsp+48h] [rbp-B8h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-B0h]
  LPARAM lParam; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h]
  wchar_t *v25; // [rsp+78h] [rbp-88h]
  _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-40h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF

  hWnd = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = (wchar_t *)calloc(0x2138u, 1u);
  v5 = v4;
  if ( !v4 )
    return 1;
  v7 = (char *)(v4 + 1156);
  v8 = SQLGetPrivateProfileStringCover(a2, L"Driver", &SubKey, v4 + 2060, 260, L"ODBCINST.INI");
  v9 = v5;
  if ( v8 )
  {
    StringCchCopyW(v5, 0x80u, a2);
    ExtractFileName(v5 + 128);
    v10 = -1;
    do
      ++v10;
    while ( v5[v10 + 128] );
    CharUpperBuffW(v5 + 128, v10);
    SetString((LPWSTR)v7 + 776, 128);
    StringCchCopyW(v5 + 388, 0x80u, (STRSAFE_LPCWSTR)v7 + 776);
    StringCchCopyW(v5 + 516, 0x80u, (STRSAFE_LPCWSTR)v7 + 776);
    StringCchCopyW(v5 + 772, 0x80u, (STRSAFE_LPCWSTR)v7 + 776);
    StringCchCopyW(v5 + 644, 0x80u, (STRSAFE_LPCWSTR)v7 + 776);
    FileVersion = GetFileVersion((LPCWSTR)v7 + 904, v7);
    v12 = 0;
    if ( FileVersion )
    {
      if ( *((_WORD *)v7 + 128) )
        StringCchCopyW(v5 + 388, 0x80u, (STRSAFE_LPCWSTR)v7 + 128);
      v13 = v5 + 516;
      if ( *((_WORD *)v7 + 256) != v12 )
        StringCchCopyW(v5 + 516, 0x80u, (STRSAFE_LPCWSTR)v7 + 256);
      if ( *((_WORD *)v7 + 384) != v12 )
        StringCchCopyW(v5 + 772, 0x80u, (STRSAFE_LPCWSTR)v7 + 384);
      v14 = v5 + 644;
      cchDate[0] = *((_DWORD *)v7 + 386);
      LODWORD(lpDateStr) = *((_DWORD *)v7 + 385);
      StringCchPrintfW(
        v5 + 644,
        0x80u,
        L"%d.%02d.%02d.%02d",
        *((unsigned int *)v7 + 384),
        lpDateStr,
        *(_QWORD *)cchDate,
        *((_DWORD *)v7 + 387));
    }
    else
    {
      v13 = v5 + 516;
      v14 = v5 + 644;
    }
    FirstFileW = FindFirstFileW((LPCWSTR)v7 + 904, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      LocalFileTime = 0;
      SystemTime = 0;
      MakeIntlSize(FindFileData.nFileSizeLow, v5 + 1028);
      if ( FileTimeToLocalFileTime(&FindFileData.ftLastWriteTime, &LocalFileTime)
        && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
      {
        ThreadLocale = GetThreadLocale();
        if ( !GetDateFormatW(ThreadLocale, 1u, &SystemTime, 0, v5 + 900, 128) )
          v5[900] = 0;
      }
      FindClose(FirstFileW);
    }
    memset_0(&lParam, 0, 0x58u);
    v17 = hWnd;
    v25 = v14;
    v24 = 1;
    SendMessageW(hWnd, 0x1074u, a3, (LPARAM)&lParam);
    memset_0(&lParam, 0, 0x58u);
    v24 = 2;
    v25 = v13;
    SendMessageW(v17, 0x1074u, a3, (LPARAM)&lParam);
    memset_0(&lParam, 0, 0x58u);
    v24 = 3;
    v25 = v5 + 128;
    SendMessageW(v17, 0x1074u, a3, (LPARAM)&lParam);
    memset_0(&lParam, 0, 0x58u);
    v24 = 4;
    v25 = v5 + 900;
    SendMessageW(v17, 0x1074u, a3, (LPARAM)&lParam);
    v9 = v5;
  }
  OFree(v9);
  return 0;
}

```

## disassembly

```asm
0x18000a66c  mov     [rsp-8+arg_18], rbx
0x18000a671  push    rbp
0x18000a672  push    rsi
0x18000a673  push    rdi
0x18000a674  push    r12
0x18000a676  push    r13
0x18000a678  push    r14
0x18000a67a  push    r15
0x18000a67c  lea     rbp, [rsp-230h]
0x18000a684  sub     rsp, 330h
0x18000a68b  mov     rax, cs:__security_cookie
0x18000a692  xor     rax, rsp
0x18000a695  mov     [rbp+260h+var_40], rax
0x18000a69c  mov     [rsp+360h+var_320], r8d
0x18000a6a1  mov     r14, rdx
0x18000a6a4  mov     [rsp+360h+hWnd], rcx
0x18000a6a9  xor     edx, edx; Val
0x18000a6ab  mov     r8d, 250h; Size
0x18000a6b1  lea     rcx, [rbp+260h+FindFileData]; void *
0x18000a6b5  call    memset_0
0x18000a6ba  mov     ebx, 1
0x18000a6bf  mov     ecx, 2138h; Count
0x18000a6c4  mov     edx, ebx; Size
0x18000a6c6  call    cs:__imp_calloc
0x18000a6cc  xor     r12d, r12d
0x18000a6cf  mov     rdi, rax
0x18000a6d2  test    rax, rax
0x18000a6d5  jnz     short loc_18000A6DE
0x18000a6d7  mov     eax, ebx
0x18000a6d9  jmp     loc_18000AA13
0x18000a6de  lea     rbx, [rax+908h]
0x18000a6e5  mov     rcx, r14
0x18000a6e8  lea     rax, aOdbcinstIni
0x18000a6ef  mov     qword ptr [rsp+360h+cchDate], rax
0x18000a6f4  lea     r15, [rbx+610h]
0x18000a6fb  lea     rsi, [r15+100h]
0x18000a702  mov     dword ptr [rsp+360h+lpDateStr], 104h
0x18000a70a  mov     r9, rsi
0x18000a70d  lea     r8, SubKey
0x18000a714  lea     rdx, aDriver_0
0x18000a71b  call    SQLGetPrivateProfileStringCover
0x18000a720  mov     rcx, rdi; pszDest
0x18000a723  test    eax, eax
0x18000a725  jz      loc_18000AA0C
0x18000a72b  mov     r13d, 80h
0x18000a731  mov     r8, r14; pszSrc
0x18000a734  mov     edx, r13d; cchDest
0x18000a737  call    StringCchCopyW
0x18000a73c  lea     r14, [rdi+100h]
0x18000a743  mov     r8, rsi
0x18000a746  mov     rcx, r14; pszDest
0x18000a749  call    ExtractFileName
0x18000a74e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a752  inc     rdx; cchLength
0x18000a755  cmp     [r14+rdx*2], r12w
0x18000a75a  jnz     short loc_18000A752
0x18000a75c  mov     rcx, r14; lpsz
0x18000a75f  call    cs:__imp_CharUpperBuffW
0x18000a765  mov     r8d, 526h
0x18000a76b  mov     edx, r13d; cchBufferMax
0x18000a76e  mov     rcx, r15; lpBuffer
0x18000a771  call    SetString
0x18000a776  lea     r12, [rdi+308h]
0x18000a77d  mov     r8, r15; pszSrc
0x18000a780  mov     rcx, r12; pszDest
0x18000a783  mov     rdx, r13; cchDest
0x18000a786  call    StringCchCopyW
0x18000a78b  lea     rcx, [rdi+408h]; pszDest
0x18000a792  mov     r8, r15; pszSrc
0x18000a795  mov     rdx, r13; cchDest
0x18000a798  call    StringCchCopyW
0x18000a79d  lea     r13, [rdi+608h]
0x18000a7a4  mov     r8, r15; pszSrc
0x18000a7a7  mov     rcx, r13; pszDest
0x18000a7aa  mov     edx, 80h; cchDest
0x18000a7af  call    StringCchCopyW
0x18000a7b4  mov     r8, r15; pszSrc
0x18000a7b7  lea     rcx, [rdi+508h]; pszDest
0x18000a7be  mov     r15d, 80h
0x18000a7c4  mov     edx, r15d; cchDest
0x18000a7c7  call    StringCchCopyW
0x18000a7cc  lea     r8d, [r15-7Fh]
0x18000a7d0  mov     rdx, rbx; void *
0x18000a7d3  mov     rcx, rsi; lptstrFilename
0x18000a7d6  call    GetFileVersion
0x18000a7db  xor     r11d, r11d
0x18000a7de  test    eax, eax
0x18000a7e0  jz      loc_18000A882
0x18000a7e6  lea     r8, [rbx+100h]; pszSrc
0x18000a7ed  cmp     [r8], r11w
0x18000a7f1  jz      short loc_18000A7FE
0x18000a7f3  mov     edx, r15d; cchDest
0x18000a7f6  mov     rcx, r12; pszDest
0x18000a7f9  call    StringCchCopyW
0x18000a7fe  lea     r8, [rbx+200h]; pszSrc
0x18000a805  cmp     [r8], r11w
0x18000a809  jz      short loc_18000A81F
0x18000a80b  mov     rdx, r15; cchDest
0x18000a80e  lea     r15, [rdi+408h]
0x18000a815  mov     rcx, r15; pszDest
0x18000a818  call    StringCchCopyW
0x18000a81d  jmp     short loc_18000A826
0x18000a81f  lea     r15, [rdi+408h]
0x18000a826  lea     r8, [rbx+300h]; pszSrc
0x18000a82d  cmp     [r8], r11w
0x18000a831  jz      short loc_18000A840
0x18000a833  mov     edx, 80h; cchDest
0x18000a838  mov     rcx, r13; pszDest
0x18000a83b  call    StringCchCopyW
0x18000a840  mov     eax, [rbx+60Ch]
0x18000a846  lea     r12, [rdi+508h]
0x18000a84d  mov     r9d, [rbx+600h]
0x18000a854  lea     r8, aD02d02d02d
0x18000a85b  mov     [rsp+360h+var_330], eax
0x18000a85f  mov     edx, 80h; cchDest
0x18000a864  mov     eax, [rbx+608h]
0x18000a86a  mov     rcx, r12; pszDest
0x18000a86d  mov     [rsp+360h+cchDate], eax
0x18000a871  mov     eax, [rbx+604h]
0x18000a877  mov     dword ptr [rsp+360h+lpDateStr], eax
0x18000a87b  call    StringCchPrintfW
0x18000a880  jmp     short loc_18000A890
0x18000a882  lea     r15, [rdi+408h]
0x18000a889  lea     r12, [rdi+508h]
0x18000a890  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18000a894  mov     rcx, rsi; lpFileName
0x18000a897  call    cs:__imp_FindFirstFileW
0x18000a89d  mov     rbx, rax
0x18000a8a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a8a4  jz      loc_18000A92C
0x18000a8aa  mov     ecx, [rbp+260h+FindFileData.nFileSizeLow]
0x18000a8ad  lea     rdx, [rdi+808h]
0x18000a8b4  xorps   xmm0, xmm0
0x18000a8b7  xor     r13d, r13d
0x18000a8ba  mov     qword ptr [rsp+360h+LocalFileTime.dwLowDateTime], r13
0x18000a8bf  movups  xmmword ptr [rbp+260h+SystemTime.wYear], xmm0
0x18000a8c3  call    MakeIntlSize
0x18000a8c8  lea     rdx, [rsp+360h+LocalFileTime]; lpLocalFileTime
0x18000a8cd  lea     rcx, [rbp+260h+FindFileData.ftLastWriteTime]; lpFileTime
0x18000a8d1  call    cs:__imp_FileTimeToLocalFileTime
0x18000a8d7  test    eax, eax
0x18000a8d9  jz      short loc_18000A923
0x18000a8db  lea     rdx, [rbp+260h+SystemTime]; lpSystemTime
0x18000a8df  lea     rcx, [rsp+360h+LocalFileTime]; lpFileTime
0x18000a8e4  call    cs:__imp_FileTimeToSystemTime
0x18000a8ea  test    eax, eax
0x18000a8ec  jz      short loc_18000A923
0x18000a8ee  lea     rsi, [rdi+708h]
0x18000a8f5  call    cs:__imp_GetThreadLocale
0x18000a8fb  mov     [rsp+360h+cchDate], 80h; cchDate
0x18000a903  lea     r8, [rbp+260h+SystemTime]; lpDate
0x18000a907  mov     ecx, eax; Locale
0x18000a909  mov     [rsp+360h+lpDateStr], rsi; lpDateStr
0x18000a90e  xor     r9d, r9d; lpFormat
0x18000a911  lea     edx, [r13+1]; dwFlags
0x18000a915  call    cs:__imp_GetDateFormatW
0x18000a91b  test    eax, eax
0x18000a91d  jnz     short loc_18000A923
0x18000a91f  mov     [rsi], r13w
0x18000a923  mov     rcx, rbx; hFindFile
0x18000a926  call    cs:__imp_FindClose
0x18000a92c  mov     r13d, 58h ; 'X'
0x18000a932  lea     rcx, [rsp+360h+lParam]; void *
0x18000a937  mov     r8d, r13d; Size
0x18000a93a  xor     edx, edx; Val
0x18000a93c  call    memset_0
0x18000a941  movsxd  rbx, [rsp+360h+var_320]
0x18000a946  lea     r9, [rsp+360h+lParam]; lParam
0x18000a94b  mov     rsi, [rsp+360h+hWnd]
0x18000a950  mov     r8, rbx; wParam
0x18000a953  mov     [rsp+360h+var_2E8], r12
0x18000a958  mov     rcx, rsi; hWnd
0x18000a95b  mov     r12d, 1074h
0x18000a961  mov     [rsp+360h+var_2F8], 1
0x18000a969  mov     edx, r12d; Msg
0x18000a96c  call    cs:__imp_SendMessageW
0x18000a972  mov     r8d, r13d; Size
0x18000a975  lea     rcx, [rsp+360h+lParam]; void *
0x18000a97a  xor     edx, edx; Val
0x18000a97c  call    memset_0
0x18000a981  lea     r9, [rsp+360h+lParam]; lParam
0x18000a986  mov     [rsp+360h+var_2F8], 2
0x18000a98e  mov     r8, rbx; wParam
0x18000a991  mov     [rsp+360h+var_2E8], r15
0x18000a996  mov     edx, r12d; Msg
0x18000a999  mov     rcx, rsi; hWnd
0x18000a99c  call    cs:__imp_SendMessageW
0x18000a9a2  mov     r8d, r13d; Size
0x18000a9a5  lea     rcx, [rsp+360h+lParam]; void *
0x18000a9aa  xor     edx, edx; Val
0x18000a9ac  call    memset_0
0x18000a9b1  lea     r9, [rsp+360h+lParam]; lParam
0x18000a9b6  mov     [rsp+360h+var_2F8], 3
0x18000a9be  mov     r8, rbx; wParam
0x18000a9c1  mov     [rsp+360h+var_2E8], r14
0x18000a9c6  mov     edx, r12d; Msg
0x18000a9c9  mov     rcx, rsi; hWnd
0x18000a9cc  call    cs:__imp_SendMessageW
0x18000a9d2  mov     r8d, r13d; Size
0x18000a9d5  lea     rcx, [rsp+360h+lParam]; void *
0x18000a9da  xor     edx, edx; Val
0x18000a9dc  call    memset_0
0x18000a9e1  lea     rax, [rdi+708h]
0x18000a9e8  mov     [rsp+360h+var_2F8], 4
0x18000a9f0  lea     r9, [rsp+360h+lParam]; lParam
0x18000a9f5  mov     [rsp+360h+var_2E8], rax
0x18000a9fa  mov     r8, rbx; wParam
0x18000a9fd  mov     edx, r12d; Msg
0x18000aa00  mov     rcx, rsi; hWnd
0x18000aa03  call    cs:__imp_SendMessageW
0x18000aa09  mov     rcx, rdi
0x18000aa0c  call    OFree
0x18000aa11  xor     eax, eax
0x18000aa13  mov     rcx, [rbp+260h+var_40]
0x18000aa1a  xor     rcx, rsp; StackCookie
0x18000aa1d  call    __security_check_cookie
0x18000aa22  mov     rbx, [rsp+360h+arg_18]
0x18000aa2a  add     rsp, 330h
0x18000aa31  pop     r15
0x18000aa33  pop     r14
0x18000aa35  pop     r13
0x18000aa37  pop     r12
0x18000aa39  pop     rdi
0x18000aa3a  pop     rsi
0x18000aa3b  pop     rbp
0x18000aa3c  retn
```
