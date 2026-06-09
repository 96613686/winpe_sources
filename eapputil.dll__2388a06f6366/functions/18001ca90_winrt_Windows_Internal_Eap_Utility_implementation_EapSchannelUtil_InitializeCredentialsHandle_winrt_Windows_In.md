# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::InitializeCredentialsHandle(winrt::Windows::Internal::Eap::Utility::EapTlsVersionFlags,winrt::Windows::Internal::Eap::Utility::EapTlsCryptographicRestrictions,_CERT_CONTEXT const *)

- ea: `0x18001ca90`
- end: `0x18001cc86`
- name: `?InitializeCredentialsHandle@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXW4EapTlsVersionFlags@34567@W4EapTlsCryptographicRestrictions@34567@PEBU_CERT_CONTEXT@@@Z`
- size: `502`
- prototype: `__int64(__int64, char, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800188f0`

## callees

- `0x180002b78`
- `0x180002bd8`
- `0x180004380`
- `0x1800101c4`
- `0x18001ca90`
- `0x18001dc94`
- `0x180023b94`

## import_xrefs

- `SspiCli!AcquireCredentialsHandleW` at `0x18001cc0b`
- `SspiCli!AcquireCredentialsHandleW` at `0x18001cc0b`
- `msvcp_win!_Xtime_get_ticks` at `0x18001cc15`
- `msvcp_win!_Xtime_get_ticks` at `0x18001cc15`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001caf6`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001caf6`

## string_xrefs

- `0x18001cbe4`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
__int64 winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::InitializeCredentialsHandle(
        __int64 a1,
        char a2,
        int a3,
        ...)
{
  bool v6; // r14
  int v7; // eax
  SECURITY_STATUS v8; // eax
  __int64 result; // rax
  unsigned int v10; // eax
  int pAuthData; // [rsp+28h] [rbp-69h]
  int pAuthDataa; // [rsp+28h] [rbp-69h]
  __int128 v13; // [rsp+58h] [rbp-39h] BYREF
  __int128 v14; // [rsp+68h] [rbp-29h]
  __int64 v15; // [rsp+78h] [rbp-19h]
  int v16[4]; // [rsp+88h] [rbp-9h] BYREF
  va_list v17; // [rsp+98h] [rbp+7h]
  int v18; // [rsp+BCh] [rbp+2Bh]
  int v19; // [rsp+C0h] [rbp+2Fh]
  __int128 *v20; // [rsp+C8h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]
  int v22; // [rsp+100h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+110h] [rbp+7Fh] BYREF
  va_list va; // [rsp+110h] [rbp+7Fh]
  va_list va1; // [rsp+118h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v23 = va_arg(va1, _QWORD);
  winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReleaseSecurityHandles((winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *)a1);
  memset_0(v16, 0, 0x48u);
  v16[0] = 5;
  v6 = 1;
  if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
  {
    v22 = 1;
    if ( (int)PolicyManager_GetPolicyInt(L"Eap", L"AllowTLS1_3", &v22) >= 0 )
      v6 = v22 == 1;
  }
  v15 = 0;
  v13 = 0;
  v14 = 0;
  if ( !v6 )
  {
    v7 = 12288;
LABEL_6:
    LODWORD(v14) = v7;
    goto LABEL_11;
  }
  if ( !*(_DWORD *)(a1 + 72)
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Tls13InTeap>::GetImpl'::`2'::impl) )
  {
    v7 = v14 | 0x3000;
    goto LABEL_6;
  }
  v7 = v14;
