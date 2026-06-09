# SetRegDbVersionInRegistryInternal(__int64)

- ea: `0x180018844`
- end: `0x1800188d0`
- name: `?SetRegDbVersionInRegistryInternal@@YAJ_J@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e890`

## callees

- `0x180018844`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018877`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018877`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800188a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800188a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800188b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800188b5`

## string_xrefs

- `0x180018869`: `Software\Microsoft\COM3`

## pseudocode

```c
__int64 __fastcall SetRegDbVersionInRegistryInternal(__int64 a1)
{
  LSTATUS v1; // ebx
  __int64 Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3", 0, 0x20106u, &hKey);
  if ( !v1 )
  {
    v1 = RegSetValueExW(hKey, L"REGDBVersion", 0, 3u, (const BYTE *)&Data, 8u);
    RegCloseKey(hKey);
  }
  if ( v1 > 0 )
    return (unsigned __int16)v1 | 0x80070000;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180018844  mov     r11, rsp
0x180018847  mov     [r11+8], rcx
0x18001884b  push    rbx
0x18001884c  sub     rsp, 30h
0x180018850  lea     rax, [r11+10h]
0x180018854  mov     qword ptr [r11+10h], 0
0x18001885c  mov     r9d, 20106h; samDesired
0x180018862  mov     [r11-18h], rax
0x180018866  xor     r8d, r8d; ulOptions
0x180018869  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\COM3"
0x180018870  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018877  call    cs:__imp_RegOpenKeyExW
0x18001887d  mov     ebx, eax
0x18001887f  test    eax, eax
0x180018881  jnz     short loc_1800188BB
0x180018883  mov     rcx, [rsp+38h+hKey]; hKey
0x180018888  lea     rax, [rsp+38h+Data]
0x18001888d  mov     [rsp+38h+cbData], 8; cbData
0x180018895  lea     r9d, [rbx+3]; dwType
0x180018899  xor     r8d, r8d; Reserved
0x18001889c  mov     [rsp+38h+lpData], rax; lpData
0x1800188a1  lea     rdx, aRegdbversion; "REGDBVersion"
0x1800188a8  call    cs:__imp_RegSetValueExW
0x1800188ae  mov     rcx, [rsp+38h+hKey]; hKey
0x1800188b3  mov     ebx, eax
0x1800188b5  call    cs:__imp_RegCloseKey
0x1800188bb  test    ebx, ebx
0x1800188bd  jle     short loc_1800188C8
0x1800188bf  movzx   ebx, bx
0x1800188c2  or      ebx, 80070000h
0x1800188c8  mov     eax, ebx
0x1800188ca  add     rsp, 30h
0x1800188ce  pop     rbx
0x1800188cf  retn
```
