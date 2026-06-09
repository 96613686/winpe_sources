# areg_WriteEntryToRegistry

- ea: `0x1800312e4`
- end: `0x1800317d7`
- name: `areg_WriteEntryToRegistry`
- size: `1267`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180037cfc`
- `0x18004ab34`

## callees

- `0x18002979c`
- `0x1800312e4`
- `0x18003fc1c`
- `0x180046ec0`
- `0x18004af6c`
- `0x18007b0bc`
- `0x180086384`
- `0x1800868b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800317b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800317b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031477`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800314e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031548`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003163c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031663`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003168f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031722`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031477`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800314e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031548`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003163c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031663`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003168f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800316fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031722`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800317a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800317a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031400`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031400`

## string_xrefs

- `0x180031314`: `Inside function areg_WriteEntryToRegistry`
- `0x1800316c8`: `CompartmentId`
- `0x180031651`: `SentPriUpdateToIp`
- `0x180031626`: `SentUpdateToIp`

## pseudocode

```c
LSTATUS __fastcall areg_WriteEntryToRegistry(__int64 a1)
{
  const wchar_t *v2; // rax
  int v3; // eax
  LSTATUS v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  const WCHAR *v7; // r9
  int v8; // edx
  const BYTE *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  const BYTE *v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  const BYTE *v15; // rcx
  DWORD v16; // eax
  const BYTE *v17; // rcx
  DWORD v18; // eax
  HKEY v19; // rcx
  int v20; // edx
  LSTATUS result; // eax
  DWORD cbData; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp+7h] BYREF
  BYTE v25[4]; // [rsp+64h] [rbp+Bh] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp+Fh] BYREF
  BYTE v27[4]; // [rsp+6Ch] [rbp+13h] BYREF

  hKey = 0;
  dwDisposition = 0;
  *(_DWORD *)v25 = 0;
  *(_DWORD *)v27 = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  areg_LogEntry("Inside function areg_WriteEntryToRegistry", a1);
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
  {
    if ( a1 )
      v2 = *(const wchar_t **)(a1 + 24);
    else
      v2 = L"NULL";
    WPP_SF_qS(1047, 70, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, a1, (__int64)v2);
  }
  if ( *(_DWORD *)(a1 + 260) )
    goto LABEL_59;
  v3 = *(_DWORD *)Data;
  if ( *(_DWORD *)(a1 + 268) )
  {
    v3 = *(_DWORD *)Data | 1;
    *(_DWORD *)Data |= 1u;
  }
  if ( *(_DWORD *)(a1 + 264) )
  {
    v3 |= 2u;
    *(_DWORD *)Data = v3;
  }
  if ( *(_DWORD *)(a1 + 276) )
  {
    v3 |= 4u;
    *(_DWORD *)Data = v3;
  }
  if ( *(_DWORD *)(a1 + 280) )
  {
    v3 |= 8u;
    *(_DWORD *)Data = v3;
  }
  if ( v3 )
    *(_DWORD *)v25 = 1;
  v4 = RegCreateKeyExW(
         g_hAregRegKey,
         *(LPCWSTR *)(a1 + 24),
         0,
         (LPWSTR)L"AdapterNameClass",
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_59;
    v7 = *(const WCHAR **)(a1 + 24);
    v8 = 71;
    goto LABEL_20;
  }
  v9 = *(const BYTE **)(a1 + 32);
  if ( !v9 )
    goto LABEL_59;
  if ( (unsigned int)Dns_CheckedStringLengthBytes(*(_QWORD *)(a1 + 32), v5, v6, &cbData) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_59;
    v20 = 72;
    goto LABEL_58;
  }
  v4 = RegSetValueExW(hKey, L"Hostname", 0, 1u, v9, cbData);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v8 = 73;
      v7 = L"Hostname";
LABEL_20:
      WPP_SF_SD(1035, v8, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (_DWORD)v7, v4);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  v9 = (const BYTE *)&WideCharStr;
  v12 = (const BYTE *)&WideCharStr;
  if ( *(_QWORD *)(a1 + 48) )
    v12 = *(const BYTE **)(a1 + 48);
  if ( (unsigned int)Dns_CheckedStringLengthBytes(v12, v10, v11, &cbData) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_DS(1035, 74, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, 123, (__int64)v12);
    goto LABEL_59;
  }
  v4 = RegSetValueExW(hKey, L"AdapterDomainName", 0, 1u, v12, cbData);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v8 = 75;
      v7 = L"AdapterDomainName";
      goto LABEL_20;
    }
LABEL_59:
    result = RegDeleteKeyExW(g_hAregRegKey, *(LPCWSTR *)(a1 + 24), 0, 0);
    v19 = hKey;
    if ( !hKey )
      return result;
    return RegCloseKey(v19);
  }
  if ( *(_QWORD *)(a1 + 40) )
    v9 = *(const BYTE **)(a1 + 40);
  if ( (unsigned int)Dns_CheckedStringLengthBytes(v9, v13, v14, &cbData) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_59;
    v20 = 76;
LABEL_58:
    WPP_SF_DS(1035, v20, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, 123, (__int64)v9);
    goto LABEL_59;
  }
  v4 = RegSetValueExW(hKey, L"PrimaryDomainName", 0, 1u, v9, cbData);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v8 = 77;
      v7 = L"PrimaryDomainName";
      goto LABEL_20;
    }
    goto LABEL_59;
  }
  v15 = *(const BYTE **)(a1 + 88);
  v16 = 0;
  if ( v15 )
    v16 = DnsAddrArray_Sizeof();
  v4 = RegSetValueExW(hKey, L"HostAddrs", 0, 3u, v15, v16);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v8 = 78;
      v7 = L"HostAddrs";
      goto LABEL_20;
    }
    goto LABEL_59;
  }
  v17 = *(const BYTE **)(a1 + 96);
  v18 = 0;
  if ( v17 )
    v18 = DnsAddrArray_Sizeof();
  v4 = RegSetValueExW(hKey, L"DnsServers", 0, 3u, v17, v18);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v8 = 79;
      v7 = L"DnsServers";
      goto LABEL_20;
    }
    goto LABEL_59;
  }
  RegSetValueExW(hKey, L"SentUpdateToIp", 0, 3u, (const BYTE *)(a1 + 104), 0x40u);
  RegSetValueExW(hKey, L"SentPriUpdateToIp", 0, 3u, (const BYTE *)(a1 + 168), 0x40u);
  RegSetValueExW(hKey, L"Ttl", 0, 4u, (const BYTE *)(a1 + 236), 4u);
  RegSetValueExW(hKey, L"Flags", 0, 4u, Data, 4u);
  RegSetValueExW(hKey, L"CompartmentId", 0, 4u, (const BYTE *)(a1 + 232), 4u);
  RegSetValueExW(hKey, L"StaleAdapter", 0, 4u, v27, 4u);
  v4 = RegSetValueExW(hKey, L"RegisteredSinceBoot", 0, 4u, v25, 4u);
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v8 = 80;
      v7 = L"RegisteredSinceBoot";
      goto LABEL_20;
    }
    goto LABEL_59;
  }
  v19 = hKey;
  return RegCloseKey(v19);
}

```

