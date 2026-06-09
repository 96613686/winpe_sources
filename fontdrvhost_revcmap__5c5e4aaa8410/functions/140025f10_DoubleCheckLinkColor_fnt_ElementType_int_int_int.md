# DoubleCheckLinkColor(fnt_ElementType *,int,int,int)

- ea: `0x140025f10`
- end: `0x1400260dd`
- name: `?DoubleCheckLinkColor@@YAHPEAUfnt_ElementType@@HHH@Z`
- size: `461`
- prototype: `__int64 __fastcall(struct fnt_ElementType *, int, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d630`
- `0x140025310`

## callees

- `0x140025f10`

## pseudocode

```c
__int64 __fastcall DoubleCheckLinkColor(struct fnt_ElementType *a1, int a2, int a3, unsigned int a4)
{
  int v4; // r10d
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 v9; // rcx
  __int64 v11; // r8
  __int64 v12; // r15
  int v13; // ebp
  int v14; // edx
  int v15; // r14d
  int v16; // ecx
  __int64 v17; // r11
  __int64 v18; // r10
  int v19; // r13d
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // ecx
  bool v23; // sf
  bool v24; // of
  int v25; // ecx
  unsigned __int8 v26; // r12
  bool v27; // zf
  int v28; // edi
  int v29; // eax
  int v30; // esi
  int v31; // edi
  int v32; // ecx
  int v33; // esi
  int v34; // ecx
  int v35; // eax
  int v36; // [rsp+48h] [rbp+8h]

  v4 = *((__int16 *)a1 + 40);
  v5 = 0;
  v6 = a3;
  v7 = a2;
  if ( v4 <= 0 )
  {
LABEL_5:
    if ( (int)v5 >= v4 )
      return 0;
  }
  else
  {
    v9 = *((_QWORD *)a1 + 8);
    while ( a2 > *(__int16 *)(v9 + 2 * v5) )
    {
      v5 = (unsigned int)(v5 + 1);
      if ( (int)v5 >= v4 )
        goto LABEL_5;
    }
  }
  if ( (int)v5 < 0 )
    return 0;
  v11 = 0;
  if ( v4 <= 0 )
  {
LABEL_11:
    if ( (int)v11 >= v4 )
      return 0;
  }
  else
  {
    while ( (int)v6 > *(__int16 *)(*((_QWORD *)a1 + 8) + 2 * v11) )
    {
      v11 = (unsigned int)(v11 + 1);
      if ( (int)v11 >= v4 )
        goto LABEL_11;
    }
  }
  if ( (int)v11 < 0 )
    return 0;
  if ( (_DWORD)v5 != (_DWORD)v11 )
    return a4;
  v12 = (int)v5;
  v13 = *(__int16 *)(*((_QWORD *)a1 + 7) + 2LL * (int)v5);
  v14 = v13;
  v15 = *(__int16 *)(*((_QWORD *)a1 + 8) + 2LL * (int)v5);
  v16 = v15;
  if ( (_DWORD)v7 != v15 )
    v14 = v7 + 1;
  if ( (_DWORD)v7 != v13 )
    v16 = v7 - 1;
  if ( (_DWORD)v6 != v14 && (_DWORD)v6 != v16 )
    return a4;
  v17 = *((_QWORD *)a1 + 4);
  v18 = *((_QWORD *)a1 + 5);
  v19 = *(_DWORD *)(4 * v7 + v17);
  v36 = *(_DWORD *)(4 * v7 + v18);
  v20 = 4LL * v14;
  v21 = (*(_DWORD *)(v20 + v18) - v36) * (v19 - *(_DWORD *)(4LL * v16 + v17));
  v22 = (*(_DWORD *)(v20 + v17) - v19) * (v36 - *(_DWORD *)(4LL * v16 + v18));
  v24 = __OFSUB__(v21, v22);
  v23 = v21 - v22 < 0;
  v25 = *(__int16 *)(*((_QWORD *)a1 + 8) + 2LL * (int)v5);
  v26 = v23 ^ v24;
  if ( (_DWORD)v6 != v13 )
    v25 = v6 - 1;
  v27 = (_DWORD)v6 == v15;
  v28 = *(_DWORD *)(4 * v6 + v17);
  v29 = v6 + 1;
  v30 = *(_DWORD *)(4 * v6 + v18);
  if ( !v27 )
    v13 = v29;
  if ( v26 != (*(_DWORD *)(4LL * v13 + v18) - v30) * (v28 - *(_DWORD *)(4LL * v25 + v17)) < (*(_DWORD *)(4LL * v13 + v17)
                                                                                           - v28)
                                                                                          * (v30
                                                                                           - *(_DWORD *)(4LL * v25 + v18)) )
    return 0;
  v31 = v28 - v19;
  v32 = -v31;
  if ( v31 > 0 )
    v32 = v31;
  v33 = v30 - v36;
  v34 = 2 * v32;
  v35 = -v33;
  if ( v33 > 0 )
    v35 = v33;
  if ( v34 < v35 )
    return 0;
  return (((*(_BYTE *)(v12 + *((_QWORD *)a1 + 11)) & 1) == 0) ^ (unsigned int)v26) + 1;
}

```

