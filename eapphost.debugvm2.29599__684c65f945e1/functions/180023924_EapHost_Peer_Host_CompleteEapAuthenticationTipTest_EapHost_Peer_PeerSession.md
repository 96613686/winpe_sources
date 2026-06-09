# EapHost::Peer::Host::CompleteEapAuthenticationTipTest(EapHost::Peer::PeerSession &)

- ea: `0x180023924`
- end: `0x180023a65`
- name: `?CompleteEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEAVPeerSession@23@@Z`
- size: `321`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024a8c`

## callees

- `0x180009728`
- `0x18000a780`
- `0x18000b4cc`
- `0x180022438`
- `0x180022b84`
- `0x180022c34`
- `0x180022f18`
- `0x180023924`
- `0x18002b2d4`
- `0x18002b304`
- `0x18002b43c`
- `0x18002c1a4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800239a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800239a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002394c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002394c`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::CompleteEapAuthenticationTipTest(
        EapHost::Peer::Host *this,
        struct EapHost::Peer::PeerSession *a2)
{
  __int128 v2; // xmm0
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx
  unsigned int v6; // ebx
  DWORD TickCount; // eax
  DWORD v8; // edx
  bool v9; // cf
  __int64 v10; // rax
  char *v11; // rbx
  __int128 v12; // [rsp+20h] [rbp-10h] BYREF
  EapHost::Peer::Host *v13; // [rsp+50h] [rbp+20h] BYREF
  __int64 v14; // [rsp+58h] [rbp+28h] BYREF
  char v15; // [rsp+60h] [rbp+30h] BYREF

  v13 = this;
  v2 = *((_OWORD *)a2 + 7);
  v13 = 0;
  v12 = v2;
  v4 = CoTaskMemAlloc(0x158u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  v14 = tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(
          v4,
          &v12);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
    &v13,
    &v14);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v14);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started((char *)v13 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(
      &v13,
      &v14);
    v6 = *((_DWORD *)a2 + 91);
    TickCount = GetTickCount();
    v8 = TickCount - v6;
    v9 = TickCount < v6;
    v10 = v14;
    if ( v9 )
      v8 = 0;
    *(_QWORD *)(v14 + 296) = v8;
    if ( *((_DWORD *)a2 + 65) != 7 )
      *(_BYTE *)(v10 + 308) = *((_DWORD *)a2 + 68) == 2;
    *(_DWORD *)(v10 + 328) = *((_DWORD *)a2 + 67);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v14);
    if ( v13 )
    {
      v11 = (char *)v13 + 8;
      wil::EnterCriticalSection(&v15, (char *)v13 + 200);
      *((_DWORD *)v11 + 16) |= 0x300u;
      if ( *((_QWORD *)v11 + 30) )
        tip2::details::shared_data<1,0,0>::complete_helper(v11, 2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v14);
  }
  *((GUID *)a2 + 7) = GUID_NULL;
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v13);
}

```

## disassembly

```asm
0x180023924  mov     [rsp-18h+arg_0], rcx
0x180023929  push    rbp
0x18002392a  push    rbx
0x18002392b  push    rdi
0x18002392c  mov     rbp, rsp
0x18002392f  sub     rsp, 30h
0x180023933  movups  xmm0, xmmword ptr [rdx+70h]
0x180023937  mov     ecx, 158h; cb
0x18002393c  mov     [rbp+arg_0], 0
0x180023944  mov     rdi, rdx
0x180023947  movdqu  [rbp+var_10], xmm0
0x18002394c  call    cs:__imp_CoTaskMemAlloc
0x180023952  test    rax, rax
0x180023955  jz      loc_180023A5F
0x18002395b  lea     rdx, [rbp+var_10]
0x18002395f  mov     rcx, rax
0x180023962  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x180023967  lea     rdx, [rbp+arg_8]
0x18002396b  mov     [rbp+arg_8], rax
0x18002396f  lea     rcx, [rbp+arg_0]
0x180023973  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x180023978  lea     rcx, [rbp+arg_8]
0x18002397c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180023981  mov     rcx, [rbp+arg_0]
0x180023985  add     rcx, 8
0x180023989  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18002398e  test    al, al
0x180023990  jz      loc_180023A42
0x180023996  lea     rdx, [rbp+arg_8]
0x18002399a  lea     rcx, [rbp+arg_0]
0x18002399e  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x1800239a3  mov     ebx, [rdi+16Ch]
0x1800239a9  call    cs:__imp_GetTickCount
0x1800239af  xor     ecx, ecx
0x1800239b1  mov     edx, eax
0x1800239b3  sub     edx, ebx
0x1800239b5  cmp     eax, ebx
0x1800239b7  mov     rax, [rbp+arg_8]
0x1800239bb  cmovb   edx, ecx
0x1800239be  mov     ecx, edx
0x1800239c0  mov     [rax+128h], rcx
0x1800239c7  cmp     dword ptr [rdi+104h], 7
0x1800239ce  jz      short loc_1800239E0
0x1800239d0  cmp     dword ptr [rdi+110h], 2
0x1800239d7  setz    cl
0x1800239da  mov     [rax+134h], cl
0x1800239e0  mov     ecx, [rdi+10Ch]
0x1800239e6  mov     [rax+148h], ecx
0x1800239ec  lea     rcx, [rbp+arg_8]
0x1800239f0  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x1800239f5  mov     rax, [rbp+arg_0]
0x1800239f9  test    rax, rax
0x1800239fc  jz      short loc_180023A39
0x1800239fe  lea     rbx, [rax+8]
0x180023a02  lea     rdx, [rbx+0C0h]
0x180023a09  lea     rcx, [rbp+arg_10]
0x180023a0d  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180023a12  or      dword ptr [rbx+40h], 300h
0x180023a19  cmp     qword ptr [rbx+0F0h], 0
0x180023a21  jz      short loc_180023A30
0x180023a23  mov     edx, 2
0x180023a28  mov     rcx, rbx
0x180023a2b  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180023a30  lea     rcx, [rbp+arg_10]
0x180023a34  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180023a39  lea     rcx, [rbp+arg_8]
0x180023a3d  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x180023a42  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180023a49  lea     rcx, [rbp+arg_0]
0x180023a4d  movdqu  xmmword ptr [rdi+70h], xmm0
0x180023a52  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180023a57  add     rsp, 30h
0x180023a5b  pop     rdi
0x180023a5c  pop     rbx
0x180023a5d  pop     rbp
0x180023a5e  retn
0x180023a5f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