## disassembly

```asm
0x1800312e4  push    rbp
0x1800312e6  push    rbx
0x1800312e7  push    rsi
0x1800312e8  push    rdi
0x1800312e9  push    r12
0x1800312eb  push    r14
0x1800312ed  lea     rbp, [rsp-2Fh]
0x1800312f2  sub     rsp, 88h
0x1800312f9  mov     rax, cs:__security_cookie
0x180031300  xor     rax, rsp
0x180031303  mov     [rbp+57h+var_40], rax
0x180031307  xor     r14d, r14d
0x18003130a  mov     rbx, rcx
0x18003130d  mov     rdx, rcx
0x180031310  mov     [rbp+57h+hKey], r14
0x180031314  lea     rcx, aInsideFunction; "Inside function areg_WriteEntryToRegist"...
0x18003131b  mov     [rbp+57h+dwDisposition], r14d
0x18003131f  mov     dword ptr [rbp+57h+var_4C], r14d
0x180031323  mov     dword ptr [rbp+57h+var_44], r14d
0x180031327  mov     dword ptr [rbp+57h+Data], r14d
0x18003132b  mov     [rbp+57h+cbData], r14d
0x18003132f  call    areg_LogEntry
0x180031334  cmp     byte ptr cs:xmmword_1800AB5A0+2, r14b
0x18003133b  lea     r12, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180031342  jge     short loc_180031370
0x180031344  test    rbx, rbx
0x180031347  jz      short loc_18003134F
0x180031349  mov     rax, [rbx+18h]
0x18003134d  jmp     short loc_180031356
0x18003134f  lea     rax, aNull_0; "NULL"
0x180031356  mov     edx, 46h ; 'F'
0x18003135b  mov     qword ptr [rsp+0B0h+dwOptions], rax
0x180031360  mov     ecx, 417h
0x180031365  mov     r9, rbx
0x180031368  mov     r8, r12
0x18003136b  call    WPP_SF_qS
0x180031370  cmp     [rbx+104h], r14d
0x180031377  jnz     loc_180031795
0x18003137d  mov     eax, dword ptr [rbp+57h+Data]
0x180031380  cmp     [rbx+10Ch], r14d
0x180031387  jz      short loc_18003138F
0x180031389  or      eax, 1
0x18003138c  mov     dword ptr [rbp+57h+Data], eax
0x18003138f  cmp     [rbx+108h], r14d
0x180031396  jz      short loc_18003139E
0x180031398  or      eax, 2
0x18003139b  mov     dword ptr [rbp+57h+Data], eax
0x18003139e  cmp     [rbx+114h], r14d
0x1800313a5  jz      short loc_1800313AD
0x1800313a7  or      eax, 4
0x1800313aa  mov     dword ptr [rbp+57h+Data], eax
0x1800313ad  cmp     [rbx+118h], r14d
0x1800313b4  jz      short loc_1800313BC
0x1800313b6  or      eax, 8
0x1800313b9  mov     dword ptr [rbp+57h+Data], eax
0x1800313bc  test    eax, eax
0x1800313be  jz      short loc_1800313C7
0x1800313c0  mov     dword ptr [rbp+57h+var_4C], 1
0x1800313c7  mov     rdx, [rbx+18h]; lpSubKey
0x1800313cb  lea     rax, [rbp+57h+dwDisposition]
0x1800313cf  mov     rcx, cs:g_hAregRegKey; hKey
0x1800313d6  lea     r9, aAdapternamecla; "AdapterNameClass"
0x1800313dd  mov     [rsp+0B0h+lpdwDisposition], rax; lpdwDisposition
0x1800313e2  xor     r8d, r8d; Reserved
0x1800313e5  lea     rax, [rbp+57h+hKey]
0x1800313e9  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800313ee  mov     [rsp+0B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800313f3  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x1800313fb  mov     [rsp+0B0h+dwOptions], r14d; dwOptions
0x180031400  call    cs:__imp_RegCreateKeyExW
0x180031406  test    eax, eax
0x180031408  jz      short loc_180031436
0x18003140a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031411  jz      loc_180031795
0x180031417  mov     r9, [rbx+18h]
0x18003141b  mov     edx, 47h ; 'G'
0x180031420  mov     ecx, 40Bh
0x180031425  mov     [rsp+0B0h+dwOptions], eax
0x180031429  mov     r8, r12
0x18003142c  call    WPP_SF_SD
0x180031431  jmp     loc_180031795
0x180031436  mov     rdi, [rbx+20h]
0x18003143a  test    rdi, rdi
0x18003143d  jz      loc_180031795
0x180031443  lea     r9, [rbp+57h+cbData]
0x180031447  mov     rcx, rdi
0x18003144a  call    Dns_CheckedStringLengthBytes
0x18003144f  test    eax, eax
0x180031451  jnz     loc_18003176F
0x180031457  mov     eax, [rbp+57h+cbData]
0x18003145a  lea     rdx, aHostname; "Hostname"
0x180031461  mov     rcx, [rbp+57h+hKey]; hKey
0x180031465  mov     r9d, 1; dwType
0x18003146b  mov     [rsp+0B0h+samDesired], eax; cbData
0x18003146f  xor     r8d, r8d; Reserved
0x180031472  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x180031477  call    cs:__imp_RegSetValueExW
0x18003147d  test    eax, eax
0x18003147f  jz      short loc_18003149C
0x180031481  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031488  jz      loc_180031795
0x18003148e  mov     edx, 49h ; 'I'
0x180031493  lea     r9, aHostname; "Hostname"
0x18003149a  jmp     short loc_180031420
0x18003149c  cmp     [rbx+30h], r14
0x1800314a0  lea     rdi, WideCharStr
0x1800314a7  mov     rsi, rdi
0x1800314aa  lea     r9, [rbp+57h+cbData]
0x1800314ae  cmovnz  rsi, [rbx+30h]
0x1800314b3  mov     rcx, rsi
0x1800314b6  call    Dns_CheckedStringLengthBytes
0x1800314bb  test    eax, eax
0x1800314bd  jnz     loc_18003175A
0x1800314c3  mov     eax, [rbp+57h+cbData]
0x1800314c6  lea     rdx, aAdapterdomainn; "AdapterDomainName"
0x1800314cd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800314d1  mov     r9d, 1; dwType
0x1800314d7  mov     [rsp+0B0h+samDesired], eax; cbData
0x1800314db  xor     r8d, r8d; Reserved
0x1800314de  mov     qword ptr [rsp+0B0h+dwOptions], rsi; lpData
0x1800314e3  call    cs:__imp_RegSetValueExW
0x1800314e9  test    eax, eax
0x1800314eb  jz      short loc_18003150B
0x1800314ed  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800314f4  jz      loc_180031795
0x1800314fa  mov     edx, 4Bh ; 'K'
0x1800314ff  lea     r9, aAdapterdomainn; "AdapterDomainName"
0x180031506  jmp     loc_180031420
0x18003150b  cmp     [rbx+28h], r14
0x18003150f  lea     r9, [rbp+57h+cbData]
0x180031513  cmovnz  rdi, [rbx+28h]
0x180031518  mov     rcx, rdi
0x18003151b  call    Dns_CheckedStringLengthBytes
0x180031520  test    eax, eax
0x180031522  jnz     loc_18003174A
0x180031528  mov     eax, [rbp+57h+cbData]
0x18003152b  lea     rdx, aPrimarydomainn; "PrimaryDomainName"
0x180031532  mov     rcx, [rbp+57h+hKey]; hKey
0x180031536  mov     r9d, 1; dwType
0x18003153c  mov     [rsp+0B0h+samDesired], eax; cbData
0x180031540  xor     r8d, r8d; Reserved
0x180031543  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x180031548  call    cs:__imp_RegSetValueExW
0x18003154e  test    eax, eax
0x180031550  jz      short loc_180031570
0x180031552  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031559  jz      loc_180031795
0x18003155f  mov     edx, 4Dh ; 'M'
0x180031564  lea     r9, aPrimarydomainn; "PrimaryDomainName"
0x18003156b  jmp     loc_180031420
0x180031570  mov     rcx, [rbx+58h]
0x180031574  mov     eax, r14d
0x180031577  test    rcx, rcx
0x18003157a  jz      short loc_180031581
0x18003157c  call    DnsAddrArray_Sizeof
0x180031581  mov     [rsp+0B0h+samDesired], eax; cbData
0x180031585  lea     rdx, aHostaddrs; "HostAddrs"
0x18003158c  mov     qword ptr [rsp+0B0h+dwOptions], rcx; lpData
0x180031591  mov     esi, 3
0x180031596  mov     rcx, [rbp+57h+hKey]; hKey
0x18003159a  mov     r9d, esi; dwType
0x18003159d  xor     r8d, r8d; Reserved
0x1800315a0  call    cs:__imp_RegSetValueExW
0x1800315a6  test    eax, eax
0x1800315a8  jz      short loc_1800315C6
0x1800315aa  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800315b1  jz      loc_180031795
0x1800315b7  lea     edx, [rsi+4Bh]
0x1800315ba  lea     r9, aHostaddrs; "HostAddrs"
0x1800315c1  jmp     loc_180031420
0x1800315c6  mov     rcx, [rbx+60h]
0x1800315ca  mov     eax, r14d
0x1800315cd  test    rcx, rcx
0x1800315d0  jz      short loc_1800315D7
0x1800315d2  call    DnsAddrArray_Sizeof
0x1800315d7  mov     [rsp+0B0h+samDesired], eax; cbData
0x1800315db  lea     rdx, aDnsservers; "DnsServers"
0x1800315e2  mov     qword ptr [rsp+0B0h+dwOptions], rcx; lpData
0x1800315e7  mov     r9d, esi; dwType
0x1800315ea  mov     rcx, [rbp+57h+hKey]; hKey
0x1800315ee  xor     r8d, r8d; Reserved
0x1800315f1  call    cs:__imp_RegSetValueExW
0x1800315f7  test    eax, eax
0x1800315f9  jz      short loc_180031619
0x1800315fb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031602  jz      loc_180031795
0x180031608  mov     edx, 4Fh ; 'O'
0x18003160d  lea     r9, aDnsservers; "DnsServers"
0x180031614  jmp     loc_180031420
0x180031619  mov     rcx, [rbp+57h+hKey]; hKey
0x18003161d  lea     rax, [rbx+68h]
0x180031621  mov     edi, 40h ; '@'
0x180031626  lea     rdx, aSentupdatetoip; "SentUpdateToIp"
0x18003162d  mov     [rsp+0B0h+samDesired], edi; cbData
0x180031631  mov     r9d, esi; dwType
0x180031634  xor     r8d, r8d; Reserved
0x180031637  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x18003163c  call    cs:__imp_RegSetValueExW
0x180031642  mov     rcx, [rbp+57h+hKey]; hKey
0x180031646  lea     rax, [rbx+0A8h]
0x18003164d  mov     [rsp+0B0h+samDesired], edi; cbData
0x180031651  lea     rdx, aSentpriupdatet; "SentPriUpdateToIp"
0x180031658  mov     r9d, esi; dwType
0x18003165b  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x180031660  xor     r8d, r8d; Reserved
0x180031663  call    cs:__imp_RegSetValueExW
0x180031669  mov     rcx, [rbp+57h+hKey]; hKey
0x18003166d  lea     rax, [rbx+0ECh]
0x180031674  mov     edi, 4
0x180031679  lea     rdx, aTtl; "Ttl"
0x180031680  mov     [rsp+0B0h+samDesired], edi; cbData
0x180031684  mov     r9d, edi; dwType
0x180031687  xor     r8d, r8d; Reserved
0x18003168a  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x18003168f  call    cs:__imp_RegSetValueExW
0x180031695  mov     rcx, [rbp+57h+hKey]; hKey
0x180031699  lea     rax, [rbp+57h+Data]
0x18003169d  mov     [rsp+0B0h+samDesired], edi; cbData
0x1800316a1  lea     rdx, aFlags; "Flags"
0x1800316a8  mov     r9d, edi; dwType
0x1800316ab  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x1800316b0  xor     r8d, r8d; Reserved
0x1800316b3  call    cs:__imp_RegSetValueExW
0x1800316b9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800316bd  lea     rax, [rbx+0E8h]
0x1800316c4  mov     [rsp+0B0h+samDesired], edi; cbData
0x1800316c8  lea     rdx, aCompartmentid; "CompartmentId"
0x1800316cf  mov     r9d, edi; dwType
0x1800316d2  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x1800316d7  xor     r8d, r8d; Reserved
0x1800316da  call    cs:__imp_RegSetValueExW
0x1800316e0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800316e4  lea     rax, [rbp+57h+var_44]
0x1800316e8  mov     [rsp+0B0h+samDesired], edi; cbData
0x1800316ec  lea     rdx, aStaleadapter; "StaleAdapter"
0x1800316f3  mov     r9d, edi; dwType
0x1800316f6  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x1800316fb  xor     r8d, r8d; Reserved
0x1800316fe  call    cs:__imp_RegSetValueExW
0x180031704  mov     rcx, [rbp+57h+hKey]; hKey
0x180031708  lea     rax, [rbp+57h+var_4C]
0x18003170c  mov     [rsp+0B0h+samDesired], edi; cbData
0x180031710  lea     rdx, aRegisteredsinc; "RegisteredSinceBoot"
0x180031717  mov     r9d, edi; dwType
0x18003171a  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x18003171f  xor     r8d, r8d; Reserved
0x180031722  call    cs:__imp_RegSetValueExW
0x180031728  test    eax, eax
0x18003172a  jz      short loc_180031744
0x18003172c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031733  jz      short loc_180031795
0x180031735  lea     edx, [rdi+4Ch]
0x180031738  lea     r9, aRegisteredsinc; "RegisteredSinceBoot"
0x18003173f  jmp     loc_180031420
0x180031744  mov     rcx, [rbp+57h+hKey]
0x180031748  jmp     short loc_1800317B5
0x18003174a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031751  jz      short loc_180031795
0x180031753  mov     edx, 4Ch ; 'L'
0x180031758  jmp     short loc_18003177D
0x18003175a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031761  jz      short loc_180031795
0x180031763  mov     edx, 4Ah ; 'J'
0x180031768  mov     qword ptr [rsp+0B0h+dwOptions], rsi
0x18003176d  jmp     short loc_180031782
0x18003176f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180031776  jz      short loc_180031795
0x180031778  mov     edx, 48h ; 'H'
0x18003177d  mov     qword ptr [rsp+0B0h+dwOptions], rdi
0x180031782  mov     r9d, 7Bh ; '{'
0x180031788  mov     r8, r12
0x18003178b  mov     ecx, 40Bh
0x180031790  call    WPP_SF_DS
0x180031795  mov     rdx, [rbx+18h]; lpSubKey
0x180031799  xor     r9d, r9d; Reserved
0x18003179c  mov     rcx, cs:g_hAregRegKey; hKey
0x1800317a3  xor     r8d, r8d; samDesired
0x1800317a6  call    cs:__imp_RegDeleteKeyExW
0x1800317ac  mov     rcx, [rbp+57h+hKey]; hKey
0x1800317b0  test    rcx, rcx
0x1800317b3  jz      short loc_1800317BB
0x1800317b5  call    cs:__imp_RegCloseKey
0x1800317bb  mov     rcx, [rbp+57h+var_40]
0x1800317bf  xor     rcx, rsp; StackCookie
0x1800317c2  call    __security_check_cookie
0x1800317c7  add     rsp, 88h
0x1800317ce  pop     r14
0x1800317d0  pop     r12
0x1800317d2  pop     rdi
0x1800317d3  pop     rsi
0x1800317d4  pop     rbx
0x1800317d5  pop     rbp
0x1800317d6  retn
```
