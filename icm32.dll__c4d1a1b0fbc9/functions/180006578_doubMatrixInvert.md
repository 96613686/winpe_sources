# doubMatrixInvert

- ea: `0x180006578`
- end: `0x180006763`
- name: `doubMatrixInvert`
- size: `491`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c70`
- `0x180007fe0`

## callees

- `0x180006578`

## pseudocode

```c
char __fastcall doubMatrixInvert(double *a1, double *a2)
{
  double v2; // xmm4_8
  double v3; // xmm6_8
  double v4; // xmm5_8
  double v5; // xmm8_8
  double v6; // xmm7_8
  double v7; // xmm9_8
  double v8; // xmm10_8
  double v9; // xmm5_8
  double v10; // xmm8_8
  double v11; // xmm11_8
  double v12; // xmm2_8
  char result; // al
  double v14; // xmm3_8
  double v15; // xmm5_8
  double v16; // xmm6_8
  double v17; // xmm1_8
  double v18; // xmm0_8
  double v19; // xmm2_8
  double v20; // xmm0_8
  double v21; // xmm2_8
  double v22; // xmm0_8

  v2 = a1[1] * a1[5];
  v3 = *a1 * a1[4];
  v4 = a1[2];
  v5 = a1[3];
  v6 = v4 * a1[4];
  v7 = a1[8];
  v8 = a1[5] * *a1;
  v9 = v4 * v5;
  v10 = v5 * a1[1];
  v11 = a1[7];
  v12 = v3 * v7 + v2 * a1[6] + v9 * v11 - v6 * a1[6] - v10 * v7 - v8 * v11;
  if ( v12 < 0.000000001 && v12 > -0.000000001 )
    return 0;
  result = 1;
  v14 = 1.0 / v12;
  v15 = (v9 - v8) * (1.0 / v12);
  v16 = (v3 - v10) * (1.0 / v12);
  *a2 = (v7 * a1[4] - v11 * a1[5]) * (1.0 / v12);
  v17 = a1[2] * a1[7];
  v18 = a1[8] * a1[1];
  a2[2] = (v2 - v6) * (1.0 / v12);
  a2[1] = (v17 - v18) * (1.0 / v12);
  a2[3] = (a1[6] * a1[5] - a1[8] * a1[3]) * (1.0 / v12);
  v19 = a1[8] * *a1;
  v20 = a1[6] * a1[2];
  a2[5] = v15;
  a2[4] = (v19 - v20) * v14;
  a2[6] = (a1[3] * a1[7] - a1[6] * a1[4]) * v14;
  v21 = a1[6] * a1[1];
  v22 = *a1 * a1[7];
  a2[8] = v16;
  a2[7] = (v21 - v22) * v14;
  return result;
}

