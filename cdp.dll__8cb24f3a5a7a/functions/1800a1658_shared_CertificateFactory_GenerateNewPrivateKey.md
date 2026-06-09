# shared::CertificateFactory::GenerateNewPrivateKey

- ea: `0x1800a1658`
- end: `0x1800a18db`
- name: `shared::CertificateFactory::GenerateNewPrivateKey`
- size: `643`
- prototype: `__int64 __fastcall(NCRYPT_KEY_HANDLE *phKey, LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a18e4`

## callees

- `0x1800113bc`
- `0x180030190`
- `0x1800624cc`
- `0x1800a1168`
- `0x1800a1658`
- `0x1800a5aa8`
- `0x18011d8c4`
- `0x1801f6fb0`

## import_xrefs

- `ncrypt!NCryptCreatePersistedKey` at `0x1800a179c`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800a179c`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a16a1`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a16a1`
- `ncrypt!NCryptFinalizeKey` at `0x1800a186f`
- `ncrypt!NCryptFinalizeKey` at `0x1800a186f`
- `ncrypt!NCryptDeleteKey` at `0x1800a172d`
- `ncrypt!NCryptDeleteKey` at `0x1800a172d`
- `ncrypt!NCryptFreeObject` at `0x1800a18b2`
- `ncrypt!NCryptFreeObject` at `0x1800a18b2`
- `ncrypt!NCryptOpenKey` at `0x1800a1717`
- `ncrypt!NCryptOpenKey` at `0x1800a1717`
- `ncrypt!NCryptSetProperty` at `0x1800a1830`
- `ncrypt!NCryptSetProperty` at `0x1800a1830`

## string_xrefs

- `0x1800a17ab`: `NCryptCreatePersistedKey returned 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
NCRYPT_KEY_HANDLE *__fastcall shared::CertificateFactory::GenerateNewPrivateKey(
        NCRYPT_KEY_HANDLE *phKey,
        const WCHAR *pszKeyName)
{
  unsigned int v4; // eax
  __int64 v5; // rax
  const WCHAR *v6; // rsi
  NCRYPT_KEY_HANDLE v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rax
  SECURITY_STATUS PersistedKey; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rax
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-39h] BYREF
  int v19; // [rsp+38h] [rbp-31h]
  BYTE pbInput[4]; // [rsp+3Ch] [rbp-2Dh] BYREF
  NCRYPT_KEY_HANDLE *v21; // [rsp+40h] [rbp-29h]
  _BYTE v22[56]; // [rsp+48h] [rbp-21h] BYREF
  const char *v23; // [rsp+80h] [rbp+17h] BYREF
  int v24; // [rsp+88h] [rbp+1Fh]

  v21 = phKey;
  v19 = 0;
  phProvider = 0;
  v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  if ( v4 )
  {
    v23 = ".\\certificatefactory.cpp";
    v24 = 42;
    v5 = cdp::MakeException<cdp::hresult_exception>(v22, &v23, v4);
    cdp::CdpThrow<cdp::hresult_exception>(&v23, v5);
  }
  *phKey = 0;
  v19 = 1;
  if ( *((_QWORD *)pszKeyName + 3) <= 7u )
    v6 = pszKeyName;
  else
    v6 = *(const WCHAR **)pszKeyName;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    phKey,
    0);
  if ( !NCryptOpenKey(phProvider, phKey, v6, 0, 0) )
  {
    v7 = *phKey;
    *phKey = 0;
    v8 = NCryptDeleteKey(v7, 0);
    if ( v8 )
    {
      v23 = ".\\certificatefactory.cpp";
      v24 = 49;
      v9 = cdp::MakeException<cdp::hresult_exception>(v22, &v23, v8);
      cdp::CdpThrow<cdp::hresult_exception>(&v23, v9);
    }
  }
  if ( *((_QWORD *)pszKeyName + 3) > 7u )
    pszKeyName = *(const WCHAR **)pszKeyName;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    phKey,
    0);
  PersistedKey = NCryptCreatePersistedKey(phProvider, phKey, L"ECDSA_P256", pszKeyName, 0, 0x80u);
  v11 = PersistedKey;
  if ( PersistedKey )
  {
    cdp::detail::StringFormat(&v23, "NCryptCreatePersistedKey returned 0x%08x", PersistedKey);
    shared::AggregatedTelemetryLogger::Log(2147549183LL, &v23, ".\\certificatefactory.cpp", 55);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v23);
    v23 = ".\\certificatefactory.cpp";
    v24 = 56;
    v12 = cdp::MakeException<cdp::hresult_exception>(v22, &v23, v11);
    cdp::CdpThrow<cdp::hresult_exception>(&v23, v12);
  }
  *(_DWORD *)pbInput = 3;
  v13 = NCryptSetProperty(*phKey, L"Export Policy", pbInput, 4u, 0x80000000);
  if ( v13 )
  {
    v23 = ".\\certificatefactory.cpp";
    v24 = 61;
    v14 = cdp::MakeException<cdp::hresult_exception>(v22, &v23, v13);
    cdp::CdpThrow<cdp::hresult_exception>(&v23, v14);
  }
  v15 = NCryptFinalizeKey(*phKey, 0);
  if ( v15 )
  {
    v23 = ".\\certificatefactory.cpp";
    v24 = 64;
    v16 = cdp::MakeException<cdp::hresult_exception>(v22, &v23, v15);
    cdp::CdpThrow<cdp::hresult_exception>(&v23, v16);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return phKey;
}

