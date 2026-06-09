# std::vector<Container::Manager::Image::FeatureAdjustment,std::allocator<Container::Manager::Image::FeatureAdjustment>>::_Change_array(Container::Manager::Image::FeatureAdjustment * const,unsigned __int64,unsigned __int64)

- ea: `0x14001f4e8`
- end: `0x14001f5b9`
- name: `?_Change_array@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAUFeatureAdjustment@Image@Manager@Container@@_K1@Z`
- size: `209`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001307c`
- `0x140013230`
- `0x140013b08`
- `0x140013cf4`
- `0x1400148cc`
- `0x140014a44`

## callees

- `0x140002344`
- `0x14001f4e8`

## pseudocode

```c
__int64 __fastcall std::vector<Container::Manager::Image::FeatureAdjustment>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void **v4; // rbx
  void **v9; // rsi
  void **v10; // rcx
  const struct std::nothrow_t *v11; // rdx
  void **v12; // rax
  __int64 result; // rax

  v4 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(void ***)(a1 + 8);
    while ( v4 != v9 )
    {
      if ( *v4 != v4 + 2 )
        operator delete(*v4, (const struct std::nothrow_t *)&std::nothrow);
      v4 += 5;
    }
    v10 = *(void ***)a1;
    v11 = (const struct std::nothrow_t *)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3));
    if ( (unsigned __int64)v11 < 0x1000 )
    {
      v12 = *(void ***)a1;
    }
    else
    {
      v12 = (void **)*(v10 - 1);
      if ( (unsigned __int64)((char *)v10 - (char *)v12 - 8) > 0x1F )
        __fastfail(5u);
      v11 = (const struct std::nothrow_t *)((char *)v11 + 39);
    }
    operator delete(v12, v11);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 40 * a3;
  result = 5 * a4;
  *(_QWORD *)(a1 + 16) = a2 + 40 * a4;
  return result;
}

```

## disassembly

```asm
0x14001f4e8  push    rbx
0x14001f4ea  push    rsi
0x14001f4eb  push    rdi
0x14001f4ec  push    r12
0x14001f4ee  push    r14
0x14001f4f0  push    r15
0x14001f4f2  sub     rsp, 28h
0x14001f4f6  mov     rbx, [rcx]
0x14001f4f9  mov     r15, r9
0x14001f4fc  mov     r12, r8
0x14001f4ff  mov     r14, rdx
0x14001f502  mov     rdi, rcx
0x14001f505  test    rbx, rbx
0x14001f508  jz      loc_14001F58F
0x14001f50e  mov     rsi, [rcx+8]
0x14001f512  jmp     short loc_14001F530
0x14001f514  lea     rax, [rbx+10h]
0x14001f518  cmp     [rbx], rax
0x14001f51b  jz      short loc_14001F52C
0x14001f51d  mov     rcx, [rbx]; void *
0x14001f520  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001f527  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f52c  add     rbx, 28h ; '('
0x14001f530  cmp     rbx, rsi
0x14001f533  jnz     short loc_14001F514
0x14001f535  mov     rcx, [rdi]
0x14001f538  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x14001f542  mov     rax, [rdi+10h]
0x14001f546  sub     rax, rcx
0x14001f549  sar     rax, 3
0x14001f54d  imul    rax, rdx
0x14001f551  lea     rax, [rax+rax*4]
0x14001f555  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x14001f55d  cmp     rdx, 1000h
0x14001f564  jb      short loc_14001F584
0x14001f566  mov     rax, [rcx-8]
0x14001f56a  sub     rcx, rax
0x14001f56d  sub     rcx, 8
0x14001f571  cmp     rcx, 1Fh
0x14001f575  ja      short loc_14001F57D
0x14001f577  add     rdx, 27h ; '''
0x14001f57b  jmp     short loc_14001F587
0x14001f57d  mov     ecx, 5
0x14001f582  int     29h; Win8: RtlFailFast(ecx)
0x14001f584  mov     rax, rcx
0x14001f587  mov     rcx, rax; void *
0x14001f58a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f58f  lea     rax, [r12+r12*4]
0x14001f593  mov     [rdi], r14
0x14001f596  lea     rcx, [r14+rax*8]
0x14001f59a  mov     [rdi+8], rcx
0x14001f59e  lea     rax, [r15+r15*4]
0x14001f5a2  lea     rcx, [r14+rax*8]
0x14001f5a6  mov     [rdi+10h], rcx
0x14001f5aa  add     rsp, 28h
0x14001f5ae  pop     r15
0x14001f5b0  pop     r14
0x14001f5b2  pop     r12
0x14001f5b4  pop     rdi
0x14001f5b5  pop     rsi
0x14001f5b6  pop     rbx
0x14001f5b7  retn
```
