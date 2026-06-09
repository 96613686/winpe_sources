# ConvertIYUVorYV12toNV12(tagRECT const &,ParameterBase const *,int)

- ea: `0x180096610`
- end: `0x18009679e`
- name: `?ConvertIYUVorYV12toNV12@@YAJAEBUtagRECT@@PEBUParameterBase@@H@Z`
- size: `398`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180096a00`
- `0x180099b70`

## callees

- `0x180096610`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x1800966df`
- `MFPlat!MFCopyImage` at `0x1800966df`

## pseudocode

```c
__int64 __fastcall ConvertIYUVorYV12toNV12(const struct tagRECT *a1, const struct ParameterBase *a2, int a3)
{
  LONG v3; // r9d
  __int64 v4; // rbx
  int v5; // r12d
  __int64 v6; // r14
  signed int v7; // esi
  signed int v8; // ebp
  signed int v9; // r15d
  signed int v10; // r13d
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // esi
  int v16; // ebp
  int v17; // r10d
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r11
  __int64 i; // rbx
  int j; // r8d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v26; // [rsp+70h] [rbp+8h]
  __int64 v27; // [rsp+78h] [rbp+10h]
  __int64 v28; // [rsp+88h] [rbp+20h]

  v3 = *((_DWORD *)a2 + 6);
  v4 = *((_QWORD *)a2 + 2);
  v5 = *((_DWORD *)a2 + 3);
  v6 = *((int *)a2 + 2);
  v7 = a1->left & 0xFFFFFFFE;
  v8 = a1->right & 0xFFFFFFFE;
  v9 = a1->top & 0xFFFFFFFE;
  v26 = *(_QWORD *)a2;
  v10 = a1->bottom & 0xFFFFFFFE;
  v11 = v3 / 2;
  v12 = v4 + v3 * v5;
  v13 = v12;
  v14 = v12 + (int)v11 * (v5 / 2);
  if ( !a3 )
  {
    v13 = v12 + (int)v11 * (v5 / 2);
    v14 = v4 + v3 * v5;
  }
  v27 = v14;
  v28 = v13;
  if ( !MFCopyImage(
          (BYTE *)(v26 + v7 + (__int64)((int)v6 * v9)),
          v6,
          (const BYTE *)(v4 + v7 + (__int64)(v3 * v9)),
          v3,
          v8 - v7,
          v10 - v9) )
  {
    v15 = v7 / 2;
    v16 = v8 / 2;
    v17 = v9 / 2;
    v18 = v26 + (int)v6 * (v9 / 2) + (int)v6 * v5;
    v19 = (int)v11 * (v9 / 2);
    v20 = v19 + v27;
    for ( i = v19 + v28; v17 < v10 / 2; ++v17 )
    {
      for ( j = v15; j < v16; *(_BYTE *)(v24 + v18 + 1) = *(_BYTE *)(v23 + i) )
      {
        v23 = j;
        v24 = 2 * j++;
        *(_BYTE *)(v24 + v18) = *(_BYTE *)(v23 + v20);
      }
      v20 += v11;
      i += v11;
      v18 += v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180096610  mov     [rsp+arg_10], rbx
0x180096615  push    rbp
0x180096616  push    rsi
0x180096617  push    rdi
0x180096618  push    r12
0x18009661a  push    r13
0x18009661c  push    r14
0x18009661e  push    r15
0x180096620  sub     rsp, 30h
0x180096624  mov     rax, [rdx]
0x180096627  mov     r10d, 2
0x18009662d  mov     r9d, [rdx+18h]; lSrcStride
0x180096631  mov     rbx, [rdx+10h]
0x180096635  mov     r12d, [rdx+0Ch]
0x180096639  movsxd  r14, dword ptr [rdx+8]
0x18009663d  mov     esi, [rcx]
0x18009663f  mov     ebp, [rcx+8]
0x180096642  and     esi, 0FFFFFFFEh
0x180096645  mov     r15d, [rcx+4]
0x180096649  and     ebp, 0FFFFFFFEh
0x18009664c  mov     r13d, [rcx+0Ch]
0x180096650  and     r15d, 0FFFFFFFEh
0x180096654  mov     [rsp+68h+arg_0], rax
0x180096659  and     r13d, 0FFFFFFFEh
0x18009665d  mov     eax, r9d
0x180096660  mov     r11d, r13d
0x180096663  cdq
0x180096664  idiv    r10d
0x180096667  movsxd  rdi, eax
0x18009666a  mov     eax, r12d
0x18009666d  imul    eax, r9d
0x180096671  movsxd  rcx, eax
0x180096674  mov     eax, r12d
0x180096677  cdq
0x180096678  add     rcx, rbx
0x18009667b  idiv    r10d
0x18009667e  mov     rdx, rcx
0x180096681  mov     r10d, ebp
0x180096684  imul    eax, edi
0x180096687  cdqe
0x180096689  add     rax, rcx
0x18009668c  test    r8d, r8d
0x18009668f  cmovz   rdx, rax
0x180096693  cmovz   rax, rcx
0x180096697  mov     [rsp+68h+arg_8], rax
0x18009669c  sub     r11d, r15d
0x18009669f  mov     [rsp+68h+arg_18], rdx
0x1800966a7  mov     eax, r15d
0x1800966aa  imul    eax, r9d
0x1800966ae  sub     r10d, esi
0x1800966b1  movsxd  rdx, esi
0x1800966b4  mov     [rsp+68h+dwLines], r11d; dwLines
0x1800966b9  mov     [rsp+68h+dwWidthInBytes], r10d; dwWidthInBytes
0x1800966be  movsxd  r8, eax
0x1800966c1  mov     eax, r15d
0x1800966c4  add     r8, rdx
0x1800966c7  imul    eax, r14d
0x1800966cb  add     r8, rbx; pSrc
0x1800966ce  mov     rbx, [rsp+68h+arg_0]
0x1800966d3  movsxd  rcx, eax
0x1800966d6  add     rcx, rdx
0x1800966d9  mov     edx, r14d; lDestStride
0x1800966dc  add     rcx, rbx; pDest
0x1800966df  call    cs:__imp_MFCopyImage
0x1800966e5  test    eax, eax
0x1800966e7  jnz     loc_180096784
0x1800966ed  mov     r11, [rsp+68h+arg_8]
0x1800966f2  mov     ecx, 2
0x1800966f7  mov     eax, esi
0x1800966f9  imul    r12d, r14d
0x1800966fd  cdq
0x1800966fe  idiv    ecx
0x180096700  movsxd  r9, r12d
0x180096703  mov     esi, eax
0x180096705  mov     eax, ebp
0x180096707  cdq
0x180096708  idiv    ecx
0x18009670a  mov     ebp, eax
0x18009670c  mov     eax, r15d
0x18009670f  cdq
0x180096710  idiv    ecx
0x180096712  mov     r10d, eax
0x180096715  mov     eax, r13d
0x180096718  cdq
0x180096719  idiv    ecx
0x18009671b  mov     ecx, r10d
0x18009671e  imul    ecx, r14d
0x180096722  mov     r15d, eax
0x180096725  movsxd  rcx, ecx
0x180096728  add     rcx, rbx
0x18009672b  mov     rbx, [rsp+68h+arg_18]
0x180096733  add     r9, rcx
0x180096736  mov     ecx, r10d
0x180096739  imul    ecx, edi
0x18009673c  movsxd  rdx, ecx
0x18009673f  add     r11, rdx
0x180096742  add     rbx, rdx
0x180096745  cmp     r10d, eax
0x180096748  jge     short loc_180096784
0x18009674a  mov     r8d, esi
0x18009674d  cmp     esi, ebp
0x18009674f  jge     short loc_180096773
0x180096751  movsxd  rdx, r8d
0x180096754  lea     eax, [r8+r8]
0x180096758  movsxd  rcx, eax
0x18009675b  inc     r8d
0x18009675e  mov     al, [rdx+r11]
0x180096762  mov     [rcx+r9], al
0x180096766  mov     al, [rdx+rbx]
0x180096769  mov     [rcx+r9+1], al
0x18009676e  cmp     r8d, ebp
0x180096771  jl      short loc_180096751
0x180096773  add     r11, rdi
0x180096776  add     rbx, rdi
0x180096779  add     r9, r14
0x18009677c  inc     r10d
0x18009677f  cmp     r10d, r15d
0x180096782  jl      short loc_18009674A
0x180096784  mov     rbx, [rsp+68h+arg_10]
0x18009678c  xor     eax, eax
0x18009678e  add     rsp, 30h
0x180096792  pop     r15
0x180096794  pop     r14
0x180096796  pop     r13
0x180096798  pop     r12
0x18009679a  pop     rdi
0x18009679b  pop     rsi
0x18009679c  pop     rbp
0x18009679d  retn
```
