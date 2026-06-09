# WriteBlockedGroupPolicies(void)

- ea: `0x18012c258`
- end: `0x18012c723`
- name: `?WriteBlockedGroupPolicies@@YAJXZ`
- size: `1227`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e5744`
- `0x1800e6838`
- `0x1800e6b14`
- `0x1800ed46c`
- `0x1800eef28`
- `0x1800efd9c`
- `0x180105480`
- `0x180106b6c`
- `0x180106ee0`
- `0x1801165f0`
- `0x18012269c`
- `0x18012845c`
- `0x1801284b0`
- `0x180129498`
- `0x180129aac`
- `0x180129ee0`
- `0x18012c258`
- `0x1801330e0`
- `0x180137a54`

## import_xrefs

- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x18012c29b`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x18012c29b`

## string_xrefs

- `0x18012c396`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c3f1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c5f3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012c2e2`: `MDM Uris Blocking GP`
- `0x18012c35c`: `Group Policies that were blocked from GP Engine because MDM has configured the equivalent policy`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 WriteBlockedGroupPolicies(void)
{
  int v0; // esi
  __int64 v2; // rbx
  __int64 v3; // rax
  int v4; // ebx
  int BlockedGroupPolicies; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r14
  __int64 v11; // rbx
  int v12; // eax
  int v13; // [rsp+30h] [rbp-128h] BYREF
  int v14[2]; // [rsp+38h] [rbp-120h] BYREF
  __int128 v15; // [rsp+40h] [rbp-118h]
  _BYTE v16[8]; // [rsp+50h] [rbp-108h] BYREF
  __int64 v17; // [rsp+58h] [rbp-100h]
  __int64 v18; // [rsp+60h] [rbp-F8h]
  __int64 v19; // [rsp+68h] [rbp-F0h] BYREF
  std::_Ref_count_base *v20; // [rsp+70h] [rbp-E8h]
  _BYTE v21[32]; // [rsp+80h] [rbp-D8h] BYREF
  _QWORD v22[10]; // [rsp+A0h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-68h] BYREF
  _QWORD v24[4]; // [rsp+100h] [rbp-58h] BYREF
  _QWORD v25[7]; // [rsp+120h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v0 = 0;
  v13 = 0;
  EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(0, L"ControlPolicyConflict", L"MDMWinsOverGP", &v13);
  if ( !v13 )
    return 5;
  v24[0] = L"Blocked GP Entity";
  v24[1] = L"Blocked GP Value Name";
  v24[2] = L"Blocked Value";
  v24[3] = L"MDM Uris Blocking GP";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v22,
    L"Blocked Group Policies",
    L"BlockedGroupPoliciesTable");
  v2 = std::vector<int>::vector<int>(&v19, &si128, v24);
  v3 = std::vector<std::wstring>::vector<std::wstring>(v16, v24, v25);
  v4 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
         v22,
         L"Group Policies that were blocked from GP Engine because MDM has configured the equivalent policy",
         v3,
         v2);
  std::vector<std::wstring>::_Tidy(v16);
  std::vector<enum TpmCapabilityPT>::_Tidy(&v19);
  if ( v4 >= 0 )
  {
    std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v14);
    BlockedGroupPolicies = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies((__int64)v14);
    v6 = BlockedGroupPolicies;
    if ( BlockedGroupPolicies >= 0 )
    {
      v7 = *(_QWORD *)v14;
      v8 = *(_QWORD *)v14;
      v9 = v15;
      v10 = v15;
      while ( v8 != v10 )
      {
        std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
          &v19,
          v8);
        std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v16);
        v11 = v19;
        std::wstring::wstring(v21, v19);
        if ( v17 == v18 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v16, v17, v21);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v16, v21);
        std::wstring::_Tidy_deallocate(v21);
        std::wstring::wstring(v21, v11 + 32);
        if ( v17 == v18 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v16, v17, v21);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v16, v21);
        std::wstring::_Tidy_deallocate(v21);
        std::wstring::wstring(v21, v11 + 64);
        if ( v17 == v18 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v16, v17, v21);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v16, v21);
        std::wstring::_Tidy_deallocate(v21);
        std::wstring::wstring(v21, v11 + 96);
        if ( v17 == v18 )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v16, v17, v21);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v16, v21);
        std::wstring::_Tidy_deallocate(v21);
        v12 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v22, v16);
        v6 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8FA,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
            (const char *)(unsigned int)v12,
            0);
          std::vector<std::wstring>::_Tidy(v16);
          if ( v20 )
            std::_Ref_count_base::_Decref(v20);
          if ( *(_QWORD *)v14 )
          {
            std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(
              *(_QWORD *)v14,
              v15);
            std::_Deallocate<16>(*(_QWORD *)v14, (*((_QWORD *)&v15 + 1) - *(_QWORD *)v14) & 0xFFFFFFFFFFFFFFF0uLL);
            *(_QWORD *)v14 = 0;
            v15 = 0;
          }
          goto LABEL_8;
        }
        v0 |= 0xFu;
        std::vector<std::wstring>::_Tidy(v16);
        if ( v20 )
          std::_Ref_count_base::_Decref(v20);
        v8 += 16;
        v9 = v15;
        v7 = *(_QWORD *)v14;
      }
      if ( v7 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(
          v7,
          v9);
        std::_Deallocate<16>(*(_QWORD *)v14, (*((_QWORD *)&v15 + 1) - *(_QWORD *)v14) & 0xFFFFFFFFFFFFFFF0uLL);
        *(_QWORD *)v14 = 0;
        v15 = 0;
      }
      v22[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v22);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8EE,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)BlockedGroupPolicies,
        0);
      if ( *(_QWORD *)v14 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(
          *(_QWORD *)v14,
          v15);
        std::_Deallocate<16>(*(_QWORD *)v14, (*((_QWORD *)&v15 + 1) - *(_QWORD *)v14) & 0xFFFFFFFFFFFFFFF0uLL);
        *(_QWORD *)v14 = 0;
        v15 = 0;
      }
