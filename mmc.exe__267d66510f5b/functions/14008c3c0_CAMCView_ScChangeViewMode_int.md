# CAMCView::ScChangeViewMode(int)

- ea: `0x14008c3c0`
- end: `0x14008c734`
- name: `?ScChangeViewMode@CAMCView@@UEAA?AVSC@mmcerror@@H@Z`
- size: `884`
- prototype: `struct mmcerror::SC __high(int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000125c`
- `0x1400019b8`
- `0x14000d720`
- `0x14002a050`
- `0x14002d850`
- `0x140042dc0`
- `0x14007a864`
- `0x14008b024`
- `0x14008c3c0`
- `0x140097e38`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `MFC42u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x14008c400`
- `MFC42u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x14008c400`
- `MFC42u!__imp_?AfxGetAppModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x14008c3f3`
- `MFC42u!__imp_?AfxGetAppModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x14008c3f3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008c5f0`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008c621`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008c6fb`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008c5f0`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008c621`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14008c6fb`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14008c40f`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008c616`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008c6f0`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008c616`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14008c6f0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14008c5e5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14008c5e5`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14008c42b`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14008c42b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008c520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14008c520`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=5
mmcerror::SC *__fastcall CAMCView::ScChangeViewMode(__int64 a1, mmcerror::SC *a2, int a3)
{
  struct AFX_MODULE_STATE *AppModuleState; // rax
  __int64 v7; // rdx
  const wchar_t *v8; // rax
  const OLECHAR *v9; // rax
  const OLECHAR *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  CAMCView *v15; // rcx
  __int64 v16; // rax
  int v17; // ebx
  __int64 v18; // rax
  int v19; // ebx
  __int64 v20; // rbx
  __int64 v21; // rax
  int v23; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-71h] BYREF
  __int128 v25; // [rsp+60h] [rbp-69h]
  DWORD CurrentProcessId; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v27[2]; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v28[3]; // [rsp+88h] [rbp-41h] BYREF
  const wchar_t *v29; // [rsp+A0h] [rbp-29h] BYREF
  const OLECHAR *v30; // [rsp+A8h] [rbp-21h] BYREF
  _QWORD v31[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-9h]
  unsigned __int64 v33; // [rsp+C8h] [rbp-1h]
  _QWORD v34[2]; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v35; // [rsp+E0h] [rbp+17h]
  unsigned __int64 v36; // [rsp+E8h] [rbp+1Fh]

  v28[0] = a2;
  AppModuleState = AfxGetAppModuleState();
  AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2((AFX_MAINTAIN_STATE2 *)v27, AppModuleState);
  v25 = 0;
  ++mmcerror::SC::s_CallDepth;
  v24 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v24, L"CAMCView::OnViewModeChange");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth>::GetImpl'::`2'::impl)
    && (a3 & 0xFFFFFFFD) == 0 )
  {
    v35 = 0;
    v36 = 7;
    std::wstring::_Eos(v34, 0);
    v32 = 0;
    v33 = 7;
    std::wstring::_Eos(v31, 0);
    v23 = 0;
    GetMMCTelemetryContext(v34, v31, &v23);
    if ( (unsigned int)dword_140157418 > 4 && (unsigned __int8)tlgKeywordOn() )
    {
      v28[2] = 0x2000000;
      v8 = L"LargeIcons";
      if ( a3 )
        v8 = L"SmallIcons";
      v29 = v8;
      v9 = &WindowName;
      if ( v32 )
      {
        v10 = (const OLECHAR *)v31;
        if ( v33 >= 8 )
          v10 = (const OLECHAR *)v31[0];
      }
      else
      {
        v10 = &WindowName;
      }
      v30 = v10;
      if ( v35 )
      {
        v9 = (const OLECHAR *)v34;
        if ( v36 >= 8 )
          v9 = (const OLECHAR *)v34[0];
      }
      v28[0] = v9;
      CurrentProcessId = GetCurrentProcessId();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v11,
        (__int64)&unk_140135160,
        v12,
        v13,
        (__int64)&CurrentProcessId,
        v28,
        &v30,
        (__int64)&v23,
        &v29);
    }
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v31, v7, 0);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v34, v14, 0);
  }
  if ( CAMCView::HasListOrListPad((CAMCView *)(a1 - 136)) )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 568) + 40LL))(*(_QWORD *)(a1 + 568));
    if ( a3 != 4 || (*(_BYTE *)(a1 + 1096) & 8) != 0 )
    {
      CAMCView::PrivateChangeListViewMode((CAMCView *)(a1 - 136), a3);
      if ( (v19 == 4) != (a3 == 4) && (*(_BYTE *)(a1 + 1096) & 8) != 0 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 240LL))(a1);
        v21 = _com_ptr_t<_com_IIID<SnapIn,&_GUID const IID_SnapIn>>::operator->(a1 + 288);
        (*(void (__fastcall **)(__int64, __int64, __int64, bool, _QWORD))(*(_QWORD *)v21 + 240LL))(
          v21,
          v20,
          36897,
          a3 == 4,
          0);
      }
    }
    else
    {
      v24 = 0x8007005700000003uLL;
    }
  }
  else
  {
    v16 = *(_QWORD *)(a1 + 1168);
    v17 = *(_DWORD *)(v16 + 32);
    *(_DWORD *)(v16 + 32) = 2;
    CAMCView::PrivateChangeListViewMode(v15, a3);
    *(_DWORD *)(*(_QWORD *)(a1 + 1168) + 32LL) = v17;
    v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 560) + 560LL))(*(_QWORD *)(a1 + 560), v31);
    mmcerror::SC::operator=(&v24, v18);
    mmcerror::SC::~SC((mmcerror::SC *)v31);
  }
  mmcerror::SC::SC(a2, (const struct mmcerror::SC *)&v24);
  mmcerror::SC::~SC((mmcerror::SC *)&v24);
  *(_QWORD *)(v27[1] + 8LL) = v27[0];
  return a2;
}

