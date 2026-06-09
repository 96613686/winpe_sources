# ExcelMIWriteCellList(x,x,x,x)

- ea: `0x1000a1f0`
- end: `0x1000a3e9`
- name: `_ExcelMIWriteCellList@16`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1001c090`

## callees

- `0x10007450`
- `0x100077d0`
- `0x1000a000`
- `0x1000a1f0`

## pseudocode

```c
int __fastcall ExcelMIWriteCellList(_DWORD *a1, int a2, __int16 a3, int *a4)
{
  int v5; // ecx
  _DWORD *v6; // esi
  unsigned int v7; // edi
  int v8; // ebx
  int v9; // eax
  int *v10; // esi
  __int16 v11; // ax
  int v12; // eax
  _DWORD *CellSpace; // eax
  _DWORD *v14; // edx
  int v15; // ecx
  __int16 v16; // ax
  char v17; // al
  int v18; // ecx
  char v19; // al
  int v20; // eax
  int v22; // [esp+Ch] [ebp-1Ch] BYREF
  int v23; // [esp+10h] [ebp-18h]
  _DWORD *v24; // [esp+14h] [ebp-14h]
  _DWORD *v25; // [esp+18h] [ebp-10h]
  int v26; // [esp+1Ch] [ebp-Ch]
  int v27; // [esp+20h] [ebp-8h]
  char v28; // [esp+27h] [ebp-1h]

  v5 = 0;
  v6 = (_DWORD *)*a1;
  v7 = 0;
  v24 = a1;
  v8 = 0;
  v9 = 0;
  v23 = 0;
  v25 = v6;
  if ( a2 > 0 )
  {
    do
    {
      v6 = (_DWORD *)*v6;
      ++v9;
    }
    while ( v9 < a2 );
    v25 = v6;
  }
  v6[11] = 0;
  v10 = a4;
  LOWORD(v26) = a3;
  if ( !a4 )
    return v5;
  while ( 1 )
  {
    HIWORD(v26) = *((unsigned __int8 *)v10 + 4);
    v11 = *((_WORD *)v10 + 4);
    if ( (v11 & 0x800) == 0 )
      break;
    v12 = DeleteCellFromWorksheet(v26);
LABEL_44:
    v5 = v12;
    if ( !v12 )
    {
      v10 = (int *)*v10;
      a4 = v10;
      if ( v10 )
        continue;
    }
    return v5;
  }
  if ( (v11 & 2) != 0 )
  {
    if ( v10[6] || (v10[7] & 3) != 0 )
    {
      v7 = 16;
      v8 = 5;
    }
    else
    {
      v7 = 12;
      v23 = v10[7];
      v8 = 6;
    }
  }
  else if ( (v11 & 0x10) != 0 )
  {
    v7 = 16;
    v8 = 8;
  }
  else if ( (v11 & 4) != 0 )
  {
    v7 = 10;
    v8 = 2;
  }
  else if ( (v11 & 8) != 0 )
  {
    v7 = 10;
    v8 = 2;
  }
  else if ( (v11 & 1) != 0 )
  {
    v7 = 8;
    v8 = 1;
  }
  CellSpace = AllocateCellSpace((int)v24, v7);
  v14 = CellSpace;
  if ( CellSpace )
  {
    v15 = *((unsigned __int16 *)v10 + 6);
    *((_WORD *)CellSpace + 2) = v15;
    v27 = v15;
    *((_BYTE *)CellSpace + 6) = BYTE2(v26);
    v16 = v15;
    *((_BYTE *)v14 + 7) = v8;
    if ( (unsigned int)(v8 - 2) <= 6 )
    {
      v16 = v27;
      switch ( v8 )
      {
        case 2:
          if ( (v10[2] & 4) != 0 )
          {
            v17 = *((_BYTE *)v10 + 24);
            v27 = (unsigned __int16)v27;
            *((_BYTE *)v14 + 8) = v17;
            v16 = v27;
            v28 = 0;
            *((_BYTE *)v14 + 9) = 0;
          }
          else
          {
            v18 = v10[6];
            if ( v18 )
            {
              switch ( v18 )
              {
                case 1:
                  v19 = 7;
                  break;
                case 2:
                  v19 = 15;
                  break;
                case 3:
                  v19 = 23;
                  break;
                case 4:
                  v19 = 29;
                  break;
                default:
                  v19 = 42;
                  if ( v18 == 5 )
                    v19 = 36;
                  break;
              }
            }
            else
            {
              v19 = 0;
            }
            v27 = *((unsigned __int16 *)v14 + 2);
            v10 = a4;
            *((_BYTE *)v14 + 8) = v19;
            v16 = v27;
            *((_BYTE *)v14 + 9) = 1;
          }
          break;
        case 3:
        case 4:
        case 7:
          break;
        case 5:
          *((_QWORD *)v14 + 1) = *((_QWORD *)v10 + 3);
          goto LABEL_42;
        case 6:
          v20 = v23;
          goto LABEL_41;
        case 8:
          v20 = v10[6];
LABEL_41:
          v14[2] = v20;
LABEL_42:
          v16 = v27;
          break;
      }
    }
    v12 = AddCellToWorksheet((int)v24, (int)v25, v26, 255, 0, v16, v14, &v22);
    goto LABEL_44;
  }
  return -2;
}

