# GetPerAdapterRegConfig

- ea: `0x180004124`
- end: `0x1800042b1`
- name: `GetPerAdapterRegConfig`
- size: `397`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, _DWORD *, BYTE *, LPDWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ea0`
- `0x180041a24`

## callees

- `0x180004124`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004186`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004186`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000422d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000422d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800042a4`
- `DNSAPI!DnsQueryConfigDword` at `0x18000419a`
- `DNSAPI!DnsQueryConfigDword` at `0x18000419a`

## pseudocode

```c
__int64 __fastcall GetPerAdapterRegConfig(HKEY hKey, __int64 a2, _DWORD *a3, BYTE *a4, LPDWORD a5)
{
  LPDWORD lpcbData; // rdi
  int v10; // esi
  unsigned int Value; // ebx
  DWORD v13; // r14d
  HKEY hKeya; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+90h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+58h] BYREF

  lpcbData = a5;
  Data = 0;
  hKeya = 0;
  if ( !a4 || (v10 = 1, !a5) )
    v10 = 0;
  cbData = 4;
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows NT\\DnsClient",
            0,
            0x20019u,
            &hKeya);
  if ( Value || (Value = RegQueryValueExW(hKeya, L"RegisterAdapterName", 0, 0, (LPBYTE)&Data, &cbData)) != 0 )
    Data = DnsQueryConfigDword(10, a2);
  if ( Data == 1 && v10 )
  {
    v13 = 0;
    if ( lpcbData )
      v13 = *lpcbData;
    Value = RegQueryValueExW(hKeya, L"AdapterDomainName", 0, 0, a4, lpcbData);
    if ( Value )
    {
      if ( lpcbData )
        *lpcbData = v13;
      Value = RegQueryValueExW(hKey, L"Domain", 0, 0, a4, lpcbData);
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v10 && !Value && !*(_WORD *)a4 )
    Value = 1012;
  *a3 = Data;
  return Value;
}

```

## disassembly

```asm
0x180004124  mov     [rsp-38h+arg_0], rbx
0x180004129  push    rbp
0x18000412a  push    rsi
0x18000412b  push    rdi
0x18000412c  push    r12
0x18000412e  push    r13
0x180004130  push    r14
0x180004132  push    r15
0x180004134  mov     rbp, rsp
0x180004137  sub     rsp, 40h
0x18000413b  mov     rdi, [rbp+arg_20]
0x18000413f  xor     eax, eax
0x180004141  mov     [rbp+Data], eax
0x180004144  mov     r15, r9
0x180004147  mov     [rbp+hKey], rax
0x18000414b  mov     r12, r8
0x18000414e  mov     r14, rdx
0x180004151  mov     r13, rcx
0x180004154  test    r9, r9
0x180004157  jnz     loc_1800041F7
0x18000415d  mov     esi, eax
0x18000415f  lea     rax, [rbp+hKey]
0x180004163  mov     [rbp+cbData], 4
0x18000416a  mov     r9d, 20019h; samDesired
0x180004170  mov     [rsp+40h+phkResult], rax; phkResult
0x180004175  xor     r8d, r8d; ulOptions
0x180004178  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x18000417f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004186  call    cs:__imp_RegOpenKeyExW
0x18000418c  mov     ebx, eax
0x18000418e  test    eax, eax
0x180004190  jz      short loc_18000420A
0x180004192  mov     rdx, r14
0x180004195  mov     ecx, 0Ah
0x18000419a  call    cs:__imp_DnsQueryConfigDword
0x1800041a0  mov     [rbp+Data], eax
0x1800041a3  xor     eax, eax
0x1800041a5  cmp     [rbp+Data], 1
0x1800041a9  jz      loc_180004244
0x1800041af  mov     rcx, [rbp+hKey]; hKey
0x1800041b3  xor     edi, edi
0x1800041b5  test    rcx, rcx
0x1800041b8  jz      short loc_1800041C0
0x1800041ba  call    cs:__imp_RegCloseKey
0x1800041c0  test    esi, esi
0x1800041c2  jnz     short loc_1800041E5
0x1800041c4  mov     eax, [rbp+Data]
0x1800041c7  mov     [r12], eax
0x1800041cb  mov     eax, ebx
0x1800041cd  mov     rbx, [rsp+40h+arg_0]
0x1800041d5  add     rsp, 40h
0x1800041d9  pop     r15
0x1800041db  pop     r14
0x1800041dd  pop     r13
0x1800041df  pop     r12
0x1800041e1  pop     rdi
0x1800041e2  pop     rsi
0x1800041e3  pop     rbp
0x1800041e4  retn
0x1800041e5  test    ebx, ebx
0x1800041e7  jnz     short loc_1800041C4
0x1800041e9  cmp     [r15], di
0x1800041ed  mov     eax, 3F4h
0x1800041f2  cmovz   ebx, eax
0x1800041f5  jmp     short loc_1800041C4
0x1800041f7  mov     esi, 1
0x1800041fc  test    rdi, rdi
0x1800041ff  jnz     loc_18000415F
0x180004205  jmp     loc_18000415D
0x18000420a  mov     rcx, [rbp+hKey]; hKey
0x18000420e  lea     rax, [rbp+cbData]
0x180004212  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180004217  lea     rdx, aRegisteradapte; "RegisterAdapterName"
0x18000421e  lea     rax, [rbp+Data]
0x180004222  xor     r9d, r9d; lpType
0x180004225  xor     r8d, r8d; lpReserved
0x180004228  mov     [rsp+40h+phkResult], rax; lpData
0x18000422d  call    cs:__imp_RegQueryValueExW
0x180004233  mov     ebx, eax
0x180004235  xor     eax, eax
0x180004237  test    ebx, ebx
0x180004239  jz      loc_1800041A5
0x18000423f  jmp     loc_180004192
0x180004244  test    esi, esi
0x180004246  jz      loc_1800041AF
0x18000424c  mov     r14d, eax
0x18000424f  test    rdi, rdi
0x180004252  jz      short loc_180004257
0x180004254  mov     r14d, [rdi]
0x180004257  mov     rcx, [rbp+hKey]; hKey
0x18000425b  lea     rdx, aAdapterdomainn; "AdapterDomainName"
0x180004262  mov     [rsp+40h+lpcbData], rdi; lpcbData
0x180004267  xor     r9d, r9d; lpType
0x18000426a  xor     r8d, r8d; lpReserved
0x18000426d  mov     [rsp+40h+phkResult], r15; lpData
0x180004272  call    cs:__imp_RegQueryValueExW
0x180004278  mov     ebx, eax
0x18000427a  test    eax, eax
0x18000427c  jz      loc_1800041AF
0x180004282  test    rdi, rdi
0x180004285  jz      short loc_18000428A
0x180004287  mov     [rdi], r14d
0x18000428a  mov     [rsp+40h+lpcbData], rdi; lpcbData
0x18000428f  lea     rdx, aDomain; "Domain"
0x180004296  xor     r9d, r9d; lpType
0x180004299  mov     [rsp+40h+phkResult], r15; lpData
0x18000429e  xor     r8d, r8d; lpReserved
0x1800042a1  mov     rcx, r13; hKey
0x1800042a4  call    cs:__imp_RegQueryValueExW
0x1800042aa  mov     ebx, eax
0x1800042ac  jmp     loc_1800041AF
```
