# RassrvRegGetBinary

- ea: `0x180033c90`
- end: `0x180033d36`
- name: `RassrvRegGetBinary`
- size: `166`
- prototype: `__int64 __usercall@<rax>(LPBYTE lpData@<rcx>, DWORD Type)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180036be0`

## callees

- `0x180033c90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033ce4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033ce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033d13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033d13`

## pseudocode

```c
__int64 __fastcall RassrvRegGetBinary(LPBYTE lpData, __int64 a2, const WCHAR *a3, __int64 a4, DWORD Type)
{
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF

  Type = 3;
  cbData = 16;
  hKey = 0;
  if ( !lpData )
    return 87;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
  if ( !v7 )
    RegQueryValueExW(hKey, L"From", 0, &Type, lpData, &cbData);
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180033c90  mov     [rsp+arg_10], rbx
0x180033c95  mov     [rsp+cbData], edx
0x180033c99  push    rdi
0x180033c9a  sub     rsp, 30h
0x180033c9e  mov     [rsp+38h+Type], 3
0x180033ca6  mov     rax, r8
0x180033ca9  mov     [rsp+38h+cbData], 10h
0x180033cb1  mov     rdi, rcx
0x180033cb4  mov     [rsp+38h+hKey], 0
0x180033cbd  test    rcx, rcx
0x180033cc0  jnz     short loc_180033CC7
0x180033cc2  lea     eax, [rcx+57h]
0x180033cc5  jmp     short loc_180033D2B
0x180033cc7  lea     rcx, [rsp+38h+hKey]
0x180033ccc  mov     r9d, 20019h; samDesired
0x180033cd2  mov     [rsp+38h+phkResult], rcx; phkResult
0x180033cd7  xor     r8d, r8d; ulOptions
0x180033cda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033ce1  mov     rdx, rax; lpSubKey
0x180033ce4  call    cs:__imp_RegOpenKeyExW
0x180033cea  mov     ebx, eax
0x180033cec  test    eax, eax
0x180033cee  jnz     short loc_180033D19
0x180033cf0  mov     rcx, [rsp+38h+hKey]; hKey
0x180033cf5  lea     rax, [rsp+38h+cbData]
0x180033cfa  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180033cff  lea     r9, [rsp+38h+Type]; lpType
0x180033d04  xor     r8d, r8d; lpReserved
0x180033d07  mov     [rsp+38h+phkResult], rdi; lpData
0x180033d0c  lea     rdx, ValueName; "From"
0x180033d13  call    cs:__imp_RegQueryValueExW
0x180033d19  mov     rcx, [rsp+38h+hKey]; hKey
0x180033d1e  test    rcx, rcx
0x180033d21  jz      short loc_180033D29
0x180033d23  call    cs:__imp_RegCloseKey
0x180033d29  mov     eax, ebx
0x180033d2b  mov     rbx, [rsp+38h+arg_10]
0x180033d30  add     rsp, 30h
0x180033d34  pop     rdi
0x180033d35  retn
```
