# CopyIconToDisk(wchar_t const *,wchar_t const *)

- ea: `0x1800ca3bc`
- end: `0x1800ca65c`
- name: `?CopyIconToDisk@@YAJPEB_W0@Z`
- size: `672`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800a6020`

## callees

- `0x180014d80`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800ca360`
- `0x1800ca3bc`
- `0x1800caf10`
- `0x180136d80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca61e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca61e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ca455`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ca455`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca5ef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca5fc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca609`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca616`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca5ef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca5fc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca609`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca616`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CopyIconToDisk(const wchar_t *a1, const wchar_t *a2)
{
  signed int System32Directory; // ebx
  __int64 v6; // [rsp+20h] [rbp-E0h]
  __int64 v7; // [rsp+20h] [rbp-E0h]
  __int64 v8; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+28h] [rbp-D8h]
  __int64 v11; // [rsp+28h] [rbp-D8h]
  wchar_t v12[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v13[520]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR Dst[520]; // [rsp+650h] [rbp+550h] BYREF
  WCHAR v15[520]; // [rsp+A60h] [rbp+960h] BYREF
  WCHAR v16[520]; // [rsp+E70h] [rbp+D70h] BYREF
  WCHAR v17[520]; // [rsp+1280h] [rbp+1180h] BYREF
  WCHAR FileName[520]; // [rsp+1690h] [rbp+1590h] BYREF

  memset_0(v15, 0, sizeof(v15));
  memset_0(v16, 0, sizeof(v16));
  memset_0(v17, 0, sizeof(v17));
  System32Directory = GetSystem32Directory(v12);
  if ( !System32Directory )
  {
    if ( ExpandEnvironmentStringsW(a2, Dst, 0x208u) )
    {
      StringCchPrintfW(v13, 0x208u, L"%s_%d.bin", Dst, 16);
      StringCchPrintfW(FileName, 0x208u, L"%s\\networklist\\icons\\%s_%d.bin", v12, a1, 16);
      System32Directory = CopyIconFile(v13, FileName);
      if ( System32Directory )
        goto LABEL_7;
      LODWORD(v6) = 24;
      StringCchPrintfW(v13, 0x208u, L"%s_%d.bin", Dst, v6);
      LODWORD(v9) = 24;
      StringCchPrintfW(v15, 0x208u, L"%s\\networklist\\icons\\%s_%d.bin", v12, a1, v9);
      System32Directory = CopyIconFile(v13, v15);
      if ( System32Directory )
        goto LABEL_7;
      LODWORD(v7) = 32;
      StringCchPrintfW(v13, 0x208u, L"%s_%d.bin", Dst, v7);
      LODWORD(v10) = 32;
      StringCchPrintfW(v16, 0x208u, L"%s\\networklist\\icons\\%s_%d.bin", v12, a1, v10);
      System32Directory = CopyIconFile(v13, v16);
      if ( System32Directory
        || (LODWORD(v8) = 48,
            StringCchPrintfW(v13, 0x208u, L"%s_%d.bin", Dst, v8),
            LODWORD(v11) = 48,
            StringCchPrintfW(v17, 0x208u, L"%s\\networklist\\icons\\%s_%d.bin", v12, a1, v11),
            (System32Directory = CopyIconFile(v13, v17)) != 0) )
      {
LABEL_7:
        DeleteFileW(FileName);
        DeleteFileW(v15);
        DeleteFileW(v16);
        DeleteFileW(v17);
      }
    }
    else
    {
      System32Directory = GetLastError();
    }
  }
  if ( System32Directory > 0 )
    return (unsigned __int16)System32Directory | 0x80070000;
  return (unsigned int)System32Directory;
}

```

## disassembly

