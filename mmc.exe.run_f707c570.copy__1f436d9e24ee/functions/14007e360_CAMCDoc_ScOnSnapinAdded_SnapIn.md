# CAMCDoc::ScOnSnapinAdded(SnapIn *)

- ea: `0x14007e360`
- end: `0x14007e604`
- name: `?ScOnSnapinAdded@CAMCDoc@@UEAA?AVSC@mmcerror@@PEAUSnapIn@@@Z`
- size: `676`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14000125c`
- `0x140001330`
- `0x14000c1d0`
- `0x14004b06c`
- `0x1400754f4`
- `0x14007e360`
- `0x14007fea8`
- `0x14007ff20`
- `0x1400f3010`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14007e3ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14007e5de`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14007e3ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14007e5de`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14007e3a3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14007e3e3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14007e5d3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14007e3e3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14007e5d3`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14007e3c0`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14007e3c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007e4aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14007e4aa`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e58e`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e59d`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e5ac`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e58e`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e59d`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e5ac`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAMCDoc::ScOnSnapinAdded(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  int v7; // eax
  int v8; // r12d
  int v9; // r14d
  int v10; // r15d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  BSTR v14; // rax
  BSTR v15; // rax
  BSTR v16; // rax
  BSTR v17; // rdx
  __int64 v18; // rax
  BSTR v20; // [rsp+58h] [rbp-29h] BYREF
  DWORD CurrentProcessId; // [rsp+60h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-19h] BYREF
  BSTR v23; // [rsp+70h] [rbp-11h] BYREF
  __int64 v24; // [rsp+78h] [rbp-9h] BYREF
  BSTR v25; // [rsp+80h] [rbp-1h] BYREF
  BSTR v26; // [rsp+88h] [rbp+7h] BYREF
  BSTR v27; // [rsp+90h] [rbp+Fh] BYREF
  _BYTE v28[32]; // [rsp+98h] [rbp+17h] BYREF

  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  ++mmcerror::SC::s_CallDepth;
  *(_QWORD *)a2 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)a2, L"CAMCDoc::ScOnSnapinAdded");
  v6 = ScCheckPointers(v28, &theApp, 2147549183LL);
  mmcerror::SC::operator=(a2, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v28);
  v7 = *(_DWORD *)(a2 + 4);
  if ( !v7 || *(_DWORD *)a2 == 3 && v7 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::GetImpl'::`2'::impl)
      && a3 )
    {
      bstrString = 0;
      v20 = 0;
      v23 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
      v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 64LL))(a3, &v20);
      v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 88LL))(a3, &v23);
      if ( (unsigned int)dword_140157418 > 4 && (unsigned __int8)tlgKeywordOn() )
      {
        v24 = 0x2000000;
        CurrentProcessId = GetCurrentProcessId();
        if ( v10 < 0 || (v14 = v23) == 0 )
          v14 = (BSTR)L"Unknown";
        v25 = v14;
        if ( v9 < 0 || (v15 = v20) == 0 )
          v15 = (BSTR)L"Unknown";
        v26 = v15;
        if ( v8 < 0 || (v16 = bstrString) == 0 )
          v16 = (BSTR)L"Unknown";
        v27 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v11,
          (unsigned int)byte_140134C4D,
          v12,
          v13,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&CurrentProcessId,
          (__int64)&v24);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage>::GetImpl'::`2'::impl) )
      {
        if ( *(_QWORD *)(a1 + 208) )
          std::wstring::append(a1 + 192, L";");
        if ( v9 < 0 || (v17 = v20) == 0 )
          v17 = (BSTR)L"Unknown";
        std::wstring::append(a1 + 192, v17);
      }
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v20 )
        SysFreeString(v20);
      if ( v23 )
        SysFreeString(v23);
    }
    v18 = CAMCApp::ScOnSnapinAdded(&theApp, v28, a1 - 192, a3);
    mmcerror::SC::operator=(a2, v18);
    mmcerror::SC::~SC((mmcerror::SC *)v28);
  }
  return a2;
}

