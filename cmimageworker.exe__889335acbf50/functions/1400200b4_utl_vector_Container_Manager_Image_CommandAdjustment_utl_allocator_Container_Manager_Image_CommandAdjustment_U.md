# utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_Uninit(void)

- ea: `0x1400200b4`
- end: `0x140020144`
- name: `?_Uninit@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAAXXZ`
- size: `144`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140011ea0`
- `0x140015f98`
- `0x14001f9f8`

## callees

- `0x140002344`
- `0x1400200b4`

## pseudocode

```c
void __fastcall utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_Uninit(
        __int64 a1)
{
  _QWORD *v1; // rdi
  __int64 v3; // rdx
  __int64 v4; // rbx
  char *v5; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    v4 = v3 / 40;
    while ( v4 )
    {
      --v4;
      v5 = (char *)v1[5 * v4 + 1];
      if ( v5 != (char *)&v1[5 * v4 + 3] )
        operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    }
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x1400200b4  mov     [rsp+arg_0], rbx
0x1400200b9  mov     [rsp+arg_8], rsi
0x1400200be  push    rdi
0x1400200bf  sub     rsp, 20h
0x1400200c3  mov     rdi, [rcx]
0x1400200c6  mov     rsi, rcx
0x1400200c9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400200cd  jz      short loc_140020133
0x1400200cf  mov     rdx, [rcx+8]
0x1400200d3  mov     rax, 6666666666666667h
0x1400200dd  sub     rdx, rdi
0x1400200e0  mov     [rcx+8], rdi
0x1400200e4  imul    rdx
0x1400200e7  mov     rbx, rdx
0x1400200ea  sar     rbx, 4
0x1400200ee  mov     rax, rbx
0x1400200f1  shr     rax, 3Fh
0x1400200f5  add     rbx, rax
0x1400200f8  jz      short loc_140020124
0x1400200fa  dec     rbx
0x1400200fd  lea     rax, [rbx+rbx*4]
0x140020101  mov     rcx, [rdi+rax*8+8]; void *
0x140020106  lea     rax, [rax+3]
0x14002010a  lea     rax, [rdi+rax*8]
0x14002010e  cmp     rcx, rax
0x140020111  jz      short loc_14002011F
0x140020113  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002011a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002011f  test    rbx, rbx
0x140020122  jnz     short loc_1400200FA
0x140020124  mov     rcx, [rsi]; void *
0x140020127  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002012e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140020133  mov     rbx, [rsp+28h+arg_0]
0x140020138  mov     rsi, [rsp+28h+arg_8]
0x14002013d  add     rsp, 20h
0x140020141  pop     rdi
0x140020142  retn
```
