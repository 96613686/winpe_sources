# AdjustLastTempData

- ea: `0x180001288`
- end: `0x18000141b`
- name: `AdjustLastTempData`
- size: `403`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002150`

## callees

- `0x180001288`
- `0x180001424`
- `0x180001db8`

## pseudocode

```c
__int64 __fastcall AdjustLastTempData(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  unsigned int v6; // edi
  unsigned int v7; // esi
  int *v8; // rbx
  unsigned int v9; // eax
  int v10; // eax
  unsigned int AnyFreeBlockNode; // r15d
  unsigned int v12; // r13d
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // edx
  int *v17; // rcx
  SIZE_T dwBytes; // [rsp+28h] [rbp-50h]

  if ( *(_DWORD *)(a2 + 4) - a3 < a4 && *(_DWORD *)(a2 + 12) != -1 )
  {
    v6 = a3 - *(_DWORD *)(a2 + 4) + a4;
    v7 = v6;
    v8 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * *(unsigned int *)(a2 + 12));
    if ( v8[1] < v6 )
    {
      do
      {
        v9 = v8[3];
        if ( v9 == -1 )
          goto LABEL_24;
        v7 -= v8[1];
        v8 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * v9);
      }
      while ( v8[1] < v7 );
    }
    if ( *v8 < 0 )
    {
      v10 = v8[1];
      if ( v10 != v7 )
      {
        if ( v10 - v7 <= *(_DWORD *)(a1 + 148) )
        {
          AnyFreeBlockNode = -1;
        }
        else
        {
          AnyFreeBlockNode = mwFindAnyFreeBlockNode(a1);
          if ( AnyFreeBlockNode == -1 )
            return 0;
        }
        v12 = v7 + *(_DWORD *)(a1 + 148) - 1 - (v7 + *(_DWORD *)(a1 + 148) - 1) % *(_DWORD *)(a1 + 148);
        if ( v12 >= v8[1] )
          v12 = v8[1];
        if ( v12 == v7 || (LODWORD(dwBytes) = v12 - v7, (unsigned int)CopyBlockData(a1, v8, v8, v7, 0, dwBytes)) )
        {
          if ( AnyFreeBlockNode != -1 )
          {
            v14 = *(_QWORD *)(a1 + 104);
            v15 = 2LL * AnyFreeBlockNode;
            *(_DWORD *)(v14 + 8 * v15) = v12 + *v8;
            *(_DWORD *)(v14 + 8 * v15 + 4) = v8[1] - v12;
            *(_DWORD *)(v14 + 8 * v15 + 8) = v8[2] - v12;
            *(_DWORD *)(v14 + 8 * v15 + 12) = v8[3];
            v8[3] = AnyFreeBlockNode;
            v8[2] = v12;
          }
          v6 -= v7;
          v8[1] = v12 - v7;
          goto LABEL_24;
        }
        return 0;
      }
    }
