# RegRemoveSubtree

- ea: `0x180010cc0`
- end: `0x180010d93`
- name: `RegRemoveSubtree`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010cc0`
- `0x1800112a0`

## callees

- `0x1800014f0`
- `0x180010cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180010d01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180010d01`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180010d1d`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180010d51`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180010d1d`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180010d51`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180010d6c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180010d6c`

## pseudocode

```c
LSTATUS __fastcall RegRemoveSubtree(HKEY a1, const CHAR *a2)
{
  LSTATUS result; // eax
  __int64 v5; // r8
  HKEY hKey; // [rsp+30h] [rbp-128h] BYREF
  CHAR Name[256]; // [rsp+40h] [rbp-118h] BYREF

  hKey = 0;
  result = RegOpenKeyExA(a1, a2, 0, 0xF003Fu, &hKey);
  if ( !result )
  {
    while ( !RegEnumKeyA(hKey, 0, Name, 0x100u) )
      RegRemoveSubtree(hKey, Name, v5);
    RegCloseKey(hKey);
    return RegDeleteKeyA(a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x180010cc0  mov     [rsp+arg_10], rbx
0x180010cc5  push    rdi
0x180010cc6  sub     rsp, 150h
0x180010ccd  mov     rax, cs:__security_cookie
0x180010cd4  xor     rax, rsp
0x180010cd7  mov     [rsp+158h+var_18], rax
0x180010cdf  lea     rax, [rsp+158h+hKey]
0x180010ce4  mov     [rsp+158h+hKey], 0
0x180010ced  mov     r9d, 0F003Fh; samDesired
0x180010cf3  mov     [rsp+158h+phkResult], rax; phkResult
0x180010cf8  xor     r8d, r8d; ulOptions
0x180010cfb  mov     rdi, rdx
0x180010cfe  mov     rbx, rcx
0x180010d01  call    cs:__imp_RegOpenKeyExA
0x180010d07  test    eax, eax
0x180010d09  jnz     short loc_180010D72
0x180010d0b  mov     rcx, [rsp+158h+hKey]; hKey
0x180010d10  lea     r8, [rsp+158h+Name]; lpName
0x180010d15  mov     r9d, 100h; cchName
0x180010d1b  xor     edx, edx; dwIndex
0x180010d1d  call    cs:__imp_RegEnumKeyA
0x180010d23  test    eax, eax
0x180010d25  jnz     short loc_180010D5B
0x180010d27  nop     word ptr [rax+rax+00000000h]
0x180010d30  mov     rcx, [rsp+158h+hKey]
0x180010d35  lea     rdx, [rsp+158h+Name]
0x180010d3a  call    RegRemoveSubtree
0x180010d3f  mov     rcx, [rsp+158h+hKey]; hKey
0x180010d44  lea     r8, [rsp+158h+Name]; lpName
0x180010d49  mov     r9d, 100h; cchName
0x180010d4f  xor     edx, edx; dwIndex
0x180010d51  call    cs:__imp_RegEnumKeyA
0x180010d57  test    eax, eax
0x180010d59  jz      short loc_180010D30
0x180010d5b  mov     rcx, [rsp+158h+hKey]; hKey
0x180010d60  call    cs:__imp_RegCloseKey
0x180010d66  mov     rdx, rdi; lpSubKey
0x180010d69  mov     rcx, rbx; hKey
0x180010d6c  call    cs:__imp_RegDeleteKeyA
0x180010d72  mov     rcx, [rsp+158h+var_18]
0x180010d7a  xor     rcx, rsp; StackCookie
0x180010d7d  call    __security_check_cookie
0x180010d82  mov     rbx, [rsp+158h+arg_10]
0x180010d8a  add     rsp, 150h
0x180010d91  pop     rdi
0x180010d92  retn
```
