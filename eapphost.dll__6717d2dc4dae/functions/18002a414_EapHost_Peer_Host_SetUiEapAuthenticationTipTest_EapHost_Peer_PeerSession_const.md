# EapHost::Peer::Host::SetUiEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)

- ea: `0x18002a414`
- end: `0x18002a4e6`
- name: `?SetUiEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z`
- size: `210`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, const struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a0b8`

## callees

- `0x180009728`
- `0x180022438`
- `0x180022b84`
- `0x180022c34`
- `0x180022f18`
- `0x18002a414`
- `0x18002b2d4`
- `0x18002b43c`
- `0x18002c1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a43f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a43f`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::SetUiEapAuthenticationTipTest(
        EapHost::Peer::Host *this,
        const struct EapHost::Peer::PeerSession *a2)
{
  __int128 v2; // xmm0
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx
  char v6; // cl
  _BYTE *v7; // rax
  __int128 v8; // [rsp+20h] [rbp-10h] BYREF
  char *v9; // [rsp+40h] [rbp+10h] BYREF
  _BYTE *v10; // [rsp+48h] [rbp+18h] BYREF

  v9 = (char *)this;
  v2 = *((_OWORD *)a2 + 7);
  v9 = 0;
  v8 = v2;
  v4 = CoTaskMemAlloc(0x158u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v10 = (_BYTE *)tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(
                   v4,
                   &v8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
    (void **)&v9,
    (void **)&v10);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v10);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v9 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(
      &v9,
      &v10);
    v6 = 2;
    v7 = v10;
    if ( *((_DWORD *)a2 + 67) != 1 )
      v6 = 8;
    v10[332] |= v6;
    *((_DWORD *)v7 + 82) = *((_DWORD *)a2 + 67);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v10);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v10);
  }
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v9);
}

```

## disassembly

```asm
0x18002a414  mov     [rsp-8+arg_10], rbx
0x18002a419  mov     [rsp-8+arg_0], rcx
0x18002a41e  push    rbp
0x18002a41f  mov     rbp, rsp
0x18002a422  sub     rsp, 30h
0x18002a426  movups  xmm0, xmmword ptr [rdx+70h]
0x18002a42a  mov     ecx, 158h; cb
0x18002a42f  mov     [rbp+arg_0], 0
0x18002a437  mov     rbx, rdx
0x18002a43a  movdqu  [rbp+var_10], xmm0
0x18002a43f  call    cs:__imp_CoTaskMemAlloc
0x18002a445  test    rax, rax
0x18002a448  jz      loc_18002A4E0
0x18002a44e  lea     rdx, [rbp+var_10]
0x18002a452  mov     rcx, rax
0x18002a455  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x18002a45a  lea     rdx, [rbp+arg_8]
0x18002a45e  mov     [rbp+arg_8], rax
0x18002a462  lea     rcx, [rbp+arg_0]
0x18002a466  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x18002a46b  lea     rcx, [rbp+arg_8]
0x18002a46f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x18002a474  mov     rcx, [rbp+arg_0]
0x18002a478  add     rcx, 8
0x18002a47c  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18002a481  test    al, al
0x18002a483  jz      short loc_18002A4CC
0x18002a485  lea     rdx, [rbp+arg_8]
0x18002a489  lea     rcx, [rbp+arg_0]
0x18002a48d  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x18002a492  cmp     dword ptr [rbx+10Ch], 1
0x18002a499  mov     ecx, 2
0x18002a49e  mov     rax, [rbp+arg_8]
0x18002a4a2  lea     edx, [rcx+6]
0x18002a4a5  cmovnz  ecx, edx
0x18002a4a8  or      [rax+14Ch], cl
0x18002a4ae  mov     ecx, [rbx+10Ch]
0x18002a4b4  mov     [rax+148h], ecx
0x18002a4ba  lea     rcx, [rbp+arg_8]
0x18002a4be  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x18002a4c3  lea     rcx, [rbp+arg_8]
0x18002a4c7  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x18002a4cc  lea     rcx, [rbp+arg_0]
0x18002a4d0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x18002a4d5  mov     rbx, [rsp+30h+arg_10]
0x18002a4da  add     rsp, 30h
0x18002a4de  pop     rbp
0x18002a4df  retn
0x18002a4e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
