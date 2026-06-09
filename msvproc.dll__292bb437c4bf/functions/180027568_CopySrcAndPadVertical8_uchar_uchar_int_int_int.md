# CopySrcAndPadVertical8(uchar *,uchar *,int,int,int)

- ea: `0x180027568`
- end: `0x18002772f`
- name: `?CopySrcAndPadVertical8@@YAXPEAE0HHH@Z`
- size: `455`
- prototype: `void(unsigned __int8 *Src, unsigned __int8 *, LONG lSrcStride, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a0d0`

## callees

- `0x1800cfecc`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x1800275d1`
- `MFPlat!MFCopyImage` at `0x1800275d1`

## pseudocode

```c
void __fastcall CopySrcAndPadVertical8(
        unsigned __int8 *Src,
        unsigned __int8 *a2,
        LONG lSrcStride,
        DWORD dwLines,
        LONG lSrcStridea)
{
  size_t dwWidthInBytes; // rbx
  BYTE *v9; // rcx
  __int64 v10; // r12
  __int64 v11; // r15
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rbx
  BYTE *v16; // [rsp+30h] [rbp-48h]
  unsigned __int8 *Srca; // [rsp+80h] [rbp+8h]
  size_t Size; // [rsp+88h] [rbp+10h]

  dwWidthInBytes = lSrcStride;
  v9 = &a2[8 * (int)dwWidthInBytes];
  Srca = &Src[lSrcStridea * (dwLines - 1)];
  v16 = &v9[(int)(dwLines * dwWidthInBytes)];
  MFCopyImage(v9, dwWidthInBytes, Src, lSrcStridea, dwWidthInBytes, dwLines);
  Size = dwWidthInBytes;
  memcpy_0(a2, Src, dwWidthInBytes);
  memcpy_0(&a2[dwWidthInBytes], Src, dwWidthInBytes);
  v10 = 2 * (int)dwWidthInBytes;
  memcpy_0(&a2[v10], Src, dwWidthInBytes);
  v11 = 3 * (int)dwWidthInBytes;
  memcpy_0(&a2[v11], Src, dwWidthInBytes);
  v12 = 4 * (int)dwWidthInBytes;
  memcpy_0(&a2[v12], Src, dwWidthInBytes);
  v13 = 5 * (int)dwWidthInBytes;
  memcpy_0(&a2[v13], Src, dwWidthInBytes);
  v14 = 6 * (int)dwWidthInBytes;
  memcpy_0(&a2[v14], Src, dwWidthInBytes);
  v15 = 7 * (int)dwWidthInBytes;
  memcpy_0(&a2[v15], Src, Size);
  memcpy_0(v16, Srca, Size);
  memcpy_0(&v16[Size], Srca, Size);
  memcpy_0(&v16[v10], Srca, Size);
  memcpy_0(&v16[v11], Srca, Size);
  memcpy_0(&v16[v12], Srca, Size);
  memcpy_0(&v16[v13], Srca, Size);
  memcpy_0(&v16[v14], Srca, Size);
  memcpy_0(&v16[v15], Srca, Size);
}

