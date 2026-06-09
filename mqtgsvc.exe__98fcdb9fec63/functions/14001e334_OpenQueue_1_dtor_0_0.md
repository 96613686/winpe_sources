# _OpenQueue_::_1_::dtor$0_0

- ea: `0x14001e334`
- end: `0x14001e340`
- name: `_OpenQueue_::_1_::dtor$0_0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003be8`

## pseudocode

```c
__int64 __fastcall OpenQueue_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>(a2 + 32);
}

```

## disassembly

```asm
0x14001e334  lea     rcx, [rdx+20h]
0x14001e33b  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UIMSMQQueueInfo4@@$1?_GUID_eba96b21_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>(void)
```