```

## disassembly

```asm
0x180006578  mov     rax, rsp
0x18000657b  sub     rsp, 68h
0x18000657f  movsd   xmm4, qword ptr [rcx+8]
0x180006584  mulsd   xmm4, qword ptr [rcx+28h]
0x180006589  movaps  xmmword ptr [rax-18h], xmm6
0x18000658d  movsd   xmm6, qword ptr [rcx]
0x180006591  mulsd   xmm6, qword ptr [rcx+20h]
0x180006596  movaps  xmmword ptr [rax-28h], xmm7
0x18000659a  movaps  xmm0, xmm4
0x18000659d  mulsd   xmm0, qword ptr [rcx+30h]
0x1800065a2  movsd   xmm7, qword ptr [rcx+10h]
0x1800065a7  movaps  xmm2, xmm6
0x1800065aa  movaps  xmmword ptr [rax-38h], xmm8
0x1800065af  movaps  xmm5, xmm7
0x1800065b2  movsd   xmm8, qword ptr [rcx+18h]
0x1800065b8  mulsd   xmm7, qword ptr [rcx+20h]
0x1800065bd  movaps  xmmword ptr [rax-48h], xmm9
0x1800065c2  movsd   xmm9, qword ptr [rcx+40h]
0x1800065c8  mulsd   xmm2, xmm9
0x1800065cd  movaps  xmmword ptr [rax-58h], xmm10
0x1800065d2  movsd   xmm10, qword ptr [rcx+28h]
0x1800065d8  mulsd   xmm10, qword ptr [rcx]
0x1800065dd  addsd   xmm2, xmm0
0x1800065e1  mulsd   xmm5, xmm8
0x1800065e6  movaps  [rsp+68h+var_68], xmm11
0x1800065eb  movaps  xmm0, xmm7
0x1800065ee  mulsd   xmm8, qword ptr [rcx+8]
0x1800065f4  mulsd   xmm0, qword ptr [rcx+30h]
0x1800065f9  movaps  xmm1, xmm5
0x1800065fc  movsd   xmm11, qword ptr [rcx+38h]
0x180006602  mulsd   xmm1, xmm11
0x180006607  addsd   xmm2, xmm1
0x18000660b  movaps  xmm1, xmm8
0x18000660f  mulsd   xmm1, xmm9
0x180006614  subsd   xmm2, xmm0
0x180006618  movaps  xmm0, xmm10
0x18000661c  mulsd   xmm0, xmm11
0x180006621  subsd   xmm2, xmm1
0x180006625  subsd   xmm2, xmm0
0x180006629  movsd   xmm0, cs:__real@3e112e0be826d695
0x180006631  comisd  xmm0, xmm2
0x180006635  jbe     short loc_180006648
0x180006637  comisd  xmm2, cs:__real@be112e0be826d695
0x18000663f  jbe     short loc_180006648
0x180006641  xor     al, al
0x180006643  jmp     loc_18000673D
0x180006648  mulsd   xmm9, qword ptr [rcx+20h]
0x18000664e  subsd   xmm4, xmm7
0x180006652  mov     al, 1
0x180006654  mulsd   xmm11, qword ptr [rcx+28h]
0x18000665a  subsd   xmm5, xmm10
0x18000665f  movsd   xmm3, cs:__real@3ff0000000000000
0x180006667  subsd   xmm6, xmm8
0x18000666c  divsd   xmm3, xmm2
0x180006670  subsd   xmm9, xmm11
0x180006675  mulsd   xmm4, xmm3
0x180006679  mulsd   xmm5, xmm3
0x18000667d  mulsd   xmm9, xmm3
0x180006682  mulsd   xmm6, xmm3
0x180006686  movsd   qword ptr [rdx], xmm9
0x18000668b  movsd   xmm1, qword ptr [rcx+10h]
0x180006690  mulsd   xmm1, qword ptr [rcx+38h]
0x180006695  movsd   xmm0, qword ptr [rcx+40h]
0x18000669a  mulsd   xmm0, qword ptr [rcx+8]
0x18000669f  movsd   qword ptr [rdx+10h], xmm4
0x1800066a4  subsd   xmm1, xmm0
0x1800066a8  mulsd   xmm1, xmm3
0x1800066ac  movsd   qword ptr [rdx+8], xmm1
0x1800066b1  movsd   xmm1, qword ptr [rcx+30h]
0x1800066b6  mulsd   xmm1, qword ptr [rcx+28h]
0x1800066bb  movsd   xmm0, qword ptr [rcx+40h]
0x1800066c0  mulsd   xmm0, qword ptr [rcx+18h]
0x1800066c5  subsd   xmm1, xmm0
0x1800066c9  mulsd   xmm1, xmm3
0x1800066cd  movsd   qword ptr [rdx+18h], xmm1
0x1800066d2  movsd   xmm2, qword ptr [rcx+40h]
0x1800066d7  mulsd   xmm2, qword ptr [rcx]
0x1800066db  movsd   xmm0, qword ptr [rcx+30h]
0x1800066e0  mulsd   xmm0, qword ptr [rcx+10h]
0x1800066e5  movsd   qword ptr [rdx+28h], xmm5
0x1800066ea  subsd   xmm2, xmm0
0x1800066ee  mulsd   xmm2, xmm3
0x1800066f2  movsd   qword ptr [rdx+20h], xmm2
0x1800066f7  movsd   xmm0, qword ptr [rcx+30h]
0x1800066fc  mulsd   xmm0, qword ptr [rcx+20h]
0x180006701  movsd   xmm1, qword ptr [rcx+18h]
0x180006706  mulsd   xmm1, qword ptr [rcx+38h]
0x18000670b  subsd   xmm1, xmm0
0x18000670f  mulsd   xmm1, xmm3
0x180006713  movsd   qword ptr [rdx+30h], xmm1
0x180006718  movsd   xmm2, qword ptr [rcx+30h]
0x18000671d  mulsd   xmm2, qword ptr [rcx+8]
0x180006722  movsd   xmm0, qword ptr [rcx]
0x180006726  mulsd   xmm0, qword ptr [rcx+38h]
0x18000672b  movsd   qword ptr [rdx+40h], xmm6
0x180006730  subsd   xmm2, xmm0
0x180006734  mulsd   xmm2, xmm3
0x180006738  movsd   qword ptr [rdx+38h], xmm2
0x18000673d  movaps  xmm6, [rsp+68h+var_18]
0x180006742  movaps  xmm7, [rsp+68h+var_28]
0x180006747  movaps  xmm8, [rsp+68h+var_38]
0x18000674d  movaps  xmm9, [rsp+68h+var_48]
0x180006753  movaps  xmm10, [rsp+68h+var_58]
0x180006759  movaps  xmm11, [rsp+68h+var_68]
0x18000675e  add     rsp, 68h
0x180006762  retn
```
