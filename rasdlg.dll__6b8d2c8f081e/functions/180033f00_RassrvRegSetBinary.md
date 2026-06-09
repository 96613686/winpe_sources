# RassrvRegSetBinary

- ea: `0x180033f00`
- end: `0x180033fb2`
- name: `RassrvRegSetBinary`
- size: `178`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180036d34`

## callees

- `0x180033f00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033f5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033f98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033f86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033f86`

## pseudocode

```c
__int64 __fastcall RassrvRegSetBinary(BYTE *lpData, __int64 a2, const WCHAR *a3, const WCHAR *a4)
{
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  DWORD v9; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v9 = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x20006u, 0, &hKey, &v9);
  if ( !v6 )
    v6 = RegSetValueExW(hKey, a4, 0, 3u, lpData, 0x10u);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180033f00  mov     rax, rsp
0x180033f03  mov     [rax+8], rbx
0x180033f07  mov     [rax+18h], rsi
0x180033f0b  mov     [rax+10h], edx
0x180033f0e  push    rdi
0x180033f0f  sub     rsp, 60h
0x180033f13  mov     rsi, rcx
0x180033f16  mov     qword ptr [rax-18h], 0
0x180033f1e  lea     rcx, [rax+10h]
0x180033f22  mov     dword ptr [rax+10h], 0
0x180033f29  mov     [rax-28h], rcx
0x180033f2d  mov     rdi, r9
0x180033f30  lea     rcx, [rax-18h]
0x180033f34  mov     rdx, r8; lpSubKey
0x180033f37  mov     [rax-30h], rcx
0x180033f3b  xor     r9d, r9d; lpClass
0x180033f3e  mov     qword ptr [rax-38h], 0
0x180033f46  xor     r8d, r8d; Reserved
0x180033f49  mov     dword ptr [rax-40h], 20006h
0x180033f50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033f57  mov     dword ptr [rax-48h], 0
0x180033f5e  call    cs:__imp_RegCreateKeyExW
0x180033f64  mov     ebx, eax
0x180033f66  test    eax, eax
0x180033f68  jnz     short loc_180033F8E
0x180033f6a  mov     rcx, [rsp+68h+hKey]; hKey
0x180033f6f  lea     r9d, [rax+3]; dwType
0x180033f73  mov     [rsp+68h+cbData], 10h; cbData
0x180033f7b  xor     r8d, r8d; Reserved
0x180033f7e  mov     rdx, rdi; lpValueName
0x180033f81  mov     [rsp+68h+lpData], rsi; lpData
0x180033f86  call    cs:__imp_RegSetValueExW
0x180033f8c  mov     ebx, eax
0x180033f8e  mov     rcx, [rsp+68h+hKey]; hKey
0x180033f93  test    rcx, rcx
0x180033f96  jz      short loc_180033F9E
0x180033f98  call    cs:__imp_RegCloseKey
0x180033f9e  lea     r11, [rsp+68h+var_8]
0x180033fa3  mov     eax, ebx
0x180033fa5  mov     rbx, [r11+10h]
0x180033fa9  mov     rsi, [r11+20h]
0x180033fad  mov     rsp, r11
0x180033fb0  pop     rdi
0x180033fb1  retn
```
