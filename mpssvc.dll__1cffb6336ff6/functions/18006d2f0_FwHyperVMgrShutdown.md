# FwHyperVMgrShutdown

- ea: `0x18006d2f0`
- end: `0x18006d558`
- name: `FwHyperVMgrShutdown`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18007e830`

## callees

- `0x180017110`
- `0x180038158`
- `0x180045fb8`
- `0x18005c5a0`
- `0x180065b18`
- `0x180066564`
- `0x1800680d0`
- `0x18006b6cc`
- `0x18006d2f0`
- `0x18006d560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006d333`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006d333`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d34a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d34a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d38f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d38f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d3c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d3c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006d3b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006d3b5`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x18006d36a`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x18006d36a`
- `fwbase!FwFree` at `0x18006d45e`
- `fwbase!FwFree` at `0x18006d45e`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x18006d4cb`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x18006d4cb`

## pseudocode

```c
__int64 FwHyperVMgrShutdown()
{
  struct _TP_WORK *v0; // rcx
  __int64 v1; // rsi
  __int64 v2; // rdi
  __int64 v3; // rcx
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  _QWORD *v6; // rbx
  __int64 result; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids);
  AcquireSRWLockExclusive(&stru_18012C958);
  gFwHyperVMgr = 0;
  ReleaseSRWLockExclusive(&stru_18012C958);
  if ( !*(&gFwHyperVMgr + 1) )
    FwCancelLock();
  if ( (_QWORD)xmmword_18012D0C0 )
  {
    PowerUnregisterSuspendResumeNotification();
    *(_QWORD *)&xmmword_18012D0C0 = 0;
  }
  if ( qword_18012D0B8 )
  {
    SetThreadpoolTimer(qword_18012D0B8, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &qword_18012D0B8,
      0);
  }
  v0 = (struct _TP_WORK *)(*off_180126498)[1];
  if ( v0 )
  {
    WaitForThreadpoolWorkCallbacks(v0, 0);
    CloseThreadpoolWork((PTP_WORK)(*off_180126498)[1]);
    (*off_180126498)[1] = 0;
  }
  v1 = 1;
  v2 = 32;
  do
  {
    v3 = **(_QWORD **)((char *)&gFwHyperVMgr + v2 + 40);
    v11 = v3;
    while ( !*(_BYTE *)(v3 + 25) )
    {
      FwFreeHyperVRuleContainer(*(_QWORD *)(v3 + 64));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>>>,std::_Iterator_base0>::operator++(&v11);
      v3 = v11;
    }
    v4 = *(_QWORD **)((char *)&gFwHyperVMgr + v2 + 40);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *>>>(
      (char *)&gFwHyperVMgr + v2 + 40,
      (char *)&gFwHyperVMgr + v2 + 40,
      v4[1]);
    v4[1] = v4;
    *v4 = v4;
    v4[2] = v4;
    *(_QWORD *)((char *)&gFwHyperVMgr + v2 + 48) = 0;
    v5 = **(_QWORD **)((char *)&gFwHyperVMgr + v2 + 56);
    v11 = v5;
    while ( !*(_BYTE *)(v5 + 25) )
    {
      FwFree(*(_QWORD *)(v5 + 48));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>,std::_Iterator_base0>::operator++(&v11);
      v5 = v11;
    }
    v6 = *(_QWORD **)((char *)&gFwHyperVMgr + v2 + 56);
    result = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *>>>(
               (char *)&gFwHyperVMgr + v2 + 56,
               (char *)&gFwHyperVMgr + v2 + 56,
               v6[1]);
    v6[1] = v6;
    ++v1;
    *v6 = v6;
    v6[2] = v6;
    *(_QWORD *)((char *)&gFwHyperVMgr + v2 + 64) = 0;
    v2 += 32;
  }
  while ( v1 != 13 );
  v8 = qword_18012C960;
  v9 = qword_18012C968;
  if ( qword_18012C960 != (void *)qword_18012C968 )
  {
    do
      result = FwFreeHyperVPortsBySchemaVersion(*v8++, 545);
    while ( v8 != (_QWORD *)v9 );
    if ( qword_18012C960 != (void *)qword_18012C968 )
      qword_18012C968 = (__int64)qword_18012C960;
  }
  v10 = *(_QWORD *)qword_18012CB18;
  v11 = *(_QWORD *)qword_18012CB18;
  while ( !*(_BYTE *)(v10 + 25) )
  {
    FwHyperVMgrFreeVmCreatorContainer(*(_QWORD *)(v10 + 48));
    result = std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>,std::_Iterator_base0>::operator++(&v11);
    v10 = v11;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    return WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18006d2f0  push    rbx
0x18006d2f2  push    rsi
0x18006d2f3  push    rdi
0x18006d2f4  push    r12
0x18006d2f6  push    r14
0x18006d2f8  push    r15
0x18006d2fa  sub     rsp, 28h
0x18006d2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d305  lea     r12, WPP_GLOBAL_Control
0x18006d30c  cmp     rcx, r12
0x18006d30f  jz      short loc_18006D32C
0x18006d311  test    byte ptr [rcx+1Ch], 8
0x18006d315  jz      short loc_18006D32C
0x18006d317  mov     rcx, [rcx+10h]
0x18006d31b  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18006d322  mov     edx, 16h
0x18006d327  call    WPP_SF_
0x18006d32c  lea     rcx, stru_18012C958; SRWLock
0x18006d333  call    cs:__imp_AcquireSRWLockExclusive
0x18006d339  lea     rcx, stru_18012C958; SRWLock
0x18006d340  mov     dword ptr cs:gFwHyperVMgr, 0
0x18006d34a  call    cs:__imp_ReleaseSRWLockExclusive
0x18006d350  cmp     dword ptr cs:gFwHyperVMgr+4, 0
0x18006d357  jnz     short loc_18006D35E
0x18006d359  call    FwCancelLock
0x18006d35e  mov     rcx, qword ptr cs:xmmword_18012D0C0
0x18006d365  test    rcx, rcx
0x18006d368  jz      short loc_18006D37B
0x18006d36a  call    cs:__imp_PowerUnregisterSuspendResumeNotification
0x18006d370  mov     qword ptr cs:xmmword_18012D0C0, 0
0x18006d37b  mov     rcx, cs:qword_18012D0B8; pti
0x18006d382  test    rcx, rcx
0x18006d385  jz      short loc_18006D3A3
0x18006d387  xor     r9d, r9d; msWindowLength
0x18006d38a  xor     r8d, r8d; msPeriod
0x18006d38d  xor     edx, edx; pftDueTime
0x18006d38f  call    cs:__imp_SetThreadpoolTimer
0x18006d395  xor     edx, edx
0x18006d397  lea     rcx, qword_18012D0B8
0x18006d39e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006d3a3  mov     rax, cs:off_180126498
0x18006d3aa  mov     rcx, [rax+8]; pwk
0x18006d3ae  test    rcx, rcx
0x18006d3b1  jz      short loc_18006D3DB
0x18006d3b3  xor     edx, edx; fCancelPendingCallbacks
0x18006d3b5  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18006d3bb  mov     rcx, cs:off_180126498
0x18006d3c2  mov     rcx, [rcx+8]; pwk
0x18006d3c6  call    cs:__imp_CloseThreadpoolWork
0x18006d3cc  mov     rax, cs:off_180126498
0x18006d3d3  mov     qword ptr [rax+8], 0
0x18006d3db  mov     esi, 1
0x18006d3e0  lea     r15, gFwHyperVMgr
0x18006d3e7  lea     edi, [rsi+1Fh]
0x18006d3ea  lea     r14, [rdi+r15]
0x18006d3ee  mov     rcx, [r14+28h]
0x18006d3f2  mov     rcx, [rcx]
0x18006d3f5  mov     [rsp+58h+arg_0], rcx
0x18006d3fa  cmp     byte ptr [rcx+19h], 0
0x18006d3fe  jnz     short loc_18006D41A
0x18006d400  mov     rcx, [rcx+40h]
0x18006d404  call    FwFreeHyperVRuleContainer
0x18006d409  lea     rcx, [rsp+58h+arg_0]
0x18006d40e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>>>,std::_Iterator_base0>::operator++(void)
0x18006d413  mov     rcx, [rsp+58h+arg_0]
0x18006d418  jmp     short loc_18006D3FA
0x18006d41a  mov     rbx, [rdi+r15+28h]
0x18006d41f  lea     rdx, [r14+28h]
0x18006d423  lea     rcx, [r14+28h]
0x18006d427  mov     r8, [rbx+8]
0x18006d42b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *> *)
0x18006d430  mov     [rbx+8], rbx
0x18006d434  lea     r14, [rdi+r15]
0x18006d438  mov     [rbx], rbx
0x18006d43b  mov     [rbx+10h], rbx
0x18006d43f  mov     qword ptr [rdi+r15+30h], 0
0x18006d448  mov     rcx, [r14+38h]
0x18006d44c  mov     rcx, [rcx]
0x18006d44f  mov     [rsp+58h+arg_0], rcx
0x18006d454  cmp     byte ptr [rcx+19h], 0
0x18006d458  jnz     short loc_18006D475
0x18006d45a  mov     rcx, [rcx+30h]
0x18006d45e  call    cs:__imp_FwFree
0x18006d464  lea     rcx, [rsp+58h+arg_0]
0x18006d469  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>,std::_Iterator_base0>::operator++(void)
0x18006d46e  mov     rcx, [rsp+58h+arg_0]
0x18006d473  jmp     short loc_18006D454
0x18006d475  mov     rbx, [rdi+r15+38h]
0x18006d47a  lea     rdx, [r14+38h]
0x18006d47e  lea     rcx, [r14+38h]
0x18006d482  mov     r8, [rbx+8]
0x18006d486  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *>> &,std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *> *)
0x18006d48b  mov     [rbx+8], rbx
0x18006d48f  inc     rsi
0x18006d492  mov     [rbx], rbx
0x18006d495  mov     [rbx+10h], rbx
0x18006d499  mov     qword ptr [rdi+r15+40h], 0
0x18006d4a2  add     rdi, 20h ; ' '
0x18006d4a6  cmp     rsi, 0Dh
0x18006d4aa  jnz     loc_18006D3EA
0x18006d4b0  mov     rbx, cs:qword_18012C960
0x18006d4b7  mov     rdi, cs:qword_18012C968
0x18006d4be  cmp     rbx, rdi
0x18006d4c1  jz      short loc_18006D4F4
0x18006d4c3  mov     rcx, [rbx]
0x18006d4c6  mov     edx, 221h
0x18006d4cb  call    cs:__imp_FwFreeHyperVPortsBySchemaVersion
0x18006d4d1  add     rbx, 8
0x18006d4d5  cmp     rbx, rdi
0x18006d4d8  jnz     short loc_18006D4C3
0x18006d4da  mov     rdi, cs:qword_18012C968
0x18006d4e1  mov     rbx, cs:qword_18012C960
0x18006d4e8  cmp     rbx, rdi
0x18006d4eb  jz      short loc_18006D4F4
0x18006d4ed  mov     cs:qword_18012C968, rbx
0x18006d4f4  mov     rcx, cs:qword_18012CB18
0x18006d4fb  mov     rcx, [rcx]
0x18006d4fe  mov     [rsp+58h+arg_0], rcx
0x18006d503  cmp     byte ptr [rcx+19h], 0
0x18006d507  jnz     short loc_18006D523
0x18006d509  mov     rcx, [rcx+30h]
0x18006d50d  call    FwHyperVMgrFreeVmCreatorContainer
0x18006d512  lea     rcx, [rsp+58h+arg_0]
0x18006d517  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>,std::_Iterator_base0>::operator++(void)
0x18006d51c  mov     rcx, [rsp+58h+arg_0]
0x18006d521  jmp     short loc_18006D503
0x18006d523  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d52a  cmp     rcx, r12
0x18006d52d  jz      short loc_18006D54A
0x18006d52f  test    byte ptr [rcx+1Ch], 8
0x18006d533  jz      short loc_18006D54A
0x18006d535  mov     rcx, [rcx+10h]
0x18006d539  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x18006d540  mov     edx, 17h
0x18006d545  call    WPP_SF_
0x18006d54a  add     rsp, 28h
0x18006d54e  pop     r15
0x18006d550  pop     r14
0x18006d552  pop     r12
0x18006d554  pop     rdi
0x18006d555  pop     rsi
0x18006d556  pop     rbx
0x18006d557  retn
```
