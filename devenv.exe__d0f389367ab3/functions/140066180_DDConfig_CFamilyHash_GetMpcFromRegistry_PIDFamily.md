# DDConfig::CFamilyHash::GetMpcFromRegistry(PIDFamily)

- ea: `0x140066180`
- end: `0x140066290`
- name: `?GetMpcFromRegistry@CFamilyHash@DDConfig@@SAHW4PIDFamily@@@Z`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140066134`
- `0x140066e70`

## callees

- `0x140001020`
- `0x140066180`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140066262`
- `ADVAPI32!RegCloseKey` at `0x140066262`
- `ADVAPI32!RegOpenKeyExW` at `0x1400661d7`
- `ADVAPI32!RegOpenKeyExW` at `0x1400661d7`
- `ADVAPI32!RegQueryValueExW` at `0x140066207`
- `ADVAPI32!RegQueryValueExW` at `0x14006623f`
- `ADVAPI32!RegQueryValueExW` at `0x140066207`
- `ADVAPI32!RegQueryValueExW` at `0x14006623f`

## pseudocode

```c
__int64 __fastcall DDConfig::CFamilyHash::GetMpcFromRegistry(unsigned int a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+30h] [rbp-69h] BYREF
  DWORD Type; // [rsp+38h] [rbp-61h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-5Dh] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-59h] BYREF

  v1 = (int)a1;
  if ( a1 > 0x26 )
    return 0xFFFFFFFFLL;
  _mm_lfence();
  v2 = -1;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Licenses\\1299B4B9-DFCC-476D-98F0-F65A2B46C96D", 0, 0x20219u, &hKey) )
  {
    Type = 0;
    cbData = 0;
    if ( !RegQueryValueExW(hKey, 0, 0, &Type, 0, &cbData)
      && Type == 3
      && cbData == 156
      && !RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData)
      && Type == 3 )
    {
      v2 = (4 * v1 + 62903) ^ (v1 + *(_DWORD *)&Data[4 * v1]);
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x140066180  mov     [rsp-8+arg_0], rbx
0x140066185  mov     [rsp-8+arg_8], rdi
0x14006618a  push    rbp
0x14006618b  lea     rbp, [rsp-57h]
0x140066190  sub     rsp, 0F0h
0x140066197  mov     rax, cs:__security_cookie
0x14006619e  xor     rax, rsp
0x1400661a1  mov     [rbp+57h+var_10], rax
0x1400661a5  movsxd  rdi, ecx
0x1400661a8  cmp     edi, 26h ; '&'
0x1400661ab  ja      loc_14006626C
0x1400661b1  lfence
0x1400661b4  lea     rax, [rbp+57h+hKey]
0x1400661b8  mov     r9d, 20219h; samDesired
0x1400661be  xor     r8d, r8d; ulOptions
0x1400661c1  mov     [rsp+0F0h+phkResult], rax; lpData
0x1400661c6  lea     rdx, ?REGKEYNAME_RegistrationMatrix@DDConfig@@3QBGB; "Licenses\\1299B4B9-DFCC-476D-98F0-F65A2"...
0x1400661cd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1400661d4  or      ebx, 0FFFFFFFFh
0x1400661d7  call    cs:__imp_RegOpenKeyExW
0x1400661dd  test    eax, eax
0x1400661df  jnz     loc_140066268
0x1400661e5  and     [rbp+57h+Type], eax
0x1400661e8  lea     r9, [rbp+57h+Type]; lpType
0x1400661ec  and     [rbp+57h+cbData], eax
0x1400661ef  xor     r8d, r8d; lpReserved
0x1400661f2  mov     rcx, [rbp+57h+hKey]; hKey
0x1400661f6  lea     rax, [rbp+57h+cbData]
0x1400661fa  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x1400661ff  xor     edx, edx; lpValueName
0x140066201  and     [rsp+0F0h+phkResult], 0
0x140066207  call    cs:__imp_RegQueryValueExW
0x14006620d  test    eax, eax
0x14006620f  jnz     short loc_14006625E
0x140066211  cmp     [rbp+57h+Type], 3
0x140066215  jnz     short loc_14006625E
0x140066217  cmp     [rbp+57h+cbData], 9Ch
0x14006621e  jnz     short loc_14006625E
0x140066220  mov     rcx, [rbp+57h+hKey]; hKey
0x140066224  lea     rax, [rbp+57h+cbData]
0x140066228  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14006622d  lea     r9, [rbp+57h+Type]; lpType
0x140066231  lea     rax, [rbp+57h+Data]
0x140066235  xor     r8d, r8d; lpReserved
0x140066238  xor     edx, edx; lpValueName
0x14006623a  mov     [rsp+0F0h+phkResult], rax; lpData
0x14006623f  call    cs:__imp_RegQueryValueExW
0x140066245  test    eax, eax
0x140066247  jnz     short loc_14006625E
0x140066249  cmp     [rbp+57h+Type], 3
0x14006624d  jnz     short loc_14006625E
0x14006624f  mov     ebx, dword ptr [rbp+rdi*4+57h+Data]
0x140066253  lea     ecx, ds:0F5B7h[rdi*4]
0x14006625a  add     ebx, edi
0x14006625c  xor     ebx, ecx
0x14006625e  mov     rcx, [rbp+57h+hKey]; hKey
0x140066262  call    cs:__imp_RegCloseKey
0x140066268  mov     eax, ebx
0x14006626a  jmp     short loc_14006626F
0x14006626c  or      eax, 0FFFFFFFFh
0x14006626f  mov     rcx, [rbp+57h+var_10]
0x140066273  xor     rcx, rsp; StackCookie
0x140066276  call    __security_check_cookie
0x14006627b  lea     r11, [rsp+0F0h+var_s0]
0x140066283  mov     rbx, [r11+10h]
0x140066287  mov     rdi, [r11+18h]
0x14006628b  mov     rsp, r11
0x14006628e  pop     rbp
0x14006628f  retn
```