```

## disassembly

```asm
0x14007e360  mov     rax, rsp
0x14007e363  mov     [rax+8], rbx
0x14007e367  mov     [rax+18h], rsi
0x14007e36b  mov     [rax+10h], rdx
0x14007e36f  push    rbp
0x14007e370  push    rdi
0x14007e371  push    r12
0x14007e373  push    r14
0x14007e375  push    r15
0x14007e377  lea     rbp, [rax-5Fh]
0x14007e37b  sub     rsp, 0B0h
0x14007e382  mov     rsi, r8
0x14007e385  mov     rbx, rdx
0x14007e388  mov     rdi, rcx
0x14007e38b  mov     ecx, 1
0x14007e390  mov     [rbp+57h+arg_18], ecx
0x14007e393  mov     qword ptr [rdx+8], 0
0x14007e39b  mov     qword ptr [rdx+10h], 0
0x14007e3a3  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14007e3aa  add     [rax], ecx
0x14007e3ac  mov     qword ptr [rdx], 3
0x14007e3b3  mov     [rbp+57h+arg_18], ecx
0x14007e3b6  lea     rdx, aCamcdocSconsna; "CAMCDoc::ScOnSnapinAdded"
0x14007e3bd  mov     rcx, rbx
0x14007e3c0  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14007e3c6  mov     r8d, 8000FFFFh
0x14007e3cc  lea     rdx, ?theApp@@3VCAMCApp@@A; CAMCApp theApp
0x14007e3d3  lea     rcx, [rbp+57h+var_40]
0x14007e3d7  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x14007e3dc  nop
0x14007e3dd  mov     rdx, rax
0x14007e3e0  mov     rcx, rbx
0x14007e3e3  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14007e3e9  nop
0x14007e3ea  lea     rcx, [rbp+57h+var_40]
0x14007e3ee  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14007e3f4  mov     eax, [rbx+4]
0x14007e3f7  test    eax, eax
0x14007e3f9  jz      short loc_14007E40F
0x14007e3fb  cmp     dword ptr [rbx], 3
0x14007e3fe  jnz     loc_14007E5E5
0x14007e404  shr     eax, 1Fh
0x14007e407  test    al, al
0x14007e409  jnz     loc_14007E5E5
0x14007e40f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::GetImpl(void)'::`2'::impl
0x14007e416  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::__private_IsEnabled(void)
0x14007e41b  test    al, al
0x14007e41d  jz      loc_14007E5B2
0x14007e423  test    rsi, rsi
0x14007e426  jz      loc_14007E5B2
0x14007e42c  mov     [rbp+57h+bstrString], 0
0x14007e434  mov     [rbp+57h+var_80], 0
0x14007e43c  mov     [rbp+57h+var_68], 0
0x14007e444  mov     rax, [rsi]
0x14007e447  lea     rdx, [rbp+57h+bstrString]
0x14007e44b  mov     rcx, rsi
0x14007e44e  mov     rax, [rax+38h]
0x14007e452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e457  mov     r12d, eax
0x14007e45a  mov     rcx, [rsi]
0x14007e45d  mov     rax, [rcx+40h]
0x14007e461  lea     rdx, [rbp+57h+var_80]
0x14007e465  mov     rcx, rsi
0x14007e468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e46d  mov     r14d, eax
0x14007e470  mov     rcx, [rsi]
0x14007e473  mov     rax, [rcx+58h]
0x14007e477  lea     rdx, [rbp+57h+var_68]
0x14007e47b  mov     rcx, rsi
0x14007e47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e483  mov     r15d, eax
0x14007e486  mov     ecx, cs:dword_140157418
0x14007e48c  cmp     ecx, 4
0x14007e48f  jbe     loc_14007E537
0x14007e495  call    _tlgKeywordOn
0x14007e49a  test    al, al
0x14007e49c  jz      loc_14007E537
0x14007e4a2  mov     [rbp+57h+var_60], 2000000h
0x14007e4aa  call    cs:__imp_GetCurrentProcessId
0x14007e4b0  mov     [rbp+57h+var_78], eax
0x14007e4b3  test    r15d, r15d
0x14007e4b6  js      short loc_14007E4C1
0x14007e4b8  mov     rax, [rbp+57h+var_68]
0x14007e4bc  test    rax, rax
0x14007e4bf  jnz     short loc_14007E4C8
0x14007e4c1  lea     rax, aUnknown; "Unknown"
0x14007e4c8  mov     [rbp+57h+var_58], rax
0x14007e4cc  test    r14d, r14d
0x14007e4cf  js      short loc_14007E4DA
0x14007e4d1  mov     rax, [rbp+57h+var_80]
0x14007e4d5  test    rax, rax
0x14007e4d8  jnz     short loc_14007E4E1
0x14007e4da  lea     rax, aUnknown; "Unknown"
0x14007e4e1  mov     [rbp+57h+var_50], rax
0x14007e4e5  test    r12d, r12d
0x14007e4e8  js      short loc_14007E4F3
0x14007e4ea  mov     rax, [rbp+57h+bstrString]
0x14007e4ee  test    rax, rax
0x14007e4f1  jnz     short loc_14007E4FA
0x14007e4f3  lea     rax, aUnknown; "Unknown"
0x14007e4fa  mov     [rbp+57h+var_48], rax
0x14007e4fe  lea     rax, [rbp+57h+var_60]
0x14007e502  mov     [rsp+0D0h+var_90], rax
0x14007e507  lea     rax, [rbp+57h+var_78]
0x14007e50b  mov     [rsp+0D0h+var_98], rax
0x14007e510  lea     rax, [rbp+57h+var_58]
0x14007e514  mov     [rsp+0D0h+var_A0], rax
0x14007e519  lea     rax, [rbp+57h+var_50]
0x14007e51d  mov     [rsp+0D0h+var_A8], rax
0x14007e522  lea     rax, [rbp+57h+var_48]
0x14007e526  mov     [rsp+0D0h+var_B0], rax
0x14007e52b  lea     rdx, byte_140134C4D
0x14007e532  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14007e537  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage>::GetImpl(void)'::`2'::impl
0x14007e53e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryMMCRemoteConnectionUsage>::__private_IsEnabled(void)
0x14007e543  test    al, al
0x14007e545  jz      short loc_14007E585
0x14007e547  cmp     qword ptr [rdi+0D0h], 0
0x14007e54f  jz      short loc_14007E564
0x14007e551  lea     rcx, [rdi+0C0h]
0x14007e558  lea     rdx, asc_140111B04; ";"
0x14007e55f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14007e564  test    r14d, r14d
0x14007e567  js      short loc_14007E572
0x14007e569  mov     rdx, [rbp+57h+var_80]
0x14007e56d  test    rdx, rdx
0x14007e570  jnz     short loc_14007E579
0x14007e572  lea     rdx, aUnknown; "Unknown"
0x14007e579  lea     rcx, [rdi+0C0h]
0x14007e580  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14007e585  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14007e589  test    rcx, rcx
0x14007e58c  jz      short loc_14007E594
0x14007e58e  call    cs:__imp_SysFreeString
0x14007e594  mov     rcx, [rbp+57h+var_80]; bstrString
0x14007e598  test    rcx, rcx
0x14007e59b  jz      short loc_14007E5A3
0x14007e59d  call    cs:__imp_SysFreeString
0x14007e5a3  mov     rcx, [rbp+57h+var_68]; bstrString
0x14007e5a7  test    rcx, rcx
0x14007e5aa  jz      short loc_14007E5B2
0x14007e5ac  call    cs:__imp_SysFreeString
0x14007e5b2  lea     r8, [rdi-0C0h]
0x14007e5b9  mov     r9, rsi
0x14007e5bc  lea     rdx, [rbp+57h+var_40]
0x14007e5c0  lea     rcx, ?theApp@@3VCAMCApp@@A; CAMCApp theApp
0x14007e5c7  call    ?ScOnSnapinAdded@CAMCApp@@QEAA?AVSC@mmcerror@@PEAVCAMCDoc@@PEAUSnapIn@@@Z; CAMCApp::ScOnSnapinAdded(CAMCDoc *,SnapIn *)
0x14007e5cc  nop
0x14007e5cd  mov     rdx, rax
0x14007e5d0  mov     rcx, rbx
0x14007e5d3  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14007e5d9  nop
0x14007e5da  lea     rcx, [rbp+57h+var_40]
0x14007e5de  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14007e5e4  nop
0x14007e5e5  mov     rax, rbx
0x14007e5e8  lea     r11, [rsp+0D0h+var_20]
0x14007e5f0  mov     rbx, [r11+30h]
0x14007e5f4  mov     rsi, [r11+40h]
0x14007e5f8  mov     rsp, r11
0x14007e5fb  pop     r15
0x14007e5fd  pop     r14
0x14007e5ff  pop     r12
0x14007e601  pop     rdi
0x14007e602  pop     rbp
0x14007e603  retn
```
