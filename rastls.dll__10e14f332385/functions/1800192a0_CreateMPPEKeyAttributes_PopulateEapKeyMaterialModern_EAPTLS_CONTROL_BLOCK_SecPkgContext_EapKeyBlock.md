# CreateMPPEKeyAttributes_PopulateEapKeyMaterialModern(_EAPTLS_CONTROL_BLOCK *,_SecPkgContext_EapKeyBlock &)

- ea: `0x1800192a0`
- end: `0x18001971e`
- name: `?CreateMPPEKeyAttributes_PopulateEapKeyMaterialModern@@YAJPEAU_EAPTLS_CONTROL_BLOCK@@AEAU_SecPkgContext_EapKeyBlock@@@Z`
- size: `1150`
- prototype: `int(struct _EAPTLS_CONTROL_BLOCK *, struct _SecPkgContext_EapKeyBlock *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002c44c`

## callees

- `0x1800075b0`
- `0x1800192a0`
- `0x18002689c`
- `0x180026a0c`
- `0x18002d048`
- `0x180032acc`
- `0x1800361ba`
- `0x18003623c`
- `0x18003cfdc`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800194bc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019514`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001952b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001964c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800196a4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800196bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800194bc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019514`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001952b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001964c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800196a4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800196bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v12; // rcx
  const char *v13; // r9
  void *v14; // rax
  __int64 *v15; // rcx
  int v16; // eax
  void *v17; // rcx
  unsigned int v18; // eax
  size_t v19; // rbx
  void *v20; // rax
  __int64 result; // rax
  __int64 v22; // [rsp+20h] [rbp-58h] BYREF
  void *v23; // [rsp+28h] [rbp-50h] BYREF
  void *Src; // [rsp+30h] [rbp-48h] BYREF
  int v25; // [rsp+38h] [rbp-40h] BYREF
  __int128 v26; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  size_t Size; // [rsp+80h] [rbp+8h] BYREF
  void *v29; // [rsp+90h] [rbp+18h] BYREF
  __int64 v30; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(v29) = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids);
      v5 = 0;
      v22 = 0;
      LODWORD(v29) = 1;
      if ( (*((_BYTE *)a1 + 4) & 1) != 0 )
      {
        v6 = (__int64 *)winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(
                          (char *)a1 + 864,
                          &v30,
                          &Size);
        v7 = 0;
        if ( &v22 != v6 )
        {
          v5 = *v6;
          *v6 = 0;
          v22 = v5;
          v7 = v5;
        }
        if ( !v30 )
          goto LABEL_18;
      }
      else
      {
        v8 = (__int64 *)winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(
                          (char *)a1 + 856,
                          &v30,
                          &Size);
        v7 = 0;
        if ( &v22 != v8 )
        {
          v5 = *v8;
          *v8 = 0;
          v22 = v5;
          v7 = v5;
        }
        if ( !v30 )
        {
LABEL_18:
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids);
          LODWORD(Size) = 0;
          v25 = 0;
          v26 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v7 + 56LL))(v7, &Size);
          if ( v9 < 0 )
            winrt::throw_hresult((unsigned int)v9, &v25);
          Src = 0;
          v23 = 0;
          v25 = 0;
          v26 = 0;
          v10 = (**(__int64 (__fastcall ***)(__int64, __int64 *, void **))v7)(
                  v7,
                  winrt::impl::guid_v<winrt::impl::IBufferByteAccess>,
                  &v23);
          winrt::check_hresult(&v30, v10, &v25);
          v29 = v23;
          v11 = (unsigned int)Size;
          (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v23 + 24LL))(v23, &Src);
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v29);
          if ( v11 )
          {
            if ( !a2 )
              goto LABEL_24;
            v14 = Src;
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
            if ( v14 )
            {
              if ( v11 <= 0x80 )
                goto LABEL_32;
              *(_DWORD *)_o__errno(v12) = 34;
            }
            else
            {
LABEL_24:
              *(_DWORD *)_o__errno(v12) = 22;
            }
            invalid_parameter_noinfo();
          }
