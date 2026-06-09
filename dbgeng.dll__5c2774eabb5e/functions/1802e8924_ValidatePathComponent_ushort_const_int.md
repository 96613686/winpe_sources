# ValidatePathComponent(ushort const *,int)

- ea: `0x1802e8924`
- end: `0x1802e8b16`
- name: `?ValidatePathComponent@@YAHPEBGH@Z`
- size: `498`
- prototype: `__int64 __fastcall(wchar_t *String1, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802e2cc8`

## callees

- `0x1800793cc`
- `0x1800a7e58`
- `0x1800c12b8`
- `0x1800f0f40`
- `0x1802bdf98`
- `0x1802e52f0`
- `0x1802e8924`
- `0x18041c610`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e897a`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e899e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e89c2`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e897a`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e899e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1802e89c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1802e8a7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1802e8a9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1802e8a7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1802e8a9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e8a04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e8a04`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1802e8a8f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1802e8a8f`

## string_xrefs

- `0x1802e895a`: `WARNING: Empty path component\n`
- `0x1802e89b8`: `CACHE*`
- `0x1802e8ade`: `WARNING: Network path disallowed: '%s'\n`
- `0x1802e8a56`: `WARNING: Unable to net-check path: '%s'\n`
- `0x1802e8a62`: `WARNING: Invalid path disallowed: '%s'\n`
- `0x1802e8ac9`: `WARNING: Non-directory path: '%s'\n`
- `0x1802e8ab5`: `WARNING: Inaccessible path: '%s'\n`

## pseudocode

```c
__int64 __fastcall ValidatePathComponent(wchar_t *String1)
{
  __int64 v1; // rax
  unsigned int v4; // eax
  WCHAR *v5; // rdx
  UINT v6; // ebx
  DWORD FileAttributesW; // edi
  WCHAR Dst[520]; // [rsp+20h] [rbp-428h] BYREF

  v1 = -1;
  do
    ++v1;
  while ( String1[v1] );
  if ( !v1 )
  {
    WarnOut(L"WARNING: Empty path component\n");
    return 0;
  }
  if ( _wcsnicmp(String1, L"SYMSRV*", 7u)
    && _wcsnicmp(String1, L"SRV*", 4u)
    && _wcsnicmp(String1, L"CACHE*", 6u)
    && !IsSourceServerPathComponent(String1)
    && !(unsigned int)DbgClientLibIsUrlPathComponent(String1) )
  {
    if ( !ExpandEnvironmentStringsW(String1, Dst, 0x208u) )
    {
      ErrOut(L"WARNING: Environment expansion failed: '%s'\n", String1);
      return 0;
    }
    if ( (g_EngOptions & 8) != 0 )
    {
      v4 = NetworkPathCheck(Dst);
      if ( v4 )
      {
        v5 = Dst;
        if ( v4 == 161 )
        {
          WarnOut(L"WARNING: Invalid path disallowed: '%s'\n", Dst);
          return 0;
        }
        if ( v4 != 4350 )
        {
          WarnOut(L"WARNING: Unable to net-check path: '%s'\n", Dst);
          return 0;
        }
LABEL_26:
        WarnOut(L"WARNING: Network path disallowed: '%s'\n", v5);
        return 0;
      }
    }
    if ( !(unsigned int)AnySystemProcesses(1) )
    {
      v6 = SetErrorMode(1u);
      FileAttributesW = GetFileAttributesW(Dst);
      SetErrorMode(v6);
      if ( FileAttributesW == -1 )
      {
        WarnOut(L"WARNING: Inaccessible path: '%s'\n", Dst);
        return 0;
      }
      if ( (FileAttributesW & 0x10) == 0 )
      {
        WarnOut(L"WARNING: Non-directory path: '%s'\n", Dst);
        return 0;
      }
    }
  }
  else if ( (g_EngOptions & 8) != 0 )
  {
    v5 = String1;
    goto LABEL_26;
  }
  return 1;
}

