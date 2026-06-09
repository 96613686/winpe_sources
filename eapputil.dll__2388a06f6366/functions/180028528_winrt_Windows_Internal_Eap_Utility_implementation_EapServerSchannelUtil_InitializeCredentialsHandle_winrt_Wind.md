# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::InitializeCredentialsHandle(winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions const &)

- ea: `0x180028528`
- end: `0x180028824`
- name: `?InitializeCredentialsHandle@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBUEapTlsHandshakeOptions@34567@@Z`
- size: `764`
- prototype: `void __fastcall(struct _SecHandle *this, const struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002647c`

## callees

- `0x180002b78`
- `0x180002bd8`
- `0x180004380`
- `0x1800101c4`
- `0x180010e04`
- `0x180018d08`
- `0x180019d04`
- `0x18001a180`
- `0x180023760`
- `0x180028528`
- `0x180028ce0`
- `0x180033010`

## import_xrefs

- `SspiCli!AcquireCredentialsHandleW` at `0x18002877c`
- `SspiCli!AcquireCredentialsHandleW` at `0x18002877c`
- `CRYPT32!CertCloseStore` at `0x1800287b1`
- `CRYPT32!CertCloseStore` at `0x1800287b1`
- `CRYPT32!CertOpenStore` at `0x180028722`
- `CRYPT32!CertOpenStore` at `0x180028722`
- `msvcp_win!_Xtime_get_ticks` at `0x18002878a`
- `msvcp_win!_Xtime_get_ticks` at `0x18002878a`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180028589`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180028589`

## string_xrefs

- `0x180028773`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::InitializeCredentialsHandle(
        struct _SecHandle *this,
        const struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *a2)
{
  bool v4; // bl
  char v5; // r8
  int v6; // ecx
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  char v13; // di
  int v14; // edx
  int v15; // ecx
  void *v16; // rbx
  HCERTSTORE v17; // rax
  const char *v18; // r9
  SECURITY_STATUS v19; // eax
  __int64 ticks; // rax
  unsigned int v21; // eax
  int pvPara; // [rsp+20h] [rbp-89h]
  int pvParaa; // [rsp+20h] [rbp-89h]
  __int128 v24; // [rsp+50h] [rbp-59h] BYREF
  __int128 v25; // [rsp+60h] [rbp-49h]
  __int64 v26; // [rsp+70h] [rbp-39h]
  int v27; // [rsp+78h] [rbp-31h] BYREF
  __int128 v28; // [rsp+80h] [rbp-29h]
  _DWORD pAuthData[4]; // [rsp+90h] [rbp-19h] BYREF
  __int64 *v30; // [rsp+A0h] [rbp-9h]
  HCERTSTORE v31; // [rsp+A8h] [rbp-1h]
  int v32; // [rsp+C4h] [rbp+1Bh]
  int v33; // [rsp+C8h] [rbp+1Fh]
  __int128 *v34; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  HCERTSTORE v36; // [rsp+120h] [rbp+77h] BYREF
  __int64 v37; // [rsp+128h] [rbp+7Fh] BYREF

  winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::ReleaseSecurityHandles((winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *)this);
  memset_0(pAuthData, 0, 0x48u);
  pAuthData[0] = 5;
  v4 = 1;
  if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
  {
    LODWORD(v36) = 1;
    if ( (int)PolicyManager_GetPolicyInt(L"Eap", L"AllowTLS1_3", &v36) >= 0 )
      v4 = (_DWORD)v36 == 1;
  }
  v5 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::DisabledTlsVersions(a2);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v6 = _mm_cvtsi128_si32((__m128i)0LL);
  if ( !v4 )
    v6 = 12288;
  LODWORD(v25) = v6;
  v7 = (!v4 ? 0x3000 : 0) | 0xC0;
  if ( (v5 & 1) != 0 )
    LODWORD(v25) = (!v4 ? 0x3000 : 0) | 0xC0;
  else
    v7 = !v4 ? 0x3000 : 0;
  v8 = v7 | 0x300;
  if ( (v5 & 2) != 0 )
    LODWORD(v25) = v7 | 0x300;
  else
    v8 = v7;
  v9 = v8 | 0xC00;
  if ( (v5 & 4) != 0 )
    LODWORD(v25) = v8 | 0xC00;
  else
    v9 = v8;
  if ( (v5 & 8) != 0 )
    LODWORD(v25) = v9 | 0x3000;
  v10 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CryptographicRestrictions(a2);
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      v21 = wil::verify_hresult<long>(0x80070057);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        (const char *)v21,
        pvPara);
    }
    DWORD1(v25) = 16;
    *((_QWORD *)&v25 + 1) = &g_wpa3SuiteBDisabledCrypto;
  }
  LODWORD(v36) = 0;
  v11 = *(_QWORD *)a2;
  v27 = 0;
  v28 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, HCERTSTORE *))(*(_QWORD *)v11 + 48LL))(v11, &v36);
  if ( v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v27);
  v13 = (char)v36;
  v14 = 0;
  if ( ((unsigned __int8)v36 & 0x40) == 0 )
  {
    v14 = ((char)v36 < 0 ? 1024 : 512) | 0x800;
    if ( ((unsigned __int16)v36 & 0x100) == 0 )
      v14 = (char)v36 < 0 ? 1024 : 512;
    if ( ((unsigned __int16)v36 & 0x200) != 0 )
      v14 |= 0x1000u;
  }
  if ( LODWORD(this[1].dwUpper) != 3 && ((unsigned __int8)v36 & 0x20) != 0 )
    v14 |= 2u;
  v33 = 1;
  v34 = &v24;
  v15 = v14 | 0xC800;
  if ( ((unsigned __int8)v36 & 8) == 0 )
    v15 = v14;
  v32 = v15;
  v37 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CertificateContext(a2);
  if ( v37 )
  {
    pAuthData[2] = 1;
    v30 = &v37;
  }
  v16 = 0;
  v36 = 0;
  if ( (v13 & 0x10) != 0 )
  {
    v17 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"EAPServerCustomRootStore");
    v16 = v17;
    v36 = v17;
    if ( !v17 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x12A,
        (int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        v18);
    v31 = v17;
  }
  v19 = AcquireCredentialsHandleW(
          0,
          (LPWSTR)L"Microsoft Unified Security Protocol Provider",
          1u,
          0,
          pAuthData,
          0,
          0,
          this + 3,
          0);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      (const char *)(unsigned int)v19,
      pvParaa);
  ticks = _Xtime_get_ticks();
  if ( !LOBYTE(this[11].dwLower) )
    LOBYTE(this[11].dwLower) = 1;
  this[10].dwUpper = ticks;
  if ( v16 )
    CertCloseStore(v16, 0);
}