```

## disassembly

```asm
0x14008c3c0  mov     [rsp-8+arg_18], rbx
0x14008c3c5  push    rbp
0x14008c3c6  push    rsi
0x14008c3c7  push    rdi
0x14008c3c8  push    r14
0x14008c3ca  push    r15
0x14008c3cc  lea     rbp, [rsp-37h]
0x14008c3d1  sub     rsp, 100h
0x14008c3d8  mov     rax, cs:__security_cookie
0x14008c3df  xor     rax, rsp
0x14008c3e2  mov     [rbp+57h+var_30], rax
0x14008c3e6  mov     r14d, r8d
0x14008c3e9  mov     rdi, rdx
0x14008c3ec  mov     rsi, rcx
0x14008c3ef  mov     [rbp+57h+var_98], rdx
0x14008c3f3  call    cs:__imp_?AfxGetAppModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetAppModuleState(void)
0x14008c3f9  mov     rdx, rax
0x14008c3fc  lea     rcx, [rbp+57h+var_A8]
0x14008c400  call    cs:__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z; AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2(AFX_MODULE_STATE *)
0x14008c406  nop
0x14008c407  xorps   xmm0, xmm0
0x14008c40a  movdqu  [rbp+57h+var_C0], xmm0
0x14008c40f  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14008c416  inc     dword ptr [rax]
0x14008c418  mov     [rbp+57h+var_C8], 3
0x14008c420  lea     rdx, aCamcviewOnview; "CAMCView::OnViewModeChange"
0x14008c427  lea     rcx, [rbp+57h+var_C8]
0x14008c42b  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14008c431  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth>::GetImpl(void)'::`2'::impl
0x14008c438  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCLowUsageFeatFourth>::__private_IsEnabled(void)
0x14008c43d  test    al, al
0x14008c43f  jz      loc_14008C589
0x14008c445  test    r14d, 0FFFFFFFDh
0x14008c44c  jnz     loc_14008C589
0x14008c452  mov     [rbp+57h+var_40], 0
0x14008c45a  mov     ebx, 7
0x14008c45f  mov     [rbp+57h+var_38], rbx
0x14008c463  xor     edx, edx
0x14008c465  lea     rcx, [rbp+57h+var_50]
0x14008c469  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x14008c46e  nop
0x14008c46f  mov     [rbp+57h+var_60], 0
0x14008c477  mov     [rbp+57h+var_58], rbx
0x14008c47b  xor     edx, edx
0x14008c47d  lea     rcx, [rbp+57h+var_70]
0x14008c481  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x14008c486  nop
0x14008c487  mov     [rbp+57h+var_D0], 0
0x14008c48e  lea     r8, [rbp+57h+var_D0]
0x14008c492  lea     rdx, [rbp+57h+var_70]
0x14008c496  lea     rcx, [rbp+57h+var_50]
0x14008c49a  call    ?GetMMCTelemetryContext@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAJ@Z; GetMMCTelemetryContext(std::wstring &,std::wstring &,long &)
0x14008c49f  mov     eax, cs:dword_140157418
0x14008c4a5  cmp     eax, 4
0x14008c4a8  jbe     loc_14008C56C
0x14008c4ae  call    _tlgKeywordOn
0x14008c4b3  test    al, al
0x14008c4b5  jz      loc_14008C56C
0x14008c4bb  mov     [rbp+57h+var_88], 2000000h
0x14008c4c3  lea     rcx, aSmallicons; "SmallIcons"
0x14008c4ca  lea     rax, aLargeicons; "LargeIcons"
0x14008c4d1  test    r14d, r14d
0x14008c4d4  cmovnz  rax, rcx
0x14008c4d8  mov     [rbp+57h+var_80], rax
0x14008c4dc  mov     eax, [rbp+57h+var_D0]
0x14008c4df  mov     [rbp+57h+var_D0], eax
0x14008c4e2  lea     rax, WindowName
0x14008c4e9  cmp     [rbp+57h+var_60], 0
0x14008c4ee  jnz     short loc_14008C4F5
0x14008c4f0  mov     rcx, rax
0x14008c4f3  jmp     short loc_14008C503
0x14008c4f5  lea     rcx, [rbp+57h+var_70]
0x14008c4f9  cmp     [rbp+57h+var_58], 8
0x14008c4fe  cmovnb  rcx, [rbp+57h+var_70]
0x14008c503  mov     [rbp+57h+var_78], rcx
0x14008c507  cmp     [rbp+57h+var_40], 0
0x14008c50c  jz      short loc_14008C51C
0x14008c50e  lea     rax, [rbp+57h+var_50]
0x14008c512  cmp     [rbp+57h+var_38], 8
0x14008c517  cmovnb  rax, [rbp+57h+var_50]
0x14008c51c  mov     [rbp+57h+var_98], rax
0x14008c520  call    cs:__imp_GetCurrentProcessId
0x14008c526  mov     [rbp+57h+var_B0], eax
0x14008c529  lea     rax, [rbp+57h+var_88]
0x14008c52d  mov     [rsp+120h+var_D8], rax
0x14008c532  lea     rax, [rbp+57h+var_80]
0x14008c536  mov     [rsp+120h+var_E0], rax
0x14008c53b  lea     rax, [rbp+57h+var_D0]
0x14008c53f  mov     [rsp+120h+var_E8], rax
0x14008c544  lea     rax, [rbp+57h+var_78]
0x14008c548  mov     [rsp+120h+var_F0], rax
0x14008c54d  lea     rax, [rbp+57h+var_98]
0x14008c551  mov     [rsp+120h+var_F8], rax
0x14008c556  lea     rax, [rbp+57h+var_B0]
0x14008c55a  mov     [rsp+120h+var_100], rax
0x14008c55f  lea     rdx, unk_140135160
0x14008c566  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@434AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14008c56b  nop
0x14008c56c  xor     r8d, r8d
0x14008c56f  mov     dl, 1
0x14008c571  lea     rcx, [rbp+57h+var_70]
0x14008c575  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14008c57a  nop
0x14008c57b  xor     r8d, r8d
0x14008c57e  mov     dl, 1
0x14008c580  lea     rcx, [rbp+57h+var_50]
0x14008c584  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14008c589  lea     r15, [rsi-88h]
0x14008c590  mov     rcx, r15; this
0x14008c593  call    ?HasListOrListPad@CAMCView@@QEBA_NXZ; CAMCView::HasListOrListPad(void)
0x14008c598  test    al, al
0x14008c59a  jnz     loc_14008C639
0x14008c5a0  mov     rax, [rsi+490h]
0x14008c5a7  mov     ebx, [rax+20h]
0x14008c5aa  mov     dword ptr [rax+20h], 2
0x14008c5b1  mov     edx, r14d; int
0x14008c5b4  call    ?PrivateChangeListViewMode@CAMCView@@AEAAXH@Z; CAMCView::PrivateChangeListViewMode(int)
0x14008c5b9  mov     rax, [rsi+490h]
0x14008c5c0  mov     [rax+20h], ebx
0x14008c5c3  mov     rcx, [rsi+230h]
0x14008c5ca  mov     rax, [rcx]
0x14008c5cd  lea     rdx, [rbp+57h+var_70]
0x14008c5d1  mov     rax, [rax+230h]
0x14008c5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c5dd  nop
0x14008c5de  mov     rdx, rax
0x14008c5e1  lea     rcx, [rbp+57h+var_C8]
0x14008c5e5  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14008c5eb  nop
0x14008c5ec  lea     rcx, [rbp+57h+var_70]
0x14008c5f0  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14008c5f6  mov     eax, dword ptr [rbp+57h+var_C8+4]
0x14008c5f9  test    eax, eax
0x14008c5fb  jz      loc_14008C6E9
0x14008c601  cmp     dword ptr [rbp+57h+var_C8], 3
0x14008c605  jnz     short loc_14008C60F
0x14008c607  test    eax, eax
0x14008c609  jns     loc_14008C6E9
0x14008c60f  lea     rdx, [rbp+57h+var_C8]
0x14008c613  mov     rcx, rdi
0x14008c616  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14008c61c  nop
0x14008c61d  lea     rcx, [rbp+57h+var_C8]
0x14008c621  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14008c627  nop
0x14008c628  mov     rdx, [rbp+57h+var_A8]
0x14008c62c  mov     rcx, [rbp+57h+var_A0]
0x14008c630  mov     [rcx+8], rdx
0x14008c634  jmp     loc_14008C70E
0x14008c639  mov     rcx, [rsi+238h]
0x14008c640  mov     rax, [rcx]
0x14008c643  mov     rax, [rax+28h]
0x14008c647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c64c  mov     ebx, eax
0x14008c64e  cmp     r14d, 4
0x14008c652  jnz     short loc_14008C66D
0x14008c654  test    byte ptr [rsi+448h], 8
0x14008c65b  jnz     short loc_14008C66D
0x14008c65d  mov     dword ptr [rbp+57h+var_C8], 3
0x14008c664  mov     dword ptr [rbp+57h+var_C8+4], 80070057h
0x14008c66b  jmp     short loc_14008C6E9
0x14008c66d  mov     edx, r14d; int
0x14008c670  mov     rcx, r15; this
0x14008c673  call    ?PrivateChangeListViewMode@CAMCView@@AEAAXH@Z; CAMCView::PrivateChangeListViewMode(int)
0x14008c678  xor     ecx, ecx
0x14008c67a  cmp     ebx, 4
0x14008c67d  setz    cl
0x14008c680  xor     eax, eax
0x14008c682  cmp     r14d, 4
0x14008c686  setz    al
0x14008c689  cmp     ecx, eax
0x14008c68b  jz      short loc_14008C6E9
0x14008c68d  test    byte ptr [rsi+448h], 8
0x14008c694  jz      short loc_14008C6E9
0x14008c696  mov     rax, [rsi]
0x14008c699  mov     rcx, rsi
0x14008c69c  mov     rax, [rax+0F0h]
0x14008c6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c6a8  mov     rbx, rax
0x14008c6ab  lea     rcx, [rsi+120h]
0x14008c6b2  call    ??C?$_com_ptr_t@V?$_com_IIID@USnapIn@@$1?IID_SnapIn@@3U_GUID@@B@@@@QEBAPEAUSnapIn@@XZ; _com_ptr_t<_com_IIID<SnapIn,&_GUID const IID_SnapIn>>::operator->(void)
0x14008c6b7  mov     r10, rax
0x14008c6ba  mov     rcx, [rax]
0x14008c6bd  xor     r9d, r9d
0x14008c6c0  cmp     r14d, 4
0x14008c6c4  setz    r9b
0x14008c6c8  mov     rax, [rcx+0F0h]
0x14008c6cf  mov     [rsp+120h+var_100], 0
0x14008c6d8  mov     r8d, 9021h
0x14008c6de  mov     rdx, rbx
0x14008c6e1  mov     rcx, r10
0x14008c6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c6e9  lea     rdx, [rbp+57h+var_C8]
0x14008c6ed  mov     rcx, rdi
0x14008c6f0  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14008c6f6  nop
0x14008c6f7  lea     rcx, [rbp+57h+var_C8]
0x14008c6fb  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14008c701  nop
0x14008c702  mov     rax, [rbp+57h+var_A0]
0x14008c706  mov     rcx, [rbp+57h+var_A8]
0x14008c70a  mov     [rax+8], rcx
0x14008c70e  mov     rax, rdi
0x14008c711  mov     rcx, [rbp+57h+var_30]
0x14008c715  xor     rcx, rsp; StackCookie
0x14008c718  call    __security_check_cookie
0x14008c71d  mov     rbx, [rsp+120h+arg_18]
0x14008c725  add     rsp, 100h
0x14008c72c  pop     r15
0x14008c72e  pop     r14
0x14008c730  pop     rdi
0x14008c731  pop     rsi
0x14008c732  pop     rbp
0x14008c733  retn
```
