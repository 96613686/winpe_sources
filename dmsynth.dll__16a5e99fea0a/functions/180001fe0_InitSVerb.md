# InitSVerb

- ea: `0x180001fe0`
- end: `0x180002111`
- name: `InitSVerb`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f60`
- `0x1800073a0`

## callees

- `0x180002a40`

## pseudocode

```c
__int64 __fastcall InitSVerb(float a1, __int64 a2)
{
  int v3; // r10d
  int v4; // r11d
  int v5; // edx
  int v6; // ecx

  *(_DWORD *)a2 = 148;
  *(_DWORD *)(a2 + 4) = 1;
  *(_DWORD *)(a2 + 52) = 1058944890;
  *(float *)(a2 + 8) = a1;
  v3 = (int)(a1 * 0.045 + 0.5);
  v4 = (int)((float)((float)v3 * 1.1892071) + 0.5);
  v5 = (int)((float)((int)((float)((float)v4 * 1.1892071) + 0.5) + v3) * 0.1154666692018509 + 0.5);
  *(_DWORD *)(a2 + 28) = 4 * (v3 - v5);
  *(_DWORD *)(a2 + 44) = 2 * v5;
  *(_DWORD *)(a2 + 32) = 4 * ((int)((float)((float)v4 * 1.1892071) + 0.5) - v5);
  v6 = (int)((float)((int)((float)((float)(int)((float)((float)v4 * 1.1892071) + 0.5) * 1.1892071) + 0.5) + v4)
           * 0.1154666692018509
           + 0.5);
  *(_DWORD *)(a2 + 36) = 4 * (v4 - v6);
  *(_DWORD *)(a2 + 48) = 2 * v6;
  *(_DWORD *)(a2 + 40) = 4 * ((int)((float)((float)(int)((float)((float)v4 * 1.1892071) + 0.5) * 1.1892071) + 0.5) - v6);
  return SetSVerb(0.0, -10.0, 1000.0, 0.001, a2);
}

```

## disassembly

```asm
0x180001fe0  push    rbx
0x180001fe2  sub     rsp, 30h
0x180001fe6  movsd   xmm3, cs:__real@3fe0000000000000
0x180001fee  xorps   xmm1, xmm1
0x180001ff1  movss   xmm2, cs:__real@3f9837f0
0x180001ff9  mov     rbx, rdx
0x180001ffc  cvtss2sd xmm1, xmm0
0x180002000  mov     dword ptr [rdx], 94h
0x180002006  mov     dword ptr [rdx+4], 1
0x18000200d  mov     dword ptr [rdx+34h], 3F1E377Ah
0x180002014  mov     [rsp+38h+var_18], rbx
0x180002019  movss   dword ptr [rdx+8], xmm0
0x18000201e  mulsd   xmm1, cs:__real@3fa70a3d70a3d70a
0x180002026  addsd   xmm1, xmm3
0x18000202a  cvttsd2si r10d, xmm1
0x18000202f  movd    xmm0, r10d
0x180002034  cvtdq2ps xmm0, xmm0
0x180002037  mulss   xmm0, xmm2
0x18000203b  cvtps2pd xmm0, xmm0
0x18000203e  addsd   xmm0, xmm3
0x180002042  cvttsd2si r11d, xmm0
0x180002047  movd    xmm1, r11d
0x18000204c  cvtdq2ps xmm1, xmm1
0x18000204f  mulss   xmm1, xmm2
0x180002053  cvtps2pd xmm0, xmm1
0x180002056  addsd   xmm0, xmm3
0x18000205a  cvttsd2si r8d, xmm0
0x18000205f  lea     eax, [r8+r10]
0x180002063  movd    xmm1, r8d
0x180002068  cvtdq2ps xmm1, xmm1
0x18000206b  mulss   xmm1, xmm2
0x18000206f  movss   xmm2, cs:__real@447a0000
0x180002077  cvtps2pd xmm0, xmm1
0x18000207a  addsd   xmm0, xmm3
0x18000207e  cvttsd2si r9d, xmm0
0x180002083  movd    xmm0, eax
0x180002087  cvtdq2ps xmm0, xmm0
0x18000208a  lea     eax, [r9+r11]
0x18000208e  cvtps2pd xmm1, xmm0
0x180002091  movd    xmm0, eax
0x180002095  mulsd   xmm1, cs:__real@3fbd8f3940000000
0x18000209d  cvtdq2ps xmm0, xmm0
0x1800020a0  addsd   xmm1, xmm3
0x1800020a4  cvttsd2si edx, xmm1
0x1800020a8  cvtps2pd xmm1, xmm0
0x1800020ab  sub     r10d, edx
0x1800020ae  sub     r8d, edx
0x1800020b1  shl     r10d, 2
0x1800020b5  shl     r8d, 2
0x1800020b9  mov     [rbx+1Ch], r10d
0x1800020bd  lea     eax, [rdx+rdx]
0x1800020c0  mov     [rbx+2Ch], eax
0x1800020c3  xorps   xmm0, xmm0
0x1800020c6  mov     [rbx+20h], r8d
0x1800020ca  mulsd   xmm1, cs:__real@3fbd8f3940000000
0x1800020d2  addsd   xmm1, xmm3
0x1800020d6  movss   xmm3, cs:__real@3a83126f
0x1800020de  cvttsd2si ecx, xmm1
0x1800020e2  movss   xmm1, cs:__real@c1200000
0x1800020ea  sub     r11d, ecx
0x1800020ed  sub     r9d, ecx
0x1800020f0  shl     r11d, 2
0x1800020f4  shl     r9d, 2
0x1800020f8  lea     eax, [rcx+rcx]
0x1800020fb  mov     [rbx+24h], r11d
0x1800020ff  mov     [rbx+30h], eax
0x180002102  mov     [rbx+28h], r9d
0x180002106  call    SetSVerb
0x18000210b  add     rsp, 30h
0x18000210f  pop     rbx
0x180002110  retn
```
