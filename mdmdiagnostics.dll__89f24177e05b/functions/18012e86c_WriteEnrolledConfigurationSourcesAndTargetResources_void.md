# WriteEnrolledConfigurationSourcesAndTargetResources(void)

- ea: `0x18012e86c`
- end: `0x18012ece2`
- name: `?WriteEnrolledConfigurationSourcesAndTargetResources@@YAJXZ`
- size: `1142`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e5594`
- `0x1800e6664`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ef5d8`
- `0x180104270`
- `0x1801058cc`
- `0x180105c40`
- `0x180120ce0`
- `0x180126a14`
- `0x180126a64`
- `0x1801279ac`
- `0x180127f78`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012e86c`
- `0x1801312d0`
- `0x180132d20`
- `0x1801373b8`
- `0x180138070`
- `0x18013b118`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012e9de`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012ea66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012ec39`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012e9de`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012ea66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012ec39`
- `DMCmnUtils!DmGetEnrollmentTypeName` at `0x18012eae8`
- `DMCmnUtils!DmGetEnrollmentTypeName` at `0x18012eae8`

## string_xrefs

- `0x18012e958`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e9c5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ec15`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012e895`: `Configuration source`
- `0x18012e8d6`: `Enrolled configuration sources and target resources`
- `0x18012e8cf`: `EnrolledConfigurationSourcesAndTargetResourcesTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 WriteEnrolledConfigurationSourcesAndTargetResources(void)
{
  int v0; // r14d
  unsigned int **v1; // rbx
  _QWORD *v2; // rax
  int v3; // ebx
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // esi
  _QWORD **v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *v10; // rbx
  __int64 *v11; // rdi
  __int64 *i; // rbx
  _QWORD **v13; // rcx
  _QWORD *v14; // rdi
  _QWORD *v15; // rbx
  const unsigned __int16 *EnrollmentTypeName; // rax
  int v17; // eax
  _QWORD **v18; // rcx
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  int v21; // [rsp+20h] [rbp-108h] BYREF
  _BYTE v22[8]; // [rsp+28h] [rbp-100h] BYREF
  __int64 v23; // [rsp+30h] [rbp-F8h]
  __int64 v24; // [rsp+38h] [rbp-F0h]
  __int128 v25; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v26[32]; // [rsp+50h] [rbp-D8h] BYREF
  _QWORD v27[10]; // [rsp+70h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-68h] BYREF
  _QWORD v29[4]; // [rsp+D0h] [rbp-58h] BYREF
  _QWORD v30[7]; // [rsp+F0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v0 = 0;
  v21 = 0;
  v29[0] = L"Configuration source";
  v29[1] = L"ID";
  v29[2] = L"Target";
  v29[3] = L"Resource";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v27,
    L"Enrolled configuration sources and target resources",
    L"EnrolledConfigurationSourcesAndTargetResourcesTable");
  v1 = (unsigned int **)std::vector<int>::vector<int>(v26, &si128, v29);
  v2 = (_QWORD *)std::vector<std::wstring>::vector<std::wstring>(v22, v29, v30);
  v3 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
         (__int64)v27,
         0,
         v2,
         v1);
  std::vector<std::wstring>::_Tidy(v22);
  std::vector<enum TpmCapabilityPT>::_Tidy(v26);
  if ( v3 >= 0 )
  {
    v25 = 0;
    std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::_Alloc_sentinel_and_proxy(&v25);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources((Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources *)&v21);
    v6 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(v5, &v25);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v11 = (__int64 *)v25;
      for ( i = *(__int64 **)v25; ; i = (__int64 *)*i )
      {
        if ( i == v11 )
        {
          if ( v21 )
          {
            CoUninitialize();
            v21 = 0;
          }
          v13 = (_QWORD **)v25;
          **(_QWORD **)(v25 + 8) = 0;
          v14 = *v13;
          if ( *v13 )
          {
            do
            {
              v15 = (_QWORD *)*v14;
              Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord((Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord *)(v14 + 2));
              std::_Deallocate<16>(v14, 120);
              v14 = v15;
            }
            while ( v15 );
          }
          std::_Deallocate<16>(v25, 120);
          v27[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
          Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v27);
          return 0;
        }
        std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v22);
        EnrollmentTypeName = DmGetEnrollmentTypeName(*((_DWORD *)i + 4));
        std::wstring::wstring(v26, EnrollmentTypeName);
        if ( v23 == v24 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v22, v23, v26);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v22, v26);
        std::wstring::_Tidy_deallocate(v26);
        std::wstring::wstring(v26, i + 3);
        if ( v23 == v24 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v22, v23, v26);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v22, v26);
        std::wstring::_Tidy_deallocate(v26);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(i + 7, v26);
        if ( v23 == v24 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v22, v23, v26);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v22, v26);
        std::wstring::_Tidy_deallocate(v26);
        std::wstring::wstring(v26, i + 11);
        if ( v23 == v24 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v22, v23, v26);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v22, v26);
        std::wstring::_Tidy_deallocate(v26);
        v17 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v27, v22);
        v7 = v17;
        if ( v17 < 0 )
          break;
        v0 |= 7u;
        std::vector<std::wstring>::_Tidy(v22);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F4,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v17,
        v21);
      std::vector<std::wstring>::_Tidy(v22);
      if ( v21 )
      {
        CoUninitialize();
        v21 = 0;
      }
      v18 = (_QWORD **)v25;
      **(_QWORD **)(v25 + 8) = 0;
      v19 = *v18;
      if ( *v18 )
      {
        do
        {
          v20 = (_QWORD *)*v19;
          Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord((Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord *)(v19 + 2));
          std::_Deallocate<16>(v19, 120);
          v19 = v20;
        }
        while ( v20 );
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6EA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v6,
        v21);
      if ( v21 )
      {
        CoUninitialize();
        v21 = 0;
      }
      v8 = (_QWORD **)v25;
      **(_QWORD **)(v25 + 8) = 0;
      v9 = *v8;
      if ( *v8 )
      {
        do
        {
          v10 = (_QWORD *)*v9;
          Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord((Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord *)(v9 + 2));
          std::_Deallocate<16>(v9, 120);
          v9 = v10;
        }
        while ( v10 );
      }
    }
    std::_Deallocate<16>(v25, 120);
    v27[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v27);
    return v7;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v3,
      v21);
    v27[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v27);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x18012e86c  mov     r11, rsp
