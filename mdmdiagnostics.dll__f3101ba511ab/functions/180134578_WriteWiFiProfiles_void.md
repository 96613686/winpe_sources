# WriteWiFiProfiles(void)

- ea: `0x180134578`
- end: `0x180134b6e`
- name: `?WriteWiFiProfiles@@YAJXZ`
- size: `1526`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e5744`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x180105480`
- `0x180105688`
- `0x1801056d0`
- `0x180106b3c`
- `0x180106dc8`
- `0x18012269c`
- `0x18012845c`
- `0x1801284b0`
- `0x180128c50`
- `0x180129304`
- `0x1801293b4`
- `0x1801293ec`
- `0x180129498`
- `0x180129aac`
- `0x180129ee0`
- `0x18012c10c`
- `0x1801330e0`
- `0x180134578`
- `0x18013944c`
- `0x18013a39c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134630`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801346d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134812`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801348a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801349ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134b06`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134630`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801346d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134812`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801348a4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801349ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134b06`

## string_xrefs

- `0x1801345e4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180134792`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180134951`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180134a5f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 WriteWiFiProfiles(void)
{
  __int64 v0; // rcx
  int v1; // eax
  unsigned int v2; // edi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  _QWORD *i; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rax
  WCHAR *v22; // rax
  int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // esi
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-138h]
  int v33; // [rsp+20h] [rbp-138h]
  int v34; // [rsp+30h] [rbp-128h] BYREF
  int v35; // [rsp+34h] [rbp-124h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp-120h] BYREF
  _QWORD v37[2]; // [rsp+48h] [rbp-110h] BYREF
  int v38[2]; // [rsp+58h] [rbp-100h] BYREF
  _BYTE v39[8]; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-E8h]
  __int64 v41; // [rsp+78h] [rbp-E0h]
  const wchar_t *v42; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v43[8]; // [rsp+88h] [rbp-D0h] BYREF
  _BYTE v44[32]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v45[32]; // [rsp+B0h] [rbp-A8h] BYREF
  _QWORD v46[10]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v47[32]; // [rsp+120h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources((Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources *)&v34);
  std::list<std::wstring>::list<std::wstring>(v38);
  std::list<std::wstring>::list<std::wstring>(v37);
  v1 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(
         v0,
         (__int64)L"WiFi",
         (int)v37,
         (int)v38);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x937,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v1,
      v32);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v3,
      v37[0]);
    std::_Deallocate<16>(v37[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v4,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(_QWORD *)v38, 48);
    if ( v34 )
      CoUninitialize();
    return v2;
  }
  std::list<std::wstring>::list<std::wstring>(v36, v37);
  std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(
    (unsigned int)v36,
    (unsigned int)v43,
    v36[0],
    **(_QWORD **)v38,
    *(__int64 *)v38);
  if ( !v36[1] )
  {
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v6,
      v36[0]);
    std::_Deallocate<16>(v36[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v7,
      v37[0]);
    std::_Deallocate<16>(v37[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v8,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(_QWORD *)v38, 48);
    if ( v34 )
      CoUninitialize();
    return 0;
  }
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v46,
    L"WiFi profiles",
    L"WifiProfilesTable");
  v42 = L"Profile";
  v35 = 40;
  v9 = std::vector<int>::vector<int>(v44, &v35, v36);
  v10 = std::vector<std::wstring>::vector<std::wstring>(v39, &v42, v43);
  v11 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
          v46,
          L"Only profiles managed by this MDM connection are displayed",
          v10,
          v9);
  std::vector<std::wstring>::_Tidy(v39);
  std::vector<enum TpmCapabilityPT>::_Tidy(v44);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x947,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v11,
      v33);
    v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v12,
      v36[0]);
    std::_Deallocate<16>(v36[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v13,
      v37[0]);
    std::_Deallocate<16>(v37[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v14,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(_QWORD *)v38, 48);
    if ( v34 )
      CoUninitialize();
    return (unsigned int)v11;
  }
  v15 = (_QWORD *)v36[0];
  for ( i = *(_QWORD **)v36[0]; ; i = (_QWORD *)*i )
  {
    if ( i == v15 )
    {
      v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v17,
        v36[0]);
      std::_Deallocate<16>(v36[0], 48);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v18,
        v37[0]);
      std::_Deallocate<16>(v37[0], 48);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v19,
        *(_QWORD *)v38);
      std::_Deallocate<16>(*(_QWORD *)v38, 48);
      if ( v34 )
        CoUninitialize();
      return 0;
    }
    std::wstring::wstring(v45, i + 2);
    v20 = std::wstring::rfind(v45, 47, -1);
    if ( v20 != -1 )
      break;