```

## disassembly

```asm
0x1800a1658  mov     [rsp-8+arg_10], rbx
0x1800a165d  push    rbp
0x1800a165e  push    rsi
0x1800a165f  push    rdi
0x1800a1660  lea     rbp, [rsp-47h]
0x1800a1665  sub     rsp, 0B0h
0x1800a166c  mov     rax, cs:__security_cookie
0x1800a1673  xor     rax, rsp
0x1800a1676  mov     [rbp+57h+var_20], rax
0x1800a167a  mov     rdi, rdx
0x1800a167d  mov     rbx, rcx
0x1800a1680  mov     [rbp+57h+var_80], rcx
0x1800a1684  mov     [rbp+57h+var_88], 0
0x1800a168b  mov     [rbp+57h+phProvider], 0
0x1800a1693  xor     r8d, r8d; dwFlags
0x1800a1696  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x1800a169d  lea     rcx, [rbp+57h+phProvider]; phProvider
0x1800a16a1  call    cs:__imp_NCryptOpenStorageProvider
0x1800a16a7  test    eax, eax
0x1800a16a9  jz      short loc_1800A16DB
0x1800a16ab  lea     rbx, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a16b2  mov     [rbp+57h+var_40], rbx
0x1800a16b6  mov     [rbp+57h+var_38], 2Ah ; '*'
0x1800a16bd  mov     r8d, eax
0x1800a16c0  lea     rdx, [rbp+57h+var_40]
0x1800a16c4  lea     rcx, [rbp+57h+var_78]
0x1800a16c8  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a16cd  nop
0x1800a16ce  mov     rdx, rax
0x1800a16d1  lea     rcx, [rbp+57h+var_40]
0x1800a16d5  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a16db  mov     qword ptr [rbx], 0
0x1800a16e2  mov     [rbp+57h+var_88], 1
0x1800a16e9  cmp     qword ptr [rdi+18h], 7
0x1800a16ee  jbe     short loc_1800A16F5
0x1800a16f0  mov     rsi, [rdi]
0x1800a16f3  jmp     short loc_1800A16F8
0x1800a16f5  mov     rsi, rdi
0x1800a16f8  xor     edx, edx
0x1800a16fa  mov     rcx, rbx
0x1800a16fd  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a1702  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x1800a170a  xor     r9d, r9d; dwLegacyKeySpec
0x1800a170d  mov     r8, rsi; pszKeyName
0x1800a1710  mov     rdx, rbx; phKey
0x1800a1713  mov     rcx, [rbp+57h+phProvider]; hProvider
0x1800a1717  call    cs:__imp_NCryptOpenKey
0x1800a171d  test    eax, eax
0x1800a171f  jnz     short loc_1800A1767
0x1800a1721  mov     rcx, [rbx]; hKey
0x1800a1724  mov     qword ptr [rbx], 0
0x1800a172b  xor     edx, edx; dwFlags
0x1800a172d  call    cs:__imp_NCryptDeleteKey
0x1800a1733  test    eax, eax
0x1800a1735  jz      short loc_1800A1767
0x1800a1737  lea     rbx, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a173e  mov     [rbp+57h+var_40], rbx
0x1800a1742  mov     [rbp+57h+var_38], 31h ; '1'
0x1800a1749  mov     r8d, eax
0x1800a174c  lea     rdx, [rbp+57h+var_40]
0x1800a1750  lea     rcx, [rbp+57h+var_78]
0x1800a1754  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a1759  nop
0x1800a175a  mov     rdx, rax
0x1800a175d  lea     rcx, [rbp+57h+var_40]
0x1800a1761  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a1767  cmp     qword ptr [rdi+18h], 7
0x1800a176c  jbe     short loc_1800A1771
0x1800a176e  mov     rdi, [rdi]
0x1800a1771  xor     edx, edx
0x1800a1773  mov     rcx, rbx
0x1800a1776  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a177b  mov     [rsp+0C0h+var_98], 80h; dwFlags
0x1800a1783  mov     [rsp+0C0h+dwFlags], 0; dwLegacyKeySpec
0x1800a178b  mov     r9, rdi; pszKeyName
0x1800a178e  lea     r8, aEcdsaP256; "ECDSA_P256"
0x1800a1795  mov     rdx, rbx; phKey
0x1800a1798  mov     rcx, [rbp+57h+phProvider]; hProvider
0x1800a179c  call    cs:__imp_NCryptCreatePersistedKey
0x1800a17a2  mov     edi, eax
0x1800a17a4  test    eax, eax
0x1800a17a6  jz      short loc_1800A180D
0x1800a17a8  mov     r8d, eax
0x1800a17ab  lea     rdx, aNcryptcreatepe_0; "NCryptCreatePersistedKey returned 0x%08"...
0x1800a17b2  lea     rcx, [rbp+57h+var_40]
0x1800a17b6  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800a17bb  nop
0x1800a17bc  mov     r9d, 37h ; '7'
0x1800a17c2  lea     rbx, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a17c9  mov     r8, rbx
0x1800a17cc  lea     rdx, [rbp+57h+var_40]
0x1800a17d0  mov     ecx, 8000FFFFh
0x1800a17d5  call    ?Log@AggregatedTelemetryLogger@shared@@SAXJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDI@Z; shared::AggregatedTelemetryLogger::Log(long,std::string const &,char const *,uint)
0x1800a17da  nop
0x1800a17db  lea     rcx, [rbp+57h+var_40]; void *
0x1800a17df  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a17e4  mov     [rbp+57h+var_40], rbx
0x1800a17e8  mov     [rbp+57h+var_38], 38h ; '8'
0x1800a17ef  mov     r8d, edi
0x1800a17f2  lea     rdx, [rbp+57h+var_40]
0x1800a17f6  lea     rcx, [rbp+57h+var_78]
0x1800a17fa  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a17ff  nop
0x1800a1800  mov     rdx, rax
0x1800a1803  lea     rcx, [rbp+57h+var_40]
0x1800a1807  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a180d  mov     dword ptr [rbp+57h+pbInput], 3
0x1800a1814  mov     [rsp+0C0h+dwFlags], 80000000h; dwFlags
0x1800a181c  mov     r9d, 4; cbInput
0x1800a1822  lea     r8, [rbp+57h+pbInput]; pbInput
0x1800a1826  lea     rdx, aExportPolicy; "Export Policy"
0x1800a182d  mov     rcx, [rbx]; hObject
0x1800a1830  call    cs:__imp_NCryptSetProperty
0x1800a1836  test    eax, eax
0x1800a1838  jz      short loc_1800A186A
0x1800a183a  lea     rbx, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a1841  mov     [rbp+57h+var_40], rbx
0x1800a1845  mov     [rbp+57h+var_38], 3Dh ; '='
0x1800a184c  mov     r8d, eax
0x1800a184f  lea     rdx, [rbp+57h+var_40]
0x1800a1853  lea     rcx, [rbp+57h+var_78]
0x1800a1857  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a185c  nop
0x1800a185d  mov     rdx, rax
0x1800a1860  lea     rcx, [rbp+57h+var_40]
0x1800a1864  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a186a  xor     edx, edx; dwFlags
0x1800a186c  mov     rcx, [rbx]; hKey
0x1800a186f  call    cs:__imp_NCryptFinalizeKey
0x1800a1875  test    eax, eax
0x1800a1877  jz      short loc_1800A18A9
0x1800a1879  lea     rbx, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a1880  mov     [rbp+57h+var_40], rbx
0x1800a1884  mov     [rbp+57h+var_38], 40h ; '@'
0x1800a188b  mov     r8d, eax
0x1800a188e  lea     rdx, [rbp+57h+var_40]
0x1800a1892  lea     rcx, [rbp+57h+var_78]
0x1800a1896  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a189b  nop
0x1800a189c  mov     rdx, rax
0x1800a189f  lea     rcx, [rbp+57h+var_40]
0x1800a18a3  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a18a9  mov     rcx, [rbp+57h+phProvider]; hObject
0x1800a18ad  test    rcx, rcx
0x1800a18b0  jz      short loc_1800A18B8
0x1800a18b2  call    cs:__imp_NCryptFreeObject
0x1800a18b8  mov     rax, rbx
0x1800a18bb  mov     rcx, [rbp+57h+var_20]
0x1800a18bf  xor     rcx, rsp; StackCookie
0x1800a18c2  call    __security_check_cookie
0x1800a18c7  mov     rbx, [rsp+0C0h+arg_10]
0x1800a18cf  add     rsp, 0B0h
0x1800a18d6  pop     rdi
0x1800a18d7  pop     rsi
0x1800a18d8  pop     rbp
0x1800a18d9  retn
```
