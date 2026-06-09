# MapsBackgroundTransferService_FreeJob(void *)

- ea: `0x180005000`
- end: `0x180005067`
- name: `?MapsBackgroundTransferService_FreeJob@@YAXPEAX@Z`
- size: `103`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800039a4`
- `0x180003cac`
- `0x180004094`
- `0x180004408`
- `0x180004664`
- `0x180005000`

## pseudocode

```c
void __fastcall MapsBackgroundTransferService_FreeJob(void *a1)
{
  __int64 v2; // rcx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  void *v5; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v3,
    (struct _RTL_CRITICAL_SECTION *)qword_18001D860);
  v5 = a1;
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Erase<MapsBackgroundTransferJob *>(
    v2,
    (unsigned __int8 *)&v5);
  if ( !qword_18001D830 )
    std::unique_ptr<TimerQueue>::operator=<std::default_delete<TimerQueue>,0>(&v4, &qword_18001D8A0);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v3);
  std::unique_ptr<TimerQueue>::~unique_ptr<TimerQueue>(&v4);
}

```

## disassembly

```asm
0x180005000  push    rbx
0x180005002  sub     rsp, 30h
0x180005006  mov     rbx, rcx
0x180005009  mov     [rsp+38h+arg_0], 0
0x180005012  lea     rcx, [rsp+38h+var_18]
0x180005017  lea     rdx, qword_18001D860
0x18000501e  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180005023  lea     rdx, [rsp+38h+arg_8]
0x180005028  mov     [rsp+38h+arg_8], rbx
0x18000502d  call    ??$_Erase@PEAVMapsBackgroundTransferJob@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@AEAA_KAEBQEAVMapsBackgroundTransferJob@@@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Erase<MapsBackgroundTransferJob *>(MapsBackgroundTransferJob * const &)
0x180005032  cmp     cs:qword_18001D830, 0
0x18000503a  jnz     short loc_18000504D
0x18000503c  lea     rdx, qword_18001D8A0
0x180005043  lea     rcx, [rsp+38h+arg_0]
0x180005048  call    ??$?4U?$default_delete@VTimerQueue@@@std@@$0A@@?$unique_ptr@VTimerQueue@@U?$default_delete@VTimerQueue@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TimerQueue>::operator=<std::default_delete<TimerQueue>,0>(std::unique_ptr<TimerQueue> &&)
0x18000504d  lea     rcx, [rsp+38h+var_18]
0x180005052  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180005057  lea     rcx, [rsp+38h+arg_0]
0x18000505c  call    ??1?$unique_ptr@VTimerQueue@@U?$default_delete@VTimerQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<TimerQueue>::~unique_ptr<TimerQueue>(void)
0x180005061  add     rsp, 30h
0x180005065  pop     rbx
0x180005066  retn
```
