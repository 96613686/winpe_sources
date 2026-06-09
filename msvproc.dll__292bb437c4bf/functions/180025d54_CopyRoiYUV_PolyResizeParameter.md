# CopyRoiYUV(PolyResizeParameter *)

- ea: `0x180025d54`
- end: `0x180025edd`
- name: `?CopyRoiYUV@@YAXPEAUPolyResizeParameter@@@Z`
- size: `393`
- prototype: `void __fastcall(struct PolyResizeParameter *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025cf0`

## callees

- `0x180025d54`
- `0x1800cfecc`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180025e75`
- `MFPlat!MFCopyImage` at `0x180025e8f`
- `MFPlat!MFCopyImage` at `0x180025ebf`
- `MFPlat!MFCopyImage` at `0x180025e75`
- `MFPlat!MFCopyImage` at `0x180025e8f`
- `MFPlat!MFCopyImage` at `0x180025ebf`

## pseudocode

```c
void __fastcall CopyRoiYUV(struct PolyResizeParameter *a1)
{
  LONG v1; // edi
  unsigned int v3; // r8d
  const void *v4; // rdx
  void *v5; // r11
  unsigned int v6; // r10d
  LONG v7; // r13d
  unsigned int v8; // ecx
  int v9; // ebx
  unsigned int v10; // r12d
  DWORD dwLines; // esi
  DWORD dwWidthInBytes; // ebp
  LONG v13; // r15d
  const BYTE *v14; // rdi
  BYTE *v15; // rbx
  LONG lSrcStride; // [rsp+70h] [rbp+8h]
  unsigned int v17; // [rsp+78h] [rbp+10h]

  v1 = *((_DWORD *)a1 + 9);
  v3 = *((_DWORD *)a1 + 6);
  v4 = *(const void **)a1;
  v5 = (void *)*((_QWORD *)a1 + 1);
  v6 = *((_DWORD *)a1 + 8);
  v7 = *((_DWORD *)a1 + 15);
  v8 = *((_DWORD *)a1 + 7);
  v9 = *((_DWORD *)a1 + 5);
  v10 = *((_DWORD *)a1 + 14);
  v17 = v6;
  lSrcStride = v1;
  if ( v3 == v1 && v3 == v7 && !v9 && !*((_DWORD *)a1 + 11) && v10 == v8 && v6 == v8 )
  {
    memcpy_0(v5, v4, (unsigned __int64)(3 * v7 * v10) >> 1);
  }
  else
  {
    dwLines = v8 >> 1;
    dwWidthInBytes = v3 >> 1;
    v13 = v1 / 2;
    v14 = (const BYTE *)(v1 / 2 * (v9 >> 1) + *(_QWORD *)a1 + v1 * v6 + ((__int64)*((int *)a1 + 4) >> 1));
    v15 = (BYTE *)(v7 / 2 * (*((int *)a1 + 11) >> 1) + *((_QWORD *)a1 + 1) + v7 * v10 + ((__int64)*((int *)a1 + 10) >> 1));
    MFCopyImage(
      (BYTE *)(*((_QWORD *)a1 + 1) + *((int *)a1 + 10) + (__int64)(v7 * *((_DWORD *)a1 + 11))),
      v7,
      (const BYTE *)(*(_QWORD *)a1 + *((int *)a1 + 4) + (__int64)(lSrcStride * *((_DWORD *)a1 + 5))),
      lSrcStride,
      *((_DWORD *)a1 + 6),
      *((_DWORD *)a1 + 7));
    MFCopyImage(v15, v7 / 2, v14, v13, dwWidthInBytes, dwLines);
    MFCopyImage(&v15[v7 / 2 * (v10 >> 1)], v7 / 2, &v14[v13 * (v17 >> 1)], v13, dwWidthInBytes, dwLines);
  }
}

