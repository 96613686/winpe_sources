# myRetrieveLogLevel

- ea: `0x180007110`
- end: `0x1800071c8`
- name: `myRetrieveLogLevel`
- size: `184`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027d8`
- `0x1800070b8`

## callees

- `0x180007110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000718b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000718b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007161`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007161`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071b0`

## pseudocode

```c
__int64 __fastcall myRetrieveLogLevel(HKEY a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v4; // ebx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int v9; // [rsp+64h] [rbp+24h]
  int Data; // [rsp+68h] [rbp+28h] BYREF

  v9 = HIDWORD(a3);
  Data = 2;
  cbData = 4;
  Type = 0;
  hKey = 0;
  v4 = 0;
  if ( RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &hKey) )
    goto LABEL_5;
  if ( !RegQueryValueExW(hKey, a2, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
  {
    v4 = 1;
LABEL_5:
    g_dwLoglevel = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180007110  mov     r11, rsp
0x180007113  mov     [r11+8], rbx
0x180007117  mov     [r11+10h], rdi
0x18000711b  mov     [r11+18h], r8
0x18000711f  push    rbp
0x180007120  mov     rbp, rsp
0x180007123  sub     rsp, 40h
0x180007127  mov     rdi, rdx
0x18000712a  mov     [rbp+Data], 2
0x180007131  lea     rax, [rbp+hKey]
0x180007135  mov     [rbp+cbData], 4
0x18000713c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x180007143  mov     [r11-28h], rax
0x180007147  mov     r9d, 20019h; samDesired
0x18000714d  mov     [rbp+Type], 0
0x180007154  xor     r8d, r8d; ulOptions
0x180007157  mov     [rbp+hKey], 0
0x18000715f  xor     ebx, ebx
0x180007161  call    cs:__imp_RegOpenKeyExW
0x180007167  test    eax, eax
0x180007169  jnz     short loc_18000719E
0x18000716b  mov     rcx, [rbp+hKey]; hKey
0x18000716f  lea     rax, [rbp+cbData]
0x180007173  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180007178  lea     r9, [rbp+Type]; lpType
0x18000717c  lea     rax, [rbp+Data]
0x180007180  xor     r8d, r8d; lpReserved
0x180007183  mov     rdx, rdi; lpValueName
0x180007186  mov     [rsp+40h+lpData], rax; lpData
0x18000718b  call    cs:__imp_RegQueryValueExW
0x180007191  test    eax, eax
0x180007193  jnz     short loc_1800071A7
0x180007195  cmp     [rbp+Type], 4
0x180007199  jnz     short loc_1800071A7
0x18000719b  lea     ebx, [rax+1]
0x18000719e  mov     ecx, [rbp+Data]
0x1800071a1  mov     cs:g_dwLoglevel, ecx
0x1800071a7  mov     rcx, [rbp+hKey]; hKey
0x1800071ab  test    rcx, rcx
0x1800071ae  jz      short loc_1800071B6
0x1800071b0  call    cs:__imp_RegCloseKey
0x1800071b6  mov     rdi, [rsp+40h+arg_8]
0x1800071bb  mov     eax, ebx
0x1800071bd  mov     rbx, [rsp+40h+arg_0]
0x1800071c2  add     rsp, 40h
0x1800071c6  pop     rbp
0x1800071c7  retn
```
