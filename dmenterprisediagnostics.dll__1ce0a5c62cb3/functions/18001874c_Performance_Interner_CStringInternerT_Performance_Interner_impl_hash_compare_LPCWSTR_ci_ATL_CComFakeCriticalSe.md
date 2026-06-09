# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x18001874c`
- end: `0x180018783`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018894`
- `0x1800254e1`

## callees

- `0x180001804`
- `0x18001874c`
- `0x1800187b0`

## pseudocode

```c
void __fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 *i; // rbx

  for ( i = *(__int64 **)(a1 + 8); ; operator delete((void *)i[2], a2) )
  {
    i = (__int64 *)*i;
    if ( i == *(__int64 **)(a1 + 8) )
      break;
  }
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::~_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>(a1);
}

```

## disassembly

```asm
0x18001874c  mov     [rsp+arg_0], rbx
0x180018751  push    rdi
0x180018752  sub     rsp, 20h
0x180018756  mov     rbx, [rcx+8]
0x18001875a  mov     rdi, rcx
0x18001875d  mov     rbx, [rbx]
0x180018760  cmp     rbx, [rdi+8]
0x180018764  jz      short loc_180018771
0x180018766  mov     rcx, [rbx+10h]; void *
0x18001876a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001876f  jmp     short loc_18001875D
0x180018771  mov     rcx, rdi
0x180018774  mov     rbx, [rsp+28h+arg_0]
0x180018779  add     rsp, 20h
0x18001877d  pop     rdi
0x18001877e  jmp     ??1?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::~_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>(void)
```
