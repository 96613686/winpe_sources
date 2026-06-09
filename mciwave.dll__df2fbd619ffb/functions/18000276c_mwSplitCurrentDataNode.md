# mwSplitCurrentDataNode

- ea: `0x18000276c`
- end: `0x18000290d`
- name: `mwSplitCurrentDataNode`
- size: `417`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001fa4`
- `0x180002150`

## callees

- `0x180001424`
- `0x180001db8`
- `0x18000276c`
- `0x180003e60`

## pseudocode

```c
__int64 __fastcall mwSplitCurrentDataNode(__int64 a1, unsigned int a2)
{
  int v3; // ebp
  int v4; // edi
  int *v5; // r14
  int v6; // r15d
  unsigned int AnyFreeDataNode; // eax
  unsigned int v8; // esi
  __int64 result; // rax
  __int64 v10; // r8
  int v11; // ebp
  _DWORD *v12; // rdi
  int v13; // edx
  __int64 i; // rcx
  int v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // r12
  unsigned int v18; // ecx
  unsigned int v19; // edx
  int v20; // r15d
  unsigned int v21; // r13d
  __int64 v22; // rdx
  SIZE_T dwBytes; // [rsp+28h] [rbp-50h]
  unsigned int AnyFreeBlockNode; // [rsp+80h] [rbp+8h]

  v3 = *(_DWORD *)(a1 + 64);
  v4 = *(_DWORD *)(a1 + 124);
  v5 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * *(unsigned int *)(a1 + 120));
  if ( *v5 >= 0 )
  {
    v6 = 0;
  }
  else
  {
    a2 += *(_DWORD *)(a1 + 148);
    v6 = 1;
  }
  AnyFreeDataNode = mwFindAnyFreeDataNode(a1, a2);
  v8 = AnyFreeDataNode;
  if ( AnyFreeDataNode == -1 )
    return 0xFFFFFFFFLL;
  v10 = *(_QWORD *)(a1 + 104);
  v11 = v3 - v4;
  v12 = (_DWORD *)(v10 + 16LL * AnyFreeDataNode);
  if ( v11 )
  {
    if ( v11 == v5[1] )
    {
      v12[3] = v5[3];
      v15 = v5[1];
      v5[3] = v8;
      *(_DWORD *)(a1 + 124) += v15;
    }
    else
    {
      AnyFreeBlockNode = mwFindAnyFreeBlockNode(a1);
      v16 = AnyFreeBlockNode;
      if ( AnyFreeBlockNode == -1 )
      {
        v12[1] = -1;
        return 0xFFFFFFFFLL;
      }
      v17 = *(_QWORD *)(a1 + 104);
      if ( v6 )
      {
        v18 = *(_DWORD *)(a1 + 148);
        v19 = (v11 + v18 - 1) % v18;
        v20 = v11 + v18 - 1 - v19;
        if ( v20 != v11 )
        {
          v21 = v18 - 1 - v19;
          LODWORD(dwBytes) = v21;
          if ( !(unsigned int)CopyBlockData(a1, v5, v12, v11, 0, dwBytes) )
          {
            result = 0xFFFFFFFFLL;
            v12[1] = -1;
            return result;
          }
          v16 = AnyFreeBlockNode;
          v12[1] = v21;
        }
      }
      else
      {
        v20 = v11;
      }
      v22 = 2LL * v16;
      *(_DWORD *)(v17 + 8 * v22 + 12) = v5[3];
      *(_DWORD *)(v17 + 8 * v22) = v20 + *v5;
      *(_DWORD *)(v17 + 8 * v22 + 4) = v5[1] - v20;
      *(_DWORD *)(v17 + 8 * v22 + 8) = v5[2] - v20;
      v12[3] = v16;
      v5[1] = v11;
      v5[2] = v20;
      v5[3] = v8;
      *(_DWORD *)(a1 + 124) += v11;
    }
  }
  else
  {
    v13 = *(_DWORD *)(a1 + 120);
    if ( v13 == *(_DWORD *)(a1 + 116) )
    {
      *(_DWORD *)(a1 + 116) = AnyFreeDataNode;
    }
    else
    {
      for ( i = v10 + 16LL * *(unsigned int *)(a1 + 116);
            *(_DWORD *)(i + 12) != v13;
            i = v10 + 16LL * *(unsigned int *)(i + 12) )
      {
        ;
      }
      *(_DWORD *)(i + 12) = AnyFreeDataNode;
    }
    v12[3] = *(_DWORD *)(a1 + 120);
  }
  *(_DWORD *)(a1 + 120) = v8;
  return v8;
}

