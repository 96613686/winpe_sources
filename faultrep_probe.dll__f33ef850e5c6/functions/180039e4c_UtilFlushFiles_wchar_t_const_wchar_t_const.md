# UtilFlushFiles(wchar_t const *,wchar_t const *)

- ea: `0x180039e4c`
- end: `0x18003a15d`
- name: `?UtilFlushFiles@@YAJPEB_W0@Z`
- size: `785`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000ff8c`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180006b50`
- `0x18000758c`
- `0x18000760c`
- `0x180009f00`
- `0x180039e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a0a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a02b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a02b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039fe0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039fe0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003a136`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003a136`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180039ff6`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180039ff6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180039f1a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180039f1a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003a087`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003a087`

## pseudocode

```c
__int64 __fastcall UtilFlushFiles(const wchar_t *a1, const wchar_t *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 FirstFileW; // rbx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  HANDLE FileW; // rax
  void *v11; // rdi
  LPCWSTR v12; // rdi
  signed int LastError; // eax
  signed int v14; // eax
  LPCWSTR v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v19[8]; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpFileName[0] = v19;
  v19[0] = 0;
  lpFileName[1] = v19;
  v17[0] = 0;
  v16[0] = v17;
  v16[1] = v17;
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpFileName,
         L"%ls\\%ls",
         a1,
         L"*.*");
  v4 = v3;
  if ( v3 < 0 )
  {
    FirstFileW = -1;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 94;
      v8 = (unsigned int)v3;
LABEL_36:
      WPP_SF_d(v6[2], v7, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v8);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  if ( FirstFileW != -1 )
  {
    do
    {
      if ( (FindFileData.cFileName[0] != 46
         || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
        && (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
               v16,
               L"%ls\\%ls",
               a1,
               FindFileData.cFileName);
        if ( v9 >= 0 )
        {
          FileW = CreateFileW(v16[0], 0x40000000u, 3u, 0, 3u, 0, 0);
          v11 = FileW;
          if ( (unsigned __int64)FileW + 1 <= 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = v16[0];
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                98,
                (unsigned int)&WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
                LastError,
                (__int64)v12);
            }
          }
          else
          {
            FlushFileBuffers(FileW);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                97,
                &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
                v16[0]);
            CloseHandle(v11);
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (unsigned int)v9);
        }
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    goto LABEL_28;
  }
  if ( GetLastError() == 2 )
  {
LABEL_28:
    v4 = 0;
    goto LABEL_37;
  }
  v14 = GetLastError();
  v4 = v14;
  if ( v14 > 0 )
    v4 = (unsigned __int16)v14 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 95;
    v8 = v4;
    goto LABEL_36;
  }
LABEL_37:
  if ( v16[0] != v17 )
    operator delete((void *)v16[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v19 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return v4;
}

```

## disassembly

