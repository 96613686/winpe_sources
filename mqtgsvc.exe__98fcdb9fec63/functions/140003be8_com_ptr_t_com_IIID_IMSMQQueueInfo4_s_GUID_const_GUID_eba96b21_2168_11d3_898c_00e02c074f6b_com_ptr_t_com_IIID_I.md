# _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>(void)

- ea: `0x140003be8`
- end: `0x140003bed`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIMSMQQueueInfo4@@$1?_GUID_eba96b21_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d625`
- `0x14001d637`
- `0x14001d74e`
- `0x14001d902`
- `0x14001d9a5`
- `0x14001dc2f`
- `0x14001dc82`
- `0x14001e043`
- `0x14001e216`
- `0x14001e334`
- `0x14001e346`
- `0x14001e55e`
- `0x14001e582`

## callees

- `0x140004eb4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>::~_com_ptr_t<_com_IIID<IMSMQQueueInfo4,&__s_GUID const _GUID_eba96b21_2168_11d3_898c_00e02c074f6b>>(
        __int64 a1)
{
  return R<IObjectContext>::~R<IObjectContext>(a1);
}

```

## disassembly

```asm
0x140003be8  jmp     ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
```
