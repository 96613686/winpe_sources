# std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>::~vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>(void)

- ea: `0x14001596c`
- end: `0x140015a31`
- name: `??1?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140010448`
- `0x14002f023`

## callees

- `0x140002344`
- `0x14001596c`

## pseudocode

```c
void __fastcall std::vector<Container::Manager::Image::CommandAdjustment>::~vector<Container::Manager::Image::CommandAdjustment>(
        char **a1)
{
  char *v1; // rbx
  char *v3; // rbp
  void **v4; // rsi
  char *v5; // rcx
  const struct std::nothrow_t *v6; // rdx
  char *v7; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    if ( v1 != v3 )
    {
      v4 = (void **)(v1 + 8);
      do
      {
        if ( *v4 != v4 + 2 )
          operator delete(*v4, (const struct std::nothrow_t *)&std::nothrow);
        v1 += 40;
        v4 += 5;
      }
      while ( v1 != v3 );
    }
    v5 = *a1;
    v6 = (const struct std::nothrow_t *)(8 * ((a1[2] - *a1) >> 3));
    if ( (unsigned __int64)v6 < 0x1000 )
    {
      v7 = *a1;
    }
    else
    {
      v7 = (char *)*((_QWORD *)v5 - 1);
      if ( (unsigned __int64)(v5 - v7 - 8) > 0x1F )
        __fastfail(5u);
      v6 = (const struct std::nothrow_t *)((char *)v6 + 39);
    }
    operator delete(v7, v6);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x14001596c  push    rbx
0x14001596e  push    rbp
0x14001596f  push    rsi
0x140015970  push    rdi
0x140015971  sub     rsp, 28h
0x140015975  mov     rbx, [rcx]
0x140015978  mov     rdi, rcx
0x14001597b  test    rbx, rbx
0x14001597e  jz      loc_140015A27
0x140015984  mov     rbp, [rcx+8]
0x140015988  cmp     rbx, rbp
0x14001598b  jz      short loc_1400159B6
0x14001598d  lea     rsi, [rbx+8]
0x140015991  lea     rax, [rsi+10h]
0x140015995  cmp     [rsi], rax
0x140015998  jz      short loc_1400159A9
0x14001599a  mov     rcx, [rsi]; void *
0x14001599d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400159a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400159a9  add     rbx, 28h ; '('
0x1400159ad  add     rsi, 28h ; '('
0x1400159b1  cmp     rbx, rbp
0x1400159b4  jnz     short loc_140015991
0x1400159b6  mov     rcx, [rdi]
0x1400159b9  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x1400159c3  mov     rax, [rdi+10h]
0x1400159c7  sub     rax, rcx
0x1400159ca  sar     rax, 3
0x1400159ce  imul    rax, rdx
0x1400159d2  lea     rax, [rax+rax*4]
0x1400159d6  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x1400159de  cmp     rdx, 1000h
0x1400159e5  jb      short loc_140015A05
0x1400159e7  mov     rax, [rcx-8]
0x1400159eb  sub     rcx, rax
0x1400159ee  sub     rcx, 8
0x1400159f2  cmp     rcx, 1Fh
0x1400159f6  ja      short loc_1400159FE
0x1400159f8  add     rdx, 27h ; '''
0x1400159fc  jmp     short loc_140015A08
0x1400159fe  mov     ecx, 5
0x140015a03  int     29h; Win8: RtlFailFast(ecx)
0x140015a05  mov     rax, rcx
0x140015a08  mov     rcx, rax; void *
0x140015a0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015a10  mov     qword ptr [rdi], 0
0x140015a17  mov     qword ptr [rdi+8], 0
0x140015a1f  mov     qword ptr [rdi+10h], 0
0x140015a27  add     rsp, 28h
0x140015a2b  pop     rdi
0x140015a2c  pop     rsi
0x140015a2d  pop     rbp
0x140015a2e  pop     rbx
0x140015a2f  retn
```
