# EapHost::Peer::Host::CompleteEapAuthenticationTipTest(EapHost::Peer::PeerSession &)

- ea: `0x180024604`
- end: `0x180024736`
- name: `?CompleteEapAuthenticationTipTest@Host@Peer@EapHost@@AEBAXAEAVPeerSession@23@@Z`
- size: `306`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025770`

## callees

- `0x18000abe4`
- `0x18000b9ac`
- `0x180022e94`
- `0x1800237b4`
- `0x18002386c`
- `0x180023b80`
- `0x180024604`
- `0x18002c23c`
- `0x18002c26c`
- `0x18002c3b4`
- `0x18002d148`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024679`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024679`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::CompleteEapAuthenticationTipTest(
        EapHost::Peer::Host *this,
        struct EapHost::Peer::PeerSession *a2)
{
  __int128 v2; // xmm0
  _QWORD *v4; // rax
  unsigned int v5; // ebx
  DWORD TickCount; // eax
  DWORD v7; // edx
  bool v8; // cf
  __int128 *v9; // rax
  __int64 v10; // rbx
  __int128 v11; // [rsp+20h] [rbp-10h] BYREF
  EapHost::Peer::Host *v12; // [rsp+50h] [rbp+20h] BYREF
  __int128 *v13; // [rsp+58h] [rbp+28h] BYREF
  __int64 v14; // [rsp+60h] [rbp+30h] BYREF

  v12 = this;
  v2 = *((_OWORD *)a2 + 7);
  v12 = 0;
  v13 = &v11;
  v11 = v2;
  v4 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,_GUID * &>(
         &v14,
         &v13);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
    &v12,
    v4);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v14);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started((char *)v12 + 8) )
  {
    tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(
      &v12,
      &v13);
    v5 = *((_DWORD *)a2 + 91);
    TickCount = GetTickCount();
    v7 = TickCount - v5;
    v8 = TickCount < v5;
    v9 = v13;
    if ( v8 )
      v7 = 0;
    *((_QWORD *)v13 + 37) = v7;
    if ( *((_DWORD *)a2 + 65) != 7 )
      *((_BYTE *)v9 + 308) = *((_DWORD *)a2 + 68) == 2;
    *((_DWORD *)v9 + 82) = *((_DWORD *)a2 + 67);
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(&v13);
    if ( v12 )
    {
      v10 = (__int64)v12 + 8;
      wil::EnterCriticalSection(&v14, (char *)v12 + 200);
      *(_DWORD *)(v10 + 64) |= 0x300u;
      if ( *(_QWORD *)(v10 + 240) )
        tip2::details::shared_data<1,0,0>::complete_helper(v10, 2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v14);
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(&v13);
  }
  *((GUID *)a2 + 7) = GUID_NULL;
  wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v12);
}

```

## disassembly

```asm
0x180024604  mov     [rsp-18h+arg_0], rcx
0x180024609  push    rbp
0x18002460a  push    rbx
0x18002460b  push    rdi
0x18002460c  mov     rbp, rsp
0x18002460f  sub     rsp, 30h
0x180024613  movups  xmm0, xmmword ptr [rdx+70h]
0x180024617  mov     rdi, rdx
0x18002461a  mov     [rbp+arg_0], 0
0x180024622  lea     rax, [rbp+var_10]
0x180024626  lea     rdx, [rbp+arg_8]
0x18002462a  mov     [rbp+arg_8], rax
0x18002462e  lea     rcx, [rbp+arg_10]
0x180024632  movdqu  [rbp+var_10], xmm0
0x180024637  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,_GUID * &>(_GUID * &)
0x18002463c  mov     rdx, rax
0x18002463f  lea     rcx, [rbp+arg_0]
0x180024643  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x180024648  lea     rcx, [rbp+arg_10]
0x18002464c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x180024651  mov     rcx, [rbp+arg_0]
0x180024655  add     rcx, 8
0x180024659  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18002465e  test    al, al
0x180024660  jz      loc_180024718
0x180024666  lea     rdx, [rbp+arg_8]
0x18002466a  lea     rcx, [rbp+arg_0]
0x18002466e  call    ?data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::data(void)
0x180024673  mov     ebx, [rdi+16Ch]
0x180024679  call    cs:__imp_GetTickCount
0x180024680  nop     dword ptr [rax+rax+00h]
0x180024685  xor     ecx, ecx
0x180024687  mov     edx, eax
0x180024689  sub     edx, ebx
0x18002468b  cmp     eax, ebx
0x18002468d  mov     rax, [rbp+arg_8]
0x180024691  cmovb   edx, ecx
0x180024694  mov     ecx, edx
0x180024696  mov     [rax+128h], rcx
0x18002469d  cmp     dword ptr [rdi+104h], 7
0x1800246a4  jz      short loc_1800246B6
0x1800246a6  cmp     dword ptr [rdi+110h], 2
0x1800246ad  setz    cl
0x1800246b0  mov     [rax+134h], cl
0x1800246b6  mov     ecx, [rdi+10Ch]
0x1800246bc  mov     [rax+148h], ecx
0x1800246c2  lea     rcx, [rbp+arg_8]
0x1800246c6  call    ?close@?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::close(void)
0x1800246cb  mov     rax, [rbp+arg_0]
0x1800246cf  test    rax, rax
0x1800246d2  jz      short loc_18002470F
0x1800246d4  lea     rbx, [rax+8]
0x1800246d8  lea     rdx, [rbx+0C0h]
0x1800246df  lea     rcx, [rbp+arg_10]
0x1800246e3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800246e8  or      dword ptr [rbx+40h], 300h
0x1800246ef  cmp     qword ptr [rbx+0F0h], 0
0x1800246f7  jz      short loc_180024706
0x1800246f9  mov     edx, 2
0x1800246fe  mov     rcx, rbx
0x180024701  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180024706  lea     rcx, [rbp+arg_10]
0x18002470a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002470f  lea     rcx, [rbp+arg_8]
0x180024713  call    ??1?$test_data_control@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>(void)
0x180024718  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002471f  lea     rcx, [rbp+arg_0]
0x180024723  movdqu  xmmword ptr [rdi+70h], xmm0
0x180024728  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x18002472d  add     rsp, 30h
0x180024731  pop     rdi
0x180024732  pop     rbx
0x180024733  pop     rbp
0x180024734  retn
```