LABEL_11:
  if ( (a2 & 1) != 0 )
  {
    v7 |= 0xC0u;
    LODWORD(v14) = v7;
  }
  if ( (a2 & 2) != 0 )
  {
    v7 |= 0x300u;
    LODWORD(v14) = v7;
  }
  if ( (a2 & 4) != 0 )
  {
    v7 |= 0xC00u;
    LODWORD(v14) = v7;
  }
  if ( (a2 & 8) != 0 )
    LODWORD(v14) = v7 | 0x3000;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      v10 = wil::verify_hresult<long>(0x80070057);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
        (const char *)v10,
        pAuthData);
    }
    DWORD1(v14) = 16;
    *((_QWORD *)&v14 + 1) = &g_wpa3SuiteBDisabledCrypto;
  }
  v20 = &v13;
  v19 = 1;
  v18 = 7192;
  if ( v23 )
  {
    v16[2] = 1;
    va_copy(v17, va);
  }
  v8 = AcquireCredentialsHandleW(
         0,
         (LPWSTR)L"Microsoft Unified Security Protocol Provider",
         2u,
         0,
         v16,
         0,
         0,
         (PCredHandle)(a1 + 104),
         0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapschannelutil.cpp",
      (const char *)(unsigned int)v8,
      pAuthDataa);
  result = _Xtime_get_ticks();
  *(_QWORD *)(a1 + 200) = result;
  if ( !*(_BYTE *)(a1 + 208) )
    *(_BYTE *)(a1 + 208) = 1;
  return result;
}