```

## disassembly

```asm
0x180028528  mov     [rsp-8+arg_0], rbx
0x18002852d  push    rbp
0x18002852e  push    rsi
0x18002852f  push    rdi
0x180028530  push    r12
0x180028532  push    r14
0x180028534  lea     rbp, [rsp-37h]
0x180028539  sub     rsp, 0E0h
0x180028540  mov     r14, rdx
0x180028543  mov     rsi, rcx
0x180028546  call    ?ReleaseSecurityHandles@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::ReleaseSecurityHandles(void)
0x18002854b  xor     edx, edx; Val
0x18002854d  lea     r8d, [rdx+48h]; Size
0x180028551  lea     rcx, [rbp+57h+pAuthData]; void *
0x180028555  call    memset_0
0x18002855a  mov     [rbp+57h+pAuthData], 5
0x180028561  mov     r12d, 1
0x180028567  mov     bl, r12b
0x18002856a  call    IsPolicyManager_GetPolicyIntPresent
0x18002856f  test    al, al
0x180028571  jz      short loc_18002859A
0x180028573  mov     dword ptr [rbp+57h+arg_10], r12d
0x180028577  lea     r8, [rbp+57h+arg_10]
0x18002857b  lea     rdx, aAllowtls13; "AllowTLS1_3"
0x180028582  lea     rcx, aEap; "Eap"
0x180028589  call    cs:__imp_PolicyManager_GetPolicyInt
0x18002858f  test    eax, eax
0x180028591  js      short loc_18002859A
0x180028593  cmp     dword ptr [rbp+57h+arg_10], r12d
0x180028597  setz    bl
0x18002859a  mov     rcx, r14
0x18002859d  call    ?DisabledTlsVersions@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::DisabledTlsVersions(void)
0x1800285a2  mov     r8d, eax
0x1800285a5  xorps   xmm0, xmm0
0x1800285a8  xor     eax, eax
0x1800285aa  movups  [rbp+57h+var_B0], xmm0
0x1800285ae  movups  [rbp+57h+var_A0], xmm0
0x1800285b2  mov     [rbp+57h+var_90], rax
0x1800285b6  movd    ecx, xmm0
0x1800285ba  mov     r9d, 3000h
0x1800285c0  test    bl, bl
0x1800285c2  cmovz   ecx, r9d
0x1800285c6  mov     dword ptr [rbp+57h+var_A0], ecx
0x1800285c9  neg     bl
0x1800285cb  sbb     ecx, ecx
0x1800285cd  not     ecx
0x1800285cf  and     ecx, r9d
0x1800285d2  mov     edx, r8d
0x1800285d5  mov     eax, ecx
0x1800285d7  or      eax, 0C0h
0x1800285dc  and     edx, r12d
0x1800285df  jz      short loc_1800285E4
0x1800285e1  mov     dword ptr [rbp+57h+var_A0], eax
0x1800285e4  test    edx, edx
0x1800285e6  cmovz   eax, ecx
0x1800285e9  mov     edx, r8d
0x1800285ec  mov     ecx, eax
0x1800285ee  or      ecx, 300h
0x1800285f4  and     edx, 2
0x1800285f7  jz      short loc_1800285FC
0x1800285f9  mov     dword ptr [rbp+57h+var_A0], ecx
0x1800285fc  test    edx, edx
0x1800285fe  cmovz   ecx, eax
0x180028601  mov     edx, r8d
0x180028604  mov     eax, ecx
0x180028606  or      eax, 0C00h
0x18002860b  and     edx, 4
0x18002860e  jz      short loc_180028613
0x180028610  mov     dword ptr [rbp+57h+var_A0], eax
0x180028613  test    edx, edx
0x180028615  cmovz   eax, ecx
0x180028618  test    r8b, 8
0x18002861c  jz      short loc_180028624
0x18002861e  or      eax, r9d
0x180028621  mov     dword ptr [rbp+57h+var_A0], eax
0x180028624  mov     rcx, r14
0x180028627  call    ?CryptographicRestrictions@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CryptographicRestrictions(void)
0x18002862c  test    eax, eax
0x18002862e  jz      short loc_18002864B
0x180028630  cmp     eax, r12d
0x180028633  jnz     loc_1800287E3
0x180028639  mov     dword ptr [rbp+57h+var_A0+4], 10h
0x180028640  lea     rax, ?g_wpa3SuiteBDisabledCrypto@@3PAU_CRYPTO_SETTINGS@@A; _CRYPTO_SETTINGS near * g_wpa3SuiteBDisabledCrypto
0x180028647  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18002864b  mov     dword ptr [rbp+57h+arg_10], 0
0x180028652  mov     rcx, [r14]
0x180028655  mov     [rbp+57h+var_88], 0
0x18002865c  xorps   xmm0, xmm0
0x18002865f  movdqu  [rbp+57h+var_80], xmm0
0x180028664  mov     rax, [rcx]
0x180028667  lea     rdx, [rbp+57h+arg_10]
0x18002866b  mov     rax, [rax+30h]
0x18002866f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028674  test    eax, eax
0x180028676  js      loc_180028806
0x18002867c  mov     edi, dword ptr [rbp+57h+arg_10]
0x18002867f  xor     edx, edx
0x180028681  test    dil, 40h
0x180028685  jnz     short loc_1800286B1
0x180028687  mov     eax, edi
0x180028689  and     al, 80h
0x18002868b  neg     al
0x18002868d  sbb     ecx, ecx
0x18002868f  mov     r8d, 200h
0x180028695  and     ecx, r8d
0x180028698  add     ecx, r8d
0x18002869b  mov     edx, ecx
0x18002869d  bts     edx, 0Bh
0x1800286a1  bt      edi, 8
0x1800286a5  cmovnb  edx, ecx
0x1800286a8  test    r8d, edi
0x1800286ab  jz      short loc_1800286B1
0x1800286ad  bts     edx, 0Ch
0x1800286b1  cmp     dword ptr [rsi+18h], 3
0x1800286b5  jz      short loc_1800286C0
0x1800286b7  test    dil, 20h
0x1800286bb  jz      short loc_1800286C0
0x1800286bd  or      edx, 2
0x1800286c0  mov     [rbp+57h+var_38], r12d
0x1800286c4  lea     rax, [rbp+57h+var_B0]
0x1800286c8  mov     [rbp+57h+var_30], rax
0x1800286cc  mov     ecx, edx
0x1800286ce  or      ecx, 0C800h
0x1800286d4  test    dil, 8
0x1800286d8  cmovz   ecx, edx
0x1800286db  mov     [rbp+57h+var_3C], ecx
0x1800286de  mov     rcx, r14
0x1800286e1  call    ?CertificateContext@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CertificateContext(void)
0x1800286e6  mov     [rbp+57h+arg_18], rax
0x1800286ea  test    rax, rax
0x1800286ed  jz      short loc_1800286FB
0x1800286ef  mov     [rbp+57h+var_68], r12d
0x1800286f3  lea     rax, [rbp+57h+arg_18]
0x1800286f7  mov     [rbp+57h+var_60], rax
0x1800286fb  xor     ebx, ebx
0x1800286fd  mov     [rbp+57h+arg_10], rbx
0x180028701  test    dil, 10h
0x180028705  jz      short loc_180028740
0x180028707  lea     rax, aEapservercusto; "EAPServerCustomRootStore"
0x18002870e  mov     [rsp+100h+pvPara], rax; pvPara
0x180028713  mov     r9d, 28000h; dwFlags
0x180028719  xor     r8d, r8d; hCryptProv
0x18002871c  mov     edx, r12d; dwEncodingType
0x18002871f  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x180028722  call    cs:__imp_CertOpenStore
0x180028728  mov     rbx, rax
0x18002872b  mov     [rbp+57h+arg_10], rax
0x18002872f  mov     rcx, [rbp+5Fh]; this
0x180028733  test    rax, rax
0x180028736  jz      loc_180028812
0x18002873c  mov     [rbp+57h+var_58], rax
0x180028740  lea     rax, [rsi+30h]
0x180028744  mov     [rsp+100h+ptsExpiry], 0; ptsExpiry
0x18002874d  mov     [rsp+100h+phCredential], rax; phCredential
0x180028752  mov     [rsp+100h+pvGetKeyArgument], 0; pvGetKeyArgument
0x18002875b  mov     [rsp+100h+pGetKeyFn], 0; pGetKeyFn
0x180028764  lea     rax, [rbp+57h+pAuthData]
0x180028768  mov     [rsp+100h+pvPara], rax; int
0x18002876d  xor     r9d, r9d; pvLogonId
0x180028770  mov     r8d, r12d; fCredentialUse
0x180028773  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x18002877a  xor     ecx, ecx; pszPrincipal
0x18002877c  call    cs:__imp_AcquireCredentialsHandleW
0x180028782  mov     rcx, [rbp+5Fh]; this
0x180028786  test    eax, eax
0x180028788  js      short loc_1800287CE
0x18002878a  call    cs:__imp__Xtime_get_ticks
0x180028790  cmp     byte ptr [rsi+0B0h], 0
0x180028797  jnz     short loc_1800287A0
0x180028799  mov     [rsi+0B0h], r12b
0x1800287a0  mov     [rsi+0A8h], rax
0x1800287a7  test    rbx, rbx
0x1800287aa  jz      short loc_1800287B7
0x1800287ac  xor     edx, edx; dwFlags
0x1800287ae  mov     rcx, rbx; hCertStore
0x1800287b1  call    cs:__imp_CertCloseStore
0x1800287b7  mov     rbx, [rsp+100h+arg_0]
0x1800287bf  add     rsp, 0E0h
0x1800287c6  pop     r14
0x1800287c8  pop     r12
0x1800287ca  pop     rdi
0x1800287cb  pop     rsi
0x1800287cc  pop     rbp
0x1800287cd  retn
0x1800287ce  mov     r9d, eax; char *
0x1800287d1  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800287d8  mov     edx, 12Fh; void *
0x1800287dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800287e3  mov     ecx, 80070057h
0x1800287e8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800287ed  mov     r9d, eax; char *
0x1800287f0  mov     rcx, [rbp+5Fh]; this
0x1800287f4  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800287fb  mov     edx, 113h; void *
0x180028800  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028806  lea     rdx, [rbp+57h+var_88]
0x18002880a  mov     ecx, eax
0x18002880c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028812  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180028819  mov     edx, 12Ah; void *
0x18002881e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
