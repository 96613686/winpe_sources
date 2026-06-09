# std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1400161c8`
- end: `0x140016260`
- name: `??1_Reallocation_guard@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012ec4`
- `0x140013914`
- `0x140014754`

## callees

- `0x140002344`
- `0x1400161c8`

## pseudocode

```c
void __fastcall std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  void **v4; // rsi
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  void *v7; // rax

  if ( a1[1] )
  {
    v2 = a1[4];
    v3 = a1[3];
    if ( v3 != v2 )
    {
      v4 = (void **)(v3 + 8);
      do
      {
        if ( *v4 != v4 + 2 )
          operator delete(*v4, (const struct std::nothrow_t *)&std::nothrow);
        v3 += 40;
        v4 += 5;
      }
      while ( v3 != v2 );
    }
    v5 = a1[1];
    v6 = 40LL * a1[2];
    if ( v6 < 0x1000 )
    {
      v7 = (void *)a1[1];
    }
    else
    {
      v7 = *(void **)(v5 - 8);
      if ( (unsigned __int64)(v5 - (_QWORD)v7 - 8) > 0x1F )
        __fastfail(5u);
      v6 += 39LL;
    }
    operator delete(v7, (const struct std::nothrow_t *)v6);
  }
}

```

## disassembly

```asm
0x1400161c8  push    rbx
0x1400161ca  push    rbp
0x1400161cb  push    rsi
0x1400161cc  push    rdi
0x1400161cd  sub     rsp, 28h
0x1400161d1  cmp     qword ptr [rcx+8], 0
0x1400161d6  mov     rbx, rcx
0x1400161d9  jz      short loc_140016256
0x1400161db  mov     rbp, [rcx+20h]
0x1400161df  mov     rdi, [rcx+18h]
0x1400161e3  cmp     rdi, rbp
0x1400161e6  jz      short loc_140016211
0x1400161e8  lea     rsi, [rdi+8]
0x1400161ec  lea     rax, [rsi+10h]
0x1400161f0  cmp     [rsi], rax
0x1400161f3  jz      short loc_140016204
0x1400161f5  mov     rcx, [rsi]; void *
0x1400161f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400161ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016204  add     rdi, 28h ; '('
0x140016208  add     rsi, 28h ; '('
0x14001620c  cmp     rdi, rbp
0x14001620f  jnz     short loc_1400161EC
0x140016211  mov     rax, [rbx+10h]
0x140016215  mov     rdx, [rbx+8]
0x140016219  lea     rcx, [rax+rax*4]
0x14001621d  shl     rcx, 3
0x140016221  cmp     rcx, 1000h
0x140016228  jb      short loc_140016248
0x14001622a  mov     rax, [rdx-8]
0x14001622e  sub     rdx, rax
0x140016231  sub     rdx, 8
0x140016235  cmp     rdx, 1Fh
0x140016239  ja      short loc_140016241
0x14001623b  add     rcx, 27h ; '''
0x14001623f  jmp     short loc_14001624B
0x140016241  mov     ecx, 5
0x140016246  int     29h; Win8: RtlFailFast(ecx)
0x140016248  mov     rax, rdx
0x14001624b  mov     rdx, rcx; struct std::nothrow_t *
0x14001624e  mov     rcx, rax; void *
0x140016251  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016256  add     rsp, 28h
0x14001625a  pop     rdi
0x14001625b  pop     rsi
0x14001625c  pop     rbp
0x14001625d  pop     rbx
0x14001625e  retn
```
