# NgcPolicy::VerifyLogonCertRAEnrollmentIsReady(NgcPolicyCheckEvent &,_AADPLUGIN_PRT_INFO const &)

- ea: `0x1800384dc`
- end: `0x1800386aa`
- name: `?VerifyLogonCertRAEnrollmentIsReady@NgcPolicy@@CAJAEAVNgcPolicyCheckEvent@@AEBU_AADPLUGIN_PRT_INFO@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(struct NgcPolicyCheckEvent *, const struct _AADPLUGIN_PRT_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180030a00`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000eda4`
- `0x18000f324`
- `0x18000fb60`
- `0x180012948`
- `0x18001378c`
- `0x1800137c8`
- `0x1800384dc`
- `0x1800386b0`

## import_xrefs

- `certenroll!__imp_IsLogonCertificateTemplateAvailable` at `0x180038545`
- `certenroll!__imp_IsLogonCertificateTemplateAvailable` at `0x180038545`

## string_xrefs

- `0x180038516`: `NgcPolicy::VerifyLogonCertRAEnrollmentIsReady`
- `0x18003855c`: `NgcPolicy::VerifyLogonCertRAEnrollmentIsReady`
- `0x180038620`: `NgcPolicy::VerifyLogonCertRAEnrollmentIsReady`
- `0x180038680`: `NgcPolicy::VerifyLogonCertRAEnrollmentIsReady`
- `0x18003868e`: `%s: { %s } stage succeeded { NgcCertEnrollmentRA is advertising,  cert template verified } `
- `0x180038524`: `%s: { %s } stage failed { NgcCertEnrollmentRA is advertising it's NOT ready } `
- `0x18003862e`: `%s: { %s } stage failed { logon cert template state is %s  } `
- `0x180038555`: `IsLogonCertificateTemplateAvailable`
- `0x180038577`: `IsLogonCertificateTemplateAvailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcPolicy::VerifyLogonCertRAEnrollmentIsReady(
        struct NgcPolicyCheckEvent *a1,
        const struct _AADPLUGIN_PRT_INFO *a2,
        __int64 a3)
{
  int v5; // eax
  unsigned int v6; // r14d
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 CorrelationId; // rax
  __int64 PolicyResult; // rax
  __int64 v11; // r8
  __int64 LogonTemplateName; // rax
  __int64 v13; // r8
  _BYTE v14[8]; // [rsp+20h] [rbp-39h] BYREF
  std::_Ref_count_base *v15; // [rsp+28h] [rbp-31h]
  _BYTE v16[32]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[64]; // [rsp+70h] [rbp+17h] BYREF
  unsigned int v19; // [rsp+C8h] [rbp+6Fh] BYREF
  _BYTE *v20; // [rsp+D0h] [rbp+77h]
  _BYTE *v21; // [rsp+D8h] [rbp+7Fh]

  if ( !*((_BYTE *)a2 + 16) )
  {
    *(_DWORD *)(*(_QWORD *)NgcPolicyCheckEvent::GetPolicyResult(a1, v14, a3) + 36LL) = 0;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    Logger::TraceWarning(
      (wchar_t *)L"%s: { %s } stage failed { NgcCertEnrollmentRA is advertising it's NOT ready } ",
      L"NgcPolicyCheck",
      L"NgcPolicy::VerifyLogonCertRAEnrollmentIsReady");
    return 1;
  }
  v19 = -1;
  v5 = IsLogonCertificateTemplateAvailable(&v19);
  v6 = v5;
  if ( v5 >= 0 )
  {
    PolicyResult = NgcPolicyCheckEvent::GetPolicyResult(a1, v14, v19);
    *(_DWORD *)(*(_QWORD *)PolicyResult + 44LL) = v11;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v19 )
    {
      *(_DWORD *)(*(_QWORD *)NgcPolicyCheckEvent::GetPolicyResult(a1, v14, v11) + 40LL) = 0;
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      LogonTemplateName = GetLogonTemplateName(v19);
      Logger::TraceWarning(
        (wchar_t *)L"%s: { %s } stage failed { logon cert template state is %s  } ",
        L"NgcPolicyCheck",
        L"NgcPolicy::VerifyLogonCertRAEnrollmentIsReady",
        LogonTemplateName);
      return 1;
    }
    *(_DWORD *)(*(_QWORD *)NgcPolicyCheckEvent::GetPolicyResult(a1, v14, v11) + 36LL) = 1;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    *(_DWORD *)(*(_QWORD *)NgcPolicyCheckEvent::GetPolicyResult(a1, v14, v13) + 40LL) = 1;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    Logger::TraceInformation(
      L"%s: { %s } stage succeeded { NgcCertEnrollmentRA is advertising,  cert template verified } ",
      L"NgcPolicyCheck",
      L"NgcPolicy::VerifyLogonCertRAEnrollmentIsReady");
    return 0;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"NgcPolicy::VerifyLogonCertRAEnrollmentIsReady",
      L"IsLogonCertificateTemplateAvailable",
      (unsigned int)v5);
    v20 = v16;
    v7 = std::wstring::wstring((__int64)v16, (__int64)L"IsLogonCertificateTemplateAvailable");
    v21 = v17;
    v8 = std::wstring::wstring((__int64)v17, (__int64)L"NgcPolicyCheck");
    CorrelationId = NgcPolicyCheckEvent::GetCorrelationId(a1, v18);
    NgcPolicy::WriteTelemetryFailure(CorrelationId, v8, v7, v6);
    return v6;
  }
}

```

## disassembly

```asm
0x1800384dc  push    rbp
0x1800384de  push    rbx
0x1800384df  push    rsi
0x1800384e0  push    rdi
0x1800384e1  push    r14
0x1800384e3  lea     rbp, [rsp-37h]
0x1800384e8  sub     rsp, 90h
0x1800384ef  mov     rsi, rcx
0x1800384f2  xor     ebx, ebx
0x1800384f4  cmp     [rdx+10h], bl
0x1800384f7  jnz     short loc_18003853A
0x1800384f9  lea     rdx, [rbp+57h+var_90]
0x1800384fd  call    ?GetPolicyResult@NgcPolicyCheckEvent@@QEAA?AV?$shared_ptr@U_NgcPolicyCheckResult@@@std@@XZ; NgcPolicyCheckEvent::GetPolicyResult(void)
0x180038502  mov     rcx, [rax]
0x180038505  mov     [rcx+24h], ebx
0x180038508  mov     rcx, [rbp+57h+var_88]; this
0x18003850c  test    rcx, rcx
0x18003850f  jz      short loc_180038516
0x180038511  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180038516  lea     r8, aNgcpolicyVerif_2; "NgcPolicy::VerifyLogonCertRAEnrollmentI"...
0x18003851d  lea     rdx, aNgcpolicycheck; "NgcPolicyCheck"
0x180038524  lea     rcx, aSSStageFailedN; "%s: { %s } stage failed { NgcCertEnroll"...
0x18003852b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180038530  mov     eax, 1
0x180038535  jmp     loc_18003869C
0x18003853a  mov     [rbp+57h+arg_8], 0FFFFFFFFh
0x180038541  lea     rcx, [rbp+57h+arg_8]
0x180038545  call    cs:__imp_IsLogonCertificateTemplateAvailable
0x18003854b  mov     r14d, eax
0x18003854e  test    eax, eax
0x180038550  jns     short loc_1800385CB
0x180038552  mov     r9d, eax
0x180038555  lea     r8, aIslogoncertifi; "IsLogonCertificateTemplateAvailable"
0x18003855c  lea     rdx, aNgcpolicyVerif_2; "NgcPolicy::VerifyLogonCertRAEnrollmentI"...
0x180038563  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003856a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003856f  lea     rax, [rbp+57h+var_80]
0x180038573  mov     [rbp+57h+arg_10], rax
0x180038577  lea     rdx, aIslogoncertifi; "IsLogonCertificateTemplateAvailable"
0x18003857e  lea     rcx, [rbp+57h+var_80]
0x180038582  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180038587  mov     rdi, rax
0x18003858a  lea     rax, [rbp+57h+var_60]
0x18003858e  mov     [rbp+57h+arg_18], rax
0x180038592  lea     rdx, aNgcpolicycheck; "NgcPolicyCheck"
0x180038599  lea     rcx, [rbp+57h+var_60]
0x18003859d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800385a2  mov     rbx, rax
0x1800385a5  lea     rdx, [rbp+57h+var_40]
0x1800385a9  mov     rcx, rsi
0x1800385ac  call    ?GetCorrelationId@NgcPolicyCheckEvent@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcPolicyCheckEvent::GetCorrelationId(void)
0x1800385b1  nop
0x1800385b2  mov     r9d, r14d
0x1800385b5  mov     r8, rdi
0x1800385b8  mov     rdx, rbx
0x1800385bb  mov     rcx, rax
0x1800385be  call    ?WriteTelemetryFailure@NgcPolicy@@CAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00J@Z; NgcPolicy::WriteTelemetryFailure(std::wstring,std::wstring,std::wstring,long)
0x1800385c3  mov     eax, r14d
0x1800385c6  jmp     loc_18003869C
0x1800385cb  mov     r8d, [rbp+57h+arg_8]
0x1800385cf  lea     rdx, [rbp+57h+var_90]
0x1800385d3  mov     rcx, rsi
0x1800385d6  call    ?GetPolicyResult@NgcPolicyCheckEvent@@QEAA?AV?$shared_ptr@U_NgcPolicyCheckResult@@@std@@XZ; NgcPolicyCheckEvent::GetPolicyResult(void)
0x1800385db  mov     rcx, [rax]
0x1800385de  mov     [rcx+2Ch], r8d
0x1800385e2  mov     rcx, [rbp+57h+var_88]; this
0x1800385e6  test    rcx, rcx
0x1800385e9  jz      short loc_1800385F0
0x1800385eb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800385f0  lea     rdx, [rbp+57h+var_90]
0x1800385f4  mov     rcx, rsi
0x1800385f7  cmp     [rbp+57h+arg_8], ebx
0x1800385fa  jz      short loc_18003863F
0x1800385fc  call    ?GetPolicyResult@NgcPolicyCheckEvent@@QEAA?AV?$shared_ptr@U_NgcPolicyCheckResult@@@std@@XZ; NgcPolicyCheckEvent::GetPolicyResult(void)
0x180038601  mov     rcx, [rax]
0x180038604  mov     [rcx+28h], ebx
0x180038607  mov     rcx, [rbp+57h+var_88]; this
0x18003860b  test    rcx, rcx
0x18003860e  jz      short loc_180038615
0x180038610  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180038615  mov     ecx, [rbp+57h+arg_8]
0x180038618  call    ?GetLogonTemplateName@@YAPEBGW4LogonTemplateState@@@Z; GetLogonTemplateName(LogonTemplateState)
0x18003861d  mov     r9, rax
0x180038620  lea     r8, aNgcpolicyVerif_2; "NgcPolicy::VerifyLogonCertRAEnrollmentI"...
0x180038627  lea     rdx, aNgcpolicycheck; "NgcPolicyCheck"
0x18003862e  lea     rcx, aSSStageFailedL; "%s: { %s } stage failed { logon cert te"...
0x180038635  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18003863a  jmp     loc_180038530
0x18003863f  call    ?GetPolicyResult@NgcPolicyCheckEvent@@QEAA?AV?$shared_ptr@U_NgcPolicyCheckResult@@@std@@XZ; NgcPolicyCheckEvent::GetPolicyResult(void)
0x180038644  mov     rcx, [rax]
0x180038647  mov     dword ptr [rcx+24h], 1
0x18003864e  mov     rcx, [rbp+57h+var_88]; this
0x180038652  test    rcx, rcx
0x180038655  jz      short loc_18003865C
0x180038657  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003865c  lea     rdx, [rbp+57h+var_90]
0x180038660  mov     rcx, rsi
0x180038663  call    ?GetPolicyResult@NgcPolicyCheckEvent@@QEAA?AV?$shared_ptr@U_NgcPolicyCheckResult@@@std@@XZ; NgcPolicyCheckEvent::GetPolicyResult(void)
0x180038668  mov     rcx, [rax]
0x18003866b  mov     dword ptr [rcx+28h], 1
0x180038672  mov     rcx, [rbp+57h+var_88]; this
0x180038676  test    rcx, rcx
0x180038679  jz      short loc_180038680
0x18003867b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180038680  lea     r8, aNgcpolicyVerif_2; "NgcPolicy::VerifyLogonCertRAEnrollmentI"...
0x180038687  lea     rdx, aNgcpolicycheck; "NgcPolicyCheck"
0x18003868e  lea     rcx, aSSStageSucceed; "%s: { %s } stage succeeded { NgcCertEnr"...
0x180038695  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18003869a  xor     eax, eax
0x18003869c  add     rsp, 90h
0x1800386a3  pop     r14
0x1800386a5  pop     rdi
0x1800386a6  pop     rsi
0x1800386a7  pop     rbx
0x1800386a8  pop     rbp
0x1800386a9  retn
```