```

## disassembly

```asm
0x1802e8924  mov     [rsp+arg_8], rbx
0x1802e8929  push    rdi
0x1802e892a  sub     rsp, 440h
0x1802e8931  mov     rax, cs:__security_cookie
0x1802e8938  xor     rax, rsp
0x1802e893b  mov     [rsp+448h+var_18], rax
0x1802e8943  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802e8947  mov     rbx, rcx
0x1802e894a  xor     edi, edi
0x1802e894c  inc     rax
0x1802e894f  cmp     [rcx+rax*2], di
0x1802e8953  jnz     short loc_1802E894C
0x1802e8955  test    rax, rax
0x1802e8958  jnz     short loc_1802E896D
0x1802e895a  lea     rcx, aWarningEmptyPa; "WARNING: Empty path component\n"
0x1802e8961  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802e8966  xor     eax, eax
0x1802e8968  jmp     loc_1802E8AF4
0x1802e896d  mov     r8d, 7; MaxCount
0x1802e8973  lea     rdx, aSymsrv; "SYMSRV*"
0x1802e897a  call    cs:__imp__wcsnicmp
0x1802e8981  nop     dword ptr [rax+rax+00h]
0x1802e8986  test    eax, eax
0x1802e8988  jz      loc_1802E8AD2
0x1802e898e  mov     r8d, 4; MaxCount
0x1802e8994  lea     rdx, aSrv; "SRV*"
0x1802e899b  mov     rcx, rbx; String1
0x1802e899e  call    cs:__imp__wcsnicmp
0x1802e89a5  nop     dword ptr [rax+rax+00h]
0x1802e89aa  test    eax, eax
0x1802e89ac  jz      loc_1802E8AD2
0x1802e89b2  mov     r8d, 6; MaxCount
0x1802e89b8  lea     rdx, aCache; "CACHE*"
0x1802e89bf  mov     rcx, rbx; String1
0x1802e89c2  call    cs:__imp__wcsnicmp
0x1802e89c9  nop     dword ptr [rax+rax+00h]
0x1802e89ce  test    eax, eax
0x1802e89d0  jz      loc_1802E8AD2
0x1802e89d6  mov     rcx, rbx; Str
0x1802e89d9  call    ?IsSourceServerPathComponent@@YA_NPEBG@Z; IsSourceServerPathComponent(ushort const *)
0x1802e89de  test    al, al
0x1802e89e0  jnz     loc_1802E8AD2
0x1802e89e6  mov     rcx, rbx; String1
0x1802e89e9  call    DbgClientLibIsUrlPathComponent
0x1802e89ee  test    eax, eax
0x1802e89f0  jnz     loc_1802E8AD2
0x1802e89f6  mov     r8d, 208h; nSize
0x1802e89fc  lea     rdx, [rsp+448h+Dst]; lpDst
0x1802e8a01  mov     rcx, rbx; lpSrc
0x1802e8a04  call    cs:__imp_ExpandEnvironmentStringsW
0x1802e8a0b  nop     dword ptr [rax+rax+00h]
0x1802e8a10  test    eax, eax
0x1802e8a12  jnz     short loc_1802E8A28
0x1802e8a14  mov     rdx, rbx
0x1802e8a17  lea     rcx, aWarningEnviron; "WARNING: Environment expansion failed: "...
0x1802e8a1e  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802e8a23  jmp     loc_1802E8966
0x1802e8a28  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x1802e8a2f  jz      short loc_1802E8A6B
0x1802e8a31  lea     rcx, [rsp+448h+Dst]; Src
0x1802e8a36  call    ?NetworkPathCheck@@YAKPEBG@Z; NetworkPathCheck(ushort const *)
0x1802e8a3b  test    eax, eax
0x1802e8a3d  jz      short loc_1802E8A6B
0x1802e8a3f  lea     rdx, [rsp+448h+Dst]
0x1802e8a44  cmp     eax, 0A1h
0x1802e8a49  jz      short loc_1802E8A62
0x1802e8a4b  cmp     eax, 10FEh
0x1802e8a50  jz      loc_1802E8ADE
0x1802e8a56  lea     rcx, aWarningUnableT_2; "WARNING: Unable to net-check path: '%s'"...
0x1802e8a5d  jmp     loc_1802E8AE5
0x1802e8a62  lea     rcx, aWarningInvalid; "WARNING: Invalid path disallowed: '%s'"...
0x1802e8a69  jmp     short loc_1802E8AE5
0x1802e8a6b  mov     ecx, 1; int
0x1802e8a70  call    ?AnySystemProcesses@@YAHH@Z; AnySystemProcesses(int)
0x1802e8a75  test    eax, eax
0x1802e8a77  jnz     short loc_1802E8AEF
0x1802e8a79  lea     ecx, [rax+1]; uMode
0x1802e8a7c  call    cs:__imp_SetErrorMode
0x1802e8a83  nop     dword ptr [rax+rax+00h]
0x1802e8a88  lea     rcx, [rsp+448h+Dst]; lpFileName
0x1802e8a8d  mov     ebx, eax
0x1802e8a8f  call    cs:__imp_GetFileAttributesW
0x1802e8a96  nop     dword ptr [rax+rax+00h]
0x1802e8a9b  mov     ecx, ebx; uMode
0x1802e8a9d  mov     edi, eax
0x1802e8a9f  call    cs:__imp_SetErrorMode
0x1802e8aa6  nop     dword ptr [rax+rax+00h]
0x1802e8aab  cmp     edi, 0FFFFFFFFh
0x1802e8aae  jnz     short loc_1802E8ABE
0x1802e8ab0  lea     rdx, [rsp+448h+Dst]
0x1802e8ab5  lea     rcx, aWarningInacces; "WARNING: Inaccessible path: '%s'\n"
0x1802e8abc  jmp     short loc_1802E8AE5
0x1802e8abe  test    dil, 10h
0x1802e8ac2  jnz     short loc_1802E8AEF
0x1802e8ac4  lea     rdx, [rsp+448h+Dst]
0x1802e8ac9  lea     rcx, aWarningNonDire; "WARNING: Non-directory path: '%s'\n"
0x1802e8ad0  jmp     short loc_1802E8AE5
0x1802e8ad2  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x1802e8ad9  jz      short loc_1802E8AEF
0x1802e8adb  mov     rdx, rbx
0x1802e8ade  lea     rcx, aWarningNetwork_0; "WARNING: Network path disallowed: '%s'"...
0x1802e8ae5  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1802e8aea  jmp     loc_1802E8966
0x1802e8aef  mov     eax, 1
0x1802e8af4  mov     rcx, [rsp+448h+var_18]
0x1802e8afc  xor     rcx, rsp; StackCookie
0x1802e8aff  call    __security_check_cookie
0x1802e8b04  mov     rbx, [rsp+448h+arg_8]
0x1802e8b0c  add     rsp, 440h
0x1802e8b13  pop     rdi
0x1802e8b14  retn
```
