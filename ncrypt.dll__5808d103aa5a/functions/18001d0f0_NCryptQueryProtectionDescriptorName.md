# NCryptQueryProtectionDescriptorName

- ea: `0x18001d0f0`
- end: `0x18001d276`
- name: `NCryptQueryProtectionDescriptorName`
- size: `390`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015490`

## callees

- `0x18000e120`
- `0x1800198c4`
- `0x18001d0f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d1f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d1f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d1a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d1a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d25b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d25b`

## string_xrefs

- `0x18001d23e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`
- `0x18001d197`: `Software\Microsoft\Cryptography\NProtect\NamedDescriptors`

## pseudocode

```c
__int64 __fastcall NCryptQueryProtectionDescriptorName(LPCWSTR lpValueName, LPBYTE lpData, unsigned __int64 *a3)
{
  __int64 v6; // r9
  unsigned __int64 v7; // r14
  DWORD v8; // r8d
  int v9; // r11d
  unsigned int v10; // ebx
  __int64 v11; // rcx
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  unsigned __int64 v14; // rcx
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !a3 )
  {
    v6 = 618;
LABEL_22:
    v10 = -2146893785;
    v11 = 2148073511LL;
    goto LABEL_23;
  }
  v7 = *a3;
  *a3 = 0;
  if ( !lpValueName || !*lpValueName || StringCchLengthW(lpValueName, (size_t)lpData, 0) < 0 )
  {
    v6 = 631;
    goto LABEL_22;
  }
  if ( (v9 & 0xFFFFFFDF) != 0 )
  {
    v10 = -2146893815;
    v6 = 638;
    v11 = 2148073481LL;
LABEL_23:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c", v6);
    goto LABEL_24;
  }
  v12 = RegOpenKeyExW(
          (HKEY)(((v9 & 0x20) != 0) - 0x7FFFFFFFLL),
          L"Software\\Microsoft\\Cryptography\\NProtect\\NamedDescriptors",
          v8,
          0x20019u,
          &hKey);
  v10 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    v6 = 661;
LABEL_12:
    v11 = v10;
    goto LABEL_23;
  }
  cbData = 2 * v7;
  v13 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
  v10 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    v6 = 678;
    goto LABEL_12;
  }
  v14 = (unsigned __int64)cbData >> 1;
  *a3 = v14;
  if ( lpData && v14 )
    *(_WORD *)&lpData[2 * v14 - 2] = 0;
  v10 = 0;
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18001d0f0  mov     rax, rsp
0x18001d0f3  mov     [rax+8], rbx
0x18001d0f7  mov     [rax+10h], rbp
0x18001d0fb  push    rsi
0x18001d0fc  push    rdi
0x18001d0fd  push    r14
0x18001d0ff  sub     rsp, 40h
0x18001d103  mov     qword ptr [rax-20h], 0
0x18001d10b  mov     r11d, r9d
0x18001d10e  mov     dword ptr [rax-28h], 0
0x18001d115  mov     rdi, r8
0x18001d118  mov     dword ptr [rax+18h], 0
0x18001d11f  mov     rbp, rdx
0x18001d122  mov     rsi, rcx
0x18001d125  test    r8, r8
0x18001d128  jnz     short loc_18001D135
0x18001d12a  mov     r9d, 26Ah
0x18001d130  jmp     loc_18001D234
0x18001d135  mov     r14, [r8]
0x18001d138  mov     qword ptr [r8], 0
0x18001d13f  test    rsi, rsi
0x18001d142  jz      loc_18001D22E
0x18001d148  xor     eax, eax
0x18001d14a  cmp     ax, [rcx]
0x18001d14d  jz      loc_18001D22E
0x18001d153  xor     r8d, r8d; pcchLength
0x18001d156  call    StringCchLengthW
0x18001d15b  test    eax, eax
0x18001d15d  js      loc_18001D22E
0x18001d163  test    r11d, 0FFFFFFDFh
0x18001d16a  jz      short loc_18001D181
0x18001d16c  mov     ebx, 80090009h
0x18001d171  mov     r9d, 27Eh
0x18001d177  mov     ecx, 80090009h
0x18001d17c  jmp     loc_18001D23E
0x18001d181  xor     ecx, ecx
0x18001d183  lea     rax, [rsp+58h+hKey]
0x18001d188  test    r11b, 20h
0x18001d18c  mov     [rsp+58h+phkResult], rax; phkResult
0x18001d191  mov     r9d, 20019h; samDesired
0x18001d197  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Cryptography\\NPro"...
0x18001d19e  setnz   cl
0x18001d1a1  add     rcx, 0FFFFFFFF80000001h; hKey
0x18001d1a8  call    cs:__imp_RegOpenKeyExW
0x18001d1ae  mov     ebx, eax
0x18001d1b0  test    eax, eax
0x18001d1b2  jz      short loc_18001D1C9
0x18001d1b4  jle     short loc_18001D1BF
0x18001d1b6  movzx   ebx, ax
0x18001d1b9  or      ebx, 80070000h
0x18001d1bf  mov     r9d, 295h
0x18001d1c5  mov     ecx, ebx
0x18001d1c7  jmp     short loc_18001D23E
0x18001d1c9  mov     rcx, [rsp+58h+hKey]; hKey
0x18001d1ce  lea     eax, [r14+r14]
0x18001d1d2  mov     [rsp+58h+cbData], eax
0x18001d1d6  lea     r9, [rsp+58h+Type]; lpType
0x18001d1db  lea     rax, [rsp+58h+cbData]
0x18001d1e0  xor     r8d, r8d; lpReserved
0x18001d1e3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001d1e8  mov     rdx, rsi; lpValueName
0x18001d1eb  mov     [rsp+58h+phkResult], rbp; lpData
0x18001d1f0  call    cs:__imp_RegQueryValueExW
0x18001d1f6  mov     ebx, eax
0x18001d1f8  test    eax, eax
0x18001d1fa  jz      short loc_18001D20F
0x18001d1fc  jle     short loc_18001D207
0x18001d1fe  movzx   ebx, ax
0x18001d201  or      ebx, 80070000h
0x18001d207  mov     r9d, 2A6h
0x18001d20d  jmp     short loc_18001D1C5
0x18001d20f  mov     ecx, [rsp+58h+cbData]
0x18001d213  shr     rcx, 1
0x18001d216  mov     [rdi], rcx
0x18001d219  test    rbp, rbp
0x18001d21c  jz      short loc_18001D22A
0x18001d21e  test    rcx, rcx
0x18001d221  jz      short loc_18001D22A
0x18001d223  xor     eax, eax
0x18001d225  mov     [rbp+rcx*2-2], ax
0x18001d22a  xor     ebx, ebx
0x18001d22c  jmp     short loc_18001D251
0x18001d22e  mov     r9d, 277h
0x18001d234  mov     ebx, 80090027h
0x18001d239  mov     ecx, 80090027h
0x18001d23e  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d245  lea     rdx, aStatus; "Status"
0x18001d24c  call    DebugTraceError
0x18001d251  mov     rcx, [rsp+58h+hKey]; hKey
0x18001d256  test    rcx, rcx
0x18001d259  jz      short loc_18001D261
0x18001d25b  call    cs:__imp_RegCloseKey
0x18001d261  mov     rbp, [rsp+58h+arg_8]
0x18001d266  mov     eax, ebx
0x18001d268  mov     rbx, [rsp+58h+arg_0]
0x18001d26d  add     rsp, 40h
0x18001d271  pop     r14
0x18001d273  pop     rdi
0x18001d274  pop     rsi
0x18001d275  retn
```
