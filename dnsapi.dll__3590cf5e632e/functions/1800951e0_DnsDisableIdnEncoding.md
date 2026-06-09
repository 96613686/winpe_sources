# DnsDisableIdnEncoding

- ea: `0x1800951e0`
- end: `0x180095730`
- name: `DnsDisableIdnEncoding`
- size: `1360`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x1800097e0`
- `0x180011700`
- `0x180017e00`
- `0x180034d20`
- `0x18004ec60`
- `0x180062990`
- `0x180062c94`
- `0x18006f350`
- `0x18008b5f0`
- `0x18008b630`
- `0x180090be0`
- `0x1800951e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180095613`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180095613`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956f6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180095679`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800956e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180095679`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800956e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095658`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095658`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009543d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095479`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800954b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800954ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009552e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009556a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009543d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095479`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800954b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800954ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009552e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009556a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095401`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095401`
- `RPCRT4!UuidCreate` at `0x18009536b`
- `RPCRT4!UuidCreate` at `0x18009536b`

## string_xrefs

- `0x1800953a0`: `Parameters\DnsPolicyConfig`
- `0x1800955a3`: `Parameters\DnsPolicyConfig`
- `0x1800953b3`: `Dnscache`
- `0x1800955b6`: `Dnscache`
- `0x1800953ac`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x1800955af`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x180095553`: `IDNConfig`
- `0x180095514`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall DnsDisableIdnEncoding(int a1, const WCHAR *a2, __int64 a3, int a4)
{
  int v5; // esi
  DNS_STATUS v6; // eax
  unsigned int PersistedRegistryKeyHelper; // ebx
  unsigned __int64 v8; // r11
  size_t v9; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  DWORD v12; // edi
  unsigned int PolicyTableInfo; // eax
  _QWORD *j; // rbx
  int v15; // r9d
  DWORD i; // edi
  LSTATUS v17; // eax
  size_t pcbLength; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h]
  LPVOID lpMem; // [rsp+68h] [rbp-98h]
  BYTE Data[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  UUID Uuid; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SubKey[80]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t psz; // [rsp+140h] [rbp+40h] BYREF
  wchar_t pszDest[255]; // [rsp+142h] [rbp+42h] BYREF

  hKey = 0;
  v5 = 0;
  phkResult = 0;
  lpMem = 0;
  if ( a1 != 1 )
  {
    if ( a1 == 2 )
    {
      *(_DWORD *)Data = 0;
      PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                     (unsigned int)L"Dnscache",
                                     (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                     (unsigned int)L"Parameters\\DnsPolicyConfig",
                                     a4,
                                     983103);
      if ( PersistedRegistryKeyHelper )
      {
        PersistedRegistryKeyHelper = 0;
        goto LABEL_50;
      }
      for ( i = 0; i < 0x3E8; ++i )
      {
        *(_DWORD *)Data = 80;
        v17 = RegEnumKeyExW(hKey, i, SubKey, (LPDWORD)Data, 0, 0, 0, 0);
        PersistedRegistryKeyHelper = v17;
        if ( v17 == 259 )
        {
          PersistedRegistryKeyHelper = 0;
          goto LABEL_48;
        }
        if ( v17 != 234 )
        {
          if ( v17 )
            goto LABEL_50;
          PersistedRegistryKeyHelper = RegGetValueW(hKey, SubKey, L"Volatile", 0xFFFFu, 0, 0, 0);
          if ( !PersistedRegistryKeyHelper )
          {
            PersistedRegistryKeyHelper = RegDeleteKeyExW(hKey, SubKey, 0, 0);
            if ( !PersistedRegistryKeyHelper )
              --i;
          }
        }
      }
      goto LABEL_48;
    }
    goto LABEL_49;
  }
  if ( !a2 )
  {
LABEL_49:
    PersistedRegistryKeyHelper = 87;
    goto LABEL_50;
  }
  pcbLength = 0;
  v24 = 0;
  v25 = 0;
  *(_DWORD *)Data = 0;
  Uuid = 0;
  v6 = DnsValidateName_W(a2, DnsNameDomain);
  PersistedRegistryKeyHelper = v6;
  if ( !v6 || v6 == 9556 )
  {
    psz = 46;
    if ( StringCbCopyW(pszDest, 0x1FCu, a2) < 0 || StringCbLengthW(&psz, 0x200u, &pcbLength) < 0 )
    {
      PersistedRegistryKeyHelper = 123;
      goto LABEL_50;
    }
    v9 = pcbLength;
    if ( pcbLength >> 1 > 1 && SubKey[(pcbLength >> 1) + 79] == 46 )
      v9 = pcbLength - 2;
    v10 = 2 * (v9 >> 1);
    if ( v10 >= v8 || (pszDest[v10 / 2 - 1] = 0, v11 = v10 + 2, v11 >= v8) )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)&pszDest[-1] + v11) = 0;
    v12 = v9 + 4;
    PolicyTableInfo = DnsGetPolicyTableInfo(&psz);
    PersistedRegistryKeyHelper = PolicyTableInfo;
    if ( PolicyTableInfo != 9572 )
    {
      if ( !PolicyTableInfo )
      {
        for ( j = lpMem; j; j = (_QWORD *)j[14] )
        {
          if ( !(unsigned int)wcsicmp_ThatWorks(&psz, (PCNZWCH)*j) && (*((_BYTE *)j + 108) & 0x10) != 0 )
          {
            PersistedRegistryKeyHelper = *((_DWORD *)j + 26) != 0 ? 0x1392 : 0;
            goto LABEL_50;
          }
        }
      }
      if ( UuidCreate(&Uuid) || !(unsigned int)Dns_GuidToString(&Uuid, SubKey) )
      {
        PersistedRegistryKeyHelper = 8;
        goto LABEL_50;
      }
      PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                     (unsigned int)L"Dnscache",
                                     (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                     (unsigned int)L"Parameters\\DnsPolicyConfig",
                                     v15,
                                     983103);
      if ( !PersistedRegistryKeyHelper )
      {
        PersistedRegistryKeyHelper = RegCreateKeyExW(hKey, SubKey, 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
        if ( !PersistedRegistryKeyHelper )
        {
          *(_DWORD *)Data = 1;
          PersistedRegistryKeyHelper = RegSetValueExW(phkResult, L"Volatile", 0, 4u, Data, 4u);
          if ( PersistedRegistryKeyHelper )
            goto LABEL_27;
          PersistedRegistryKeyHelper = RegSetValueExW(phkResult, L"Name", 0, 7u, (const BYTE *)&psz, v12);
          if ( PersistedRegistryKeyHelper )
            goto LABEL_27;
          *(_DWORD *)Data = 0;
          PersistedRegistryKeyHelper = RegSetValueExW(phkResult, L"IPSECCARestriction", 0, 1u, Data, 2u);
          if ( PersistedRegistryKeyHelper
            || (*(_DWORD *)Data = 2,
                (PersistedRegistryKeyHelper = RegSetValueExW(phkResult, L"Version", 0, 4u, Data, 4u)) != 0)
            || (*(_DWORD *)Data = 16,
                (PersistedRegistryKeyHelper = RegSetValueExW(phkResult, L"ConfigOptions", 0, 4u, Data, 4u)) != 0)
            || (*(_DWORD *)Data = 0,
                (PersistedRegistryKeyHelper = RegSetValueExW(phkResult, L"IDNConfig", 0, 4u, Data, 4u)) != 0) )
          {
LABEL_27:
            v5 = 1;
            goto LABEL_50;
          }
LABEL_48:
          DnsNotifyResolver(0, 0);
        }
      }
    }
  }
