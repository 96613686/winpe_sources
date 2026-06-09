# std::_Merge_move_unchecked<GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *,bool (*)(GDI::MatchingAxisValueRecord const &,GDI::MatchingAxisValueRecord const &)>(GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord * const,GDI::MatchingAxisValueRecord * const,GDI::MatchingAxisValueRecord *,bool (*)(GDI::MatchingAxisValueRecord const &,GDI::MatchingAxisValueRecord const &))

- ea: `0x140094230`
- end: `0x1400942d5`
- name: `??$_Merge_move_unchecked@PEAUMatchingAxisValueRecord@GDI@@PEAU12@P6A_NAEBU12@0@Z@std@@YAPEAUMatchingAxisValueRecord@GDI@@PEAU12@QEAU12@10P6A_NAEBU12@2@Z@Z`
- size: `165`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140093d80`

## callees

- `0x140076ef6`
- `0x140094230`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall std::_Merge_move_unchecked<GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *,bool (*)(GDI::MatchingAxisValueRecord const &,GDI::MatchingAxisValueRecord const &)>(
        char *Src,
        char *a2,
        char *a3,
        _OWORD *a4,
        unsigned __int8 (__fastcall *a5)(char *, char *))
{
  char *v9; // rdi
  _OWORD *v10; // r14
  __int128 v11; // xmm1
  size_t v12; // rsi
  __int128 v14; // xmm1
  size_t v15; // r15

  v9 = a2;
  while ( 1 )
  {
    v10 = a4 + 2;
    if ( !a5(v9, Src) )
      break;
    *a4 = *(_OWORD *)v9;
    v11 = *((_OWORD *)v9 + 1);
    v9 += 32;
    a4[1] = v11;
    if ( v9 == a3 )
    {
      v12 = a2 - Src;
      memmove_0(a4 + 2, Src, v12);
      return (__int64)v10 + v12;
    }
LABEL_6:
    a4 += 2;
  }
  *a4 = *(_OWORD *)Src;
  v14 = *((_OWORD *)Src + 1);
  Src += 32;
  a4[1] = v14;
  if ( Src != a2 )
    goto LABEL_6;
  v15 = a3 - v9;
  memmove_0(a4 + 2, v9, v15);
  return (__int64)v10 + v15;
}

```

## disassembly

```asm
0x140094230  push    rbx
0x140094232  push    rbp
0x140094233  push    rsi
0x140094234  push    rdi
0x140094235  push    r14
0x140094237  push    r15
0x140094239  sub     rsp, 28h
0x14009423d  mov     rbp, r9
0x140094240  mov     r15, r8
0x140094243  mov     rsi, rdx
0x140094246  mov     rbx, rcx
0x140094249  mov     rdi, rdx
0x14009424c  mov     rax, [rsp+58h+arg_20]
0x140094254  lea     r14, [rbp+20h]
0x140094258  mov     rdx, rbx
0x14009425b  mov     rcx, rdi
0x14009425e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094263  test    al, al
0x140094265  jz      short loc_140094296
0x140094267  movups  xmm0, xmmword ptr [rdi]
0x14009426a  movups  xmmword ptr [rbp+0], xmm0
0x14009426e  movups  xmm1, xmmword ptr [rdi+10h]
0x140094272  add     rdi, 20h ; ' '
0x140094276  movups  xmmword ptr [rbp+10h], xmm1
0x14009427a  cmp     rdi, r15
0x14009427d  jnz     short loc_1400942AE
0x14009427f  sub     rsi, rbx
0x140094282  mov     rdx, rbx; Src
0x140094285  mov     r8, rsi; Size
0x140094288  mov     rcx, r14; void *
0x14009428b  call    memmove_0
0x140094290  lea     rax, [rsi+r14]
0x140094294  jmp     short loc_1400942C8
0x140094296  movups  xmm0, xmmword ptr [rbx]
0x140094299  movups  xmmword ptr [rbp+0], xmm0
0x14009429d  movups  xmm1, xmmword ptr [rbx+10h]
0x1400942a1  add     rbx, 20h ; ' '
0x1400942a5  movups  xmmword ptr [rbp+10h], xmm1
0x1400942a9  cmp     rbx, rsi
0x1400942ac  jz      short loc_1400942B3
0x1400942ae  mov     rbp, r14
0x1400942b1  jmp     short loc_14009424C
0x1400942b3  sub     r15, rdi
0x1400942b6  mov     rdx, rdi; Src
0x1400942b9  mov     r8, r15; Size
0x1400942bc  mov     rcx, r14; void *
0x1400942bf  call    memmove_0
0x1400942c4  lea     rax, [r15+r14]
0x1400942c8  add     rsp, 28h
0x1400942cc  pop     r15
0x1400942ce  pop     r14
0x1400942d0  pop     rdi
0x1400942d1  pop     rsi
0x1400942d2  pop     rbp
0x1400942d3  pop     rbx
0x1400942d4  retn
```
