# std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)

- ea: `0x140012e48`
- end: `0x140012ebd`
- name: `??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z`
- size: `117`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1400111d0`
- `0x1400133e4`
- `0x140013ee8`
- `0x140014bbc`
- `0x140015b08`
- `0x14001f5c0`

## callees

- `0x140002344`
- `0x140012e48`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rcx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = (_QWORD *)v3[9];
      if ( v4 != v3 + 11 )
        operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
      v5 = (_QWORD *)v3[5];
      if ( v5 != v3 + 7 )
        operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
      v6 = (_QWORD *)v3[1];
      if ( v6 != v3 + 3 )
        operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
      v3 += 15;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x140012e48  cmp     rcx, rdx
0x140012e4b  jz      short locret_140012EBB
0x140012e4d  mov     [rsp+arg_0], rbx
0x140012e52  push    rdi
0x140012e53  sub     rsp, 20h
0x140012e57  mov     rdi, rdx
0x140012e5a  mov     rbx, rcx
0x140012e5d  mov     rcx, [rbx+48h]; void *
0x140012e61  lea     rax, [rbx+58h]
0x140012e65  cmp     rcx, rax
0x140012e68  jz      short loc_140012E76
0x140012e6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012e71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012e76  mov     rcx, [rbx+28h]; void *
0x140012e7a  lea     rax, [rbx+38h]
0x140012e7e  cmp     rcx, rax
0x140012e81  jz      short loc_140012E8F
0x140012e83  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012e8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012e8f  mov     rcx, [rbx+8]; void *
0x140012e93  lea     rax, [rbx+18h]
0x140012e97  cmp     rcx, rax
0x140012e9a  jz      short loc_140012EA8
0x140012e9c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140012ea3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012ea8  add     rbx, 78h ; 'x'
0x140012eac  cmp     rbx, rdi
0x140012eaf  jnz     short loc_140012E5D
0x140012eb1  mov     rbx, [rsp+28h+arg_0]
0x140012eb6  add     rsp, 20h
0x140012eba  pop     rdi
0x140012ebb  retn
```
