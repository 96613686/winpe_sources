# PenEventsDispatcherPrincipal::PenEventsDispatcherPrincipal(ISMBamos_AutoBamos::BamoConnection *)

- ea: `0x180039408`
- end: `0x1800396fb`
- name: `??0PenEventsDispatcherPrincipal@@QEAA@PEAVBamoConnection@ISMBamos_AutoBamos@@@Z`
- size: `755`
- prototype: `PenEventsDispatcherPrincipal *__fastcall(PenEventsDispatcherPrincipal *__hidden this, struct ISMBamos_AutoBamos::BamoConnection *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003912c`

## callees

- `0x18000c5bc`
- `0x18000ce20`
- `0x180012b74`
- `0x18001d704`
- `0x180028da8`
- `0x180030260`
- `0x180039408`
- `0x180039940`
- `0x18003d7ec`
- `0x18006e260`
- `0x18008dcac`
- `0x18008ee44`
- `0x1800f0990`
- `0x180107558`
- `0x180197ea8`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x180039558`
- `CoreMessaging!CoreUICreate` at `0x180039558`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800395b3`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800395b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
PenEventsDispatcherPrincipal *__fastcall PenEventsDispatcherPrincipal::PenEventsDispatcherPrincipal(
        PenEventsDispatcherPrincipal *this,
        struct ISMBamos_AutoBamos::BamoConnection *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // r8
  const char *v6; // r9
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, char *, __int64, char *); // rbx
  __int64 v10; // r8
  int v11; // eax
  unsigned int i; // ebx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-39h]
  _QWORD pvParam[3]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-11h] BYREF
  __int64 v18; // [rsp+60h] [rbp+7h]
  HSTRING_HEADER *p_hstringHeader; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  pvParam[1] = this;
  *(_QWORD *)this = &BamoPenEventsDispatcherPrincipal::`vftable'{for `Microsoft::Bamo::BamoPrincipal'};
  *((_QWORD *)this + 1) = &PenEventsDispatcherPrincipal::`vftable'{for `IPenEventsDispatcherPrincipal'};
  Microsoft::BamoImpl::BamoPrincipalImpl::BamoPrincipalImpl((PenEventsDispatcherPrincipal *)((char *)this + 16), a2);
  *((_QWORD *)this + 2) = &BamoImpl::BamoPenEventsDispatcherPrincipalImpl::`vftable';
  *(_QWORD *)this = &PenEventsDispatcherPrincipal::`vftable'{for `Microsoft::Bamo::BamoPrincipal'};
  *((_QWORD *)this + 1) = &PenEventsDispatcherPrincipal::`vftable'{for `IPenEventsDispatcherPrincipal'};
  *((_QWORD *)this + 7) = &PenEventsDispatcherPrincipal::`vftable';
  pvParam[0] = (char *)this + 64;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  std::list<std::pair<unsigned long const,IRawInputProvider *>>::_Alloc_sentinel_and_proxy((char *)this + 72);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>((char *)this + 88);
  *((_QWORD *)this + 14) = 7;
  *((_QWORD *)this + 15) = 8;
  *((_DWORD *)this + 16) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,ResizeProcessor::MessageInfo>>>>>>::_Assign_grow(
    v3,
    16,
    *((_QWORD *)this + 9));
  std::unordered_set<unsigned int>::unordered_set<unsigned int>((char *)this + 128);
  *((_BYTE *)this + 196) = 1;
  *((_DWORD *)this + 50) = 1;
  *((_DWORD *)this + 51) = 1;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = "CMK:PenEvent";
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  if ( IsEdition(0x224Au) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 208);
    v4 = CoreUICreate((char *)this + 208);
    if ( v4 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\stylus\\events\\server\\peneve"
                      "ntsdispatcherprincipal.cpp",
        (const char *)(unsigned int)v4,
        v15);
    hstringHeader.Reserved.Reserved1 = off_1801D1060;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = this;
    p_hstringHeader = &hstringHeader;
    KernelInputConnection<_MIT_PEN_EVENT_MESSAGE>::Initialize(
      (char *)this + 216,
      (char *)this + 208,
      v5,
      &hstringHeader);
    LODWORD(pvParam[0]) = 0;
    if ( SystemParametersInfoW(0x1052u, 0, pvParam, 0) )
      *((_BYTE *)this + 196) = LODWORD(pvParam[0]) != 1;
    else
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\stylus\\events\\server\\peneve"
                      "ntsdispatcherprincipal.cpp",
        v6);
  }
  else
  {
    pvParam[0] = 0;
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UI.Internal.Text.HotKeyClient",
      0x26u,
      0x25u);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>>(
           v18,
           pvParam);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\stylus\\events\\server\\peneve"
                      "ntsdispatcherprincipal.cpp",
        (const char *)(unsigned int)v7,
        v15);
    v8 = pvParam[0];
    v9 = *(__int64 (__fastcall **)(__int64, char *, __int64, char *))(*(_QWORD *)pvParam[0] + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 360);
    LOBYTE(v10) = 1;
    v11 = v9(v8, (char *)this + 56, v10, (char *)this + 360);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\stylus\\events\\server\\peneve"
                      "ntsdispatcherprincipal.cpp",
        (const char *)(unsigned int)v11,
        v15);
    for ( i = 0; i <= 4; ++i )
    {
      LOBYTE(v15) = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 45) + 48LL))(
              *((_QWORD *)this + 45),
              i,
              *((unsigned __int16 *)&PenEventsDispatcherPrincipal::s_hotkeyList + 2 * i),
              *((unsigned __int8 *)&PenEventsDispatcherPrincipal::s_hotkeyList + 4 * i + 2));
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x82,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\stylus\\events\\server\\pene"
                        "ventsdispatcherprincipal.cpp",
          (const char *)(unsigned int)v13,
          v15);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pvParam);
  }
  return this;
}

```

