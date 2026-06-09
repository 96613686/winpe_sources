# RassrvRegGetBinary

- ea: `0x180021674`
- end: `0x18002171a`
- name: `RassrvRegGetBinary`
- size: `166`
- prototype: `__int64 __usercall@<rax>(LPBYTE lpData@<rcx>, DWORD Type)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180028afc`

## callees

- `0x180021674`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021707`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021707`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800216c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800216c8`
- `KERNEL32!RegQueryValueExW` at `0x1800216f7`
- `KERNEL32!RegQueryValueExW` at `0x1800216f7`

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
0x180021674  mov     [rsp+arg_10], rbx
0x180021679  mov     [rsp+cbData], edx
0x18002167d  push    rdi
0x18002167e  sub     rsp, 30h
0x180021682  mov     [rsp+38h+Type], 3
0x18002168a  mov     rax, r8
0x18002168d  mov     [rsp+38h+cbData], 10h
0x180021695  mov     rdi, rcx
0x180021698  mov     [rsp+38h+hKey], 0
0x1800216a1  test    rcx, rcx
0x1800216a4  jnz     short loc_1800216AB
0x1800216a6  lea     eax, [rcx+57h]
0x1800216a9  jmp     short loc_18002170F
0x1800216ab  lea     rcx, [rsp+38h+hKey]
0x1800216b0  mov     r9d, 20019h; samDesired
0x1800216b6  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800216bb  xor     r8d, r8d; ulOptions
0x1800216be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800216c5  mov     rdx, rax; lpSubKey
0x1800216c8  call    cs:__imp_RegOpenKeyExW
0x1800216ce  mov     ebx, eax
0x1800216d0  test    eax, eax
0x1800216d2  jnz     short loc_1800216FD
0x1800216d4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800216d9  lea     rax, [rsp+38h+cbData]
0x1800216de  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800216e3  lea     r9, [rsp+38h+Type]; lpType
0x1800216e8  xor     r8d, r8d; lpReserved
0x1800216eb  mov     [rsp+38h+phkResult], rdi; lpData
0x1800216f0  lea     rdx, ValueName; "From"
0x1800216f7  call    cs:__imp_RegQueryValueExW
0x1800216fd  mov     rcx, [rsp+38h+hKey]; hKey
0x180021702  test    rcx, rcx
0x180021705  jz      short loc_18002170D
0x180021707  call    cs:__imp_RegCloseKey
0x18002170d  mov     eax, ebx
0x18002170f  mov     rbx, [rsp+38h+arg_10]
0x180021714  add     rsp, 30h
0x180021718  pop     rdi
0x180021719  retn
```
