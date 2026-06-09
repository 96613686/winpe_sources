# EapHost::Peer::Host::SetEapAuthenticationTipTestResult(EapHost::Peer::PeerSession const &,tagEapHostPeerMethodResult const &)

- ea: `0x180029f3c`
- end: `0x18002a018`
- name: `?SetEapAuthenticationTipTestResult@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@AEBUtagEapHostPeerMethodResult@@@Z`
- size: `220`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, const struct EapHost::Peer::PeerSession *, const struct tagEapHostPeerMethodResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025b18`

## callees

- `0x180009728`
- `0x180022438`
- `0x180022b84`
- `0x180022c34`
- `0x180022f18`
- `0x180029f3c`
- `0x18002b2d4`
- `0x18002b43c`
- `0x18002c1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f6f`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::SetEapAuthenticationTipTestResult(
        EapHost::Peer::Host *this,
        const struct EapHost::Peer::PeerSession *a2,
        const struct tagEapHostPeerMethodResult *a3)
{
  __int128 v3; // xmm0
  LPVOID v6; // rax
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rax
  __int128 v9; // [rsp+20h] [rbp-10h] BYREF
  EapHost::Peer::Host *v10; // [rsp+40h] [rbp+10h] BYREF
  __int64 v11; // [rsp+48h] [rbp+18h] BYREF

  v10 = this;
  v3 = *((_OWORD *)a2 + 7);
  v10 = 0;
  v9 = v3;
  v6 = CoTaskMemAlloc(0x158u);
  if ( !v6 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v7);
  v11 = tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(
          v6,
          &v9);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
    &v10,
    &v11);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v11);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started((char *)v10 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(
      &v10,
      &v11);
    v8 = v11;
    *(_BYTE *)(v11 + 308) = a3->fIsSuccess;
    *(_DWORD *)(v8 + 304) = a3->dwFailureReasonCode;
    *(_DWORD *)(v8 + 328) = *((_DWORD *)a2 + 67);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v11);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v11);
  }
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v10);
}

```

## disassembly

```asm
0x180029f3c  mov     [rsp-8+arg_10], rbx
0x180029f41  mov     [rsp-8+arg_18], rdi
0x180029f46  mov     [rsp-8+arg_0], rcx
0x180029f4b  push    rbp
0x180029f4c  mov     rbp, rsp
0x180029f4f  sub     rsp, 30h
0x180029f53  movups  xmm0, xmmword ptr [rdx+70h]
0x180029f57  mov     ecx, 158h; cb
0x180029f5c  mov     [rbp+arg_0], 0
0x180029f64  mov     rdi, r8
0x180029f67  mov     rbx, rdx
0x180029f6a  movdqu  [rbp+var_10], xmm0
0x180029f6f  call    cs:__imp_CoTaskMemAlloc
0x180029f75  test    rax, rax
0x180029f78  jz      loc_18002A012
0x180029f7e  lea     rdx, [rbp+var_10]
0x180029f82  mov     rcx, rax
0x180029f85  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x180029f8a  lea     rdx, [rbp+arg_8]
0x180029f8e  mov     [rbp+arg_8], rax
0x180029f92  lea     rcx, [rbp+arg_0]
0x180029f96  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x180029f9b  lea     rcx, [rbp+arg_8]
0x180029f9f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180029fa4  mov     rcx, [rbp+arg_0]
0x180029fa8  add     rcx, 8
0x180029fac  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180029fb1  test    al, al
0x180029fb3  jz      short loc_180029FF9
0x180029fb5  lea     rdx, [rbp+arg_8]
0x180029fb9  lea     rcx, [rbp+arg_0]
0x180029fbd  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x180029fc2  cmp     dword ptr [rdi], 0
0x180029fc5  mov     rax, [rbp+arg_8]
0x180029fc9  setnz   cl
0x180029fcc  mov     [rax+134h], cl
0x180029fd2  mov     ecx, [rdi+4]
0x180029fd5  mov     [rax+130h], ecx
0x180029fdb  mov     ecx, [rbx+10Ch]
0x180029fe1  mov     [rax+148h], ecx
0x180029fe7  lea     rcx, [rbp+arg_8]
0x180029feb  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x180029ff0  lea     rcx, [rbp+arg_8]
0x180029ff4  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x180029ff9  lea     rcx, [rbp+arg_0]
0x180029ffd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x18002a002  mov     rbx, [rsp+30h+arg_10]
0x18002a007  mov     rdi, [rsp+30h+arg_18]
0x18002a00c  add     rsp, 30h
0x18002a010  pop     rbp
0x18002a011  retn
0x18002a012  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
