# std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>::_Change_array(Container::Manager::Image::CommandAdjustment * const,unsigned __int64,unsigned __int64)

- ea: `0x14001f404`
- end: `0x14001f4e2`
- name: `?_Change_array@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAUCommandAdjustment@Image@Manager@Container@@_K1@Z`
- size: `222`
- prototype: `__int64 __fastcall(char **, char *, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012ec4`
- `0x140013914`
- `0x140014754`

## callees

- `0x140002344`
- `0x14001f404`

## pseudocode

```c
__int64 __fastcall std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(
        char **a1,
        char *a2,
        __int64 a3,
        __int64 a4)
{
  char *v4; // rbx
  char *v9; // rbp
  void **v10; // rsi
  char *v11; // rcx
  const struct std::nothrow_t *v12; // rdx
  char *v13; // rax
  __int64 result; // rax

  v4 = *a1;
  if ( *a1 )
  {
    v9 = a1[1];
    if ( v4 != v9 )
    {
      v10 = (void **)(v4 + 8);
      do
      {
        if ( *v10 != v10 + 2 )
          operator delete(*v10, (const struct std::nothrow_t *)&std::nothrow);
        v4 += 40;
        v10 += 5;
      }
      while ( v4 != v9 );
    }
    v11 = *a1;
    v12 = (const struct std::nothrow_t *)(8 * ((a1[2] - *a1) >> 3));
    if ( (unsigned __int64)v12 < 0x1000 )
    {
      v13 = *a1;
    }
    else
    {
      v13 = (char *)*((_QWORD *)v11 - 1);
      if ( (unsigned __int64)(v11 - v13 - 8) > 0x1F )
        __fastfail(5u);
      v12 = (const struct std::nothrow_t *)((char *)v12 + 39);
    }
    operator delete(v13, v12);
  }
  *a1 = a2;
  a1[1] = &a2[40 * a3];
  result = 5 * a4;
  a1[2] = &a2[40 * a4];
  return result;
}

```

## disassembly

```asm
0x14001f404  push    rbx
0x14001f406  push    rbp
0x14001f407  push    rsi
0x14001f408  push    rdi
0x14001f409  push    r12
0x14001f40b  push    r14
0x14001f40d  push    r15
0x14001f40f  sub     rsp, 20h
0x14001f413  mov     rbx, [rcx]
0x14001f416  mov     r15, r9
0x14001f419  mov     r12, r8
0x14001f41c  mov     r14, rdx
0x14001f41f  mov     rdi, rcx
0x14001f422  test    rbx, rbx
0x14001f425  jz      loc_14001F4B7
0x14001f42b  mov     rbp, [rcx+8]
0x14001f42f  cmp     rbx, rbp
0x14001f432  jz      short loc_14001F45D
0x14001f434  lea     rsi, [rbx+8]
0x14001f438  lea     rax, [rsi+10h]
0x14001f43c  cmp     [rsi], rax
0x14001f43f  jz      short loc_14001F450
0x14001f441  mov     rcx, [rsi]; void *
0x14001f444  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001f44b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f450  add     rbx, 28h ; '('
0x14001f454  add     rsi, 28h ; '('
0x14001f458  cmp     rbx, rbp
0x14001f45b  jnz     short loc_14001F438
0x14001f45d  mov     rcx, [rdi]
0x14001f460  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x14001f46a  mov     rax, [rdi+10h]
0x14001f46e  sub     rax, rcx
0x14001f471  sar     rax, 3
0x14001f475  imul    rax, rdx
0x14001f479  lea     rax, [rax+rax*4]
0x14001f47d  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x14001f485  cmp     rdx, 1000h
0x14001f48c  jb      short loc_14001F4AC
0x14001f48e  mov     rax, [rcx-8]
0x14001f492  sub     rcx, rax
0x14001f495  sub     rcx, 8
0x14001f499  cmp     rcx, 1Fh
0x14001f49d  ja      short loc_14001F4A5
0x14001f49f  add     rdx, 27h ; '''
0x14001f4a3  jmp     short loc_14001F4AF
0x14001f4a5  mov     ecx, 5
0x14001f4aa  int     29h; Win8: RtlFailFast(ecx)
0x14001f4ac  mov     rax, rcx
0x14001f4af  mov     rcx, rax; void *
0x14001f4b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f4b7  lea     rax, [r12+r12*4]
0x14001f4bb  mov     [rdi], r14
0x14001f4be  lea     rcx, [r14+rax*8]
0x14001f4c2  mov     [rdi+8], rcx
0x14001f4c6  lea     rax, [r15+r15*4]
0x14001f4ca  lea     rcx, [r14+rax*8]
0x14001f4ce  mov     [rdi+10h], rcx
0x14001f4d2  add     rsp, 20h
0x14001f4d6  pop     r15
0x14001f4d8  pop     r14
0x14001f4da  pop     r12
0x14001f4dc  pop     rdi
0x14001f4dd  pop     rsi
0x14001f4de  pop     rbp
0x14001f4df  pop     rbx
0x14001f4e0  retn
```