LABEL_50:
  if ( lpMem )
    DnsFreePolicyConfig(lpMem);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    RegDeleteKeyExW(hKey, SubKey, 0, 0);
  if ( hKey )
    RegCloseKey(hKey);
  return PersistedRegistryKeyHelper;
}

```

## disassembly

```asm
0x1800951e0  mov     [rsp-8+arg_0], rbx
0x1800951e5  mov     [rsp-8+arg_10], rsi
0x1800951ea  push    rbp
0x1800951eb  push    rdi
0x1800951ec  push    r12
0x1800951ee  push    r14
0x1800951f0  push    r15
0x1800951f2  lea     rbp, [rsp-250h]
0x1800951fa  sub     rsp, 350h
0x180095201  mov     rax, cs:__security_cookie
0x180095208  xor     rax, rsp
0x18009520b  mov     [rbp+270h+var_30], rax
0x180095212  xor     r14d, r14d
0x180095215  mov     rdi, rdx
0x180095218  mov     [rsp+370h+hKey], r14
0x18009521d  mov     esi, r14d
0x180095220  mov     [rsp+370h+var_318], r14
0x180095225  mov     [rsp+370h+lpMem], r14
0x18009522a  lea     r15d, [r14+1]
0x18009522e  cmp     ecx, r15d
0x180095231  jnz     loc_18009558B
0x180095237  test    rdx, rdx
0x18009523a  jz      loc_1800956A3
0x180095240  xor     eax, eax
0x180095242  mov     [rsp+370h+pcbLength], r14
0x180095247  xorps   xmm0, xmm0
0x18009524a  mov     [rsp+370h+var_2F8], rax
0x18009524f  xor     edx, edx; Format
0x180095251  mov     [rbp+270h+var_2F0], eax
0x180095254  mov     rcx, rdi; pszName
0x180095257  mov     dword ptr [rsp+370h+Data], r14d
0x18009525c  movups  xmmword ptr [rbp+270h+Uuid.Data1], xmm0
0x180095260  call    DnsValidateName_W
0x180095265  mov     ebx, eax
0x180095267  test    eax, eax
0x180095269  jz      short loc_180095276
0x18009526b  cmp     eax, 2554h
0x180095270  jnz     loc_1800956A8
0x180095276  mov     ebx, 2Eh ; '.'
0x18009527b  lea     rcx, [rbp+270h+pszDest]; pszDest
0x18009527f  mov     r8, rdi; pszSrc
0x180095282  mov     [rbp+270h+psz], bx
0x180095286  mov     edx, 1FCh; cbDest
0x18009528b  call    StringCbCopyW
0x180095290  test    eax, eax
0x180095292  jns     short loc_18009529E
0x180095294  mov     ebx, 7Bh ; '{'
0x180095299  jmp     loc_1800956A8
0x18009529e  mov     r11d, 200h
0x1800952a4  lea     r8, [rsp+370h+pcbLength]; pcbLength
0x1800952a9  mov     edx, r11d; cbMax
0x1800952ac  lea     rcx, [rbp+270h+psz]; psz
0x1800952b0  call    StringCbLengthW
0x1800952b5  test    eax, eax
0x1800952b7  js      short loc_180095294
0x1800952b9  mov     rdi, [rsp+370h+pcbLength]
0x1800952be  mov     rax, rdi
0x1800952c1  shr     rax, 1
0x1800952c4  cmp     rax, r15
0x1800952c7  jbe     short loc_1800952D4
0x1800952c9  cmp     [rbp+rax*2+270h+var_232], bx
0x1800952ce  jnz     short loc_1800952D4
0x1800952d0  sub     rdi, 2
0x1800952d4  mov     rax, rdi
0x1800952d7  shr     rax, 1
0x1800952da  lea     rcx, [rax+rax]
0x1800952de  cmp     rcx, r11
0x1800952e1  jnb     loc_180095585
0x1800952e7  mov     [rbp+rcx+270h+psz], r14w
0x1800952ed  add     rcx, 2
0x1800952f1  cmp     rcx, r11
0x1800952f4  jnb     loc_180095585
0x1800952fa  mov     [rbp+rcx+270h+psz], r14w
0x180095300  lea     r9, [rsp+370h+var_2F8]
0x180095305  mov     r12d, 4
0x18009530b  lea     rcx, [rbp+270h+psz]; Src
0x18009530f  lea     r8, [rsp+370h+lpMem]
0x180095314  xor     edx, edx
0x180095316  add     rdi, r12
0x180095319  call    DnsGetPolicyTableInfo
0x18009531e  mov     ebx, eax
0x180095320  cmp     eax, 2564h
0x180095325  jz      loc_1800956A8
0x18009532b  test    eax, eax
0x18009532d  jnz     short loc_180095367
0x18009532f  mov     rbx, [rsp+370h+lpMem]
0x180095334  test    rbx, rbx
0x180095337  jz      short loc_180095367
0x180095339  mov     rdx, [rbx]; lpString2
0x18009533c  lea     rcx, [rbp+270h+psz]; lpString1
0x180095340  call    wcsicmp_ThatWorks
0x180095345  test    eax, eax
0x180095347  jnz     short loc_18009534F
0x180095349  test    byte ptr [rbx+6Ch], 10h
0x18009534d  jnz     short loc_180095355
0x18009534f  mov     rbx, [rbx+70h]
0x180095353  jmp     short loc_180095334
0x180095355  mov     eax, [rbx+68h]
0x180095358  neg     eax
0x18009535a  sbb     ebx, ebx
0x18009535c  and     ebx, 1392h
0x180095362  jmp     loc_1800956A8
0x180095367  lea     rcx, [rbp+270h+Uuid]; Uuid
0x18009536b  call    cs:__imp_UuidCreate
0x180095372  nop     dword ptr [rax+rax+00h]
0x180095377  test    eax, eax
0x180095379  jz      short loc_180095385
0x18009537b  mov     ebx, 8
0x180095380  jmp     loc_1800956A8
0x180095385  lea     rdx, [rbp+270h+SubKey]
0x180095389  lea     rcx, [rbp+270h+Uuid]
0x18009538d  call    Dns_GuidToString
0x180095392  test    eax, eax
0x180095394  jz      short loc_18009537B
0x180095396  lea     rax, [rsp+370h+hKey]
0x18009539b  mov     [rsp+370h+phkResult], rax
0x1800953a0  lea     r8, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x1800953a7  mov     dword ptr [rsp+370h+lpSecurityAttributes], r15d
0x1800953ac  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800953b3  lea     rcx, aDnscache_1; "Dnscache"
0x1800953ba  mov     [rsp+370h+dwOptions], 0F003Fh
0x1800953c2  call    CreatePersistedRegistryKeyHelper
0x1800953c7  mov     ebx, eax
0x1800953c9  test    eax, eax
0x1800953cb  jnz     loc_1800956A8
0x1800953d1  mov     rcx, [rsp+370h+hKey]; hKey
0x1800953d6  lea     rax, [rsp+370h+var_318]
0x1800953db  mov     [rsp+370h+lpdwDisposition], r14; lpdwDisposition
0x1800953e0  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x1800953e4  mov     [rsp+370h+phkResult], rax; phkResult
0x1800953e9  xor     r9d, r9d; lpClass
0x1800953ec  mov     [rsp+370h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800953f1  xor     r8d, r8d; Reserved
0x1800953f4  mov     [rsp+370h+samDesired], 0F003Fh; samDesired
0x1800953fc  mov     [rsp+370h+dwOptions], r15d; dwOptions
0x180095401  call    cs:__imp_RegCreateKeyExW
0x180095408  nop     dword ptr [rax+rax+00h]
0x18009540d  mov     ebx, eax
0x18009540f  test    eax, eax
0x180095411  jnz     loc_1800956A8
0x180095417  mov     rcx, [rsp+370h+var_318]; hKey
0x18009541c  lea     rax, [rsp+370h+Data]
0x180095421  mov     [rsp+370h+samDesired], r12d; cbData
0x180095426  lea     rdx, aVolatile; "Volatile"
0x18009542d  mov     r9d, r12d; dwType
0x180095430  mov     qword ptr [rsp+370h+dwOptions], rax; lpData
0x180095435  xor     r8d, r8d; Reserved
0x180095438  mov     dword ptr [rsp+370h+Data], r15d
0x18009543d  call    cs:__imp_RegSetValueExW
0x180095444  nop     dword ptr [rax+rax+00h]
0x180095449  mov     ebx, eax
0x18009544b  test    eax, eax
0x18009544d  jz      short loc_180095457
0x18009544f  mov     esi, r15d
0x180095452  jmp     loc_1800956A8
0x180095457  mov     rcx, [rsp+370h+var_318]; hKey
0x18009545c  lea     rax, [rbp+270h+psz]
0x180095460  mov     [rsp+370h+samDesired], edi; cbData
0x180095464  lea     rdx, aName; "Name"
0x18009546b  mov     r9d, 7; dwType
0x180095471  mov     qword ptr [rsp+370h+dwOptions], rax; lpData
0x180095476  xor     r8d, r8d; Reserved
0x180095479  call    cs:__imp_RegSetValueExW
0x180095480  nop     dword ptr [rax+rax+00h]
0x180095485  mov     ebx, eax
0x180095487  test    eax, eax
0x180095489  jnz     short loc_18009544F
0x18009548b  mov     rcx, [rsp+370h+var_318]; hKey
0x180095490  lea     rax, [rsp+370h+Data]
0x180095495  mov     [rsp+370h+samDesired], 2; cbData
0x18009549d  lea     rdx, aIpseccarestric; "IPSECCARestriction"
0x1800954a4  mov     r9d, r15d; dwType
0x1800954a7  mov     qword ptr [rsp+370h+dwOptions], rax; lpData
0x1800954ac  xor     r8d, r8d; Reserved
0x1800954af  mov     dword ptr [rsp+370h+Data], r14d
0x1800954b4  call    cs:__imp_RegSetValueExW
0x1800954bb  nop     dword ptr [rax+rax+00h]
0x1800954c0  mov     ebx, eax
0x1800954c2  test    eax, eax
0x1800954c4  jnz     short loc_18009544F
0x1800954c6  mov     rcx, [rsp+370h+var_318]; hKey
0x1800954cb  lea     rax, [rsp+370h+Data]
0x1800954d0  mov     [rsp+370h+samDesired], r12d; cbData
0x1800954d5  lea     rdx, aVersion; "Version"
0x1800954dc  mov     r9d, r12d; dwType
0x1800954df  mov     qword ptr [rsp+370h+dwOptions], rax; lpData
0x1800954e4  xor     r8d, r8d; Reserved
0x1800954e7  mov     dword ptr [rsp+370h+Data], 2
0x1800954ef  call    cs:__imp_RegSetValueExW
0x1800954f6  nop     dword ptr [rax+rax+00h]
0x1800954fb  mov     ebx, eax
0x1800954fd  test    eax, eax
0x1800954ff  jnz     loc_18009544F
0x180095505  mov     rcx, [rsp+370h+var_318]; hKey
0x18009550a  lea     rax, [rsp+370h+Data]
0x18009550f  mov     [rsp+370h+samDesired], r12d; cbData
0x180095514  lea     rdx, aConfigoptions; "ConfigOptions"
0x18009551b  mov     r9d, r12d; dwType
0x18009551e  mov     qword ptr [rsp+370h+dwOptions], rax; lpData
0x180095523  xor     r8d, r8d; Reserved
0x180095526  mov     dword ptr [rsp+370h+Data], 10h
0x18009552e  call    cs:__imp_RegSetValueExW
0x180095535  nop     dword ptr [rax+rax+00h]
0x18009553a  mov     ebx, eax
0x18009553c  test    eax, eax
0x18009553e  jnz     loc_18009544F
0x180095544  mov     rcx, [rsp+370h+var_318]; hKey
0x180095549  lea     rax, [rsp+370h+Data]
0x18009554e  mov     [rsp+370h+samDesired], r12d; cbData
0x180095553  lea     rdx, aIdnconfig; "IDNConfig"
0x18009555a  mov     r9d, r12d; dwType
0x18009555d  mov     qword ptr [rsp+370h+dwOptions], rax; lpData
0x180095562  xor     r8d, r8d; Reserved
0x180095565  mov     dword ptr [rsp+370h+Data], r14d
0x18009556a  call    cs:__imp_RegSetValueExW
0x180095571  nop     dword ptr [rax+rax+00h]
0x180095576  mov     ebx, eax
0x180095578  test    eax, eax
0x18009557a  jz      loc_180095698
0x180095580  jmp     loc_18009544F
0x180095585  call    __report_rangecheckfailure
0x18009558b  cmp     ecx, 2
0x18009558e  jnz     loc_1800956A3
0x180095594  lea     rax, [rsp+370h+hKey]
0x180095599  mov     dword ptr [rsp+370h+Data], r14d
0x18009559e  mov     [rsp+370h+phkResult], rax
0x1800955a3  lea     r8, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x1800955aa  mov     dword ptr [rsp+370h+lpSecurityAttributes], r14d
0x1800955af  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800955b6  lea     rcx, aDnscache_1; "Dnscache"
0x1800955bd  mov     [rsp+370h+dwOptions], 0F003Fh
0x1800955c5  call    CreatePersistedRegistryKeyHelper
0x1800955ca  mov     ebx, eax
0x1800955cc  test    eax, eax
0x1800955ce  jz      short loc_1800955D8
0x1800955d0  mov     ebx, r14d
0x1800955d3  jmp     loc_1800956A8
0x1800955d8  mov     edi, r14d
0x1800955db  cmp     edi, 3E8h
0x1800955e1  jnb     loc_180095698
0x1800955e7  mov     rcx, [rsp+370h+hKey]; hKey
0x1800955ec  lea     r9, [rsp+370h+Data]; lpcchName
0x1800955f1  mov     [rsp+370h+phkResult], r14; lpftLastWriteTime
0x1800955f6  lea     r8, [rbp+270h+SubKey]; lpName
0x1800955fa  mov     [rsp+370h+lpSecurityAttributes], r14; lpcchClass
0x1800955ff  mov     edx, edi; dwIndex
0x180095601  mov     qword ptr [rsp+370h+samDesired], r14; lpClass
0x180095606  mov     qword ptr [rsp+370h+dwOptions], r14; lpReserved
0x18009560b  mov     dword ptr [rsp+370h+Data], 50h ; 'P'
0x180095613  call    cs:__imp_RegEnumKeyExW
0x18009561a  nop     dword ptr [rax+rax+00h]
0x18009561f  mov     ebx, eax
0x180095621  cmp     eax, 103h
0x180095626  jz      short loc_180095695
0x180095628  cmp     eax, 0EAh
0x18009562d  jz      short loc_18009568D
0x18009562f  test    eax, eax
0x180095631  jnz     short loc_1800956A8
0x180095633  mov     rcx, [rsp+370h+hKey]; hkey
0x180095638  lea     r8, aVolatile; "Volatile"
0x18009563f  mov     [rsp+370h+lpSecurityAttributes], r14; pcbData
0x180095644  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x180095648  mov     qword ptr [rsp+370h+samDesired], r14; pvData
0x18009564d  mov     r9d, 0FFFFh; dwFlags
0x180095653  mov     qword ptr [rsp+370h+dwOptions], r14; pdwType
0x180095658  call    cs:__imp_RegGetValueW
0x18009565f  nop     dword ptr [rax+rax+00h]
0x180095664  mov     ebx, eax
0x180095666  test    eax, eax
0x180095668  jnz     short loc_18009568D
0x18009566a  mov     rcx, [rsp+370h+hKey]; hKey
0x18009566f  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x180095673  xor     r9d, r9d; Reserved
0x180095676  xor     r8d, r8d; samDesired
0x180095679  call    cs:__imp_RegDeleteKeyExW
0x180095680  nop     dword ptr [rax+rax+00h]
0x180095685  mov     ebx, eax
0x180095687  test    eax, eax
0x180095689  jnz     short loc_18009568D
0x18009568b  dec     edi
0x18009568d  add     edi, r15d
0x180095690  jmp     loc_1800955DB
0x180095695  mov     ebx, r14d
0x180095698  xor     edx, edx
0x18009569a  xor     ecx, ecx
0x18009569c  call    DnsNotifyResolver
0x1800956a1  jmp     short loc_1800956A8
0x1800956a3  mov     ebx, 57h ; 'W'
0x1800956a8  mov     rcx, [rsp+370h+lpMem]; lpMem
0x1800956ad  test    rcx, rcx
0x1800956b0  jz      short loc_1800956B7
0x1800956b2  call    DnsFreePolicyConfig
0x1800956b7  mov     rcx, [rsp+370h+var_318]; hKey
0x1800956bc  test    rcx, rcx
0x1800956bf  jz      short loc_1800956CD
0x1800956c1  call    cs:__imp_RegCloseKey
0x1800956c8  nop     dword ptr [rax+rax+00h]
0x1800956cd  test    esi, esi
0x1800956cf  jz      short loc_1800956EC
0x1800956d1  mov     rcx, [rsp+370h+hKey]; hKey
  ... truncated ...
```
