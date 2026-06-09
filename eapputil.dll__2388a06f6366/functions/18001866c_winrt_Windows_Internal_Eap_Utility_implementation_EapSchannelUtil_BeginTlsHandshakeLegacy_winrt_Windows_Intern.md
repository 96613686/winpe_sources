# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::BeginTlsHandshakeLegacy(winrt::Windows::Internal::Eap::Utility::EapTlsVersionFlags,winrt::Windows::Internal::Eap::Utility::EapTlsCryptographicRestrictions,_CERT_CONTEXT const *)

- ea: `0x18001866c`
- end: `0x1800188e9`
- name: `?BeginTlsHandshakeLegacy@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXW4EapTlsVersionFlags@34567@W4EapTlsCryptographicRestrictions@34567@PEBU_CERT_CONTEXT@@@Z`
- size: `637`
- prototype: `void(__int64, char, int, ...)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018580`
- `0x180018b10`

## callees

- `0x180002b78`
- `0x180002bd8`
- `0x180004380`
- `0x1800101c4`
- `0x18001866c`
- `0x180018e1c`
- `0x180023af4`
- `0x180023b94`

## import_xrefs

- `SspiCli!AcquireCredentialsHandleW` at `0x180018842`
- `SspiCli!AcquireCredentialsHandleW` at `0x180018842`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001871d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001871d`

## string_xrefs

- `0x18001881b`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
void winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::BeginTlsHandshakeLegacy(
        __int64 a1,
        char a2,
        int a3,
        ...)
{
  char IsEnabled; // al
  int v7; // r9d
  bool v8; // zf
  bool v9; // al
  bool v10; // si
  int v11; // eax
  SECURITY_STATUS v12; // eax
  unsigned int v13; // eax
  int pAuthData; // [rsp+28h] [rbp-69h]
  int pAuthDataa; // [rsp+28h] [rbp-69h]
  int v16; // [rsp+58h] [rbp-39h] BYREF
  __int128 v17; // [rsp+60h] [rbp-31h] BYREF
  __int128 v18; // [rsp+70h] [rbp-21h]
  __int64 v19; // [rsp+80h] [rbp-11h]
  int v20[4]; // [rsp+88h] [rbp-9h] BYREF
  va_list v21; // [rsp+98h] [rbp+7h]
  int v22; // [rsp+BCh] [rbp+2Bh]
  int v23; // [rsp+C0h] [rbp+2Fh]
  __int128 *v24; // [rsp+C8h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]
  __int64 v26; // [rsp+110h] [rbp+7Fh] BYREF
  va_list va; // [rsp+110h] [rbp+7Fh]
  va_list va1; // [rsp+118h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v26 = va_arg(va1, _QWORD);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl);
  v7 = *(_DWORD *)(a1 + 76);
  if ( IsEnabled )
  {
    if ( v7 )
    {
      v8 = v7 == 3;
      if ( v7 != 3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)0x8007139FLL,
          pAuthData);
    }
    else
    {
      v8 = 0;
    }
    v9 = v8;
  }
  else
  {
    v9 = 0;
    if ( v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)0x8007139FLL,
        pAuthData);
  }
  *(_DWORD *)(a1 + 76) = 1;
  if ( !v9
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
  {
    memset_0(v20, 0, 0x48u);
    v20[0] = 5;
    v10 = 1;
    if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    {
      v16 = 1;
      if ( (int)PolicyManager_GetPolicyInt(L"Eap", L"AllowTLS1_3", &v16) >= 0 )
        v10 = v16 == 1;
    }
    v19 = 0;
    v17 = 0;
    v18 = 0;
    if ( v10 )
    {
      if ( *(_DWORD *)(a1 + 72)
        || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Tls13InTeap>::GetImpl'::`2'::impl) )
      {
        v11 = v18;
        goto LABEL_21;
      }
      v11 = v18 | 0x3000;
    }
    else
    {
      v11 = 12288;
    }
    LODWORD(v18) = v11;
