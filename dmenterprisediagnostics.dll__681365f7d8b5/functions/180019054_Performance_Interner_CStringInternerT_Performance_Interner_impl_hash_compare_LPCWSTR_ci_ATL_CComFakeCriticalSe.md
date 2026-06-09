# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x180019054`
- end: `0x18001908b`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800191a0`
- `0x18002639a`

## callees

- `0x180001824`
- `0x180019054`
- `0x1800190b8`

## pseudocode

```c
__int64 __fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(
        __int64 a1)
{
  __int64 *i; // rbx

  for ( i = *(__int64 **)(a1 + 8); ; operator delete((void *)i[2]) )
  {
    i = (__int64 *)*i;
    if ( i == *(__int64 **)(a1 + 8) )
      break;
  }
  return std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::~_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>(a1);
}

```

## disassembly

```asm
0x180019054  mov     [rsp+arg_0], rbx
0x180019059  push    rdi
0x18001905a  sub     rsp, 20h
0x18001905e  mov     rbx, [rcx+8]
0x180019062  mov     rdi, rcx
0x180019065  mov     rbx, [rbx]
0x180019068  cmp     rbx, [rdi+8]
0x18001906c  jz      short loc_180019079
0x18001906e  mov     rcx, [rbx+10h]; void *
0x180019072  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019077  jmp     short loc_180019065
0x180019079  mov     rcx, rdi
0x18001907c  mov     rbx, [rsp+28h+arg_0]
0x180019081  add     rsp, 20h
0x180019085  pop     rdi
0x180019086  jmp     ??1?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::~_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>(void)
```
