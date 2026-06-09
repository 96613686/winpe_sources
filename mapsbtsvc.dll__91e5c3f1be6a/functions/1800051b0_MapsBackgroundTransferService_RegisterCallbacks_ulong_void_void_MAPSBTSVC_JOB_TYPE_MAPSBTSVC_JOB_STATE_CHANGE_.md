# MapsBackgroundTransferService_RegisterCallbacks(ulong,void (*)(void *,MAPSBTSVC_JOB_TYPE,MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON),void (*)(void *,MAPSBTSVC_TRANSFER_STATE,unsigned __int64),void *)

- ea: `0x1800051b0`
- end: `0x18000534e`
- name: `?MapsBackgroundTransferService_RegisterCallbacks@@YAJKP6AXPEAXW4MAPSBTSVC_JOB_TYPE@@W4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@ZP6AX0W4MAPSBTSVC_TRANSFER_STATE@@_K@Z0@Z`
- size: `414`
- prototype: `__int64 __fastcall(int, void (__high *)(void *, enum MAPSBTSVC_JOB_TYPE, enum MAPSBTSVC_JOB_STATE_CHANGE, enum MAPSBTSVC_JOB_WAITING_REASON), void (__high *)(void *, enum MAPSBTSVC_TRANSFER_STATE, unsigned __int64), __int64)`
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
- `0x1800051b0`
- `0x180005b9c`
- `0x180005bf0`
- `0x180005e8c`
- `0x18000cf70`
- `0x180015010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800051fc`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800051fc`

## string_xrefs

- `0x1800051f5`: `MapsBackgroundTransferService_RegisterCallbacks`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferService_RegisterCallbacks(
        int a1,
        void (__high *a2)(void *, enum MAPSBTSVC_JOB_TYPE, enum MAPSBTSVC_JOB_STATE_CHANGE, enum MAPSBTSVC_JOB_WAITING_REASON),
        void (__high *a3)(void *, enum MAPSBTSVC_TRANSFER_STATE, unsigned __int64),
        __int64 a4)
{
  int v8; // r8d
  int v9; // ecx
  unsigned int v10; // r14d
  unsigned __int64 v11; // rax
  _QWORD *v12; // rdi
  _QWORD *i; // rbx
  __int64 v14; // rsi
  std::_Ref_count_base *v15; // rsi
  __int64 *v17; // [rsp+20h] [rbp-60h] BYREF
  std::_Ref_count_base *v18; // [rsp+28h] [rbp-58h]
  _BYTE v19[16]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v21[7]; // [rsp+48h] [rbp-38h] BYREF

  std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>((__int64)&v20);
  if ( !a1 )
  {
    v8 = 273;
    v9 = -2147024809;
LABEL_3:
    v10 = ZTraceReportOriginationNoThis(v9, "MapsBackgroundTransferService_RegisterCallbacks", v8);
    goto LABEL_15;
  }
  if ( !a2 )
  {
    v8 = 274;
    v9 = -2147467261;
    goto LABEL_3;
  }
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v19,
    (struct _RTL_CRITICAL_SECTION *)qword_18001D860);
  dword_18001D648 = a1;
  qword_18001D640 = (__int64)a2;
  qword_18001D638 = (__int64)a3;
  qword_18001D630 = a4;
  v17 = &v20;
  LODWORD(v20) = dword_18001D820;
  std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(
    (__int64)v21,
    *(_QWORD **)qword_18001D828,
    (_QWORD *)qword_18001D828);
  v11 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(
          (__int64)&v20,
          v21[1]);
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(
    &v20,
    v11);
  v17 = 0;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(&v17);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v19);
  v12 = (_QWORD *)v21[0];
  for ( i = *(_QWORD **)v21[0]; i != v12; i = (_QWORD *)*i )
  {
    std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(&v17, i + 3);
    v14 = (__int64)v17;
    if ( (unsigned int)MapsBackgroundTransferJob::GetJobState((__int64)v17) != 4 )
    {
      *(_DWORD *)(v14 + 736) = a1;
      *(_QWORD *)(v14 + 744) = a2;
      *(_QWORD *)(v14 + 752) = a3;
      *(_QWORD *)(v14 + 760) = a4;
    }
    v15 = v18;
    if ( v18 && _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v15)(v15);
      std::_Ref_count_base::_Decwref(v15);
    }
  }
  v10 = 0;
LABEL_15:
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>((__int64)&v20);
  return v10;
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp-38h+arg_8], rbx
0x1800051b5  mov     [rsp-38h+arg_10], r8
0x1800051ba  push    rbp
0x1800051bb  push    rsi
0x1800051bc  push    rdi
0x1800051bd  push    r12
0x1800051bf  push    r13
0x1800051c1  push    r14
0x1800051c3  push    r15
0x1800051c5  mov     rbp, rsp
0x1800051c8  sub     rsp, 80h
0x1800051cf  mov     r13, r9
0x1800051d2  mov     rbx, r8
0x1800051d5  mov     r15, rdx
0x1800051d8  mov     r12d, ecx
0x1800051db  lea     rcx, [rbp+var_40]
0x1800051df  call    ??0?$unordered_map@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@U?$hash@PEAVMapsBackgroundTransferJob@@@3@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@@std@@QEAA@XZ; std::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>::unordered_map<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>>(void)
0x1800051e4  nop
0x1800051e5  test    r12d, r12d
0x1800051e8  jnz     short loc_18000520A
0x1800051ea  mov     r8d, 111h
0x1800051f0  mov     ecx, 80070057h
0x1800051f5  lea     rdx, aMapsbackground_39; "MapsBackgroundTransferService_RegisterC"...
0x1800051fc  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180005202  mov     r14d, eax
0x180005205  jmp     loc_180005327
0x18000520a  test    r15, r15
0x18000520d  jnz     short loc_18000521C
0x18000520f  mov     r8d, 112h
0x180005215  mov     ecx, 80004003h
0x18000521a  jmp     short loc_1800051F5
0x18000521c  xor     r14d, r14d
0x18000521f  mov     [rbp+arg_0], r14d
0x180005223  lea     rdx, qword_18001D860
0x18000522a  lea     rcx, [rbp+var_50]
0x18000522e  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180005233  nop
0x180005234  mov     cs:dword_18001D648, r12d
0x18000523b  mov     cs:qword_18001D640, r15
0x180005242  mov     cs:qword_18001D638, rbx
0x180005249  mov     cs:qword_18001D630, r13
0x180005250  lea     rax, [rbp+var_40]
0x180005254  mov     [rbp+var_60], rax
0x180005258  mov     eax, cs:dword_18001D820
0x18000525e  mov     dword ptr [rbp+var_40], eax
0x180005261  mov     rdx, cs:qword_18001D828
0x180005268  mov     r8, rdx
0x18000526b  mov     rdx, [rdx]
0x18000526e  lea     rcx, [rbp+var_38]
0x180005272  call    ??$_Assign_cast@AEAU?$pair@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>::_Assign_cast<std::pair<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>,std::_Iterator_base0>)
0x180005277  mov     rdx, [rbp+var_30]
0x18000527b  lea     rcx, [rbp+var_40]
0x18000527f  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180005284  mov     rdx, rax
0x180005287  lea     rcx, [rbp+var_40]
0x18000528b  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(unsigned __int64)
0x180005290  mov     [rbp+var_60], r14
0x180005294  lea     rcx, [rbp+var_60]
0x180005298  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000529d  nop
0x18000529e  lea     rcx, [rbp+var_50]
0x1800052a2  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x1800052a7  mov     rdi, [rbp+var_38]
0x1800052ab  mov     rbx, [rdi]
0x1800052ae  mov     r14, [rbp+arg_10]
0x1800052b2  cmp     rbx, rdi
0x1800052b5  jz      short loc_180005323
0x1800052b7  lea     rdx, [rbx+18h]
0x1800052bb  lea     rcx, [rbp+var_60]
0x1800052bf  call    ??0?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x1800052c4  nop
0x1800052c5  mov     rsi, [rbp+var_60]
0x1800052c9  mov     rcx, rsi
0x1800052cc  call    ?GetJobState@MapsBackgroundTransferJob@@UEAA?AW4MAPSBTSVC_JOB_STATE@@XZ; MapsBackgroundTransferJob::GetJobState(void)
0x1800052d1  cmp     eax, 4
0x1800052d4  jz      short loc_1800052F2
0x1800052d6  mov     [rsi+2E0h], r12d
0x1800052dd  mov     [rsi+2E8h], r15
0x1800052e4  mov     [rsi+2F0h], r14
0x1800052eb  mov     [rsi+2F8h], r13
0x1800052f2  mov     rsi, [rbp+var_58]
0x1800052f6  test    rsi, rsi
0x1800052f9  jz      short loc_18000531E
0x1800052fb  or      eax, 0FFFFFFFFh
0x1800052fe  lock xadd [rsi+8], eax
0x180005303  cmp     eax, 1
0x180005306  jnz     short loc_18000531E
0x180005308  mov     rax, [rsi]
0x18000530b  mov     rcx, rsi
0x18000530e  mov     rax, [rax]
0x180005311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005316  mov     rcx, rsi; this
0x180005319  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000531e  mov     rbx, [rbx]
0x180005321  jmp     short loc_1800052B2
0x180005323  mov     r14d, [rbp+arg_0]
0x180005327  lea     rcx, [rbp+var_40]
0x18000532b  call    ??1?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::~_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>(void)
0x180005330  mov     eax, r14d
0x180005333  mov     rbx, [rsp+80h+arg_8]
0x18000533b  add     rsp, 80h
0x180005342  pop     r15
0x180005344  pop     r14
0x180005346  pop     r13
0x180005348  pop     r12
0x18000534a  pop     rdi
0x18000534b  pop     rsi
0x18000534c  pop     rbp
0x18000534d  retn
```
