# MapsBackgroundTransferService_GetIsAnyJobWaiting(bool *)

- ea: `0x180005070`
- end: `0x18000519d`
- name: `?MapsBackgroundTransferService_GetIsAnyJobWaiting@@YAJPEA_N@Z`
- size: `301`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003b44`
- `0x180004094`
- `0x180004134`
- `0x180004168`
- `0x180004408`
- `0x180004454`
- `0x180004730`
- `0x180005070`
- `0x180005b9c`
- `0x180005bf0`
- `0x180005e8c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferService_GetIsAnyJobWaiting(bool *a1)
{
  bool v2; // r14
  unsigned __int64 v3; // rax
  _QWORD *v4; // rdi
  _QWORD *i; // rbx
  std::_Ref_count_base *v6; // rsi
  std::_Ref_count_base *v7; // rbx
  __int64 v9; // [rsp+20h] [rbp-58h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-50h]
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v12[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v13; // [rsp+B0h] [rbp+38h] BYREF

  std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>((__int64)&v11);
  v2 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)&v9,
    (struct _RTL_CRITICAL_SECTION *)qword_18001D860);
  v13 = &v11;
  LODWORD(v11) = dword_18001D820;
  std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(
    (__int64)v12,
    *(_QWORD **)qword_18001D828,
    (_QWORD *)qword_18001D828);
  v3 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(
         (__int64)&v11,
         v12[1]);
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(
    &v11,
    v3);
  v13 = 0;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(&v13);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)&v9);
  v4 = (_QWORD *)v12[0];
  for ( i = *(_QWORD **)v12[0]; i != v4; i = (_QWORD *)*i )
  {
    std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(&v9, i + 3);
    if ( *(_DWORD *)(v9 + 776) )
    {
      v2 = 1;
      v7 = v10;
      if ( v10 && _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v7)(v7);
        std::_Ref_count_base::_Decwref(v7);
      }
      break;
    }
    v6 = v10;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v6)(v6);
        std::_Ref_count_base::_Decwref(v6);
      }
    }
  }
  *a1 = v2;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>((__int64)&v11);
  return 0;
}

```

## disassembly

```asm
0x180005070  push    rbp
0x180005072  push    rbx
0x180005073  push    rsi
0x180005074  push    rdi
0x180005075  push    r14
0x180005077  push    r15
0x180005079  mov     rbp, rsp
0x18000507c  sub     rsp, 78h
0x180005080  mov     r15, rcx
0x180005083  lea     rcx, [rbp+var_48]
0x180005087  call    ??0?$unordered_map@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@U?$hash@PEAVMapsBackgroundTransferJob@@@3@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@@std@@QEAA@XZ; std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>(void)
0x18000508c  nop
0x18000508d  xor     r14b, r14b
0x180005090  lea     rdx, qword_18001D860
0x180005097  lea     rcx, [rbp+var_58]
0x18000509b  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800050a0  nop
0x1800050a1  lea     rax, [rbp+var_48]
0x1800050a5  mov     [rbp+arg_0], rax
0x1800050a9  mov     eax, cs:dword_18001D820
0x1800050af  mov     dword ptr [rbp+var_48], eax
0x1800050b2  mov     rdx, cs:qword_18001D828
0x1800050b9  mov     r8, rdx
0x1800050bc  mov     rdx, [rdx]
0x1800050bf  lea     rcx, [rbp+var_40]
0x1800050c3  call    ??$_Assign_cast@AEAU?$pair@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>)
0x1800050c8  mov     rdx, [rbp+var_38]
0x1800050cc  lea     rcx, [rbp+var_48]
0x1800050d0  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1800050d5  mov     rdx, rax
0x1800050d8  lea     rcx, [rbp+var_48]
0x1800050dc  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(unsigned __int64)
0x1800050e1  mov     [rbp+arg_0], 0
0x1800050e9  lea     rcx, [rbp+arg_0]
0x1800050ed  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800050f2  nop
0x1800050f3  lea     rcx, [rbp+var_58]
0x1800050f7  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x1800050fc  mov     rdi, [rbp+var_40]
0x180005100  mov     rbx, [rdi]
0x180005103  cmp     rbx, rdi
0x180005106  jz      short loc_180005182
0x180005108  lea     rdx, [rbx+18h]
0x18000510c  lea     rcx, [rbp+var_58]
0x180005110  call    ??0?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x180005115  mov     rcx, [rbp+var_58]
0x180005119  cmp     dword ptr [rcx+308h], 0
0x180005120  jnz     short loc_180005153
0x180005122  mov     rsi, [rbp+var_50]
0x180005126  test    rsi, rsi
0x180005129  jz      short loc_18000514E
0x18000512b  or      eax, 0FFFFFFFFh
0x18000512e  lock xadd [rsi+8], eax
0x180005133  cmp     eax, 1
0x180005136  jnz     short loc_18000514E
0x180005138  mov     rax, [rsi]
0x18000513b  mov     rcx, rsi
0x18000513e  mov     rax, [rax]
0x180005141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005146  mov     rcx, rsi; this
0x180005149  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000514e  mov     rbx, [rbx]
0x180005151  jmp     short loc_180005103
0x180005153  mov     r14b, 1
0x180005156  mov     rbx, [rbp+var_50]
0x18000515a  test    rbx, rbx
0x18000515d  jz      short loc_180005182
0x18000515f  or      eax, 0FFFFFFFFh
0x180005162  lock xadd [rbx+8], eax
0x180005167  cmp     eax, 1
0x18000516a  jnz     short loc_180005182
0x18000516c  mov     rax, [rbx]
0x18000516f  mov     rcx, rbx
0x180005172  mov     rax, [rax]
0x180005175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000517a  mov     rcx, rbx; this
0x18000517d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180005182  mov     [r15], r14b
0x180005185  lea     rcx, [rbp+var_48]
0x180005189  call    ??1?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>(void)
0x18000518e  xor     eax, eax
0x180005190  add     rsp, 78h
0x180005194  pop     r15
0x180005196  pop     r14
0x180005198  pop     rdi
0x180005199  pop     rsi
0x18000519a  pop     rbx
0x18000519b  pop     rbp
0x18000519c  retn
```
