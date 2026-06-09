# Fill_inverse_ushort_ALUT_from_ParameterizedCurveFunc

- ea: `0x18001863c`
- end: `0x1800187b7`
- name: `Fill_inverse_ushort_ALUT_from_ParameterizedCurveFunc`
- size: `379`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006af0`
- `0x18003ce38`

## callees

- `0x18001863c`
- `0x18003e010`

## pseudocode

```c
__int64 __fastcall Fill_inverse_ushort_ALUT_from_ParameterizedCurveFunc(
        __int64 a1,
        __int64 a2,
        double (__fastcall *a3)(__int64, double *),
        double *a4)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  double v8; // xmm0_8
  unsigned int v9; // r8d
  __int64 v10; // r11
  unsigned int v11; // r9d
  int v12; // edi
  int v13; // r10d
  __int64 v14; // rax
  int v15; // edx
  int v16; // r10d
  unsigned int v17; // r8d
  int v18; // r9d
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi

  v6 = a1;
  v7 = 0;
  do
  {
    a1 = (unsigned int)(int)(a3(a1, a4) * 65535.0 + 0.5);
    *(_WORD *)(v6 + 2 * v7) = a1;
    v7 = (unsigned int)(v7 + 16);
  }
  while ( (unsigned int)v7 < 0x3FF );
  v8 = a3(a1, a4);
  v9 = 0;
  *(_WORD *)(v6 + 2046) = (int)(v8 * 65535.0 + 0.5);
  do
  {
    v10 = v9 + 16;
    v11 = 1;
    v12 = *(unsigned __int16 *)(v6 + 2LL * v9);
    v13 = *(unsigned __int16 *)(v6 + 2 * v10) - v12;
    do
    {
      v14 = v11 + v9;
      v15 = v11 * v13;
      ++v11;
      *(_WORD *)(v6 + 2 * v14) = v12 + ((unsigned int)(16 * (v15 + 8)) >> 8);
    }
    while ( v11 < 0x10 );
    v9 += 16;
  }
  while ( (unsigned int)v10 < 0x3F0 );
  v16 = *(unsigned __int16 *)(v6 + 2016);
  v17 = 1;
  v18 = *(unsigned __int16 *)(v6 + 2046) - v16;
  do
  {
    v19 = (v17 * v18) << 8;
    v20 = v17 + 1008;
    ++v17;
    *(_WORD *)(v6 + 2 * v20) = v16 + (((unsigned int)v19 / 0xF + 128) >> 8);
  }
  while ( v17 < 0xF );
  if ( 1.0 / *a4 < 1.0 )
  {
    v21 = 0;
    do
    {
      LODWORD(v19) = (int)(a3(v19, a4) * 65535.0);
      *(_WORD *)(v6 + 2 * v21) = v19;
      v21 = (unsigned int)(v21 + 1);
    }
    while ( (unsigned int)v21 < 0x10 );
  }
  return 0;
}

