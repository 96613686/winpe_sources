# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180004270`
- end: `0x18000429d`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800036b4`
- `0x180008e20`
- `0x180008ecc`
- `0x180008fb8`
- `0x1800090b0`
- `0x1800091a0`
- `0x18000926c`
- `0x180009340`
- `0x1800093fc`
- `0x180009a30`

## callees

- `0x180004270`
- `0x1800053f0`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a2 += 39LL;
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x180004270  cmp     rdx, 1000h
0x180004277  jb      short loc_180004291
0x180004279  mov     rax, [rcx-8]
0x18000427d  sub     rcx, rax
0x180004280  sub     rcx, 8
0x180004284  cmp     rcx, 1Fh
0x180004288  ja      short loc_180004296
0x18000428a  add     rdx, 27h ; '''; unsigned __int64
0x18000428e  mov     rcx, rax; void *
0x180004291  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004296  mov     ecx, 5
0x18000429b  int     29h; Win8: RtlFailFast(ecx)
```
