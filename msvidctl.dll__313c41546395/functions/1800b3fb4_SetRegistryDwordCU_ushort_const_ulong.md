# SetRegistryDwordCU(ushort const *,ulong)

- ea: `0x1800b3fb4`
- end: `0x1800b405a`
- name: `?SetRegistryDwordCU@@YAHPEBGK@Z`
- size: `166`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b41c0`
- `0x1800b4210`
- `0x1800b4260`

## callees

- `0x1800b3fb4`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800b400b`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b400b`
- `ADVAPI32!RegSetValueExW` at `0x1800b4035`
- `ADVAPI32!RegSetValueExW` at `0x1800b4035`
- `ADVAPI32!RegCloseKey` at `0x1800b4042`
- `ADVAPI32!RegCloseKey` at `0x1800b4042`

## pseudocode

```c
_BOOL8 __fastcall SetRegistryDwordCU(LPCWSTR lpValueName, int a2)
{
  LSTATUS v3; // ebx
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = a2;
  hKey = 0;
  v3 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\DVD", 0, 0, 0, 2u, 0, &hKey, 0);
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
0x1800b3fb4  mov     r11, rsp
0x1800b3fb7  mov     [r11+8], rbx
0x1800b3fbb  mov     [rsp+Data], edx
0x1800b3fbf  push    rdi
0x1800b3fc0  sub     rsp, 50h
0x1800b3fc4  mov     qword ptr [r11-18h], 0
0x1800b3fcc  lea     rax, [r11+18h]
0x1800b3fd0  mov     [r11-20h], rax
0x1800b3fd4  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b3fdb  mov     qword ptr [r11-28h], 0
0x1800b3fe3  mov     rdi, rcx
0x1800b3fe6  mov     [rsp+58h+samDesired], 2; samDesired
0x1800b3fee  xor     r9d, r9d; lpClass
0x1800b3ff1  xor     r8d, r8d; Reserved
0x1800b3ff4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800b3ffc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b4003  mov     qword ptr [r11+18h], 0
0x1800b400b  call    cs:__imp_RegCreateKeyExW
0x1800b4011  mov     ebx, eax
0x1800b4013  test    eax, eax
0x1800b4015  jnz     short loc_1800B4048
0x1800b4017  mov     rcx, [rsp+58h+hKey]; hKey
0x1800b401c  lea     r9d, [rax+4]; dwType
0x1800b4020  lea     rax, [rsp+58h+Data]
0x1800b4025  mov     [rsp+58h+samDesired], r9d; cbData
0x1800b402a  xor     r8d, r8d; Reserved
0x1800b402d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800b4032  mov     rdx, rdi; lpValueName
0x1800b4035  call    cs:__imp_RegSetValueExW
0x1800b403b  mov     rcx, [rsp+58h+hKey]; hKey
0x1800b4040  mov     ebx, eax
0x1800b4042  call    cs:__imp_RegCloseKey
0x1800b4048  xor     eax, eax
0x1800b404a  test    ebx, ebx
0x1800b404c  mov     rbx, [rsp+58h+arg_0]
0x1800b4051  setz    al
0x1800b4054  add     rsp, 50h
0x1800b4058  pop     rdi
0x1800b4059  retn
```
