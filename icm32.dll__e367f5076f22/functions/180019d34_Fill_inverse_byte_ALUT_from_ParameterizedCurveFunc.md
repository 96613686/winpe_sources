# Fill_inverse_byte_ALUT_from_ParameterizedCurveFunc

- ea: `0x180019d34`
- end: `0x180019ea9`
- name: `Fill_inverse_byte_ALUT_from_ParameterizedCurveFunc`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018288`
- `0x180021964`

## callees

- `0x180019d34`
- `0x18003e010`

## pseudocode

```c
__int64 __fastcall Fill_inverse_byte_ALUT_from_ParameterizedCurveFunc(
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
  __int16 v12; // di
  __int16 v13; // r10
  __int64 v14; // rax
  __int16 v15; // dx
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
    a1 = (unsigned int)(int)(a3(a1, a4) * 255.0 + 0.5);
    *(_BYTE *)(v7 + v6) = a1;
    v7 = (unsigned int)(v7 + 16);
  }
  while ( (unsigned int)v7 < 0x3FF );
  v8 = a3(a1, a4);
  v9 = 0;
  *(_BYTE *)(v6 + 1023) = (int)(v8 * 255.0 + 0.5);
  do
  {
    v10 = v9 + 16;
    v11 = 1;
    v12 = *(unsigned __int8 *)(v9 + v6);
    v13 = *(unsigned __int8 *)(v10 + v6) - v12;
    do
    {
      v14 = v11 + v9;
      v15 = v11++ * v13;
      *(_BYTE *)(v14 + v6) = v12 + ((unsigned __int16)(v15 + 8) >> 4);
    }
    while ( v11 < 0x10 );
    v9 += 16;
  }
  while ( (unsigned int)v10 < 0x3F0 );
  v16 = *(unsigned __int8 *)(v6 + 1008);
  v17 = 1;
  v18 = *(unsigned __int8 *)(v6 + 1023) - v16;
  do
  {
    v19 = (v17 * v18) << 8;
    v20 = v17 + 1008;
    ++v17;
    *(_BYTE *)(v20 + v6) = v16 + ((unsigned __int16)((unsigned int)v19 / 0xF + 128) >> 8);
  }
  while ( v17 < 0xF );
  if ( 1.0 / *a4 < 1.0 )
  {
    v21 = 0;
    do
    {
      LODWORD(v19) = (int)(a3(v19, a4) * 255.0);
      *(_BYTE *)(v21 + v6) = v19;
      v21 = (unsigned int)(v21 + 1);
    }
    while ( (unsigned int)v21 < 0x10 );
  }
  return 0;
}

```

## disassembly

```asm
0x180019d34  push    rbx
0x180019d36  push    rbp
0x180019d37  push    rsi
0x180019d38  push    rdi
0x180019d39  sub     rsp, 38h
0x180019d3d  movaps  [rsp+58h+var_38], xmm6
0x180019d42  mov     rsi, r9
0x180019d45  movsd   xmm6, cs:__real@3ff0000000000000
0x180019d4d  mov     rbp, r8
0x180019d50  mov     rbx, rcx
0x180019d53  xor     edi, edi
0x180019d55  xorps   xmm1, xmm1
0x180019d58  mov     eax, edi
0x180019d5a  movaps  xmm0, xmm6
0x180019d5d  mov     rdx, rsi
0x180019d60  cvtsi2sd xmm1, rax
0x180019d65  mov     rax, rbp
0x180019d68  mulsd   xmm1, cs:__real@3f50101010101010
0x180019d70  minsd   xmm0, xmm1
0x180019d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d79  mulsd   xmm0, cs:__real@406fe00000000000
0x180019d81  addsd   xmm0, cs:__real@3fe0000000000000
0x180019d89  cvttsd2si ecx, xmm0
0x180019d8d  mov     [rdi+rbx], cl
0x180019d90  add     edi, 10h
0x180019d93  cmp     edi, 3FFh
0x180019d99  jb      short loc_180019D55
0x180019d9b  mov     rdx, rsi
0x180019d9e  movaps  xmm0, xmm6
0x180019da1  mov     rax, rbp
0x180019da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019da9  mulsd   xmm0, cs:__real@406fe00000000000
0x180019db1  xor     r8d, r8d
0x180019db4  addsd   xmm0, cs:__real@3fe0000000000000
0x180019dbc  cvttsd2si eax, xmm0
0x180019dc0  mov     [rbx+3FFh], al
0x180019dc6  mov     eax, r8d
0x180019dc9  lea     r11d, [r8+10h]
0x180019dcd  movzx   r10d, byte ptr [r11+rbx]
0x180019dd2  mov     r9d, 1
0x180019dd8  movzx   edi, byte ptr [rax+rbx]
0x180019ddc  sub     r10d, edi
0x180019ddf  lea     eax, [r9+r8]
0x180019de3  mov     edx, r10d
0x180019de6  imul    edx, r9d
0x180019dea  inc     r9d
0x180019ded  add     edx, 8
0x180019df0  shl     edx, 4
0x180019df3  shr     edx, 8
0x180019df6  add     dl, dil
0x180019df9  mov     [rax+rbx], dl
0x180019dfc  cmp     r9d, 10h
0x180019e00  jb      short loc_180019DDF
0x180019e02  mov     r8d, r11d
0x180019e05  cmp     r11d, 3F0h
0x180019e0c  jb      short loc_180019DC6
0x180019e0e  movzx   r10d, byte ptr [rbx+3F0h]
0x180019e16  mov     r8d, 1
0x180019e1c  movzx   r9d, byte ptr [rbx+3FFh]
0x180019e24  sub     r9d, r10d
0x180019e27  mov     eax, 88888889h
0x180019e2c  mov     ecx, r9d
0x180019e2f  imul    ecx, r8d
0x180019e33  shl     ecx, 8
0x180019e36  mul     ecx
0x180019e38  lea     eax, [r8+3F0h]
0x180019e3f  inc     r8d
0x180019e42  shr     edx, 3
0x180019e45  sub     edx, 0FFFFFF80h
0x180019e48  shr     edx, 8
0x180019e4b  add     dl, r10b
0x180019e4e  mov     [rax+rbx], dl
0x180019e51  cmp     r8d, 0Fh
0x180019e55  jb      short loc_180019E27
0x180019e57  movaps  xmm0, xmm6
0x180019e5a  divsd   xmm0, qword ptr [rsi]
0x180019e5e  comisd  xmm6, xmm0
0x180019e62  jbe     short loc_180019E99
0x180019e64  xor     edi, edi
0x180019e66  xorps   xmm0, xmm0
0x180019e69  mov     eax, edi
0x180019e6b  mov     rdx, rsi
0x180019e6e  cvtsi2sd xmm0, rax
0x180019e73  mov     rax, rbp
0x180019e76  mulsd   xmm0, cs:__real@3f50101010101010
0x180019e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e83  mulsd   xmm0, cs:__real@406fe00000000000
0x180019e8b  cvttsd2si ecx, xmm0
0x180019e8f  mov     [rdi+rbx], cl
0x180019e92  inc     edi
0x180019e94  cmp     edi, 10h
0x180019e97  jb      short loc_180019E66
0x180019e99  movaps  xmm6, [rsp+58h+var_38]
0x180019e9e  xor     eax, eax
0x180019ea0  add     rsp, 38h
0x180019ea4  pop     rdi
0x180019ea5  pop     rsi
0x180019ea6  pop     rbp
0x180019ea7  pop     rbx
0x180019ea8  retn
```
