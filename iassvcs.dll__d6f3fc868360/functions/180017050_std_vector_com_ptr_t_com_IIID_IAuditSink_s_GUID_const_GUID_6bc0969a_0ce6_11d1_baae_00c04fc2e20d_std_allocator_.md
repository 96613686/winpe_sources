# std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>>::_Reallocate(unsigned __int64)

- ea: `0x180017050`
- end: `0x180017132`
- name: `?_Reallocate@?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@IEAAX_K@Z`
- size: `226`
- prototype: `_QWORD *__fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017150`

## callees

- `0x180001238`
- `0x18000d98c`
- `0x180016b3c`
- `0x180017050`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x1800170fc`
- `msvcrt!free` at `0x1800170fc`

## pseudocode

```c
_QWORD *__fastcall std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::_Reallocate(
        void **a1,
        unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  _QWORD *v6; // r14
  _QWORD *v7; // r13
  __int64 v8; // r12
  _QWORD *v9; // rsi
  _QWORD *result; // rax
  void *v11; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v11 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = operator new(8 * a2), (v11 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v9 = a1 + 1;
    std::_Uninit_move<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(
      *a1,
      a1[1],
      v4);
  }
  catch ( ... )
  {
    std::_Tree_buy<std::pair<std::wstring const,_RadiusClientEntry *>>::_Freenode0(v5, v11);
    throw;
  }
  v6 = *a1;
  v7 = (_QWORD *)*v9;
  v8 = (__int64)(*v9 - (_QWORD)*a1) >> 3;
  if ( *a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        if ( *v6 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
        ++v6;
      }
      while ( v6 != v7 );
      v9 = a1 + 1;
    }
    free(*a1);
  }
  a1[2] = &v4[a2];
  result = &v4[v8];
  *v9 = result;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180017050  mov     [rsp+arg_0], rbx
0x180017055  mov     [rsp+arg_10], rsi
0x18001705a  push    rdi
0x18001705b  push    r12
0x18001705d  push    r13
0x18001705f  push    r14
0x180017061  push    r15
0x180017063  sub     rsp, 30h
0x180017067  mov     r15, rdx
0x18001706a  mov     rdi, rcx
0x18001706d  xor     ebx, ebx
0x18001706f  mov     [rsp+58h+arg_8], rbx
0x180017074  test    rdx, rdx
0x180017077  jz      short loc_1800170AA
0x180017079  mov     rax, 1FFFFFFFFFFFFFFFh
0x180017083  cmp     rdx, rax
0x180017086  ja      loc_18001712C
0x18001708c  lea     rcx, ds:0[rdx*8]; Size
0x180017094  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017099  mov     rbx, rax
0x18001709c  mov     [rsp+58h+arg_8], rax
0x1800170a1  test    rax, rax
0x1800170a4  jz      loc_18001712C
0x1800170aa  lea     rsi, [rdi+8]
0x1800170ae  mov     r8, rbx
0x1800170b1  mov     rdx, [rsi]
0x1800170b4  mov     rcx, [rdi]
0x1800170b7  call    ??$_Uninit_move@PEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@PEAV1@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@V1@@std@@YAPEAV?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@PEAV1@00AEAU?$_Wrap_alloc@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::_Wrap_alloc<std::allocator<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>> &,_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>> *,std::_Nonscalar_ptr_iterator_tag)
0x1800170bc  nop
0x1800170bd  mov     r14, [rdi]
0x1800170c0  mov     r13, [rsi]
0x1800170c3  mov     r12, r13
0x1800170c6  sub     r12, r14
0x1800170c9  sar     r12, 3
0x1800170cd  test    r14, r14
0x1800170d0  jz      short loc_180017102
0x1800170d2  cmp     r14, r13
0x1800170d5  jz      short loc_1800170F9
0x1800170d7  mov     rcx, [r14]
0x1800170da  test    rcx, rcx
0x1800170dd  jz      short loc_1800170EC
0x1800170df  mov     rax, [rcx]
0x1800170e2  mov     rax, [rax+10h]
0x1800170e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170eb  nop
0x1800170ec  add     r14, 8
0x1800170f0  cmp     r14, r13
0x1800170f3  jnz     short loc_1800170D7
0x1800170f5  lea     rsi, [rdi+8]
0x1800170f9  mov     rcx, [rdi]; Block
0x1800170fc  call    cs:__imp_free
0x180017102  lea     rax, [rbx+r15*8]
0x180017106  mov     [rdi+10h], rax
0x18001710a  lea     rax, [rbx+r12*8]
0x18001710e  mov     [rsi], rax
0x180017111  mov     [rdi], rbx
0x180017114  mov     rbx, [rsp+58h+arg_0]
0x180017119  mov     rsi, [rsp+58h+arg_10]
0x18001711e  add     rsp, 30h
0x180017122  pop     r15
0x180017124  pop     r14
0x180017126  pop     r13
0x180017128  pop     r12
0x18001712a  pop     rdi
0x18001712b  retn
0x18001712c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
