# CMSPolyPhaseResizer::ConvertNV12ToPlannar_MT(int,int,PolyResizeParameter const *)

- ea: `0x18000486c`
- end: `0x180004988`
- name: `?ConvertNV12ToPlannar_MT@CMSPolyPhaseResizer@@AEAAXHHPEBUPolyResizeParameter@@@Z`
- size: `284`
- prototype: `void __fastcall(CMSPolyPhaseResizer *__hidden this, int, int, const struct PolyResizeParameter *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004760`

## callees

- `0x180004e10`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180004927`
- `MFPlat!MFCopyImage` at `0x180004927`

## pseudocode

```c
void __fastcall CMSPolyPhaseResizer::ConvertNV12ToPlannar_MT(
        CMSPolyPhaseResizer *this,
        int a2,
        int a3,
        const struct PolyResizeParameter *a4)
{
  __int64 v5; // r11
  int v6; // eax
  unsigned int v7; // r15d
  unsigned __int64 v8; // rsi
  int v9; // r12d
  __int64 v10; // r14
  __int64 v11; // rbx
  LONG lSrcStride; // [rsp+88h] [rbp+10h]

  v5 = *((int *)a4 + 4);
  v6 = a2 + *((_DWORD *)a4 + 5);
  v7 = *((_DWORD *)this + 102);
  v8 = (unsigned int)(*((_DWORD *)this + 103) * *((_DWORD *)this + 102));
  lSrcStride = *((_DWORD *)a4 + 9);
  v9 = a2 >> 1;
  v10 = *(_QWORD *)a4 + v5 + lSrcStride * (v6 >> 1) + (unsigned int)(*((_DWORD *)a4 + 8) * lSrcStride);
  v11 = *((_QWORD *)this + 5) + v8 + (int)((v7 >> 1) * (a2 >> 1));
  MFCopyImage(
    (BYTE *)(*((_QWORD *)this + 5) + a2 * v7),
    *((_DWORD *)this + 102),
    (const BYTE *)(*(_QWORD *)a4 + v5 + lSrcStride * v6),
    lSrcStride,
    *((_DWORD *)this + 102),
    a3 - a2);
  UnpackUVToPlannar_SSE2(v10, v11, v11 + (v8 >> 2), *((_DWORD *)this + 102) >> 1, (a3 >> 1) - v9, lSrcStride, v7 >> 1);
}

```

## disassembly

```asm
0x18000486c  mov     [rsp+arg_18], rbx
0x180004871  mov     [rsp+arg_10], r8d
0x180004876  push    rbp
0x180004877  push    rsi
0x180004878  push    rdi
0x180004879  push    r12
0x18000487b  push    r13
0x18000487d  push    r14
0x18000487f  push    r15
0x180004881  sub     rsp, 40h
0x180004885  mov     r8d, [r9+14h]
0x180004889  mov     r13, rcx
0x18000488c  mov     ecx, [r9+24h]
0x180004890  add     r8d, edx
0x180004893  movsxd  r11, dword ptr [r9+10h]
0x180004897  mov     eax, r8d
0x18000489a  mov     rdi, [r9]
0x18000489d  mov     r14d, ecx
0x1800048a0  imul    r14d, [r9+20h]
0x1800048a5  mov     r12d, edx
0x1800048a8  mov     r15d, [r13+198h]
0x1800048af  mov     ebx, r15d
0x1800048b2  mov     r9d, [rsp+78h+arg_10]
0x1800048ba  mov     esi, r15d
0x1800048bd  imul    esi, [r13+19Ch]
0x1800048c5  sub     r9d, edx
0x1800048c8  imul    r8d, ecx
0x1800048cc  sar     eax, 1
0x1800048ce  imul    eax, ecx
0x1800048d1  shr     ebx, 1
0x1800048d3  mov     [rsp+78h+lSrcStride], ecx
0x1800048da  mov     ecx, r15d
0x1800048dd  imul    ecx, edx
0x1800048e0  mov     edx, r15d; lDestStride
0x1800048e3  mov     [rsp+78h+arg_0], ebx
0x1800048ea  cdqe
0x1800048ec  add     rax, r11
0x1800048ef  movsxd  r8, r8d
0x1800048f2  add     r14, rax
0x1800048f5  mov     [rsp+78h+dwLines], r9d; dwLines
0x1800048fa  add     rcx, [r13+28h]; pDest
0x1800048fe  add     r8, r11
0x180004901  mov     r9d, [rsp+78h+lSrcStride]; lSrcStride
0x180004909  add     r8, rdi; pSrc
0x18000490c  sar     r12d, 1
0x18000490f  add     r14, rdi
0x180004912  mov     eax, r12d
0x180004915  mov     [rsp+78h+dwWidthInBytes], r15d; dwWidthInBytes
0x18000491a  imul    eax, ebx
0x18000491d  movsxd  rbx, eax
0x180004920  add     rbx, rsi
0x180004923  add     rbx, [r13+28h]
0x180004927  call    cs:__imp_MFCopyImage
0x18000492d  mov     eax, [rsp+78h+arg_0]
0x180004934  mov     rdx, rbx
0x180004937  mov     ecx, [rsp+78h+arg_10]
0x18000493e  mov     r9d, [r13+198h]
0x180004945  mov     [rsp+78h+var_48], eax
0x180004949  mov     eax, [rsp+78h+lSrcStride]
0x180004950  sar     ecx, 1
0x180004952  sub     ecx, r12d
0x180004955  shr     rsi, 2
0x180004959  mov     [rsp+78h+dwLines], eax
0x18000495d  mov     [rsp+78h+dwWidthInBytes], ecx
0x180004961  mov     rcx, r14
0x180004964  shr     r9d, 1
0x180004967  lea     r8, [rbx+rsi]
0x18000496b  call    UnpackUVToPlannar_SSE2
0x180004970  mov     rbx, [rsp+78h+arg_18]
0x180004978  add     rsp, 40h
0x18000497c  pop     r15
0x18000497e  pop     r14
0x180004980  pop     r13
0x180004982  pop     r12
0x180004984  pop     rdi
0x180004985  pop     rsi
0x180004986  pop     rbp
0x180004987  retn
```
