# CMSPolyPhaseResizer::ConvertPlannarToNV12_MT(int,int,PolyResizeParameter const *)

- ea: `0x1800133b4`
- end: `0x1800134d5`
- name: `?ConvertPlannarToNV12_MT@CMSPolyPhaseResizer@@AEAAXHHPEBUPolyResizeParameter@@@Z`
- size: `289`
- prototype: `void __fastcall(CMSPolyPhaseResizer *__hidden this, int, int, const struct PolyResizeParameter *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012ec0`

## callees

- `0x1800134e0`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180013475`
- `MFPlat!MFCopyImage` at `0x180013475`

## pseudocode

```c
void __fastcall CMSPolyPhaseResizer::ConvertPlannarToNV12_MT(
        CMSPolyPhaseResizer *this,
        int a2,
        int a3,
        const struct PolyResizeParameter *a4)
{
  DWORD v4; // r14d
  __int64 v5; // rbx
  __int64 v6; // rdi
  int v7; // r10d
  int v8; // r12d
  int v9; // r15d
  int v10; // r13d
  const BYTE *v11; // r8
  __int64 v12; // rsi
  DWORD dwLines; // [rsp+28h] [rbp-60h]

  v4 = *((_DWORD *)this + 105);
  v5 = *((int *)a4 + 10);
  v6 = *((_QWORD *)this + 6);
  v7 = a2 + *((_DWORD *)a4 + 11);
  v8 = *((_DWORD *)this + 106);
  v9 = a2 >> 1;
  v10 = v6 + v4 * v8 + (v4 >> 1) * (a2 >> 1);
  dwLines = a3 - a2;
  v11 = (const BYTE *)(v6 + a2 * v4);
  LODWORD(v6) = *((_DWORD *)a4 + 15);
  v12 = v5 + *((_QWORD *)a4 + 1) + (int)v6 * (v7 >> 1) + (unsigned int)(*((_DWORD *)a4 + 14) * v6);
  MFCopyImage((BYTE *)(v5 + *((_QWORD *)a4 + 1) + (int)v6 * v7), v6, v11, v4, v4, dwLines);
  PackPlannarToUV_SSE2(
    v10,
    v10 + (((v4 >> 1) * v8) >> 1),
    v12,
    *((_DWORD *)this + 105) >> 1,
    (a3 >> 1) - v9,
    v4 >> 1,
    v6);
}

```

## disassembly

```asm
0x1800133b4  mov     r11, rsp
0x1800133b7  mov     [r11+18h], r8d
0x1800133bb  mov     [r11+8], rcx
0x1800133bf  push    rbx
0x1800133c0  push    rbp
0x1800133c1  push    rsi
0x1800133c2  push    rdi
0x1800133c3  push    r12
0x1800133c5  push    r13
0x1800133c7  push    r14
0x1800133c9  push    r15
0x1800133cb  sub     rsp, 48h
0x1800133cf  mov     r14d, [rcx+1A4h]
0x1800133d6  mov     rax, rcx
0x1800133d9  mov     r8d, [r9+3Ch]
0x1800133dd  mov     ebp, edx
0x1800133df  movsxd  rbx, dword ptr [r9+28h]
0x1800133e3  mov     r15d, edx
0x1800133e6  mov     r10d, [r9+2Ch]
0x1800133ea  mov     esi, r8d
0x1800133ed  mov     rdi, [rax+30h]
0x1800133f1  add     r10d, ebp
0x1800133f4  mov     r12d, [rax+1A8h]
0x1800133fb  mov     ecx, r14d
0x1800133fe  imul    esi, [r9+38h]
0x180013403  mov     edx, r12d
0x180013406  shr     ecx, 1
0x180013408  imul    edx, r14d
0x18001340c  mov     [rsp+88h+lDestStride], r8d
0x180013414  mov     [rsp+88h+arg_18], ecx
0x18001341b  sar     r15d, 1
0x18001341e  mov     eax, r15d
0x180013421  imul    eax, ecx
0x180013424  movsxd  r13, eax
0x180013427  lea     rax, [rdi+rdx]
0x18001342b  mov     edx, [r11+18h]
0x18001342f  add     r13, rax
0x180013432  mov     eax, r10d
0x180013435  sub     edx, ebp
0x180013437  sar     eax, 1
0x180013439  imul    eax, r8d
0x18001343d  mov     r8d, r14d
0x180013440  mov     [rsp+88h+dwLines], edx; dwLines
0x180013444  imul    r8d, ebp
0x180013448  mov     [r11-68h], r14d
0x18001344c  cdqe
0x18001344e  add     rax, [r9+8]
0x180013452  add     r8, rdi; pSrc
0x180013455  add     rsi, rax
0x180013458  mov     edi, [rsp+88h+lDestStride]
0x18001345f  add     rsi, rbx
0x180013462  imul    r10d, edi
0x180013466  mov     edx, edi; lDestStride
0x180013468  movsxd  rcx, r10d
0x18001346b  add     rcx, [r9+8]
0x18001346f  mov     r9d, r14d; lSrcStride
0x180013472  add     rcx, rbx; pDest
0x180013475  call    cs:__imp_MFCopyImage
0x18001347b  mov     eax, [rsp+88h+arg_18]
0x180013482  mov     r8, rsi
0x180013485  mov     ecx, [rsp+88h+arg_10]
0x18001348c  mov     r9, [rsp+88h+arg_0]
0x180013494  sar     ecx, 1
0x180013496  sub     ecx, r15d
0x180013499  imul    r12d, eax
0x18001349d  mov     [rsp+88h+var_58], edi
0x1800134a1  mov     r9d, [r9+1A4h]
0x1800134a8  mov     [rsp+88h+dwLines], eax
0x1800134ac  mov     [rsp+88h+var_68], ecx
0x1800134b0  mov     rcx, r13
0x1800134b3  mov     edx, r12d
0x1800134b6  shr     rdx, 1
0x1800134b9  add     rdx, r13
0x1800134bc  shr     r9d, 1
0x1800134bf  call    PackPlannarToUV_SSE2
0x1800134c4  add     rsp, 48h
0x1800134c8  pop     r15
0x1800134ca  pop     r14
0x1800134cc  pop     r13
0x1800134ce  pop     r12
0x1800134d0  pop     rdi
0x1800134d1  pop     rsi
0x1800134d2  pop     rbp
0x1800134d3  pop     rbx
0x1800134d4  retn
```