```

## disassembly

```asm
0x1000a1f0  mov     edi, edi
0x1000a1f2  push    ebp
0x1000a1f3  mov     ebp, esp
0x1000a1f5  sub     esp, 1Ch
0x1000a1f8  mov     eax, ecx
0x1000a1fa  xor     ecx, ecx
0x1000a1fc  push    ebx
0x1000a1fd  push    esi
0x1000a1fe  push    edi
0x1000a1ff  mov     esi, [eax]
0x1000a201  xor     edi, edi
0x1000a203  mov     [ebp+var_14], eax
0x1000a206  xor     ebx, ebx
0x1000a208  xor     eax, eax
0x1000a20a  mov     [ebp+var_18], ecx
0x1000a20d  mov     [ebp+var_10], esi
0x1000a210  test    edx, edx
0x1000a212  jle     short loc_1000A21E
0x1000a214  mov     esi, [esi]
0x1000a216  inc     eax
0x1000a217  cmp     eax, edx
0x1000a219  jl      short loc_1000A214
0x1000a21b  mov     [ebp+var_10], esi
0x1000a21e  mov     ax, [ebp+arg_0]
0x1000a222  mov     [esi+2Ch], ecx
0x1000a225  mov     esi, [ebp+arg_4]
0x1000a228  mov     word ptr [ebp+var_C], ax
0x1000a22c  test    esi, esi
0x1000a22e  jz      loc_1000A3D0
0x1000a234  movzx   eax, byte ptr [esi+4]
0x1000a238  mov     word ptr [ebp+var_C+2], ax
0x1000a23c  movzx   eax, word ptr [esi+8]
0x1000a240  test    eax, 800h
0x1000a245  jz      short loc_1000A25A
0x1000a247  push    [ebp+var_C]
0x1000a24a  mov     edx, [ebp+var_10]
0x1000a24d  mov     ecx, [ebp+var_14]
0x1000a250  call    DeleteCellFromWorksheet
0x1000a255  jmp     loc_1000A3BD
0x1000a25a  test    al, 2
0x1000a25c  jz      short loc_1000A282
0x1000a25e  cmp     dword ptr [esi+18h], 0
0x1000a262  jnz     short loc_1000A278
0x1000a264  mov     eax, [esi+1Ch]
0x1000a267  test    al, 3
0x1000a269  jnz     short loc_1000A278
0x1000a26b  mov     edi, 0Ch
0x1000a270  mov     [ebp+var_18], eax
0x1000a273  lea     ebx, [edi-6]
0x1000a276  jmp     short loc_1000A2B8
0x1000a278  mov     edi, 10h
0x1000a27d  lea     ebx, [edi-0Bh]
0x1000a280  jmp     short loc_1000A2B8
0x1000a282  test    al, 10h
0x1000a284  jz      short loc_1000A290
0x1000a286  mov     edi, 10h
0x1000a28b  lea     ebx, [edi-8]
0x1000a28e  jmp     short loc_1000A2B8
0x1000a290  test    al, 4
0x1000a292  jz      short loc_1000A29E
0x1000a294  mov     edi, 0Ah
0x1000a299  lea     ebx, [edi-8]
0x1000a29c  jmp     short loc_1000A2B8
0x1000a29e  test    al, 8
0x1000a2a0  jz      short loc_1000A2AC
0x1000a2a2  mov     edi, 0Ah
0x1000a2a7  lea     ebx, [edi-8]
0x1000a2aa  jmp     short loc_1000A2B8
0x1000a2ac  test    al, 1
0x1000a2ae  jz      short loc_1000A2B8
0x1000a2b0  mov     edi, 8
0x1000a2b5  lea     ebx, [edi-7]
0x1000a2b8  mov     ecx, [ebp+var_14]
0x1000a2bb  mov     edx, edi
0x1000a2bd  call    AllocateCellSpace
0x1000a2c2  mov     edx, eax
0x1000a2c4  test    edx, edx
0x1000a2c6  jz      loc_1000A3DB
0x1000a2cc  movzx   ecx, word ptr [esi+0Ch]
0x1000a2d0  mov     eax, ecx
0x1000a2d2  mov     [edx+4], cx
0x1000a2d6  mov     [ebp+var_8], eax
0x1000a2d9  mov     al, byte ptr [ebp+var_C+2]
0x1000a2dc  mov     [edx+6], al
0x1000a2df  movzx   eax, cx
0x1000a2e2  lea     ecx, [ebx-2]
0x1000a2e5  cmp     ecx, 6
0x1000a2e8  mov     [edx+7], bl
0x1000a2eb  mov     ecx, [ebp+var_8]
0x1000a2ee  ja      loc_1000A3A1; jumptable 1000A2FA cases 1,2,5
0x1000a2f4  movzx   eax, cx
0x1000a2f7  lea     ecx, [ebx-2]
0x1000a2fa  jmp     ds:jpt_1000A2FA[ecx*4]; switch 7 cases
0x1000a301  movsd   xmm0, qword ptr [esi+18h]; jumptable 1000A2FA case 3
0x1000a306  movsd   qword ptr [edx+8], xmm0
0x1000a30b  jmp     loc_1000A39B
0x1000a310  test    byte ptr [esi+8], 4; jumptable 1000A2FA case 0
0x1000a314  mov     ecx, [ebp+var_8]
0x1000a317  jz      short loc_1000A337
0x1000a319  mov     al, [esi+18h]
0x1000a31c  movzx   ecx, cx
0x1000a31f  mov     [ebp+var_8], ecx
0x1000a322  mov     [edx+8], al
0x1000a325  mov     eax, [ebp+var_8]
0x1000a328  mov     [ebp+var_1], 0
0x1000a32c  mov     cl, [ebp+var_1]
0x1000a32f  mov     [edx+9], cl
0x1000a332  movzx   eax, ax
0x1000a335  jmp     short loc_1000A3A1; jumptable 1000A2FA cases 1,2,5
0x1000a337  mov     ecx, [esi+18h]
0x1000a33a  test    ecx, ecx
0x1000a33c  jnz     short loc_1000A342
0x1000a33e  xor     al, al
0x1000a340  jmp     short loc_1000A376
0x1000a342  cmp     ecx, 1
0x1000a345  jnz     short loc_1000A34B
0x1000a347  mov     al, 7
0x1000a349  jmp     short loc_1000A376
0x1000a34b  cmp     ecx, 2
0x1000a34e  jnz     short loc_1000A354
0x1000a350  mov     al, 0Fh
0x1000a352  jmp     short loc_1000A376
0x1000a354  cmp     ecx, 3
0x1000a357  jnz     short loc_1000A35D
0x1000a359  mov     al, 17h
0x1000a35b  jmp     short loc_1000A376
0x1000a35d  cmp     ecx, 4
0x1000a360  jnz     short loc_1000A366
0x1000a362  mov     al, 1Dh
0x1000a364  jmp     short loc_1000A376
0x1000a366  cmp     ecx, 5
0x1000a369  mov     eax, 2Ah ; '*'
0x1000a36e  mov     ecx, 24h ; '$'
0x1000a373  cmovz   eax, ecx
0x1000a376  movzx   esi, word ptr [edx+4]
0x1000a37a  mov     cl, 1
0x1000a37c  mov     [ebp+var_8], esi
0x1000a37f  mov     esi, [ebp+arg_4]
0x1000a382  mov     [edx+8], al
0x1000a385  mov     eax, [ebp+var_8]
0x1000a388  mov     [edx+9], cl
0x1000a38b  movzx   eax, ax
0x1000a38e  jmp     short loc_1000A3A1; jumptable 1000A2FA cases 1,2,5
0x1000a390  mov     eax, [esi+18h]; jumptable 1000A2FA case 6
0x1000a393  jmp     short loc_1000A398
0x1000a395  mov     eax, [ebp+var_18]; jumptable 1000A2FA case 4
0x1000a398  mov     [edx+8], eax
0x1000a39b  mov     ecx, [ebp+var_8]
0x1000a39e  movzx   eax, cx
0x1000a3a1  lea     ecx, [ebp+var_1C]; jumptable 1000A2FA cases 1,2,5
0x1000a3a4  cwde
0x1000a3a5  push    ecx
0x1000a3a6  mov     ecx, [ebp+var_14]
0x1000a3a9  push    edx
0x1000a3aa  mov     edx, [ebp+var_10]
0x1000a3ad  push    eax
0x1000a3ae  push    0
0x1000a3b0  push    0FFh
0x1000a3b5  push    [ebp+var_C]
0x1000a3b8  call    AddCellToWorksheet
0x1000a3bd  mov     ecx, eax
0x1000a3bf  test    ecx, ecx
0x1000a3c1  jnz     short loc_1000A3D0
0x1000a3c3  mov     esi, [esi]
0x1000a3c5  mov     [ebp+arg_4], esi
0x1000a3c8  test    esi, esi
0x1000a3ca  jnz     loc_1000A234
0x1000a3d0  pop     edi
0x1000a3d1  pop     esi
0x1000a3d2  mov     eax, ecx
0x1000a3d4  pop     ebx
0x1000a3d5  mov     esp, ebp
0x1000a3d7  pop     ebp
0x1000a3d8  retn    8
0x1000a3db  pop     edi
0x1000a3dc  pop     esi
0x1000a3dd  mov     eax, 0FFFFFFFEh
0x1000a3e2  pop     ebx
0x1000a3e3  mov     esp, ebp
0x1000a3e5  pop     ebp
0x1000a3e6  retn    8
```
