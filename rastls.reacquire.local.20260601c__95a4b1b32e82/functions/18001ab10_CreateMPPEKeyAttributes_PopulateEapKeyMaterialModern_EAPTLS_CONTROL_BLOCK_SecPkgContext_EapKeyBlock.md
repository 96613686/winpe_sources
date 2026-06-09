# CreateMPPEKeyAttributes_PopulateEapKeyMaterialModern(_EAPTLS_CONTROL_BLOCK *,_SecPkgContext_EapKeyBlock &)

- ea: `0x18001ab10`
- end: `0x18001af8a`
- name: `?CreateMPPEKeyAttributes_PopulateEapKeyMaterialModern@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@AEAU_SecPkgContext_EapKeyBlock@@@Z`
- size: `1146`
- prototype: `__int64 __fastcall(struct _EAPTLS_CONTROL_BLOCK *, struct _SecPkgContext_EapKeyBlock *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002ea48`

## callees

- `0x180007d00`
- `0x18001ab10`
- `0x180028420`
- `0x180028594`
- `0x18002f5e0`
- `0x1800356f4`
- `0x180038dca`
- `0x180038e4c`
- `0x18003ff44`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ad2c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ad93`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001aeba`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001af21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ad2c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001ad93`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001aeba`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001af21`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CreateMPPEKeyAttributes_PopulateEapKeyMaterialModern(
        struct _EAPTLS_CONTROL_BLOCK *a1,
        struct _SecPkgContext_EapKeyBlock *a2)
{
  int v4; // ebx
  __int64 v5; // rbx
  __int64 *v6; // rax
  __int64 v7; // rsi
  __int64 *v8; // rax
  int v9; // eax
  unsigned int v10; // eax
  size_t v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  const char *v15; // r9
  void *v16; // rax
  __int64 *v17; // rcx
  int v18; // eax
  void *v19; // rcx
  unsigned int v20; // eax
  size_t v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  void *v25; // rax
  __int64 result; // rax
  __int64 v27; // [rsp+20h] [rbp-58h] BYREF
  void *v28; // [rsp+28h] [rbp-50h] BYREF
  void *Src; // [rsp+30h] [rbp-48h] BYREF
  int v30; // [rsp+38h] [rbp-40h] BYREF
  __int128 v31; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  size_t Size; // [rsp+80h] [rbp+8h] BYREF
  void *v34; // [rsp+90h] [rbp+18h] BYREF
  __int64 v35; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(v34) = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_253d6767ad5c33bd246c71206321af56_Traceguids);
  v4 = 6;
  if ( (*((_DWORD *)a1 + 1) & 0x4000) == 0 )
    v4 = 3;
  LODWORD(Size) = v4;
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
    {
      LODWORD(Size) = v4;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_253d6767ad5c33bd246c71206321af56_Traceguids);
      v5 = 0;
      v27 = 0;
      LODWORD(v34) = 1;
      if ( (*((_BYTE *)a1 + 4) & 1) != 0 )
      {
        v6 = (__int64 *)winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(
                          (char *)a1 + 864,
                          &v35,
                          &Size);
        v7 = 0;
        if ( &v27 != v6 )
        {
          v5 = *v6;
          *v6 = 0;
          v27 = v5;
          v7 = v5;
        }
        if ( !v35 )
          goto LABEL_18;
      }
      else
      {
        v8 = (__int64 *)winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(
                          (char *)a1 + 856,
                          &v35,
                          &Size);
        v7 = 0;
        if ( &v27 != v8 )
        {
          v5 = *v8;
          *v8 = 0;
          v27 = v5;
          v7 = v5;
        }
        if ( !v35 )
        {
LABEL_18:
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_253d6767ad5c33bd246c71206321af56_Traceguids);
          LODWORD(Size) = 0;
          v30 = 0;
          v31 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v7 + 56LL))(v7, &Size);
          if ( v9 < 0 )
            winrt::throw_hresult((unsigned int)v9, &v30);
          Src = 0;
          v28 = 0;
          v30 = 0;
          v31 = 0;
          v10 = (**(__int64 (__fastcall ***)(__int64, __int64 *, void **))v7)(
                  v7,
                  winrt::impl::guid_v<winrt::impl::IBufferByteAccess>,
                  &v28);
          winrt::check_hresult(&v35, v10, &v30);
          v34 = v28;
          v11 = (unsigned int)Size;
          (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v28 + 24LL))(v28, &Src);
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v34);
          if ( v11 )
          {
            if ( !a2 )
              goto LABEL_24;
            v16 = Src;
            if ( Src && v11 <= 0x80 )
            {
              memcpy_0(a2, Src, v11);
              goto LABEL_32;
            }
            *(_OWORD *)a2->rgbKeys = 0;
            *(_OWORD *)&a2->rgbKeys[16] = 0;
            *(_OWORD *)&a2->rgbKeys[32] = 0;
            *(_OWORD *)&a2->rgbKeys[48] = 0;
            *(_OWORD *)&a2->rgbKeys[64] = 0;
            *(_OWORD *)&a2->rgbKeys[80] = 0;
            *(_OWORD *)&a2->rgbKeys[96] = 0;
            *(_OWORD *)&a2->rgbKeys[112] = 0;
            if ( v16 )
            {
              if ( v11 <= 0x80 )
                goto LABEL_32;
              *(_DWORD *)_o__errno(v13, v12, v14) = 34;
            }
            else
            {
LABEL_24:
              *(_DWORD *)_o__errno(v13, v12, v14) = 22;
            }
            invalid_parameter_noinfo();
          }
LABEL_32:
          if ( v5 )
          {
            v17 = &v27;
LABEL_51:
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v17);
            goto LABEL_52;
          }
          goto LABEL_52;
        }
      }
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v35);
      goto LABEL_18;
    }
    winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(
      (char *)a1 + 856,
      &v35,
      &Size);
    LODWORD(Size) = 0;
    v30 = 0;
    v31 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v35 + 56LL))(v35, &Size);
    if ( v18 < 0 )
      winrt::throw_hresult((unsigned int)v18, &v30);
    v28 = 0;
    if ( v35 )
    {
      Src = 0;
      v30 = 0;
      v31 = 0;
      v20 = (**(__int64 (__fastcall ***)(__int64, __int64 *, void **))v35)(
              v35,
              winrt::impl::guid_v<winrt::impl::IBufferByteAccess>,
              &Src);
      winrt::check_hresult(&v34, v20, &v30);
      v19 = Src;
      v34 = Src;
    }
    else
    {
      v34 = 0;
      v19 = 0;
    }
    v21 = (unsigned int)Size;
    (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v19 + 24LL))(v19, &v28);
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v34);
    if ( v21 )
    {
      if ( !a2 )
        goto LABEL_41;
      v25 = v28;
      if ( v28 && v21 <= 0x80 )
      {
        memcpy_0(a2, v28, v21);
        goto LABEL_49;
      }
      *(_OWORD *)a2->rgbKeys = 0;
      *(_OWORD *)&a2->rgbKeys[16] = 0;
      *(_OWORD *)&a2->rgbKeys[32] = 0;
      *(_OWORD *)&a2->rgbKeys[48] = 0;
      *(_OWORD *)&a2->rgbKeys[64] = 0;
      *(_OWORD *)&a2->rgbKeys[80] = 0;
      *(_OWORD *)&a2->rgbKeys[96] = 0;
      *(_OWORD *)&a2->rgbKeys[112] = 0;
      if ( v25 )
      {
        if ( v21 <= 0x80 )
          goto LABEL_49;
        *(_DWORD *)_o__errno(v23, v22, v24) = 34;
      }
      else
      {
LABEL_41:
        *(_DWORD *)_o__errno(v23, v22, v24) = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_49:
    if ( v35 )
    {
      v17 = &v35;
      goto LABEL_51;
    }
LABEL_52:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_253d6767ad5c33bd246c71206321af56_Traceguids);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(Size) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x337,
                      (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
                      v15);
    return (unsigned int)Size;
  }
  return result;
}

```

