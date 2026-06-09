# WriteManagedPolicies(void)

- ea: `0x1801324f4`
- end: `0x180132cb2`
- name: `?WriteManagedPolicies@@YAJXZ`
- size: `1982`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e6838`
- `0x1800e6b14`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800eef28`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x1800f99d4`
- `0x1800fa2e4`
- `0x1800fa478`
- `0x1800faa0c`
- `0x180105480`
- `0x180105f10`
- `0x180105f3c`
- `0x180106b3c`
- `0x180106b6c`
- `0x180106dc8`
- `0x180106ee0`
- `0x18012269c`
- `0x18012845c`
- `0x1801284b0`
- `0x180128570`
- `0x180129498`
- `0x180129aac`
- `0x180129ee0`
- `0x18012a958`
- `0x18012b150`
- `0x1801324f4`
- `0x1801330e0`
- `0x180137ea0`
- `0x18013d43c`
- `0x18013d460`

## string_xrefs

- `0x180132630`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132691`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801326f7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132b35`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132582`: `Config Source`
- `0x1801325f6`: `Policies that are not set to the default value or have a configuration source applied`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
__int64 WriteManagedPolicies(void)
{
  int v0; // edi
  __int64 v1; // rbx
  __int64 v2; // rax
  int v3; // ebx
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v5; // rax
  int EnrollmentId; // eax
  unsigned int v7; // ebx
  int ManagedPolicies; // eax
  unsigned int v9; // ebx
  __int64 *v10; // rbx
  __int64 v11; // rsi
  __int64 PolicyName; // rax
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r14
  __int64 v19; // rsi
  _BYTE *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // esi
  __int64 **v25; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v28[4]; // [rsp+20h] [rbp-248h] BYREF
  __int64 v29; // [rsp+30h] [rbp-238h]
  int v30; // [rsp+38h] [rbp-230h]
  __int128 v31; // [rsp+40h] [rbp-228h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-218h] BYREF
  __int64 v33; // [rsp+60h] [rbp-208h] BYREF
  std::_Ref_count_base *v34; // [rsp+68h] [rbp-200h]
  _BYTE v35[16]; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v36; // [rsp+88h] [rbp-1E0h]
  __int128 v37; // [rsp+98h] [rbp-1D0h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-1C0h]
  __int64 v39; // [rsp+B0h] [rbp-1B8h]
  _BYTE v40[40]; // [rsp+B8h] [rbp-1B0h] BYREF
  _QWORD v41[10]; // [rsp+E0h] [rbp-188h] BYREF
  _BYTE v42[32]; // [rsp+130h] [rbp-138h] BYREF
  _BYTE v43[32]; // [rsp+150h] [rbp-118h] BYREF
  _BYTE v44[32]; // [rsp+170h] [rbp-F8h] BYREF
  _BYTE v45[32]; // [rsp+190h] [rbp-D8h] BYREF
  _BYTE v46[32]; // [rsp+1B0h] [rbp-B8h] BYREF
  _BYTE v47[32]; // [rsp+1D0h] [rbp-98h] BYREF
  __m128i si128; // [rsp+1F0h] [rbp-78h] BYREF
  int v49; // [rsp+200h] [rbp-68h]
  int v50; // [rsp+204h] [rbp-64h]
  _QWORD v51[6]; // [rsp+208h] [rbp-60h] BYREF
  _QWORD v52[6]; // [rsp+238h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v0 = 0;
  v30 = 0;
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v41,
    L"Managed policies",
    L"ManagedPoliciesTable");
  v51[0] = L"Area";
  v51[1] = L"Policy";
  v51[2] = L"Default Value";
  v51[3] = L"Current Value";
  v51[4] = L"Target";
  v51[5] = L"Config Source";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v49 = 8;
  v50 = 28;
  v1 = std::vector<int>::vector<int>(&v33, &si128, v51);
  v2 = std::vector<std::wstring>::vector<std::wstring>(v28, v51, v52);
  v3 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
         v41,
         L"Policies that are not set to the default value or have a configuration source applied",
         v2,
         v1);
  std::vector<std::wstring>::_Tidy(v28);
  std::vector<enum TpmCapabilityPT>::_Tidy(&v33);
  if ( v3 >= 0 )
  {
    v31 = 0;
    v5 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v5, &v31);
    v7 = EnrollmentId;
    if ( EnrollmentId >= 0 )
    {
      std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>(v32);
      ManagedPolicies = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(v32);
      v9 = ManagedPolicies;
      if ( ManagedPolicies >= 0 )
      {
        v10 = *(__int64 **)v32[0];
        while ( 1 )
        {
          if ( *((_BYTE *)v10 + 25) )
          {
            std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(v32);
            std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v31);
            v41[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
            Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v41);
            return 0;
          }
          std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
            &v33,
            v10 + 5);
          *(_OWORD *)v28 = 0;
          v29 = 0;
          v11 = v33;
          std::wstring::wstring(v35, v33);
          if ( *(_QWORD *)&v28[2] == v29 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v28, *(_QWORD *)&v28[2], v35);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v28, v35);
          std::wstring::_Tidy_deallocate(v35);
          PolicyName = Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetPolicyName(v11, v40);
          if ( *(_QWORD *)&v28[2] == v29 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v28, *(_QWORD *)&v28[2], PolicyName);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v28, PolicyName);
          std::wstring::_Tidy_deallocate(v40);
          std::wstring::wstring(v35, v11 + 128);
          if ( *(_QWORD *)&v28[2] == v29 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v28, *(_QWORD *)&v28[2], v35);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v28, v35);
          std::wstring::_Tidy_deallocate(v35);
          std::wstring::wstring(v35, v11 + 96);
          if ( *(_QWORD *)&v28[2] == v29 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v28, *(_QWORD *)&v28[2], v35);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v28, v35);
          std::wstring::_Tidy_deallocate(v35);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(v11 + 64, v35);
          if ( *(_QWORD *)&v28[2] == v29 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v28, *(_QWORD *)&v28[2], v35);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v28, v35);
          std::wstring::_Tidy_deallocate(v35);
          v13 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetPolicyName(v11, v43);
          std::wstring::wstring(v35, v11);
          v14 = std::operator+<unsigned short>(v42, L"/", v35);
          v15 = std::operator+<unsigned short>(v47, v14, L"/");
          v16 = std::operator+<unsigned short>(v40, v15, v13);
          std::operator+<unsigned short>(v46, v16, L"/");
          std::wstring::_Tidy_deallocate(v40);
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v42);
          std::wstring::_Tidy_deallocate(v35);
          std::wstring::_Tidy_deallocate(v43);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetRawTargetId(v11 + 64, v45);
          v0 |= 0x3Fu;
          v37 = 0;
          v17 = 0;
          v38 = 0;
          v39 = 7;
          LOWORD(v37) = 0;
          v18 = *(_QWORD *)(v11 + 168);
          v19 = *(_QWORD *)(v11 + 176);
          while ( v18 != v19 )
          {
            if ( v17 )
              std::wstring::append(&v37, L",<br/>");
            std::wstring::wstring(v35, v18 + 32);
            if ( v36 )
            {
              std::wstring::wstring(v40, v18);
              v0 |= 0x140u;
              v21 = std::operator+<unsigned short>(v42, v40, L"=");
              v22 = std::operator+<unsigned short>(v43, v21, v35);
              std::wstring::append(&v37, v22);
              std::wstring::_Tidy_deallocate(v43);
              std::wstring::_Tidy_deallocate(v42);
              v20 = v40;
            }
            else
            {
              std::wstring::wstring(v44, v18);
              v0 |= 0xC0u;
              std::wstring::append(&v37, v44);
              v20 = v44;
            }
            std::wstring::_Tidy_deallocate(v20);
            std::wstring::_Tidy_deallocate(v35);
            v18 += 64;
            v17 = v38;
          }
          if ( *(_QWORD *)&v28[2] == v29 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v28, *(_QWORD *)&v28[2], &v37);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v28, &v37);
          v23 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v41, v28);
          v24 = v23;
          if ( v23 < 0 )
            break;
          std::wstring::_Tidy_deallocate(&v37);
          std::wstring::_Tidy_deallocate(v45);
          std::wstring::_Tidy_deallocate(v46);
          std::vector<std::wstring>::_Tidy(v28);
          if ( v34 )
            std::_Ref_count_base::_Decref(v34);
          v25 = (__int64 **)v10[2];
          if ( *((_BYTE *)v25 + 25) )
          {
            for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25) && v10 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v10 = i;
            v10 = i;
          }
          else
          {
            v10 = (__int64 *)v10[2];
            for ( j = *v25; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v10 = j;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v23,
          v28[0]);
        std::wstring::_Tidy_deallocate(&v37);
        std::wstring::_Tidy_deallocate(v45);
        std::wstring::_Tidy_deallocate(v46);
        std::vector<std::wstring>::_Tidy(v28);
        if ( v34 )
          std::_Ref_count_base::_Decref(v34);
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(v32);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v31);
        v41[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v41);
        return v24;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x875,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)ManagedPolicies,
          v28[0]);
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(v32);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v31);
        v41[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v41);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x872,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)EnrollmentId,
        v28[0]);
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v31);
      v41[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v41);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v3,
      v28[0]);
    v41[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v41);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x1801324f4  push    rbx
