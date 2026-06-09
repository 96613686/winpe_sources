# utl::_Tree<Container::Manager::Image::RegistryHive,utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<Container::Manager::Image::RegistryHive,utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(void)

- ea: `0x140015718`
- end: `0x1400157ec`
- name: `??1?$_Tree@W4RegistryHive@Image@Manager@Container@@U?$pair@$$CBW4RegistryHive@Image@Manager@Container@@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@utl@@U?$less@W4RegistryHive@Image@Manager@Container@@@6@V?$allocator@U?$pair@$$CBW4RegistryHive@Image@Manager@Container@@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@utl@@@6@$0A@@utl@@IEAA@XZ`
- size: `212`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x140016da0`

## callees

- `0x140002344`
- `0x1400140a0`
- `0x140015718`

## pseudocode

```c
void __fastcall utl::_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>::~_Tree<enum Container::Manager::Image::RegistryHive,utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>,utl::less<enum Container::Manager::Image::RegistryHive>,utl::allocator<utl::pair<enum Container::Manager::Image::RegistryHive const,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>>,0>(
        _QWORD *a1)
{
  unsigned __int64 v1; // rbx
  unsigned __int64 v3; // rsi
  void *v4; // rbp
  __int64 v5; // r9
  __int64 v6; // rcx

  v1 = a1[2];
  if ( (_QWORD *)v1 != a1 )
  {
    while ( 1 )
    {
      while ( *(void ***)(v1 + 8) != &utl::_TreeSentinel )
        v1 = *(_QWORD *)(v1 + 8);
LABEL_9:
      if ( *(void ***)(v1 + 16) == &utl::_TreeSentinel )
        break;
      v1 = *(_QWORD *)(v1 + 16);
    }
    while ( 1 )
    {
      v3 = v1;
      v4 = (void *)v1;
      v1 = *(_QWORD *)v1 & 0xFFFFFFFFFFFFFFFEuLL;
      v5 = *(_QWORD *)(v3 + 32);
      if ( v5 != -1 )
      {
        v6 = *(_QWORD *)(v3 + 40) - v5;
        *(_QWORD *)(v3 + 40) = v5;
        utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(v6, v5, v6 / 120 + v6);
        operator delete(*(void **)(v3 + 32), (const struct std::nothrow_t *)&std::nothrow);
      }
      operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
      if ( (_QWORD *)v1 == a1 )
        break;
      if ( *(void ***)(v1 + 8) != &utl::_TreeSentinel )
      {
        *(_QWORD *)(v1 + 8) = &utl::_TreeSentinel;
        goto LABEL_9;
      }
    }
    *a1 = a1;
    a1[1] = a1;
    a1[2] = a1;
    a1[3] = 0;
  }
}

```

## disassembly

```asm
0x140015718  push    rbx
0x14001571a  push    rbp
0x14001571b  push    rsi
0x14001571c  push    rdi
0x14001571d  push    r14
0x14001571f  sub     rsp, 20h
0x140015723  mov     rbx, [rcx+10h]
0x140015727  mov     rdi, rcx
0x14001572a  cmp     rbx, rcx
0x14001572d  jz      loc_1400157E0
0x140015733  lea     r14, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14001573a  mov     rax, [rbx+8]
0x14001573e  cmp     rax, r14
0x140015741  jz      short loc_1400157BE
0x140015743  mov     rbx, rax
0x140015746  jmp     short loc_14001573A
0x140015748  mov     rsi, rbx
0x14001574b  mov     rbp, rbx
0x14001574e  mov     rbx, [rbx]
0x140015751  and     rbx, 0FFFFFFFFFFFFFFFEh
0x140015755  mov     r9, [rsi+20h]
0x140015759  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x14001575d  jz      short loc_1400157A0
0x14001575f  mov     rcx, [rsi+28h]
0x140015763  mov     rax, 8888888888888889h
0x14001576d  sub     rcx, r9
0x140015770  mov     [rsi+28h], r9
0x140015774  imul    rcx
0x140015777  add     rdx, rcx
0x14001577a  sar     rdx, 6
0x14001577e  mov     r8, rdx
0x140015781  shr     r8, 3Fh
0x140015785  add     r8, rdx
0x140015788  mov     rdx, r9
0x14001578b  call    ??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)
0x140015790  mov     rcx, [rsi+20h]; void *
0x140015794  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001579b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400157a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400157a7  mov     rcx, rbp; void *
0x1400157aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400157af  cmp     rbx, rdi
0x1400157b2  jz      short loc_1400157CD
0x1400157b4  cmp     [rbx+8], r14
0x1400157b8  jz      short loc_140015748
0x1400157ba  mov     [rbx+8], r14
0x1400157be  cmp     [rbx+10h], r14
0x1400157c2  jz      short loc_140015748
0x1400157c4  mov     rbx, [rbx+10h]
0x1400157c8  jmp     loc_14001573A
0x1400157cd  mov     [rdi], rdi
0x1400157d0  mov     [rdi+8], rdi
0x1400157d4  mov     [rdi+10h], rdi
0x1400157d8  mov     qword ptr [rdi+18h], 0
0x1400157e0  add     rsp, 20h
0x1400157e4  pop     r14
0x1400157e6  pop     rdi
0x1400157e7  pop     rsi
0x1400157e8  pop     rbp
0x1400157e9  pop     rbx
0x1400157ea  retn
```
