# EapHost::Peer::Host::SendPacketEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)

- ea: `0x180029bc0`
- end: `0x180029c8c`
- name: `?SendPacketEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z`
- size: `204`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, const struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800294c8`

## callees

- `0x180009728`
- `0x180022438`
- `0x180022b84`
- `0x180022c34`
- `0x180022f18`
- `0x180029bc0`
- `0x18002b2d4`
- `0x18002b43c`
- `0x18002c1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029beb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029beb`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::SendPacketEapAuthenticationTipTest(
        EapHost::Peer::Host *this,
        const struct EapHost::Peer::PeerSession *a2)
{
  __int128 v2; // xmm0
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx
  _DWORD *v6; // rax
  __int128 v7; // [rsp+20h] [rbp-10h] BYREF
  char *v8; // [rsp+40h] [rbp+10h] BYREF
  _DWORD *v9; // [rsp+48h] [rbp+18h] BYREF

  v8 = (char *)this;
  v2 = *((_OWORD *)a2 + 7);
  v8 = 0;
  v7 = v2;
  v4 = CoTaskMemAlloc(0x158u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v9 = (_DWORD *)tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(
                   v4,
                   &v7);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
    (void **)&v8,
    (void **)&v9);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v9);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v8 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(
      &v8,
      &v9);
    v6 = v9;
    v9[81] = *((_DWORD *)a2 + 66);
    v6[82] = *((_DWORD *)a2 + 67);
    ++v6[70];
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v9);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v9);
  }
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v8);
}

```

## disassembly

```asm
0x180029bc0  mov     [rsp-8+arg_10], rbx
0x180029bc5  mov     [rsp-8+arg_0], rcx
0x180029bca  push    rbp
0x180029bcb  mov     rbp, rsp
0x180029bce  sub     rsp, 30h
0x180029bd2  movups  xmm0, xmmword ptr [rdx+70h]
0x180029bd6  mov     ecx, 158h; cb
0x180029bdb  mov     [rbp+arg_0], 0
0x180029be3  mov     rbx, rdx
0x180029be6  movdqu  [rbp+var_10], xmm0
0x180029beb  call    cs:__imp_CoTaskMemAlloc
0x180029bf1  test    rax, rax
0x180029bf4  jz      loc_180029C86
0x180029bfa  lea     rdx, [rbp+var_10]
0x180029bfe  mov     rcx, rax
0x180029c01  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x180029c06  lea     rdx, [rbp+arg_8]
0x180029c0a  mov     [rbp+arg_8], rax
0x180029c0e  lea     rcx, [rbp+arg_0]
0x180029c12  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x180029c17  lea     rcx, [rbp+arg_8]
0x180029c1b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180029c20  mov     rcx, [rbp+arg_0]
0x180029c24  add     rcx, 8
0x180029c28  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180029c2d  test    al, al
0x180029c2f  jz      short loc_180029C72
0x180029c31  lea     rdx, [rbp+arg_8]
0x180029c35  lea     rcx, [rbp+arg_0]
0x180029c39  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x180029c3e  mov     ecx, [rbx+108h]
0x180029c44  mov     rax, [rbp+arg_8]
0x180029c48  mov     [rax+144h], ecx
0x180029c4e  mov     ecx, [rbx+10Ch]
0x180029c54  mov     [rax+148h], ecx
0x180029c5a  lea     rcx, [rbp+arg_8]
0x180029c5e  inc     dword ptr [rax+118h]
0x180029c64  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x180029c69  lea     rcx, [rbp+arg_8]
0x180029c6d  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x180029c72  lea     rcx, [rbp+arg_0]
0x180029c76  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180029c7b  mov     rbx, [rsp+30h+arg_10]
0x180029c80  add     rsp, 30h
0x180029c84  pop     rbp
0x180029c85  retn
0x180029c86  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