```asm
0x1800ca3bc  mov     [rsp-8+arg_10], rbx
0x1800ca3c1  mov     [rsp-8+arg_18], rsi
0x1800ca3c6  push    rbp
0x1800ca3c7  push    rdi
0x1800ca3c8  push    r14
0x1800ca3ca  lea     rbp, [rsp-19B0h]
0x1800ca3d2  mov     eax, 1AB0h
0x1800ca3d7  call    _alloca_probe
0x1800ca3dc  sub     rsp, rax
0x1800ca3df  mov     rax, cs:__security_cookie
0x1800ca3e6  xor     rax, rsp
0x1800ca3e9  mov     [rbp+19C0h+var_20], rax
0x1800ca3f0  mov     rsi, rdx
0x1800ca3f3  mov     rdi, rcx
0x1800ca3f6  mov     ebx, 410h
0x1800ca3fb  lea     rcx, [rbp+19C0h+var_1060]; void *
0x1800ca402  mov     r8d, ebx; Size
0x1800ca405  xor     edx, edx; Val
0x1800ca407  call    memset_0
0x1800ca40c  mov     r8d, ebx; Size
0x1800ca40f  lea     rcx, [rbp+19C0h+var_C50]; void *
0x1800ca416  xor     edx, edx; Val
0x1800ca418  call    memset_0
0x1800ca41d  mov     r8d, ebx; Size
0x1800ca420  lea     rcx, [rbp+19C0h+var_840]; void *
0x1800ca427  xor     edx, edx; Val
0x1800ca429  call    memset_0
0x1800ca42e  lea     rcx, [rsp+1AC0h+var_1A90]; wchar_t *
0x1800ca433  call    ?GetSystem32Directory@@YAKPEA_W@Z; GetSystem32Directory(wchar_t *)
0x1800ca438  mov     ebx, eax
0x1800ca43a  test    eax, eax
0x1800ca43c  jnz     loc_1800CA626
0x1800ca442  mov     r14d, 208h
0x1800ca448  lea     rdx, [rbp+19C0h+Dst]; lpDst
0x1800ca44f  mov     r8d, r14d; nSize
0x1800ca452  mov     rcx, rsi; lpSrc
0x1800ca455  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ca45b  test    eax, eax
0x1800ca45d  jz      loc_1800CA61E
0x1800ca463  lea     rsi, aSDBin; "%s_%d.bin"
0x1800ca46a  mov     ebx, 10h
0x1800ca46f  mov     r8, rsi; wchar_t *
0x1800ca472  mov     dword ptr [rsp+1AC0h+var_1AA0], ebx
0x1800ca476  lea     r9, [rbp+19C0h+Dst]
0x1800ca47d  mov     edx, r14d; unsigned __int64
0x1800ca480  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca487  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca48c  lea     r9, [rsp+1AC0h+var_1A90]
0x1800ca491  mov     dword ptr [rsp+1AC0h+var_1A98], ebx
0x1800ca495  lea     r8, aSNetworklistIc_0; "%s\\networklist\\icons\\%s_%d.bin"
0x1800ca49c  mov     [rsp+1AC0h+var_1AA0], rdi
0x1800ca4a1  mov     edx, r14d; unsigned __int64
0x1800ca4a4  lea     rcx, [rbp+19C0h+FileName]; wchar_t *
0x1800ca4ab  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca4b0  lea     rdx, [rbp+19C0h+FileName]; wchar_t *
0x1800ca4b7  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca4be  call    ?CopyIconFile@@YAKPEB_W0@Z; CopyIconFile(wchar_t const *,wchar_t const *)
0x1800ca4c3  mov     ebx, eax
0x1800ca4c5  test    eax, eax
0x1800ca4c7  jnz     loc_1800CA5E8
0x1800ca4cd  lea     ebx, [rax+18h]
0x1800ca4d0  mov     r8, rsi; wchar_t *
0x1800ca4d3  lea     r9, [rbp+19C0h+Dst]
0x1800ca4da  mov     dword ptr [rsp+1AC0h+var_1AA0], ebx
0x1800ca4de  mov     edx, r14d; unsigned __int64
0x1800ca4e1  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca4e8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca4ed  lea     r9, [rsp+1AC0h+var_1A90]
0x1800ca4f2  mov     dword ptr [rsp+1AC0h+var_1A98], ebx
0x1800ca4f6  lea     r8, aSNetworklistIc_0; "%s\\networklist\\icons\\%s_%d.bin"
0x1800ca4fd  mov     [rsp+1AC0h+var_1AA0], rdi
0x1800ca502  mov     edx, r14d; unsigned __int64
0x1800ca505  lea     rcx, [rbp+19C0h+var_1060]; wchar_t *
0x1800ca50c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca511  lea     rdx, [rbp+19C0h+var_1060]; wchar_t *
0x1800ca518  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca51f  call    ?CopyIconFile@@YAKPEB_W0@Z; CopyIconFile(wchar_t const *,wchar_t const *)
0x1800ca524  mov     ebx, eax
0x1800ca526  test    eax, eax
0x1800ca528  jnz     loc_1800CA5E8
0x1800ca52e  lea     ebx, [rax+20h]
0x1800ca531  mov     r8, rsi; wchar_t *
0x1800ca534  lea     r9, [rbp+19C0h+Dst]
0x1800ca53b  mov     dword ptr [rsp+1AC0h+var_1AA0], ebx
0x1800ca53f  mov     edx, r14d; unsigned __int64
0x1800ca542  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca549  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca54e  lea     r9, [rsp+1AC0h+var_1A90]
0x1800ca553  mov     dword ptr [rsp+1AC0h+var_1A98], ebx
0x1800ca557  lea     r8, aSNetworklistIc_0; "%s\\networklist\\icons\\%s_%d.bin"
0x1800ca55e  mov     [rsp+1AC0h+var_1AA0], rdi
0x1800ca563  mov     edx, r14d; unsigned __int64
0x1800ca566  lea     rcx, [rbp+19C0h+var_C50]; wchar_t *
0x1800ca56d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca572  lea     rdx, [rbp+19C0h+var_C50]; wchar_t *
0x1800ca579  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca580  call    ?CopyIconFile@@YAKPEB_W0@Z; CopyIconFile(wchar_t const *,wchar_t const *)
0x1800ca585  mov     ebx, eax
0x1800ca587  test    eax, eax
0x1800ca589  jnz     short loc_1800CA5E8
0x1800ca58b  lea     ebx, [rax+30h]
0x1800ca58e  mov     r8, rsi; wchar_t *
0x1800ca591  lea     r9, [rbp+19C0h+Dst]
0x1800ca598  mov     dword ptr [rsp+1AC0h+var_1AA0], ebx
0x1800ca59c  mov     edx, r14d; unsigned __int64
0x1800ca59f  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca5a6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca5ab  lea     r9, [rsp+1AC0h+var_1A90]
0x1800ca5b0  mov     dword ptr [rsp+1AC0h+var_1A98], ebx
0x1800ca5b4  lea     r8, aSNetworklistIc_0; "%s\\networklist\\icons\\%s_%d.bin"
0x1800ca5bb  mov     [rsp+1AC0h+var_1AA0], rdi
0x1800ca5c0  mov     edx, r14d; unsigned __int64
0x1800ca5c3  lea     rcx, [rbp+19C0h+var_840]; wchar_t *
0x1800ca5ca  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ca5cf  lea     rdx, [rbp+19C0h+var_840]; wchar_t *
0x1800ca5d6  lea     rcx, [rbp+19C0h+var_1880]; wchar_t *
0x1800ca5dd  call    ?CopyIconFile@@YAKPEB_W0@Z; CopyIconFile(wchar_t const *,wchar_t const *)
0x1800ca5e2  mov     ebx, eax
0x1800ca5e4  test    eax, eax
0x1800ca5e6  jz      short loc_1800CA626
0x1800ca5e8  lea     rcx, [rbp+19C0h+FileName]; lpFileName
0x1800ca5ef  call    cs:__imp_DeleteFileW
0x1800ca5f5  lea     rcx, [rbp+19C0h+var_1060]; lpFileName
0x1800ca5fc  call    cs:__imp_DeleteFileW
0x1800ca602  lea     rcx, [rbp+19C0h+var_C50]; lpFileName
0x1800ca609  call    cs:__imp_DeleteFileW
0x1800ca60f  lea     rcx, [rbp+19C0h+var_840]; lpFileName
0x1800ca616  call    cs:__imp_DeleteFileW
0x1800ca61c  jmp     short loc_1800CA626
0x1800ca61e  call    cs:__imp_GetLastError
0x1800ca624  mov     ebx, eax
0x1800ca626  test    ebx, ebx
0x1800ca628  jle     short loc_1800CA633
0x1800ca62a  movzx   ebx, bx
0x1800ca62d  or      ebx, 80070000h
0x1800ca633  mov     eax, ebx
0x1800ca635  mov     rcx, [rbp+19C0h+var_20]
0x1800ca63c  xor     rcx, rsp; StackCookie
0x1800ca63f  call    __security_check_cookie
0x1800ca644  lea     r11, [rsp+1AC0h+var_10]
0x1800ca64c  mov     rbx, [r11+30h]
0x1800ca650  mov     rsi, [r11+38h]
0x1800ca654  mov     rsp, r11
0x1800ca657  pop     r14
0x1800ca659  pop     rdi
0x1800ca65a  pop     rbp
0x1800ca65b  retn
```
