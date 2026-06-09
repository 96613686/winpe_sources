# std::_Uninit_move<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>> &,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180016b3c`
- end: `0x180016ba4`
- name: `??$_Uninit_move@PEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@PEAV1@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@V1@@std@@YAPEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@PEAV1@00AEAU?$_Wrap_alloc@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `104`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017050`

## callees

- `0x180016b3c`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v3; // rbx
  _QWORD *i; // rdi
  _QWORD *result; // rax
  _QWORD *j; // rbx
  _QWORD *v8; // [rsp+40h] [rbp+18h]

  v8 = a3;
  try
  {
    v3 = a3;
    for ( i = a1; i != a2; ++i )
    {
      a1 = (_QWORD *)*i;
      *v3 = *i;
      if ( a1 )
        (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
      v8 = ++v3;
    }
    result = v3;
  }
  catch ( ... )
  {
    for ( j = a3; j != v8; ++j )
      std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::destroy<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(
        a1,
        j);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180016b3c  mov     rax, rsp
0x180016b3f  mov     [rax+8], rbx
0x180016b43  mov     [rax+10h], rsi
0x180016b47  mov     [rax+20h], r9
0x180016b4b  mov     [rax+18h], r8
0x180016b4f  push    rdi
0x180016b50  sub     rsp, 20h
0x180016b54  mov     rbx, r8
0x180016b57  mov     rsi, rdx
0x180016b5a  mov     rdi, rcx
0x180016b5d  mov     [rsp+28h+arg_18], rbx
0x180016b62  cmp     rcx, rdx
0x180016b65  jz      short loc_180016B91
0x180016b67  mov     rcx, [rdi]
0x180016b6a  mov     [rbx], rcx
0x180016b6d  test    rcx, rcx
0x180016b70  jz      short loc_180016B7F
0x180016b72  mov     rax, [rcx]
0x180016b75  mov     rax, [rax+8]
0x180016b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b7e  nop
0x180016b7f  add     rbx, 8
0x180016b83  mov     [rsp+28h+arg_10], rbx
0x180016b88  add     rdi, 8
0x180016b8c  cmp     rdi, rsi
0x180016b8f  jnz     short loc_180016B67
0x180016b91  mov     rax, rbx
0x180016b94  mov     rbx, [rsp+28h+arg_0]
0x180016b99  mov     rsi, [rsp+28h+arg_8]
0x180016b9e  add     rsp, 20h
0x180016ba2  pop     rdi
0x180016ba3  retn
```
