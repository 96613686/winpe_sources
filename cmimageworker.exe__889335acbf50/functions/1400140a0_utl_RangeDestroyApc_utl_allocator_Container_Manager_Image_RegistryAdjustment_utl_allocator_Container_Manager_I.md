# utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)

- ea: `0x1400140a0`
- end: `0x140014132`
- name: `??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z`
- size: `146`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1400113ec`
- `0x140011f60`
- `0x140015718`
- `0x140015f98`
- `0x140016da0`
- `0x14001feac`

## callees

- `0x140002344`
- `0x1400140a0`

## pseudocode

```c
void __fastcall utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( a3 )
  {
    v3 = a3;
    do
    {
      --v3;
      v5 = 120 * v3;
      v6 = *(void **)(120 * v3 + a2 + 72);
      if ( v6 != (void *)(120 * v3 + a2 + 88) )
        operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
      v7 = *(void **)(v5 + a2 + 40);
      if ( v7 != (void *)(v5 + a2 + 56) )
        operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
      v8 = *(void **)(v5 + a2 + 8);
      if ( v8 != (void *)(v5 + a2 + 24) )
        operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x1400140a0  test    r8, r8
0x1400140a3  jz      locret_140014130
0x1400140a9  mov     [rsp+arg_0], rbx
0x1400140ae  mov     [rsp+arg_8], rsi
0x1400140b3  push    rdi
0x1400140b4  sub     rsp, 20h
0x1400140b8  mov     rbx, r8
0x1400140bb  mov     rsi, rdx
0x1400140be  dec     rbx
0x1400140c1  lea     rax, [rsi+58h]
0x1400140c5  imul    rdi, rbx, 78h ; 'x'
0x1400140c9  add     rax, rdi
0x1400140cc  mov     rcx, [rdi+rsi+48h]; void *
0x1400140d1  cmp     rcx, rax
0x1400140d4  jz      short loc_1400140E2
0x1400140d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400140dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400140e2  mov     rcx, [rdi+rsi+28h]; void *
0x1400140e7  lea     rax, [rsi+38h]
0x1400140eb  add     rax, rdi
0x1400140ee  cmp     rcx, rax
0x1400140f1  jz      short loc_1400140FF
0x1400140f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400140fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400140ff  mov     rcx, [rdi+rsi+8]; void *
0x140014104  lea     rax, [rsi+18h]
0x140014108  add     rax, rdi
0x14001410b  cmp     rcx, rax
0x14001410e  jz      short loc_14001411C
0x140014110  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140014117  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001411c  test    rbx, rbx
0x14001411f  jnz     short loc_1400140BE
0x140014121  mov     rbx, [rsp+28h+arg_0]
0x140014126  mov     rsi, [rsp+28h+arg_8]
0x14001412b  add     rsp, 20h
0x14001412f  pop     rdi
0x140014130  retn
```