## disassembly

```asm
0x18001ab10  push    rbx
0x18001ab12  push    rsi
0x18001ab13  push    rdi
0x18001ab14  push    r14
0x18001ab16  push    r15
0x18001ab18  sub     rsp, 50h
0x18001ab1c  mov     rdi, rdx
0x18001ab1f  mov     rsi, rcx
0x18001ab22  xor     r14d, r14d
0x18001ab25  mov     dword ptr [rsp+78h+arg_10], r14d
0x18001ab2d  lea     r15, WPP_GLOBAL_Control
0x18001ab34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab3b  cmp     rcx, r15
0x18001ab3e  jz      short loc_18001AB55
0x18001ab40  mov     edx, 1Eh
0x18001ab45  lea     r8, WPP_253d6767ad5c33bd246c71206321af56_Traceguids
0x18001ab4c  mov     rcx, [rcx+10h]
0x18001ab50  call    WPP_SF_
0x18001ab55  test    dword ptr [rsi+4], 4000h
0x18001ab5c  mov     ebx, 6
0x18001ab61  mov     eax, 3
0x18001ab66  cmovz   ebx, eax
0x18001ab69  mov     dword ptr [rsp+78h+Size], ebx
0x18001ab70  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x18001ab77  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18001ab7c  test    al, al
0x18001ab7e  jz      loc_18001ADBE
0x18001ab84  mov     dword ptr [rsp+78h+Size], ebx
0x18001ab8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab92  cmp     rcx, r15
0x18001ab95  jz      short loc_18001ABAC
0x18001ab97  mov     edx, 1Ch
0x18001ab9c  lea     r8, WPP_253d6767ad5c33bd246c71206321af56_Traceguids
0x18001aba3  mov     rcx, [rcx+10h]
0x18001aba7  call    WPP_SF_
0x18001abac  mov     rbx, r14
0x18001abaf  mov     [rsp+78h+var_58], rbx
0x18001abb4  mov     dword ptr [rsp+78h+arg_10], 1
0x18001abbf  lea     r8, [rsp+78h+Size]
0x18001abc7  lea     rdx, [rsp+78h+arg_18]
0x18001abcf  test    byte ptr [rsi+4], 1
0x18001abd3  jz      short loc_18001AC09
0x18001abd5  lea     rcx, [rsi+360h]
0x18001abdc  call    ?ExportEapKeyMaterial@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4EapKeyMaterialType@Utility@Eap@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType const &)
0x18001abe1  mov     rsi, r14
0x18001abe4  lea     rcx, [rsp+78h+var_58]
0x18001abe9  cmp     rcx, rax
0x18001abec  jz      short loc_18001ABFC
0x18001abee  mov     rbx, [rax]
0x18001abf1  mov     [rax], r14
0x18001abf4  mov     [rsp+78h+var_58], rbx
0x18001abf9  mov     rsi, rbx
0x18001abfc  cmp     [rsp+78h+arg_18], 0
0x18001ac05  jnz     short loc_18001AC3B
0x18001ac07  jmp     short loc_18001AC48
0x18001ac09  lea     rcx, [rsi+358h]
0x18001ac10  call    ?ExportEapKeyMaterial@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4EapKeyMaterialType@Utility@Eap@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType const &)
0x18001ac15  mov     rsi, r14
0x18001ac18  lea     rcx, [rsp+78h+var_58]
0x18001ac1d  cmp     rcx, rax
0x18001ac20  jz      short loc_18001AC30
0x18001ac22  mov     rbx, [rax]
0x18001ac25  mov     [rax], r14
0x18001ac28  mov     [rsp+78h+var_58], rbx
0x18001ac2d  mov     rsi, rbx
0x18001ac30  cmp     [rsp+78h+arg_18], 0
0x18001ac39  jz      short loc_18001AC48
0x18001ac3b  lea     rcx, [rsp+78h+arg_18]
0x18001ac43  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001ac48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac4f  cmp     rcx, r15
0x18001ac52  jz      short loc_18001AC69
0x18001ac54  mov     edx, 1Dh
0x18001ac59  lea     r8, WPP_253d6767ad5c33bd246c71206321af56_Traceguids
0x18001ac60  mov     rcx, [rcx+10h]
0x18001ac64  call    WPP_SF_
0x18001ac69  mov     dword ptr [rsp+78h+Size], r14d
0x18001ac71  mov     [rsp+78h+var_40], r14d
0x18001ac76  xorps   xmm0, xmm0
0x18001ac79  movdqu  [rsp+78h+var_38], xmm0
0x18001ac7f  mov     rax, [rsi]
0x18001ac82  lea     rdx, [rsp+78h+Size]
0x18001ac8a  mov     rcx, rsi
0x18001ac8d  mov     rax, [rax+38h]
0x18001ac91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac96  test    eax, eax
0x18001ac98  jns     short loc_18001ACA6
0x18001ac9a  lea     rdx, [rsp+78h+var_40]
0x18001ac9f  mov     ecx, eax
0x18001aca1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001aca6  mov     [rsp+78h+Src], r14
0x18001acab  mov     [rsp+78h+var_50], r14
0x18001acb0  mov     [rsp+78h+var_40], r14d
0x18001acb5  xorps   xmm0, xmm0
0x18001acb8  movdqu  [rsp+78h+var_38], xmm0
0x18001acbe  mov     rax, [rsi]
0x18001acc1  lea     r8, [rsp+78h+var_50]
0x18001acc6  lea     rdx, ??$guid_v@UIBufferByteAccess@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IBufferByteAccess>
0x18001accd  mov     rcx, rsi
0x18001acd0  mov     rax, [rax]
0x18001acd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acd8  lea     r8, [rsp+78h+var_40]
0x18001acdd  mov     edx, eax
0x18001acdf  lea     rcx, [rsp+78h+arg_18]
0x18001ace7  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001acec  mov     rcx, [rsp+78h+var_50]
0x18001acf1  mov     [rsp+78h+arg_10], rcx
0x18001acf9  mov     esi, dword ptr [rsp+78h+Size]
0x18001ad00  mov     rax, [rcx]
0x18001ad03  lea     rdx, [rsp+78h+Src]
0x18001ad08  mov     rax, [rax+18h]
0x18001ad0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad11  lea     rcx, [rsp+78h+arg_10]
0x18001ad19  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001ad1e  test    rsi, rsi
0x18001ad21  jz      loc_18001ADAB
0x18001ad27  test    rdi, rdi
0x18001ad2a  jnz     short loc_18001AD40
0x18001ad2c  call    cs:__imp__o__errno
0x18001ad33  nop     dword ptr [rax+rax+00h]
0x18001ad38  mov     dword ptr [rax], 16h
0x18001ad3e  jmp     short loc_18001ADA5
0x18001ad40  mov     rax, [rsp+78h+Src]
0x18001ad45  test    rax, rax
0x18001ad48  jz      short loc_18001AD63
0x18001ad4a  cmp     rsi, 80h
0x18001ad51  ja      short loc_18001AD63
0x18001ad53  mov     r8, rsi; Size
0x18001ad56  mov     rdx, rax; Src
0x18001ad59  mov     rcx, rdi; void *
0x18001ad5c  call    memcpy_0
0x18001ad61  jmp     short loc_18001ADAB
0x18001ad63  xorps   xmm0, xmm0
0x18001ad66  movups  xmmword ptr [rdi], xmm0
0x18001ad69  movups  xmmword ptr [rdi+10h], xmm0
0x18001ad6d  movups  xmmword ptr [rdi+20h], xmm0
0x18001ad71  movups  xmmword ptr [rdi+30h], xmm0
0x18001ad75  movups  xmmword ptr [rdi+40h], xmm0
0x18001ad79  movups  xmmword ptr [rdi+50h], xmm0
0x18001ad7d  movups  xmmword ptr [rdi+60h], xmm0
0x18001ad81  movups  xmmword ptr [rdi+70h], xmm0
0x18001ad85  test    rax, rax
0x18001ad88  jz      short loc_18001AD2C
0x18001ad8a  cmp     rsi, 80h
0x18001ad91  jbe     short loc_18001ADAB
0x18001ad93  call    cs:__imp__o__errno
0x18001ad9a  nop     dword ptr [rax+rax+00h]
0x18001ad9f  mov     dword ptr [rax], 22h ; '"'
0x18001ada5  call    _invalid_parameter_noinfo
0x18001adaa  nop
0x18001adab  test    rbx, rbx
0x18001adae  jz      loc_18001AF51
0x18001adb4  lea     rcx, [rsp+78h+var_58]
0x18001adb9  jmp     loc_18001AF4C
0x18001adbe  lea     rcx, [rsi+358h]
0x18001adc5  lea     r8, [rsp+78h+Size]
0x18001adcd  lea     rdx, [rsp+78h+arg_18]
0x18001add5  call    ?ExportEapKeyMaterial@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4EapKeyMaterialType@Utility@Eap@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType const &)
0x18001adda  nop
0x18001addb  mov     dword ptr [rsp+78h+Size], r14d
0x18001ade3  mov     rcx, [rsp+78h+arg_18]
0x18001adeb  mov     [rsp+78h+var_40], r14d
0x18001adf0  xorps   xmm0, xmm0
0x18001adf3  movdqu  [rsp+78h+var_38], xmm0
0x18001adf9  mov     rax, [rcx]
0x18001adfc  lea     rdx, [rsp+78h+Size]
0x18001ae04  mov     rax, [rax+38h]
0x18001ae08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae0d  test    eax, eax
0x18001ae0f  jns     short loc_18001AE1D
0x18001ae11  lea     rdx, [rsp+78h+var_40]
0x18001ae16  mov     ecx, eax
0x18001ae18  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ae1d  mov     [rsp+78h+var_50], r14
0x18001ae22  mov     rcx, [rsp+78h+arg_18]
0x18001ae2a  test    rcx, rcx
0x18001ae2d  jnz     short loc_18001AE3C
0x18001ae2f  mov     [rsp+78h+arg_10], r14
0x18001ae37  mov     rcx, r14
0x18001ae3a  jmp     short loc_18001AE87
0x18001ae3c  mov     [rsp+78h+Src], r14
0x18001ae41  mov     [rsp+78h+var_40], r14d
0x18001ae46  xorps   xmm0, xmm0
0x18001ae49  movdqu  [rsp+78h+var_38], xmm0
0x18001ae4f  mov     rax, [rcx]
0x18001ae52  lea     r8, [rsp+78h+Src]
0x18001ae57  lea     rdx, ??$guid_v@UIBufferByteAccess@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IBufferByteAccess>
0x18001ae5e  mov     rax, [rax]
0x18001ae61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae66  lea     r8, [rsp+78h+var_40]
0x18001ae6b  mov     edx, eax
0x18001ae6d  lea     rcx, [rsp+78h+arg_10]
0x18001ae75  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001ae7a  mov     rcx, [rsp+78h+Src]
0x18001ae7f  mov     [rsp+78h+arg_10], rcx
0x18001ae87  mov     ebx, dword ptr [rsp+78h+Size]
0x18001ae8e  mov     rax, [rcx]
0x18001ae91  lea     rdx, [rsp+78h+var_50]
0x18001ae96  mov     rax, [rax+18h]
0x18001ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae9f  lea     rcx, [rsp+78h+arg_10]
0x18001aea7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001aeac  test    rbx, rbx
0x18001aeaf  jz      loc_18001AF39
0x18001aeb5  test    rdi, rdi
0x18001aeb8  jnz     short loc_18001AECE
0x18001aeba  call    cs:__imp__o__errno
0x18001aec1  nop     dword ptr [rax+rax+00h]
0x18001aec6  mov     dword ptr [rax], 16h
0x18001aecc  jmp     short loc_18001AF33
0x18001aece  mov     rax, [rsp+78h+var_50]
0x18001aed3  test    rax, rax
0x18001aed6  jz      short loc_18001AEF1
0x18001aed8  cmp     rbx, 80h
0x18001aedf  ja      short loc_18001AEF1
0x18001aee1  mov     r8, rbx; Size
0x18001aee4  mov     rdx, rax; Src
0x18001aee7  mov     rcx, rdi; void *
0x18001aeea  call    memcpy_0
0x18001aeef  jmp     short loc_18001AF39
0x18001aef1  xorps   xmm0, xmm0
0x18001aef4  movups  xmmword ptr [rdi], xmm0
0x18001aef7  movups  xmmword ptr [rdi+10h], xmm0
0x18001aefb  movups  xmmword ptr [rdi+20h], xmm0
0x18001aeff  movups  xmmword ptr [rdi+30h], xmm0
0x18001af03  movups  xmmword ptr [rdi+40h], xmm0
0x18001af07  movups  xmmword ptr [rdi+50h], xmm0
0x18001af0b  movups  xmmword ptr [rdi+60h], xmm0
0x18001af0f  movups  xmmword ptr [rdi+70h], xmm0
0x18001af13  test    rax, rax
0x18001af16  jz      short loc_18001AEBA
0x18001af18  cmp     rbx, 80h
0x18001af1f  jbe     short loc_18001AF39
0x18001af21  call    cs:__imp__o__errno
0x18001af28  nop     dword ptr [rax+rax+00h]
0x18001af2d  mov     dword ptr [rax], 22h ; '"'
0x18001af33  call    _invalid_parameter_noinfo
0x18001af38  nop
0x18001af39  cmp     [rsp+78h+arg_18], 0
0x18001af42  jz      short loc_18001AF51
0x18001af44  lea     rcx, [rsp+78h+arg_18]
0x18001af4c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001af51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af58  cmp     rcx, r15
0x18001af5b  jz      short loc_18001AF72
0x18001af5d  mov     edx, 1Fh
0x18001af62  lea     r8, WPP_253d6767ad5c33bd246c71206321af56_Traceguids
0x18001af69  mov     rcx, [rcx+10h]
0x18001af6d  call    WPP_SF_
0x18001af72  xor     eax, eax
0x18001af74  jmp     short loc_18001AF7D
0x18001af76  mov     eax, dword ptr [rsp+78h+Size]
0x18001af7d  add     rsp, 50h
0x18001af81  pop     r15
0x18001af83  pop     r14
0x18001af85  pop     rdi
0x18001af86  pop     rsi
0x18001af87  pop     rbx
0x18001af88  retn
```
