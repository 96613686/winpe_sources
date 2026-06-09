# WriteBlockedGroupPolicies(void)

- ea: `0x18012a624`
- end: `0x18012aae9`
- name: `?WriteBlockedGroupPolicies@@YAJXZ`
- size: `1221`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e5594`
- `0x1800e6664`
- `0x1800e691c`
- `0x1800ece5c`
- `0x1800ee898`
- `0x1800ef5d8`
- `0x180104270`
- `0x1801058cc`
- `0x180105c40`
- `0x180115004`
- `0x180120ce0`
- `0x180126a14`
- `0x180126a64`
- `0x1801279ac`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012a624`
- `0x1801312d0`
- `0x180135ac4`

## import_xrefs

- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x18012a667`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x18012a667`

## string_xrefs

- `0x18012a75c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012a7b7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012a9b9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012a6a8`: `MDM Uris Blocking GP`
- `0x18012a722`: `Group Policies that were blocked from GP Engine because MDM has configured the equivalent policy`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 WriteBlockedGroupPolicies(void)
{
  int v0; // esi
  unsigned int **v2; // rbx
  _QWORD *v3; // rax
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
  v2 = (unsigned int **)std::vector<int>::vector<int>(&v19, &si128, v24);
  v3 = (_QWORD *)std::vector<std::wstring>::vector<std::wstring>(v16, v24, v25);
  v4 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
         (__int64)v22,
         (__int64)L"Group Policies that were blocked from GP Engine because MDM has configured the equivalent policy",
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
0x18012a624  push    rbx
0x18012a626  push    rsi
0x18012a627  push    rdi
0x18012a628  push    r14
0x18012a62a  sub     rsp, 138h
0x18012a631  mov     rax, cs:__security_cookie
0x18012a638  xor     rax, rsp
0x18012a63b  mov     [rsp+158h+var_38], rax
0x18012a643  xor     esi, esi
0x18012a645  mov     [rsp+158h+var_128], esi
0x18012a649  mov     [rsp+158h+var_128], esi
0x18012a64d  mov     qword ptr [rsp+158h+var_138], rsi; int
0x18012a652  lea     r9, [rsp+158h+var_128]
0x18012a657  lea     r8, aMdmwinsovergp; "MDMWinsOverGP"
0x18012a65e  lea     rdx, aControlpolicyc; "ControlPolicyConflict"
0x18012a665  xor     ecx, ecx
0x18012a667  call    cs:__imp_?EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed@@YAJW4EnrollmentEnrollType@@PEBG1PEAHPEAPEAE@Z; EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(EnrollmentEnrollType,ushort const *,ushort const *,int *,uchar * *)
0x18012a66d  cmp     [rsp+158h+var_128], esi
0x18012a671  jnz     short loc_18012A67B
0x18012a673  lea     eax, [rsi+5]
0x18012a676  jmp     loc_18012AACB
0x18012a67b  lea     rax, aBlockedGpEntit; "Blocked GP Entity"
0x18012a682  mov     [rsp+158h+var_58], rax
0x18012a68a  lea     rax, aBlockedGpValue; "Blocked GP Value Name"
0x18012a691  mov     [rsp+158h+var_50], rax
0x18012a699  lea     rax, aBlockedValue; "Blocked Value"
0x18012a6a0  mov     [rsp+158h+var_48], rax
0x18012a6a8  lea     rax, aMdmUrisBlockin; "MDM Uris Blocking GP"
0x18012a6af  mov     [rsp+158h+var_40], rax
0x18012a6b7  movdqa  xmm0, cs:__xmm@000000230000000a0000000f0000001e
0x18012a6bf  movdqu  [rsp+158h+var_68], xmm0
0x18012a6c8  lea     r8, aBlockedgrouppo; "BlockedGroupPoliciesTable"
0x18012a6cf  lea     rdx, aBlockedGroupPo; "Blocked Group Policies"
0x18012a6d6  lea     rcx, [rsp+158h+var_B8]; this
0x18012a6de  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x18012a6e3  nop
0x18012a6e4  lea     r8, [rsp+158h+var_58]
0x18012a6ec  lea     rdx, [rsp+158h+var_68]
0x18012a6f4  lea     rcx, [rsp+158h+var_F0]
0x18012a6f9  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x18012a6fe  mov     rbx, rax
0x18012a701  lea     r8, [rsp+158h+var_38]
0x18012a709  lea     rdx, [rsp+158h+var_58]
0x18012a711  lea     rcx, [rsp+158h+var_108]
0x18012a716  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18012a71b  nop
0x18012a71c  mov     r9, rbx
0x18012a71f  mov     r8, rax
0x18012a722  lea     rdx, aGroupPoliciesT; "Group Policies that were blocked from G"...
0x18012a729  lea     rcx, [rsp+158h+var_B8]
0x18012a731  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x18012a736  mov     ebx, eax
0x18012a738  lea     rcx, [rsp+158h+var_108]
0x18012a73d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012a742  nop
0x18012a743  lea     rcx, [rsp+158h+var_F0]
0x18012a748  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x18012a74d  test    ebx, ebx
0x18012a74f  jns     short loc_18012A791
0x18012a751  mov     rcx, [rsp+158h]; this
0x18012a759  mov     r9d, ebx; char *
0x18012a75c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012a763  mov     edx, 8EBh; void *
0x18012a768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a76d  nop
0x18012a76e  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012a775  mov     [rsp+158h+var_B8], rax
0x18012a77d  lea     rcx, [rsp+158h+var_B8]; this
0x18012a785  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012a78a  mov     eax, ebx
0x18012a78c  jmp     loc_18012AACB
0x18012a791  lea     rcx, [rsp+158h+var_120]
0x18012a796  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012a79b  nop
0x18012a79c  lea     rcx, [rsp+158h+var_120]; int
0x18012a7a1  call    ?RetrieveBlockedGroupPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies(std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>> &)
0x18012a7a6  mov     ebx, eax
0x18012a7a8  test    eax, eax
0x18012a7aa  jns     short loc_18012A828
0x18012a7ac  mov     rcx, [rsp+158h]; this
0x18012a7b4  mov     r9d, eax; char *
0x18012a7b7  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012a7be  mov     edx, 8EEh; void *
0x18012a7c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a7c8  nop
0x18012a7c9  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012a7ce  test    rcx, rcx
0x18012a7d1  jz      short loc_18012A805
0x18012a7d3  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012a7d8  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x18012a7dd  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012a7e2  mov     rdx, qword ptr [rsp+158h+var_118+8]
0x18012a7e7  sub     rdx, rcx
0x18012a7ea  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18012a7ee  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012a7f3  mov     qword ptr [rsp+158h+var_120], 0
0x18012a7fc  xorps   xmm0, xmm0
0x18012a7ff  movdqu  [rsp+158h+var_118], xmm0
0x18012a805  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012a80c  mov     [rsp+158h+var_B8], rax
0x18012a814  lea     rcx, [rsp+158h+var_B8]; this
0x18012a81c  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012a821  mov     eax, ebx
0x18012a823  jmp     loc_18012AACB
0x18012a828  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012a82d  mov     rdi, rcx
0x18012a830  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012a835  mov     r14, rdx
0x18012a838  cmp     rdi, r14
0x18012a83b  jz      loc_18012AA75
0x18012a841  mov     rdx, rdi
0x18012a844  lea     rcx, [rsp+158h+var_F0]
0x18012a849  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18012a84e  nop
0x18012a84f  lea     rcx, [rsp+158h+var_108]
0x18012a854  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012a859  nop
0x18012a85a  mov     rbx, [rsp+158h+var_F0]
0x18012a85f  mov     rdx, rbx
0x18012a862  lea     rcx, [rsp+158h+var_D8]
0x18012a86a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012a86f  nop
0x18012a870  mov     rdx, [rsp+158h+var_100]
0x18012a875  lea     rcx, [rsp+158h+var_108]
0x18012a87a  cmp     rdx, [rsp+158h+var_F8]
0x18012a87f  jz      short loc_18012A890
0x18012a881  lea     rdx, [rsp+158h+var_D8]
0x18012a889  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012a88e  jmp     short loc_18012A89E
0x18012a890  lea     r8, [rsp+158h+var_D8]
0x18012a898  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012a89d  nop
0x18012a89e  lea     rcx, [rsp+158h+var_D8]
0x18012a8a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a8ab  lea     rdx, [rbx+20h]
0x18012a8af  lea     rcx, [rsp+158h+var_D8]
0x18012a8b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012a8bc  nop
0x18012a8bd  mov     rdx, [rsp+158h+var_100]
0x18012a8c2  lea     rcx, [rsp+158h+var_108]
0x18012a8c7  cmp     rdx, [rsp+158h+var_F8]
0x18012a8cc  jz      short loc_18012A8DD
0x18012a8ce  lea     rdx, [rsp+158h+var_D8]
0x18012a8d6  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012a8db  jmp     short loc_18012A8EB
0x18012a8dd  lea     r8, [rsp+158h+var_D8]
0x18012a8e5  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012a8ea  nop
0x18012a8eb  lea     rcx, [rsp+158h+var_D8]
0x18012a8f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a8f8  lea     rdx, [rbx+40h]
0x18012a8fc  lea     rcx, [rsp+158h+var_D8]
0x18012a904  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012a909  nop
0x18012a90a  mov     rdx, [rsp+158h+var_100]
0x18012a90f  lea     rcx, [rsp+158h+var_108]
0x18012a914  cmp     rdx, [rsp+158h+var_F8]
0x18012a919  jz      short loc_18012A92A
0x18012a91b  lea     rdx, [rsp+158h+var_D8]
0x18012a923  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012a928  jmp     short loc_18012A938
0x18012a92a  lea     r8, [rsp+158h+var_D8]
0x18012a932  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012a937  nop
0x18012a938  lea     rcx, [rsp+158h+var_D8]
0x18012a940  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a945  lea     rdx, [rbx+60h]
0x18012a949  lea     rcx, [rsp+158h+var_D8]
0x18012a951  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012a956  nop
0x18012a957  mov     rdx, [rsp+158h+var_100]
0x18012a95c  lea     rcx, [rsp+158h+var_108]
0x18012a961  cmp     rdx, [rsp+158h+var_F8]
0x18012a966  jz      short loc_18012A977
0x18012a968  lea     rdx, [rsp+158h+var_D8]
0x18012a970  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012a975  jmp     short loc_18012A985
0x18012a977  lea     r8, [rsp+158h+var_D8]
0x18012a97f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012a984  nop
0x18012a985  lea     rcx, [rsp+158h+var_D8]
0x18012a98d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a992  lea     rdx, [rsp+158h+var_108]
0x18012a997  lea     rcx, [rsp+158h+var_B8]
0x18012a99f  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012a9a4  mov     ebx, eax
0x18012a9a6  test    eax, eax
0x18012a9a8  jns     loc_18012AA45
0x18012a9ae  mov     rcx, [rsp+158h]; this
0x18012a9b6  mov     r9d, eax; char *
0x18012a9b9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012a9c0  mov     edx, 8FAh; void *
0x18012a9c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a9ca  nop
0x18012a9cb  lea     rcx, [rsp+158h+var_108]
0x18012a9d0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012a9d5  nop
0x18012a9d6  mov     rcx, [rsp+158h+var_E8]; this
0x18012a9db  test    rcx, rcx
0x18012a9de  jz      short loc_18012A9E6
0x18012a9e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012a9e5  nop
0x18012a9e6  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012a9eb  test    rcx, rcx
0x18012a9ee  jz      short loc_18012AA22
0x18012a9f0  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012a9f5  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x18012a9fa  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012a9ff  mov     rdx, qword ptr [rsp+158h+var_118+8]
0x18012aa04  sub     rdx, rcx
0x18012aa07  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18012aa0b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012aa10  mov     qword ptr [rsp+158h+var_120], 0
0x18012aa19  xorps   xmm0, xmm0
0x18012aa1c  movdqu  [rsp+158h+var_118], xmm0
0x18012aa22  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012aa29  mov     [rsp+158h+var_B8], rax
0x18012aa31  lea     rcx, [rsp+158h+var_B8]; this
0x18012aa39  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012aa3e  mov     eax, ebx
0x18012aa40  jmp     loc_18012AACB
0x18012aa45  or      esi, 0Fh
0x18012aa48  lea     rcx, [rsp+158h+var_108]
0x18012aa4d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012aa52  nop
0x18012aa53  mov     rcx, [rsp+158h+var_E8]; this
0x18012aa58  test    rcx, rcx
0x18012aa5b  jz      short loc_18012AA62
0x18012aa5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012aa62  add     rdi, 10h
0x18012aa66  mov     rdx, qword ptr [rsp+158h+var_118]
0x18012aa6b  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012aa70  jmp     loc_18012A838
0x18012aa75  test    rcx, rcx
0x18012aa78  jz      short loc_18012AAA7
0x18012aa7a  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x18012aa7f  mov     rcx, qword ptr [rsp+158h+var_120]
0x18012aa84  mov     rdx, qword ptr [rsp+158h+var_118+8]
0x18012aa89  sub     rdx, rcx
0x18012aa8c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18012aa90  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012aa95  mov     qword ptr [rsp+158h+var_120], 0
0x18012aa9e  xorps   xmm0, xmm0
0x18012aaa1  movdqu  [rsp+158h+var_118], xmm0
0x18012aaa7  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x18012aaae  mov     [rsp+158h+var_B8], rax
0x18012aab6  lea     rcx, [rsp+158h+var_B8]; this
0x18012aabe  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18012aac3  xor     eax, eax
0x18012aac5  jmp     short loc_18012AACB
0x18012aac7  mov     eax, [rsp+158h+var_128]
0x18012aacb  mov     rcx, [rsp+158h+var_38]
0x18012aad3  xor     rcx, rsp; StackCookie
0x18012aad6  call    __security_check_cookie
0x18012aadb  add     rsp, 138h
0x18012aae2  pop     r14
0x18012aae4  pop     rdi
0x18012aae5  pop     rsi
0x18012aae6  pop     rbx
0x18012aae7  retn
```
