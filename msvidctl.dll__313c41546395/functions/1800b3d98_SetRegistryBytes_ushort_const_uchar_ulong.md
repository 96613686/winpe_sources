# SetRegistryBytes(ushort const *,uchar *,ulong)

- ea: `0x1800b3d98`
- end: `0x1800b3e43`
- name: `?SetRegistryBytes@@YAHPEBGPEAEK@Z`
- size: `171`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3110`
- `0x1800b436c`

## callees

- `0x1800b3d98`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1800b3e00`
- `ADVAPI32!RegDeleteValueW` at `0x1800b3e00`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b3de6`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b3de6`
- `ADVAPI32!RegSetValueExW` at `0x1800b3e1f`
- `ADVAPI32!RegSetValueExW` at `0x1800b3e1f`
- `ADVAPI32!RegCloseKey` at `0x1800b3e32`
- `ADVAPI32!RegCloseKey` at `0x1800b3e32`

## pseudocode

```c
__int64 __fastcall SetRegistryBytes(LPCWSTR lpValueName, BYTE *lpData, DWORD cbData)
{
  unsigned int v3; // ebx
  bool v7; // zf
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multimedia\\DVD", 0, 0, 0, 2u, 0, &hKey, 0) )
  {
    if ( lpData )
      v7 = RegSetValueExW(hKey, lpValueName, 0, 3u, lpData, cbData) == 0;
    else
      v7 = (RegDeleteValueW(hKey, lpValueName) & 0xFFFFFFFD) == 0;
    LOBYTE(v3) = v7;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x1800b3d98  mov     r11, rsp
0x1800b3d9b  push    rbx
0x1800b3d9c  push    rbp
0x1800b3d9d  push    rsi
0x1800b3d9e  push    rdi
0x1800b3d9f  sub     rsp, 58h
0x1800b3da3  xor     ebx, ebx
0x1800b3da5  mov     qword ptr [r11+20h], 0
0x1800b3dad  mov     [r11-38h], rbx
0x1800b3db1  lea     rax, [r11+20h]
0x1800b3db5  mov     [r11-40h], rax
0x1800b3db9  mov     ebp, r8d
0x1800b3dbc  mov     [r11-48h], rbx
0x1800b3dc0  mov     rdi, rdx
0x1800b3dc3  mov     rsi, rcx
0x1800b3dc6  mov     [rsp+78h+samDesired], 2; samDesired
0x1800b3dce  xor     r9d, r9d; lpClass
0x1800b3dd1  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x1800b3dd5  xor     r8d, r8d; Reserved
0x1800b3dd8  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b3ddf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b3de6  call    cs:__imp_RegCreateKeyExW
0x1800b3dec  test    eax, eax
0x1800b3dee  jnz     short loc_1800B3E38
0x1800b3df0  mov     rcx, [rsp+78h+hKey]; hKey
0x1800b3df8  mov     rdx, rsi; lpValueName
0x1800b3dfb  test    rdi, rdi
0x1800b3dfe  jnz     short loc_1800B3E0D
0x1800b3e00  call    cs:__imp_RegDeleteValueW
0x1800b3e06  test    eax, 0FFFFFFFDh
0x1800b3e0b  jmp     short loc_1800B3E27
0x1800b3e0d  mov     [rsp+78h+samDesired], ebp; cbData
0x1800b3e11  mov     r9d, 3; dwType
0x1800b3e17  xor     r8d, r8d; Reserved
0x1800b3e1a  mov     qword ptr [rsp+78h+dwOptions], rdi; lpData
0x1800b3e1f  call    cs:__imp_RegSetValueExW
0x1800b3e25  test    eax, eax
0x1800b3e27  mov     rcx, [rsp+78h+hKey]; hKey
0x1800b3e2f  setz    bl
0x1800b3e32  call    cs:__imp_RegCloseKey
0x1800b3e38  mov     eax, ebx
0x1800b3e3a  add     rsp, 58h
0x1800b3e3e  pop     rdi
0x1800b3e3f  pop     rsi
0x1800b3e40  pop     rbp
0x1800b3e41  pop     rbx
0x1800b3e42  retn
```
