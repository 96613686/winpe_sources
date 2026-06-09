# UtilPruneFolder(wchar_t const *,wchar_t const *,ulong)

- ea: `0x18003d194`
- end: `0x18003d43f`
- name: `?UtilPruneFolder@@YAJPEB_W0K@Z`
- size: `683`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800199f8`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180006b50`
- `0x180009f00`
- `0x18003d194`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d395`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003d31f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003d31f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003d305`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003d377`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003d305`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003d377`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003d270`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003d270`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003d2f8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003d2f8`

## pseudocode

```c
__int64 __fastcall UtilPruneFolder(const wchar_t *a1, const wchar_t *a2, int a3)
{
  const wchar_t *v3; // r13
  int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v7; // r15d
  int v8; // r12d
  HANDLE FirstFileW; // rbx
  int dwLowDateTime; // r14d
  int dwHighDateTime; // edi
  unsigned int v12; // esi
  unsigned int v13; // r13d
  signed int LastError; // eax
  __int64 v16; // [rsp+20h] [rbp-E0h]
  FILETIME ftLastWriteTime; // [rsp+30h] [rbp-D0h]
  LPCWSTR v19; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR *v20; // [rsp+40h] [rbp-C0h]
  _WORD v21[8]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v23[12]; // [rsp+68h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  LODWORD(v16) = a3;
  v3 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpFileName[0] = v23;
  lpFileName[1] = v23;
  v23[0] = 0;
  v19 = v21;
  v20 = v21;
  v21[0] = 0;
  v4 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpFileName,
         L"%ls\\%ls",
         v3,
         L"*.dmp");
  if ( v4 >= 0 )
  {
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
        break;
      dwLowDateTime = -1;
      dwHighDateTime = -1;
      v20 = v19;
      v12 = 0;
      *v19 = 0;
      while ( 1 )
      {
        if ( *(_QWORD *)&FindFileData.ftLastWriteTime < __PAIR64__(dwHighDateTime, dwLowDateTime)
          && *(_QWORD *)&FindFileData.ftLastWriteTime > __PAIR64__(v8, v7) )
        {
          ftLastWriteTime = FindFileData.ftLastWriteTime;
          v4 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 &v19,
                 L"%ls\\%ls",
                 v3,
                 FindFileData.cFileName,
                 v16);
          if ( v4 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
                (unsigned int)v4);
            FindClose(FirstFileW);
            goto LABEL_35;
          }
          dwHighDateTime = ftLastWriteTime.dwHighDateTime;
          dwLowDateTime = ftLastWriteTime.dwLowDateTime;
        }
        v13 = v12++;
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          break;
        v3 = a1;
      }
      FindClose(FirstFileW);
      if ( v12 <= (unsigned int)v16 )
        goto LABEL_26;
      if ( v19 == v20 )
      {
        v4 = -2147467259;
        goto LABEL_35;
      }
      if ( DeleteFileW(v19) )
      {
        if ( v13 <= (unsigned int)v16 )
          goto LABEL_26;
      }
      else
      {
        v7 = dwLowDateTime;
        v8 = dwHighDateTime;
      }
      v3 = a1;
    }
    if ( GetLastError() == 2 )
    {
LABEL_26:
      v4 = 0;
      goto LABEL_35;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v4 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 34;
      goto LABEL_34;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 33;
LABEL_34:
      WPP_SF_d(v5[2], v6, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids, (unsigned int)v4);
    }
  }
LABEL_35:
  if ( v19 != v21 )
    operator delete((void *)v19, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v23 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003d194  push    rbp
0x18003d196  push    rbx
0x18003d197  push    rsi
0x18003d198  push    rdi
0x18003d199  push    r12
0x18003d19b  push    r13
0x18003d19d  push    r14
0x18003d19f  push    r15
0x18003d1a1  lea     rbp, [rsp-1E8h]
0x18003d1a9  sub     rsp, 2E8h
0x18003d1b0  mov     rax, cs:__security_cookie
0x18003d1b7  xor     rax, rsp
0x18003d1ba  mov     [rbp+220h+var_50], rax
0x18003d1c1  mov     dword ptr [rsp+320h+var_300], r8d
0x18003d1c6  mov     r13, rcx
0x18003d1c9  mov     [rsp+320h+var_2F8], rcx
0x18003d1ce  mov     r8d, 250h; Size
0x18003d1d4  lea     rcx, [rbp+220h+FindFileData]; void *
0x18003d1d8  xor     edx, edx; Val
0x18003d1da  call    memset_0
0x18003d1df  lea     rax, [rsp+320h+var_2B8]
0x18003d1e4  mov     r8, r13
0x18003d1e7  mov     [rsp+320h+lpFileName], rax
0x18003d1ec  lea     r9, aDmp_0; "*.dmp"
0x18003d1f3  lea     rax, [rsp+320h+var_2B8]
0x18003d1f8  mov     [rsp+320h+var_2C0], rax
0x18003d1fd  lea     rdx, aLsLs; "%ls\\%ls"
0x18003d204  xor     eax, eax
0x18003d206  lea     rcx, [rsp+320h+lpFileName]
0x18003d20b  mov     [rsp+320h+var_2B8], ax
0x18003d210  lea     rax, [rsp+320h+var_2D8]
0x18003d215  mov     [rsp+320h+var_2E8], rax
0x18003d21a  lea     rax, [rsp+320h+var_2D8]
0x18003d21f  mov     [rsp+320h+var_2E0], rax
0x18003d224  xor     eax, eax
0x18003d226  mov     [rsp+320h+var_2D8], ax
0x18003d22b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003d230  mov     edi, eax
0x18003d232  test    eax, eax
0x18003d234  jns     short loc_18003D261
0x18003d236  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d23d  lea     rax, WPP_GLOBAL_Control
0x18003d244  cmp     rcx, rax
0x18003d247  jz      loc_18003D3E4
0x18003d24d  test    byte ptr [rcx+1Ch], 1
0x18003d251  jz      loc_18003D3E4
0x18003d257  mov     edx, 21h ; '!'
0x18003d25c  jmp     loc_18003D3D1
0x18003d261  xor     r15d, r15d
0x18003d264  xor     r12d, r12d
0x18003d267  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x18003d26c  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x18003d270  call    cs:__imp_FindFirstFileW
0x18003d276  mov     rbx, rax
0x18003d279  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d27d  jz      loc_18003D386
0x18003d283  mov     rcx, [rsp+320h+var_2E8]
0x18003d288  or      r14d, 0FFFFFFFFh
0x18003d28c  or      edi, r14d
0x18003d28f  mov     [rsp+320h+var_2E0], rcx
0x18003d294  xor     esi, esi
0x18003d296  xor     eax, eax
0x18003d298  mov     [rcx], ax
0x18003d29b  jmp     short loc_18003D2A2
0x18003d29d  mov     r13, [rsp+320h+var_2F8]
0x18003d2a2  mov     ecx, [rbp+220h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x18003d2a5  mov     rax, [rbp-6Ch]
0x18003d2a9  cmp     ecx, edi
0x18003d2ab  jb      short loc_18003D2B4
0x18003d2ad  ja      short loc_18003D2EC
0x18003d2af  cmp     eax, r14d
0x18003d2b2  jnb     short loc_18003D2EC
0x18003d2b4  cmp     ecx, r12d
0x18003d2b7  jb      short loc_18003D2EC
0x18003d2b9  ja      short loc_18003D2C0
0x18003d2bb  cmp     eax, r15d
0x18003d2be  jbe     short loc_18003D2EC
0x18003d2c0  lea     r9, [rbp+220h+FindFileData.cFileName]
0x18003d2c4  mov     [rsp+320h+var_2F0], rax
0x18003d2c9  mov     r8, r13
0x18003d2cc  lea     rdx, aLsLs; "%ls\\%ls"
0x18003d2d3  lea     rcx, [rsp+320h+var_2E8]
0x18003d2d8  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003d2dd  mov     edi, eax
0x18003d2df  test    eax, eax
0x18003d2e1  js      short loc_18003D343
0x18003d2e3  mov     edi, dword ptr [rsp+320h+var_2F0+4]
0x18003d2e7  mov     r14d, dword ptr [rsp+320h+var_2F0]
0x18003d2ec  mov     r13d, esi
0x18003d2ef  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x18003d2f3  mov     rcx, rbx; hFindFile
0x18003d2f6  inc     esi
0x18003d2f8  call    cs:__imp_FindNextFileW
0x18003d2fe  test    eax, eax
0x18003d300  jnz     short loc_18003D29D
0x18003d302  mov     rcx, rbx; hFindFile
0x18003d305  call    cs:__imp_FindClose
0x18003d30b  mov     ebx, dword ptr [rsp+320h+var_300]
0x18003d30f  cmp     esi, ebx
0x18003d311  jbe     short loc_18003D391
0x18003d313  mov     rcx, [rsp+320h+var_2E8]; lpFileName
0x18003d318  cmp     rcx, [rsp+320h+var_2E0]
0x18003d31d  jz      short loc_18003D37F
0x18003d31f  call    cs:__imp_DeleteFileW
0x18003d325  test    eax, eax
0x18003d327  jz      short loc_18003D33B
0x18003d329  mov     esi, r13d
0x18003d32c  cmp     r13d, ebx
0x18003d32f  jbe     short loc_18003D391
0x18003d331  mov     r13, [rsp+320h+var_2F8]
0x18003d336  jmp     loc_18003D267
0x18003d33b  mov     r15d, r14d
0x18003d33e  mov     r12d, edi
0x18003d341  jmp     short loc_18003D331
0x18003d343  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d34a  lea     rax, WPP_GLOBAL_Control
0x18003d351  cmp     rcx, rax
0x18003d354  jz      short loc_18003D374
0x18003d356  test    byte ptr [rcx+1Ch], 1
0x18003d35a  jz      short loc_18003D374
0x18003d35c  mov     rcx, [rcx+10h]
0x18003d360  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18003d367  mov     edx, 23h ; '#'
0x18003d36c  mov     r9d, edi
0x18003d36f  call    WPP_SF_d
0x18003d374  mov     rcx, rbx; hFindFile
0x18003d377  call    cs:__imp_FindClose
0x18003d37d  jmp     short loc_18003D3E4
0x18003d37f  mov     edi, 80004005h
0x18003d384  jmp     short loc_18003D3E4
0x18003d386  call    cs:__imp_GetLastError
0x18003d38c  cmp     eax, 2
0x18003d38f  jnz     short loc_18003D395
0x18003d391  xor     edi, edi
0x18003d393  jmp     short loc_18003D3E4
0x18003d395  call    cs:__imp_GetLastError
0x18003d39b  test    eax, eax
0x18003d39d  jle     short loc_18003D3A7
0x18003d39f  movzx   eax, ax
0x18003d3a2  or      eax, 80070000h
0x18003d3a7  mov     edi, 80004005h
0x18003d3ac  test    eax, eax
0x18003d3ae  cmovns  eax, edi
0x18003d3b1  mov     edi, eax
0x18003d3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3ba  lea     rax, WPP_GLOBAL_Control
0x18003d3c1  cmp     rcx, rax
0x18003d3c4  jz      short loc_18003D3E4
0x18003d3c6  test    byte ptr [rcx+1Ch], 1
0x18003d3ca  jz      short loc_18003D3E4
0x18003d3cc  mov     edx, 22h ; '"'
0x18003d3d1  mov     rcx, [rcx+10h]
0x18003d3d5  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x18003d3dc  mov     r9d, edi
0x18003d3df  call    WPP_SF_d
0x18003d3e4  mov     rcx, [rsp+320h+var_2E8]; void *
0x18003d3e9  lea     rax, [rsp+320h+var_2D8]
0x18003d3ee  cmp     rcx, rax
0x18003d3f1  jz      short loc_18003D3FF
0x18003d3f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d3fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003d3ff  mov     rcx, [rsp+320h+lpFileName]; void *
0x18003d404  lea     rax, [rsp+320h+var_2B8]
0x18003d409  cmp     rcx, rax
0x18003d40c  jz      short loc_18003D41A
0x18003d40e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d415  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003d41a  mov     eax, edi
0x18003d41c  mov     rcx, [rbp+220h+var_50]
0x18003d423  xor     rcx, rsp; StackCookie
0x18003d426  call    __security_check_cookie
0x18003d42b  add     rsp, 2E8h
0x18003d432  pop     r15
0x18003d434  pop     r14
0x18003d436  pop     r13
0x18003d438  pop     r12
0x18003d43a  pop     rdi
0x18003d43b  pop     rsi
0x18003d43c  pop     rbx
0x18003d43d  pop     rbp
0x18003d43e  retn
```
