# indexer::result::details::log_error_code_exception(void *,uint,char const *,char const *,char const *,void *,long,char const *,char const *)

- ea: `0x180013ad8`
- end: `0x180013bec`
- name: `?log_error_code_exception@details@result@indexer@@YAXPEAXIPEBD110J11@Z`
- size: `276`
- prototype: `void __fastcall(indexer::result::details *this, void *, __int64, const char *, const char *, const char *, wil::details *, __int64, const char *)`
- caller_count: `18`
- callee_count: `7`
- tags: ``

## callers

- `0x18001638f`
- `0x18001640c`
- `0x180016489`
- `0x180016506`
- `0x180016583`
- `0x180016603`
- `0x180016683`
- `0x180016703`
- `0x180016783`
- `0x1800167f9`
- `0x1800168d3`
- `0x1800169ad`
- `0x180016a2d`
- `0x180016aad`
- `0x180016b2d`
- `0x180016bad`
- `0x180016c5b`
- `0x180016cdb`

## callees

- `0x1800024a0`
- `0x18000377c`
- `0x180006b64`
- `0x180009688`
- `0x18001363c`
- `0x180013ad8`
- `0x180015650`

## pseudocode

```c
void __fastcall indexer::result::details::log_error_code_exception(
        indexer::result::details *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        const char *a6,
        wil::details *a7,
        __int64 a8,
        const char *a9)
{
  unsigned int v10; // esi
  wchar_t v12[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v10 = (unsigned int)a2;
  wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_44936384>::GetImpl'::`2'::impl) )
    StringCchPrintfW(v12, 0x100u, L"%hs: %hs", a8, a9);
  else
    StringCchPrintfW(v12, 0x800u, L"%hs: %hs", a8, a9);
  wil::details::ReportFailure_Base<1,0>(this, v10, a3);
}

```

## disassembly

```asm
0x180013ad8  mov     [rsp-8+arg_18], rbx
0x180013add  push    rbp
0x180013ade  push    rsi
0x180013adf  push    rdi
0x180013ae0  push    r12
0x180013ae2  push    r13
0x180013ae4  push    r14
0x180013ae6  push    r15
0x180013ae8  lea     rbp, [rsp-0F70h]
0x180013af0  mov     eax, 1070h
0x180013af5  call    _alloca_probe
0x180013afa  sub     rsp, rax
0x180013afd  mov     rax, cs:__security_cookie
0x180013b04  xor     rax, rsp
0x180013b07  mov     [rbp+0FA0h+var_40], rax
0x180013b0e  mov     r15, [rbp+0FA0h+arg_28]
0x180013b15  mov     r14, r8
0x180013b18  mov     r12, [rbp+0FA0h+arg_38]
0x180013b1f  mov     esi, edx
0x180013b21  mov     r13, [rbp+0FA0h+arg_40]
0x180013b28  mov     rdi, rcx
0x180013b2b  mov     ebx, dword ptr [rbp+0FA0h+arg_30]
0x180013b31  mov     ecx, ebx; this
0x180013b33  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013b38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_44936384@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384> `wil::Feature<__WilFeatureTraits_Feature_BugFix_44936384>::GetImpl(void)'::`2'::impl
0x180013b3f  mov     [rsp+10A0h+var_1050], eax
0x180013b43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::__private_IsEnabled(void)
0x180013b48  mov     [rsp+10A0h+var_1080], r13
0x180013b4d  mov     r9, r12
0x180013b50  lea     r8, aHsHs; "%hs: %hs"
0x180013b57  test    al, al
0x180013b59  jz      short loc_180013B79
0x180013b5b  mov     edx, 100h; unsigned __int64
0x180013b60  lea     rcx, [rsp+10A0h+var_1040]; wchar_t *
0x180013b65  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013b6a  mov     eax, [rsp+10A0h+var_1050]
0x180013b6e  mov     [rsp+10A0h+var_1048], eax
0x180013b72  lea     rax, [rsp+10A0h+var_1040]
0x180013b77  jmp     short loc_180013B95
0x180013b79  mov     edx, 800h; unsigned __int64
0x180013b7e  lea     rcx, [rsp+10A0h+var_1040]; wchar_t *
0x180013b83  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013b88  mov     eax, [rsp+10A0h+var_1050]
0x180013b8c  mov     [rsp+10A0h+var_1048], eax
0x180013b90  lea     rax, [rsp+10A0h+var_1040]
0x180013b95  mov     [rsp+10A0h+var_1068], rax
0x180013b9a  mov     r8, r14
0x180013b9d  lea     rax, [rsp+10A0h+var_104C]
0x180013ba2  mov     [rsp+10A0h+var_104C], ebx
0x180013ba6  mov     [rsp+10A0h+var_1070], rax
0x180013bab  mov     edx, esi
0x180013bad  mov     rcx, rdi
0x180013bb0  mov     [rsp+10A0h+var_1078], r15
0x180013bb5  mov     [rsp+10A0h+var_1044], 0
0x180013bbd  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180013bc2  mov     rcx, [rbp+0FA0h+var_40]
0x180013bc9  xor     rcx, rsp; StackCookie
0x180013bcc  call    __security_check_cookie
0x180013bd1  mov     rbx, [rsp+10A0h+arg_18]
0x180013bd9  add     rsp, 1070h
0x180013be0  pop     r15
0x180013be2  pop     r14
0x180013be4  pop     r13
0x180013be6  pop     r12
0x180013be8  pop     rdi
0x180013be9  pop     rsi
0x180013bea  pop     rbp
0x180013beb  retn
```