```

## disassembly

```asm
0x18001863c  push    rbx
0x18001863e  push    rbp
0x18001863f  push    rsi
0x180018640  push    rdi
0x180018641  sub     rsp, 38h
0x180018645  movaps  [rsp+58h+var_38], xmm6
0x18001864a  mov     rsi, r9
0x18001864d  movsd   xmm6, cs:__real@3ff0000000000000
0x180018655  mov     rbp, r8
0x180018658  mov     rbx, rcx
0x18001865b  xor     edi, edi
0x18001865d  xorps   xmm1, xmm1
0x180018660  mov     eax, edi
0x180018662  movaps  xmm0, xmm6
0x180018665  mov     rdx, rsi
0x180018668  cvtsi2sd xmm1, rax
0x18001866d  mov     rax, rbp
0x180018670  mulsd   xmm1, cs:__real@3f50040100401004
0x180018678  minsd   xmm0, xmm1
0x18001867c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018681  mulsd   xmm0, cs:__real@40efffe000000000
0x180018689  addsd   xmm0, cs:__real@3fe0000000000000
0x180018691  cvttsd2si ecx, xmm0
0x180018695  mov     [rbx+rdi*2], cx
0x180018699  add     edi, 10h
0x18001869c  cmp     edi, 3FFh
0x1800186a2  jb      short loc_18001865D
0x1800186a4  mov     rdx, rsi
0x1800186a7  movaps  xmm0, xmm6
0x1800186aa  mov     rax, rbp
0x1800186ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186b2  mulsd   xmm0, cs:__real@40efffe000000000
0x1800186ba  xor     r8d, r8d
0x1800186bd  addsd   xmm0, cs:__real@3fe0000000000000
0x1800186c5  cvttsd2si eax, xmm0
0x1800186c9  mov     [rbx+7FEh], ax
0x1800186d0  mov     eax, r8d
0x1800186d3  lea     r11d, [r8+10h]
0x1800186d7  movzx   r10d, word ptr [rbx+r11*2]
0x1800186dc  mov     r9d, 1
0x1800186e2  movzx   edi, word ptr [rbx+rax*2]
0x1800186e6  sub     r10d, edi
0x1800186e9  lea     eax, [r9+r8]
0x1800186ed  mov     edx, r10d
0x1800186f0  imul    edx, r9d
0x1800186f4  inc     r9d
0x1800186f7  add     edx, 8
0x1800186fa  shl     edx, 4
0x1800186fd  shr     edx, 8
0x180018700  add     dx, di
0x180018703  mov     [rbx+rax*2], dx
0x180018707  cmp     r9d, 10h
0x18001870b  jb      short loc_1800186E9
0x18001870d  mov     r8d, r11d
0x180018710  cmp     r11d, 3F0h
0x180018717  jb      short loc_1800186D0
0x180018719  movzx   r10d, word ptr [rbx+7E0h]
0x180018721  mov     r8d, 1
0x180018727  movzx   r9d, word ptr [rbx+7FEh]
0x18001872f  sub     r9d, r10d
0x180018732  mov     eax, 88888889h
0x180018737  mov     ecx, r9d
0x18001873a  imul    ecx, r8d
0x18001873e  shl     ecx, 8
0x180018741  mul     ecx
0x180018743  lea     eax, [r8+3F0h]
0x18001874a  inc     r8d
0x18001874d  shr     edx, 3
0x180018750  sub     edx, 0FFFFFF80h
0x180018753  shr     edx, 8
0x180018756  add     dx, r10w
0x18001875a  mov     [rbx+rax*2], dx
0x18001875e  cmp     r8d, 0Fh
0x180018762  jb      short loc_180018732
0x180018764  movaps  xmm0, xmm6
0x180018767  divsd   xmm0, qword ptr [rsi]
0x18001876b  comisd  xmm6, xmm0
0x18001876f  jbe     short loc_1800187A7
0x180018771  xor     edi, edi
0x180018773  xorps   xmm0, xmm0
0x180018776  mov     eax, edi
0x180018778  mov     rdx, rsi
0x18001877b  cvtsi2sd xmm0, rax
0x180018780  mov     rax, rbp
0x180018783  mulsd   xmm0, cs:__real@3f50040100401004
0x18001878b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018790  mulsd   xmm0, cs:__real@40efffe000000000
0x180018798  cvttsd2si ecx, xmm0
0x18001879c  mov     [rbx+rdi*2], cx
0x1800187a0  inc     edi
0x1800187a2  cmp     edi, 10h
0x1800187a5  jb      short loc_180018773
0x1800187a7  movaps  xmm6, [rsp+58h+var_38]
0x1800187ac  xor     eax, eax
0x1800187ae  add     rsp, 38h
0x1800187b2  pop     rdi
0x1800187b3  pop     rsi
0x1800187b4  pop     rbp
0x1800187b5  pop     rbx
0x1800187b6  retn
```