```

## disassembly

```asm
0x18001ca90  mov     rax, rsp
0x18001ca93  mov     [rax+8], rbx
0x18001ca97  mov     [rax+18h], rsi
0x18001ca9b  mov     [rax+20h], r9
0x18001ca9f  push    rbp
0x18001caa0  push    rdi
0x18001caa1  push    r14
0x18001caa3  lea     rbp, [rax-5Fh]
0x18001caa7  sub     rsp, 0D0h
0x18001caae  mov     edi, r8d
0x18001cab1  mov     esi, edx
0x18001cab3  mov     rbx, rcx
0x18001cab6  call    ?ReleaseSecurityHandles@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReleaseSecurityHandles(void)
0x18001cabb  xor     edx, edx; Val
0x18001cabd  lea     rcx, [rbp+57h+var_60]; void *
0x18001cac1  lea     r8d, [rdx+48h]; Size
0x18001cac5  call    memset_0
0x18001caca  mov     [rbp+57h+var_60], 5
0x18001cad1  mov     r14b, 1
0x18001cad4  call    IsPolicyManager_GetPolicyIntPresent
0x18001cad9  test    al, al
0x18001cadb  jz      short loc_18001CB08
0x18001cadd  lea     r8, [rbp+57h+arg_8]
0x18001cae1  mov     [rbp+57h+arg_8], 1
0x18001cae8  lea     rdx, aAllowtls13; "AllowTLS1_3"
0x18001caef  lea     rcx, aEap; "Eap"
0x18001caf6  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001cafc  test    eax, eax
0x18001cafe  js      short loc_18001CB08
0x18001cb00  cmp     [rbp+57h+arg_8], 1
0x18001cb04  setz    r14b
0x18001cb08  xor     eax, eax
0x18001cb0a  xorps   xmm0, xmm0
0x18001cb0d  mov     [rbp+57h+var_70], rax
0x18001cb11  movups  [rbp+57h+var_90], xmm0
0x18001cb15  movups  [rbp+57h+var_80], xmm0
0x18001cb19  test    r14b, r14b
0x18001cb1c  jnz     short loc_18001CB28
0x18001cb1e  mov     eax, 3000h
0x18001cb23  mov     dword ptr [rbp+57h+var_80], eax
0x18001cb26  jmp     short loc_18001CB4A
0x18001cb28  cmp     [rbx+48h], eax
0x18001cb2b  jnz     short loc_18001CB47
0x18001cb2d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Tls13InTeap@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Tls13InTeap@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap> `wil::Feature<__WilFeatureTraits_Feature_Tls13InTeap>::GetImpl(void)'::`2'::impl
0x18001cb34  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Tls13InTeap@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap>::__private_IsEnabled(void)
0x18001cb39  test    al, al
0x18001cb3b  jnz     short loc_18001CB47
0x18001cb3d  mov     eax, dword ptr [rbp+57h+var_80]
0x18001cb40  or      eax, 3000h
0x18001cb45  jmp     short loc_18001CB23
0x18001cb47  mov     eax, dword ptr [rbp+57h+var_80]
0x18001cb4a  test    sil, 1
0x18001cb4e  jz      short loc_18001CB58
0x18001cb50  or      eax, 0C0h
0x18001cb55  mov     dword ptr [rbp+57h+var_80], eax
0x18001cb58  mov     r8d, 2; fCredentialUse
0x18001cb5e  test    r8b, sil
0x18001cb61  jz      short loc_18001CB6B
0x18001cb63  or      eax, 300h
0x18001cb68  mov     dword ptr [rbp+57h+var_80], eax
0x18001cb6b  test    sil, 4
0x18001cb6f  jz      short loc_18001CB79
0x18001cb71  or      eax, 0C00h
0x18001cb76  mov     dword ptr [rbp+57h+var_80], eax
0x18001cb79  test    sil, 8
0x18001cb7d  jz      short loc_18001CB87
0x18001cb7f  or      eax, 3000h
0x18001cb84  mov     dword ptr [rbp+57h+var_80], eax
0x18001cb87  test    edi, edi
0x18001cb89  jz      short loc_18001CBA6
0x18001cb8b  cmp     edi, 1
0x18001cb8e  jnz     loc_18001CC63
0x18001cb94  lea     rax, ?g_wpa3SuiteBDisabledCrypto@@3PAU_CRYPTO_SETTINGS@@A; _CRYPTO_SETTINGS near * g_wpa3SuiteBDisabledCrypto
0x18001cb9b  mov     dword ptr [rbp+57h+var_80+4], 10h
0x18001cba2  mov     qword ptr [rbp+57h+var_80+8], rax
0x18001cba6  cmp     [rbp+57h+arg_18], 0
0x18001cbab  lea     rax, [rbp+57h+var_90]
0x18001cbaf  mov     [rbp+57h+var_20], rax
0x18001cbb3  mov     [rbp+57h+var_28], 1
0x18001cbba  mov     [rbp+57h+var_2C], 1C18h
0x18001cbc1  jz      short loc_18001CBD2
0x18001cbc3  lea     rax, [rbp+57h+arg_18]
0x18001cbc7  mov     [rbp+57h+var_58], 1
0x18001cbce  mov     [rbp+57h+var_50], rax
0x18001cbd2  mov     [rsp+0E0h+ptsExpiry], 0; ptsExpiry
0x18001cbdb  lea     rax, [rbx+68h]
0x18001cbdf  mov     [rsp+0E0h+phCredential], rax; phCredential
0x18001cbe4  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x18001cbeb  mov     [rsp+0E0h+pvGetKeyArgument], 0; pvGetKeyArgument
0x18001cbf4  lea     rax, [rbp+57h+var_60]
0x18001cbf8  mov     [rsp+0E0h+pGetKeyFn], 0; pGetKeyFn
0x18001cc01  xor     r9d, r9d; pvLogonId
0x18001cc04  xor     ecx, ecx; pszPrincipal
0x18001cc06  mov     [rsp+0E0h+pAuthData], rax; int
0x18001cc0b  call    cs:__imp_AcquireCredentialsHandleW
0x18001cc11  test    eax, eax
0x18001cc13  js      short loc_18001CC4A
0x18001cc15  call    cs:__imp__Xtime_get_ticks
0x18001cc1b  mov     [rbx+0C8h], rax
0x18001cc22  cmp     byte ptr [rbx+0D0h], 0
0x18001cc29  jnz     short loc_18001CC32
0x18001cc2b  mov     byte ptr [rbx+0D0h], 1
0x18001cc32  lea     r11, [rsp+0E0h+var_10]
0x18001cc3a  mov     rbx, [r11+20h]
0x18001cc3e  mov     rsi, [r11+30h]
0x18001cc42  mov     rsp, r11
0x18001cc45  pop     r14
0x18001cc47  pop     rdi
0x18001cc48  pop     rbp
0x18001cc49  retn
0x18001cc4a  mov     rcx, [rbp+5Fh]; this
0x18001cc4e  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001cc55  mov     r9d, eax; char *
0x18001cc58  mov     edx, 1DBh; void *
0x18001cc5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001cc63  mov     ecx, 80070057h
0x18001cc68  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001cc6d  mov     rcx, [rbp+5Fh]; this
0x18001cc71  lea     r8, aOnecoreuapNetE_3; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18001cc78  mov     r9d, eax; char *
0x18001cc7b  mov     edx, 1CCh; void *
0x18001cc80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
