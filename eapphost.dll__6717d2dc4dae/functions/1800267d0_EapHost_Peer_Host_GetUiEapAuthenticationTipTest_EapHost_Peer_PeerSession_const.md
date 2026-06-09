# EapHost::Peer::Host::GetUiEapAuthenticationTipTest(EapHost::Peer::PeerSession const &)

- ea: `0x1800267d0`
- end: `0x1800268a1`
- name: `?GetUiEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEBVPeerSession@23@@Z`
- size: `209`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, const struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026578`

## callees

- `0x180009728`
- `0x180022438`
- `0x180022b84`
- `0x180022c34`
- `0x180022f18`
- `0x1800267d0`
- `0x18002b2d4`
- `0x18002b43c`
- `0x18002c1a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800267fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800267fb`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::GetUiEapAuthenticationTipTest(
        EapHost::Peer::Host *this,
        const struct EapHost::Peer::PeerSession *a2)
{
  __int128 v2; // xmm0
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx
  _BYTE *v6; // rax
  char v7; // cl
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
    v6 = v10;
    v7 = 1;
    if ( *((_DWORD *)a2 + 67) != 1 )
      v7 = 4;
    v10[332] |= v7;
    *((_DWORD *)v6 + 82) = *((_DWORD *)a2 + 67);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v10);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v10);
  }
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>((void **)&v9);
}

```

## disassembly

```asm
0x1800267d0  mov     [rsp-8+arg_10], rbx
0x1800267d5  mov     [rsp-8+arg_0], rcx
0x1800267da  push    rbp
0x1800267db  mov     rbp, rsp
0x1800267de  sub     rsp, 30h
0x1800267e2  movups  xmm0, xmmword ptr [rdx+70h]
0x1800267e6  mov     ecx, 158h; cb
0x1800267eb  mov     [rbp+arg_0], 0
0x1800267f3  mov     rbx, rdx
0x1800267f6  movdqu  [rbp+var_10], xmm0
0x1800267fb  call    cs:__imp_CoTaskMemAlloc
0x180026801  test    rax, rax
0x180026804  jz      loc_18002689B
0x18002680a  lea     rdx, [rbp+var_10]
0x18002680e  mov     rcx, rax
0x180026811  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x180026816  lea     rdx, [rbp+arg_8]
0x18002681a  mov     [rbp+arg_8], rax
0x18002681e  lea     rcx, [rbp+arg_0]
0x180026822  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x180026827  lea     rcx, [rbp+arg_8]
0x18002682b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180026830  mov     rcx, [rbp+arg_0]
0x180026834  add     rcx, 8
0x180026838  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18002683d  test    al, al
0x18002683f  jz      short loc_180026887
0x180026841  lea     rdx, [rbp+arg_8]
0x180026845  lea     rcx, [rbp+arg_0]
0x180026849  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x18002684e  mov     rax, [rbp+arg_8]
0x180026852  mov     ecx, 1
0x180026857  cmp     [rbx+10Ch], ecx
0x18002685d  lea     edx, [rcx+3]
0x180026860  cmovnz  ecx, edx
0x180026863  or      [rax+14Ch], cl
0x180026869  mov     ecx, [rbx+10Ch]
0x18002686f  mov     [rax+148h], ecx
0x180026875  lea     rcx, [rbp+arg_8]
0x180026879  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x18002687e  lea     rcx, [rbp+arg_8]
0x180026882  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x180026887  lea     rcx, [rbp+arg_0]
0x18002688b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180026890  mov     rbx, [rsp+30h+arg_10]
0x180026895  add     rsp, 30h
0x180026899  pop     rbp
0x18002689a  retn
0x18002689b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
