# SetSrcRGBtoYVUTable(DIRECTCOLORCONVFRM *)

- ea: `0x180013778`
- end: `0x180013971`
- name: `?SetSrcRGBtoYVUTable@@YAXPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `505`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fe84`
- `0x180019ea4`
- `0x18001f874`

## callees

- `0x180013778`

## pseudocode

```c
void __fastcall SetSrcRGBtoYVUTable(struct DIRECTCOLORCONVFRM *a1)
{
  __int64 v1; // rdx
  int v2; // r8d
  int v3; // eax
  double v4; // xmm3_8
  int v5; // eax
  double v6; // xmm3_8

  v1 = 0;
  v2 = 0;
  if ( *((_DWORD *)a1 + 3636) )
  {
    do
    {
      v5 = v2++;
      v6 = (double)(v5 << 16);
      *((_DWORD *)a1 + v1 + 49) = (int)(v6 * 0.18187);
      *((_DWORD *)a1 + v1 + 817) = (int)(v6 * 0.61183);
      *((_DWORD *)a1 + v1 + 1585) = (int)(v6 * 0.061765 + 1081344.0);
      *((_DWORD *)a1 + v1 + 305) = (int)(v6 * -0.10025);
      *((_DWORD *)a1 + v1 + 1073) = (int)(v6 * -0.33725);
      *((_DWORD *)a1 + v1 + 1841) = (int)(v6 * 0.4375 + 8421376.0);
      *((_DWORD *)a1 + v1 + 561) = (int)(v6 * 0.4375);
      *((_DWORD *)a1 + v1 + 1329) = (int)(v6 * -0.39738);
      *((_DWORD *)a1 + v1++ + 2097) = (int)(8421376.0 - v6 * 0.040116);
    }
    while ( v2 < 256 );
  }
  else
  {
    do
    {
      v3 = v2++;
      v4 = (double)(v3 << 16);
      *((_DWORD *)a1 + v1 + 49) = (int)(v4 * 0.257);
      *((_DWORD *)a1 + v1 + 817) = (int)(v4 * 0.504);
      *((_DWORD *)a1 + v1 + 1585) = (int)(v4 * 0.098 + 1081344.0);
      *((_DWORD *)a1 + v1 + 305) = (int)(v4 * -0.148);
      *((_DWORD *)a1 + v1 + 1073) = (int)(v4 * -0.291);
      *((_DWORD *)a1 + v1 + 1841) = (int)(v4 * 0.439 + 8421376.0);
      *((_DWORD *)a1 + v1 + 561) = (int)(v4 * 0.439);
      *((_DWORD *)a1 + v1 + 1329) = (int)(v4 * -0.368);
      *((_DWORD *)a1 + v1++ + 2097) = (int)(8421376.0 - v4 * 0.07099999999999999);
    }
    while ( v2 < 256 );
  }
}

```

## disassembly

