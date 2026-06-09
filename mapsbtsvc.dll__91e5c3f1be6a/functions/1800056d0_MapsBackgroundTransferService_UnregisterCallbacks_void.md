# MapsBackgroundTransferService_UnregisterCallbacks(void)

- ea: `0x1800056d0`
- end: `0x180005818`
- name: `?MapsBackgroundTransferService_UnregisterCallbacks@@YAJXZ`
- size: `328`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003b44`
- `0x180004094`
- `0x180004134`
- `0x180004168`
- `0x180004408`
- `0x180004454`
- `0x180004730`
- `0x1800056d0`
- `0x180005b9c`
- `0x180005bf0`
- `0x180005e8c`
- `0x18000cf70`
- `0x180015010`

## pseudocode

```c
__int64 MapsBackgroundTransferService_UnregisterCallbacks(void)
{
  unsigned __int64 v0; // rax
  _QWORD *v1; // rdi
  _QWORD *i; // rbx
  __int64 v3; // rsi
  std::_Ref_count_base *v4; // rsi
  __int64 v6; // [rsp+20h] [rbp-58h] BYREF
  std::_Ref_count_base *v7; // [rsp+28h] [rbp-50h]
  __int64 v8; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v9[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v10; // [rsp+A0h] [rbp+28h] BYREF

  std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>((__int64)&v8);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)&v6,
    (struct _RTL_CRITICAL_SECTION *)qword_18001D860);
  dword_18001D648 = 0;
  qword_18001D640 = 0;
  qword_18001D638 = 0;
  qword_18001D630 = 0;
  v10 = &v8;
  LODWORD(v8) = dword_18001D820;
  std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(
    (__int64)v9,
    *(_QWORD **)qword_18001D828,
    (_QWORD *)qword_18001D828);
  v0 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(
         (__int64)&v8,
         v9[1]);
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(
    &v8,
    v0);
  v10 = 0;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(&v10);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)&v6);
  v1 = (_QWORD *)v9[0];
  for ( i = *(_QWORD **)v9[0]; i != v1; i = (_QWORD *)*i )
  {
    std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(&v6, i + 3);
    v3 = v6;
    if ( (unsigned int)MapsBackgroundTransferJob::GetJobState(v6) != 4 )
    {
      *(_DWORD *)(v3 + 736) = 0;
      *(_QWORD *)(v3 + 744) = 0;
      *(_QWORD *)(v3 + 752) = 0;
      *(_QWORD *)(v3 + 760) = 0;
    }
    v4 = v7;
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v4)(v4);
        std::_Ref_count_base::_Decwref(v4);
      }
    }
  }
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>((__int64)&v8);
  return 0;
}

```

## disassembly

```asm
0x1800056d0  push    rbp
0x1800056d2  push    rbx
0x1800056d3  push    rsi
0x1800056d4  push    rdi
0x1800056d5  mov     rbp, rsp
0x1800056d8  sub     rsp, 78h
0x1800056dc  lea     rcx, [rbp+var_48]
0x1800056e0  call    ??0?$unordered_map@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@U?$hash@PEAVMapsBackgroundTransferJob@@@3@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@@std@@QEAA@XZ; std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>(void)
0x1800056e5  nop
0x1800056e6  lea     rdx, qword_18001D860
0x1800056ed  lea     rcx, [rbp+var_58]
0x1800056f1  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800056f6  nop
0x1800056f7  mov     cs:dword_18001D648, 0
0x180005701  mov     cs:qword_18001D640, 0
0x18000570c  mov     cs:qword_18001D638, 0
0x180005717  mov     cs:qword_18001D630, 0
0x180005722  lea     rax, [rbp+var_48]
0x180005726  mov     [rbp+arg_0], rax
0x18000572a  mov     eax, cs:dword_18001D820
0x180005730  mov     dword ptr [rbp+var_48], eax
0x180005733  mov     rdx, cs:qword_18001D828
0x18000573a  mov     r8, rdx
0x18000573d  mov     rdx, [rdx]
0x180005740  lea     rcx, [rbp+var_40]
0x180005744  call    ??$_Assign_cast@AEAU?$pair@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>)
0x180005749  mov     rdx, [rbp+var_38]
0x18000574d  lea     rcx, [rbp+var_48]
0x180005751  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180005756  mov     rdx, rax
0x180005759  lea     rcx, [rbp+var_48]
0x18000575d  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(unsigned __int64)
0x180005762  mov     [rbp+arg_0], 0
0x18000576a  lea     rcx, [rbp+arg_0]
0x18000576e  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180005773  nop
0x180005774  lea     rcx, [rbp+var_58]
0x180005778  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000577d  mov     rdi, [rbp+var_40]
0x180005781  mov     rbx, [rdi]
0x180005784  cmp     rbx, rdi
0x180005787  jz      short loc_180005804
0x180005789  lea     rdx, [rbx+18h]
0x18000578d  lea     rcx, [rbp+var_58]
0x180005791  call    ??0?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x180005796  nop
0x180005797  mov     rsi, [rbp+var_58]
0x18000579b  mov     rcx, rsi
0x18000579e  call    ?GetJobState@MapsBackgroundTransferJob@@UEAA?AW4MAPSBTSVC_JOB_STATE@@XZ; MapsBackgroundTransferJob::GetJobState(void)
0x1800057a3  cmp     eax, 4
0x1800057a6  jz      short loc_1800057D3
0x1800057a8  mov     dword ptr [rsi+2E0h], 0
0x1800057b2  mov     qword ptr [rsi+2E8h], 0
0x1800057bd  mov     qword ptr [rsi+2F0h], 0
0x1800057c8  mov     qword ptr [rsi+2F8h], 0
0x1800057d3  mov     rsi, [rbp+var_50]
0x1800057d7  test    rsi, rsi
0x1800057da  jz      short loc_1800057FF
0x1800057dc  or      eax, 0FFFFFFFFh
0x1800057df  lock xadd [rsi+8], eax
0x1800057e4  cmp     eax, 1
0x1800057e7  jnz     short loc_1800057FF
0x1800057e9  mov     rax, [rsi]
0x1800057ec  mov     rcx, rsi
0x1800057ef  mov     rax, [rax]
0x1800057f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f7  mov     rcx, rsi; this
0x1800057fa  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800057ff  mov     rbx, [rbx]
0x180005802  jmp     short loc_180005784
0x180005804  lea     rcx, [rbp+var_48]
0x180005808  call    ??1?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>(void)
0x18000580d  xor     eax, eax
0x18000580f  add     rsp, 78h
0x180005813  pop     rdi
0x180005814  pop     rsi
0x180005815  pop     rbx
0x180005816  pop     rbp
0x180005817  retn
```
