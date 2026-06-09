# WriteRowRecords

- ea: `0x10014020`
- end: `0x1001430f`
- name: `WriteRowRecords`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x10014320`

## callees

- `0x10013d10`
- `0x10013ee0`
- `0x10013fc0`
- `0x10014020`
- `0x1002580a`
- `0x10025ab7`
- `0x10025f86`
- `0x1002611f`
- `0x10026233`

## pseudocode

```c
int __fastcall WriteRowRecords(_DWORD *a1, __int16 a2, int a3, unsigned int a4, int a5, int a6)
{
  int v6; // ebx
  _DWORD *v7; // esi
  _DWORD *v8; // eax
  size_t *v9; // ecx
  int **v10; // edi
  int result; // eax
  bool v12; // cc
  _DWORD *v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  int v18; // edi
  int v19; // esi
  int v20; // esi
  int v21; // eax
  _OWORD *v22; // edx
  __int16 v23; // ax
  int *v24; // eax
  __int16 v25; // ax
  _WORD *v26; // ecx
  int *v27; // ebx
  unsigned int v28; // esi
  int v29; // ecx
  int v30; // eax
  int v31; // esi
  _OWORD *v34; // [esp+18h] [ebp-28h] BYREF
  char *v35; // [esp+1Ch] [ebp-24h]
  signed int v36; // [esp+20h] [ebp-20h]
  int v37; // [esp+24h] [ebp-1Ch] BYREF
  int v38; // [esp+28h] [ebp-18h]
  int v39; // [esp+2Ch] [ebp-14h] BYREF
  int v40; // [esp+30h] [ebp-10h]
  _WORD *v41; // [esp+34h] [ebp-Ch]
  int **v42; // [esp+38h] [ebp-8h]
  int *v43; // [esp+3Ch] [ebp-4h]
  int savedregs; // [esp+40h] [ebp+0h] BYREF

  v6 = a6;
  v7 = a1;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v41 = 0;
  if ( a4 )
  {
    v8 = a1;
    if ( *a1 == 1 )
      v8 = (_DWORD *)a1[11];
    v8[26] = 0;
    *((_WORD *)v8 + 48) = 0x4000;
    UpdateIndex(a6, a1, (int)&savedregs, a4, 1);
    v9 = (size_t *)v7[5];
    v10 = (int **)(v7 + 5);
    v43 = v7 + 5;
    result = dword_10001970[abs32(BFOpenFileSpace(v9, a6, a4))];
    if ( result )
      return result;
  }
  else
  {
    v10 = (int **)(a1 + 5);
    v43 = a1 + 5;
  }
  v12 = v7[1] < 5;
  v42 = v10;
  if ( !v12 )
  {
    v42 = v10;
    if ( a5 )
    {
      v38 = *(_DWORD *)(a3 + 4);
      result = OpenFileSpace(a5, 1);
      if ( result )
        return result;
      *(_DWORD *)(a3 + 4) = v38;
      v42 = (int **)(v7 + 5);
    }
    if ( (int)v7[1] >= 5 )
    {
      v37 = CountRowsInBlock(&v34);
      v36 = 2 * v40 + 4;
      v13 = (_DWORD *)MemAllocate(v36);
      v35 = (char *)v13;
      if ( !v13 )
        return -2;
      v14 = *(_DWORD *)(a3 + 4);
      if ( !v14 )
      {
        v14 = a6 + 20 * v40;
        *(_DWORD *)(a3 + 4) = v14;
      }
      v10 = v42;
      *v13 = v14 - a6;
      v41 = v13 + 1;
      v43 = (int *)v10;
    }
  }
  v42 = 0;
  v38 = 0;
  BFSetFilePosition(*v10, 0, a6);
  v15 = a3;
  v16 = 0;
  v40 = 0;
  do
  {
    v17 = 20 * v16;
    v18 = v17 + v15 + 8;
    if ( *(_DWORD *)(v17 + v15 + 20) != -1 )
    {
      v19 = *(_DWORD *)(v18 + 12);
      v34 = pExcelRecordBuffer;
      if ( v42 )
      {
        v20 = v19 - (_DWORD)v42[3];
        if ( (v20 & 0xFFFF0000) != 0 )
          v20 = v38;
      }
      else
      {
        v20 = v19 - v6 - 20;
      }
      v39 = 1049096;
      v21 = BFWriteFile(*v43, (char *)&v39, 4u);
      if ( !v21 )
      {
        v22 = v34;
        v23 = a2 + v40;
        *v34 = 0;
        *(_WORD *)v22 = v23;
        *((_WORD *)v22 + 1) = *(_WORD *)v18;
        *((_WORD *)v22 + 2) = *(_WORD *)(v18 + 2);
        *((_WORD *)v22 + 3) = *(_WORD *)(v18 + 4);
        v24 = v43;
        *((_WORD *)v22 + 5) = v20;
        *(_DWORD *)(v18 + 16) = v6;
        v38 = v20;
        v21 = BFWriteFile(*v24, (char *)v22, 0x10u);
      }
      result = dword_10001970[abs32(v21)];
      if ( result == -10 )
        result = -10;
      if ( result )
        return result;
      v7 = a1;
      if ( (int)a1[1] >= 5 )
      {
        if ( v18 == v37 )
        {
          v25 = *(_WORD *)(v18 + 12) - v6 - 20;
        }
        else
        {
          if ( !v42 )
            return -1;
          v25 = *(_WORD *)(v18 + 12) - *((_WORD *)v42 + 6);
        }
        v26 = v41;
        *v41 = v25;
        v41 = v26 + 1;
      }
      v15 = a3;
      v6 += 20;
      v42 = (int **)v18;
    }
    v16 = v40 + 1;
    v40 = v16;
  }
  while ( v16 < 32 );
  if ( (int)v7[1] < 5 )
    return 0;
  v27 = v43;
  BFSetFilePosition((int *)*v43, 0, *(_DWORD *)(v15 + 4));
  v28 = v36;
  v29 = *v27;
  LOWORD(v37) = 215;
  HIWORD(v37) = v36;
  v30 = BFWriteFile(v29, (char *)&v37, 4u);
  if ( !v30 )
  {
    v31 = BFWriteFile(*v27, v35, v28);
    MemFree(v35);
    v30 = v31;
  }
  result = dword_10001970[abs32(v30)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10014020  mov     edi, edi
0x10014022  push    ebp
0x10014023  mov     ebp, esp
0x10014025  sub     esp, 34h
0x10014028  push    ebx
0x10014029  mov     ebx, [ebp+arg_C]
0x1001402c  xor     eax, eax
0x1001402e  push    esi
0x1001402f  mov     esi, ecx
0x10014031  mov     [ebp+var_2C], edx
0x10014034  mov     ecx, [ebp+arg_4]
0x10014037  mov     [ebp+var_30], esi
0x1001403a  mov     [ebp+var_1C], 0
0x10014041  mov     [ebp+var_20], 0
0x10014048  mov     [ebp+var_24], 0
0x1001404f  mov     [ebp+var_C], eax
0x10014052  push    edi
0x10014053  test    ecx, ecx
0x10014055  jz      short loc_100140B7
0x10014057  cmp     dword ptr [esi], 1
0x1001405a  mov     eax, esi
0x1001405c  jnz     short loc_10014061
0x1001405e  mov     eax, [esi+2Ch]
0x10014061  mov     edx, 4000h
0x10014066  mov     dword ptr [eax+68h], 0
0x1001406d  push    1
0x1001406f  mov     [eax+60h], dx
0x10014073  mov     edx, ebx
0x10014075  push    ecx
0x10014076  mov     ecx, esi
0x10014078  call    UpdateIndex
0x1001407d  push    [ebp+arg_4]
0x10014080  mov     ecx, [esi+14h]
0x10014083  lea     edi, [esi+14h]
0x10014086  mov     edx, ebx
0x10014088  mov     [ebp+var_4], edi
0x1001408b  call    _BFOpenFileSpace@12; BFOpenFileSpace(x,x,x)
0x10014090  cdq
0x10014091  xor     eax, edx
0x10014093  sub     eax, edx
0x10014095  mov     eax, ds:dword_10001970[eax*4]
0x1001409c  cmp     eax, 0FFFFFFF6h
0x1001409f  jnz     short loc_100140AA
0x100140a1  pop     edi
0x100140a2  pop     esi
0x100140a3  pop     ebx
0x100140a4  mov     esp, ebp
0x100140a6  pop     ebp
0x100140a7  retn    10h
0x100140aa  test    eax, eax
0x100140ac  jz      short loc_100140BD
0x100140ae  pop     edi
0x100140af  pop     esi
0x100140b0  pop     ebx
0x100140b1  mov     esp, ebp
0x100140b3  pop     ebp
0x100140b4  retn    10h
0x100140b7  lea     edi, [esi+14h]
0x100140ba  mov     [ebp+var_4], edi
0x100140bd  cmp     dword ptr [esi+4], 5
0x100140c1  mov     [ebp+var_8], edi
0x100140c4  jl      loc_10014166
0x100140ca  mov     ecx, [ebp+arg_8]
0x100140cd  mov     [ebp+var_8], edi
0x100140d0  test    ecx, ecx
0x100140d2  jz      short loc_10014100
0x100140d4  mov     eax, [ebp+arg_0]
0x100140d7  push    1
0x100140d9  push    ecx
0x100140da  mov     ecx, esi
0x100140dc  mov     eax, [eax+4]
0x100140df  mov     edx, eax
0x100140e1  mov     [ebp+var_18], eax
0x100140e4  call    OpenFileSpace
0x100140e9  test    eax, eax
0x100140eb  jnz     loc_10014306
0x100140f1  mov     eax, [ebp+arg_0]
0x100140f4  mov     ecx, [ebp+var_18]
0x100140f7  mov     [eax+4], ecx
0x100140fa  lea     eax, [esi+14h]
0x100140fd  mov     [ebp+var_8], eax
0x10014100  cmp     dword ptr [esi+4], 5
0x10014104  jl      short loc_10014166
0x10014106  mov     edi, [ebp+arg_0]
0x10014109  lea     eax, [ebp+var_28]
0x1001410c  push    eax
0x1001410d  lea     edx, [ebp+var_10]
0x10014110  mov     ecx, edi
0x10014112  call    CountRowsInBlock
0x10014117  mov     ecx, [ebp+var_10]
0x1001411a  mov     [ebp+var_1C], eax
0x1001411d  lea     eax, ds:4[ecx*2]
0x10014124  mov     ecx, eax
0x10014126  mov     [ebp+var_20], eax
0x10014129  call    _MemAllocate@4; MemAllocate(x)
0x1001412e  mov     ecx, eax
0x10014130  mov     [ebp+var_24], ecx
0x10014133  test    ecx, ecx
0x10014135  jnz     short loc_10014143
0x10014137  lea     eax, [ecx-2]
0x1001413a  pop     edi
0x1001413b  pop     esi
0x1001413c  pop     ebx
0x1001413d  mov     esp, ebp
0x1001413f  pop     ebp
0x10014140  retn    10h
0x10014143  mov     eax, [edi+4]
0x10014146  test    eax, eax
0x10014148  jnz     short loc_10014156
0x1001414a  mov     eax, [ebp+var_10]
0x1001414d  lea     eax, [eax+eax*4]
0x10014150  lea     eax, [ebx+eax*4]
0x10014153  mov     [edi+4], eax
0x10014156  mov     edi, [ebp+var_8]
0x10014159  sub     eax, ebx
0x1001415b  mov     [ecx], eax
0x1001415d  lea     eax, [ecx+4]
0x10014160  mov     [ebp+var_C], eax
0x10014163  mov     [ebp+var_4], edi
0x10014166  xor     ecx, ecx
0x10014168  xor     edx, edx
0x1001416a  mov     [ebp+var_8], ecx
0x1001416d  mov     [ebp+var_18], ecx
0x10014170  mov     ecx, [edi]
0x10014172  push    ebx
0x10014173  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10014178  mov     ecx, [ebp+arg_0]
0x1001417b  xor     eax, eax
0x1001417d  mov     [ebp+var_10], eax
0x10014180  lea     eax, [eax+eax*4]
0x10014183  shl     eax, 2
0x10014186  lea     edi, [ecx+8]
0x10014189  add     edi, eax
0x1001418b  cmp     dword ptr [eax+ecx+14h], 0FFFFFFFFh
0x10014190  jz      loc_1001427C
0x10014196  mov     eax, _pExcelRecordBuffer
0x1001419b  mov     esi, [edi+0Ch]
0x1001419e  mov     [ebp+var_28], eax
0x100141a1  mov     eax, [ebp+var_8]
0x100141a4  test    eax, eax
0x100141a6  jnz     short loc_100141AF
0x100141a8  sub     esi, ebx
0x100141aa  sub     esi, 14h
0x100141ad  jmp     short loc_100141BC
0x100141af  sub     esi, [eax+0Ch]
0x100141b2  test    esi, 0FFFF0000h
0x100141b8  cmovnz  esi, [ebp+var_18]
0x100141bc  mov     eax, [ebp+var_4]
0x100141bf  lea     edx, [ebp+var_14]
0x100141c2  push    4
0x100141c4  mov     [ebp+var_14], 100208h
0x100141cb  mov     ecx, [eax]
0x100141cd  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100141d2  test    eax, eax
0x100141d4  jnz     short loc_10014217
0x100141d6  mov     ecx, [ebp+var_28]
0x100141d9  xorps   xmm0, xmm0
0x100141dc  mov     eax, [ebp+var_10]
0x100141df  mov     edx, ecx
0x100141e1  add     eax, [ebp+var_2C]
0x100141e4  push    10h
0x100141e6  movups  xmmword ptr [ecx], xmm0
0x100141e9  mov     [ecx], ax
0x100141ec  movzx   eax, word ptr [edi]
0x100141ef  mov     [ecx+2], ax
0x100141f3  movzx   eax, word ptr [edi+2]
0x100141f7  mov     [ecx+4], ax
0x100141fb  movzx   eax, word ptr [edi+4]
0x100141ff  mov     [ecx+6], ax
0x10014203  mov     eax, [ebp+var_4]
0x10014206  mov     [ecx+0Ah], si
0x1001420a  mov     [edi+10h], ebx
0x1001420d  mov     [ebp+var_18], esi
0x10014210  mov     ecx, [eax]
0x10014212  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10014217  cdq
0x10014218  xor     eax, edx
0x1001421a  sub     eax, edx
0x1001421c  mov     edx, 0FFFFFFF6h
0x10014221  mov     eax, ds:dword_10001970[eax*4]
0x10014228  cmp     eax, 0FFFFFFF6h
0x1001422b  cmovz   eax, edx
0x1001422e  test    eax, eax
0x10014230  jnz     loc_10014306
0x10014236  mov     esi, [ebp+var_30]
0x10014239  cmp     dword ptr [esi+4], 5
0x1001423d  jl      short loc_10014273
0x1001423f  cmp     edi, [ebp+var_1C]
0x10014242  jnz     short loc_10014251
0x10014244  mov     ax, [edi+0Ch]
0x10014248  sub     ax, bx
0x1001424b  sub     ax, 14h
0x1001424f  jmp     short loc_10014264
0x10014251  mov     ecx, [ebp+var_8]
0x10014254  test    ecx, ecx
0x10014256  jz      loc_100142F8
0x1001425c  mov     ax, [edi+0Ch]
0x10014260  sub     ax, [ecx+0Ch]
0x10014264  mov     ecx, [ebp+var_C]
0x10014267  movzx   eax, ax
0x1001426a  mov     [ecx], ax
0x1001426d  add     ecx, 2
0x10014270  mov     [ebp+var_C], ecx
0x10014273  mov     ecx, [ebp+arg_0]
0x10014276  add     ebx, 14h
0x10014279  mov     [ebp+var_8], edi
0x1001427c  mov     eax, [ebp+var_10]
0x1001427f  inc     eax
0x10014280  mov     [ebp+var_10], eax
0x10014283  cmp     eax, 20h ; ' '
0x10014286  jl      loc_10014180
0x1001428c  cmp     dword ptr [esi+4], 5
0x10014290  jl      short loc_10014304
0x10014292  mov     ebx, [ebp+var_4]
0x10014295  xor     edx, edx
0x10014297  push    dword ptr [ecx+4]
0x1001429a  mov     ecx, [ebx]
0x1001429c  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x100142a1  mov     esi, [ebp+var_20]
0x100142a4  lea     edx, [ebp+var_1C]
0x100142a7  mov     ecx, [ebx]
0x100142a9  mov     eax, 0D7h
0x100142ae  push    4
0x100142b0  mov     word ptr [ebp+var_1C], ax
0x100142b4  mov     word ptr [ebp+var_1C+2], si
0x100142b8  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100142bd  test    eax, eax
0x100142bf  jnz     short loc_100142D8
0x100142c1  mov     edx, [ebp+var_24]
0x100142c4  mov     ecx, [ebx]
0x100142c6  push    esi
0x100142c7  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100142cc  mov     ecx, [ebp+var_24]
0x100142cf  mov     esi, eax
0x100142d1  call    _MemFree@4; MemFree(x)
0x100142d6  mov     eax, esi
0x100142d8  cdq
0x100142d9  xor     eax, edx
0x100142db  sub     eax, edx
0x100142dd  mov     edx, 0FFFFFFF6h
0x100142e2  mov     eax, ds:dword_10001970[eax*4]
0x100142e9  cmp     eax, 0FFFFFFF6h
0x100142ec  cmovz   eax, edx
0x100142ef  pop     edi
0x100142f0  pop     esi
0x100142f1  pop     ebx
0x100142f2  mov     esp, ebp
0x100142f4  pop     ebp
0x100142f5  retn    10h
0x100142f8  or      eax, 0FFFFFFFFh
0x100142fb  pop     edi
0x100142fc  pop     esi
0x100142fd  pop     ebx
0x100142fe  mov     esp, ebp
0x10014300  pop     ebp
0x10014301  retn    10h
0x10014304  xor     eax, eax
0x10014306  pop     edi
0x10014307  pop     esi
0x10014308  pop     ebx
0x10014309  mov     esp, ebp
0x1001430b  pop     ebp
0x1001430c  retn    10h
```
