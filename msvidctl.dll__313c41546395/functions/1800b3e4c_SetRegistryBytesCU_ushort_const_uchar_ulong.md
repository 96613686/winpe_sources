# SetRegistryBytesCU(ushort const *,uchar *,ulong)

- ea: `0x1800b3e4c`
- end: `0x1800b3f02`
- name: `?SetRegistryBytesCU@@YAHPEBGPEAEK@Z`
- size: `182`
- prototype: `int(const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b4340`
- `0x1800b462c`

## callees

- `0x1800b3e4c`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1800b3ebb`
- `ADVAPI32!RegDeleteValueW` at `0x1800b3ebb`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b3ea0`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b3ea0`
- `ADVAPI32!RegSetValueExW` at `0x1800b3eda`
- `ADVAPI32!RegSetValueExW` at `0x1800b3eda`
- `ADVAPI32!RegCloseKey` at `0x1800b3eea`
- `ADVAPI32!RegCloseKey` at `0x1800b3eea`

## pseudocode

```c
__int64 __fastcall SetRegistryBytesCU(const unsigned __int16 *a1, unsigned __int8 *a2, DWORD a3)
{
  unsigned int v3; // ebx
  bool v6; // zf
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  hKey = 0;
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\DVD", 0, 0, 0, 2u, 0, &hKey, 0) )
  {
    if ( a2 )
      v6 = RegSetValueExW(hKey, L"DVD.bookmark", 0, 3u, a2, a3) == 0;
    else
      v6 = (RegDeleteValueW(hKey, L"DVD.bookmark") & 0xFFFFFFFD) == 0;
    LOBYTE(v3) = v6;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x1800b3e4c  mov     r11, rsp
0x1800b3e4f  mov     [r11+10h], rbx
0x1800b3e53  mov     [r11+18h], rsi
0x1800b3e57  mov     [r11+8], rcx
0x1800b3e5b  push    rdi
0x1800b3e5c  sub     rsp, 50h
0x1800b3e60  xor     ebx, ebx
0x1800b3e62  mov     qword ptr [r11+8], 0
0x1800b3e6a  mov     [r11-18h], rbx
0x1800b3e6e  lea     rax, [r11+8]
0x1800b3e72  mov     [r11-20h], rax
0x1800b3e76  mov     esi, r8d
0x1800b3e79  mov     [r11-28h], rbx
0x1800b3e7d  mov     rdi, rdx
0x1800b3e80  mov     [rsp+58h+samDesired], 2; samDesired
0x1800b3e88  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\DVD"
0x1800b3e8f  xor     r9d, r9d; lpClass
0x1800b3e92  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x1800b3e96  xor     r8d, r8d; Reserved
0x1800b3e99  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b3ea0  call    cs:__imp_RegCreateKeyExW
0x1800b3ea6  test    eax, eax
0x1800b3ea8  jnz     short loc_1800B3EF0
0x1800b3eaa  mov     rcx, [rsp+58h+hKey]; hKey
0x1800b3eaf  lea     rdx, ValueName; "DVD.bookmark"
0x1800b3eb6  test    rdi, rdi
0x1800b3eb9  jnz     short loc_1800B3EC8
0x1800b3ebb  call    cs:__imp_RegDeleteValueW
0x1800b3ec1  test    eax, 0FFFFFFFDh
0x1800b3ec6  jmp     short loc_1800B3EE2
0x1800b3ec8  mov     [rsp+58h+samDesired], esi; cbData
0x1800b3ecc  mov     r9d, 3; dwType
0x1800b3ed2  xor     r8d, r8d; Reserved
0x1800b3ed5  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x1800b3eda  call    cs:__imp_RegSetValueExW
0x1800b3ee0  test    eax, eax
0x1800b3ee2  mov     rcx, [rsp+58h+hKey]; hKey
0x1800b3ee7  setz    bl
0x1800b3eea  call    cs:__imp_RegCloseKey
0x1800b3ef0  mov     rsi, [rsp+58h+arg_10]
0x1800b3ef5  mov     eax, ebx
0x1800b3ef7  mov     rbx, [rsp+58h+arg_8]
0x1800b3efc  add     rsp, 50h
0x1800b3f00  pop     rdi
0x1800b3f01  retn
```
