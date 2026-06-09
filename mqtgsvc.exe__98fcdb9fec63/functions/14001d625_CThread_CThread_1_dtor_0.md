# _CThread::CThread_::_1_::dtor$0

- ea: `0x14001d625`
- end: `0x14001d631`
- name: `_CThread::CThread_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003be8`

## pseudocode

```c
__int64 __fastcall CThread::CThread_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>(*(_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x14001d625  mov     rcx, [rdx+58h]
0x14001d62c  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UIMSMQQueueInfo4@@$1?_GUID_eba96b21_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>(void)
```