## disassembly

```asm
0x140025f10  push    rbx
0x140025f12  push    rbp
0x140025f13  push    rsi
0x140025f14  push    rdi
0x140025f15  push    r12
0x140025f17  push    r13
0x140025f19  push    r14
0x140025f1b  push    r15
0x140025f1d  movsx   r10d, word ptr [rcx+50h]
0x140025f22  xor     eax, eax
0x140025f24  movsxd  rsi, r8d
0x140025f27  mov     r11d, r9d
0x140025f2a  movsxd  rdi, edx
0x140025f2d  mov     rbx, rcx
0x140025f30  test    r10d, r10d
0x140025f33  jle     short loc_140025F48
0x140025f35  mov     rcx, [rcx+40h]
0x140025f39  movsx   edx, word ptr [rcx+rax*2]
0x140025f3d  cmp     edi, edx
0x140025f3f  jle     short loc_140025F5C
0x140025f41  inc     eax
0x140025f43  cmp     eax, r10d
0x140025f46  jl      short loc_140025F39
0x140025f48  cmp     eax, r10d
0x140025f4b  jl      short loc_140025F5C
0x140025f4d  xor     eax, eax
0x140025f4f  pop     r15
0x140025f51  pop     r14
0x140025f53  pop     r13
0x140025f55  pop     r12
0x140025f57  pop     rdi
0x140025f58  pop     rsi
0x140025f59  pop     rbp
0x140025f5a  pop     rbx
0x140025f5b  retn
0x140025f5c  test    eax, eax
0x140025f5e  js      short loc_140025F4D
0x140025f60  xor     r8d, r8d
0x140025f63  test    r10d, r10d
0x140025f66  jle     short loc_140025F7D
0x140025f68  mov     r9, [rbx+40h]
0x140025f6c  movsx   edx, word ptr [r9+r8*2]
0x140025f71  cmp     esi, edx
0x140025f73  jle     short loc_140025F82
0x140025f75  inc     r8d
0x140025f78  cmp     r8d, r10d
0x140025f7b  jl      short loc_140025F6C
0x140025f7d  cmp     r8d, r10d
0x140025f80  jge     short loc_140025F4D
0x140025f82  test    r8d, r8d
0x140025f85  js      short loc_140025F4D
0x140025f87  cmp     eax, r8d
0x140025f8a  jnz     short loc_140025FBF
0x140025f8c  movsxd  r15, eax
0x140025f8f  mov     rax, [rbx+38h]
0x140025f93  movsx   ebp, word ptr [rax+r15*2]
0x140025f98  mov     rax, [rbx+40h]
0x140025f9c  mov     edx, ebp
0x140025f9e  movsx   r14d, word ptr [rax+r15*2]
0x140025fa3  lea     eax, [rdi+1]
0x140025fa6  cmp     edi, r14d
0x140025fa9  mov     ecx, r14d
0x140025fac  cmovnz  edx, eax
0x140025faf  cmp     edi, ebp
0x140025fb1  lea     eax, [rdi-1]
0x140025fb4  cmovnz  ecx, eax
0x140025fb7  cmp     esi, edx
0x140025fb9  jz      short loc_140025FCF
0x140025fbb  cmp     esi, ecx
0x140025fbd  jz      short loc_140025FCF
0x140025fbf  mov     eax, r11d
0x140025fc2  pop     r15
0x140025fc4  pop     r14
0x140025fc6  pop     r13
0x140025fc8  pop     r12
0x140025fca  pop     rdi
0x140025fcb  pop     rsi
0x140025fcc  pop     rbp
0x140025fcd  pop     rbx
0x140025fce  retn
0x140025fcf  mov     r11, [rbx+20h]
0x140025fd3  mov     r10, [rbx+28h]
0x140025fd7  movsxd  rax, ecx
0x140025fda  lea     rcx, ds:0[rdi*4]
0x140025fe2  mov     r13d, [rcx+r11]
0x140025fe6  mov     r8d, r13d
0x140025fe9  mov     ecx, [rcx+r10]
0x140025fed  lea     r9, ds:0[rax*4]
0x140025ff5  mov     [rsp+40h+arg_0], ecx
0x140025ff9  sub     r8d, [r9+r11]
0x140025ffd  movsxd  rax, edx
0x140026000  lea     rdx, ds:0[rax*4]
0x140026008  mov     eax, [rdx+r10]
0x14002600c  sub     eax, ecx
0x14002600e  sub     ecx, [r9+r10]
0x140026012  imul    r8d, eax
0x140026016  mov     eax, [rdx+r11]
0x14002601a  sub     eax, r13d
0x14002601d  imul    ecx, eax
0x140026020  lea     eax, [rsi-1]
0x140026023  cmp     r8d, ecx
0x140026026  mov     ecx, r14d
0x140026029  setl    r12b
0x14002602d  cmp     esi, ebp
0x14002602f  cmovnz  ecx, eax
0x140026032  cmp     esi, r14d
0x140026035  movsxd  rax, ecx
0x140026038  lea     rcx, ds:0[rsi*4]
0x140026040  mov     edi, [rcx+r11]
0x140026044  mov     r8d, edi
0x140026047  lea     r9, ds:0[rax*4]
0x14002604f  lea     eax, [rsi+1]
0x140026052  mov     esi, [rcx+r10]
0x140026056  cmovnz  ebp, eax
0x140026059  mov     ecx, esi
0x14002605b  sub     r8d, [r9+r11]
0x14002605f  sub     ecx, [r9+r10]
0x140026063  movsxd  rax, ebp
0x140026066  lea     rdx, ds:0[rax*4]
0x14002606e  mov     eax, [rdx+r10]
0x140026072  sub     eax, esi
0x140026074  imul    r8d, eax
0x140026078  mov     eax, [rdx+r11]
0x14002607c  sub     eax, edi
0x14002607e  imul    ecx, eax
0x140026081  cmp     r8d, ecx
0x140026084  jge     short loc_1400260D5
0x140026086  mov     al, 1
0x140026088  cmp     r12b, al
0x14002608b  jnz     loc_140025F4D
0x140026091  sub     edi, r13d
0x140026094  mov     ecx, edi
0x140026096  neg     ecx
0x140026098  cmovs   ecx, edi
0x14002609b  sub     esi, [rsp+40h+arg_0]
0x14002609f  add     ecx, ecx
0x1400260a1  mov     eax, esi
0x1400260a3  neg     eax
0x1400260a5  cmovs   eax, esi
0x1400260a8  cmp     ecx, eax
0x1400260aa  jl      loc_140025F4D
0x1400260b0  mov     rax, [rbx+58h]
0x1400260b4  test    byte ptr [r15+rax], 1
0x1400260b9  jnz     short loc_1400260D9
0x1400260bb  mov     cl, 1
0x1400260bd  movzx   eax, r12b
0x1400260c1  movzx   ecx, cl
0x1400260c4  xor     eax, ecx
0x1400260c6  inc     eax
0x1400260c8  pop     r15
0x1400260ca  pop     r14
0x1400260cc  pop     r13
0x1400260ce  pop     r12
0x1400260d0  pop     rdi
0x1400260d1  pop     rsi
0x1400260d2  pop     rbp
0x1400260d3  pop     rbx
0x1400260d4  retn
0x1400260d5  xor     al, al
0x1400260d7  jmp     short loc_140026088
0x1400260d9  xor     cl, cl
0x1400260db  jmp     short loc_1400260BD
```
