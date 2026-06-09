# DSNotificationSink::OnUninstall(_GUID)

- ea: `0x1800134f4`
- end: `0x18001357a`
- name: `?OnUninstall@DSNotificationSink@@QEAAXU_GUID@@@Z`
- size: `134`
- prototype: `void(DSNotificationSink *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180013400`

## callees

- `0x18000c758`
- `0x18000f254`
- `0x18000f384`
- `0x18001213c`
- `0x180012194`
- `0x1800134f4`
- `0x180017318`

## pseudocode

```c
void __fastcall DSNotificationSink::OnUninstall(DSNotificationSink *this, struct _GUID *a2)
{
  __int64 *v3; // rbx
  int TokensByOwner; // eax
  __int64 v5; // rcx
  __int64 *v6; // rax
  __int64 **v7[5]; // [rsp+20h] [rbp-28h] BYREF

  v3 = tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get((__int64)this);
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v7);
  if ( *(_DWORD *)v3 )
  {
    TokensByOwner = SharingTokenDatabase::GetTokensByOwner((SharingTokenDatabase *)(v3 + 1), (__int64)a2, (__int64)v7);
    v5 = TokensByOwner + 0x80000000;
    if ( ((int)v5 < 0 || TokensByOwner == -1055719418) && (__int64 ***)v7[0] != v7 )
    {
      v6 = tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(v5);
      SharingTokenManager::RemoveSharingTokens((SharingTokenManager *)v6, v7);
    }
  }
  utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear((__int64)v7);
  SharingTokenManager::RemoveSharingTokensByShareScope((SharingTokenManager *)v3, a2);
}

```

## disassembly

```asm
0x1800134f4  mov     [rsp+arg_0], rbx
0x1800134f9  push    rdi
0x1800134fa  sub     rsp, 40h
0x1800134fe  mov     rdi, rdx
0x180013501  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x180013506  lea     rcx, [rsp+48h+var_28]
0x18001350b  mov     rbx, rax
0x18001350e  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x180013513  cmp     dword ptr [rbx], 0
0x180013516  jz      short loc_18001355A
0x180013518  lea     rcx, [rbx+8]; this
0x18001351c  mov     rdx, rdi
0x18001351f  lea     r8, [rsp+48h+var_28]
0x180013524  call    ?GetTokensByOwner@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; SharingTokenDatabase::GetTokensByOwner(_GUID const &,utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)
0x180013529  mov     edx, 80000000h
0x18001352e  lea     ecx, [rax+rdx]
0x180013531  test    edx, ecx
0x180013533  jnz     short loc_18001353C
0x180013535  cmp     eax, 0C1130006h
0x18001353a  jnz     short loc_18001355A
0x18001353c  lea     rax, [rsp+48h+var_28]
0x180013541  cmp     [rsp+48h+var_28], rax
0x180013546  jz      short loc_18001355A
0x180013548  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18001354d  lea     rdx, [rsp+48h+var_28]
0x180013552  mov     rcx, rax; this
0x180013555  call    ?RemoveSharingTokens@SharingTokenManager@@QEAAJAEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; SharingTokenManager::RemoveSharingTokens(utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)
0x18001355a  lea     rcx, [rsp+48h+var_28]
0x18001355f  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x180013564  mov     rdx, rdi; struct _GUID *
0x180013567  mov     rcx, rbx; this
0x18001356a  call    ?RemoveSharingTokensByShareScope@SharingTokenManager@@QEAAJAEBU_GUID@@@Z; SharingTokenManager::RemoveSharingTokensByShareScope(_GUID const &)
0x18001356f  mov     rbx, [rsp+48h+arg_0]
0x180013574  add     rsp, 40h
0x180013578  pop     rdi
0x180013579  retn
```
