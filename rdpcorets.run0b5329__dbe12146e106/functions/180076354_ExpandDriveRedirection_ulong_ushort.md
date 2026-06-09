# ExpandDriveRedirection(ulong,ushort *)

- ea: `0x180076354`
- end: `0x1800764ea`
- name: `?ExpandDriveRedirection@@YAJKPEAG@Z`
- size: `406`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180076d08`

## callees

- `0x180009088`
- `0x18000e420`
- `0x180033da0`
- `0x180076354`

## import_xrefs

- `RDPBASE!TRC_TraceBufferW` at `0x1800763ce`
- `RDPBASE!TRC_TraceBufferW` at `0x1800764bd`
- `RDPBASE!TRC_TraceBufferW` at `0x1800763ce`
- `RDPBASE!TRC_TraceBufferW` at `0x1800764bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800763e9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800763e9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180076380`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180076380`

## string_xrefs

- `0x18007646d`: `StringCchCopy hr[0x%x]`
- `0x18007638d`: `PathGetDriveNumberW hr[0x%x]`
- `0x180076481`: `Invalid DirectoryAndFile hr[0x%x]`

## pseudocode

```c
__int64 __fastcall ExpandDriveRedirection(unsigned int a1, unsigned __int16 *a2)
{
  unsigned __int64 v2; // rbp
  unsigned int DriveNumberW; // eax
  __int16 v5; // bx
  unsigned int v6; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r8
  LPWSTR v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v13; // [rsp+38h] [rbp-230h]
  int v14; // [rsp+38h] [rbp-230h]
  int v15; // [rsp+38h] [rbp-230h]
  int v16; // [rsp+38h] [rbp-230h]
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = a1;
  DriveNumberW = PathGetDriveNumberW(a2);
  v5 = DriveNumberW;
  if ( DriveNumberW > 0x19 )
  {
    v6 = -2147024881;
    v14 = -2147024881;
    TRC_TraceBufferW(
      3,
      4096,
      547,
      L"GetDrivePrefix",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      L"PathGetDriveNumberW hr[0x%x]",
      v14);
    v7 = L"GetDrivePrefix hr[0x%x]";
    v8 = 576;
LABEL_11:
    LODWORD(v13) = v6;
    TRC_TraceBufferW(
      3,
      4096,
      v8,
      L"ExpandDriveRedirection",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      v7,
      v13);
    return v6;
  }
  v9 = PathSkipRootW(a2);
  if ( !v9 || v9 < a2 || v9 > a2 + 260 )
  {
    v6 = -2147467259;
    v7 = L"Invalid DirectoryAndFile hr[0x%x]";
    v8 = 585;
    goto LABEL_11;
  }
  v10 = StringCchPrintfW(v17, 0x104u, L"\\\\tsclient\\%c\\%s", (unsigned __int16)(v5 + 65), v9);
  v6 = v10;
  if ( v10 >= 0 )
  {
    v11 = StringCchCopyW(a2, v2, v17);
    v6 = v11;
    if ( v11 < 0 )
    {
      v16 = v11;
      TRC_TraceBufferW(
        3,
        4096,
        595,
        L"ExpandDriveRedirection",
        L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
        0,
        L"StringCchCopy hr[0x%x]",
        v16);
    }
  }
  else
  {
    v15 = v10;
    TRC_TraceBufferW(
      3,
      4096,
      592,
      L"ExpandDriveRedirection",
      L"clientcore\\termsrv\\rap\\allow\\lib\\tsallow.cpp",
      0,
      L"StringCchPrintf hr[0x%x]",
      v15);
  }
  return v6;
}

```

## disassembly

