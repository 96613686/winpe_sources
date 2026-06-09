# UnicodeEnabled(void)

- ea: `0x180021d5c`
- end: `0x180021e27`
- name: `?UnicodeEnabled@@YA_NXZ`
- size: `203`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021e30`

## callees

- `0x180021d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021e0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021e0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021de2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021de2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021da7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021da7`

## pseudocode

```c
char UnicodeEnabled(void)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( !byte_1800C4E0C )
  {
    if ( !byte_1800C4E0E )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
      {
        Type = 0;
        Data = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"Unicode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 && Data )
        {
          byte_1800C4E0E = 1;
          byte_1800C4E0D = 0;
        }
        RegCloseKey(hKey);
      }
    }
    byte_1800C4E0C = 1;
  }
  return byte_1800C4E0E;
}

```

## disassembly

```asm
0x180021d5c  push    rbp
0x180021d5e  mov     rbp, rsp
0x180021d61  sub     rsp, 30h
0x180021d65  cmp     cs:byte_1800C4E0C, 0
0x180021d6c  jnz     loc_180021E1B
0x180021d72  cmp     cs:byte_1800C4E0E, 0
0x180021d79  jnz     loc_180021E14
0x180021d7f  lea     rax, [rbp+hKey]
0x180021d83  mov     [rbp+hKey], 0
0x180021d8b  mov     r9d, 20019h; samDesired
0x180021d91  mov     [rsp+30h+phkResult], rax; phkResult
0x180021d96  xor     r8d, r8d; ulOptions
0x180021d99  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\Auto"...
0x180021da0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021da7  call    cs:__imp_RegOpenKeyExW
0x180021dad  test    eax, eax
0x180021daf  jnz     short loc_180021E14
0x180021db1  mov     rcx, [rbp+hKey]; hKey
0x180021db5  lea     r9, [rbp+Type]; lpType
0x180021db9  mov     [rbp+Type], eax
0x180021dbc  lea     rdx, aUnicode; "Unicode"
0x180021dc3  mov     [rbp+Data], eax
0x180021dc6  xor     r8d, r8d; lpReserved
0x180021dc9  lea     rax, [rbp+cbData]
0x180021dcd  mov     [rbp+cbData], 4
0x180021dd4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180021dd9  lea     rax, [rbp+Data]
0x180021ddd  mov     [rsp+30h+phkResult], rax; lpData
0x180021de2  call    cs:__imp_RegQueryValueExW
0x180021de8  test    eax, eax
0x180021dea  jnz     short loc_180021E0A
0x180021dec  cmp     [rbp+Type], 4
0x180021df0  jnz     short loc_180021E0A
0x180021df2  cmp     [rbp+cbData], 4
0x180021df6  jnz     short loc_180021E0A
0x180021df8  cmp     [rbp+Data], eax
0x180021dfb  jz      short loc_180021E0A
0x180021dfd  mov     cs:byte_1800C4E0E, 1
0x180021e04  mov     cs:byte_1800C4E0D, al
0x180021e0a  mov     rcx, [rbp+hKey]; hKey
0x180021e0e  call    cs:__imp_RegCloseKey
0x180021e14  mov     cs:byte_1800C4E0C, 1
0x180021e1b  mov     al, cs:byte_1800C4E0E
0x180021e21  add     rsp, 30h
0x180021e25  pop     rbp
0x180021e26  retn
```
