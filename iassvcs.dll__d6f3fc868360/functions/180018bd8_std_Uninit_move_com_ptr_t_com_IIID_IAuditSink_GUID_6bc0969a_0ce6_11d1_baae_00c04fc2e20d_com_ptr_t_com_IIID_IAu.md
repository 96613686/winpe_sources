# _std::_Uninit_move__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d______std::allocator__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d______::_1_::catch$1

- ea: `0x180018bd8`
- end: `0x180018c08`
- name: `_std::_Uninit_move__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d______std::allocator__com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______com_ptr_t__com_IIID_IAuditSink_&_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d______::_1_::catch$1`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001e0e`
- `0x18000d568`
- `0x180018bd8`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move__com_ptr_t__com_IIID_IAuditSink___GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______com_ptr_t__com_IIID_IAuditSink___GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d______std::allocator__com_ptr_t__com_IIID_IAuditSink___GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d_______com_ptr_t__com_IIID_IAuditSink___GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d______::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  _QWORD *i; // rbx

  for ( i = *(_QWORD **)(a2 + 72); i != *(_QWORD **)(a2 + 64); ++i )
    std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::destroy<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(
      a1,
      i);
  throw;
}

```

## disassembly

```asm
0x180018bd8  mov     [rsp+arg_8], rdx
0x180018bdd  push    rbx
0x180018bde  push    rbp
0x180018bdf  sub     rsp, 28h
0x180018be3  mov     rbp, rdx
0x180018be6  mov     rbx, [rbp+48h]
0x180018bea  jmp     short loc_180018BF8
0x180018bec  mov     rdx, rbx
0x180018bef  call    ??$destroy@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@?$_Wrap_alloc@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAAXPEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@Z; std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::destroy<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *)
0x180018bf4  add     rbx, 8
0x180018bf8  cmp     rbx, [rbp+40h]
0x180018bfc  jnz     short loc_180018BEC
0x180018bfe  xor     edx, edx; pThrowInfo
0x180018c00  xor     ecx, ecx; pExceptionObject
0x180018c02  call    _CxxThrowException_0
```