LABEL_31:
    std::wstring::_Tidy_deallocate(v45);
  }
  std::wstring::wstring(v44);
  v21 = std::wstring::substr(v45, v47, v20 + 1, -1);
  v22 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  v23 = UrlUnEscapeWrapper(v22);
  std::wstring::_Tidy_deallocate(v47);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v23,
      v33);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v45);
    v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v24,
      v36[0]);
    std::_Deallocate<16>(v36[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v25,
      v37[0]);
    std::_Deallocate<16>(v37[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v26,
      *(_QWORD *)v38);
    std::_Deallocate<16>(*(_QWORD *)v38, 48);
    if ( v34 )
      CoUninitialize();
    return (unsigned int)v23;
  }
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v39);
  if ( v40 == v41 )
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v39, v40, v44);
  else
    std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v39, v44);
  v27 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v46, v39);
  v28 = v27;
  if ( v27 >= 0 )
  {
    std::vector<std::wstring>::_Tidy(v39);
    std::wstring::_Tidy_deallocate(v44);
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x953,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
    (const char *)(unsigned int)v27,
    v33);
  std::vector<std::wstring>::_Tidy(v39);
  std::wstring::_Tidy_deallocate(v44);
  std::wstring::_Tidy_deallocate(v45);
  v46[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v46);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v29,
    v36[0]);
  std::_Deallocate<16>(v36[0], 48);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v30,
    v37[0]);
  std::_Deallocate<16>(v37[0], 48);
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v31,
    *(_QWORD *)v38);
  std::_Deallocate<16>(*(_QWORD *)v38, 48);
  if ( v34 )
    CoUninitialize();
  return v28;
}