## disassembly

```asm
0x180039408  mov     [rsp-8+arg_10], rbx
0x18003940d  mov     [rsp-8+arg_18], rsi
0x180039412  push    rbp
0x180039413  push    rdi
0x180039414  push    r12
0x180039416  push    r14
0x180039418  push    r15
0x18003941a  lea     rbp, [rsp-37h]
0x18003941f  sub     rsp, 90h
0x180039426  mov     rax, cs:__security_cookie
0x18003942d  xor     rax, rsp
0x180039430  mov     [rbp+57h+var_28], rax
0x180039434  mov     rsi, rcx
0x180039437  mov     [rbp+57h+var_78], rcx
0x18003943b  lea     rax, ??_7BamoPenEventsDispatcherPrincipal@@6BBamoPrincipal@Bamo@Microsoft@@@; const BamoPenEventsDispatcherPrincipal::`vftable'{for `Microsoft::Bamo::BamoPrincipal'}
0x180039442  mov     [rcx], rax
0x180039445  lea     rax, ??_7PenEventsDispatcherPrincipal@@6BIPenEventsDispatcherPrincipal@@@; const PenEventsDispatcherPrincipal::`vftable'{for `IPenEventsDispatcherPrincipal'}
0x18003944c  mov     [rcx+8], rax
0x180039450  add     rcx, 10h; this
0x180039454  call    ??0BamoPrincipalImpl@BamoImpl@Microsoft@@QEAA@PEAVBaseBamoConnection@Bamo@2@@Z; Microsoft::BamoImpl::BamoPrincipalImpl::BamoPrincipalImpl(Microsoft::Bamo::BaseBamoConnection *)
0x180039459  lea     rax, ??_7BamoPenEventsDispatcherPrincipalImpl@BamoImpl@@6B@; const BamoImpl::BamoPenEventsDispatcherPrincipalImpl::`vftable'
0x180039460  mov     [rsi+10h], rax
0x180039464  lea     rax, ??_7PenEventsDispatcherPrincipal@@6BBamoPrincipal@Bamo@Microsoft@@@; const PenEventsDispatcherPrincipal::`vftable'{for `Microsoft::Bamo::BamoPrincipal'}
0x18003946b  mov     [rsi], rax
0x18003946e  lea     rax, ??_7PenEventsDispatcherPrincipal@@6BIPenEventsDispatcherPrincipal@@@; const PenEventsDispatcherPrincipal::`vftable'{for `IPenEventsDispatcherPrincipal'}
0x180039475  mov     [rsi+8], rax
0x180039479  lea     rax, ??_7PenEventsDispatcherPrincipal@@6B@; const PenEventsDispatcherPrincipal::`vftable'
0x180039480  mov     [rsi+38h], rax
0x180039484  lea     rdi, [rsi+40h]
0x180039488  mov     [rbp+57h+pvParam], rdi
0x18003948c  xor     r12d, r12d
0x18003948f  mov     [rdi], r12d
0x180039492  lea     rbx, [rdi+8]
0x180039496  mov     [rbx], r12
0x180039499  mov     [rbx+8], r12
0x18003949d  mov     rcx, rbx
0x1800394a0  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBKPEAUIRawInputProvider@@@std@@V?$allocator@U?$pair@$$CBKPEAUIRawInputProvider@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<ulong const,IRawInputProvider *>>::_Alloc_sentinel_and_proxy(void)
0x1800394a5  nop
0x1800394a6  lea     rcx, [rdi+18h]
0x1800394aa  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x1800394af  nop
0x1800394b0  mov     qword ptr [rdi+30h], 7
0x1800394b8  mov     qword ptr [rdi+38h], 8
0x1800394c0  mov     dword ptr [rdi], 3F800000h
0x1800394c6  mov     r8, [rbx]
0x1800394c9  lea     edx, [r12+10h]
0x1800394ce  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUMessageInfo@ResizeProcessor@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUMessageInfo@ResizeProcessor@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,ResizeProcessor::MessageInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,ResizeProcessor::MessageInfo>>>>)
0x1800394d3  nop
0x1800394d4  lea     rcx, [rsi+80h]
0x1800394db  call    ??0?$unordered_set@IU?$hash@I@std@@U?$equal_to@I@2@V?$allocator@I@2@@std@@QEAA@XZ; std::unordered_set<uint>::unordered_set<uint>(void)
0x1800394e0  nop
0x1800394e1  mov     byte ptr [rsi+0C4h], 1
0x1800394e8  mov     dword ptr [rsi+0C8h], 1
0x1800394f2  mov     dword ptr [rsi+0CCh], 1
0x1800394fc  lea     rbx, [rsi+0D0h]
0x180039503  mov     [rbx], r12
0x180039506  lea     rdi, [rsi+0D8h]
0x18003950d  mov     [rdi], r12
0x180039510  mov     [rdi+8], r12
0x180039514  mov     [rdi+10h], r12
0x180039518  mov     [rdi+78h], r12
0x18003951c  lea     rax, aCmkPenevent; "CMK:PenEvent"
0x180039523  mov     [rdi+80h], rax
0x18003952a  lea     r14, [rsi+168h]
0x180039531  mov     [r14], r12
0x180039534  mov     [rsi+170h], r12
0x18003953b  mov     ecx, 224Ah; unsigned __int64
0x180039540  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x180039545  test    al, al
0x180039547  jz      loc_1800395E7
0x18003954d  mov     rcx, rbx
0x180039550  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039555  mov     rcx, rbx
0x180039558  call    cs:__imp_CoreUICreate
0x18003955e  mov     rcx, [rbp+5Fh]; this
0x180039562  test    eax, eax
0x180039564  jns     short loc_18003957B
0x180039566  mov     r9d, eax; char *
0x180039569  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\moderncore\\inputv"...
0x180039570  lea     edx, [r12+65h]; void *
0x180039575  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003957b  lea     rax, off_1801D1060
0x180039582  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180039586  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x18003958a  lea     rax, [rbp+57h+hstringHeader]
0x18003958e  mov     [rbp+57h+var_30], rax
0x180039592  lea     r9, [rbp+57h+hstringHeader]
0x180039596  mov     rdx, rbx
0x180039599  mov     rcx, rdi
0x18003959c  call    ?Initialize@?$KernelInputConnection@U_MIT_PEN_EVENT_MESSAGE@@@@QEAAXAEBV?$ComPtr@UIMessageSession@@@WRL@Microsoft@@W4_MIT_ENDPOINT@@V?$function@$$A6AXPEBU_MIT_PEN_EVENT_MESSAGE@@@Z@std@@@Z; KernelInputConnection<_MIT_PEN_EVENT_MESSAGE>::Initialize(Microsoft::WRL::ComPtr<IMessageSession> const &,_MIT_ENDPOINT,std::function<void (_MIT_PEN_EVENT_MESSAGE const *)>)
0x1800395a1  mov     dword ptr [rbp+57h+pvParam], r12d
0x1800395a5  xor     r9d, r9d; fWinIni
0x1800395a8  lea     r8, [rbp+57h+pvParam]; pvParam
0x1800395ac  xor     edx, edx; uiParam
0x1800395ae  mov     ecx, 1052h; uiAction
0x1800395b3  call    cs:__imp_SystemParametersInfoW
0x1800395b9  mov     rcx, [rbp+5Fh]; this
0x1800395bd  test    eax, eax
0x1800395bf  jnz     short loc_1800395D5
0x1800395c1  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800395c8  lea     edx, [rax+71h]; void *
0x1800395cb  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800395d0  jmp     loc_1800396D0
0x1800395d5  cmp     dword ptr [rbp+57h+pvParam], 1
0x1800395d9  setnz   al
0x1800395dc  mov     [rsi+0C4h], al
0x1800395e2  jmp     loc_1800396D0
0x1800395e7  mov     [rbp+57h+pvParam], r12
0x1800395eb  mov     [rbp+57h+var_50], r12
0x1800395ef  mov     r9d, 25h ; '%'; unsigned int
0x1800395f5  lea     r8d, [r9+1]; unsigned int
0x1800395f9  lea     rdx, ?RuntimeClass_Windows_UI_Internal_Text_HotKeyClient@@3QBGB; "Windows.UI.Internal.Text.HotKeyClient"
0x180039600  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180039604  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180039609  lea     rdx, [rbp+57h+pvParam]
0x18003960d  mov     rcx, [rbp+57h+var_50]
0x180039611  call    ??$GetActivationFactory@V?$ComPtr@UIHotKeyClientStatics@Text@Internal@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIHotKeyClientStatics@Text@Internal@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>>)
0x180039616  mov     rcx, [rbp+5Fh]; this
0x18003961a  test    eax, eax
0x18003961c  jns     short loc_180039632
0x18003961e  mov     r9d, eax; char *
0x180039621  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\moderncore\\inputv"...
0x180039628  mov     edx, 79h ; 'y'; void *
0x18003962d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039632  mov     rdi, [rbp+57h+pvParam]
0x180039636  mov     rax, [rdi]
0x180039639  mov     rbx, [rax+30h]
0x18003963d  mov     rcx, r14
0x180039640  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039645  mov     r9, r14
0x180039648  mov     r8b, 1
0x18003964b  lea     rdx, [rsi+38h]
0x18003964f  mov     rcx, rdi
0x180039652  mov     rax, rbx
0x180039655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003965a  mov     rcx, [rbp+5Fh]; this
0x18003965e  test    eax, eax
0x180039660  jns     short loc_180039676
0x180039662  mov     r9d, eax; char *
0x180039665  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003966c  mov     edx, 7Ah ; 'z'; void *
0x180039671  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039676  mov     ebx, r12d
0x180039679  lea     rdi, ?s_hotkeyList@PenEventsDispatcherPrincipal@@0QBUHotkeyIdentity@1@B; PenEventsDispatcherPrincipal::HotkeyIdentity const near * const PenEventsDispatcherPrincipal::s_hotkeyList
0x180039680  mov     rcx, [r14]
0x180039683  mov     edx, ebx
0x180039685  mov     rax, [rcx]
0x180039688  movzx   r9d, byte ptr [rdi+rdx*4+2]
0x18003968e  movzx   r8d, word ptr [rdi+rdx*4]
0x180039693  mov     byte ptr [rsp+0B0h+var_90], r12b; int
0x180039698  mov     edx, ebx
0x18003969a  mov     rax, [rax+30h]
0x18003969e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396a3  mov     rcx, [rbp+5Fh]; this
0x1800396a7  test    eax, eax
0x1800396a9  jns     short loc_1800396BF
0x1800396ab  mov     r9d, eax; char *
0x1800396ae  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800396b5  mov     edx, 82h; void *
0x1800396ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800396bf  inc     ebx
0x1800396c1  cmp     ebx, 4
0x1800396c4  jbe     short loc_180039680
0x1800396c6  lea     rcx, [rbp+57h+pvParam]
0x1800396ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800396cf  nop
0x1800396d0  mov     rax, rsi
0x1800396d3  mov     rcx, [rbp+57h+var_28]
0x1800396d7  xor     rcx, rsp; StackCookie
0x1800396da  call    __security_check_cookie
0x1800396df  lea     r11, [rsp+0B0h+var_20]
0x1800396e7  mov     rbx, [r11+40h]
0x1800396eb  mov     rsi, [r11+48h]
0x1800396ef  mov     rsp, r11
0x1800396f2  pop     r15
0x1800396f4  pop     r14
0x1800396f6  pop     r12
0x1800396f8  pop     rdi
0x1800396f9  pop     rbp
0x1800396fa  retn
```
