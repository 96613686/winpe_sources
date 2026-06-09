# DnsConnectionManager::ConnectionDeletePolicyEntriesRegistry(DNS_CONNECTION_POLICY_TAG)

- ea: `0x1800ab380`
- end: `0x1800ab821`
- name: `?ConnectionDeletePolicyEntriesRegistry@DnsConnectionManager@@QEAAJW4DNS_CONNECTION_POLICY_TAG@@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(DnsConnectionManager *__hidden this, enum DNS_CONNECTION_POLICY_TAG)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task`

## callers

- `0x1800752c4`

## callees

- `0x1800097e0`
- `0x18003fcb0`
- `0x18005a60c`
- `0x180065520`
- `0x180067dc4`
- `0x180075ec8`
- `0x180078528`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800ab380`
- `0x1800cc528`
- `0x1800d6098`
- `0x1800d6164`
- `0x1800d624c`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ab4a6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ab66a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ab4a6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ab66a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab4c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab69f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab6ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab7d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab7ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab4c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab69f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab6ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab7d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab7ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800ab5f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800ab5f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab56e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab56e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab51c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab51c`

## string_xrefs

- `0x1800ab444`: `Dnscache`
- `0x1800ab43d`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::ConnectionDeletePolicyEntriesRegistry(
        DnsConnectionManager *this,
        enum DNS_CONNECTION_POLICY_TAG a2)
{
  int v4; // r9d
  int PersistedRegistryKeyHelper; // eax
  bool v6; // sf
  unsigned int v7; // ebx
  int v8; // ebx
  int v9; // r12d
  DWORD v10; // edi
  bool v11; // sf
  LSTATUS v12; // eax
  int v13; // edx
  int v14; // r8d
  DWORD v15; // ecx
  enum DNS_CONNECTION_POLICY_TAG v16; // eax
  int v17; // edx
  LSTATUS v18; // esi
  int v19; // r8d
  __int64 v20; // rdi
  ConnectionAppIdPolicyNode *v21; // rcx
  DnsConnectionManager *v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h]
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  phkResult = 0;
  memset_0(Name, 0, 0x20Au);
  cchName = 261;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  v23 = this;
  v24 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 39, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, this, a2);
  AutoSrw::LockExclusive((AutoSrw *)&v23);
  PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                 (unsigned int)L"Dnscache",
                                 (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                 (unsigned int)L"Parameters\\DnsConnections",
                                 v4,
                                 131103);
  v6 = PersistedRegistryKeyHelper < 0;
  if ( PersistedRegistryKeyHelper > 0 )
  {
    PersistedRegistryKeyHelper = (unsigned __int16)PersistedRegistryKeyHelper | 0x80070000;
    v6 = PersistedRegistryKeyHelper < 0;
  }
  if ( v6 )
    goto LABEL_6;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0) )
  {
    while ( 1 )
    {
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
        WPP_SF_DS(1054, 40, (unsigned int)WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, v10, (__int64)Name);
      PersistedRegistryKeyHelper = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      v11 = PersistedRegistryKeyHelper < 0;
      if ( PersistedRegistryKeyHelper > 0 )
      {
        PersistedRegistryKeyHelper = (unsigned __int16)PersistedRegistryKeyHelper | 0x80070000;
        v11 = PersistedRegistryKeyHelper < 0;
      }
      if ( v11 )
        goto LABEL_6;
      Type = 4;
      cbData = 4;
      v12 = RegQueryValueExW(phkResult, L"PolicyTag", 0, &Type, Data, &cbData);
      v15 = Type;
      if ( v12 || Type != 4 )
      {
        if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
          WPP_SF_DDSDS((unsigned int)Name, v13, v14, v12, v10, (__int64)Name, Type);
        v16 = a2;
        *(_DWORD *)Data = a2;
      }
      else
      {
        v16 = *(_DWORD *)Data;
      }
      if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      {
        WPP_SF_DSD(v15, v13, v14, v10, (__int64)Name, v16);
        v16 = *(_DWORD *)Data;
      }
      if ( v16 == a2 || a2 == TAG_DNS_CONNECTION_POLICY_TAG_DEFAULT )
      {
        v18 = RegDeleteKeyExW(hKey, Name, 0, 0);
        if ( v18 )
        {
          if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_DDSD(*(_DWORD *)Data, v17, v19, v18, v10, (__int64)Name, Data[0]);
          ++v10;
          v8 = v18;
        }
        else
        {
          v9 = 1;
        }
      }
      else
      {
        ++v10;
      }
      cchName = 261;
      if ( RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, 0) )
      {
        if ( !v9 )
        {
          if ( v8 <= 0 )
            break;
          PersistedRegistryKeyHelper = (unsigned __int16)v8 | 0x80070000;
          goto LABEL_52;
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        v20 = *((_QWORD *)this + 2);
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_q(1035, 16, WPP_71080afd593b3f642843e61775452ce0_Traceguids, *((_QWORD *)this + 2));
        CWxRefMap<ConnectionPolicyMap,ConnectionAppIdPolicyNode>::DeleteAll(v20);
        v21 = *(ConnectionAppIdPolicyNode **)(v20 + 24);
        if ( v21 )
        {
          ConnectionAppIdPolicyNode::Release(v21);
          *(_QWORD *)(v20 + 24) = 0;
        }
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_(1035, 17, WPP_71080afd593b3f642843e61775452ce0_Traceguids);
        PersistedRegistryKeyHelper = DnsConnectionManager::ReadConnectionPolicyRules(this);
        if ( PersistedRegistryKeyHelper >= 0 )
        {
          if ( v8 > 0 )
            PersistedRegistryKeyHelper = (unsigned __int16)v8 | 0x80070000;
          else
            PersistedRegistryKeyHelper = v8;
          v7 = PersistedRegistryKeyHelper;
          goto LABEL_54;
        }
        goto LABEL_6;
      }
    }
  }
  PersistedRegistryKeyHelper = v8;