LABEL_32:
          if ( v5 )
          {
            v15 = &v22;
LABEL_51:
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v15);
            goto LABEL_52;
          }
          goto LABEL_52;
        }
      }
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
      goto LABEL_18;
    }
    winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(
      (char *)a1 + 856,
      &v30,
      &Size);
    LODWORD(Size) = 0;
    v25 = 0;
    v26 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v30 + 56LL))(v30, &Size);
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, &v25);
    v23 = 0;
    if ( v30 )
    {
      Src = 0;
      v25 = 0;
      v26 = 0;
      v18 = (**(__int64 (__fastcall ***)(__int64, __int64 *, void **))v30)(
              v30,
              winrt::impl::guid_v<winrt::impl::IBufferByteAccess>,
              &Src);
      winrt::check_hresult(&v29, v18, &v25);
      v17 = Src;
      v29 = Src;
    }
    else
    {
      v29 = 0;
      v17 = 0;
    }
    v19 = (unsigned int)Size;
    (*(void (__fastcall **)(void *, void **))(*(_QWORD *)v17 + 24LL))(v17, &v23);
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v29);
    if ( v19 )
    {
      if ( !a2 )
        goto LABEL_41;
      v20 = v23;
      if ( v23 && v19 <= 0x80 )
      {
        memcpy_0(a2, v23, v19);
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
      if ( v20 )
      {
        if ( v19 <= 0x80 )
          goto LABEL_49;
        *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
      }
      else
      {
LABEL_41:
        *(_DWORD *)((__int64 (*)(void))_o__errno)() = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_49:
    if ( v30 )
    {
      v15 = &v30;
      goto LABEL_51;
    }
LABEL_52:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(Size) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x34A,
                      (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptls\\moderntlsstackeaptls.cpp",
                      v13);
    return (unsigned int)Size;
  }
  return result;
}

```

## disassembly

```asm
0x1800192a0  push    rbx
0x1800192a2  push    rsi
0x1800192a3  push    rdi
0x1800192a4  push    r14
0x1800192a6  push    r15
0x1800192a8  sub     rsp, 50h
0x1800192ac  mov     rdi, rdx
0x1800192af  mov     rsi, rcx
0x1800192b2  xor     r14d, r14d
0x1800192b5  mov     dword ptr [rsp+78h+arg_10], r14d
0x1800192bd  lea     r15, WPP_GLOBAL_Control
0x1800192c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192cb  cmp     rcx, r15
0x1800192ce  jz      short loc_1800192E5
0x1800192d0  mov     edx, 1Eh
0x1800192d5  lea     r8, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids
0x1800192dc  mov     rcx, [rcx+10h]
0x1800192e0  call    WPP_SF_
0x1800192e5  test    dword ptr [rsi+4], 4000h
0x1800192ec  mov     ebx, 6
0x1800192f1  mov     eax, 3
0x1800192f6  cmovz   ebx, eax
0x1800192f9  mov     dword ptr [rsp+78h+Size], ebx
0x180019300  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x180019307  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x18001930c  test    al, al
0x18001930e  jz      loc_180019550
0x180019314  mov     dword ptr [rsp+78h+Size], ebx
0x18001931b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019322  cmp     rcx, r15
0x180019325  jz      short loc_18001933C
0x180019327  mov     edx, 1Ch
0x18001932c  lea     r8, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids
0x180019333  mov     rcx, [rcx+10h]
0x180019337  call    WPP_SF_
0x18001933c  mov     rbx, r14
0x18001933f  mov     [rsp+78h+var_58], rbx
0x180019344  mov     dword ptr [rsp+78h+arg_10], 1
0x18001934f  lea     r8, [rsp+78h+Size]
0x180019357  lea     rdx, [rsp+78h+arg_18]
0x18001935f  test    byte ptr [rsi+4], 1
0x180019363  jz      short loc_180019399
0x180019365  lea     rcx, [rsi+360h]
0x18001936c  call    ?ExportEapKeyMaterial@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4EapKeyMaterialType@Utility@Eap@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType const &)
0x180019371  mov     rsi, r14
0x180019374  lea     rcx, [rsp+78h+var_58]
0x180019379  cmp     rcx, rax
0x18001937c  jz      short loc_18001938C
0x18001937e  mov     rbx, [rax]
0x180019381  mov     [rax], r14
0x180019384  mov     [rsp+78h+var_58], rbx
0x180019389  mov     rsi, rbx
0x18001938c  cmp     [rsp+78h+arg_18], 0
0x180019395  jnz     short loc_1800193CB
0x180019397  jmp     short loc_1800193D8
0x180019399  lea     rcx, [rsi+358h]
0x1800193a0  call    ?ExportEapKeyMaterial@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4EapKeyMaterialType@Utility@Eap@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType const &)
0x1800193a5  mov     rsi, r14
0x1800193a8  lea     rcx, [rsp+78h+var_58]
0x1800193ad  cmp     rcx, rax
0x1800193b0  jz      short loc_1800193C0
0x1800193b2  mov     rbx, [rax]
0x1800193b5  mov     [rax], r14
0x1800193b8  mov     [rsp+78h+var_58], rbx
0x1800193bd  mov     rsi, rbx
0x1800193c0  cmp     [rsp+78h+arg_18], 0
0x1800193c9  jz      short loc_1800193D8
0x1800193cb  lea     rcx, [rsp+78h+arg_18]
0x1800193d3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800193d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193df  cmp     rcx, r15
0x1800193e2  jz      short loc_1800193F9
0x1800193e4  mov     edx, 1Dh
0x1800193e9  lea     r8, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids
0x1800193f0  mov     rcx, [rcx+10h]
0x1800193f4  call    WPP_SF_
0x1800193f9  mov     dword ptr [rsp+78h+Size], r14d
0x180019401  mov     [rsp+78h+var_40], r14d
0x180019406  xorps   xmm0, xmm0
0x180019409  movdqu  [rsp+78h+var_38], xmm0
0x18001940f  mov     rax, [rsi]
0x180019412  lea     rdx, [rsp+78h+Size]
0x18001941a  mov     rcx, rsi
0x18001941d  mov     rax, [rax+38h]
0x180019421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019426  test    eax, eax
0x180019428  jns     short loc_180019436
0x18001942a  lea     rdx, [rsp+78h+var_40]
0x18001942f  mov     ecx, eax
0x180019431  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180019436  mov     [rsp+78h+Src], r14
0x18001943b  mov     [rsp+78h+var_50], r14
0x180019440  mov     [rsp+78h+var_40], r14d
0x180019445  xorps   xmm0, xmm0
0x180019448  movdqu  [rsp+78h+var_38], xmm0
0x18001944e  mov     rax, [rsi]
0x180019451  lea     r8, [rsp+78h+var_50]
0x180019456  lea     rdx, ??$guid_v@UIBufferByteAccess@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IBufferByteAccess>
0x18001945d  mov     rcx, rsi
0x180019460  mov     rax, [rax]
0x180019463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019468  lea     r8, [rsp+78h+var_40]
0x18001946d  mov     edx, eax
0x18001946f  lea     rcx, [rsp+78h+arg_18]
0x180019477  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001947c  mov     rcx, [rsp+78h+var_50]
0x180019481  mov     [rsp+78h+arg_10], rcx
0x180019489  mov     esi, dword ptr [rsp+78h+Size]
0x180019490  mov     rax, [rcx]
0x180019493  lea     rdx, [rsp+78h+Src]
0x180019498  mov     rax, [rax+18h]
0x18001949c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194a1  lea     rcx, [rsp+78h+arg_10]
0x1800194a9  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800194ae  test    rsi, rsi
0x1800194b1  jz      loc_18001953D
0x1800194b7  test    rdi, rdi
0x1800194ba  jnz     short loc_1800194CA
0x1800194bc  call    cs:__imp__o__errno
0x1800194c2  mov     dword ptr [rax], 16h
0x1800194c8  jmp     short loc_180019537
0x1800194ca  mov     rax, [rsp+78h+Src]
0x1800194cf  test    rax, rax
0x1800194d2  jz      short loc_1800194ED
0x1800194d4  cmp     rsi, 80h
0x1800194db  ja      short loc_1800194ED
0x1800194dd  mov     r8, rsi; Size
0x1800194e0  mov     rdx, rax; Src
0x1800194e3  mov     rcx, rdi; void *
0x1800194e6  call    memcpy_0
0x1800194eb  jmp     short loc_18001953D
0x1800194ed  xorps   xmm0, xmm0
0x1800194f0  movups  xmmword ptr [rdi], xmm0
0x1800194f3  movups  xmmword ptr [rdi+10h], xmm0
0x1800194f7  movups  xmmword ptr [rdi+20h], xmm0
0x1800194fb  movups  xmmword ptr [rdi+30h], xmm0
0x1800194ff  movups  xmmword ptr [rdi+40h], xmm0
0x180019503  movups  xmmword ptr [rdi+50h], xmm0
0x180019507  movups  xmmword ptr [rdi+60h], xmm0
0x18001950b  movups  xmmword ptr [rdi+70h], xmm0
0x18001950f  test    rax, rax
0x180019512  jnz     short loc_180019522
0x180019514  call    cs:__imp__o__errno
0x18001951a  mov     dword ptr [rax], 16h
0x180019520  jmp     short loc_180019537
0x180019522  cmp     rsi, 80h
0x180019529  jbe     short loc_18001953D
0x18001952b  call    cs:__imp__o__errno
0x180019531  mov     dword ptr [rax], 22h ; '"'
0x180019537  call    _invalid_parameter_noinfo
0x18001953c  nop
0x18001953d  test    rbx, rbx
0x180019540  jz      loc_1800196E5
0x180019546  lea     rcx, [rsp+78h+var_58]
0x18001954b  jmp     loc_1800196E0
0x180019550  lea     rcx, [rsi+358h]
0x180019557  lea     r8, [rsp+78h+Size]
0x18001955f  lea     rdx, [rsp+78h+arg_18]
0x180019567  call    ?ExportEapKeyMaterial@?$consume_Windows_Internal_Eap_Utility_IEapSchannelUtil@UIEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4EapKeyMaterialType@Utility@Eap@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapSchannelUtil<winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::ExportEapKeyMaterial(winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType const &)
0x18001956c  nop
0x18001956d  mov     dword ptr [rsp+78h+Size], r14d
0x180019575  mov     rcx, [rsp+78h+arg_18]
0x18001957d  mov     [rsp+78h+var_40], r14d
0x180019582  xorps   xmm0, xmm0
0x180019585  movdqu  [rsp+78h+var_38], xmm0
0x18001958b  mov     rax, [rcx]
0x18001958e  lea     rdx, [rsp+78h+Size]
0x180019596  mov     rax, [rax+38h]
0x18001959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001959f  test    eax, eax
0x1800195a1  jns     short loc_1800195AF
0x1800195a3  lea     rdx, [rsp+78h+var_40]
0x1800195a8  mov     ecx, eax
0x1800195aa  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800195af  mov     [rsp+78h+var_50], r14
0x1800195b4  mov     rcx, [rsp+78h+arg_18]
0x1800195bc  test    rcx, rcx
0x1800195bf  jnz     short loc_1800195CE
0x1800195c1  mov     [rsp+78h+arg_10], r14
0x1800195c9  mov     rcx, r14
0x1800195cc  jmp     short loc_180019619
0x1800195ce  mov     [rsp+78h+Src], r14
0x1800195d3  mov     [rsp+78h+var_40], r14d
0x1800195d8  xorps   xmm0, xmm0
0x1800195db  movdqu  [rsp+78h+var_38], xmm0
0x1800195e1  mov     rax, [rcx]
0x1800195e4  lea     r8, [rsp+78h+Src]
0x1800195e9  lea     rdx, ??$guid_v@UIBufferByteAccess@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IBufferByteAccess>
0x1800195f0  mov     rax, [rax]
0x1800195f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f8  lea     r8, [rsp+78h+var_40]
0x1800195fd  mov     edx, eax
0x1800195ff  lea     rcx, [rsp+78h+arg_10]
0x180019607  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001960c  mov     rcx, [rsp+78h+Src]
0x180019611  mov     [rsp+78h+arg_10], rcx
0x180019619  mov     ebx, dword ptr [rsp+78h+Size]
0x180019620  mov     rax, [rcx]
0x180019623  lea     rdx, [rsp+78h+var_50]
0x180019628  mov     rax, [rax+18h]
0x18001962c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019631  lea     rcx, [rsp+78h+arg_10]
0x180019639  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001963e  test    rbx, rbx
0x180019641  jz      loc_1800196CD
0x180019647  test    rdi, rdi
0x18001964a  jnz     short loc_18001965A
0x18001964c  call    cs:__imp__o__errno
0x180019652  mov     dword ptr [rax], 16h
0x180019658  jmp     short loc_1800196C7
0x18001965a  mov     rax, [rsp+78h+var_50]
0x18001965f  test    rax, rax
0x180019662  jz      short loc_18001967D
0x180019664  cmp     rbx, 80h
0x18001966b  ja      short loc_18001967D
0x18001966d  mov     r8, rbx; Size
0x180019670  mov     rdx, rax; Src
0x180019673  mov     rcx, rdi; void *
0x180019676  call    memcpy_0
0x18001967b  jmp     short loc_1800196CD
0x18001967d  xorps   xmm0, xmm0
0x180019680  movups  xmmword ptr [rdi], xmm0
0x180019683  movups  xmmword ptr [rdi+10h], xmm0
0x180019687  movups  xmmword ptr [rdi+20h], xmm0
0x18001968b  movups  xmmword ptr [rdi+30h], xmm0
0x18001968f  movups  xmmword ptr [rdi+40h], xmm0
0x180019693  movups  xmmword ptr [rdi+50h], xmm0
0x180019697  movups  xmmword ptr [rdi+60h], xmm0
0x18001969b  movups  xmmword ptr [rdi+70h], xmm0
0x18001969f  test    rax, rax
0x1800196a2  jnz     short loc_1800196B2
0x1800196a4  call    cs:__imp__o__errno
0x1800196aa  mov     dword ptr [rax], 16h
0x1800196b0  jmp     short loc_1800196C7
0x1800196b2  cmp     rbx, 80h
0x1800196b9  jbe     short loc_1800196CD
0x1800196bb  call    cs:__imp__o__errno
0x1800196c1  mov     dword ptr [rax], 22h ; '"'
0x1800196c7  call    _invalid_parameter_noinfo
0x1800196cc  nop
0x1800196cd  cmp     [rsp+78h+arg_18], 0
0x1800196d6  jz      short loc_1800196E5
0x1800196d8  lea     rcx, [rsp+78h+arg_18]
0x1800196e0  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800196e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196ec  cmp     rcx, r15
0x1800196ef  jz      short loc_180019706
0x1800196f1  mov     edx, 1Fh
0x1800196f6  lea     r8, WPP_a12a621288f636b53cf7c22596c0e71c_Traceguids
0x1800196fd  mov     rcx, [rcx+10h]
0x180019701  call    WPP_SF_
0x180019706  xor     eax, eax
0x180019708  jmp     short loc_180019711
0x18001970a  mov     eax, dword ptr [rsp+78h+Size]
0x180019711  add     rsp, 50h
0x180019715  pop     r15
0x180019717  pop     r14
0x180019719  pop     rdi
0x18001971a  pop     rsi
0x18001971b  pop     rbx
0x18001971c  retn
```