```asm
0x180039e4c  push    rbp
0x180039e4e  push    rbx
0x180039e4f  push    rsi
0x180039e50  push    rdi
0x180039e51  push    r14
0x180039e53  push    r15
0x180039e55  lea     rbp, [rsp-1E8h]
0x180039e5d  sub     rsp, 2E8h
0x180039e64  mov     rax, cs:__security_cookie
0x180039e6b  xor     rax, rsp
0x180039e6e  mov     [rbp+210h+var_40], rax
0x180039e75  mov     r14, rcx
0x180039e78  xor     edx, edx; Val
0x180039e7a  lea     rcx, [rbp+210h+FindFileData]; void *
0x180039e7e  mov     r8d, 250h; Size
0x180039e84  call    memset_0
0x180039e89  lea     rax, [rsp+310h+var_2A0]
0x180039e8e  xor     r15d, r15d
0x180039e91  mov     [rsp+310h+lpFileName], rax
0x180039e96  lea     r9, asc_180051968; "*.*"
0x180039e9d  lea     rax, [rsp+310h+var_2A0]
0x180039ea2  mov     [rsp+310h+var_2A0], r15w
0x180039ea8  mov     [rsp+310h+var_2A8], rax
0x180039ead  lea     rdx, aLsLs; "%ls\\%ls"
0x180039eb4  lea     rax, [rsp+310h+var_2C0]
0x180039eb9  mov     [rsp+310h+var_2C0], r15w
0x180039ebf  mov     [rsp+310h+var_2D0], rax
0x180039ec4  lea     rcx, [rsp+310h+lpFileName]
0x180039ec9  lea     rax, [rsp+310h+var_2C0]
0x180039ece  mov     r8, r14
0x180039ed1  mov     [rsp+310h+var_2C8], rax
0x180039ed6  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180039edb  mov     edi, eax
0x180039edd  test    eax, eax
0x180039edf  jns     short loc_180039F11
0x180039ee1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180039eec  lea     rsi, WPP_GLOBAL_Control
0x180039ef3  cmp     rcx, rsi
0x180039ef6  jz      loc_18003A0F7
0x180039efc  test    byte ptr [rcx+1Ch], 1
0x180039f00  jz      loc_18003A0F7
0x180039f06  lea     edx, [rbx+5Fh]
0x180039f09  mov     r9d, eax
0x180039f0c  jmp     loc_18003A0E7
0x180039f11  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x180039f16  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180039f1a  call    cs:__imp_FindFirstFileW
0x180039f20  mov     rbx, rax
0x180039f23  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039f27  jz      loc_18003A097
0x180039f2d  lea     rsi, WPP_GLOBAL_Control
0x180039f34  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x180039f39  movzx   eax, [rbp+210h+FindFileData.cFileName+2]
0x180039f3d  jnz     short loc_180039F60
0x180039f3f  test    ax, ax
0x180039f42  jz      loc_18003A080
0x180039f48  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x180039f4d  jnz     short loc_180039F60
0x180039f4f  cmp     ax, 2Eh ; '.'
0x180039f53  jnz     short loc_180039F60
0x180039f55  cmp     [rbp+210h+FindFileData.cFileName+4], r15w
0x180039f5a  jz      loc_18003A080
0x180039f60  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x180039f64  jnz     loc_18003A080
0x180039f6a  lea     r9, [rbp+210h+FindFileData.cFileName]
0x180039f6e  mov     r8, r14
0x180039f71  lea     rdx, aLsLs; "%ls\\%ls"
0x180039f78  lea     rcx, [rsp+310h+var_2D0]
0x180039f7d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180039f82  test    eax, eax
0x180039f84  jns     short loc_180039FBD
0x180039f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f8d  cmp     rcx, rsi
0x180039f90  jz      loc_18003A080
0x180039f96  test    byte ptr [rcx+1Ch], 2
0x180039f9a  jz      loc_18003A080
0x180039fa0  mov     rcx, [rcx+10h]
0x180039fa4  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180039fab  mov     edx, 60h ; '`'
0x180039fb0  mov     r9d, eax
0x180039fb3  call    WPP_SF_d
0x180039fb8  jmp     loc_18003A080
0x180039fbd  mov     rcx, [rsp+310h+var_2D0]; lpFileName
0x180039fc2  xor     r9d, r9d; lpSecurityAttributes
0x180039fc5  mov     [rsp+310h+hTemplateFile], r15; hTemplateFile
0x180039fca  mov     edx, 40000000h; dwDesiredAccess
0x180039fcf  mov     [rsp+310h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180039fd4  mov     [rsp+310h+dwCreationDisposition], 3; dwCreationDisposition
0x180039fdc  lea     r8d, [r9+3]; dwShareMode
0x180039fe0  call    cs:__imp_CreateFileW
0x180039fe6  mov     rdi, rax
0x180039fe9  lea     rcx, [rax+1]
0x180039fed  cmp     rcx, 1
0x180039ff1  jbe     short loc_18003A033
0x180039ff3  mov     rcx, rax; hFile
0x180039ff6  call    cs:__imp_FlushFileBuffers
0x180039ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a003  cmp     rcx, rsi
0x18003a006  jz      short loc_18003A028
0x18003a008  test    byte ptr [rcx+1Ch], 8
0x18003a00c  jz      short loc_18003A028
0x18003a00e  mov     r9, [rsp+310h+var_2D0]
0x18003a013  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003a01a  mov     rcx, [rcx+10h]
0x18003a01e  mov     edx, 61h ; 'a'
0x18003a023  call    WPP_SF_S
0x18003a028  mov     rcx, rdi; hObject
0x18003a02b  call    cs:__imp_CloseHandle
0x18003a031  jmp     short loc_18003A080
0x18003a033  mov     rax, cs:WPP_GLOBAL_Control
0x18003a03a  cmp     rax, rsi
0x18003a03d  jz      short loc_18003A080
0x18003a03f  test    byte ptr [rax+1Ch], 2
0x18003a043  jz      short loc_18003A080
0x18003a045  mov     rdi, [rsp+310h+var_2D0]
0x18003a04a  call    cs:__imp_GetLastError
0x18003a050  test    eax, eax
0x18003a052  jle     short loc_18003A05C
0x18003a054  movzx   eax, ax
0x18003a057  or      eax, 80070000h
0x18003a05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a063  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003a06a  mov     edx, 62h ; 'b'
0x18003a06f  mov     qword ptr [rsp+310h+dwCreationDisposition], rdi
0x18003a074  mov     r9d, eax
0x18003a077  mov     rcx, [rcx+10h]
0x18003a07b  call    WPP_SF_dS
0x18003a080  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18003a084  mov     rcx, rbx; hFindFile
0x18003a087  call    cs:__imp_FindNextFileW
0x18003a08d  test    eax, eax
0x18003a08f  jnz     loc_180039F34
0x18003a095  jmp     short loc_18003A0A2
0x18003a097  call    cs:__imp_GetLastError
0x18003a09d  cmp     eax, 2
0x18003a0a0  jnz     short loc_18003A0A7
0x18003a0a2  mov     edi, r15d
0x18003a0a5  jmp     short loc_18003A0F7
0x18003a0a7  call    cs:__imp_GetLastError
0x18003a0ad  mov     edi, eax
0x18003a0af  test    eax, eax
0x18003a0b1  jle     short loc_18003A0BC
0x18003a0b3  movzx   edi, ax
0x18003a0b6  or      edi, 80070000h
0x18003a0bc  test    edi, edi
0x18003a0be  mov     eax, 80004005h
0x18003a0c3  cmovns  edi, eax
0x18003a0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0cd  lea     rsi, WPP_GLOBAL_Control
0x18003a0d4  cmp     rcx, rsi
0x18003a0d7  jz      short loc_18003A0F7
0x18003a0d9  test    byte ptr [rcx+1Ch], 1
0x18003a0dd  jz      short loc_18003A0F7
0x18003a0df  mov     edx, 5Fh ; '_'
0x18003a0e4  mov     r9d, edi
0x18003a0e7  mov     rcx, [rcx+10h]
0x18003a0eb  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003a0f2  call    WPP_SF_d
0x18003a0f7  mov     rcx, [rsp+310h+var_2D0]; void *
0x18003a0fc  lea     rax, [rsp+310h+var_2C0]
0x18003a101  cmp     rcx, rax
0x18003a104  jz      short loc_18003A112
0x18003a106  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a10d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a112  mov     rcx, [rsp+310h+lpFileName]; void *
0x18003a117  lea     rax, [rsp+310h+var_2A0]
0x18003a11c  cmp     rcx, rax
0x18003a11f  jz      short loc_18003A12D
0x18003a121  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a128  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a12d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003a131  jz      short loc_18003A13C
0x18003a133  mov     rcx, rbx; hFindFile
0x18003a136  call    cs:__imp_FindClose
0x18003a13c  mov     eax, edi
0x18003a13e  mov     rcx, [rbp+210h+var_40]
0x18003a145  xor     rcx, rsp; StackCookie
0x18003a148  call    __security_check_cookie
0x18003a14d  add     rsp, 2E8h
0x18003a154  pop     r15
0x18003a156  pop     r14
0x18003a158  pop     rdi
0x18003a159  pop     rsi
0x18003a15a  pop     rbx
0x18003a15b  pop     rbp
0x18003a15c  retn
```
