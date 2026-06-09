# WriteEnrolledConfigurationSourcesAndTargetResources(void)

- ea: `0x1801305b8`
- end: `0x180130a4a`
- name: `?WriteEnrolledConfigurationSourcesAndTargetResources@@YAJXZ`
- size: `1170`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e5744`
- `0x1800e6838`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800efd9c`
- `0x180105480`
- `0x180106b6c`
- `0x180106ee0`
- `0x18012269c`
- `0x18012845c`
- `0x1801284b0`
- `0x180129498`
- `0x180129a7c`
- `0x180129aac`
- `0x180129ee0`
- `0x1801305b8`
- `0x1801330e0`
- `0x180134bd4`
- `0x18013944c`
- `0x18013a188`
- `0x18013d460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013072a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801307bc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013099b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013072a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801307bc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013099b`
- `DMCmnUtils!DmGetEnrollmentTypeName` at `0x180130844`
- `DMCmnUtils!DmGetEnrollmentTypeName` at `0x180130844`

## string_xrefs

- `0x1801306a4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130711`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130977`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801305e1`: `Configuration source`
- `0x180130622`: `Enrolled configuration sources and target resources`
- `0x18013061b`: `EnrolledConfigurationSourcesAndTargetResourcesTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 WriteEnrolledConfigurationSourcesAndTargetResources(void)
{
  int v0; // r14d
  __int64 v1; // rbx
  __int64 v2; // rax
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
  v1 = std::vector<int>::vector<int>(v26, &si128, v29);
  v2 = std::vector<std::wstring>::vector<std::wstring>(v22, v29, v30);
  v3 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(v27, 0, v2, v1);
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
0x1801305b8  mov     r11, rsp
0x1801305bb  push    rbx
0x1801305bc  push    rsi
0x1801305bd  push    rdi
0x1801305be  push    r14
0x1801305c0  sub     rsp, 108h
0x1801305c7  mov     rax, cs:__security_cookie
0x1801305ce  xor     rax, rsp
0x1801305d1  mov     [rsp+128h+var_38], rax
0x1801305d9  xor     r14d, r14d
0x1801305dc  mov     [rsp+128h+var_108], r14d; int
0x1801305e1  lea     rax, aConfigurationS; "Configuration source"
0x1801305e8  mov     [r11-58h], rax
0x1801305ec  lea     rax, aId; "ID"
0x1801305f3  mov     [r11-50h], rax
0x1801305f7  lea     rax, aTarget; "Target"
0x1801305fe  mov     [r11-48h], rax
0x180130602  lea     rax, aResource; "Resource"
0x180130609  mov     [r11-40h], rax
0x18013060d  movdqa  xmm0, cs:__xmm@00000025000000090000001e00000018
0x180130615  movdqu  xmmword ptr [r11-68h], xmm0
0x18013061b  lea     r8, aEnrolledconfig; "EnrolledConfigurationSourcesAndTargetRe"...
0x180130622  lea     rdx, aEnrolledConfig; "Enrolled configuration sources and targ"...
0x180130629  lea     rcx, [rsp+128h+var_B8]; this
0x18013062e  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180130633  nop
0x180130634  lea     r8, [rsp+128h+var_58]
0x18013063c  lea     rdx, [rsp+128h+var_68]
0x180130644  lea     rcx, [rsp+128h+var_D8]
0x180130649  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x18013064e  mov     rbx, rax
0x180130651  lea     r8, [rsp+128h+var_38]
0x180130659  lea     rdx, [rsp+128h+var_58]
0x180130661  lea     rcx, [rsp+128h+var_100]
0x180130666  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18013066b  nop
0x18013066c  mov     r9, rbx
0x18013066f  mov     r8, rax
0x180130672  xor     edx, edx
0x180130674  lea     rcx, [rsp+128h+var_B8]
0x180130679  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x18013067e  mov     ebx, eax
0x180130680  lea     rcx, [rsp+128h+var_100]
0x180130685  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18013068a  nop
0x18013068b  lea     rcx, [rsp+128h+var_D8]
0x180130690  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x180130695  test    ebx, ebx
0x180130697  jns     short loc_1801306D3
0x180130699  mov     rcx, [rsp+128h]; this
0x1801306a1  mov     r9d, ebx; char *
0x1801306a4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801306ab  mov     edx, 6E6h; void *
0x1801306b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801306b5  nop
0x1801306b6  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801306bd  mov     [rsp+128h+var_B8], rax
0x1801306c2  lea     rcx, [rsp+128h+var_B8]; this
0x1801306c7  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801306cc  mov     eax, ebx
0x1801306ce  jmp     loc_180130A2C
0x1801306d3  xorps   xmm0, xmm0
0x1801306d6  movdqu  [rsp+128h+var_E8], xmm0
0x1801306dc  lea     rcx, [rsp+128h+var_E8]
0x1801306e1  call    ?_Alloc_sentinel_and_proxy@?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAXXZ; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::_Alloc_sentinel_and_proxy(void)
0x1801306e6  nop
0x1801306e7  lea     rcx, [rsp+128h+var_108]; this
0x1801306ec  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x1801306f1  nop
0x1801306f2  lea     rdx, [rsp+128h+var_E8]
0x1801306f7  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord> &)
0x1801306fc  mov     esi, eax
0x1801306fe  test    eax, eax
0x180130700  jns     loc_1801307A4
0x180130706  mov     rcx, [rsp+128h]; this
0x18013070e  mov     r9d, eax; char *
0x180130711  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180130718  mov     edx, 6EAh; void *
0x18013071d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130722  nop
0x180130723  cmp     [rsp+128h+var_108], 0
0x180130728  jz      short loc_18013073E
0x18013072a  call    cs:__imp_CoUninitialize
0x180130731  nop     dword ptr [rax+rax+00h]
0x180130736  mov     [rsp+128h+var_108], 0
0x18013073e  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180130743  mov     rax, [rcx+8]
0x180130747  mov     qword ptr [rax], 0
0x18013074e  mov     rdi, [rcx]
0x180130751  test    rdi, rdi
0x180130754  jz      short loc_180130777
0x180130756  mov     rbx, [rdi]
0x180130759  lea     rcx, [rdi+10h]; this
0x18013075d  call    ??1ResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord(void)
0x180130762  mov     edx, 78h ; 'x'
0x180130767  mov     rcx, rdi
0x18013076a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013076f  mov     rdi, rbx
0x180130772  test    rbx, rbx
0x180130775  jnz     short loc_180130756
0x180130777  mov     edx, 78h ; 'x'
0x18013077c  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180130781  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130786  nop
0x180130787  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18013078e  mov     [rsp+128h+var_B8], rax
0x180130793  lea     rcx, [rsp+128h+var_B8]; this
0x180130798  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013079d  mov     eax, esi
0x18013079f  jmp     loc_180130A2C
0x1801307a4  mov     rdi, qword ptr [rsp+128h+var_E8]
0x1801307a9  mov     rbx, [rdi]
0x1801307ac  cmp     rbx, rdi
0x1801307af  jnz     loc_180130836
0x1801307b5  cmp     [rsp+128h+var_108], 0
0x1801307ba  jz      short loc_1801307D0
0x1801307bc  call    cs:__imp_CoUninitialize
0x1801307c3  nop     dword ptr [rax+rax+00h]
0x1801307c8  mov     [rsp+128h+var_108], 0
0x1801307d0  mov     rcx, qword ptr [rsp+128h+var_E8]
0x1801307d5  mov     rax, [rcx+8]
0x1801307d9  mov     qword ptr [rax], 0
0x1801307e0  mov     rdi, [rcx]
0x1801307e3  test    rdi, rdi
0x1801307e6  jz      short loc_180130809
0x1801307e8  mov     rbx, [rdi]
0x1801307eb  lea     rcx, [rdi+10h]; this
0x1801307ef  call    ??1ResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord(void)
0x1801307f4  mov     edx, 78h ; 'x'
0x1801307f9  mov     rcx, rdi
0x1801307fc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130801  mov     rdi, rbx
0x180130804  test    rbx, rbx
0x180130807  jnz     short loc_1801307E8
0x180130809  mov     edx, 78h ; 'x'
0x18013080e  mov     rcx, qword ptr [rsp+128h+var_E8]
0x180130813  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130818  nop
0x180130819  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180130820  mov     [rsp+128h+var_B8], rax
0x180130825  lea     rcx, [rsp+128h+var_B8]; this
0x18013082a  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013082f  xor     eax, eax
0x180130831  jmp     loc_180130A2C
0x180130836  lea     rcx, [rsp+128h+var_100]
0x18013083b  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180130840  nop
0x180130841  mov     ecx, [rbx+10h]
0x180130844  call    cs:__imp_?DmGetEnrollmentTypeName@@YAPEBGK@Z; DmGetEnrollmentTypeName(ulong)
0x18013084b  nop     dword ptr [rax+rax+00h]
0x180130850  mov     rdx, rax
0x180130853  lea     rcx, [rsp+128h+var_D8]
0x180130858  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013085d  nop
0x18013085e  mov     rdx, [rsp+128h+var_F8]
0x180130863  lea     rcx, [rsp+128h+var_100]
0x180130868  cmp     rdx, [rsp+128h+var_F0]
0x18013086d  jz      short loc_18013087B
0x18013086f  lea     rdx, [rsp+128h+var_D8]
0x180130874  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130879  jmp     short loc_180130886
0x18013087b  lea     r8, [rsp+128h+var_D8]
0x180130880  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130885  nop
0x180130886  lea     rcx, [rsp+128h+var_D8]
0x18013088b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130890  lea     rdx, [rbx+18h]
0x180130894  lea     rcx, [rsp+128h+var_D8]
0x180130899  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013089e  nop
0x18013089f  mov     rdx, [rsp+128h+var_F8]
0x1801308a4  lea     rcx, [rsp+128h+var_100]
0x1801308a9  cmp     rdx, [rsp+128h+var_F0]
0x1801308ae  jz      short loc_1801308BC
0x1801308b0  lea     rdx, [rsp+128h+var_D8]
0x1801308b5  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801308ba  jmp     short loc_1801308C7
0x1801308bc  lea     r8, [rsp+128h+var_D8]
0x1801308c1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801308c6  nop
0x1801308c7  lea     rcx, [rsp+128h+var_D8]
0x1801308cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801308d1  lea     rcx, [rbx+38h]
0x1801308d5  lea     rdx, [rsp+128h+var_D8]
0x1801308da  call    ?GetTargetIdForReport@DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(void)
0x1801308df  nop
0x1801308e0  mov     rdx, [rsp+128h+var_F8]
0x1801308e5  lea     rcx, [rsp+128h+var_100]
0x1801308ea  cmp     rdx, [rsp+128h+var_F0]
0x1801308ef  jz      short loc_1801308FD
0x1801308f1  lea     rdx, [rsp+128h+var_D8]
0x1801308f6  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801308fb  jmp     short loc_180130908
0x1801308fd  lea     r8, [rsp+128h+var_D8]
0x180130902  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130907  nop
0x180130908  lea     rcx, [rsp+128h+var_D8]
0x18013090d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130912  lea     rdx, [rbx+58h]
0x180130916  lea     rcx, [rsp+128h+var_D8]
0x18013091b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130920  nop
0x180130921  mov     rdx, [rsp+128h+var_F8]
0x180130926  lea     rcx, [rsp+128h+var_100]
0x18013092b  cmp     rdx, [rsp+128h+var_F0]
0x180130930  jz      short loc_18013093E
0x180130932  lea     rdx, [rsp+128h+var_D8]
0x180130937  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18013093c  jmp     short loc_180130949
0x18013093e  lea     r8, [rsp+128h+var_D8]
0x180130943  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130948  nop
0x180130949  lea     rcx, [rsp+128h+var_D8]
0x18013094e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130953  lea     rdx, [rsp+128h+var_100]
0x180130958  lea     rcx, [rsp+128h+var_B8]
0x18013095d  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x180130962  mov     esi, eax
0x180130964  test    eax, eax
0x180130966  jns     loc_180130A12
0x18013096c  mov     rcx, [rsp+128h]; this
0x180130974  mov     r9d, eax; char *
0x180130977  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013097e  mov     edx, 6F4h; void *
0x180130983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130988  nop
0x180130989  lea     rcx, [rsp+128h+var_100]
0x18013098e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130993  nop
0x180130994  cmp     [rsp+128h+var_108], 0
0x180130999  jz      short loc_1801309AF
0x18013099b  call    cs:__imp_CoUninitialize
0x1801309a2  nop     dword ptr [rax+rax+00h]
0x1801309a7  mov     [rsp+128h+var_108], 0
0x1801309af  mov     rcx, qword ptr [rsp+128h+var_E8]
0x1801309b4  mov     rax, [rcx+8]
0x1801309b8  mov     qword ptr [rax], 0
0x1801309bf  mov     rdi, [rcx]
0x1801309c2  test    rdi, rdi
0x1801309c5  jz      short loc_1801309E8
0x1801309c7  mov     rbx, [rdi]
0x1801309ca  lea     rcx, [rdi+10h]; this
0x1801309ce  call    ??1ResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord::~ResourceRecord(void)
0x1801309d3  mov     edx, 78h ; 'x'
0x1801309d8  mov     rcx, rdi
0x1801309db  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801309e0  mov     rdi, rbx
0x1801309e3  test    rbx, rbx
0x1801309e6  jnz     short loc_1801309C7
0x1801309e8  mov     edx, 78h ; 'x'
0x1801309ed  mov     rcx, qword ptr [rsp+128h+var_E8]
0x1801309f2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801309f7  nop
0x1801309f8  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801309ff  mov     [rsp+128h+var_B8], rax
0x180130a04  lea     rcx, [rsp+128h+var_B8]; this
0x180130a09  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180130a0e  mov     eax, esi
0x180130a10  jmp     short loc_180130A2C
0x180130a12  or      r14d, 7
0x180130a16  lea     rcx, [rsp+128h+var_100]
0x180130a1b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130a20  mov     rbx, [rbx]
0x180130a23  jmp     loc_1801307AC
0x180130a28  mov     eax, [rsp+128h+var_108]
0x180130a2c  mov     rcx, [rsp+128h+var_38]
0x180130a34  xor     rcx, rsp; StackCookie
0x180130a37  call    __security_check_cookie
0x180130a3c  add     rsp, 108h
0x180130a43  pop     r14
0x180130a45  pop     rdi
0x180130a46  pop     rsi
0x180130a47  pop     rbx
0x180130a48  retn
```
