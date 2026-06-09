# ExcelWriteCellIndex(x)

- ea: `0x10014320`
- end: `0x10014675`
- name: `_ExcelWriteCellIndex@4`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x10011dd0`

## callees

- `0x10013ee0`
- `0x10013f50`
- `0x10013fc0`
- `0x10014020`
- `0x10014320`
- `0x10025f86`
- `0x1002611f`
- `0x10035f40`

## pseudocode

```c
int __thiscall ExcelWriteCellIndex(_DWORD *this)
{
  _DWORD *v1; // esi
  int v2; // eax
  __int16 *v3; // edi
  int result; // eax
  int v5; // eax
  signed int v6; // ecx
  int v7; // ebx
  signed int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // ebx
  int v12; // eax
  int v13; // ecx
  int v14; // ebx
  int v15; // esi
  int v16; // edx
  int v17; // esi
  int v18; // eax
  size_t v19; // ebx
  int v20; // ecx
  int v21; // eax
  _WORD *v22; // ebx
  int v23; // esi
  int v24; // ebx
  __int16 v25; // cx
  int v26; // edx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // [esp-8h] [ebp-40h]
  size_t v31; // [esp-4h] [ebp-3Ch]
  int v32; // [esp+Ch] [ebp-2Ch]
  int v33; // [esp+14h] [ebp-24h] BYREF
  int v34; // [esp+18h] [ebp-20h]
  size_t Size; // [esp+1Ch] [ebp-1Ch]
  void *v36; // [esp+20h] [ebp-18h]
  int v37; // [esp+24h] [ebp-14h] BYREF
  int v38; // [esp+28h] [ebp-10h]
  int v39; // [esp+2Ch] [ebp-Ch]
  _DWORD *v40; // [esp+30h] [ebp-8h]
  int v41; // [esp+34h] [ebp-4h]

  v1 = this;
  v36 = pExcelRecordBuffer;
  v40 = this;
  if ( *(_DWORD *)(this[11] + 40) )
    return 0;
  v2 = this[12];
  v3 = *(__int16 **)(v2 + 40);
  if ( !v3 )
    return 0;
  if ( *(_DWORD *)(v2 + 48) || !this[9] )
    goto LABEL_11;
  result = OpenFileSpace(6, 1);
  if ( !result )
  {
    v37 = 131166;
    *(_WORD *)pExcelRecordBuffer = 0;
    v5 = BFWriteFile(v1[5], (char *)&v37, 4u);
    if ( !v5 )
    {
      v5 = BFWriteFile(v1[5], (char *)pExcelRecordBuffer, 2u);
      if ( !v5 )
        goto LABEL_11;
    }
    result = dword_10001970[abs32(v5)];
    if ( result == -10 )
      result = -10;
    if ( !result )
    {
LABEL_11:
      v6 = v3[5];
      v7 = *((_DWORD *)v3 + 3);
      v32 = v7;
      v8 = 4 * v3[4] + 12;
      Size = v8;
      if ( v8 <= v6 )
      {
        if ( v8 < v6 )
        {
          result = RemoveFileSpace(v6 - v8, 1);
          if ( result )
            return result;
        }
      }
      else
      {
        result = OpenFileSpace(v8 - v6, 1);
        if ( result )
          return result;
      }
      v9 = *(_DWORD *)v3;
      v10 = 0;
      v39 = *(_DWORD *)v3;
      v41 = 0;
      if ( v3[4] <= 0 )
        goto LABEL_43;
      while ( 1 )
      {
        v11 = *(_DWORD *)&v3[2 * v10 + 8];
        if ( !v11 )
          goto LABEL_40;
        v12 = CountRowsInBlock(&v33);
        if ( v34 > 0 )
          break;
        v1 = v40;
LABEL_39:
        v9 = v39;
        v10 = v41;
LABEL_40:
        ++v10;
        v39 = v9 + 32;
        v18 = v3[4];
        v41 = v10;
        if ( v10 >= v18 )
        {
          v7 = v32;
LABEL_43:
          BFSetFilePosition((int *)v1[5], 0, v7);
          *((_DWORD *)v3 + 3) = v7;
          v19 = Size;
          v20 = v1[5];
          LOWORD(v37) = 523;
          HIWORD(v37) = Size;
          v21 = BFWriteFile(v20, (char *)&v37, 4u);
          if ( !v21 )
          {
            v31 = v19;
            v22 = v36;
            memset(v36, 0, v31);
            v22[2] = *v3;
            v23 = 12;
            v22[3] = v3[2];
            v24 = 0;
            if ( v3[4] > 0 )
            {
              v25 = v3[4];
              do
              {
                v26 = *(_DWORD *)&v3[2 * v24 + 8];
                if ( !v26 )
                {
                  v27 = v24 + 1;
                  if ( v24 + 1 >= v25 )
                    return -1;
                  while ( 1 )
                  {
                    v26 = *(_DWORD *)&v3[2 * v27 + 8];
                    if ( v26 )
                      break;
                    if ( ++v27 >= v25 )
                      return -1;
                  }
                }
                if ( (int)v40[1] < 5 )
                {
                  v29 = 0;
                  while ( *(_DWORD *)(v26 + 20 * v29 + 20) == -1 )
                  {
                    if ( ++v29 >= 32 )
                      goto LABEL_59;
                  }
                  v28 = *(_DWORD *)(v26 + 20 * v29 + 24);
                }
                else
                {
                  v28 = *(_DWORD *)(v26 + 4);
                }
                *(_DWORD *)((char *)v36 + v23) = v28;
                v23 += 4;
LABEL_59:
                ++v24;
                v25 = v3[4];
              }
              while ( v24 < v25 );
            }
            v21 = BFWriteFile(v40[5], (char *)v36, Size);
          }
          result = dword_10001970[abs32(v21)];
          if ( result == -10 )
            return -10;
          return result;
        }
        v9 = v39;
      }
      v37 = 0;
      if ( v33 == v34 )
      {
        v13 = *(_DWORD *)(v12 + 16);
        v14 = 0;
        v15 = 0;
        goto LABEL_26;
      }
      if ( v33 )
        goto LABEL_29;
      if ( (int)v40[1] < 5 )
      {
        v13 = *(_DWORD *)(v12 + 12);
        v14 = 20 * v34;
        goto LABEL_25;
      }
      if ( *(_DWORD *)(v11 + 4) != v33 )
      {
LABEL_29:
        v38 = v34 - v33;
        v14 = 20 * (v34 - v33);
        v16 = 0;
        while ( 1 )
        {
          v17 = v38;
          v13 = *(_DWORD *)(*(_DWORD *)&v3[2 * v41 + 8] + 20 * v16 + 24);
          if ( v13 )
            break;
          v17 = v38;
          v13 = *(_DWORD *)(*(_DWORD *)&v3[2 * v41 + 8] + 20 * v16 + 44);
          if ( v13 )
            break;
          v17 = v38;
          v13 = *(_DWORD *)(*(_DWORD *)&v3[2 * v41 + 8] + 20 * v16 + 64);
          if ( v13 )
            break;
          v17 = v38;
          v13 = *(_DWORD *)(*(_DWORD *)&v3[2 * v41 + 8] + 20 * v16 + 84);
          if ( v13 )
            break;
          v16 += 4;
          if ( v16 >= 32 )
          {
            v13 = *(_DWORD *)(v12 + 12);
            break;
          }
        }
        if ( (int)v40[1] >= 5 )
        {
          v15 = 2 * v17;
LABEL_26:
          v30 = v15;
          v1 = v40;
          result = WriteRowRecords(*(_DWORD *)&v3[2 * v41 + 8], v14, v30, v13);
          if ( result )
            return result;
          goto LABEL_39;
        }
      }
      else
      {
        v13 = *(_DWORD *)(v12 + 12);
        v14 = 20 * v34 + 2 * (v34 + 4);
      }
LABEL_25:
      v15 = v37;
      goto LABEL_26;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10014320  mov     edi, edi
0x10014322  push    ebp
0x10014323  mov     ebp, esp
0x10014325  sub     esp, 2Ch
0x10014328  mov     eax, _pExcelRecordBuffer
0x1001432d  push    ebx
0x1001432e  push    esi
0x1001432f  mov     esi, ecx
0x10014331  mov     [ebp+var_18], eax
0x10014334  push    edi
0x10014335  mov     [ebp+var_8], esi
0x10014338  mov     eax, [esi+2Ch]
0x1001433b  cmp     dword ptr [eax+28h], 0
0x1001433f  jnz     loc_1001466C
0x10014345  mov     eax, [esi+30h]
0x10014348  mov     edi, [eax+28h]
0x1001434b  test    edi, edi
0x1001434d  jz      loc_1001466C
0x10014353  cmp     dword ptr [eax+30h], 0
0x10014357  mov     ebx, 0FFFFFFF6h
0x1001435c  jnz     short loc_100143C8
0x1001435e  cmp     dword ptr [esi+24h], 0
0x10014362  jz      short loc_100143C8
0x10014364  mov     edx, [edi+0Ch]
0x10014367  push    1
0x10014369  push    6
0x1001436b  call    OpenFileSpace
0x10014370  test    eax, eax
0x10014372  jnz     loc_1001466E
0x10014378  mov     eax, _pExcelRecordBuffer
0x1001437d  lea     edx, [ebp+var_14]
0x10014380  xor     ecx, ecx
0x10014382  mov     [ebp+var_14], 2005Eh
0x10014389  push    4
0x1001438b  mov     [eax], cx
0x1001438e  mov     ecx, [esi+14h]
0x10014391  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10014396  test    eax, eax
0x10014398  jnz     short loc_100143AE
0x1001439a  mov     edx, _pExcelRecordBuffer
0x100143a0  mov     ecx, [esi+14h]
0x100143a3  push    2
0x100143a5  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100143aa  test    eax, eax
0x100143ac  jz      short loc_100143C8
0x100143ae  cdq
0x100143af  xor     eax, edx
0x100143b1  sub     eax, edx
0x100143b3  mov     eax, ds:dword_10001970[eax*4]
0x100143ba  cmp     eax, 0FFFFFFF6h
0x100143bd  cmovz   eax, ebx
0x100143c0  test    eax, eax
0x100143c2  jnz     loc_1001466E
0x100143c8  movsx   eax, word ptr [edi+8]
0x100143cc  movsx   ecx, word ptr [edi+0Ah]
0x100143d0  mov     ebx, [edi+0Ch]
0x100143d3  mov     [ebp+var_2C], ebx
0x100143d6  lea     eax, ds:0Ch[eax*4]
0x100143dd  mov     [ebp+Size], eax
0x100143e0  cmp     eax, ecx
0x100143e2  jle     short loc_100143FD
0x100143e4  sub     eax, ecx
0x100143e6  mov     edx, ebx
0x100143e8  push    1
0x100143ea  push    eax
0x100143eb  mov     ecx, esi
0x100143ed  call    OpenFileSpace
0x100143f2  test    eax, eax
0x100143f4  jz      short loc_10014415
0x100143f6  pop     edi
0x100143f7  pop     esi
0x100143f8  pop     ebx
0x100143f9  mov     esp, ebp
0x100143fb  pop     ebp
0x100143fc  retn
0x100143fd  jge     short loc_10014415
0x100143ff  sub     ecx, eax
0x10014401  mov     edx, ebx
0x10014403  push    1
0x10014405  push    ecx
0x10014406  mov     ecx, esi
0x10014408  call    RemoveFileSpace
0x1001440d  test    eax, eax
0x1001440f  jnz     loc_1001466E
0x10014415  mov     eax, [edi]
0x10014417  xor     ecx, ecx
0x10014419  xor     edx, edx
0x1001441b  mov     [ebp+var_C], eax
0x1001441e  mov     [ebp+var_4], ecx
0x10014421  cmp     dx, [edi+8]
0x10014425  jge     loc_10014564
0x1001442b  nop     dword ptr [eax+eax+00h]
0x10014430  mov     ebx, [edi+ecx*4+10h]
0x10014434  test    ebx, ebx
0x10014436  jz      loc_10014547
0x1001443c  lea     eax, [ebp+var_24]
0x1001443f  mov     ecx, ebx
0x10014441  push    eax
0x10014442  lea     edx, [ebp+var_20]
0x10014445  call    CountRowsInBlock
0x1001444a  mov     esi, [ebp+var_20]
0x1001444d  mov     edx, eax
0x1001444f  mov     [ebp+var_28], edx
0x10014452  test    esi, esi
0x10014454  jle     loc_1001453E
0x1001445a  mov     ecx, [ebp+var_24]
0x1001445d  mov     [ebp+var_14], 0
0x10014464  cmp     ecx, esi
0x10014466  jnz     short loc_10014471
0x10014468  mov     ecx, [edx+10h]
0x1001446b  xor     ebx, ebx
0x1001446d  mov     esi, ebx
0x1001446f  jmp     short loc_10014495
0x10014471  test    ecx, ecx
0x10014473  jnz     short loc_100144C4
0x10014475  mov     eax, [ebp+var_8]
0x10014478  cmp     dword ptr [eax+4], 5
0x1001447c  jl      short loc_100144B9
0x1001447e  cmp     [ebx+4], ecx
0x10014481  jnz     short loc_100144C4
0x10014483  mov     ecx, [edx+0Ch]
0x10014486  lea     eax, [esi+esi*4]
0x10014489  shl     eax, 2
0x1001448c  add     esi, 4
0x1001448f  lea     ebx, [eax+esi*2]
0x10014492  mov     esi, [ebp+var_14]
0x10014495  mov     eax, [ebp+var_4]
0x10014498  mov     edx, [ebp+var_C]
0x1001449b  push    ecx
0x1001449c  push    esi
0x1001449d  mov     esi, [ebp+var_8]
0x100144a0  mov     ecx, esi
0x100144a2  push    ebx
0x100144a3  push    dword ptr [edi+eax*4+10h]
0x100144a7  call    WriteRowRecords
0x100144ac  test    eax, eax
0x100144ae  jnz     loc_1001466E
0x100144b4  jmp     loc_10014541
0x100144b9  mov     ecx, [edx+0Ch]
0x100144bc  lea     ebx, [esi+esi*4]
0x100144bf  shl     ebx, 2
0x100144c2  jmp     short loc_10014492
0x100144c4  sub     esi, ecx
0x100144c6  mov     [ebp+var_10], esi
0x100144c9  lea     ebx, [esi+esi*4]
0x100144cc  shl     ebx, 2
0x100144cf  xor     edx, edx
0x100144d1  mov     esi, [ebp+var_4]
0x100144d4  lea     eax, [edx+edx*4]
0x100144d7  mov     ecx, [edi+esi*4+10h]
0x100144db  mov     esi, [ebp+var_10]
0x100144de  mov     ecx, [ecx+eax*4+18h]
0x100144e2  test    ecx, ecx
0x100144e4  jnz     short loc_1001452A
0x100144e6  mov     esi, [ebp+var_4]
0x100144e9  mov     ecx, [edi+esi*4+10h]
0x100144ed  mov     esi, [ebp+var_10]
0x100144f0  mov     ecx, [ecx+eax*4+2Ch]
0x100144f4  test    ecx, ecx
0x100144f6  jnz     short loc_1001452A
0x100144f8  mov     esi, [ebp+var_4]
0x100144fb  mov     ecx, [edi+esi*4+10h]
0x100144ff  mov     esi, [ebp+var_10]
0x10014502  mov     ecx, [ecx+eax*4+40h]
0x10014506  test    ecx, ecx
0x10014508  jnz     short loc_1001452A
0x1001450a  mov     esi, [ebp+var_4]
0x1001450d  mov     ecx, [edi+esi*4+10h]
0x10014511  mov     esi, [ebp+var_10]
0x10014514  mov     ecx, [ecx+eax*4+54h]
0x10014518  test    ecx, ecx
0x1001451a  jnz     short loc_1001452A
0x1001451c  add     edx, 4
0x1001451f  cmp     edx, 20h ; ' '
0x10014522  jl      short loc_100144D1
0x10014524  mov     ecx, [ebp+var_28]
0x10014527  mov     ecx, [ecx+0Ch]
0x1001452a  mov     eax, [ebp+var_8]
0x1001452d  cmp     dword ptr [eax+4], 5
0x10014531  jl      loc_10014492
0x10014537  add     esi, esi
0x10014539  jmp     loc_10014495
0x1001453e  mov     esi, [ebp+var_8]
0x10014541  mov     eax, [ebp+var_C]
0x10014544  mov     ecx, [ebp+var_4]
0x10014547  add     eax, 20h ; ' '
0x1001454a  inc     ecx
0x1001454b  mov     [ebp+var_C], eax
0x1001454e  movsx   eax, word ptr [edi+8]
0x10014552  mov     [ebp+var_4], ecx
0x10014555  cmp     ecx, eax
0x10014557  jge     short loc_10014561
0x10014559  mov     eax, [ebp+var_C]
0x1001455c  jmp     loc_10014430
0x10014561  mov     ebx, [ebp+var_2C]
0x10014564  mov     ecx, [esi+14h]
0x10014567  xor     edx, edx
0x10014569  push    ebx
0x1001456a  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x1001456f  mov     [edi+0Ch], ebx
0x10014572  lea     edx, [ebp+var_14]
0x10014575  mov     ebx, [ebp+Size]
0x10014578  mov     eax, 20Bh
0x1001457d  mov     ecx, [esi+14h]
0x10014580  push    4
0x10014582  mov     word ptr [ebp+var_14], ax
0x10014586  mov     word ptr [ebp+var_14+2], bx
0x1001458a  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1001458f  test    eax, eax
0x10014591  jnz     loc_1001464E
0x10014597  push    ebx; Size
0x10014598  mov     ebx, [ebp+var_18]
0x1001459b  push    eax; Val
0x1001459c  push    ebx; void *
0x1001459d  call    _memset
0x100145a2  movzx   eax, word ptr [edi]
0x100145a5  xor     ecx, ecx
0x100145a7  mov     [ebx+4], ax
0x100145ab  add     esp, 0Ch
0x100145ae  movzx   eax, word ptr [edi+4]
0x100145b2  mov     esi, 0Ch
0x100145b7  mov     [ebx+6], ax
0x100145bb  xor     ebx, ebx
0x100145bd  movzx   eax, word ptr [edi+8]
0x100145c1  cmp     cx, ax
0x100145c4  jge     short loc_1001463D
0x100145c6  mov     ecx, eax
0x100145c8  mov     edx, [edi+ebx*4+10h]
0x100145cc  test    edx, edx
0x100145ce  jnz     short loc_100145F7
0x100145d0  lea     eax, [ebx+1]
0x100145d3  movsx   ecx, cx
0x100145d6  cmp     eax, ecx
0x100145d8  jge     short loc_100145ED
0x100145da  nop     word ptr [eax+eax+00h]
0x100145e0  mov     edx, [edi+eax*4+10h]
0x100145e4  test    edx, edx
0x100145e6  jnz     short loc_100145F7
0x100145e8  inc     eax
0x100145e9  cmp     eax, ecx
0x100145eb  jl      short loc_100145E0
0x100145ed  or      eax, 0FFFFFFFFh
0x100145f0  pop     edi
0x100145f1  pop     esi
0x100145f2  pop     ebx
0x100145f3  mov     esp, ebp
0x100145f5  pop     ebp
0x100145f6  retn
0x100145f7  mov     eax, [ebp+var_8]
0x100145fa  cmp     dword ptr [eax+4], 5
0x100145fe  jl      short loc_10014605
0x10014600  mov     eax, [edx+4]
0x10014603  jmp     short loc_10014628
0x10014605  xor     eax, eax
0x10014607  nop     word ptr [eax+eax+00000000h]
0x10014610  lea     ecx, [eax+eax*4]
0x10014613  cmp     dword ptr [edx+ecx*4+14h], 0FFFFFFFFh
0x10014618  lea     ecx, [edx+ecx*4]
0x1001461b  jnz     short loc_10014625
0x1001461d  inc     eax
0x1001461e  cmp     eax, 20h ; ' '
0x10014621  jl      short loc_10014610
0x10014623  jmp     short loc_10014631
0x10014625  mov     eax, [ecx+18h]
0x10014628  mov     ecx, [ebp+var_18]
0x1001462b  mov     [esi+ecx], eax
0x1001462e  add     esi, 4
0x10014631  movzx   eax, word ptr [edi+8]
0x10014635  inc     ebx
0x10014636  mov     ecx, eax
0x10014638  cwde
0x10014639  cmp     ebx, eax
0x1001463b  jl      short loc_100145C8
0x1001463d  mov     eax, [ebp+var_8]
0x10014640  push    [ebp+Size]
0x10014643  mov     edx, [ebp+var_18]
0x10014646  mov     ecx, [eax+14h]
0x10014649  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1001464e  cdq
0x1001464f  mov     ecx, 0FFFFFFF6h
0x10014654  xor     eax, edx
0x10014656  sub     eax, edx
0x10014658  mov     eax, ds:dword_10001970[eax*4]
0x1001465f  cmp     eax, 0FFFFFFF6h
0x10014662  cmovz   eax, ecx
0x10014665  pop     edi
0x10014666  pop     esi
0x10014667  pop     ebx
0x10014668  mov     esp, ebp
0x1001466a  pop     ebp
0x1001466b  retn
0x1001466c  xor     eax, eax
0x1001466e  pop     edi
0x1001466f  pop     esi
0x10014670  pop     ebx
0x10014671  mov     esp, ebp
0x10014673  pop     ebp
0x10014674  retn
```
