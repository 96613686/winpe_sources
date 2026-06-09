# GetRegistryBytesCU(ushort const *,uchar *,ulong *)

- ea: `0x1800b384c`
- end: `0x1800b38e9`
- name: `?GetRegistryBytesCU@@YAHPEBGPEAEPEAK@Z`
- size: `157`
- prototype: `int(const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b436c`

## callees

- `0x1800b384c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800b38bb`
- `ADVAPI32!RegQueryValueExW` at `0x1800b38bb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b388d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b388d`
- `ADVAPI32!RegCloseKey` at `0x1800b38cc`
- `ADVAPI32!RegCloseKey` at `0x1800b38cc`

## pseudocode

```c
_BOOL8 __fastcall GetRegistryBytesCU(const unsigned __int16 *a1, unsigned __int8 *a2, unsigned int *a3)
{
  LSTATUS v5; // edi
  const unsigned __int16 *Type; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Type = a1;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\DVD", 0, 1u, &hKey);
  if ( !v5 )
  {
    LODWORD(Type) = 0;
    if ( RegQueryValueExW(hKey, L"DVD.bookmark", 0, (LPDWORD)&Type, a2, a3) )
      *a3 = 0;
    RegCloseKey(hKey);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x1800b384c  mov     r11, rsp
0x1800b384f  mov     [r11+10h], rbx
0x1800b3853  mov     [r11+18h], rsi
0x1800b3857  mov     [r11+8], rcx
0x1800b385b  push    rdi
0x1800b385c  sub     rsp, 30h
0x1800b3860  mov     rbx, r8
0x1800b3863  mov     qword ptr [r11+20h], 0
0x1800b386b  mov     rsi, rdx
0x1800b386e  lea     rax, [r11+20h]
0x1800b3872  xor     r8d, r8d; ulOptions
0x1800b3875  mov     [r11-18h], rax
0x1800b3879  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b3880  mov     r9d, 1; samDesired
0x1800b3886  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b388d  call    cs:__imp_RegOpenKeyExW
0x1800b3893  mov     edi, eax
0x1800b3895  test    eax, eax
0x1800b3897  jnz     short loc_1800B38D2
0x1800b3899  mov     rcx, [rsp+38h+hKey]; hKey
0x1800b389e  lea     r9, [rsp+38h+Type]; lpType
0x1800b38a3  mov     [rsp+38h+lpcbData], rbx; lpcbData
0x1800b38a8  lea     rdx, ValueName; "DVD.bookmark"
0x1800b38af  xor     r8d, r8d; lpReserved
0x1800b38b2  mov     [rsp+38h+lpData], rsi; lpData
0x1800b38b7  mov     dword ptr [rsp+38h+Type], eax
0x1800b38bb  call    cs:__imp_RegQueryValueExW
0x1800b38c1  test    eax, eax
0x1800b38c3  jz      short loc_1800B38C7
0x1800b38c5  mov     [rbx], edi
0x1800b38c7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800b38cc  call    cs:__imp_RegCloseKey
0x1800b38d2  mov     rbx, [rsp+38h+arg_8]
0x1800b38d7  xor     eax, eax
0x1800b38d9  mov     rsi, [rsp+38h+arg_10]
0x1800b38de  test    edi, edi
0x1800b38e0  setz    al
0x1800b38e3  add     rsp, 30h
0x1800b38e7  pop     rdi
0x1800b38e8  retn
```