```

## disassembly

```asm
0x18000276c  push    rbx
0x18000276e  push    rbp
0x18000276f  push    rsi
0x180002770  push    rdi
0x180002771  push    r12
0x180002773  push    r13
0x180002775  push    r14
0x180002777  push    r15
0x180002779  sub     rsp, 38h
0x18000277d  mov     r14d, [rcx+78h]
0x180002781  mov     rbx, rcx
0x180002784  mov     ebp, [rcx+40h]
0x180002787  mov     edi, [rcx+7Ch]
0x18000278a  shl     r14, 4
0x18000278e  add     r14, [rcx+68h]
0x180002792  cmp     dword ptr [r14], 0
0x180002796  jge     short loc_1800027A6
0x180002798  add     edx, [rcx+94h]
0x18000279e  mov     r15d, 1
0x1800027a4  jmp     short loc_1800027A9
0x1800027a6  xor     r15d, r15d
0x1800027a9  call    mwFindAnyFreeDataNode
0x1800027ae  or      r12d, 0FFFFFFFFh
0x1800027b2  mov     esi, eax
0x1800027b4  cmp     eax, r12d
0x1800027b7  jnz     short loc_1800027C1
0x1800027b9  mov     eax, r12d
0x1800027bc  jmp     loc_1800028FC
0x1800027c1  mov     r8, [rbx+68h]
0x1800027c5  sub     ebp, edi
0x1800027c7  mov     rdi, rsi
0x1800027ca  shl     rdi, 4
0x1800027ce  add     rdi, r8
0x1800027d1  test    ebp, ebp
0x1800027d3  jnz     short loc_180002810
0x1800027d5  mov     edx, [rbx+78h]
0x1800027d8  cmp     edx, [rbx+74h]
0x1800027db  jnz     short loc_1800027E2
0x1800027dd  mov     [rbx+74h], esi
0x1800027e0  jmp     short loc_180002805
0x1800027e2  mov     ecx, [rbx+74h]
0x1800027e5  shl     rcx, 4
0x1800027e9  add     rcx, r8
0x1800027ec  cmp     [rcx+0Ch], edx
0x1800027ef  jz      short loc_180002802
0x1800027f1  mov     eax, [rcx+0Ch]
0x1800027f4  add     rax, rax
0x1800027f7  lea     rcx, [r8+rax*8]
0x1800027fb  cmp     [r8+rax*8+0Ch], edx
0x180002800  jnz     short loc_1800027F1
0x180002802  mov     [rcx+0Ch], esi
0x180002805  mov     eax, [rbx+78h]
0x180002808  mov     [rdi+0Ch], eax
0x18000280b  jmp     loc_1800028F7
0x180002810  cmp     ebp, [r14+4]
0x180002814  jnz     short loc_18000282D
0x180002816  mov     eax, [r14+0Ch]
0x18000281a  mov     [rdi+0Ch], eax
0x18000281d  mov     eax, [r14+4]
0x180002821  mov     [r14+0Ch], esi
0x180002825  add     [rbx+7Ch], eax
0x180002828  jmp     loc_1800028F7
0x18000282d  mov     rcx, rbx
0x180002830  call    mwFindAnyFreeBlockNode
0x180002835  mov     [rsp+78h+arg_0], eax
0x18000283c  mov     r8d, eax
0x18000283f  cmp     eax, r12d
0x180002842  jnz     short loc_18000284D
0x180002844  mov     [rdi+4], r12d
0x180002848  jmp     loc_1800027B9
0x18000284d  mov     r12, [rbx+68h]
0x180002851  test    r15d, r15d
0x180002854  jz      short loc_1800028B0
0x180002856  mov     ecx, [rbx+94h]
0x18000285c  xor     edx, edx
0x18000285e  lea     r15d, [rcx-1]
0x180002862  add     r15d, ebp
0x180002865  mov     eax, r15d
0x180002868  div     ecx
0x18000286a  sub     r15d, edx
0x18000286d  cmp     r15d, ebp
0x180002870  jz      short loc_1800028B3
0x180002872  mov     r13d, r15d
0x180002875  mov     r9d, ebp; int
0x180002878  sub     r13d, ebp
0x18000287b  mov     r8, rdi; int
0x18000287e  mov     dword ptr [rsp+78h+dwBytes], r13d; dwBytes
0x180002883  mov     rdx, r14; int
0x180002886  mov     rcx, rbx; int
0x180002889  mov     [rsp+78h+var_58], 0; int
0x180002891  call    CopyBlockData
0x180002896  test    eax, eax
0x180002898  jnz     short loc_1800028A2
0x18000289a  or      eax, 0FFFFFFFFh
0x18000289d  mov     [rdi+4], eax
0x1800028a0  jmp     short loc_1800028FC
0x1800028a2  mov     r8d, [rsp+78h+arg_0]
0x1800028aa  mov     [rdi+4], r13d
0x1800028ae  jmp     short loc_1800028B3
0x1800028b0  mov     r15d, ebp
0x1800028b3  mov     eax, [r14+0Ch]
0x1800028b7  mov     edx, r8d
0x1800028ba  add     rdx, rdx
0x1800028bd  mov     [r12+rdx*8+0Ch], eax
0x1800028c2  mov     ecx, [r14]
0x1800028c5  add     ecx, r15d
0x1800028c8  mov     [r12+rdx*8], ecx
0x1800028cc  mov     eax, [r14+4]
0x1800028d0  sub     eax, r15d
0x1800028d3  mov     [r12+rdx*8+4], eax
0x1800028d8  mov     eax, [r14+8]
0x1800028dc  sub     eax, r15d
0x1800028df  mov     [r12+rdx*8+8], eax
0x1800028e4  mov     [rdi+0Ch], r8d
0x1800028e8  mov     [r14+4], ebp
0x1800028ec  mov     [r14+8], r15d
0x1800028f0  mov     [r14+0Ch], esi
0x1800028f4  add     [rbx+7Ch], ebp
0x1800028f7  mov     [rbx+78h], esi
0x1800028fa  mov     eax, esi
0x1800028fc  add     rsp, 38h
0x180002900  pop     r15
0x180002902  pop     r14
0x180002904  pop     r13
0x180002906  pop     r12
0x180002908  pop     rdi
0x180002909  pop     rsi
0x18000290a  pop     rbp
0x18000290b  pop     rbx
0x18000290c  retn
```