```

## disassembly

```asm
0x180027568  mov     [rsp+arg_10], rbx
0x18002756d  push    rbp
0x18002756e  push    rsi
0x18002756f  push    rdi
0x180027570  push    r12
0x180027572  push    r13
0x180027574  push    r14
0x180027576  push    r15
0x180027578  sub     rsp, 40h
0x18002757c  movsxd  rbx, r8d
0x18002757f  mov     r13, rcx
0x180027582  mov     r11d, r9d
0x180027585  mov     rbp, rdx
0x180027588  mov     [rsp+78h+dwLines], r11d; dwLines
0x18002758d  mov     r8, r13; pSrc
0x180027590  mov     [rsp+78h+dwWidthInBytes], ebx; dwWidthInBytes
0x180027594  lea     eax, ds:0[rbx*8]
0x18002759b  movsxd  rcx, eax
0x18002759e  lea     eax, [r9-1]
0x1800275a2  mov     r9d, [rsp+78h+lSrcStride]; lSrcStride
0x1800275aa  add     rcx, rdx; pDest
0x1800275ad  imul    eax, r9d
0x1800275b1  cdqe
0x1800275b3  add     rax, r13
0x1800275b6  mov     [rsp+78h+Src], rax
0x1800275be  mov     eax, ebx
0x1800275c0  imul    eax, r11d
0x1800275c4  movsxd  rdx, eax
0x1800275c7  add     rdx, rcx
0x1800275ca  mov     [rsp+78h+var_48], rdx
0x1800275cf  mov     edx, ebx; lDestStride
0x1800275d1  call    cs:__imp_MFCopyImage
0x1800275d7  mov     r8, rbx; Size
0x1800275da  mov     [rsp+78h+Size], rbx
0x1800275e2  mov     rdx, r13; Src
0x1800275e5  mov     rcx, rbp; void *
0x1800275e8  call    memcpy_0
0x1800275ed  lea     rcx, [rbx+rbp]; void *
0x1800275f1  mov     r8, rbx; Size
0x1800275f4  mov     rdx, r13; Src
0x1800275f7  call    memcpy_0
0x1800275fc  lea     eax, [rbx+rbx]
0x1800275ff  mov     r8, rbx; Size
0x180027602  movsxd  r12, eax
0x180027605  mov     rdx, r13; Src
0x180027608  lea     rcx, [r12+rbp]; void *
0x18002760c  call    memcpy_0
0x180027611  lea     eax, [rbx+rbx*2]
0x180027614  mov     r8, rbx; Size
0x180027617  movsxd  r15, eax
0x18002761a  mov     rdx, r13; Src
0x18002761d  lea     rcx, [r15+rbp]; void *
0x180027621  call    memcpy_0
0x180027626  lea     eax, ds:0[rbx*4]
0x18002762d  mov     r8, rbx; Size
0x180027630  movsxd  r14, eax
0x180027633  mov     rdx, r13; Src
0x180027636  lea     rcx, [r14+rbp]; void *
0x18002763a  call    memcpy_0
0x18002763f  lea     eax, [rbx+rbx*4]
0x180027642  mov     r8, rbx; Size
0x180027645  movsxd  rsi, eax
0x180027648  mov     rdx, r13; Src
0x18002764b  lea     rcx, [rsi+rbp]; void *
0x18002764f  call    memcpy_0
0x180027654  lea     eax, [rbx+rbx*2]
0x180027657  mov     r8, rbx; Size
0x18002765a  add     eax, eax
0x18002765c  mov     rdx, r13; Src
0x18002765f  movsxd  rdi, eax
0x180027662  lea     rcx, [rdi+rbp]; void *
0x180027666  call    memcpy_0
0x18002766b  imul    eax, ebx, 7
0x18002766e  mov     rdx, r13; Src
0x180027671  movsxd  rbx, eax
0x180027674  lea     rcx, [rbx+rbp]; void *
0x180027678  mov     rbp, [rsp+78h+Size]
0x180027680  mov     r8, rbp; Size
0x180027683  call    memcpy_0
0x180027688  mov     r13, [rsp+78h+var_48]
0x18002768d  mov     r8, rbp; Size
0x180027690  mov     rdx, [rsp+78h+Src]; Src
0x180027698  mov     rcx, r13; void *
0x18002769b  call    memcpy_0
0x1800276a0  mov     rdx, [rsp+78h+Src]; Src
0x1800276a8  mov     rcx, r13
0x1800276ab  add     rcx, rbp; void *
0x1800276ae  mov     r8, rbp; Size
0x1800276b1  call    memcpy_0
0x1800276b6  lea     rcx, [r12+r13]; void *
0x1800276ba  mov     r12, [rsp+78h+Src]
0x1800276c2  mov     r8, rbp; Size
0x1800276c5  mov     rdx, r12; Src
0x1800276c8  call    memcpy_0
0x1800276cd  lea     rcx, [r15+r13]; void *
0x1800276d1  mov     r8, rbp; Size
0x1800276d4  mov     rdx, r12; Src
0x1800276d7  call    memcpy_0
0x1800276dc  lea     rcx, [r14+r13]; void *
0x1800276e0  mov     r8, rbp; Size
0x1800276e3  mov     rdx, r12; Src
0x1800276e6  call    memcpy_0
0x1800276eb  lea     rcx, [rsi+r13]; void *
0x1800276ef  mov     r8, rbp; Size
0x1800276f2  mov     rdx, r12; Src
0x1800276f5  call    memcpy_0
0x1800276fa  lea     rcx, [rdi+r13]; void *
0x1800276fe  mov     r8, rbp; Size
0x180027701  mov     rdx, r12; Src
0x180027704  call    memcpy_0
0x180027709  lea     rcx, [rbx+r13]; void *
0x18002770d  mov     r8, rbp; Size
0x180027710  mov     rdx, r12; Src
0x180027713  mov     rbx, [rsp+78h+arg_10]
0x18002771b  add     rsp, 40h
0x18002771f  pop     r15
0x180027721  pop     r14
0x180027723  pop     r13
0x180027725  pop     r12
0x180027727  pop     rdi
0x180027728  pop     rsi
0x180027729  pop     rbp
0x18002772a  jmp     memcpy_0
```