LABEL_21:
    if ( (a2 & 1) != 0 )
    {
      v11 |= 0xC0u;
      LODWORD(v18) = v11;
    }
    if ( (a2 & 2) != 0 )
    {
      v11 |= 0x300u;
      LODWORD(v18) = v11;
    }
    if ( (a2 & 4) != 0 )
    {
      v11 |= 0xC00u;
      LODWORD(v18) = v11;
    }
    if ( (a2 & 8) != 0 )
      LODWORD(v18) = v11 | 0x3000;
    if ( a3 )
    {
      if ( a3 != 1 )
      {
        v13 = wil::verify_hresult<long>(0x80070057);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x140,
          (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
          (const char *)v13,
          pAuthData);
      }
      DWORD1(v18) = 16;
      *((_QWORD *)&v18 + 1) = &g_wpa3SuiteBDisabledCrypto;
    }
    v24 = &v17;
    v23 = 1;
    v22 = 7192;
    if ( v26 )
    {
      v20[2] = 1;
      va_copy(v21, va);
    }
    v12 = AcquireCredentialsHandleW(
            0,
            (LPWSTR)L"Microsoft Unified Security Protocol Provider",
            2u,
            0,
            v20,
            0,
            0,
            (PCredHandle)(a1 + 104),
            0);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)(unsigned int)v12,
        pAuthDataa);
  }
  winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CommonTlsHandshakeLoop(
    (winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *)a1,
    0,
    (struct _SecHandle *const)(a1 + 120),
    0);
}