0x1801324f6  push    rsi
0x1801324f7  push    rdi
0x1801324f8  push    r14
0x1801324fa  push    r15
0x1801324fc  sub     rsp, 240h
0x180132503  mov     rax, cs:__security_cookie
0x18013250a  xor     rax, rsp
0x18013250d  mov     [rsp+268h+var_30], rax
0x180132515  xor     edi, edi
0x180132517  mov     [rsp+268h+var_230], edi
0x18013251b  lea     r8, aManagedpolicie; "ManagedPoliciesTable"
0x180132522  lea     rdx, aManagedPolicie; "Managed policies"
0x180132529  lea     rcx, [rsp+268h+var_188]; this
0x180132531  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180132536  nop
0x180132537  lea     rax, aArea; "Area"
0x18013253e  mov     [rsp+268h+var_60], rax
0x180132546  lea     rax, aPolicy_0; "Policy"
0x18013254d  mov     [rsp+268h+var_58], rax
0x180132555  lea     rax, aDefaultValue; "Default Value"
0x18013255c  mov     [rsp+268h+var_50], rax
0x180132564  lea     rax, aCurrentValue; "Current Value"
0x18013256b  mov     [rsp+268h+var_48], rax
0x180132573  lea     rax, aTarget; "Target"
0x18013257a  mov     [rsp+268h+var_40], rax
0x180132582  lea     rax, aConfigSource; "Config Source"
0x180132589  mov     [rsp+268h+var_38], rax
0x180132591  movdqa  xmm0, cs:__xmm@0000000c0000000b0000001200000012
0x180132599  movdqu  [rsp+268h+var_78], xmm0
0x1801325a2  mov     [rsp+268h+var_68], 8
0x1801325ad  mov     [rsp+268h+var_64], 1Ch
0x1801325b8  lea     r8, [rsp+268h+var_60]
0x1801325c0  lea     rdx, [rsp+268h+var_78]
0x1801325c8  lea     rcx, [rsp+268h+var_208]
0x1801325cd  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x1801325d2  mov     rbx, rax
0x1801325d5  lea     r8, [rsp+268h+var_30]
0x1801325dd  lea     rdx, [rsp+268h+var_60]
0x1801325e5  lea     rcx, [rsp+268h+var_248]
0x1801325ea  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x1801325ef  nop
0x1801325f0  mov     r9, rbx
0x1801325f3  mov     r8, rax
0x1801325f6  lea     rdx, aPoliciesThatAr; "Policies that are not set to the defaul"...
0x1801325fd  lea     rcx, [rsp+268h+var_188]
0x180132605  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x18013260a  mov     ebx, eax
0x18013260c  lea     rcx, [rsp+268h+var_248]
0x180132611  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180132616  nop
0x180132617  lea     rcx, [rsp+268h+var_208]
0x18013261c  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x180132621  test    ebx, ebx
0x180132623  jns     short loc_180132665
0x180132625  mov     rcx, [rsp+268h]; this
0x18013262d  mov     r9d, ebx; char *
0x180132630  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180132637  mov     edx, 86Fh; void *
0x18013263c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132641  nop
0x180132642  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180132649  mov     [rsp+268h+var_188], rax
0x180132651  lea     rcx, [rsp+268h+var_188]; this
0x180132659  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013265e  mov     eax, ebx
0x180132660  jmp     loc_180132C92
0x180132665  xorps   xmm1, xmm1
0x180132668  movdqu  [rsp+268h+var_228], xmm1
0x18013266e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180132673  lea     rdx, [rsp+268h+var_228]
0x180132678  mov     rcx, rax
0x18013267b  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180132680  mov     ebx, eax
0x180132682  test    eax, eax
0x180132684  jns     short loc_1801326D1
0x180132686  mov     rcx, [rsp+268h]; this
0x18013268e  mov     r9d, eax; char *
0x180132691  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180132698  mov     edx, 872h; void *
0x18013269d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801326a2  nop
0x1801326a3  lea     rcx, [rsp+268h+var_228]
0x1801326a8  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801326ad  nop
0x1801326ae  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801326b5  mov     [rsp+268h+var_188], rax
0x1801326bd  lea     rcx, [rsp+268h+var_188]; this
0x1801326c5  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801326ca  mov     eax, ebx
0x1801326cc  jmp     loc_180132C92
0x1801326d1  lea     rcx, [rsp+268h+var_218]
0x1801326d6  call    ??0?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@QEAA@XZ; std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>(void)
0x1801326db  nop
0x1801326dc  lea     rcx, [rsp+268h+var_218]
0x1801326e1  call    ?RetrieveManagedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x1801326e6  mov     ebx, eax
0x1801326e8  test    eax, eax
0x1801326ea  jns     short loc_180132742
0x1801326ec  mov     rcx, [rsp+268h]; this
0x1801326f4  mov     r9d, eax; char *
0x1801326f7  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801326fe  mov     edx, 875h; void *
0x180132703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132708  nop
0x180132709  lea     rcx, [rsp+268h+var_218]
0x18013270e  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(void)
0x180132713  nop
0x180132714  lea     rcx, [rsp+268h+var_228]
0x180132719  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18013271e  nop
0x18013271f  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180132726  mov     [rsp+268h+var_188], rax
0x18013272e  lea     rcx, [rsp+268h+var_188]; this
0x180132736  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013273b  mov     eax, ebx
0x18013273d  jmp     loc_180132C92
0x180132742  mov     rbx, [rsp+268h+var_218]
0x180132747  mov     rbx, [rbx]
0x18013274a  cmp     byte ptr [rbx+19h], 0
0x18013274e  jnz     loc_180132C58
0x180132754  lea     rdx, [rbx+28h]
0x180132758  lea     rcx, [rsp+268h+var_208]
0x18013275d  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180132762  nop
0x180132763  xorps   xmm0, xmm0
0x180132766  movdqu  xmmword ptr [rsp+268h+var_248], xmm0; int
0x18013276c  mov     [rsp+268h+var_238], 0
0x180132775  mov     rsi, [rsp+268h+var_208]
0x18013277a  mov     rdx, rsi
0x18013277d  lea     rcx, [rsp+268h+var_1F0]
0x180132782  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180132787  nop
0x180132788  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x18013278d  lea     rcx, [rsp+268h+var_248]
0x180132792  cmp     rdx, [rsp+268h+var_238]
0x180132797  jz      short loc_1801327A5
0x180132799  lea     rdx, [rsp+268h+var_1F0]
0x18013279e  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801327a3  jmp     short loc_1801327B0
0x1801327a5  lea     r8, [rsp+268h+var_1F0]
0x1801327aa  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801327af  nop
0x1801327b0  lea     rcx, [rsp+268h+var_1F0]
0x1801327b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801327ba  lea     rdx, [rsp+268h+var_1B0]
0x1801327c2  mov     rcx, rsi
0x1801327c5  call    ?GetPolicyName@Policy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetPolicyName(void)
0x1801327ca  nop
0x1801327cb  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x1801327d0  lea     rcx, [rsp+268h+var_248]
0x1801327d5  cmp     rdx, [rsp+268h+var_238]
0x1801327da  jz      short loc_1801327E6
0x1801327dc  mov     rdx, rax
0x1801327df  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801327e4  jmp     short loc_1801327EF
0x1801327e6  mov     r8, rax
0x1801327e9  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801327ee  nop
0x1801327ef  lea     rcx, [rsp+268h+var_1B0]
0x1801327f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801327fc  lea     rdx, [rsi+80h]
0x180132803  lea     rcx, [rsp+268h+var_1F0]
0x180132808  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013280d  nop
0x18013280e  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180132813  lea     rcx, [rsp+268h+var_248]
0x180132818  cmp     rdx, [rsp+268h+var_238]
0x18013281d  jz      short loc_18013282B
0x18013281f  lea     rdx, [rsp+268h+var_1F0]
0x180132824  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180132829  jmp     short loc_180132836
0x18013282b  lea     r8, [rsp+268h+var_1F0]
0x180132830  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180132835  nop
0x180132836  lea     rcx, [rsp+268h+var_1F0]
0x18013283b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132840  lea     rdx, [rsi+60h]
0x180132844  lea     rcx, [rsp+268h+var_1F0]
0x180132849  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18013284e  nop
0x18013284f  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180132854  lea     rcx, [rsp+268h+var_248]
0x180132859  cmp     rdx, [rsp+268h+var_238]
0x18013285e  jz      short loc_18013286C
0x180132860  lea     rdx, [rsp+268h+var_1F0]
0x180132865  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18013286a  jmp     short loc_180132877
0x18013286c  lea     r8, [rsp+268h+var_1F0]
0x180132871  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180132876  nop
0x180132877  lea     rcx, [rsp+268h+var_1F0]
0x18013287c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132881  lea     rdx, [rsp+268h+var_1F0]
0x180132886  lea     rcx, [rsi+40h]
0x18013288a  call    ?GetTargetIdForReport@DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(void)
0x18013288f  nop
0x180132890  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180132895  lea     rcx, [rsp+268h+var_248]
0x18013289a  cmp     rdx, [rsp+268h+var_238]
0x18013289f  jz      short loc_1801328AD
0x1801328a1  lea     rdx, [rsp+268h+var_1F0]
0x1801328a6  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801328ab  jmp     short loc_1801328B8
0x1801328ad  lea     r8, [rsp+268h+var_1F0]
0x1801328b2  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801328b7  nop
0x1801328b8  or      edi, 1
0x1801328bb  lea     rcx, [rsp+268h+var_1F0]
0x1801328c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801328c5  lea     rdx, [rsp+268h+var_118]
0x1801328cd  mov     rcx, rsi
0x1801328d0  call    ?GetPolicyName@Policy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetPolicyName(void)
0x1801328d5  mov     r15, rax
0x1801328d8  mov     rdx, rsi
0x1801328db  lea     rcx, [rsp+268h+var_1F0]
0x1801328e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801328e5  nop
0x1801328e6  lea     r8, [rsp+268h+var_1F0]
0x1801328eb  lea     rdx, asc_1801D2C90; "/"
0x1801328f2  lea     rcx, [rsp+268h+var_138]
0x1801328fa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1801328ff  nop
0x180132900  lea     r8, asc_1801D2C90; "/"
0x180132907  mov     rdx, rax
0x18013290a  lea     rcx, [rsp+268h+var_98]
0x180132912  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180132917  nop
0x180132918  mov     r8, r15
0x18013291b  mov     rdx, rax
0x18013291e  lea     rcx, [rsp+268h+var_1B0]
0x180132926  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18013292b  nop
0x18013292c  lea     r8, asc_1801D2C90; "/"
0x180132933  mov     rdx, rax
0x180132936  lea     rcx, [rsp+268h+var_B8]
0x18013293e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180132943  nop
0x180132944  lea     rcx, [rsp+268h+var_1B0]
0x18013294c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132951  nop
0x180132952  lea     rcx, [rsp+268h+var_98]
0x18013295a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013295f  nop
0x180132960  lea     rcx, [rsp+268h+var_138]
0x180132968  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013296d  nop
0x18013296e  lea     rcx, [rsp+268h+var_1F0]
0x180132973  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132978  nop
0x180132979  lea     rcx, [rsp+268h+var_118]
0x180132981  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132986  lea     rdx, [rsp+268h+var_D8]
0x18013298e  lea     rcx, [rsi+40h]
0x180132992  call    ?GetRawTargetId@DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetRawTargetId(void)
0x180132997  or      edi, 3Eh
0x18013299a  xorps   xmm0, xmm0
0x18013299d  movups  [rsp+268h+var_1D0], xmm0
0x1801329a5  xor     ecx, ecx
0x1801329a7  mov     [rsp+268h+var_1C0], rcx
0x1801329af  mov     [rsp+268h+var_1B8], 7
0x1801329bb  xor     eax, eax
0x1801329bd  mov     word ptr [rsp+268h+var_1D0], ax
0x1801329c5  mov     r14, [rsi+0A8h]
0x1801329cc  mov     rsi, [rsi+0B0h]
0x1801329d3  cmp     r14, rsi
0x1801329d6  jz      loc_180132AE1
0x1801329dc  test    rcx, rcx
0x1801329df  jz      short loc_1801329F5
0x1801329e1  lea     rdx, aBr; ",<br/>"
0x1801329e8  lea     rcx, [rsp+268h+var_1D0]
0x1801329f0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1801329f5  lea     rdx, [r14+20h]
0x1801329f9  lea     rcx, [rsp+268h+var_1F0]
0x1801329fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180132a03  nop
0x180132a04  mov     rdx, r14
0x180132a07  cmp     [rsp+268h+var_1E0], 0
0x180132a10  jnz     short loc_180132A45
0x180132a12  lea     rcx, [rsp+268h+var_F8]
0x180132a1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180132a1f  or      edi, 0C0h
0x180132a25  lea     rdx, [rsp+268h+var_F8]
0x180132a2d  lea     rcx, [rsp+268h+var_1D0]
0x180132a35  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180132a3a  nop
0x180132a3b  lea     rcx, [rsp+268h+var_F8]
0x180132a43  jmp     short loc_180132AC0
0x180132a45  lea     rcx, [rsp+268h+var_1B0]
0x180132a4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180132a52  or      edi, 140h
0x180132a58  lea     r8, asc_1801EFBA8; "="
0x180132a5f  lea     rdx, [rsp+268h+var_1B0]
0x180132a67  lea     rcx, [rsp+268h+var_138]
0x180132a6f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180132a74  nop
0x180132a75  lea     r8, [rsp+268h+var_1F0]
0x180132a7a  mov     rdx, rax
0x180132a7d  lea     rcx, [rsp+268h+var_118]
0x180132a85  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
  ... truncated ...
```
