# std::_Move_unchecked<gsl::byte *,gsl::byte *>(gsl::byte *,gsl::byte *,gsl::byte *)

- ea: `0x140005278`
- end: `0x1400052a8`
- name: `??$_Move_unchecked@PEAW4byte@gsl@@PEAW412@@std@@YAPEAW4byte@gsl@@PEAW412@00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c69b`
- `0x14000c70f`

## callees

- `0x1400027c6`

## pseudocode

```c
__int64 __fastcall std::_Move_unchecked<enum gsl::byte *,enum gsl::byte *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x140005278  mov     [rsp+arg_0], rbx
0x14000527d  push    rdi
0x14000527e  sub     rsp, 20h
0x140005282  mov     rbx, rdx
0x140005285  mov     rdi, r8
0x140005288  sub     rbx, rcx
0x14000528b  mov     rdx, rcx; Src
0x14000528e  mov     r8, rbx; Size
0x140005291  mov     rcx, rdi; void *
0x140005294  call    memmove_0
0x140005299  lea     rax, [rbx+rdi]
0x14000529d  mov     rbx, [rsp+28h+arg_0]
0x1400052a2  add     rsp, 20h
0x1400052a6  pop     rdi
0x1400052a7  retn
```
