# EapHost::Peer::Host::ReceivePacketEapAuthenticationTipTest(EapHost::Peer::PeerSession const &,EapHost::Peer::RequestActionValue::RequestActionType)

- ea: `0x1800286c8`
- end: `0x18002879b`
- name: `?ReceivePacketEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@W4RequestActionType@RequestActionValue@23@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028168`

## callees

- `0x180009728`
- `0x180022438`
- `0x180022b84`
- `0x180022c34`
- `0x180022f18`
- `0x1800286c8`
- `0x18002b2d4`
- `0x18002b43c`
- `0x18002c1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800286fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800286fb`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::Host::ReceivePacketEapAuthenticationTipTest(char *a1, __int64 a2, int a3)
{
  __int128 v3; // xmm0
  LPVOID v6; // rax
  wil::details::in1diag3 *v7; // rcx
  _DWORD *v8; // rax
  __int128 v10; // [rsp+20h] [rbp-10h] BYREF
  char *v11; // [rsp+40h] [rbp+10h] BYREF
  _DWORD *v12; // [rsp+48h] [rbp+18h] BYREF

  v11 = a1;
  v3 = *(_OWORD *)(a2 + 112);
  v11 = 0;
  v10 = v3;
  v6 = CoTaskMemAlloc(0x158u);
  if ( !v6 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v7);
  v12 = (_DWORD *)tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(
                    v6,
                    &v10);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
    (void **)&v11,
    (void **)&v12);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v12);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v11 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(
      &v11,
      &v12);
    v8 = v12;
    v12[80] = a3;
    ++v8[71];
    v8[82] = *(_DWORD *)(a2 + 268);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v12);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v12);
  }
  return wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v11);
}

```

## disassembly

```asm
0x1800286c8  mov     [rsp-8+arg_10], rbx
0x1800286cd  mov     [rsp-8+arg_18], rdi
0x1800286d2  mov     [rsp-8+arg_0], rcx
0x1800286d7  push    rbp
0x1800286d8  mov     rbp, rsp
0x1800286db  sub     rsp, 30h
0x1800286df  movups  xmm0, xmmword ptr [rdx+70h]
0x1800286e3  mov     ecx, 158h; cb
0x1800286e8  mov     [rbp+arg_0], 0
0x1800286f0  mov     edi, r8d
0x1800286f3  mov     rbx, rdx
0x1800286f6  movdqu  [rbp+var_10], xmm0
0x1800286fb  call    cs:__imp_CoTaskMemAlloc
0x180028701  test    rax, rax
0x180028704  jz      loc_180028795
0x18002870a  lea     rdx, [rbp+var_10]
0x18002870e  mov     rcx, rax
0x180028711  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x180028716  lea     rdx, [rbp+arg_8]
0x18002871a  mov     [rbp+arg_8], rax
0x18002871e  lea     rcx, [rbp+arg_0]
0x180028722  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x180028727  lea     rcx, [rbp+arg_8]
0x18002872b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180028730  mov     rcx, [rbp+arg_0]
0x180028734  add     rcx, 8
0x180028738  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18002873d  test    al, al
0x18002873f  jz      short loc_18002877C
0x180028741  lea     rdx, [rbp+arg_8]
0x180028745  lea     rcx, [rbp+arg_0]
0x180028749  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x18002874e  mov     rax, [rbp+arg_8]
0x180028752  mov     [rax+140h], edi
0x180028758  inc     dword ptr [rax+11Ch]
0x18002875e  mov     ecx, [rbx+10Ch]
0x180028764  mov     [rax+148h], ecx
0x18002876a  lea     rcx, [rbp+arg_8]
0x18002876e  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x180028773  lea     rcx, [rbp+arg_8]
0x180028777  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x18002877c  lea     rcx, [rbp+arg_0]
0x180028780  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180028785  mov     rbx, [rsp+30h+arg_10]
0x18002878a  mov     rdi, [rsp+30h+arg_18]
0x18002878f  add     rsp, 30h
0x180028793  pop     rbp
0x180028794  retn
0x180028795  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
