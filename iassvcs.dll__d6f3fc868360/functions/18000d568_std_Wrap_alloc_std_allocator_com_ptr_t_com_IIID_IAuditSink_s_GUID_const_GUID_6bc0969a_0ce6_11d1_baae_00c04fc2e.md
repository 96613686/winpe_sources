# std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::destroy<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *)

- ea: `0x18000d568`
- end: `0x18000d586`
- name: `??$destroy@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@?$_Wrap_alloc@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAAXPEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@Z`
- size: `30`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018bd8`

## callees

- `0x18000d568`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::destroy<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  return result;
}

```

## disassembly

```asm
0x18000d568  sub     rsp, 28h
0x18000d56c  mov     rcx, [rdx]
0x18000d56f  test    rcx, rcx
0x18000d572  jz      short loc_18000D581
0x18000d574  mov     rax, [rcx]
0x18000d577  mov     rax, [rax+10h]
0x18000d57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d580  nop
0x18000d581  add     rsp, 28h
0x18000d585  retn
```