LABEL_24:
    while ( 1 )
    {
      v17 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * *(unsigned int *)(a2 + 12));
      if ( v17[1] > v6 )
        break;
      v16 = v17[1];
      *(_DWORD *)(a2 + 12) = v17[3];
      if ( *v17 >= 0 )
        v17[2] = 0;
      v17[1] = -1;
      if ( *(_DWORD *)(a2 + 12) == -1 )
        return 1;
      v6 -= v16;
    }
    if ( v6 )
    {
      *v17 += v6;
      v17[1] -= v6;
      v17[2] -= v6;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001288  push    rbx
0x18000128a  push    rbp
0x18000128b  push    rsi
0x18000128c  push    rdi
0x18000128d  push    r12
0x18000128f  push    r13
0x180001291  push    r14
0x180001293  push    r15
0x180001295  sub     rsp, 38h
0x180001299  mov     eax, [rdx+4]
0x18000129c  mov     edi, r9d
0x18000129f  sub     eax, r8d
0x1800012a2  mov     r14, rdx
0x1800012a5  mov     rbp, rcx
0x1800012a8  cmp     eax, r9d
0x1800012ab  jnb     loc_180001405
0x1800012b1  or      r12d, 0FFFFFFFFh
0x1800012b5  cmp     [rdx+0Ch], r12d
0x1800012b9  jz      loc_180001405
0x1800012bf  sub     r8d, [rdx+4]
0x1800012c3  mov     ebx, [rdx+0Ch]
0x1800012c6  add     edi, r8d
0x1800012c9  shl     rbx, 4
0x1800012cd  mov     esi, edi
0x1800012cf  add     rbx, [rcx+68h]
0x1800012d3  cmp     [rbx+4], edi
0x1800012d6  jnb     short loc_1800012F6
0x1800012d8  mov     eax, [rbx+0Ch]
0x1800012db  cmp     eax, r12d
0x1800012de  jz      loc_1800013E8
0x1800012e4  sub     esi, [rbx+4]
0x1800012e7  mov     ebx, eax
0x1800012e9  shl     rbx, 4
0x1800012ed  add     rbx, [rcx+68h]
0x1800012f1  cmp     [rbx+4], esi
0x1800012f4  jb      short loc_1800012D8
0x1800012f6  cmp     dword ptr [rbx], 0
0x1800012f9  jge     loc_1800013E8
0x1800012ff  mov     eax, [rbx+4]
0x180001302  cmp     eax, esi
0x180001304  jz      loc_1800013E8
0x18000130a  sub     eax, esi
0x18000130c  cmp     eax, [rcx+94h]
0x180001312  jbe     short loc_180001323
0x180001314  call    mwFindAnyFreeBlockNode
0x180001319  mov     r15d, eax
0x18000131c  cmp     eax, r12d
0x18000131f  jz      short loc_180001370
0x180001321  jmp     short loc_180001326
0x180001323  mov     r15d, r12d
0x180001326  mov     ecx, [rbp+94h]
0x18000132c  xor     edx, edx
0x18000132e  lea     r13d, [rcx-1]
0x180001332  add     r13d, esi
0x180001335  mov     eax, r13d
0x180001338  div     ecx
0x18000133a  sub     r13d, edx
0x18000133d  cmp     r13d, [rbx+4]
0x180001341  cmovnb  r13d, [rbx+4]
0x180001346  mov     r12d, r13d
0x180001349  sub     r12d, esi
0x18000134c  jz      short loc_180001377
0x18000134e  mov     dword ptr [rsp+78h+dwBytes], r12d; dwBytes
0x180001353  mov     r9d, esi; int
0x180001356  mov     r8, rbx; int
0x180001359  mov     [rsp+78h+var_58], 0; int
0x180001361  mov     rdx, rbx; int
0x180001364  mov     rcx, rbp; int
0x180001367  call    CopyBlockData
0x18000136c  test    eax, eax
0x18000136e  jnz     short loc_180001377
0x180001370  xor     eax, eax
0x180001372  jmp     loc_18000140A
0x180001377  cmp     r15d, 0FFFFFFFFh
0x18000137b  jz      short loc_1800013BA
0x18000137d  mov     rdx, [rbp+68h]
0x180001381  mov     ecx, [rbx]
0x180001383  add     ecx, r13d
0x180001386  mov     r8d, r15d
0x180001389  add     r8, r8
0x18000138c  mov     [rdx+r8*8], ecx
0x180001390  mov     eax, [rbx+4]
0x180001393  sub     eax, r12d
0x180001396  sub     eax, esi
0x180001398  mov     [rdx+r8*8+4], eax
0x18000139d  mov     eax, [rbx+8]
0x1800013a0  sub     eax, r12d
0x1800013a3  sub     eax, esi
0x1800013a5  mov     [rdx+r8*8+8], eax
0x1800013aa  mov     eax, [rbx+0Ch]
0x1800013ad  mov     [rdx+r8*8+0Ch], eax
0x1800013b2  mov     [rbx+0Ch], r15d
0x1800013b6  mov     [rbx+8], r13d
0x1800013ba  sub     edi, esi
0x1800013bc  mov     [rbx+4], r12d
0x1800013c0  or      r12d, 0FFFFFFFFh
0x1800013c4  jmp     short loc_1800013E8
0x1800013c6  mov     edx, [rcx+4]
0x1800013c9  mov     eax, [rcx+0Ch]
0x1800013cc  mov     [r14+0Ch], eax
0x1800013d0  cmp     dword ptr [rcx], 0
0x1800013d3  jl      short loc_1800013DC
0x1800013d5  mov     dword ptr [rcx+8], 0
0x1800013dc  mov     [rcx+4], r12d
0x1800013e0  cmp     [r14+0Ch], r12d
0x1800013e4  jz      short loc_180001405
0x1800013e6  sub     edi, edx
0x1800013e8  mov     ecx, [r14+0Ch]
0x1800013ec  shl     rcx, 4
0x1800013f0  add     rcx, [rbp+68h]
0x1800013f4  cmp     [rcx+4], edi
0x1800013f7  jbe     short loc_1800013C6
0x1800013f9  test    edi, edi
0x1800013fb  jz      short loc_180001405
0x1800013fd  add     [rcx], edi
0x1800013ff  sub     [rcx+4], edi
0x180001402  sub     [rcx+8], edi
0x180001405  mov     eax, 1
0x18000140a  add     rsp, 38h
0x18000140e  pop     r15
0x180001410  pop     r14
0x180001412  pop     r13
0x180001414  pop     r12
0x180001416  pop     rdi
0x180001417  pop     rsi
0x180001418  pop     rbp
0x180001419  pop     rbx
0x18000141a  retn
```
