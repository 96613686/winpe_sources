# WriteVPNProfiles(void)

- ea: `0x180133f7c`
- end: `0x180134572`
- name: `?WriteVPNProfiles@@YAJXZ`
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
- `0x180133f7c`
- `0x18013944c`
- `0x18013a39c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134034`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801340d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134216`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801342a8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801343f1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013450a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134034`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801340d4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180134216`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801342a8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801343f1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013450a`

## string_xrefs

- `0x180133fe8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180134196`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180134355`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180134463`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 WriteVPNProfiles(void)
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
         (__int64)L"VPNv2",
         (int)v37,
         (int)v38);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90A,
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
    L"VPN profiles",
    L"VPNProfilesTable");
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
      (void *)0x91A,
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
      (void *)0x922,
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
    (void *)0x926,
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
0x180133f7c  mov     [rsp+arg_0], rbx
0x180133f81  mov     [rsp+arg_8], rsi
0x180133f86  push    rdi
0x180133f87  sub     rsp, 150h
0x180133f8e  mov     rax, cs:__security_cookie
0x180133f95  xor     rax, rsp
0x180133f98  mov     [rsp+158h+var_18], rax
0x180133fa0  lea     rcx, [rsp+158h+var_128]; this
0x180133fa5  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x180133faa  nop
0x180133fab  lea     rcx, [rsp+158h+var_100]
0x180133fb0  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180133fb5  nop
0x180133fb6  lea     rcx, [rsp+158h+var_110]
0x180133fbb  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180133fc0  nop
0x180133fc1  lea     r9, [rsp+158h+var_100]
0x180133fc6  lea     r8, [rsp+158h+var_110]
0x180133fcb  lea     rdx, aVpnv2; "VPNv2"
0x180133fd2  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x180133fd7  mov     edi, eax
0x180133fd9  test    eax, eax
0x180133fdb  jns     short loc_180134047
0x180133fdd  mov     rcx, [rsp+158h]; this
0x180133fe5  mov     r9d, eax; char *
0x180133fe8  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180133fef  mov     edx, 90Ah; void *
0x180133ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133ff9  nop
0x180133ffa  mov     rdx, [rsp+158h+var_110]
0x180133fff  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134004  mov     ebx, 30h ; '0'
0x180134009  mov     edx, ebx
0x18013400b  mov     rcx, [rsp+158h+var_110]
0x180134010  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180134015  nop
0x180134016  mov     rdx, qword ptr [rsp+158h+var_100]
0x18013401b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134020  mov     edx, ebx
0x180134022  mov     rcx, qword ptr [rsp+158h+var_100]
0x180134027  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013402c  nop
0x18013402d  cmp     [rsp+158h+var_128], 0
0x180134032  jz      short loc_180134040
0x180134034  call    cs:__imp_CoUninitialize
0x18013403b  nop     dword ptr [rax+rax+00h]
0x180134040  mov     eax, edi
0x180134042  jmp     loc_18013454C
0x180134047  lea     rdx, [rsp+158h+var_110]
0x18013404c  lea     rcx, [rsp+158h+var_120]
0x180134051  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x180134056  nop
0x180134057  mov     r9, qword ptr [rsp+158h+var_100]
0x18013405c  mov     qword ptr [rsp+158h+var_138], r9; int
0x180134061  mov     r9, [r9]
0x180134064  mov     r8, [rsp+158h+var_120]
0x180134069  lea     rdx, [rsp+158h+var_D0]
0x180134071  lea     rcx, [rsp+158h+var_120]
0x180134076  call    ??$insert@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@1@Z; std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x18013407b  cmp     [rsp+158h+var_118], 0
0x180134081  jnz     short loc_1801340E7
0x180134083  mov     rdx, [rsp+158h+var_120]
0x180134088  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013408d  mov     ebx, 30h ; '0'
0x180134092  mov     edx, ebx
0x180134094  mov     rcx, [rsp+158h+var_120]
0x180134099  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013409e  nop
0x18013409f  mov     rdx, [rsp+158h+var_110]
0x1801340a4  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801340a9  mov     edx, ebx
0x1801340ab  mov     rcx, [rsp+158h+var_110]
0x1801340b0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801340b5  nop
0x1801340b6  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801340bb  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801340c0  mov     edx, ebx
0x1801340c2  mov     rcx, qword ptr [rsp+158h+var_100]
0x1801340c7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801340cc  nop
0x1801340cd  cmp     [rsp+158h+var_128], 0
0x1801340d2  jz      short loc_1801340E0
0x1801340d4  call    cs:__imp_CoUninitialize
0x1801340db  nop     dword ptr [rax+rax+00h]
0x1801340e0  xor     eax, eax
0x1801340e2  jmp     loc_18013454C
0x1801340e7  lea     r8, aVpnprofilestab; "VPNProfilesTable"
0x1801340ee  lea     rdx, aVpnProfiles; "VPN profiles"
0x1801340f5  lea     rcx, [rsp+158h+var_88]; this
0x1801340fd  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180134102  nop
0x180134103  lea     rax, aProfile; "Profile"
0x18013410a  mov     [rsp+158h+var_D8], rax
0x180134112  mov     [rsp+158h+var_124], 28h ; '('
0x18013411a  lea     r8, [rsp+158h+var_120]
0x18013411f  lea     rdx, [rsp+158h+var_124]
0x180134124  lea     rcx, [rsp+158h+var_C8]
0x18013412c  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x180134131  mov     rbx, rax
0x180134134  lea     r8, [rsp+158h+var_D0]
0x18013413c  lea     rdx, [rsp+158h+var_D8]
0x180134144  lea     rcx, [rsp+158h+var_F0]
0x180134149  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18013414e  nop
0x18013414f  mov     r9, rbx
0x180134152  mov     r8, rax
0x180134155  lea     rdx, aOnlyProfilesMa; "Only profiles managed by this MDM conne"...
0x18013415c  lea     rcx, [rsp+158h+var_88]
0x180134164  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x180134169  mov     edi, eax
0x18013416b  lea     rcx, [rsp+158h+var_F0]
0x180134170  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180134175  nop
0x180134176  lea     rcx, [rsp+158h+var_C8]
0x18013417e  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x180134183  test    edi, edi
0x180134185  jns     loc_180134229
0x18013418b  mov     rcx, [rsp+158h]; this
0x180134193  mov     r9d, edi; char *
0x180134196  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013419d  mov     edx, 91Ah; void *
0x1801341a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801341a7  nop
0x1801341a8  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801341af  mov     [rsp+158h+var_88], rax
0x1801341b7  lea     rcx, [rsp+158h+var_88]; this
0x1801341bf  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801341c4  nop
0x1801341c5  mov     rdx, [rsp+158h+var_120]
0x1801341ca  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801341cf  mov     ebx, 30h ; '0'
0x1801341d4  mov     edx, ebx
0x1801341d6  mov     rcx, [rsp+158h+var_120]
0x1801341db  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801341e0  nop
0x1801341e1  mov     rdx, [rsp+158h+var_110]
0x1801341e6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801341eb  mov     edx, ebx
0x1801341ed  mov     rcx, [rsp+158h+var_110]
0x1801341f2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801341f7  nop
0x1801341f8  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801341fd  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134202  mov     edx, ebx
0x180134204  mov     rcx, qword ptr [rsp+158h+var_100]
0x180134209  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013420e  nop
0x18013420f  cmp     [rsp+158h+var_128], 0
0x180134214  jz      short loc_180134222
0x180134216  call    cs:__imp_CoUninitialize
0x18013421d  nop     dword ptr [rax+rax+00h]
0x180134222  mov     eax, edi
0x180134224  jmp     loc_18013454C
0x180134229  mov     rdi, [rsp+158h+var_120]
0x18013422e  mov     rbx, [rdi]
0x180134231  cmp     rbx, rdi
0x180134234  jnz     loc_1801342BB
0x18013423a  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180134241  mov     [rsp+158h+var_88], rax
0x180134249  lea     rcx, [rsp+158h+var_88]; this
0x180134251  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180134256  nop
0x180134257  mov     rdx, [rsp+158h+var_120]
0x18013425c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134261  mov     ebx, 30h ; '0'
0x180134266  mov     edx, ebx
0x180134268  mov     rcx, [rsp+158h+var_120]
0x18013426d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180134272  nop
0x180134273  mov     rdx, [rsp+158h+var_110]
0x180134278  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013427d  mov     edx, ebx
0x18013427f  mov     rcx, [rsp+158h+var_110]
0x180134284  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180134289  nop
0x18013428a  mov     rdx, qword ptr [rsp+158h+var_100]
0x18013428f  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180134294  mov     edx, ebx
0x180134296  mov     rcx, qword ptr [rsp+158h+var_100]
0x18013429b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801342a0  nop
0x1801342a1  cmp     [rsp+158h+var_128], 0
0x1801342a6  jz      short loc_1801342B4
0x1801342a8  call    cs:__imp_CoUninitialize
0x1801342af  nop     dword ptr [rax+rax+00h]
0x1801342b4  xor     eax, eax
0x1801342b6  jmp     loc_18013454C
0x1801342bb  lea     rdx, [rbx+10h]
0x1801342bf  lea     rcx, [rsp+158h+var_A8]
0x1801342c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801342cc  nop
0x1801342cd  mov     edx, 2Fh ; '/'
0x1801342d2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801342d6  lea     rcx, [rsp+158h+var_A8]
0x1801342de  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x1801342e3  mov     rsi, rax
0x1801342e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801342ea  jz      loc_180134533
0x1801342f0  lea     rcx, [rsp+158h+var_C8]
0x1801342f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801342fd  nop
0x1801342fe  lea     r8, [rsi+1]
0x180134302  or      r9, 0FFFFFFFFFFFFFFFFh
0x180134306  lea     rdx, [rsp+158h+var_38]
0x18013430e  lea     rcx, [rsp+158h+var_A8]
0x180134316  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18013431b  mov     rcx, rax
0x18013431e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180134323  lea     rdx, [rsp+158h+var_C8]
0x18013432b  mov     rcx, rax; pszUrl
0x18013432e  call    ?UrlUnEscapeWrapper@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UrlUnEscapeWrapper(ushort const *,std::wstring &)
0x180134333  mov     esi, eax
0x180134335  lea     rcx, [rsp+158h+var_38]
0x18013433d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134342  test    esi, esi
0x180134344  jns     loc_180134404
0x18013434a  mov     rcx, [rsp+158h]; this
0x180134352  mov     r9d, esi; char *
0x180134355  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013435c  mov     edx, 922h; void *
0x180134361  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134366  nop
0x180134367  lea     rcx, [rsp+158h+var_C8]
0x18013436f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134374  nop
0x180134375  lea     rcx, [rsp+158h+var_A8]
0x18013437d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134382  nop
0x180134383  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013438a  mov     [rsp+158h+var_88], rax
0x180134392  lea     rcx, [rsp+158h+var_88]; this
0x18013439a  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013439f  nop
0x1801343a0  mov     rdx, [rsp+158h+var_120]
0x1801343a5  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801343aa  mov     ebx, 30h ; '0'
0x1801343af  mov     edx, ebx
0x1801343b1  mov     rcx, [rsp+158h+var_120]
0x1801343b6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801343bb  nop
0x1801343bc  mov     rdx, [rsp+158h+var_110]
0x1801343c1  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801343c6  mov     edx, ebx
0x1801343c8  mov     rcx, [rsp+158h+var_110]
0x1801343cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801343d2  nop
0x1801343d3  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801343d8  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801343dd  mov     edx, ebx
0x1801343df  mov     rcx, qword ptr [rsp+158h+var_100]
0x1801343e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801343e9  nop
0x1801343ea  cmp     [rsp+158h+var_128], 0
0x1801343ef  jz      short loc_1801343FD
0x1801343f1  call    cs:__imp_CoUninitialize
0x1801343f8  nop     dword ptr [rax+rax+00h]
0x1801343fd  mov     eax, esi
0x1801343ff  jmp     loc_18013454C
0x180134404  lea     rcx, [rsp+158h+var_F0]
0x180134409  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013440e  nop
0x18013440f  mov     rdx, [rsp+158h+var_E8]
0x180134414  lea     rcx, [rsp+158h+var_F0]
0x180134419  cmp     rdx, [rsp+158h+var_E0]
0x18013441e  jz      short loc_18013442F
0x180134420  lea     rdx, [rsp+158h+var_C8]
0x180134428  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18013442d  jmp     short loc_18013443C
0x18013442f  lea     r8, [rsp+158h+var_C8]
0x180134437  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18013443c  lea     rdx, [rsp+158h+var_F0]
0x180134441  lea     rcx, [rsp+158h+var_88]
0x180134449  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18013444e  mov     esi, eax
0x180134450  test    eax, eax
0x180134452  jns     loc_18013451A
0x180134458  mov     rcx, [rsp+158h]; this
0x180134460  mov     r9d, eax; char *
0x180134463  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013446a  mov     edx, 926h; void *
0x18013446f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134474  nop
0x180134475  lea     rcx, [rsp+158h+var_F0]
0x18013447a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18013447f  nop
0x180134480  lea     rcx, [rsp+158h+var_C8]
0x180134488  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013448d  nop
0x18013448e  lea     rcx, [rsp+158h+var_A8]
0x180134496  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013449b  nop
0x18013449c  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801344a3  mov     [rsp+158h+var_88], rax
0x1801344ab  lea     rcx, [rsp+158h+var_88]; this
0x1801344b3  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801344b8  nop
0x1801344b9  mov     rdx, [rsp+158h+var_120]
0x1801344be  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801344c3  mov     ebx, 30h ; '0'
0x1801344c8  mov     edx, ebx
  ... truncated ...
```
