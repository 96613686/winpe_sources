# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180006af0`
- end: `0x180006b28`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: `void __fastcall(void *, struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006b68`
- `0x1800070c0`
- `0x180007210`
- `0x180007fd4`

## callees

- `0x1800024d0`
- `0x180006af0`
- `0x180007e20`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, struct std::nothrow_t *a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  struct std::nothrow_t *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( (unsigned __int64)a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, (unsigned __int64 *)&v3);
    a2 = v3;
    a1 = v2;
  }
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x180006af0  mov     rax, rsp
0x180006af3  mov     [rax+10h], rdx
0x180006af7  mov     [rax+8], rcx
0x180006afb  sub     rsp, 28h
0x180006aff  cmp     rdx, 1000h
0x180006b06  jb      short loc_180006B1F
0x180006b08  lea     rdx, [rax+10h]; unsigned __int64 *
0x180006b0c  lea     rcx, [rax+8]; void **
0x180006b10  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180006b15  mov     rdx, [rsp+28h+arg_8]; struct std::nothrow_t *
0x180006b1a  mov     rcx, [rsp+28h+arg_0]; void *
0x180006b1f  add     rsp, 28h
0x180006b23  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
