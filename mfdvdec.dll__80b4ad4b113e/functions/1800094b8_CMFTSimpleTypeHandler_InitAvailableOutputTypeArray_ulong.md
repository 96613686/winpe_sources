# CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)

- ea: `0x1800094b8`
- end: `0x180009564`
- name: `?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z`
- size: `172`
- prototype: `__int64 __fastcall(CMFTSimpleTypeHandler *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180005340`
- `0x180008e58`

## callees

- `0x180001120`
- `0x180001178`
- `0x180001eb0`
- `0x1800094b8`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(CMFTSimpleTypeHandler *this, unsigned int a2)
{
  unsigned int v2; // esi
  unsigned __int64 v3; // rbp
  void **i; // rbx
  __int64 v6; // rcx
  void *v7; // rax

  v2 = 0;
  v3 = a2;
  for ( i = (void **)((char *)this + 40); v2 < *((_DWORD *)this + 8); ++v2 )
  {
    v6 = *((_QWORD *)*i + 2 * v2);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *((_QWORD *)*i + 2 * v2) = 0;
    }
  }
  operator delete(*i);
  *((_DWORD *)this + 8) = 0;
  if ( (_DWORD)v3 )
  {
    v7 = operator new(saturated_mul(v3, 0x10u));
    *i = v7;
    if ( !v7 )
      return 2147942414LL;
    memset_0(v7, 0, 16 * v3);
    *((_DWORD *)this + 8) = v3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800094b8  push    rbx
0x1800094ba  push    rbp
0x1800094bb  push    rsi
0x1800094bc  push    rdi
0x1800094bd  push    r14
0x1800094bf  sub     rsp, 20h
0x1800094c3  xor     esi, esi
0x1800094c5  mov     ebp, edx
0x1800094c7  lea     rbx, [rcx+28h]
0x1800094cb  mov     rdi, rcx
0x1800094ce  cmp     [rcx+20h], esi
0x1800094d1  jbe     short loc_180009503
0x1800094d3  mov     rax, [rbx]
0x1800094d6  mov     r14d, esi
0x1800094d9  add     r14, r14
0x1800094dc  mov     rcx, [rax+r14*8]
0x1800094e0  test    rcx, rcx
0x1800094e3  jz      short loc_1800094FC
0x1800094e5  mov     rax, [rcx]
0x1800094e8  mov     rax, [rax+10h]
0x1800094ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f1  mov     rax, [rbx]
0x1800094f4  mov     qword ptr [rax+r14*8], 0
0x1800094fc  inc     esi
0x1800094fe  cmp     esi, [rdi+20h]
0x180009501  jb      short loc_1800094D3
0x180009503  mov     rcx, [rbx]; Block
0x180009506  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000950b  mov     dword ptr [rdi+20h], 0
0x180009512  test    ebp, ebp
0x180009514  jz      short loc_180009557
0x180009516  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000951d  mov     eax, 10h
0x180009522  mul     rbp
0x180009525  mov     rsi, rbp
0x180009528  cmovb   rax, rcx
0x18000952c  mov     rcx, rax; Size
0x18000952f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009534  mov     [rbx], rax
0x180009537  test    rax, rax
0x18000953a  jnz     short loc_180009543
0x18000953c  mov     eax, 8007000Eh
0x180009541  jmp     short loc_180009559
0x180009543  shl     rsi, 4
0x180009547  xor     edx, edx; Val
0x180009549  mov     r8, rsi; Size
0x18000954c  mov     rcx, rax; void *
0x18000954f  call    memset_0
0x180009554  mov     [rdi+20h], ebp
0x180009557  xor     eax, eax
0x180009559  add     rsp, 20h
0x18000955d  pop     r14
0x18000955f  pop     rdi
0x180009560  pop     rsi
0x180009561  pop     rbp
0x180009562  pop     rbx
0x180009563  retn
```