```

## disassembly

```asm
0x180134578  mov     [rsp+arg_0], rbx
0x18013457d  mov     [rsp+arg_8], rsi
0x180134582  push    rdi
0x180134583  sub     rsp, 150h
0x18013458a  mov     rax, cs:__security_cookie
0x180134591  xor     rax, rsp
0x180134594  mov     [rsp+158h+var_18], rax
0x18013459c  lea     rcx, [rsp+158h+var_128]; this
0x1801345a1  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x1801345a6  nop
0x1801345a7  lea     rcx, [rsp+158h+var_100]
0x1801345ac  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1801345b1  nop
0x1801345b2  lea     rcx, [rsp+158h+var_110]
0x1801345b7  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1801345bc  nop
0x1801345bd  lea     r9, [rsp+158h+var_100]
0x1801345c2  lea     r8, [rsp+158h+var_110]
0x1801345c7  lea     rdx, aWifi; "WiFi"
0x1801345ce  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x1801345d3  mov     edi, eax
0x1801345d5  test    eax, eax
0x1801345d7  jns     short loc_180134643
0x1801345d9  mov     rcx, [rsp+158h]; this
0x1801345e1  mov     r9d, eax; char *
0x1801345e4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801345eb  mov     edx, 937h; void *
0x1801345f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801345f5  nop
0x1801345f6  mov     rdx, [rsp+158h+var_110]
0x1801345fb  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134600  mov     ebx, 30h ; '0'
0x180134605  mov     edx, ebx
0x180134607  mov     rcx, [rsp+158h+var_110]
0x18013460c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180134611  nop
0x180134612  mov     rdx, qword ptr [rsp+158h+var_100]
0x180134617  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013461c  mov     edx, ebx
0x18013461e  mov     rcx, qword ptr [rsp+158h+var_100]
0x180134623  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180134628  nop
0x180134629  cmp     [rsp+158h+var_128], 0
0x18013462e  jz      short loc_18013463C
0x180134630  call    cs:__imp_CoUninitialize
0x180134637  nop     dword ptr [rax+rax+00h]
0x18013463c  mov     eax, edi
0x18013463e  jmp     loc_180134B48
0x180134643  lea     rdx, [rsp+158h+var_110]
0x180134648  lea     rcx, [rsp+158h+var_120]
0x18013464d  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x180134652  nop
0x180134653  mov     r9, qword ptr [rsp+158h+var_100]
0x180134658  mov     qword ptr [rsp+158h+var_138], r9; int
0x18013465d  mov     r9, [r9]
0x180134660  mov     r8, [rsp+158h+var_120]
0x180134665  lea     rdx, [rsp+158h+var_D0]
0x18013466d  lea     rcx, [rsp+158h+var_120]
0x180134672  call    ??$insert@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@1@Z; std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x180134677  cmp     [rsp+158h+var_118], 0
0x18013467d  jnz     short loc_1801346E3
0x18013467f  mov     rdx, [rsp+158h+var_120]
0x180134684  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134689  mov     ebx, 30h ; '0'
0x18013468e  mov     edx, ebx
0x180134690  mov     rcx, [rsp+158h+var_120]
0x180134695  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013469a  nop
0x18013469b  mov     rdx, [rsp+158h+var_110]
0x1801346a0  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801346a5  mov     edx, ebx
0x1801346a7  mov     rcx, [rsp+158h+var_110]
0x1801346ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801346b1  nop
0x1801346b2  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801346b7  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801346bc  mov     edx, ebx
0x1801346be  mov     rcx, qword ptr [rsp+158h+var_100]
0x1801346c3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801346c8  nop
0x1801346c9  cmp     [rsp+158h+var_128], 0
0x1801346ce  jz      short loc_1801346DC
0x1801346d0  call    cs:__imp_CoUninitialize
0x1801346d7  nop     dword ptr [rax+rax+00h]
0x1801346dc  xor     eax, eax
0x1801346de  jmp     loc_180134B48
0x1801346e3  lea     r8, aWifiprofilesta; "WifiProfilesTable"
0x1801346ea  lea     rdx, aWifiProfiles; "WiFi profiles"
0x1801346f1  lea     rcx, [rsp+158h+var_88]; this
0x1801346f9  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x1801346fe  nop
0x1801346ff  lea     rax, aProfile; "Profile"
0x180134706  mov     [rsp+158h+var_D8], rax
0x18013470e  mov     [rsp+158h+var_124], 28h ; '('
0x180134716  lea     r8, [rsp+158h+var_120]
0x18013471b  lea     rdx, [rsp+158h+var_124]
0x180134720  lea     rcx, [rsp+158h+var_C8]
0x180134728  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x18013472d  mov     rbx, rax
0x180134730  lea     r8, [rsp+158h+var_D0]
0x180134738  lea     rdx, [rsp+158h+var_D8]
0x180134740  lea     rcx, [rsp+158h+var_F0]
0x180134745  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18013474a  nop
0x18013474b  mov     r9, rbx
0x18013474e  mov     r8, rax
0x180134751  lea     rdx, aOnlyProfilesMa; "Only profiles managed by this MDM conne"...
0x180134758  lea     rcx, [rsp+158h+var_88]
0x180134760  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x180134765  mov     edi, eax
0x180134767  lea     rcx, [rsp+158h+var_F0]
0x18013476c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180134771  nop
0x180134772  lea     rcx, [rsp+158h+var_C8]
0x18013477a  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x18013477f  test    edi, edi
0x180134781  jns     loc_180134825
0x180134787  mov     rcx, [rsp+158h]; this
0x18013478f  mov     r9d, edi; char *
0x180134792  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180134799  mov     edx, 947h; void *
0x18013479e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801347a3  nop
0x1801347a4  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801347ab  mov     [rsp+158h+var_88], rax
0x1801347b3  lea     rcx, [rsp+158h+var_88]; this
0x1801347bb  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801347c0  nop
0x1801347c1  mov     rdx, [rsp+158h+var_120]
0x1801347c6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801347cb  mov     ebx, 30h ; '0'
0x1801347d0  mov     edx, ebx
0x1801347d2  mov     rcx, [rsp+158h+var_120]
0x1801347d7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801347dc  nop
0x1801347dd  mov     rdx, [rsp+158h+var_110]
0x1801347e2  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801347e7  mov     edx, ebx
0x1801347e9  mov     rcx, [rsp+158h+var_110]
0x1801347ee  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801347f3  nop
0x1801347f4  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801347f9  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801347fe  mov     edx, ebx
0x180134800  mov     rcx, qword ptr [rsp+158h+var_100]
0x180134805  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013480a  nop
0x18013480b  cmp     [rsp+158h+var_128], 0
0x180134810  jz      short loc_18013481E
0x180134812  call    cs:__imp_CoUninitialize
0x180134819  nop     dword ptr [rax+rax+00h]
0x18013481e  mov     eax, edi
0x180134820  jmp     loc_180134B48
0x180134825  mov     rdi, [rsp+158h+var_120]
0x18013482a  mov     rbx, [rdi]
0x18013482d  cmp     rbx, rdi
0x180134830  jnz     loc_1801348B7
0x180134836  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013483d  mov     [rsp+158h+var_88], rax
0x180134845  lea     rcx, [rsp+158h+var_88]; this
0x18013484d  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180134852  nop
0x180134853  mov     rdx, [rsp+158h+var_120]
0x180134858  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013485d  mov     ebx, 30h ; '0'
0x180134862  mov     edx, ebx
0x180134864  mov     rcx, [rsp+158h+var_120]
0x180134869  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013486e  nop
0x18013486f  mov     rdx, [rsp+158h+var_110]
0x180134874  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134879  mov     edx, ebx
0x18013487b  mov     rcx, [rsp+158h+var_110]
0x180134880  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180134885  nop
0x180134886  mov     rdx, qword ptr [rsp+158h+var_100]
0x18013488b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134890  mov     edx, ebx
0x180134892  mov     rcx, qword ptr [rsp+158h+var_100]
0x180134897  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013489c  nop
0x18013489d  cmp     [rsp+158h+var_128], 0
0x1801348a2  jz      short loc_1801348B0
0x1801348a4  call    cs:__imp_CoUninitialize
0x1801348ab  nop     dword ptr [rax+rax+00h]
0x1801348b0  xor     eax, eax
0x1801348b2  jmp     loc_180134B48
0x1801348b7  lea     rdx, [rbx+10h]
0x1801348bb  lea     rcx, [rsp+158h+var_A8]
0x1801348c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801348c8  nop
0x1801348c9  mov     edx, 2Fh ; '/'
0x1801348ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801348d2  lea     rcx, [rsp+158h+var_A8]
0x1801348da  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x1801348df  mov     rsi, rax
0x1801348e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801348e6  jz      loc_180134B2F
0x1801348ec  lea     rcx, [rsp+158h+var_C8]
0x1801348f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801348f9  nop
0x1801348fa  lea     r8, [rsi+1]
0x1801348fe  or      r9, 0FFFFFFFFFFFFFFFFh
0x180134902  lea     rdx, [rsp+158h+var_38]
0x18013490a  lea     rcx, [rsp+158h+var_A8]
0x180134912  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180134917  mov     rcx, rax
0x18013491a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013491f  lea     rdx, [rsp+158h+var_C8]
0x180134927  mov     rcx, rax; pszUrl
0x18013492a  call    ?UrlUnEscapeWrapper@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UrlUnEscapeWrapper(ushort const *,std::wstring &)
0x18013492f  mov     esi, eax
0x180134931  lea     rcx, [rsp+158h+var_38]
0x180134939  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013493e  test    esi, esi
0x180134940  jns     loc_180134A00
0x180134946  mov     rcx, [rsp+158h]; this
0x18013494e  mov     r9d, esi; char *
0x180134951  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180134958  mov     edx, 94Fh; void *
0x18013495d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134962  nop
0x180134963  lea     rcx, [rsp+158h+var_C8]
0x18013496b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134970  nop
0x180134971  lea     rcx, [rsp+158h+var_A8]
0x180134979  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013497e  nop
0x18013497f  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180134986  mov     [rsp+158h+var_88], rax
0x18013498e  lea     rcx, [rsp+158h+var_88]; this
0x180134996  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013499b  nop
0x18013499c  mov     rdx, [rsp+158h+var_120]
0x1801349a1  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801349a6  mov     ebx, 30h ; '0'
0x1801349ab  mov     edx, ebx
0x1801349ad  mov     rcx, [rsp+158h+var_120]
0x1801349b2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801349b7  nop
0x1801349b8  mov     rdx, [rsp+158h+var_110]
0x1801349bd  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801349c2  mov     edx, ebx
0x1801349c4  mov     rcx, [rsp+158h+var_110]
0x1801349c9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801349ce  nop
0x1801349cf  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801349d4  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801349d9  mov     edx, ebx
0x1801349db  mov     rcx, qword ptr [rsp+158h+var_100]
0x1801349e0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801349e5  nop
0x1801349e6  cmp     [rsp+158h+var_128], 0
0x1801349eb  jz      short loc_1801349F9
0x1801349ed  call    cs:__imp_CoUninitialize
0x1801349f4  nop     dword ptr [rax+rax+00h]
0x1801349f9  mov     eax, esi
0x1801349fb  jmp     loc_180134B48
0x180134a00  lea     rcx, [rsp+158h+var_F0]
0x180134a05  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180134a0a  nop
0x180134a0b  mov     rdx, [rsp+158h+var_E8]
0x180134a10  lea     rcx, [rsp+158h+var_F0]
0x180134a15  cmp     rdx, [rsp+158h+var_E0]
0x180134a1a  jz      short loc_180134A2B
0x180134a1c  lea     rdx, [rsp+158h+var_C8]
0x180134a24  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x180134a29  jmp     short loc_180134A38
0x180134a2b  lea     r8, [rsp+158h+var_C8]
0x180134a33  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180134a38  lea     rdx, [rsp+158h+var_F0]
0x180134a3d  lea     rcx, [rsp+158h+var_88]
0x180134a45  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x180134a4a  mov     esi, eax
0x180134a4c  test    eax, eax
0x180134a4e  jns     loc_180134B16
0x180134a54  mov     rcx, [rsp+158h]; this
0x180134a5c  mov     r9d, eax; char *
0x180134a5f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180134a66  mov     edx, 953h; void *
0x180134a6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134a70  nop
0x180134a71  lea     rcx, [rsp+158h+var_F0]
0x180134a76  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180134a7b  nop
0x180134a7c  lea     rcx, [rsp+158h+var_C8]
0x180134a84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134a89  nop
0x180134a8a  lea     rcx, [rsp+158h+var_A8]
0x180134a92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134a97  nop
0x180134a98  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180134a9f  mov     [rsp+158h+var_88], rax
0x180134aa7  lea     rcx, [rsp+158h+var_88]; this
0x180134aaf  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180134ab4  nop
0x180134ab5  mov     rdx, [rsp+158h+var_120]
0x180134aba  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134abf  mov     ebx, 30h ; '0'
0x180134ac4  mov     edx, ebx
  ... truncated ...
```
