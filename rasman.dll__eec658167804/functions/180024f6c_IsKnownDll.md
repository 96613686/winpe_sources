# IsKnownDll

- ea: `0x180024f6c`
- end: `0x180025037`
- name: `IsKnownDll`
- size: `203`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180019ad0`

## callees

- `0x180024f6c`
- `0x1800250fc`
- `0x1800263ce`
- `0x180026400`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025006`
- `msvcrt!_wcsicmp` at `0x180025006`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180024fcd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180024fcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180024fe1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180024fe1`

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
0x180024f6c  mov     [rsp+arg_8], rbx
0x180024f71  push    rdi
0x180024f72  sub     rsp, 460h
0x180024f79  mov     rax, cs:__security_cookie
0x180024f80  xor     rax, rsp
0x180024f83  mov     [rsp+468h+var_18], rax
0x180024f8b  mov     rdi, rcx
0x180024f8e  xor     edx, edx; Val
0x180024f90  lea     rcx, [rsp+468h+Dst]; void *
0x180024f98  mov     r8d, 20Ah; Size
0x180024f9e  xor     ebx, ebx
0x180024fa0  call    memset_0
0x180024fa5  xor     edx, edx; Val
0x180024fa7  lea     rcx, [rsp+468h+Buffer]; void *
0x180024fac  mov     r8d, 20Ah; Size
0x180024fb2  call    memset_0
0x180024fb7  test    rdi, rdi
0x180024fba  jz      short loc_180025014
0x180024fbc  mov     r8d, 105h; nSize
0x180024fc2  lea     rdx, [rsp+468h+Dst]; lpDst
0x180024fca  mov     rcx, rdi; lpSrc
0x180024fcd  call    cs:__imp_ExpandEnvironmentStringsW
0x180024fd3  test    eax, eax
0x180024fd5  jz      short loc_180025014
0x180024fd7  mov     edx, 105h; uSize
0x180024fdc  lea     rcx, [rsp+468h+Buffer]; lpBuffer
0x180024fe1  call    cs:__imp_GetSystemDirectoryW
0x180024fe7  test    eax, eax
0x180024fe9  jz      short loc_180025014
0x180024feb  lea     rcx, [rsp+468h+Buffer]; pszDest
0x180024ff0  call    StringCchCatExW
0x180024ff5  test    eax, eax
0x180024ff7  js      short loc_180025014
0x180024ff9  lea     rdx, [rsp+468h+Buffer]; String2
0x180024ffe  lea     rcx, [rsp+468h+Dst]; String1
0x180025006  call    cs:__imp__wcsicmp
0x18002500c  test    eax, eax
0x18002500e  lea     ecx, [rbx+1]
0x180025011  cmovz   ebx, ecx
0x180025014  mov     eax, ebx
0x180025016  mov     rcx, [rsp+468h+var_18]
0x18002501e  xor     rcx, rsp; StackCookie
0x180025021  call    __security_check_cookie
0x180025026  mov     rbx, [rsp+468h+arg_8]
0x18002502e  add     rsp, 460h
0x180025035  pop     rdi
0x180025036  retn
```
