# WriteVPNProfiles(void)

- ea: `0x180132118`
- end: `0x1801326e6`
- name: `?WriteVPNProfiles@@YAJXZ`
- size: `1486`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e5594`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180104270`
- `0x180104460`
- `0x1801044a8`
- `0x18010589c`
- `0x180105b28`
- `0x180120ce0`
- `0x180126a14`
- `0x180126a64`
- `0x1801271ec`
- `0x180127820`
- `0x1801278d0`
- `0x180127908`
- `0x1801279ac`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012a4fc`
- `0x1801312d0`
- `0x180132118`
- `0x1801373b8`
- `0x18013826c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801321d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013226a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801323a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013242e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132571`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132684`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801321d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013226a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801323a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013242e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132571`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132684`

## string_xrefs

- `0x180132184`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132326`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801324d5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801325dd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

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
  unsigned int **v9; // rbx
  _QWORD *v10; // rax
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
         v37,
         v38);
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
  v9 = (unsigned int **)std::vector<int>::vector<int>(v44, &v35, v36);
  v10 = (_QWORD *)std::vector<std::wstring>::vector<std::wstring>(v39, &v42, v43);
  v11 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
          (__int64)v46,
          (__int64)L"Only profiles managed by this MDM connection are displayed",
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
0x180132118  mov     [rsp+arg_0], rbx
0x18013211d  mov     [rsp+arg_8], rsi
0x180132122  push    rdi
0x180132123  sub     rsp, 150h
0x18013212a  mov     rax, cs:__security_cookie
0x180132131  xor     rax, rsp
0x180132134  mov     [rsp+158h+var_18], rax
0x18013213c  lea     rcx, [rsp+158h+var_128]; this
0x180132141  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x180132146  nop
0x180132147  lea     rcx, [rsp+158h+var_100]
0x18013214c  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180132151  nop
0x180132152  lea     rcx, [rsp+158h+var_110]
0x180132157  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18013215c  nop
0x18013215d  lea     r9, [rsp+158h+var_100]
0x180132162  lea     r8, [rsp+158h+var_110]
0x180132167  lea     rdx, aVpnv2; "VPNv2"
0x18013216e  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x180132173  mov     edi, eax
0x180132175  test    eax, eax
0x180132177  jns     short loc_1801321DD
0x180132179  mov     rcx, [rsp+158h]; this
0x180132181  mov     r9d, eax; char *
0x180132184  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013218b  mov     edx, 90Ah; void *
0x180132190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132195  nop
0x180132196  mov     rdx, [rsp+158h+var_110]
0x18013219b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801321a0  mov     ebx, 30h ; '0'
0x1801321a5  mov     edx, ebx
0x1801321a7  mov     rcx, [rsp+158h+var_110]
0x1801321ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801321b1  nop
0x1801321b2  mov     rdx, qword ptr [rsp+158h+var_100]
0x1801321b7  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801321bc  mov     edx, ebx
0x1801321be  mov     rcx, qword ptr [rsp+158h+var_100]
0x1801321c3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801321c8  nop
0x1801321c9  cmp     [rsp+158h+var_128], 0
0x1801321ce  jz      short loc_1801321D6
0x1801321d0  call    cs:__imp_CoUninitialize
0x1801321d6  mov     eax, edi
0x1801321d8  jmp     loc_1801326C0
0x1801321dd  lea     rdx, [rsp+158h+var_110]
0x1801321e2  lea     rcx, [rsp+158h+var_120]
0x1801321e7  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x1801321ec  nop
0x1801321ed  mov     r9, qword ptr [rsp+158h+var_100]
0x1801321f2  mov     qword ptr [rsp+158h+var_138], r9; int
0x1801321f7  mov     r9, [r9]
0x1801321fa  mov     r8, [rsp+158h+var_120]
0x1801321ff  lea     rdx, [rsp+158h+var_D0]
0x180132207  lea     rcx, [rsp+158h+var_120]
0x18013220c  call    ??$insert@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@$0A@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V21@1@Z; std::list<std::wstring>::insert<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,0>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>)
0x180132211  cmp     [rsp+158h+var_118], 0
0x180132217  jnz     short loc_180132277
0x180132219  mov     rdx, [rsp+158h+var_120]
0x18013221e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132223  mov     ebx, 30h ; '0'
0x180132228  mov     edx, ebx
0x18013222a  mov     rcx, [rsp+158h+var_120]
0x18013222f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132234  nop
0x180132235  mov     rdx, [rsp+158h+var_110]
0x18013223a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013223f  mov     edx, ebx
0x180132241  mov     rcx, [rsp+158h+var_110]
0x180132246  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013224b  nop
0x18013224c  mov     rdx, qword ptr [rsp+158h+var_100]
0x180132251  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132256  mov     edx, ebx
0x180132258  mov     rcx, qword ptr [rsp+158h+var_100]
0x18013225d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132262  nop
0x180132263  cmp     [rsp+158h+var_128], 0
0x180132268  jz      short loc_180132270
0x18013226a  call    cs:__imp_CoUninitialize
0x180132270  xor     eax, eax
0x180132272  jmp     loc_1801326C0
0x180132277  lea     r8, aVpnprofilestab; "VPNProfilesTable"
0x18013227e  lea     rdx, aVpnProfiles; "VPN profiles"
0x180132285  lea     rcx, [rsp+158h+var_88]; this
0x18013228d  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180132292  nop
0x180132293  lea     rax, aProfile; "Profile"
0x18013229a  mov     [rsp+158h+var_D8], rax
0x1801322a2  mov     [rsp+158h+var_124], 28h ; '('
0x1801322aa  lea     r8, [rsp+158h+var_120]
0x1801322af  lea     rdx, [rsp+158h+var_124]
0x1801322b4  lea     rcx, [rsp+158h+var_C8]
0x1801322bc  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x1801322c1  mov     rbx, rax
0x1801322c4  lea     r8, [rsp+158h+var_D0]
0x1801322cc  lea     rdx, [rsp+158h+var_D8]
0x1801322d4  lea     rcx, [rsp+158h+var_F0]
0x1801322d9  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x1801322de  nop
0x1801322df  mov     r9, rbx
0x1801322e2  mov     r8, rax
0x1801322e5  lea     rdx, aOnlyProfilesMa; "Only profiles managed by this MDM conne"...
0x1801322ec  lea     rcx, [rsp+158h+var_88]
0x1801322f4  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x1801322f9  mov     edi, eax
0x1801322fb  lea     rcx, [rsp+158h+var_F0]
0x180132300  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180132305  nop
0x180132306  lea     rcx, [rsp+158h+var_C8]
0x18013230e  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x180132313  test    edi, edi
0x180132315  jns     loc_1801323B3
0x18013231b  mov     rcx, [rsp+158h]; this
0x180132323  mov     r9d, edi; char *
0x180132326  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013232d  mov     edx, 91Ah; void *
0x180132332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132337  nop
0x180132338  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013233f  mov     [rsp+158h+var_88], rax
0x180132347  lea     rcx, [rsp+158h+var_88]; this
0x18013234f  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180132354  nop
0x180132355  mov     rdx, [rsp+158h+var_120]
0x18013235a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013235f  mov     ebx, 30h ; '0'
0x180132364  mov     edx, ebx
0x180132366  mov     rcx, [rsp+158h+var_120]
0x18013236b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132370  nop
0x180132371  mov     rdx, [rsp+158h+var_110]
0x180132376  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013237b  mov     edx, ebx
0x18013237d  mov     rcx, [rsp+158h+var_110]
0x180132382  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132387  nop
0x180132388  mov     rdx, qword ptr [rsp+158h+var_100]
0x18013238d  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132392  mov     edx, ebx
0x180132394  mov     rcx, qword ptr [rsp+158h+var_100]
0x180132399  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013239e  nop
0x18013239f  cmp     [rsp+158h+var_128], 0
0x1801323a4  jz      short loc_1801323AC
0x1801323a6  call    cs:__imp_CoUninitialize
0x1801323ac  mov     eax, edi
0x1801323ae  jmp     loc_1801326C0
0x1801323b3  mov     rdi, [rsp+158h+var_120]
0x1801323b8  mov     rbx, [rdi]
0x1801323bb  cmp     rbx, rdi
0x1801323be  jnz     short loc_18013243B
0x1801323c0  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801323c7  mov     [rsp+158h+var_88], rax
0x1801323cf  lea     rcx, [rsp+158h+var_88]; this
0x1801323d7  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801323dc  nop
0x1801323dd  mov     rdx, [rsp+158h+var_120]
0x1801323e2  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801323e7  mov     ebx, 30h ; '0'
0x1801323ec  mov     edx, ebx
0x1801323ee  mov     rcx, [rsp+158h+var_120]
0x1801323f3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801323f8  nop
0x1801323f9  mov     rdx, [rsp+158h+var_110]
0x1801323fe  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132403  mov     edx, ebx
0x180132405  mov     rcx, [rsp+158h+var_110]
0x18013240a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013240f  nop
0x180132410  mov     rdx, qword ptr [rsp+158h+var_100]
0x180132415  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013241a  mov     edx, ebx
0x18013241c  mov     rcx, qword ptr [rsp+158h+var_100]
0x180132421  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132426  nop
0x180132427  cmp     [rsp+158h+var_128], 0
0x18013242c  jz      short loc_180132434
0x18013242e  call    cs:__imp_CoUninitialize
0x180132434  xor     eax, eax
0x180132436  jmp     loc_1801326C0
0x18013243b  lea     rdx, [rbx+10h]
0x18013243f  lea     rcx, [rsp+158h+var_A8]
0x180132447  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013244c  nop
0x18013244d  mov     edx, 2Fh ; '/'
0x180132452  or      r8, 0FFFFFFFFFFFFFFFFh
0x180132456  lea     rcx, [rsp+158h+var_A8]
0x18013245e  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x180132463  mov     rsi, rax
0x180132466  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18013246a  jz      loc_1801326A7
0x180132470  lea     rcx, [rsp+158h+var_C8]
0x180132478  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013247d  nop
0x18013247e  lea     r8, [rsi+1]
0x180132482  or      r9, 0FFFFFFFFFFFFFFFFh
0x180132486  lea     rdx, [rsp+158h+var_38]
0x18013248e  lea     rcx, [rsp+158h+var_A8]
0x180132496  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18013249b  mov     rcx, rax
0x18013249e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801324a3  lea     rdx, [rsp+158h+var_C8]
0x1801324ab  mov     rcx, rax; pszUrl
0x1801324ae  call    ?UrlUnEscapeWrapper@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UrlUnEscapeWrapper(ushort const *,std::wstring &)
0x1801324b3  mov     esi, eax
0x1801324b5  lea     rcx, [rsp+158h+var_38]
0x1801324bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801324c2  test    esi, esi
0x1801324c4  jns     loc_18013257E
0x1801324ca  mov     rcx, [rsp+158h]; this
0x1801324d2  mov     r9d, esi; char *
0x1801324d5  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801324dc  mov     edx, 922h; void *
0x1801324e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801324e6  nop
0x1801324e7  lea     rcx, [rsp+158h+var_C8]
0x1801324ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801324f4  nop
0x1801324f5  lea     rcx, [rsp+158h+var_A8]
0x1801324fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132502  nop
0x180132503  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013250a  mov     [rsp+158h+var_88], rax
0x180132512  lea     rcx, [rsp+158h+var_88]; this
0x18013251a  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013251f  nop
0x180132520  mov     rdx, [rsp+158h+var_120]
0x180132525  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013252a  mov     ebx, 30h ; '0'
0x18013252f  mov     edx, ebx
0x180132531  mov     rcx, [rsp+158h+var_120]
0x180132536  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013253b  nop
0x18013253c  mov     rdx, [rsp+158h+var_110]
0x180132541  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180132546  mov     edx, ebx
0x180132548  mov     rcx, [rsp+158h+var_110]
0x18013254d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132552  nop
0x180132553  mov     rdx, qword ptr [rsp+158h+var_100]
0x180132558  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013255d  mov     edx, ebx
0x18013255f  mov     rcx, qword ptr [rsp+158h+var_100]
0x180132564  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180132569  nop
0x18013256a  cmp     [rsp+158h+var_128], 0
0x18013256f  jz      short loc_180132577
0x180132571  call    cs:__imp_CoUninitialize
0x180132577  mov     eax, esi
0x180132579  jmp     loc_1801326C0
0x18013257e  lea     rcx, [rsp+158h+var_F0]
0x180132583  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180132588  nop
0x180132589  mov     rdx, [rsp+158h+var_E8]
0x18013258e  lea     rcx, [rsp+158h+var_F0]
0x180132593  cmp     rdx, [rsp+158h+var_E0]
0x180132598  jz      short loc_1801325A9
0x18013259a  lea     rdx, [rsp+158h+var_C8]
0x1801325a2  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x1801325a7  jmp     short loc_1801325B6
0x1801325a9  lea     r8, [rsp+158h+var_C8]
0x1801325b1  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1801325b6  lea     rdx, [rsp+158h+var_F0]
0x1801325bb  lea     rcx, [rsp+158h+var_88]
0x1801325c3  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x1801325c8  mov     esi, eax
0x1801325ca  test    eax, eax
0x1801325cc  jns     loc_18013268E
0x1801325d2  mov     rcx, [rsp+158h]; this
0x1801325da  mov     r9d, eax; char *
0x1801325dd  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801325e4  mov     edx, 926h; void *
0x1801325e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801325ee  nop
0x1801325ef  lea     rcx, [rsp+158h+var_F0]
0x1801325f4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801325f9  nop
0x1801325fa  lea     rcx, [rsp+158h+var_C8]
0x180132602  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132607  nop
0x180132608  lea     rcx, [rsp+158h+var_A8]
0x180132610  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132615  nop
0x180132616  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013261d  mov     [rsp+158h+var_88], rax
0x180132625  lea     rcx, [rsp+158h+var_88]; this
0x18013262d  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180132632  nop
0x180132633  mov     rdx, [rsp+158h+var_120]
0x180132638  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013263d  mov     ebx, 30h ; '0'
0x180132642  mov     edx, ebx
0x180132644  mov     rcx, [rsp+158h+var_120]
0x180132649  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013264e  nop
0x18013264f  mov     rdx, [rsp+158h+var_110]
0x180132654  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
  ... truncated ...
```
