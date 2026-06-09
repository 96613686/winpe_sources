# Marshal::Details::SetDefaultVoid<utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>(void *,unsigned __int64)

- ea: `0x140011f60`
- end: `0x140011fe6`
- name: `??$SetDefaultVoid@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@@Details@Marshal@@YAXPEAX_K@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x140002344`
- `0x140011f60`
- `0x1400140a0`
- `0x1400198a4`

## pseudocode

```c
void __fastcall Marshal::Details::SetDefaultVoid<utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v3; // r9
  _QWORD *v4; // rdi
  __int64 v5; // rcx

  if ( a2 )
    Marshal::Details::FailFast((Marshal::Details *)a1);
  v3 = *a1;
  v4 = a1 + 1;
  if ( *a1 != -1 )
  {
    v5 = *v4 - v3;
    *v4 = v3;
    utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(v5, v3, v5 / 120 + v5);
    operator delete((void *)*a1, (const struct std::nothrow_t *)&std::nothrow);
  }
  *a1 = -1;
  a1[2] = -1;
  *v4 = -1;
}

```

## disassembly

```asm
0x140011f60  mov     [rsp+arg_0], rbx
0x140011f65  mov     [rsp+arg_8], rsi
0x140011f6a  push    rdi
0x140011f6b  sub     rsp, 20h
0x140011f6f  mov     rbx, rcx
0x140011f72  test    rdx, rdx
0x140011f75  jnz     short loc_140011FE0
0x140011f77  mov     r9, [rcx]
0x140011f7a  lea     rdi, [rcx+8]
0x140011f7e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140011f82  cmp     r9, rsi
0x140011f85  jz      short loc_140011FC5
0x140011f87  mov     rcx, [rdi]
0x140011f8a  mov     rax, 8888888888888889h
0x140011f94  sub     rcx, r9
0x140011f97  mov     [rdi], r9
0x140011f9a  imul    rcx
0x140011f9d  add     rdx, rcx
0x140011fa0  sar     rdx, 6
0x140011fa4  mov     r8, rdx
0x140011fa7  shr     r8, 3Fh
0x140011fab  add     r8, rdx
0x140011fae  mov     rdx, r9
0x140011fb1  call    ??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)
0x140011fb6  mov     rcx, [rbx]; void *
0x140011fb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011fc0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011fc5  mov     [rbx], rsi
0x140011fc8  mov     [rbx+10h], rsi
0x140011fcc  mov     rbx, [rsp+28h+arg_0]
0x140011fd1  mov     [rdi], rsi
0x140011fd4  mov     rsi, [rsp+28h+arg_8]
0x140011fd9  add     rsp, 20h
0x140011fdd  pop     rdi
0x140011fde  retn
0x140011fe0  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