LABEL_52:
  if ( PersistedRegistryKeyHelper < 0 )
  {
LABEL_6:
    v7 = PersistedRegistryKeyHelper;
    goto LABEL_54;
  }
  PersistedRegistryKeyHelper = 0;
  v7 = 0;
LABEL_54:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 44, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (unsigned int)PersistedRegistryKeyHelper);
  if ( (_DWORD)v24 )
    AutoSrw::UnlockShared((AutoSrw *)&v23);
  if ( HIDWORD(v24) )
    AutoSrw::UnlockExclusive((AutoSrw *)&v23);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800ab380  push    rbp
0x1800ab382  push    rbx
0x1800ab383  push    rsi
0x1800ab384  push    rdi
0x1800ab385  push    r12
0x1800ab387  push    r13
0x1800ab389  push    r14
0x1800ab38b  push    r15
0x1800ab38d  lea     rbp, [rsp-1A8h]
0x1800ab395  sub     rsp, 2A8h
0x1800ab39c  mov     rax, cs:__security_cookie
0x1800ab3a3  xor     rax, rsp
0x1800ab3a6  mov     [rbp+1E0h+var_50], rax
0x1800ab3ad  xor     r13d, r13d
0x1800ab3b0  mov     r14d, edx
0x1800ab3b3  mov     r15, rcx
0x1800ab3b6  mov     [rsp+2E0h+var_29C], r13d
0x1800ab3bb  xor     edx, edx; Val
0x1800ab3bd  mov     [rsp+2E0h+hKey], r13
0x1800ab3c2  lea     rcx, [rbp+1E0h+Name]; void *
0x1800ab3c6  mov     [rsp+2E0h+phkResult], r13
0x1800ab3cb  mov     r8d, 20Ah; Size
0x1800ab3d1  call    memset_0
0x1800ab3d6  mov     [rsp+2E0h+cchName], 105h
0x1800ab3de  mov     [rsp+2E0h+Type], r13d
0x1800ab3e3  mov     [rsp+2E0h+cbData], r13d
0x1800ab3e8  mov     dword ptr [rsp+2E0h+Data], r13d
0x1800ab3ed  mov     [rsp+2E0h+var_298], r15
0x1800ab3f2  mov     [rsp+2E0h+var_290], r13
0x1800ab3f7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800ab3fe  jz      short loc_1800AB41D
0x1800ab400  lea     edx, [r13+27h]
0x1800ab404  mov     dword ptr [rsp+2E0h+lpReserved], r14d
0x1800ab409  mov     ecx, 40Bh
0x1800ab40e  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ab415  mov     r9, r15
0x1800ab418  call    WPP_SF_qD
0x1800ab41d  lea     rcx, [rsp+2E0h+var_298]; this
0x1800ab422  call    ?LockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::LockExclusive(void)
0x1800ab427  lea     rax, [rsp+2E0h+hKey]
0x1800ab42c  mov     [rsp+2E0h+lpftLastWriteTime], rax
0x1800ab431  lea     r8, aParametersDnsc; "Parameters\\DnsConnections"
0x1800ab438  mov     dword ptr [rsp+2E0h+lpcchClass], r13d
0x1800ab43d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800ab444  lea     rcx, aDnscache_1; "Dnscache"
0x1800ab44b  mov     dword ptr [rsp+2E0h+lpReserved], 2001Fh
0x1800ab453  call    CreatePersistedRegistryKeyHelper
0x1800ab458  mov     esi, 80070000h
0x1800ab45d  test    eax, eax
0x1800ab45f  jle     short loc_1800AB468
0x1800ab461  movzx   eax, ax
0x1800ab464  or      eax, esi
0x1800ab466  test    eax, eax
0x1800ab468  jns     short loc_1800AB479
0x1800ab46a  mov     [rsp+2E0h+var_29C], 31Eh
0x1800ab472  mov     ebx, eax
0x1800ab474  jmp     loc_1800AB786
0x1800ab479  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ab47e  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800ab483  mov     [rsp+2E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800ab488  lea     r8, [rbp+1E0h+Name]; lpName
0x1800ab48c  mov     [rsp+2E0h+lpcchClass], r13; lpcchClass
0x1800ab491  xor     edx, edx; dwIndex
0x1800ab493  mov     [rsp+2E0h+lpClass], r13; lpClass
0x1800ab498  mov     ebx, r13d
0x1800ab49b  mov     [rsp+2E0h+lpReserved], r13; lpReserved
0x1800ab4a0  mov     r12d, r13d
0x1800ab4a3  mov     edi, r13d
0x1800ab4a6  call    cs:__imp_RegEnumKeyExW
0x1800ab4ad  nop     dword ptr [rax+rax+00h]
0x1800ab4b2  test    eax, eax
0x1800ab4b4  jnz     loc_1800AB76D
0x1800ab4ba  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x1800ab4bf  test    rcx, rcx
0x1800ab4c2  jz      short loc_1800AB4D5
0x1800ab4c4  call    cs:__imp_RegCloseKey
0x1800ab4cb  nop     dword ptr [rax+rax+00h]
0x1800ab4d0  mov     [rsp+2E0h+phkResult], r13
0x1800ab4d5  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ab4dc  jz      short loc_1800AB500
0x1800ab4de  lea     rax, [rbp+1E0h+Name]
0x1800ab4e2  mov     edx, 28h ; '('
0x1800ab4e7  mov     ecx, 41Eh
0x1800ab4ec  mov     [rsp+2E0h+lpReserved], rax
0x1800ab4f1  mov     r9d, edi
0x1800ab4f4  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ab4fb  call    WPP_SF_DS
0x1800ab500  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ab505  lea     rax, [rsp+2E0h+phkResult]
0x1800ab50a  mov     r9d, 20019h; samDesired
0x1800ab510  mov     [rsp+2E0h+lpReserved], rax; phkResult
0x1800ab515  xor     r8d, r8d; ulOptions
0x1800ab518  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x1800ab51c  call    cs:__imp_RegOpenKeyExW
0x1800ab523  nop     dword ptr [rax+rax+00h]
0x1800ab528  test    eax, eax
0x1800ab52a  jle     short loc_1800AB533
0x1800ab52c  movzx   eax, ax
0x1800ab52f  or      eax, esi
0x1800ab531  test    eax, eax
0x1800ab533  js      loc_1800AB760
0x1800ab539  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x1800ab53e  lea     r9, [rsp+2E0h+Type]; lpType
0x1800ab543  mov     eax, 4
0x1800ab548  lea     rdx, aPolicytag; "PolicyTag"
0x1800ab54f  mov     [rsp+2E0h+Type], eax
0x1800ab553  xor     r8d, r8d; lpReserved
0x1800ab556  mov     [rsp+2E0h+cbData], eax
0x1800ab55a  lea     rax, [rsp+2E0h+cbData]
0x1800ab55f  mov     [rsp+2E0h+lpClass], rax; lpcbData
0x1800ab564  lea     rax, [rsp+2E0h+Data]
0x1800ab569  mov     [rsp+2E0h+lpReserved], rax; lpData
0x1800ab56e  call    cs:__imp_RegQueryValueExW
0x1800ab575  nop     dword ptr [rax+rax+00h]
0x1800ab57a  mov     ecx, [rsp+2E0h+Type]
0x1800ab57e  test    eax, eax
0x1800ab580  jnz     short loc_1800AB58D
0x1800ab582  cmp     ecx, 4
0x1800ab585  jnz     short loc_1800AB58D
0x1800ab587  mov     eax, dword ptr [rsp+2E0h+Data]
0x1800ab58b  jmp     short loc_1800AB5B6
0x1800ab58d  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ab594  jz      short loc_1800AB5AF
0x1800ab596  mov     dword ptr [rsp+2E0h+lpcchClass], ecx
0x1800ab59a  mov     r9d, eax
0x1800ab59d  lea     rcx, [rbp+1E0h+Name]
0x1800ab5a1  mov     [rsp+2E0h+lpClass], rcx
0x1800ab5a6  mov     dword ptr [rsp+2E0h+lpReserved], edi
0x1800ab5aa  call    WPP_SF_DDSDS
0x1800ab5af  mov     eax, r14d
0x1800ab5b2  mov     dword ptr [rsp+2E0h+Data], eax
0x1800ab5b6  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ab5bd  jz      short loc_1800AB5D8
0x1800ab5bf  mov     dword ptr [rsp+2E0h+lpClass], eax
0x1800ab5c3  mov     r9d, edi
0x1800ab5c6  lea     rax, [rbp+1E0h+Name]
0x1800ab5ca  mov     [rsp+2E0h+lpReserved], rax
0x1800ab5cf  call    WPP_SF_DSD
0x1800ab5d4  mov     eax, dword ptr [rsp+2E0h+Data]
0x1800ab5d8  cmp     eax, r14d
0x1800ab5db  jz      short loc_1800AB5E6
0x1800ab5dd  test    r14d, r14d
0x1800ab5e0  jz      short loc_1800AB5E6
0x1800ab5e2  inc     edi
0x1800ab5e4  jmp     short loc_1800AB63E
0x1800ab5e6  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ab5eb  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x1800ab5ef  xor     r9d, r9d; Reserved
0x1800ab5f2  xor     r8d, r8d; samDesired
0x1800ab5f5  call    cs:__imp_RegDeleteKeyExW
0x1800ab5fc  nop     dword ptr [rax+rax+00h]
0x1800ab601  mov     esi, eax
0x1800ab603  test    eax, eax
0x1800ab605  jz      short loc_1800AB633
0x1800ab607  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ab60e  jz      short loc_1800AB62D
0x1800ab610  mov     ecx, dword ptr [rsp+2E0h+Data]
0x1800ab614  lea     rax, [rbp+1E0h+Name]
0x1800ab618  mov     dword ptr [rsp+2E0h+lpcchClass], ecx
0x1800ab61c  mov     r9d, esi
0x1800ab61f  mov     [rsp+2E0h+lpClass], rax
0x1800ab624  mov     dword ptr [rsp+2E0h+lpReserved], edi
0x1800ab628  call    WPP_SF_DDSD
0x1800ab62d  inc     edi
0x1800ab62f  mov     ebx, esi
0x1800ab631  jmp     short loc_1800AB639
0x1800ab633  mov     r12d, 1
0x1800ab639  mov     esi, 80070000h
0x1800ab63e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ab643  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800ab648  mov     [rsp+2E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800ab64d  lea     r8, [rbp+1E0h+Name]; lpName
0x1800ab651  mov     [rsp+2E0h+lpcchClass], r13; lpcchClass
0x1800ab656  mov     edx, edi; dwIndex
0x1800ab658  mov     [rsp+2E0h+lpClass], r13; lpClass
0x1800ab65d  mov     [rsp+2E0h+lpReserved], r13; lpReserved
0x1800ab662  mov     [rsp+2E0h+cchName], 105h
0x1800ab66a  call    cs:__imp_RegEnumKeyExW
0x1800ab671  nop     dword ptr [rax+rax+00h]
0x1800ab676  test    eax, eax
0x1800ab678  jz      loc_1800AB4BA
0x1800ab67e  test    r12d, r12d
0x1800ab681  jnz     short loc_1800AB695
0x1800ab683  test    ebx, ebx
0x1800ab685  jle     loc_1800AB76D
0x1800ab68b  movzx   eax, bx
0x1800ab68e  or      eax, esi
0x1800ab690  jmp     loc_1800AB76F
0x1800ab695  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x1800ab69a  test    rcx, rcx
0x1800ab69d  jz      short loc_1800AB6B0
0x1800ab69f  call    cs:__imp_RegCloseKey
0x1800ab6a6  nop     dword ptr [rax+rax+00h]
0x1800ab6ab  mov     [rsp+2E0h+phkResult], r13
0x1800ab6b0  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ab6b5  test    rcx, rcx
0x1800ab6b8  jz      short loc_1800AB6CB
0x1800ab6ba  call    cs:__imp_RegCloseKey
0x1800ab6c1  nop     dword ptr [rax+rax+00h]
0x1800ab6c6  mov     [rsp+2E0h+hKey], r13
0x1800ab6cb  mov     rdi, [r15+10h]
0x1800ab6cf  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800ab6d6  jz      short loc_1800AB6F1
0x1800ab6d8  mov     edx, 10h
0x1800ab6dd  lea     r8, WPP_71080afd593b3f642843e61775452ce0_Traceguids
0x1800ab6e4  mov     ecx, 40Bh
0x1800ab6e9  mov     r9, rdi
0x1800ab6ec  call    WPP_SF_q
0x1800ab6f1  mov     rcx, rdi
0x1800ab6f4  call    ?DeleteAll@?$CWxRefMap@VConnectionPolicyMap@@VConnectionAppIdPolicyNode@@@@QEAAXXZ; CWxRefMap<ConnectionPolicyMap,ConnectionAppIdPolicyNode>::DeleteAll(void)
0x1800ab6f9  mov     rcx, [rdi+18h]; this
0x1800ab6fd  test    rcx, rcx
0x1800ab700  jz      short loc_1800AB70B
0x1800ab702  call    ?Release@ConnectionAppIdPolicyNode@@QEAAKXZ; ConnectionAppIdPolicyNode::Release(void)
0x1800ab707  mov     [rdi+18h], r13
0x1800ab70b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800ab712  jz      short loc_1800AB72A
0x1800ab714  mov     edx, 11h
0x1800ab719  lea     r8, WPP_71080afd593b3f642843e61775452ce0_Traceguids
0x1800ab720  mov     ecx, 40Bh
0x1800ab725  call    WPP_SF_
0x1800ab72a  mov     rcx, r15; this
0x1800ab72d  call    ?ReadConnectionPolicyRules@DnsConnectionManager@@AEAAJXZ; DnsConnectionManager::ReadConnectionPolicyRules(void)
0x1800ab732  test    eax, eax
0x1800ab734  jns     short loc_1800AB743
0x1800ab736  mov     [rsp+2E0h+var_29C], 390h
0x1800ab73e  jmp     loc_1800AB472
0x1800ab743  test    ebx, ebx
0x1800ab745  jg      short loc_1800AB74B
0x1800ab747  mov     eax, ebx
0x1800ab749  jmp     short loc_1800AB750
0x1800ab74b  movzx   eax, bx
0x1800ab74e  or      eax, esi
0x1800ab750  mov     ebx, eax
0x1800ab752  test    eax, eax
0x1800ab754  jns     short loc_1800AB786
0x1800ab756  mov     [rsp+2E0h+var_29C], 396h
0x1800ab75e  jmp     short loc_1800AB786
0x1800ab760  mov     [rsp+2E0h+var_29C], 337h
0x1800ab768  jmp     loc_1800AB472
0x1800ab76d  mov     eax, ebx
0x1800ab76f  test    eax, eax
0x1800ab771  jns     short loc_1800AB780
0x1800ab773  mov     [rsp+2E0h+var_29C], 382h
0x1800ab77b  jmp     loc_1800AB472
0x1800ab780  mov     eax, r13d
0x1800ab783  mov     ebx, r13d
0x1800ab786  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800ab78d  jz      short loc_1800AB7A8
0x1800ab78f  mov     edx, 2Ch ; ','
0x1800ab794  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ab79b  mov     ecx, 40Bh
0x1800ab7a0  mov     r9d, eax
0x1800ab7a3  call    WPP_SF_d
0x1800ab7a8  cmp     dword ptr [rsp+2E0h+var_290], r13d
0x1800ab7ad  jz      short loc_1800AB7B9
0x1800ab7af  lea     rcx, [rsp+2E0h+var_298]; this
0x1800ab7b4  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x1800ab7b9  cmp     dword ptr [rsp+2E0h+var_290+4], r13d
0x1800ab7be  jz      short loc_1800AB7CA
0x1800ab7c0  lea     rcx, [rsp+2E0h+var_298]; this
0x1800ab7c5  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x1800ab7ca  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x1800ab7cf  test    rcx, rcx
0x1800ab7d2  jz      short loc_1800AB7E5
0x1800ab7d4  call    cs:__imp_RegCloseKey
0x1800ab7db  nop     dword ptr [rax+rax+00h]
0x1800ab7e0  mov     [rsp+2E0h+phkResult], r13
0x1800ab7e5  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ab7ea  test    rcx, rcx
0x1800ab7ed  jz      short loc_1800AB7FB
0x1800ab7ef  call    cs:__imp_RegCloseKey
0x1800ab7f6  nop     dword ptr [rax+rax+00h]
0x1800ab7fb  mov     eax, ebx
0x1800ab7fd  mov     rcx, [rbp+1E0h+var_50]
0x1800ab804  xor     rcx, rsp; StackCookie
0x1800ab807  call    __security_check_cookie
0x1800ab80c  add     rsp, 2A8h
0x1800ab813  pop     r15
0x1800ab815  pop     r14
0x1800ab817  pop     r13
0x1800ab819  pop     r12
0x1800ab81b  pop     rdi
0x1800ab81c  pop     rsi
0x1800ab81d  pop     rbx
0x1800ab81e  pop     rbp
0x1800ab81f  retn
```
