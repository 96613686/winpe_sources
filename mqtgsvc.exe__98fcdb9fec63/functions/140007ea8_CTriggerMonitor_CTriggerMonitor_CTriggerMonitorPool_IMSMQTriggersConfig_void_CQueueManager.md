# CTriggerMonitor::CTriggerMonitor(CTriggerMonitorPool *,IMSMQTriggersConfig *,void * *,CQueueManager *)

- ea: `0x140007ea8`
- end: `0x140007f43`
- name: `??0CTriggerMonitor@@QEAA@PEAVCTriggerMonitorPool@@PEAUIMSMQTriggersConfig@@PEAPEAXPEAVCQueueManager@@@Z`
- size: `155`
- prototype: `CTriggerMonitor *__fastcall(CTriggerMonitor *this, struct CTriggerMonitorPool *, struct IMSMQTriggersConfig *, void **, struct CQueueManager *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b43c`

## callees

- `0x14000393c`
- `0x1400046bc`
- `0x1400076a8`

## pseudocode

```c
CTriggerMonitor *__fastcall CTriggerMonitor::CTriggerMonitor(
        CTriggerMonitor *this,
        struct CTriggerMonitorPool *a2,
        struct IMSMQTriggersConfig *a3,
        void **a4,
        struct CQueueManager *a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  struct CQueueManager *v10; // rbx
  CTriggerMonitor *result; // rax
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = (__int64)a3;
  _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(&v12);
  CThread::CThread(this, v8, v9, (__int64)L"CTriggerMonitor", &v12);
  *(_QWORD *)this = &CTriggerMonitor::`vftable';
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 11) = a4;
  v10 = a5;
  _InterlockedIncrement((volatile signed __int32 *)a5 + 2);
  SafeRelease<CQueue>(*((CReference **)this + 14));
  *((_QWORD *)this + 14) = v10;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  SafeRelease<CQueue>(*((CReference **)this + 13));
  result = this;
  *((_QWORD *)this + 13) = a2;
  return result;
}

```

## disassembly

```asm
0x140007ea8  mov     rax, rsp
0x140007eab  mov     [rax+10h], rbx
0x140007eaf  mov     [rax+18h], rsi
0x140007eb3  mov     [rax+8], rcx
0x140007eb7  push    rdi
0x140007eb8  sub     rsp, 30h
0x140007ebc  mov     rsi, rcx
0x140007ebf  mov     [rax+8], r8
0x140007ec3  lea     rcx, [rax+8]
0x140007ec7  mov     rbx, r9
0x140007eca  mov     rdi, rdx
0x140007ecd  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x140007ed2  lea     rax, [rsp+38h+arg_0]
0x140007ed7  mov     rcx, rsi; ArgList
0x140007eda  lea     r9, aCtriggermonito_0; "CTriggerMonitor"
0x140007ee1  mov     [rsp+38h+var_18], rax; __int64
0x140007ee6  call    ??0CThread@@QEAA@KKPEB_WV?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@@Z; CThread::CThread(ulong,ulong,wchar_t const *,_com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>)
0x140007eeb  lea     rax, ??_7CTriggerMonitor@@6B@; const CTriggerMonitor::`vftable'
0x140007ef2  mov     [rsi], rax
0x140007ef5  mov     qword ptr [rsi+68h], 0
0x140007efd  mov     qword ptr [rsi+70h], 0
0x140007f05  mov     [rsi+58h], rbx
0x140007f09  mov     rbx, [rsp+38h+arg_20]
0x140007f0e  lock inc dword ptr [rbx+8]
0x140007f12  mov     rcx, [rsi+70h]
0x140007f16  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x140007f1b  mov     [rsi+70h], rbx
0x140007f1f  lock inc dword ptr [rdi+8]
0x140007f23  mov     rcx, [rsi+68h]
0x140007f27  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x140007f2c  mov     rbx, [rsp+38h+arg_8]
0x140007f31  mov     rax, rsi
0x140007f34  mov     [rsi+68h], rdi
0x140007f38  mov     rsi, [rsp+38h+arg_10]
0x140007f3d  add     rsp, 30h
0x140007f41  pop     rdi
0x140007f42  retn
```
