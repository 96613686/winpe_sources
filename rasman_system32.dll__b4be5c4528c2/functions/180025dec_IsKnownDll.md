# IsKnownDll

- ea: `0x180025dec`
- end: `0x180025eca`
- name: `IsKnownDll`
- size: `222`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001a4c0`

## callees

- `0x180025dec`
- `0x180025fa8`
- `0x18002739e`
- `0x1800273d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025e92`
- `msvcrt!_wcsicmp` at `0x180025e92`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180025e4d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180025e4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180025e67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180025e67`

## pseudocode

```c
__int64 __fastcall IsKnownDll(LPCWSTR lpSrc)
{
  unsigned int v2; // ebx
  size_t v3; // rdx
  const wchar_t *v4; // r8
  STRSAFE_LPWSTR *v5; // r9
  size_t *v7; // [rsp+20h] [rbp-448h]
  DWORD v8; // [rsp+28h] [rbp-440h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = 0;
  memset_0(Dst, 0, 0x20Au);
  memset_0(Buffer, 0, 0x20Au);
  if ( lpSrc
    && ExpandEnvironmentStringsW(lpSrc, Dst, 0x105u)
    && GetSystemDirectoryW(Buffer, 0x105u)
    && StringCchCatExW(Buffer, v3, v4, v5, v7, v8) >= 0 )
  {
    return _wcsicmp(Dst, Buffer) == 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180025dec  mov     [rsp+arg_8], rbx
0x180025df1  push    rdi
0x180025df2  sub     rsp, 460h
0x180025df9  mov     rax, cs:__security_cookie
0x180025e00  xor     rax, rsp
0x180025e03  mov     [rsp+468h+var_18], rax
0x180025e0b  mov     rdi, rcx
0x180025e0e  xor     edx, edx; Val
0x180025e10  lea     rcx, [rsp+468h+Dst]; void *
0x180025e18  mov     r8d, 20Ah; Size
0x180025e1e  xor     ebx, ebx
0x180025e20  call    memset_0
0x180025e25  xor     edx, edx; Val
0x180025e27  lea     rcx, [rsp+468h+Buffer]; void *
0x180025e2c  mov     r8d, 20Ah; Size
0x180025e32  call    memset_0
0x180025e37  test    rdi, rdi
0x180025e3a  jz      short loc_180025EA6
0x180025e3c  mov     r8d, 105h; nSize
0x180025e42  lea     rdx, [rsp+468h+Dst]; lpDst
0x180025e4a  mov     rcx, rdi; lpSrc
0x180025e4d  call    cs:__imp_ExpandEnvironmentStringsW
0x180025e54  nop     dword ptr [rax+rax+00h]
0x180025e59  test    eax, eax
0x180025e5b  jz      short loc_180025EA6
0x180025e5d  mov     edx, 105h; uSize
0x180025e62  lea     rcx, [rsp+468h+Buffer]; lpBuffer
0x180025e67  call    cs:__imp_GetSystemDirectoryW
0x180025e6e  nop     dword ptr [rax+rax+00h]
0x180025e73  test    eax, eax
0x180025e75  jz      short loc_180025EA6
0x180025e77  lea     rcx, [rsp+468h+Buffer]; pszDest
0x180025e7c  call    StringCchCatExW
0x180025e81  test    eax, eax
0x180025e83  js      short loc_180025EA6
0x180025e85  lea     rdx, [rsp+468h+Buffer]; String2
0x180025e8a  lea     rcx, [rsp+468h+Dst]; String1
0x180025e92  call    cs:__imp__wcsicmp
0x180025e99  nop     dword ptr [rax+rax+00h]
0x180025e9e  test    eax, eax
0x180025ea0  lea     ecx, [rbx+1]
0x180025ea3  cmovz   ebx, ecx
0x180025ea6  mov     eax, ebx
0x180025ea8  mov     rcx, [rsp+468h+var_18]
0x180025eb0  xor     rcx, rsp; StackCookie
0x180025eb3  call    __security_check_cookie
0x180025eb8  mov     rbx, [rsp+468h+arg_8]
0x180025ec0  add     rsp, 460h
0x180025ec7  pop     rdi
0x180025ec8  retn
```