0x18012e86f  push    rbx
0x18012e870  push    rsi
0x18012e871  push    rdi
0x18012e872  push    r14
0x18012e874  sub     rsp, 108h
0x18012e87b  mov     rax, cs:__security_cookie
0x18012e882  xor     rax, rsp
0x18012e885  mov     [rsp+128h+var_38], rax
0x18012e88d  xor     r14d, r14d
0x18012e890  mov     [rsp+128h+var_108], r14d; int
0x18012e895  lea     rax, aConfigurationS; "Configuration source"
0x18012e89c  mov     [r11-58h], rax
0x18012e8a0  lea     rax, aId; "ID"
0x18012e8a7  mov     [r11-50h], rax
0x18012e8ab  lea     rax, aTarget; "Target"
0x18012e8b2  mov     [r11-48h], rax
0x18012e8b6  lea     rax, aResource; "Resource"
0x18012e8bd  mov     [r11-40h], rax
0x18012e8c1  movdqa  xmm0, cs:__xmm@00000025000000090000001e00000018
0x18012e8c9  movdqu  xmmword ptr [r11-68h], xmm0
0x18012e8cf  lea     r8, aEnrolledconfig; "EnrolledConfigurationSourcesAndTargetRe"...
0x18012e8d6  lea     rdx, aEnrolledConfig; "Enrolled configuration sources and targ"...
0x18012e8dd  lea     rcx, [rsp+128h+var_B8]; this
0x18012e8e2  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x18012e8e7  nop
0x18012e8e8  lea     r8, [rsp+128h+var_58]
0x18012e8f0  lea     rdx, [rsp+128h+var_68]
0x18012e8f8  lea     rcx, [rsp+128h+var_D8]
0x18012e8fd  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x18012e902  mov     rbx, rax
0x18012e905  lea     r8, [rsp+128h+var_38]
0x18012e90d  lea     rdx, [rsp+128h+var_58]
0x18012e915  lea     rcx, [rsp+128h+var_100]
0x18012e91a  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18012e91f  nop
0x18012e920  mov     r9, rbx
0x18012e923  mov     r8, rax
0x18012e926  xor     edx, edx
0x18012e928  lea     rcx, [rsp+128h+var_B8]
0x18012e92d  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x18012e932  mov     ebx, eax
0x18012e934  lea     rcx, [rsp+128h+var_100]
0x18012e939  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012e93e  nop
0x18012e93f  lea     rcx, [rsp+128h+var_D8]
0x18012e944  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x18012e949  test    ebx, ebx
0x18012e94b  jns     short loc_18012E987
0x18012e94d  mov     rcx, [rsp+128h]; this
0x18012e955  mov     r9d, ebx; char *
0x18012e958  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012e95f  mov     edx, 6E6h; void *
0x18012e964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e969  nop
0x18012e96a  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012e971  mov     [rsp+128h+var_B8], rax
0x18012e976  lea     rcx, [rsp+128h+var_B8]; this
0x18012e97b  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012e980  mov     eax, ebx
0x18012e982  jmp     loc_18012ECC4
0x18012e987  xorps   xmm0, xmm0
0x18012e98a  movdqu  [rsp+128h+var_E8], xmm0
0x18012e990  lea     rcx, [rsp+128h+var_E8]
0x18012e995  call    ?_Alloc_sentinel_and_proxy@?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::_Alloc_sentinel_and_proxy(void)
0x18012e99a  nop
0x18012e99b  lea     rcx, [rsp+128h+var_108]; this
0x18012e9a0  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x18012e9a5  nop
0x18012e9a6  lea     rdx, [rsp+128h+var_E8]
0x18012e9ab  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord> &)
0x18012e9b0  mov     esi, eax
0x18012e9b2  test    eax, eax
0x18012e9b4  jns     loc_18012EA52
0x18012e9ba  mov     rcx, [rsp+128h]; this
0x18012e9c2  mov     r9d, eax; char *
0x18012e9c5  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012e9cc  mov     edx, 6EAh; void *
0x18012e9d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012e9d6  nop
0x18012e9d7  cmp     [rsp+128h+var_108], 0
0x18012e9dc  jz      short loc_18012E9EC
0x18012e9de  call    cs:__imp_CoUninitialize
0x18012e9e4  mov     [rsp+128h+var_108], 0
0x18012e9ec  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18012e9f1  mov     rax, [rcx+8]
0x18012e9f5  mov     qword ptr [rax], 0
0x18012e9fc  mov     rdi, [rcx]
0x18012e9ff  test    rdi, rdi
0x18012ea02  jz      short loc_18012EA25
0x18012ea04  mov     rbx, [rdi]
0x18012ea07  lea     rcx, [rdi+10h]; this
0x18012ea0b  call    ??1ResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord(void)
0x18012ea10  mov     edx, 78h ; 'x'
0x18012ea15  mov     rcx, rdi
0x18012ea18  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ea1d  mov     rdi, rbx
0x18012ea20  test    rbx, rbx
0x18012ea23  jnz     short loc_18012EA04
0x18012ea25  mov     edx, 78h ; 'x'
0x18012ea2a  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18012ea2f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ea34  nop
0x18012ea35  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012ea3c  mov     [rsp+128h+var_B8], rax
0x18012ea41  lea     rcx, [rsp+128h+var_B8]; this
0x18012ea46  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012ea4b  mov     eax, esi
0x18012ea4d  jmp     loc_18012ECC4
0x18012ea52  mov     rdi, qword ptr [rsp+128h+var_E8]
0x18012ea57  mov     rbx, [rdi]
0x18012ea5a  cmp     rbx, rdi
0x18012ea5d  jnz     short loc_18012EADA
0x18012ea5f  cmp     [rsp+128h+var_108], 0
0x18012ea64  jz      short loc_18012EA74
0x18012ea66  call    cs:__imp_CoUninitialize
0x18012ea6c  mov     [rsp+128h+var_108], 0
0x18012ea74  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18012ea79  mov     rax, [rcx+8]
0x18012ea7d  mov     qword ptr [rax], 0
0x18012ea84  mov     rdi, [rcx]
0x18012ea87  test    rdi, rdi
0x18012ea8a  jz      short loc_18012EAAD
0x18012ea8c  mov     rbx, [rdi]
0x18012ea8f  lea     rcx, [rdi+10h]; this
0x18012ea93  call    ??1ResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord(void)
0x18012ea98  mov     edx, 78h ; 'x'
0x18012ea9d  mov     rcx, rdi
0x18012eaa0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012eaa5  mov     rdi, rbx
0x18012eaa8  test    rbx, rbx
0x18012eaab  jnz     short loc_18012EA8C
0x18012eaad  mov     edx, 78h ; 'x'
0x18012eab2  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18012eab7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012eabc  nop
0x18012eabd  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012eac4  mov     [rsp+128h+var_B8], rax
0x18012eac9  lea     rcx, [rsp+128h+var_B8]; this
0x18012eace  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012ead3  xor     eax, eax
0x18012ead5  jmp     loc_18012ECC4
0x18012eada  lea     rcx, [rsp+128h+var_100]
0x18012eadf  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012eae4  nop
0x18012eae5  mov     ecx, [rbx+10h]
0x18012eae8  call    cs:__imp_?DmGetEnrollmentTypeName@@YAPEBGK@Z; DmGetEnrollmentTypeName(ulong)
0x18012eaee  mov     rdx, rax
0x18012eaf1  lea     rcx, [rsp+128h+var_D8]
0x18012eaf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012eafb  nop
0x18012eafc  mov     rdx, [rsp+128h+var_F8]
0x18012eb01  lea     rcx, [rsp+128h+var_100]
0x18012eb06  cmp     rdx, [rsp+128h+var_F0]
0x18012eb0b  jz      short loc_18012EB19
0x18012eb0d  lea     rdx, [rsp+128h+var_D8]
0x18012eb12  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012eb17  jmp     short loc_18012EB24
0x18012eb19  lea     r8, [rsp+128h+var_D8]
0x18012eb1e  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012eb23  nop
0x18012eb24  lea     rcx, [rsp+128h+var_D8]
0x18012eb29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012eb2e  lea     rdx, [rbx+18h]
0x18012eb32  lea     rcx, [rsp+128h+var_D8]
0x18012eb37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012eb3c  nop
0x18012eb3d  mov     rdx, [rsp+128h+var_F8]
0x18012eb42  lea     rcx, [rsp+128h+var_100]
0x18012eb47  cmp     rdx, [rsp+128h+var_F0]
0x18012eb4c  jz      short loc_18012EB5A
0x18012eb4e  lea     rdx, [rsp+128h+var_D8]
0x18012eb53  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012eb58  jmp     short loc_18012EB65
0x18012eb5a  lea     r8, [rsp+128h+var_D8]
0x18012eb5f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012eb64  nop
0x18012eb65  lea     rcx, [rsp+128h+var_D8]
0x18012eb6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012eb6f  lea     rcx, [rbx+38h]
0x18012eb73  lea     rdx, [rsp+128h+var_D8]
0x18012eb78  call    ?GetTargetIdForReport@DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(void)
0x18012eb7d  nop
0x18012eb7e  mov     rdx, [rsp+128h+var_F8]
0x18012eb83  lea     rcx, [rsp+128h+var_100]
0x18012eb88  cmp     rdx, [rsp+128h+var_F0]
0x18012eb8d  jz      short loc_18012EB9B
0x18012eb8f  lea     rdx, [rsp+128h+var_D8]
0x18012eb94  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012eb99  jmp     short loc_18012EBA6
0x18012eb9b  lea     r8, [rsp+128h+var_D8]
0x18012eba0  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012eba5  nop
0x18012eba6  lea     rcx, [rsp+128h+var_D8]
0x18012ebab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ebb0  lea     rdx, [rbx+58h]
0x18012ebb4  lea     rcx, [rsp+128h+var_D8]
0x18012ebb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012ebbe  nop
0x18012ebbf  mov     rdx, [rsp+128h+var_F8]
0x18012ebc4  lea     rcx, [rsp+128h+var_100]
0x18012ebc9  cmp     rdx, [rsp+128h+var_F0]
0x18012ebce  jz      short loc_18012EBDC
0x18012ebd0  lea     rdx, [rsp+128h+var_D8]
0x18012ebd5  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012ebda  jmp     short loc_18012EBE7
0x18012ebdc  lea     r8, [rsp+128h+var_D8]
0x18012ebe1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012ebe6  nop
0x18012ebe7  lea     rcx, [rsp+128h+var_D8]
0x18012ebec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ebf1  lea     rdx, [rsp+128h+var_100]
0x18012ebf6  lea     rcx, [rsp+128h+var_B8]
0x18012ebfb  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012ec00  mov     esi, eax
0x18012ec02  test    eax, eax
0x18012ec04  jns     loc_18012ECAA
0x18012ec0a  mov     rcx, [rsp+128h]; this
0x18012ec12  mov     r9d, eax; char *
0x18012ec15  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012ec1c  mov     edx, 6F4h; void *
0x18012ec21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ec26  nop
0x18012ec27  lea     rcx, [rsp+128h+var_100]
0x18012ec2c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012ec31  nop
0x18012ec32  cmp     [rsp+128h+var_108], 0
0x18012ec37  jz      short loc_18012EC47
0x18012ec39  call    cs:__imp_CoUninitialize
0x18012ec3f  mov     [rsp+128h+var_108], 0
0x18012ec47  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18012ec4c  mov     rax, [rcx+8]
0x18012ec50  mov     qword ptr [rax], 0
0x18012ec57  mov     rdi, [rcx]
0x18012ec5a  test    rdi, rdi
0x18012ec5d  jz      short loc_18012EC80
0x18012ec5f  mov     rbx, [rdi]
0x18012ec62  lea     rcx, [rdi+10h]; this
0x18012ec66  call    ??1ResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord(void)
0x18012ec6b  mov     edx, 78h ; 'x'
0x18012ec70  mov     rcx, rdi
0x18012ec73  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ec78  mov     rdi, rbx
0x18012ec7b  test    rbx, rbx
0x18012ec7e  jnz     short loc_18012EC5F
0x18012ec80  mov     edx, 78h ; 'x'
0x18012ec85  mov     rcx, qword ptr [rsp+128h+var_E8]
0x18012ec8a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ec8f  nop
0x18012ec90  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012ec97  mov     [rsp+128h+var_B8], rax
0x18012ec9c  lea     rcx, [rsp+128h+var_B8]; this
0x18012eca1  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012eca6  mov     eax, esi
0x18012eca8  jmp     short loc_18012ECC4
0x18012ecaa  or      r14d, 7
0x18012ecae  lea     rcx, [rsp+128h+var_100]
0x18012ecb3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012ecb8  mov     rbx, [rbx]
0x18012ecbb  jmp     loc_18012EA5A
0x18012ecc0  mov     eax, [rsp+128h+var_108]
0x18012ecc4  mov     rcx, [rsp+128h+var_38]
0x18012eccc  xor     rcx, rsp; StackCookie
0x18012eccf  call    __security_check_cookie
0x18012ecd4  add     rsp, 108h
0x18012ecdb  pop     r14
0x18012ecdd  pop     rdi
0x18012ecde  pop     rsi
0x18012ecdf  pop     rbx
0x18012ece0  retn
```