```

## disassembly

```asm
0x180025d54  mov     [rsp+arg_10], rbx
0x180025d59  push    rbp
0x180025d5a  push    rsi
0x180025d5b  push    rdi
0x180025d5c  push    r12
0x180025d5e  push    r13
0x180025d60  push    r14
0x180025d62  push    r15
0x180025d64  sub     rsp, 30h
0x180025d68  mov     edi, [rcx+24h]
0x180025d6b  mov     r9, rcx
0x180025d6e  mov     r8d, [rcx+18h]
0x180025d72  mov     rdx, [rcx]; Src
0x180025d75  mov     r11, [rcx+8]
0x180025d79  mov     r10d, [r9+20h]
0x180025d7d  mov     r13d, [rcx+3Ch]
0x180025d81  mov     ecx, [rcx+1Ch]
0x180025d84  mov     ebx, [r9+14h]
0x180025d88  mov     r12d, [r9+38h]
0x180025d8c  mov     [rsp+68h+arg_8], r10d
0x180025d91  mov     [rsp+68h+lSrcStride], edi
0x180025d95  cmp     r8d, edi
0x180025d98  jnz     short loc_180025DCB
0x180025d9a  cmp     r8d, r13d
0x180025d9d  jnz     short loc_180025DCB
0x180025d9f  test    ebx, ebx
0x180025da1  jnz     short loc_180025DCB
0x180025da3  cmp     [r9+2Ch], ebx
0x180025da7  jnz     short loc_180025DCB
0x180025da9  cmp     r12d, ecx
0x180025dac  jnz     short loc_180025DCB
0x180025dae  cmp     r10d, ecx
0x180025db1  jnz     short loc_180025DCB
0x180025db3  imul    r12d, r13d
0x180025db7  mov     rcx, r11; void *
0x180025dba  lea     r8d, [r12+r12*2]
0x180025dbe  shr     r8, 1; Size
0x180025dc1  call    memcpy_0
0x180025dc6  jmp     loc_180025EC5
0x180025dcb  mov     esi, ecx
0x180025dcd  mov     eax, edi
0x180025dcf  cdq
0x180025dd0  shr     esi, 1
0x180025dd2  mov     r11d, 2
0x180025dd8  mov     ebp, r8d
0x180025ddb  idiv    r11d
0x180025dde  mov     ecx, ebx
0x180025de0  shr     ebp, 1
0x180025de2  mov     r15d, eax
0x180025de5  sar     ecx, 1
0x180025de7  imul    ecx, r15d
0x180025deb  mov     eax, r13d
0x180025dee  cdq
0x180025def  idiv    r11d
0x180025df2  movsxd  r11, dword ptr [r9+10h]
0x180025df6  mov     edx, r10d
0x180025df9  movsxd  r10, dword ptr [r9+28h]
0x180025dfd  mov     r14d, eax
0x180025e00  mov     eax, [r9+2Ch]
0x180025e04  mov     rbx, r10
0x180025e07  movsxd  r8, ecx
0x180025e0a  mov     ecx, r12d
0x180025e0d  imul    edx, edi
0x180025e10  mov     rdi, r11
0x180025e13  sar     eax, 1
0x180025e15  imul    eax, r14d
0x180025e19  imul    ecx, r13d
0x180025e1d  sar     rdi, 1
0x180025e20  add     rdx, [r9]
0x180025e23  add     rdx, r8
0x180025e26  sar     rbx, 1
0x180025e29  add     rdi, rdx
0x180025e2c  movsxd  rdx, eax
0x180025e2f  add     rcx, [r9+8]
0x180025e33  mov     eax, [r9+14h]
0x180025e37  add     rcx, rdx
0x180025e3a  imul    eax, [rsp+68h+lSrcStride]
0x180025e3f  add     rbx, rcx
0x180025e42  mov     edx, r13d; lDestStride
0x180025e45  movsxd  r8, eax
0x180025e48  mov     eax, [r9+2Ch]
0x180025e4c  add     r8, r11
0x180025e4f  add     r8, [r9]; pSrc
0x180025e52  imul    eax, r13d
0x180025e56  movsxd  rcx, eax
0x180025e59  mov     eax, [r9+1Ch]
0x180025e5d  add     rcx, r10
0x180025e60  add     rcx, [r9+8]; pDest
0x180025e64  mov     [rsp+68h+dwLines], eax; dwLines
0x180025e68  mov     eax, [r9+18h]
0x180025e6c  mov     r9d, [rsp+68h+lSrcStride]; lSrcStride
0x180025e71  mov     [rsp+68h+dwWidthInBytes], eax; dwWidthInBytes
0x180025e75  call    cs:__imp_MFCopyImage
0x180025e7b  mov     r9d, r15d; lSrcStride
0x180025e7e  mov     [rsp+68h+dwLines], esi; dwLines
0x180025e82  mov     r8, rdi; pSrc
0x180025e85  mov     [rsp+68h+dwWidthInBytes], ebp; dwWidthInBytes
0x180025e89  mov     edx, r14d; lDestStride
0x180025e8c  mov     rcx, rbx; pDest
0x180025e8f  call    cs:__imp_MFCopyImage
0x180025e95  mov     r8d, [rsp+68h+arg_8]
0x180025e9a  mov     r9d, r15d; lSrcStride
0x180025e9d  shr     r8d, 1
0x180025ea0  mov     edx, r14d; lDestStride
0x180025ea3  shr     r12d, 1
0x180025ea6  imul    r12d, r14d
0x180025eaa  imul    r8d, r15d
0x180025eae  mov     [rsp+68h+dwLines], esi; dwLines
0x180025eb2  mov     [rsp+68h+dwWidthInBytes], ebp; dwWidthInBytes
0x180025eb6  mov     ecx, r12d
0x180025eb9  add     r8, rdi; pSrc
0x180025ebc  add     rcx, rbx; pDest
0x180025ebf  call    cs:__imp_MFCopyImage
0x180025ec5  mov     rbx, [rsp+68h+arg_10]
0x180025ecd  add     rsp, 30h
0x180025ed1  pop     r15
0x180025ed3  pop     r14
0x180025ed5  pop     r13
0x180025ed7  pop     r12
0x180025ed9  pop     rdi
0x180025eda  pop     rsi
0x180025edb  pop     rbp
0x180025edc  retn
```