```asm
0x180076354  mov     [rsp+arg_10], rbx
0x180076359  mov     [rsp+arg_18], rbp
0x18007635e  push    rsi
0x18007635f  sub     rsp, 260h
0x180076366  mov     rax, cs:__security_cookie
0x18007636d  xor     rax, rsp
0x180076370  mov     [rsp+268h+var_18], rax
0x180076378  mov     ebp, ecx
0x18007637a  mov     rsi, rdx
0x18007637d  mov     rcx, rdx; pszPath
0x180076380  call    cs:__imp_PathGetDriveNumberW
0x180076386  mov     ebx, eax
0x180076388  cmp     eax, 19h
0x18007638b  jbe     short loc_1800763E6
0x18007638d  lea     rax, aPathgetdrivenu; "PathGetDriveNumberW hr[0x%x]"
0x180076394  mov     ebx, 8007000Fh
0x180076399  mov     dword ptr [rsp+268h+var_230], ebx
0x18007639d  lea     rsi, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x1800763a4  mov     [rsp+268h+var_238], rax
0x1800763a9  lea     r9, aGetdriveprefix; "GetDrivePrefix"
0x1800763b0  mov     [rsp+268h+var_240], 0
0x1800763b9  mov     edx, 1000h
0x1800763be  mov     ecx, 3
0x1800763c3  mov     [rsp+268h+var_248], rsi
0x1800763c8  mov     r8d, 223h
0x1800763ce  call    cs:__imp_TRC_TraceBufferW
0x1800763d4  lea     rax, aGetdriveprefix_0; "GetDrivePrefix hr[0x%x]"
0x1800763db  mov     r8d, 240h
0x1800763e1  jmp     loc_180076495
0x1800763e6  mov     rcx, rsi; pszPath
0x1800763e9  call    cs:__imp_PathSkipRootW
0x1800763ef  test    rax, rax
0x1800763f2  jz      loc_18007647C
0x1800763f8  cmp     rax, rsi
0x1800763fb  jb      short loc_18007647C
0x1800763fd  lea     rcx, [rsi+208h]
0x180076404  cmp     rax, rcx
0x180076407  ja      short loc_18007647C
0x180076409  add     bx, 41h ; 'A'
0x18007640d  mov     [rsp+268h+var_248], rax
0x180076412  movzx   r9d, bx
0x180076416  lea     r8, aTsclientCS; "\\\\tsclient\\%c\\%s"
0x18007641d  mov     edx, 104h; unsigned __int64
0x180076422  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180076427  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007642c  mov     ebx, eax
0x18007642e  test    eax, eax
0x180076430  jns     short loc_18007644C
0x180076432  mov     dword ptr [rsp+268h+var_230], eax
0x180076436  lea     rsi, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x18007643d  lea     rax, aStringcchprint_1; "StringCchPrintf hr[0x%x]"
0x180076444  mov     r8d, 250h
0x18007644a  jmp     short loc_180076499
0x18007644c  mov     rdx, rbp; unsigned __int64
0x18007644f  lea     r8, [rsp+268h+var_228]; unsigned __int16 *
0x180076454  mov     rcx, rsi; unsigned __int16 *
0x180076457  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007645c  mov     ebx, eax
0x18007645e  test    eax, eax
0x180076460  jns     short loc_1800764C3
0x180076462  mov     dword ptr [rsp+268h+var_230], eax
0x180076466  lea     rsi, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x18007646d  lea     rax, aStringcchcopyH; "StringCchCopy hr[0x%x]"
0x180076474  mov     r8d, 253h
0x18007647a  jmp     short loc_180076499
0x18007647c  mov     ebx, 80004005h
0x180076481  lea     rax, aInvalidDirecto; "Invalid DirectoryAndFile hr[0x%x]"
0x180076488  lea     rsi, aClientcoreTerm_1; "clientcore\\termsrv\\rap\\allow\\lib\\t"...
0x18007648f  mov     r8d, 249h
0x180076495  mov     dword ptr [rsp+268h+var_230], ebx
0x180076499  mov     [rsp+268h+var_238], rax
0x18007649e  lea     r9, aExpanddrivered; "ExpandDriveRedirection"
0x1800764a5  mov     [rsp+268h+var_240], 0
0x1800764ae  mov     edx, 1000h
0x1800764b3  mov     ecx, 3
0x1800764b8  mov     [rsp+268h+var_248], rsi
0x1800764bd  call    cs:__imp_TRC_TraceBufferW
0x1800764c3  mov     eax, ebx
0x1800764c5  mov     rcx, [rsp+268h+var_18]
0x1800764cd  xor     rcx, rsp; StackCookie
0x1800764d0  call    __security_check_cookie
0x1800764d5  lea     r11, [rsp+268h+var_8]
0x1800764dd  mov     rbx, [r11+20h]
0x1800764e1  mov     rbp, [r11+28h]
0x1800764e5  mov     rsp, r11
0x1800764e8  pop     rsi
0x1800764e9  retn
```
