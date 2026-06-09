# SetRegistryDword(ushort const *,ulong)

- ea: `0x1800b3f08`
- end: `0x1800b3fae`
- name: `?SetRegistryDword@@YAHPEBGK@Z`
- size: `166`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3110`
- `0x1800b3bd0`
- `0x1800b3d00`
- `0x1800b4190`
- `0x1800b42b0`

## callees

- `0x1800b3f08`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800b3f5f`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b3f5f`
- `ADVAPI32!RegSetValueExW` at `0x1800b3f89`
- `ADVAPI32!RegSetValueExW` at `0x1800b3f89`
- `ADVAPI32!RegCloseKey` at `0x1800b3f96`
- `ADVAPI32!RegCloseKey` at `0x1800b3f96`

## pseudocode

```c
_BOOL8 __fastcall SetRegistryDword(LPCWSTR lpValueName, int a2)
{
  LSTATUS v3; // ebx
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = a2;
  hKey = 0;
  v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multimedia\\DVD", 0, 0, 0, 2u, 0, &hKey, 0);
  if ( !v3 )
  {
    v3 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  return v3 == 0;
}

```

## disassembly

```asm
0x1800b3f08  mov     r11, rsp
0x1800b3f0b  mov     [r11+8], rbx
0x1800b3f0f  mov     [rsp+Data], edx
0x1800b3f13  push    rdi
0x1800b3f14  sub     rsp, 50h
0x1800b3f18  mov     qword ptr [r11-18h], 0
0x1800b3f20  lea     rax, [r11+18h]
0x1800b3f24  mov     [r11-20h], rax
0x1800b3f28  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b3f2f  mov     qword ptr [r11-28h], 0
0x1800b3f37  mov     rdi, rcx
0x1800b3f3a  mov     [rsp+58h+samDesired], 2; samDesired
0x1800b3f42  xor     r9d, r9d; lpClass
0x1800b3f45  xor     r8d, r8d; Reserved
0x1800b3f48  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800b3f50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b3f57  mov     qword ptr [r11+18h], 0
0x1800b3f5f  call    cs:__imp_RegCreateKeyExW
0x1800b3f65  mov     ebx, eax
0x1800b3f67  test    eax, eax
0x1800b3f69  jnz     short loc_1800B3F9C
0x1800b3f6b  mov     rcx, [rsp+58h+hKey]; hKey
0x1800b3f70  lea     r9d, [rax+4]; dwType
0x1800b3f74  lea     rax, [rsp+58h+Data]
0x1800b3f79  mov     [rsp+58h+samDesired], r9d; cbData
0x1800b3f7e  xor     r8d, r8d; Reserved
0x1800b3f81  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800b3f86  mov     rdx, rdi; lpValueName
0x1800b3f89  call    cs:__imp_RegSetValueExW
0x1800b3f8f  mov     rcx, [rsp+58h+hKey]; hKey
0x1800b3f94  mov     ebx, eax
0x1800b3f96  call    cs:__imp_RegCloseKey
0x1800b3f9c  xor     eax, eax
0x1800b3f9e  test    ebx, ebx
0x1800b3fa0  mov     rbx, [rsp+58h+arg_0]
0x1800b3fa5  setz    al
0x1800b3fa8  add     rsp, 50h
0x1800b3fac  pop     rdi
0x1800b3fad  retn
```
