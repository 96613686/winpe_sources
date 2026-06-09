# ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)

- ea: `0x180085dec`
- end: `0x180085e61`
- name: `?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z`
- size: `117`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800202f8`

## callees

- `0x180085dec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085e46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085e46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085e1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085e1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085e53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085e53`

## pseudocode

```c
LSTATUS __fastcall ReadRegKeyValue32W(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int *lpcbData)
{
  LSTATUS result; // eax
  LSTATUS Value; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, &hKey);
  if ( !result )
  {
    Value = RegQueryValueExW(hKey, L"LastInstance", 0, 0, a4, lpcbData);
    RegCloseKey(hKey);
    return Value;
  }
  return result;
}

```

## disassembly

```asm
0x180085dec  mov     r11, rsp
0x180085def  mov     [r11+18h], r8
0x180085df3  push    rbx
0x180085df4  sub     rsp, 30h
0x180085df8  mov     rbx, r9
0x180085dfb  mov     qword ptr [r11+18h], 0
0x180085e03  lea     rax, [r11+18h]
0x180085e07  mov     r9d, 20119h; samDesired
0x180085e0d  xor     r8d, r8d; ulOptions
0x180085e10  mov     [r11-18h], rax
0x180085e14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085e1b  call    cs:__imp_RegOpenKeyExW
0x180085e21  test    eax, eax
0x180085e23  jnz     short loc_180085E5B
0x180085e25  mov     rax, [rsp+38h+arg_20]
0x180085e2a  lea     rdx, aLastinstance; "LastInstance"
0x180085e31  mov     rcx, [rsp+38h+hKey]; hKey
0x180085e36  xor     r9d, r9d; lpType
0x180085e39  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180085e3e  xor     r8d, r8d; lpReserved
0x180085e41  mov     [rsp+38h+lpData], rbx; lpData
0x180085e46  call    cs:__imp_RegQueryValueExW
0x180085e4c  mov     rcx, [rsp+38h+hKey]; hKey
0x180085e51  mov     ebx, eax
0x180085e53  call    cs:__imp_RegCloseKey
0x180085e59  mov     eax, ebx
0x180085e5b  add     rsp, 30h
0x180085e5f  pop     rbx
0x180085e60  retn
```