LABEL_8:
      v22[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v22);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8EB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v4,
      0);
    v22[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v22);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x18012c258  push    rbx
0x18012c25a  push    rsi
0x18012c25b  push    rdi
0x18012c25c  push    r14
0x18012c25e  sub     rsp, 138h
0x18012c265  mov     rax, cs:__security_cookie
0x18012c26c  xor     rax, rsp
0x18012c26f  mov     [rsp+158h+var_38], rax
0x18012c277  xor     esi, esi
0x18012c279  mov     [rsp+158h+var_128], esi
0x18012c27d  mov     [rsp+158h+var_128], esi
0x18012c281  mov     qword ptr [rsp+158h+var_138], rsi; int
0x18012c286  lea     r9, [rsp+158h+var_128]
0x18012c28b  lea     r8, aMdmwinsovergp; "MDMWinsOverGP"
0x18012c292  lea     rdx, aControlpolicyc; "ControlPolicyConflict"
0x18012c299  xor     ecx, ecx
0x18012c29b  call    cs:__imp_?EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed@@YAJW4EnrollmentEnrollType@@PEBG1PEAHPEAPEAE@Z; EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(EnrollmentEnrollType,ushort const *,ushort const *,int *,uchar * *)
0x18012c2a2  nop     dword ptr [rax+rax+00h]
0x18012c2a7  cmp     [rsp+158h+var_128], esi
0x18012c2ab  jnz     short loc_18012C2B5
0x18012c2ad  lea     eax, [rsi+5]
0x18012c2b0  jmp     loc_18012C705
0x18012c2b5  lea     rax, aBlockedGpEntit; "Blocked GP Entity"
0x18012c2bc  mov     [rsp+158h+var_58], rax
0x18012c2c4  lea     rax, aBlockedGpValue; "Blocked GP Value Name"
0x18012c2cb  mov     [rsp+158h+var_50], rax
0x18012c2d3  lea     rax, aBlockedValue; "Blocked Value"
0x18012c2da  mov     [rsp+158h+var_48], rax
0x18012c2e2  lea     rax, aMdmUrisBlockin; "MDM Uris Blocking GP"
0x18012c2e9  mov     [rsp+158h+var_40], rax
0x18012c2f1  movdqa  xmm0, cs:__xmm@000000230000000a0000000f0000001e
0x18012c2f9  movdqu  [rsp+158h+var_68], xmm0
0x18012c302  lea     r8, aBlockedgrouppo; "BlockedGroupPoliciesTable"
0x18012c309  lea     rdx, aBlockedGroupPo; "Blocked Group Policies"
0x18012c310  lea     rcx, [rsp+158h+var_B8]; this
0x18012c318  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x18012c31d  nop
0x18012c31e  lea     r8, [rsp+158h+var_58]
0x18012c326  lea     rdx, [rsp+158h+var_68]
0x18012c32e  lea     rcx, [rsp+158h+var_F0]
0x18012c333  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x18012c338  mov     rbx, rax
0x18012c33b  lea     r8, [rsp+158h+var_38]
0x18012c343  lea     rdx, [rsp+158h+var_58]
0x18012c34b  lea     rcx, [rsp+158h+var_108]
0x18012c350  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18012c355  nop
0x18012c356  mov     r9, rbx
0x18012c359  mov     r8, rax
0x18012c35c  lea     rdx, aGroupPoliciesT; "Group Policies that were blocked from G"...
0x18012c363  lea     rcx, [rsp+158h+var_B8]
0x18012c36b  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x18012c370  mov     ebx, eax
0x18012c372  lea     rcx, [rsp+158h+var_108]
0x18012c377  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012c37c  nop
0x18012c37d  lea     rcx, [rsp+158h+var_F0]
0x18012c382  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x18012c387  test    ebx, ebx
0x18012c389  jns     short loc_18012C3CB
0x18012c38b  mov     rcx, [rsp+158h]; this
0x18012c393  mov     r9d, ebx; char *
0x18012c396  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012c39d  mov     edx, 8EBh; void *
0x18012c3a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c3a7  nop
0x18012c3a8  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012c3af  mov     [rsp+158h+var_B8], rax
0x18012c3b7  lea     rcx, [rsp+158h+var_B8]; this
0x18012c3bf  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c3c4  mov     eax, ebx
0x18012c3c6  jmp     loc_18012C705
0x18012c3cb  lea     rcx, [rsp+158h+var_120]
0x18012c3d0  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012c3d5  nop
0x18012c3d6  lea     rcx, [rsp+158h+var_120]; int
0x18012c3db  call    ?RetrieveBlockedGroupPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies(std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>> &)
0x18012c3e0  mov     ebx, eax
0x18012c3e2  test    eax, eax
0x18012c3e4  jns     short loc_18012C462
0x18012c3e6  mov     rcx, [rsp+158h]; this
0x18012c3ee  mov     r9d, eax; char *
0x18012c3f1  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012c3f8  mov     edx, 8EEh; void *
0x18012c3fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c402  nop
0x18012c403  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c408  test    rcx, rcx
0x18012c40b  jz      short loc_18012C43F
0x18012c40d  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012c412  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x18012c417  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c41c  mov     rdx, qword ptr [rsp+158h+var_118+8]
0x18012c421  sub     rdx, rcx
0x18012c424  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18012c428  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012c42d  mov     qword ptr [rsp+158h+var_120], 0
0x18012c436  xorps   xmm0, xmm0
0x18012c439  movdqu  [rsp+158h+var_118], xmm0
0x18012c43f  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012c446  mov     [rsp+158h+var_B8], rax
0x18012c44e  lea     rcx, [rsp+158h+var_B8]; this
0x18012c456  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c45b  mov     eax, ebx
0x18012c45d  jmp     loc_18012C705
0x18012c462  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c467  mov     rdi, rcx
0x18012c46a  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012c46f  mov     r14, rdx
0x18012c472  cmp     rdi, r14
0x18012c475  jz      loc_18012C6AF
0x18012c47b  mov     rdx, rdi
0x18012c47e  lea     rcx, [rsp+158h+var_F0]
0x18012c483  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18012c488  nop
0x18012c489  lea     rcx, [rsp+158h+var_108]
0x18012c48e  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012c493  nop
0x18012c494  mov     rbx, [rsp+158h+var_F0]
0x18012c499  mov     rdx, rbx
0x18012c49c  lea     rcx, [rsp+158h+var_D8]
0x18012c4a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012c4a9  nop
0x18012c4aa  mov     rdx, [rsp+158h+var_100]
0x18012c4af  lea     rcx, [rsp+158h+var_108]
0x18012c4b4  cmp     rdx, [rsp+158h+var_F8]
0x18012c4b9  jz      short loc_18012C4CA
0x18012c4bb  lea     rdx, [rsp+158h+var_D8]
0x18012c4c3  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c4c8  jmp     short loc_18012C4D8
0x18012c4ca  lea     r8, [rsp+158h+var_D8]
0x18012c4d2  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c4d7  nop
0x18012c4d8  lea     rcx, [rsp+158h+var_D8]
0x18012c4e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c4e5  lea     rdx, [rbx+20h]
0x18012c4e9  lea     rcx, [rsp+158h+var_D8]
0x18012c4f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012c4f6  nop
0x18012c4f7  mov     rdx, [rsp+158h+var_100]
0x18012c4fc  lea     rcx, [rsp+158h+var_108]
0x18012c501  cmp     rdx, [rsp+158h+var_F8]
0x18012c506  jz      short loc_18012C517
0x18012c508  lea     rdx, [rsp+158h+var_D8]
0x18012c510  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c515  jmp     short loc_18012C525
0x18012c517  lea     r8, [rsp+158h+var_D8]
0x18012c51f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c524  nop
0x18012c525  lea     rcx, [rsp+158h+var_D8]
0x18012c52d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c532  lea     rdx, [rbx+40h]
0x18012c536  lea     rcx, [rsp+158h+var_D8]
0x18012c53e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012c543  nop
0x18012c544  mov     rdx, [rsp+158h+var_100]
0x18012c549  lea     rcx, [rsp+158h+var_108]
0x18012c54e  cmp     rdx, [rsp+158h+var_F8]
0x18012c553  jz      short loc_18012C564
0x18012c555  lea     rdx, [rsp+158h+var_D8]
0x18012c55d  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c562  jmp     short loc_18012C572
0x18012c564  lea     r8, [rsp+158h+var_D8]
0x18012c56c  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c571  nop
0x18012c572  lea     rcx, [rsp+158h+var_D8]
0x18012c57a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c57f  lea     rdx, [rbx+60h]
0x18012c583  lea     rcx, [rsp+158h+var_D8]
0x18012c58b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012c590  nop
0x18012c591  mov     rdx, [rsp+158h+var_100]
0x18012c596  lea     rcx, [rsp+158h+var_108]
0x18012c59b  cmp     rdx, [rsp+158h+var_F8]
0x18012c5a0  jz      short loc_18012C5B1
0x18012c5a2  lea     rdx, [rsp+158h+var_D8]
0x18012c5aa  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012c5af  jmp     short loc_18012C5BF
0x18012c5b1  lea     r8, [rsp+158h+var_D8]
0x18012c5b9  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012c5be  nop
0x18012c5bf  lea     rcx, [rsp+158h+var_D8]
0x18012c5c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012c5cc  lea     rdx, [rsp+158h+var_108]
0x18012c5d1  lea     rcx, [rsp+158h+var_B8]
0x18012c5d9  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012c5de  mov     ebx, eax
0x18012c5e0  test    eax, eax
0x18012c5e2  jns     loc_18012C67F
0x18012c5e8  mov     rcx, [rsp+158h]; this
0x18012c5f0  mov     r9d, eax; char *
0x18012c5f3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012c5fa  mov     edx, 8FAh; void *
0x18012c5ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c604  nop
0x18012c605  lea     rcx, [rsp+158h+var_108]
0x18012c60a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012c60f  nop
0x18012c610  mov     rcx, [rsp+158h+var_E8]; this
0x18012c615  test    rcx, rcx
0x18012c618  jz      short loc_18012C620
0x18012c61a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012c61f  nop
0x18012c620  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c625  test    rcx, rcx
0x18012c628  jz      short loc_18012C65C
0x18012c62a  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012c62f  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x18012c634  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c639  mov     rdx, qword ptr [rsp+158h+var_118+8]
0x18012c63e  sub     rdx, rcx
0x18012c641  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18012c645  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012c64a  mov     qword ptr [rsp+158h+var_120], 0
0x18012c653  xorps   xmm0, xmm0
0x18012c656  movdqu  [rsp+158h+var_118], xmm0
0x18012c65c  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012c663  mov     [rsp+158h+var_B8], rax
0x18012c66b  lea     rcx, [rsp+158h+var_B8]; this
0x18012c673  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c678  mov     eax, ebx
0x18012c67a  jmp     loc_18012C705
0x18012c67f  or      esi, 0Fh
0x18012c682  lea     rcx, [rsp+158h+var_108]
0x18012c687  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012c68c  nop
0x18012c68d  mov     rcx, [rsp+158h+var_E8]; this
0x18012c692  test    rcx, rcx
0x18012c695  jz      short loc_18012C69C
0x18012c697  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012c69c  add     rdi, 10h
0x18012c6a0  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012c6a5  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c6aa  jmp     loc_18012C472
0x18012c6af  test    rcx, rcx
0x18012c6b2  jz      short loc_18012C6E1
0x18012c6b4  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x18012c6b9  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012c6be  mov     rdx, qword ptr [rsp+158h+var_118+8]
0x18012c6c3  sub     rdx, rcx
0x18012c6c6  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18012c6ca  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012c6cf  mov     qword ptr [rsp+158h+var_120], 0
0x18012c6d8  xorps   xmm0, xmm0
0x18012c6db  movdqu  [rsp+158h+var_118], xmm0
0x18012c6e1  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012c6e8  mov     [rsp+158h+var_B8], rax
0x18012c6f0  lea     rcx, [rsp+158h+var_B8]; this
0x18012c6f8  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012c6fd  xor     eax, eax
0x18012c6ff  jmp     short loc_18012C705
0x18012c701  mov     eax, [rsp+158h+var_128]
0x18012c705  mov     rcx, [rsp+158h+var_38]
0x18012c70d  xor     rcx, rsp; StackCookie
0x18012c710  call    __security_check_cookie
0x18012c715  add     rsp, 138h
0x18012c71c  pop     r14
0x18012c71e  pop     rdi
0x18012c71f  pop     rsi
0x18012c720  pop     rbx
0x18012c721  retn
```
