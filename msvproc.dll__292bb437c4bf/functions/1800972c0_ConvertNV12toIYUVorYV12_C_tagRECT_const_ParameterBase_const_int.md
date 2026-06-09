# ConvertNV12toIYUVorYV12_C(tagRECT const &,ParameterBase const *,int)

- ea: `0x1800972c0`
- end: `0x180097461`
- name: `?ConvertNV12toIYUVorYV12_C@@YAJAEBUtagRECT@@PEBUParameterBase@@H@Z`
- size: `417`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800972c0`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x180097399`
- `MFPlat!MFCopyImage` at `0x180097399`

## pseudocode

```c
__int64 __fastcall ConvertNV12toIYUVorYV12_C(const struct tagRECT *a1, const struct ParameterBase *a2, int a3)
{
  LONG v3; // edi
  __int64 v4; // r14
  int v5; // r13d
  __int64 v6; // rbx
  signed int v7; // esi
  signed int v8; // ebp
  signed int v9; // r12d
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // esi
  int v15; // ebp
  int v16; // r10d
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // r11
  __int64 i; // rbx
  int j; // r8d
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v25; // [rsp+80h] [rbp+8h]
  __int64 v26; // [rsp+88h] [rbp+10h]
  signed int v27; // [rsp+90h] [rbp+18h]
  __int64 v28; // [rsp+98h] [rbp+20h]

  v3 = *((_DWORD *)a2 + 2);
  v4 = *((int *)a2 + 6);
  v5 = *((_DWORD *)a2 + 3);
  v6 = *(_QWORD *)a2;
  v7 = a1->left & 0xFFFFFFFE;
  v8 = a1->right & 0xFFFFFFFE;
  v9 = a1->top & 0xFFFFFFFE;
  v25 = *((_QWORD *)a2 + 2);
  v27 = a1->bottom & 0xFFFFFFFE;
  v10 = v3 / 2;
  v11 = *(_QWORD *)a2 + v3 * v5;
  v12 = v11;
  v13 = v11 + (int)v10 * (v5 / 2);
  if ( !a3 )
  {
    v12 = v11 + (int)v10 * (v5 / 2);
    v13 = v6 + v3 * v5;
  }
  v26 = v13;
  v28 = v12;
  if ( !MFCopyImage(
          (BYTE *)(v6 + v7 + (__int64)(v3 * v9)),
          v3,
          (const BYTE *)(v25 + v7 + (__int64)((int)v4 * v9)),
          v4,
          v8 - v7,
          v27 - v9) )
  {
    v14 = v7 / 2;
    v15 = v8 / 2;
    v16 = v9 / 2;
    v17 = (int)v4 * v5 + v25 + (int)v4 * (v9 / 2);
    v18 = (int)v10 * (v9 / 2);
    v19 = v18 + v26;
    for ( i = v18 + v28; v16 < v27 / 2; ++v16 )
    {
      for ( j = v14; j < v15; *(_BYTE *)(v22 + i) = *(_BYTE *)(v23 + v17 + 1) )
      {
        v22 = j;
        v23 = 2 * j++;
        *(_BYTE *)(v22 + v19) = *(_BYTE *)(v23 + v17);
      }
      v19 += v10;
      i += v10;
      v17 += v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800972c0  push    rbx
0x1800972c2  push    rbp
0x1800972c3  push    rsi
0x1800972c4  push    rdi
0x1800972c5  push    r12
0x1800972c7  push    r13
0x1800972c9  push    r14
0x1800972cb  push    r15
0x1800972cd  sub     rsp, 38h
0x1800972d1  mov     rax, [rdx+10h]
0x1800972d5  mov     r9d, 2
0x1800972db  mov     edi, [rdx+8]
0x1800972de  movsxd  r14, dword ptr [rdx+18h]
0x1800972e2  mov     r13d, [rdx+0Ch]
0x1800972e6  mov     rbx, [rdx]
0x1800972e9  mov     esi, [rcx]
0x1800972eb  mov     ebp, [rcx+8]
0x1800972ee  and     esi, 0FFFFFFFEh
0x1800972f1  mov     r12d, [rcx+4]
0x1800972f5  and     ebp, 0FFFFFFFEh
0x1800972f8  mov     r10d, [rcx+0Ch]
0x1800972fc  and     r12d, 0FFFFFFFEh
0x180097300  mov     [rsp+78h+arg_0], rax
0x180097308  and     r10d, 0FFFFFFFEh
0x18009730c  mov     eax, edi
0x18009730e  mov     [rsp+78h+arg_10], r10d
0x180097316  cdq
0x180097317  mov     r11d, r10d
0x18009731a  idiv    r9d
0x18009731d  mov     r10d, ebp
0x180097320  movsxd  r15, eax
0x180097323  mov     eax, r13d
0x180097326  imul    eax, edi
0x180097329  movsxd  rcx, eax
0x18009732c  mov     eax, r13d
0x18009732f  cdq
0x180097330  add     rcx, rbx
0x180097333  idiv    r9d
0x180097336  mov     rdx, rcx
0x180097339  movsxd  r9, esi
0x18009733c  imul    eax, r15d
0x180097340  cdqe
0x180097342  add     rax, rcx
0x180097345  test    r8d, r8d
0x180097348  cmovz   rdx, rax
0x18009734c  cmovz   rax, rcx
0x180097350  mov     [rsp+78h+arg_8], rax
0x180097358  sub     r11d, r12d
0x18009735b  mov     eax, r12d
0x18009735e  mov     [rsp+78h+arg_18], rdx
0x180097366  imul    eax, r14d
0x18009736a  sub     r10d, esi
0x18009736d  mov     [rsp+78h+dwLines], r11d; dwLines
0x180097372  mov     edx, edi; lDestStride
0x180097374  mov     [rsp+78h+dwWidthInBytes], r10d; dwWidthInBytes
0x180097379  movsxd  r8, eax
0x18009737c  mov     eax, r12d
0x18009737f  add     r8, r9
0x180097382  imul    eax, edi
0x180097385  add     r8, [rsp+78h+arg_0]; pSrc
0x18009738d  movsxd  rcx, eax
0x180097390  add     rcx, r9
0x180097393  mov     r9d, r14d; lSrcStride
0x180097396  add     rcx, rbx; pDest
0x180097399  call    cs:__imp_MFCopyImage
0x18009739f  test    eax, eax
0x1800973a1  jnz     loc_18009744E
0x1800973a7  mov     r11, [rsp+78h+arg_8]
0x1800973af  mov     ecx, 2
0x1800973b4  mov     rbx, [rsp+78h+arg_18]
0x1800973bc  mov     eax, esi
0x1800973be  cdq
0x1800973bf  imul    r13d, r14d
0x1800973c3  idiv    ecx
0x1800973c5  mov     esi, eax
0x1800973c7  mov     eax, ebp
0x1800973c9  cdq
0x1800973ca  idiv    ecx
0x1800973cc  mov     ebp, eax
0x1800973ce  mov     eax, r12d
0x1800973d1  cdq
0x1800973d2  idiv    ecx
0x1800973d4  mov     r10d, eax
0x1800973d7  mov     eax, [rsp+78h+arg_10]
0x1800973de  cdq
0x1800973df  idiv    ecx
0x1800973e1  mov     ecx, r10d
0x1800973e4  movsxd  rdx, r13d
0x1800973e7  imul    ecx, r14d
0x1800973eb  mov     r12d, eax
0x1800973ee  movsxd  r9, ecx
0x1800973f1  mov     rcx, [rsp+78h+arg_0]
0x1800973f9  add     rcx, rdx
0x1800973fc  add     r9, rcx
0x1800973ff  mov     ecx, r10d
0x180097402  imul    ecx, r15d
0x180097406  movsxd  rdx, ecx
0x180097409  add     r11, rdx
0x18009740c  add     rbx, rdx
0x18009740f  cmp     r10d, eax
0x180097412  jge     short loc_18009744E
0x180097414  mov     r8d, esi
0x180097417  cmp     esi, ebp
0x180097419  jge     short loc_18009743D
0x18009741b  lea     eax, [r8+r8]
0x18009741f  movsxd  rdx, r8d
0x180097422  movsxd  rcx, eax
0x180097425  inc     r8d
0x180097428  mov     al, [rcx+r9]
0x18009742c  mov     [rdx+r11], al
0x180097430  mov     al, [rcx+r9+1]
0x180097435  mov     [rdx+rbx], al
0x180097438  cmp     r8d, ebp
0x18009743b  jl      short loc_18009741B
0x18009743d  add     r11, r15
0x180097440  add     rbx, r15
0x180097443  add     r9, r14
0x180097446  inc     r10d
0x180097449  cmp     r10d, r12d
0x18009744c  jl      short loc_180097414
0x18009744e  xor     eax, eax
0x180097450  add     rsp, 38h
0x180097454  pop     r15
0x180097456  pop     r14
0x180097458  pop     r13
0x18009745a  pop     r12
0x18009745c  pop     rdi
0x18009745d  pop     rsi
0x18009745e  pop     rbp
0x18009745f  pop     rbx
0x180097460  retn
```
