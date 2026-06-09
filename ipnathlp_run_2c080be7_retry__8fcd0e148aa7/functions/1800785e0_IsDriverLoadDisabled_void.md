# IsDriverLoadDisabled(void)

- ea: `0x1800785e0`
- end: `0x18007872a`
- name: `?IsDriverLoadDisabled@@YAEXZ`
- size: `330`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18004b360`
- `0x18006e900`

## callees

- `0x180051f30`
- `0x1800785e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800786d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800786d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800786a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800786a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800786fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800786fa`

## string_xrefs

- `0x180078605`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
bool IsDriverLoadDisabled(void)
{
  bool v0; // bl
  BYTE Data[4]; // [rsp+30h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-61h] BYREF
  wchar_t ValueName[16]; // [rsp+40h] [rbp-59h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-39h] BYREF

  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  v0 = 0;
  hKey = 0;
  wcscpy(ValueName, L"DileIpNat");
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
  {
    v0 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1800785e0  mov     [rsp-8+arg_0], rbx
0x1800785e5  mov     [rsp-8+arg_8], rsi
0x1800785ea  push    rbp
0x1800785eb  lea     rbp, [rsp-57h]
0x1800785f0  sub     rsp, 0F0h
0x1800785f7  mov     rax, cs:__security_cookie
0x1800785fe  xor     rax, rsp
0x180078601  mov     [rbp+57h+var_10], rax
0x180078605  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18007860c  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180078610  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180078617  mov     esi, 1
0x18007861c  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180078622  mov     r9d, esi; samDesired
0x180078625  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180078629  xor     r8d, r8d; ulOptions
0x18007862c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180078633  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007863a  movaps  [rbp+57h+var_70], xmm0
0x18007863e  xor     bl, bl
0x180078640  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180078647  movaps  [rbp+57h+var_80], xmm1
0x18007864b  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180078652  movaps  [rbp+57h+var_50], xmm0
0x180078656  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18007865d  movaps  [rbp+57h+var_60], xmm1
0x180078661  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180078668  movaps  [rbp+57h+var_30], xmm0
0x18007866c  movups  xmm0, xmmword ptr cs:aDisableipnat; "DisableIpNat"
0x180078673  mov     [rbp+57h+var_20], eax
0x180078676  lea     rax, [rbp+57h+hKey]
0x18007867a  movaps  [rbp+57h+var_40], xmm1
0x18007867e  movups  xmm1, xmmword ptr cs:aDisableipnat+0Ah; "leIpNat"
0x180078685  mov     [rbp+57h+hKey], 0
0x18007868d  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180078691  mov     [rbp+57h+cbData], 4
0x180078698  movups  xmmword ptr [rbp+57h+ValueName+0Ah], xmm1
0x18007869c  mov     dword ptr [rbp+57h+Data], 0
0x1800786a3  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800786a8  call    cs:__imp_RegOpenKeyExW
0x1800786af  nop     dword ptr [rax+rax+00h]
0x1800786b4  test    eax, eax
0x1800786b6  jnz     short loc_1800786F1
0x1800786b8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800786bc  lea     rax, [rbp+57h+cbData]
0x1800786c0  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x1800786c5  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x1800786c9  lea     rax, [rbp+57h+Data]
0x1800786cd  xor     r9d, r9d; lpType
0x1800786d0  xor     r8d, r8d; lpReserved
0x1800786d3  mov     [rsp+0F0h+phkResult], rax; lpData
0x1800786d8  call    cs:__imp_RegQueryValueExW
0x1800786df  nop     dword ptr [rax+rax+00h]
0x1800786e4  test    eax, eax
0x1800786e6  jnz     short loc_1800786F1
0x1800786e8  cmp     dword ptr [rbp+57h+Data], eax
0x1800786eb  movzx   ebx, bl
0x1800786ee  cmovnz  ebx, esi
0x1800786f1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800786f5  test    rcx, rcx
0x1800786f8  jz      short loc_180078706
0x1800786fa  call    cs:__imp_RegCloseKey
0x180078701  nop     dword ptr [rax+rax+00h]
0x180078706  mov     al, bl
0x180078708  mov     rcx, [rbp+57h+var_10]
0x18007870c  xor     rcx, rsp; StackCookie
0x18007870f  call    __security_check_cookie
0x180078714  lea     r11, [rsp+0F0h+var_s0]
0x18007871c  mov     rbx, [r11+10h]
0x180078720  mov     rsi, [r11+18h]
0x180078724  mov     rsp, r11
0x180078727  pop     rbp
0x180078728  retn
```