```asm
0x180013778  movsd   xmm4, cs:__real@4160100000000000
0x180013780  xor     edx, edx
0x180013782  mov     r8d, edx
0x180013785  cmp     [rcx+38D0h], edx
0x18001378b  jnz     loc_180013881
0x180013791  mov     eax, r8d
0x180013794  inc     r8d
0x180013797  shl     eax, 10h
0x18001379a  movd    xmm3, eax
0x18001379e  cvtdq2pd xmm3, xmm3
0x1800137a2  movaps  xmm0, xmm3
0x1800137a5  movaps  xmm1, xmm3
0x1800137a8  mulsd   xmm0, cs:__real@3fd072b020c49ba6
0x1800137b0  movaps  xmm2, xmm3
0x1800137b3  mulsd   xmm1, cs:__real@3fe020c49ba5e354
0x1800137bb  mulsd   xmm2, cs:__real@3fdc189374bc6a7f
0x1800137c3  cvttsd2si eax, xmm0
0x1800137c7  movaps  xmm0, xmm3
0x1800137ca  mulsd   xmm0, cs:__real@3fb916872b020c4a
0x1800137d2  mov     [rcx+rdx*4+0C4h], eax
0x1800137d9  cvttsd2si eax, xmm1
0x1800137dd  addsd   xmm0, cs:__real@4130800000000000
0x1800137e5  mov     [rcx+rdx*4+0CC4h], eax
0x1800137ec  movaps  xmm1, xmm3
0x1800137ef  mulsd   xmm1, cs:__real@bfd29fbe76c8b439
0x1800137f7  cvttsd2si eax, xmm0
0x1800137fb  movaps  xmm0, xmm3
0x1800137fe  mulsd   xmm0, cs:__real@bfc2f1a9fbe76c8b
0x180013806  mov     [rcx+rdx*4+18C4h], eax
0x18001380d  cvttsd2si eax, xmm0
0x180013811  movaps  xmm0, xmm2
0x180013814  mov     [rcx+rdx*4+4C4h], eax
0x18001381b  addsd   xmm0, xmm4
0x18001381f  cvttsd2si eax, xmm1
0x180013823  mov     [rcx+rdx*4+10C4h], eax
0x18001382a  cvttsd2si eax, xmm0
0x18001382e  movaps  xmm0, xmm3
0x180013831  mulsd   xmm3, cs:__real@3fb22d0e56041893
0x180013839  mov     [rcx+rdx*4+1CC4h], eax
0x180013840  mulsd   xmm0, cs:__real@bfd78d4fdf3b645a
0x180013848  cvttsd2si eax, xmm2
0x18001384c  mov     [rcx+rdx*4+8C4h], eax
0x180013853  cvttsd2si eax, xmm0
0x180013857  movaps  xmm0, xmm4
0x18001385a  mov     [rcx+rdx*4+14C4h], eax
0x180013861  subsd   xmm0, xmm3
0x180013865  cvttsd2si eax, xmm0
0x180013869  mov     [rcx+rdx*4+20C4h], eax
0x180013870  inc     rdx
0x180013873  cmp     r8d, 100h
0x18001387a  jl      loc_180013791
0x180013880  retn
0x180013881  mov     eax, r8d
0x180013884  inc     r8d
0x180013887  shl     eax, 10h
0x18001388a  movd    xmm3, eax
0x18001388e  cvtdq2pd xmm3, xmm3
0x180013892  movaps  xmm0, xmm3
0x180013895  movaps  xmm1, xmm3
0x180013898  mulsd   xmm0, cs:__real@3fc74784230fcf81
0x1800138a0  movaps  xmm2, xmm3
0x1800138a3  mulsd   xmm1, cs:__real@3fe3941c8216c615
0x1800138ab  mulsd   xmm2, cs:__real@3fdc000000000000
0x1800138b3  cvttsd2si eax, xmm0
0x1800138b7  movaps  xmm0, xmm3
0x1800138ba  mulsd   xmm0, cs:__real@3faf9fa97e132b56
0x1800138c2  mov     [rcx+rdx*4+0C4h], eax
0x1800138c9  cvttsd2si eax, xmm1
0x1800138cd  addsd   xmm0, cs:__real@4130800000000000
0x1800138d5  mov     [rcx+rdx*4+0CC4h], eax
0x1800138dc  movaps  xmm1, xmm3
0x1800138df  mulsd   xmm1, cs:__real@bfd595810624dd2f
0x1800138e7  cvttsd2si eax, xmm0
0x1800138eb  movaps  xmm0, xmm3
0x1800138ee  mulsd   xmm0, cs:__real@bfb9a9fbe76c8b44
0x1800138f6  mov     [rcx+rdx*4+18C4h], eax
0x1800138fd  cvttsd2si eax, xmm0
0x180013901  movaps  xmm0, xmm2
0x180013904  mov     [rcx+rdx*4+4C4h], eax
0x18001390b  addsd   xmm0, xmm4
0x18001390f  cvttsd2si eax, xmm1
0x180013913  mov     [rcx+rdx*4+10C4h], eax
0x18001391a  cvttsd2si eax, xmm0
0x18001391e  movaps  xmm0, xmm3
0x180013921  mulsd   xmm3, cs:__real@3fa48a159817b95a
0x180013929  mov     [rcx+rdx*4+1CC4h], eax
0x180013930  mulsd   xmm0, cs:__real@bfd96eac8605681f
0x180013938  cvttsd2si eax, xmm2
0x18001393c  mov     [rcx+rdx*4+8C4h], eax
0x180013943  cvttsd2si eax, xmm0
0x180013947  movaps  xmm0, xmm4
0x18001394a  mov     [rcx+rdx*4+14C4h], eax
0x180013951  subsd   xmm0, xmm3
0x180013955  cvttsd2si eax, xmm0
0x180013959  mov     [rcx+rdx*4+20C4h], eax
0x180013960  inc     rdx
0x180013963  cmp     r8d, 100h
0x18001396a  jl      loc_180013881
0x180013970  retn
```