```

## disassembly

```asm
0x18001866c  mov     rax, rsp
0x18001866f  mov     [rax+8], rbx
0x180018673  mov     [rax+10h], rsi
0x180018677  mov     [rax+20h], r9
0x18001867b  push    rbp
0x18001867c  push    rdi
0x18001867d  push    r14
0x18001867f  lea     rbp, [rax-5Fh]
0x180018683  sub     rsp, 0D0h
0x18001868a  mov     edi, r8d
0x18001868d  mov     r14d, edx
0x180018690  mov     rbx, rcx
0x180018693  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18001869a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18001869f  mov     r9d, [rbx+4Ch]
0x1800186a3  test    al, al
0x1800186a5  jz      loc_18001874F
0x1800186ab  test    r9d, r9d
0x1800186ae  jz      short loc_1800186BC
0x1800186b0  cmp     r9d, 3
0x1800186b4  jnz     loc_18001888E
0x1800186ba  jmp     short loc_1800186C0
0x1800186bc  cmp     r9d, 3
0x1800186c0  setz    al
0x1800186c3  mov     dword ptr [rbx+4Ch], 1
0x1800186ca  test    al, al
0x1800186cc  jz      short loc_1800186E2
0x1800186ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x1800186d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x1800186da  test    al, al
0x1800186dc  jnz     loc_18001884C
0x1800186e2  xor     edx, edx; Val
0x1800186e4  lea     rcx, [rbp+57h+var_60]; void *
0x1800186e8  lea     r8d, [rdx+48h]; Size
0x1800186ec  call    memset_0
0x1800186f1  mov     [rbp+57h+var_60], 5
0x1800186f8  mov     sil, 1
0x1800186fb  call    IsPolicyManager_GetPolicyIntPresent
0x180018700  test    al, al
0x180018702  jz      short loc_18001872F
0x180018704  lea     r8, [rbp+57h+var_90]
0x180018708  mov     [rbp+57h+var_90], 1
0x18001870f  lea     rdx, aAllowtls13; "AllowTLS1_3"
0x180018716  lea     rcx, aEap; "Eap"
0x18001871d  call    cs:__imp_PolicyManager_GetPolicyInt
0x180018723  test    eax, eax
0x180018725  js      short loc_18001872F
0x180018727  cmp     [rbp+57h+var_90], 1
0x18001872b  setz    sil
0x18001872f  xor     eax, eax
0x180018731  xorps   xmm0, xmm0
0x180018734  mov     [rbp+57h+var_68], rax
0x180018738  movups  [rbp+57h+var_88], xmm0
0x18001873c  movups  [rbp+57h+var_78], xmm0
0x180018740  test    sil, sil
0x180018743  jnz     short loc_18001875F
0x180018745  mov     eax, 3000h
0x18001874a  mov     dword ptr [rbp+57h+var_78], eax
0x18001874d  jmp     short loc_180018781
0x18001874f  xor     al, al
0x180018751  test    r9d, r9d
0x180018754  jnz     loc_1800188AA
0x18001875a  jmp     loc_1800186C3
0x18001875f  cmp     [rbx+48h], eax
0x180018762  jnz     short loc_18001877E
0x180018764  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Tls13InTeap@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Tls13InTeap@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap> `wil::Feature<__WilFeatureTraits_Feature_Tls13InTeap>::GetImpl(void)'::`2'::impl
0x18001876b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Tls13InTeap@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap>::__private_IsEnabled(void)
0x180018770  test    al, al
0x180018772  jnz     short loc_18001877E
0x180018774  mov     eax, dword ptr [rbp+57h+var_78]
0x180018777  or      eax, 3000h
0x18001877c  jmp     short loc_18001874A
0x18001877e  mov     eax, dword ptr [rbp+57h+var_78]
0x180018781  test    r14b, 1
0x180018785  jz      short loc_18001878F
0x180018787  or      eax, 0C0h
0x18001878c  mov     dword ptr [rbp+57h+var_78], eax
0x18001878f  mov     r8d, 2; fCredentialUse
0x180018795  test    r8b, r14b
0x180018798  jz      short loc_1800187A2
0x18001879a  or      eax, 300h
0x18001879f  mov     dword ptr [rbp+57h+var_78], eax
0x1800187a2  test    r14b, 4
0x1800187a6  jz      short loc_1800187B0
0x1800187a8  or      eax, 0C00h
0x1800187ad  mov     dword ptr [rbp+57h+var_78], eax
0x1800187b0  test    r14b, 8
0x1800187b4  jz      short loc_1800187BE
0x1800187b6  or      eax, 3000h
0x1800187bb  mov     dword ptr [rbp+57h+var_78], eax
0x1800187be  test    edi, edi
0x1800187c0  jz      short loc_1800187DD
0x1800187c2  cmp     edi, 1
0x1800187c5  jnz     loc_1800188C6
0x1800187cb  lea     rax, ?g_wpa3SuiteBDisabledCrypto@@3PAU_CRYPTO_SETTINGS@@A; _CRYPTO_SETTINGS near * g_wpa3SuiteBDisabledCrypto
0x1800187d2  mov     dword ptr [rbp+57h+var_78+4], 10h
0x1800187d9  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800187dd  cmp     [rbp+57h+arg_18], 0
0x1800187e2  lea     rax, [rbp+57h+var_88]
0x1800187e6  mov     [rbp+57h+var_20], rax
0x1800187ea  mov     [rbp+57h+var_28], 1
0x1800187f1  mov     [rbp+57h+var_2C], 1C18h
0x1800187f8  jz      short loc_180018809
0x1800187fa  lea     rax, [rbp+57h+arg_18]
0x1800187fe  mov     [rbp+57h+var_58], 1
0x180018805  mov     [rbp+57h+var_50], rax
0x180018809  mov     [rsp+0E0h+ptsExpiry], 0; ptsExpiry
0x180018812  lea     rax, [rbx+68h]
0x180018816  mov     [rsp+0E0h+phCredential], rax; phCredential
0x18001881b  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x180018822  mov     [rsp+0E0h+pvGetKeyArgument], 0; pvGetKeyArgument
0x18001882b  lea     rax, [rbp+57h+var_60]
0x18001882f  mov     [rsp+0E0h+pGetKeyFn], 0; pGetKeyFn
0x180018838  xor     r9d, r9d; pvLogonId
0x18001883b  xor     ecx, ecx; pszPrincipal
0x18001883d  mov     [rsp+0E0h+pAuthData], rax; int
0x180018842  call    cs:__imp_AcquireCredentialsHandleW
0x180018848  test    eax, eax
0x18001884a  js      short loc_180018875
0x18001884c  lea     r8, [rbx+78h]; struct _SecHandle *
0x180018850  xor     r9d, r9d; struct _SecBufferDesc *
0x180018853  xor     edx, edx; struct _SecHandle *
0x180018855  mov     rcx, rbx; this
0x180018858  call    ?CommonTlsHandshakeLoop@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXQEAU_SecHandle@@0QEAU_SecBufferDesc@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::CommonTlsHandshakeLoop(_SecHandle * const,_SecHandle * const,_SecBufferDesc * const)
0x18001885d  lea     r11, [rsp+0E0h+var_10]
0x180018865  mov     rbx, [r11+20h]
0x180018869  mov     rsi, [r11+28h]
0x18001886d  mov     rsp, r11
0x180018870  pop     r14
0x180018872  pop     rdi
0x180018873  pop     rbp
0x180018874  retn
0x180018875  mov     rcx, [rbp+5Fh]; this
0x180018879  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180018880  mov     r9d, eax; char *
0x180018883  mov     edx, 14Fh; void *
0x180018888  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001888e  mov     rcx, [rbp+5Fh]; this
0x180018892  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180018899  mov     r9d, 8007139Fh; char *
0x18001889f  mov     edx, 0F8h; void *
0x1800188a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188aa  mov     rcx, [rbp+5Fh]; this
0x1800188ae  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800188b5  mov     r9d, 8007139Fh; char *
0x1800188bb  mov     edx, 101h; void *
0x1800188c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188c6  mov     ecx, 80070057h
0x1800188cb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800188d0  mov     rcx, [rbp+5Fh]; this
0x1800188d4  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800188db  mov     r9d, eax; char *
0x1800188de  mov     edx, 140h; void *
0x1800188e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
