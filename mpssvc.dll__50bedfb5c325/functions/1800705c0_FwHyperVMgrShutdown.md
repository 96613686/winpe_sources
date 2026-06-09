# FwHyperVMgrShutdown

- ea: `0x1800705c0`
- end: `0x180070859`
- name: `FwHyperVMgrShutdown`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180082850`

## callees

- `0x180010d48`
- `0x1800192e0`
- `0x180046f50`
- `0x180061154`
- `0x1800691cc`
- `0x18006a8a8`
- `0x18006ba5c`
- `0x18006e73c`
- `0x1800705c0`
- `0x180070860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180070603`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180070603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070620`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070620`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070671`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070671`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007069d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007069d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800706b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800706b4`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x180070646`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x180070646`
- `fwbase!FwFree` at `0x180070752`
- `fwbase!FwFree` at `0x180070752`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x1800707c5`
- `FWPolicyIOMgr!FwFreeHyperVPortsBySchemaVersion` at `0x1800707c5`

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
  AcquireSRWLockExclusive(&stru_180132B28);
  gFwHyperVMgr = 0;
  ReleaseSRWLockExclusive(&stru_180132B28);
  if ( !*(&gFwHyperVMgr + 1) )
    FwCancelLock();
  if ( (_QWORD)xmmword_180133290 )
  {
    PowerUnregisterSuspendResumeNotification();
    *(_QWORD *)&xmmword_180133290 = 0;
  }
  if ( qword_180133288 )
  {
    SetThreadpoolTimer(qword_180133288, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &qword_180133288,
      0);
  }
  v0 = (struct _TP_WORK *)(*off_18012C498)[1];
  if ( v0 )
  {
    WaitForThreadpoolWorkCallbacks(v0, 0);
    CloseThreadpoolWork((PTP_WORK)(*off_18012C498)[1]);
    (*off_18012C498)[1] = 0;
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
  v8 = qword_180132B30;
  v9 = qword_180132B38;
  if ( qword_180132B30 != (void *)qword_180132B38 )
  {
    do
      result = FwFreeHyperVPortsBySchemaVersion(*v8++, 545);
    while ( v8 != (_QWORD *)v9 );
    if ( qword_180132B30 != (void *)qword_180132B38 )
      qword_180132B38 = (__int64)qword_180132B30;
  }
  v10 = *(_QWORD *)qword_180132CE8;
  v11 = *(_QWORD *)qword_180132CE8;
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
0x1800705c0  push    rbx
0x1800705c2  push    rsi
0x1800705c3  push    rdi
0x1800705c4  push    r12
0x1800705c6  push    r14
0x1800705c8  push    r15
0x1800705ca  sub     rsp, 28h
0x1800705ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800705d5  lea     r12, WPP_GLOBAL_Control
0x1800705dc  cmp     rcx, r12
0x1800705df  jz      short loc_1800705FC
0x1800705e1  test    byte ptr [rcx+1Ch], 8
0x1800705e5  jz      short loc_1800705FC
0x1800705e7  mov     rcx, [rcx+10h]
0x1800705eb  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x1800705f2  mov     edx, 16h
0x1800705f7  call    WPP_SF_
0x1800705fc  lea     rcx, stru_180132B28; SRWLock
0x180070603  call    cs:__imp_AcquireSRWLockExclusive
0x18007060a  nop     dword ptr [rax+rax+00h]
0x18007060f  lea     rcx, stru_180132B28; SRWLock
0x180070616  mov     dword ptr cs:gFwHyperVMgr, 0
0x180070620  call    cs:__imp_ReleaseSRWLockExclusive
0x180070627  nop     dword ptr [rax+rax+00h]
0x18007062c  cmp     dword ptr cs:gFwHyperVMgr+4, 0
0x180070633  jnz     short loc_18007063A
0x180070635  call    FwCancelLock
0x18007063a  mov     rcx, qword ptr cs:xmmword_180133290
0x180070641  test    rcx, rcx
0x180070644  jz      short loc_18007065D
0x180070646  call    cs:__imp_PowerUnregisterSuspendResumeNotification
0x18007064d  nop     dword ptr [rax+rax+00h]
0x180070652  mov     qword ptr cs:xmmword_180133290, 0
0x18007065d  mov     rcx, cs:qword_180133288; pti
0x180070664  test    rcx, rcx
0x180070667  jz      short loc_18007068B
0x180070669  xor     r9d, r9d; msWindowLength
0x18007066c  xor     r8d, r8d; msPeriod
0x18007066f  xor     edx, edx; pftDueTime
0x180070671  call    cs:__imp_SetThreadpoolTimer
0x180070678  nop     dword ptr [rax+rax+00h]
0x18007067d  xor     edx, edx
0x18007067f  lea     rcx, qword_180133288
0x180070686  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18007068b  mov     rax, cs:off_18012C498
0x180070692  mov     rcx, [rax+8]; pwk
0x180070696  test    rcx, rcx
0x180070699  jz      short loc_1800706CF
0x18007069b  xor     edx, edx; fCancelPendingCallbacks
0x18007069d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800706a4  nop     dword ptr [rax+rax+00h]
0x1800706a9  mov     rcx, cs:off_18012C498
0x1800706b0  mov     rcx, [rcx+8]; pwk
0x1800706b4  call    cs:__imp_CloseThreadpoolWork
0x1800706bb  nop     dword ptr [rax+rax+00h]
0x1800706c0  mov     rax, cs:off_18012C498
0x1800706c7  mov     qword ptr [rax+8], 0
0x1800706cf  mov     esi, 1
0x1800706d4  lea     r15, gFwHyperVMgr
0x1800706db  lea     edi, [rsi+1Fh]
0x1800706de  lea     r14, [rdi+r15]
0x1800706e2  mov     rcx, [r14+28h]
0x1800706e6  mov     rcx, [rcx]
0x1800706e9  mov     [rsp+58h+arg_0], rcx
0x1800706ee  cmp     byte ptr [rcx+19h], 0
0x1800706f2  jnz     short loc_18007070E
0x1800706f4  mov     rcx, [rcx+40h]
0x1800706f8  call    FwFreeHyperVRuleContainer
0x1800706fd  lea     rcx, [rsp+58h+arg_0]
0x180070702  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>>>,std::_Iterator_base0>::operator++(void)
0x180070707  mov     rcx, [rsp+58h+arg_0]
0x18007070c  jmp     short loc_1800706EE
0x18007070e  mov     rbx, [rdi+r15+28h]
0x180070713  lea     rdx, [r14+28h]
0x180070717  lea     rcx, [r14+28h]
0x18007071b  mov     r8, [rbx+8]
0x18007071f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_tag_FW_HYPERV_RULE_CONTAINER@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,_tag_FW_HYPERV_RULE_CONTAINER *>,void *> *)
0x180070724  mov     [rbx+8], rbx
0x180070728  lea     r14, [rdi+r15]
0x18007072c  mov     [rbx], rbx
0x18007072f  mov     [rbx+10h], rbx
0x180070733  mov     qword ptr [rdi+r15+30h], 0
0x18007073c  mov     rcx, [r14+38h]
0x180070740  mov     rcx, [rcx]
0x180070743  mov     [rsp+58h+arg_0], rcx
0x180070748  cmp     byte ptr [rcx+19h], 0
0x18007074c  jnz     short loc_18007076F
0x18007074e  mov     rcx, [rcx+30h]
0x180070752  call    cs:__imp_FwFree
0x180070759  nop     dword ptr [rax+rax+00h]
0x18007075e  lea     rcx, [rsp+58h+arg_0]
0x180070763  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>,std::_Iterator_base0>::operator++(void)
0x180070768  mov     rcx, [rsp+58h+arg_0]
0x18007076d  jmp     short loc_180070748
0x18007076f  mov     rbx, [rdi+r15+38h]
0x180070774  lea     rdx, [r14+38h]
0x180070778  lea     rcx, [r14+38h]
0x18007077c  mov     r8, [rbx+8]
0x180070780  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *>> &,std::_Tree_node<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>,void *> *)
0x180070785  mov     [rbx+8], rbx
0x180070789  inc     rsi
0x18007078c  mov     [rbx], rbx
0x18007078f  mov     [rbx+10h], rbx
0x180070793  mov     qword ptr [rdi+r15+40h], 0
0x18007079c  add     rdi, 20h ; ' '
0x1800707a0  cmp     rsi, 0Dh
0x1800707a4  jnz     loc_1800706DE
0x1800707aa  mov     rbx, cs:qword_180132B30
0x1800707b1  mov     rdi, cs:qword_180132B38
0x1800707b8  cmp     rbx, rdi
0x1800707bb  jz      short loc_1800707F4
0x1800707bd  mov     rcx, [rbx]
0x1800707c0  mov     edx, 221h
0x1800707c5  call    cs:__imp_FwFreeHyperVPortsBySchemaVersion
0x1800707cc  nop     dword ptr [rax+rax+00h]
0x1800707d1  add     rbx, 8
0x1800707d5  cmp     rbx, rdi
0x1800707d8  jnz     short loc_1800707BD
0x1800707da  mov     rdi, cs:qword_180132B38
0x1800707e1  mov     rbx, cs:qword_180132B30
0x1800707e8  cmp     rbx, rdi
0x1800707eb  jz      short loc_1800707F4
0x1800707ed  mov     cs:qword_180132B38, rbx
0x1800707f4  mov     rcx, cs:qword_180132CE8
0x1800707fb  mov     rcx, [rcx]
0x1800707fe  mov     [rsp+58h+arg_0], rcx
0x180070803  cmp     byte ptr [rcx+19h], 0
0x180070807  jnz     short loc_180070823
0x180070809  mov     rcx, [rcx+30h]
0x18007080d  call    FwHyperVMgrFreeVmCreatorContainer
0x180070812  lea     rcx, [rsp+58h+arg_0]
0x180070817  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAU_tag_FW_HYPERV_VM_CREATOR_CONTAINER@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_tag_FW_HYPERV_VM_CREATOR_CONTAINER *>>>,std::_Iterator_base0>::operator++(void)
0x18007081c  mov     rcx, [rsp+58h+arg_0]
0x180070821  jmp     short loc_180070803
0x180070823  mov     rcx, cs:WPP_GLOBAL_Control
0x18007082a  cmp     rcx, r12
0x18007082d  jz      short loc_18007084A
0x18007082f  test    byte ptr [rcx+1Ch], 8
0x180070833  jz      short loc_18007084A
0x180070835  mov     rcx, [rcx+10h]
0x180070839  lea     r8, WPP_a0bd6c6c6fc93deac0743cf3ecb5d7bb_Traceguids
0x180070840  mov     edx, 17h
0x180070845  call    WPP_SF_
0x18007084a  add     rsp, 28h
0x18007084e  pop     r15
0x180070850  pop     r14
0x180070852  pop     r12
0x180070854  pop     rdi
0x180070855  pop     rsi
0x180070856  pop     rbx
0x180070857  retn
```
