# std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::_Xlen(void)

- ea: `0x180017138`
- end: `0x180017149`
- name: `?_Xlen@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017150`

## callees

- `0x180001260`

## pseudocode

```c
void __noreturn std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x180017138  sub     rsp, 28h
0x18001713c  lea     rcx, aVectorTTooLong
0x180017143  call    ?_Xlength_error@std@@YAXPEBD@Z
```
