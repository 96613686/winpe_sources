# IndexMover::Move(long,MoveOption,Err &)

- ea: `0x1002f230`
- end: `0x1002f8e9`
- name: `?Move@IndexMover@@UAEXJW4MoveOption@@AAVErr@@@Z`
- size: `1721`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10010790`
- `0x10010810`
- `0x100109e0`
- `0x10010bb0`
- `0x10010c60`
- `0x10011400`
- `0x10025ee0`
- `0x1002f230`
- `0x10030270`
- `0x10030380`
- `0x10038630`
- `0x10038650`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __thiscall IndexMover::Move(int this, int a2, int a3, struct Err *a4)
{
  _DWORD *v4; // esi
  int v5; // ecx
  int v6; // eax
  int v7; // edi
  int result; // eax
  int v9; // edi
  int v10; // ecx
  int v11; // edi
  int v12; // ecx
  int v13; // edi
  char *v14; // eax
  unsigned int v15; // esi
  unsigned int v16; // edx
  unsigned int v17; // esi
  bool v18; // cf
  unsigned __int8 v19; // cl
  unsigned __int8 v20; // cl
  unsigned __int8 v21; // cl
  int v22; // eax
  int v23; // edi
  int v24; // eax
  int v25; // eax
  unsigned int Bookmark; // eax
  int v27; // ecx
  int v28; // edx
  unsigned int *v29; // [esp+10h] [ebp-4Ch]
  Btree *v30; // [esp+14h] [ebp-48h]
  Btree *v31; // [esp+14h] [ebp-48h]
  unsigned int v33; // [esp+1Ch] [ebp-40h] BYREF
  void *Block; // [esp+20h] [ebp-3Ch]
  int v35; // [esp+24h] [ebp-38h]
  int v36; // [esp+28h] [ebp-34h]
  char v37; // [esp+2Ch] [ebp-30h] BYREF
  int v38; // [esp+58h] [ebp-4h]
  int v39; // [esp+64h] [ebp+8h]

  v30 = *(Btree **)(this + 8);
  (*(void (__thiscall **)(_DWORD, struct Err *))(**(_DWORD **)(this + 4) + 124))(*(_DWORD *)(this + 4), a4);
  v4 = (_DWORD *)this;
  v5 = a3;
  if ( *(_DWORD *)(this + 8) == 4 && (a3 == 2 || a3 == 3) )
  {
    v6 = IndexMover::ResyncIndex(this, a4);
    v5 = a3;
    v7 = v6;
  }
  else
  {
    v7 = (int)v30;
  }
  result = a2;
  if ( a2 )
  {
    if ( a2 <= 0 )
      goto LABEL_124;
  }
  else
  {
    result = *(_DWORD *)(this + 8);
    if ( result != 3 )
    {
      if ( result )
        result = Err::SetError(a4, -1603, v5);
      goto LABEL_124;
    }
    v5 = 0;
    result = 1;
    a3 = 0;
  }
  while ( 2 )
  {
    v39 = result - 1;
    result = *(_DWORD *)a4;
    if ( (*(_DWORD *)a4 & 8) == 0 )
    {
      switch ( v5 )
      {
        case 0:
          Btree::First((Btree *)(v4 + 44), a4);
          v5 = a3;
          v7 = 1;
          goto LABEL_123;
        case 1:
          Btree::Last((Btree *)(v4 + 44), a4);
          v5 = a3;
          v7 = 2;
          goto LABEL_123;
        case 2:
          switch ( v4[2] )
          {
            case 0:
              Btree::Next((Btree *)(v4 + 44), a4);
              goto LABEL_30;
            case 1:
              Btree::First((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) == 0 )
                goto LABEL_22;
              goto LABEL_37;
            case 2:
              if ( result < 8 )
              {
                if ( (result & 0xFFFFFFFE) != 0 )
                {
                  if ( *((_DWORD *)a4 + 3) )
                    operator delete[](*((void **)a4 + 3));
                  if ( *((_DWORD *)a4 + 4) )
                    operator delete[](*((void **)a4 + 4));
                }
                *(_DWORD *)a4 = 8;
                *((_DWORD *)a4 + 1) = -1603;
                *((_DWORD *)a4 + 2) = 0;
                *((_DWORD *)a4 + 3) = 0;
                *((_DWORD *)a4 + 4) = 0;
              }
              goto LABEL_30;
            case 3:
              Btree::First((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_37;
              Btree::Next((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) == 0 )
LABEL_22:
                v4[2] = 0;
LABEL_30:
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_37;
              v9 = v4[31];
              if ( !v9 || IndexMover::IsInRange(v4, v4 + 59) )
                goto LABEL_37;
              switch ( v9 )
              {
                case 1:
                case 2:
                  goto LABEL_34;
                case 3:
                case 4:
                  goto LABEL_35;
                default:
                  goto LABEL_36;
              }
            default:
              goto LABEL_30;
          }
          goto LABEL_36;
        case 3:
          switch ( v4[2] )
          {
            case 0:
              Btree::Prior((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) == 0 )
                goto LABEL_49;
              goto LABEL_50;
            case 1:
            case 3:
              if ( result < 8 )
              {
                if ( (result & 0xFFFFFFFE) != 0 )
                {
                  if ( *((_DWORD *)a4 + 3) )
                    operator delete[](*((void **)a4 + 3));
                  if ( *((_DWORD *)a4 + 4) )
                    operator delete[](*((void **)a4 + 4));
                }
                *(_DWORD *)a4 = 8;
                *((_DWORD *)a4 + 1) = -1603;
                *((_DWORD *)a4 + 2) = 0;
                *((_DWORD *)a4 + 3) = 0;
                *((_DWORD *)a4 + 4) = 0;
              }
              goto LABEL_50;
            case 2:
              Btree::Last((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_57;
LABEL_49:
              v4[2] = 0;
LABEL_50:
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_57;
              v11 = v4[31];
              if ( !v11 || IndexMover::IsInRange(v4, v4 + 59) )
                goto LABEL_57;
              switch ( v11 )
              {
                case 1:
                case 2:
                  goto LABEL_54;
                case 3:
                case 4:
                  goto LABEL_55;
                default:
                  goto LABEL_56;
              }
            default:
              goto LABEL_50;
          }
LABEL_56:
          Err::SetError(a4, -1603, v12);
          v4[31] = 0;
          v4[32] = 0;
LABEL_57:
          v5 = a3;
          v7 = 1;
          goto LABEL_123;
        case 4:
          switch ( v4[2] )
          {
            case 0:
              Btree::NextNE((Btree *)(v4 + 44), a4);
              goto LABEL_72;
            case 1:
              Btree::First((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) == 0 )
                goto LABEL_64;
              goto LABEL_37;
            case 2:
              if ( result < 8 )
              {
                if ( (result & 0xFFFFFFFE) != 0 )
                {
                  if ( *((_DWORD *)a4 + 3) )
                    operator delete[](*((void **)a4 + 3));
                  if ( *((_DWORD *)a4 + 4) )
                    operator delete[](*((void **)a4 + 4));
                }
                *(_DWORD *)a4 = 8;
                *((_DWORD *)a4 + 1) = -1603;
                *((_DWORD *)a4 + 2) = 0;
                *((_DWORD *)a4 + 3) = 0;
                *((_DWORD *)a4 + 4) = 0;
              }
              goto LABEL_72;
            case 3:
              Btree::First((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_37;
              Btree::NextNE((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) == 0 )
LABEL_64:
                v4[2] = 0;
LABEL_72:
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_37;
              v13 = v4[31];
              if ( !v13 || IndexMover::IsInRange(v4, v4 + 59) )
                goto LABEL_37;
              switch ( v13 )
              {
                case 1:
                case 2:
LABEL_34:
                  v4[2] = 1;
                  break;
                case 3:
                case 4:
LABEL_35:
                  v4[2] = 2;
                  break;
                default:
                  goto LABEL_36;
              }
              break;
            default:
              goto LABEL_72;
          }
LABEL_36:
          Err::SetError(a4, -1603, v10);
          v4[31] = 0;
          v4[32] = 0;
LABEL_37:
          v5 = a3;
          v7 = 2;
          goto LABEL_123;
        case 5:
          switch ( v4[2] )
          {
            case 0:
              v33 = 0;
              v31 = (Btree *)(v4 + 44);
              Block = &v37;
              v35 = 0;
              v36 = 32;
              v38 = 0;
              v29 = v4 + 59;
              Key::Assign((Key *)&v33, (const struct QuickKey *)(v4 + 59), a4);
              if ( (*(_BYTE *)a4 & 8) != 0 )
              {
                v38 = -1;
                if ( v35 == 1 && Block )
                  operator delete[](Block);
                goto LABEL_103;
              }
              v33 -= 4;
              break;
            case 1:
            case 3:
              if ( result < 8 )
              {
                if ( (result & 0xFFFFFFFE) != 0 )
                {
                  if ( *((_DWORD *)a4 + 3) )
                    operator delete[](*((void **)a4 + 3));
                  if ( *((_DWORD *)a4 + 4) )
                    operator delete[](*((void **)a4 + 4));
                }
                *(_DWORD *)a4 = 8;
                *((_DWORD *)a4 + 1) = -1603;
                *((_DWORD *)a4 + 2) = 0;
                *((_DWORD *)a4 + 3) = 0;
                *((_DWORD *)a4 + 4) = 0;
              }
              goto LABEL_114;
            case 2:
              Btree::Last((Btree *)(v4 + 44), a4);
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_57;
LABEL_113:
              v4[2] = 0;
LABEL_114:
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_57;
              v23 = v4[31];
              if ( !v23 || IndexMover::IsInRange(v4, v4 + 59) )
                goto LABEL_57;
              switch ( v23 )
              {
                case 1:
                case 2:
LABEL_54:
                  v4[2] = 1;
                  break;
                case 3:
                case 4:
LABEL_55:
                  v4[2] = 2;
                  break;
                default:
                  goto LABEL_56;
              }
              goto LABEL_56;
            default:
              goto LABEL_114;
          }
          break;
        case 6:
          v24 = v4[5];
          v7 = 2;
          if ( v24 )
            --*(_WORD *)(v24 + 76);
          v4[6] = 0;
          v4[5] = 0;
          v25 = v4[9];
          if ( v25 )
            --*(_WORD *)(v25 + 76);
          v4[10] = 0;
          v4[9] = 0;
          v4[19] = 0;
          v4[53] = 0;
          v4[57] = 0;
          v4[59] = 0;
          goto LABEL_123;
        default:
LABEL_123:
          result = v39;
          if ( v39 <= 0 )
            goto LABEL_124;
          continue;
      }
      while ( 1 )
      {
        Btree::Prior(v31, a4);
        if ( (*(_BYTE *)a4 & 8) != 0 )
        {
LABEL_99:
          v38 = -1;
          if ( v35 == 1 && Block )
            operator delete[](Block);
          v4 = (_DWORD *)this;
LABEL_103:
          if ( (*(_BYTE *)a4 & 8) == 0 )
            goto LABEL_113;
          goto LABEL_114;
        }
        v14 = (char *)Block;
        v15 = v33;
        v16 = v29[1];
        if ( *v29 < v33 )
          v15 = *v29;
        v18 = v15 < 4;
        v17 = v15 - 4;
        if ( v18 )
        {
LABEL_88:
          if ( v17 == -4 )
            goto LABEL_97;
        }
        else
        {
          while ( *(_DWORD *)v16 == *(_DWORD *)v14 )
          {
            v16 += 4;
            v14 += 4;
            v18 = v17 < 4;
            v17 -= 4;
            if ( v18 )
              goto LABEL_88;
          }
        }
        v18 = *(_BYTE *)v16 < (unsigned __int8)*v14;
        if ( *(_BYTE *)v16 == *v14 )
        {
          if ( v17 == -3
            || (v19 = *(_BYTE *)(v16 + 1), v18 = v19 < (unsigned __int8)v14[1], v19 == v14[1])
            && (v17 == -2
             || (v20 = *(_BYTE *)(v16 + 2), v18 = v20 < (unsigned __int8)v14[2], v20 == v14[2])
             && (v17 == -1 || (v21 = *(_BYTE *)(v16 + 3), v18 = v21 < (unsigned __int8)v14[3], v21 == v14[3]))) )
          {
LABEL_97:
            v22 = 0;
            goto LABEL_98;
          }
        }
        v22 = v18 ? -1 : 1;
LABEL_98:
        if ( v22 )
          goto LABEL_99;
      }
    }
    break;
  }
LABEL_124:
  if ( (*(_BYTE *)a4 & 8) != 0 )
  {
    v4[2] = v7;
    v4[3] = 0;
  }
  else
  {
    v4[2] = 0;
    Bookmark = Btree::GetBookmark((Btree *)(v4 + 44), a4);
    v4[3] = Bookmark;
    v27 = v4[5];
    if ( v27 )
      v28 = *(_DWORD *)(v27 + 12);
    else
      v28 = 0;
    result = Bookmark >> 8;
    if ( v28 != result )
    {
      if ( v27 )
        --*(_WORD *)(v27 + 76);
      v4[6] = 0;
      v4[5] = 0;
    }
    v4[13] = 0;
    v4[14] = 0;
    v4[15] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1002f230  mov     edi, edi
0x1002f232  push    ebp
0x1002f233  mov     ebp, esp
0x1002f235  push    0FFFFFFFFh
0x1002f237  push    offset ?Move@IndexMover@@UAEXJW4MoveOption@@AAVErr@@@Z_SEH
0x1002f23c  mov     eax, large fs:0
0x1002f242  push    eax
0x1002f243  sub     esp, 40h
0x1002f246  mov     eax, ___security_cookie
0x1002f24b  xor     eax, ebp
0x1002f24d  mov     [ebp+var_10], eax
0x1002f250  push    ebx
0x1002f251  push    esi
0x1002f252  push    edi
0x1002f253  push    eax; unsigned int
0x1002f254  lea     eax, [ebp+var_C]
0x1002f257  mov     large fs:0, eax
0x1002f25d  mov     [ebp+var_44], ecx
0x1002f260  mov     edi, [ecx+4]
0x1002f263  mov     eax, [ecx+8]
0x1002f266  mov     ebx, [ebp+arg_8]
0x1002f269  mov     [ebp+var_48], eax
0x1002f26c  mov     eax, [edi]
0x1002f26e  push    ebx; void *
0x1002f26f  mov     esi, [eax+7Ch]
0x1002f272  mov     ecx, esi
0x1002f274  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002f27a  mov     ecx, edi
0x1002f27c  call    esi
0x1002f27e  mov     esi, [ebp+var_44]
0x1002f281  mov     ecx, [ebp+arg_4]
0x1002f284  cmp     dword ptr [esi+8], 4
0x1002f288  jnz     short loc_1002F2A3
0x1002f28a  cmp     ecx, 2
0x1002f28d  jz      short loc_1002F294
0x1002f28f  cmp     ecx, 3
0x1002f292  jnz     short loc_1002F2A3
0x1002f294  push    ebx
0x1002f295  mov     ecx, esi
0x1002f297  call    ?ResyncIndex@IndexMover@@AAE?AW4TblState@@AAVErr@@@Z; IndexMover::ResyncIndex(Err &)
0x1002f29c  mov     ecx, [ebp+arg_4]
0x1002f29f  mov     edi, eax
0x1002f2a1  jmp     short loc_1002F2A6
0x1002f2a3  mov     edi, [ebp+var_48]
0x1002f2a6  mov     eax, [ebp+arg_0]
0x1002f2a9  test    eax, eax
0x1002f2ab  jnz     short loc_1002F2DB
0x1002f2ad  mov     eax, [esi+8]
0x1002f2b0  cmp     eax, 3
0x1002f2b3  jnz     short loc_1002F2C1
0x1002f2b5  xor     ecx, ecx
0x1002f2b7  mov     eax, 1
0x1002f2bc  mov     [ebp+arg_4], ecx
0x1002f2bf  jmp     short loc_1002F2E1
0x1002f2c1  test    eax, eax
0x1002f2c3  jz      loc_1002F864
0x1002f2c9  push    ecx
0x1002f2ca  push    0FFFFF9BDh
0x1002f2cf  mov     ecx, ebx
0x1002f2d1  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002f2d6  jmp     loc_1002F864
0x1002f2db  jle     loc_1002F864
0x1002f2e1  dec     eax
0x1002f2e2  mov     [ebp+arg_0], eax
0x1002f2e5  mov     eax, [ebx]
0x1002f2e7  test    al, 8
0x1002f2e9  jnz     loc_1002F864
0x1002f2ef  cmp     ecx, 6; switch 7 cases
0x1002f2f2  ja      def_1002F2F8; jumptable 1002F2F8 default case
0x1002f2f8  jmp     ds:jpt_1002F2F8[ecx*4]; switch jump
0x1002f2ff  lea     ecx, [esi+0B0h]; jumptable 1002F2F8 case 0
0x1002f305  push    ebx; struct Err *
0x1002f306  call    ?First@Btree@@QAEXAAVErr@@@Z; Btree::First(Err &)
0x1002f30b  mov     ecx, [ebp+arg_4]
0x1002f30e  mov     edi, 1
0x1002f313  jmp     def_1002F2F8; jumptable 1002F2F8 default case
0x1002f318  lea     ecx, [esi+0B0h]; jumptable 1002F2F8 case 1
0x1002f31e  push    ebx; struct Err *
0x1002f31f  call    ?Last@Btree@@QAEXAAVErr@@@Z; Btree::Last(Err &)
0x1002f324  mov     ecx, [ebp+arg_4]
0x1002f327  mov     edi, 2
0x1002f32c  jmp     def_1002F2F8; jumptable 1002F2F8 default case
0x1002f331  mov     ecx, [esi+8]; jumptable 1002F2F8 case 2
0x1002f334  cmp     ecx, 3; switch 4 cases
0x1002f337  ja      def_1002F33D; jumptable 1002F33D default case
0x1002f33d  jmp     ds:jpt_1002F33D[ecx*4]; switch jump
0x1002f344  push    ebx; jumptable 1002F33D case 3
0x1002f345  lea     ecx, [esi+0B0h]; this
0x1002f34b  call    ?First@Btree@@QAEXAAVErr@@@Z; Btree::First(Err &)
0x1002f350  test    byte ptr [ebx], 8
0x1002f353  jnz     loc_1002F441
0x1002f359  push    ebx; struct Err *
0x1002f35a  lea     ecx, [esi+0B0h]; this
0x1002f360  call    ?Next@Btree@@QAEXAAVErr@@@Z; Btree::Next(Err &)
0x1002f365  test    byte ptr [ebx], 8
0x1002f368  jz      short loc_1002F38F
0x1002f36a  jmp     short def_1002F33D; jumptable 1002F33D default case
0x1002f36c  lea     ecx, [esi+0B0h]; jumptable 1002F33D case 0
0x1002f372  push    ebx; struct Err *
0x1002f373  call    ?Next@Btree@@QAEXAAVErr@@@Z; Btree::Next(Err &)
0x1002f378  jmp     short def_1002F33D; jumptable 1002F33D default case
0x1002f37a  lea     ecx, [esi+0B0h]; jumptable 1002F33D case 1
0x1002f380  push    ebx; struct Err *
0x1002f381  call    ?First@Btree@@QAEXAAVErr@@@Z; Btree::First(Err &)
0x1002f386  test    byte ptr [ebx], 8
0x1002f389  jnz     loc_1002F441
0x1002f38f  mov     dword ptr [esi+8], 0
0x1002f396  jmp     short def_1002F33D; jumptable 1002F33D default case
0x1002f398  cmp     eax, 8; jumptable 1002F33D case 2
0x1002f39b  jge     short def_1002F33D; jumptable 1002F33D default case
0x1002f39d  test    eax, 0FFFFFFFEh
0x1002f3a2  jz      short loc_1002F3C4
0x1002f3a4  mov     eax, [ebx+0Ch]
0x1002f3a7  test    eax, eax
0x1002f3a9  jz      short loc_1002F3B4
0x1002f3ab  push    eax; Block
0x1002f3ac  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002f3b1  add     esp, 4
0x1002f3b4  mov     eax, [ebx+10h]
0x1002f3b7  test    eax, eax
0x1002f3b9  jz      short loc_1002F3C4
0x1002f3bb  push    eax; Block
0x1002f3bc  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002f3c1  add     esp, 4
0x1002f3c4  mov     dword ptr [ebx], 8
0x1002f3ca  mov     dword ptr [ebx+4], 0FFFFF9BDh
0x1002f3d1  mov     dword ptr [ebx+8], 0
0x1002f3d8  mov     dword ptr [ebx+0Ch], 0
0x1002f3df  mov     dword ptr [ebx+10h], 0
0x1002f3e6  test    byte ptr [ebx], 8; jumptable 1002F33D default case
0x1002f3e9  jnz     short loc_1002F441
0x1002f3eb  mov     edi, [esi+7Ch]
0x1002f3ee  test    edi, edi
0x1002f3f0  jz      short loc_1002F441
0x1002f3f2  lea     eax, [esi+0ECh]
0x1002f3f8  mov     ecx, esi
0x1002f3fa  push    eax
0x1002f3fb  call    ?IsInRange@IndexMover@@QAE?AW4RangeResult@@ABVQuickKey@@@Z; IndexMover::IsInRange(QuickKey const &)
0x1002f400  test    eax, eax
0x1002f402  jnz     short loc_1002F441
0x1002f404  lea     eax, [edi-1]; switch 4 cases
0x1002f407  cmp     eax, 3
0x1002f40a  ja      short def_1002F40C; jumptable 1002F40C default case
0x1002f40c  jmp     ds:jpt_1002F40C[eax*4]; switch jump
0x1002f413  mov     dword ptr [esi+8], 1; jumptable 1002F40C cases 1,2
0x1002f41a  jmp     short def_1002F40C; jumptable 1002F40C default case
0x1002f41c  mov     dword ptr [esi+8], 2; jumptable 1002F40C cases 3,4
0x1002f423  push    ecx; jumptable 1002F40C default case
0x1002f424  push    0FFFFF9BDh
0x1002f429  mov     ecx, ebx
0x1002f42b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002f430  mov     dword ptr [esi+7Ch], 0
0x1002f437  mov     dword ptr [esi+80h], 0
0x1002f441  mov     ecx, [ebp+arg_4]
0x1002f444  mov     edi, 2
0x1002f449  jmp     def_1002F2F8; jumptable 1002F2F8 default case
0x1002f44e  mov     ecx, [esi+8]; jumptable 1002F2F8 case 3
0x1002f451  cmp     ecx, 3; switch 4 cases
0x1002f454  ja      def_1002F45A; jumptable 1002F45A default case
0x1002f45a  jmp     ds:jpt_1002F45A[ecx*4]; switch jump
0x1002f461  lea     ecx, [esi+0B0h]; jumptable 1002F45A case 0
0x1002f467  push    ebx; struct Err *
0x1002f468  call    ?Prior@Btree@@QAEXAAVErr@@@Z; Btree::Prior(Err &)
0x1002f46d  test    byte ptr [ebx], 8
0x1002f470  jz      short loc_1002F4D5
0x1002f472  jmp     short def_1002F45A; jumptable 1002F45A default case
0x1002f474  cmp     eax, 8; jumptable 1002F45A cases 1,3
0x1002f477  jge     short def_1002F45A; jumptable 1002F45A default case
0x1002f479  test    eax, 0FFFFFFFEh
0x1002f47e  jz      short loc_1002F4A0
0x1002f480  mov     eax, [ebx+0Ch]
0x1002f483  test    eax, eax
0x1002f485  jz      short loc_1002F490
0x1002f487  push    eax; Block
0x1002f488  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002f48d  add     esp, 4
0x1002f490  mov     eax, [ebx+10h]
0x1002f493  test    eax, eax
0x1002f495  jz      short loc_1002F4A0
0x1002f497  push    eax; Block
0x1002f498  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002f49d  add     esp, 4
0x1002f4a0  mov     dword ptr [ebx], 8
0x1002f4a6  mov     dword ptr [ebx+4], 0FFFFF9BDh
0x1002f4ad  mov     dword ptr [ebx+8], 0
0x1002f4b4  mov     dword ptr [ebx+0Ch], 0
0x1002f4bb  mov     dword ptr [ebx+10h], 0
0x1002f4c2  jmp     short def_1002F45A; jumptable 1002F45A default case
0x1002f4c4  lea     ecx, [esi+0B0h]; jumptable 1002F45A case 2
0x1002f4ca  push    ebx; struct Err *
0x1002f4cb  call    ?Last@Btree@@QAEXAAVErr@@@Z; Btree::Last(Err &)
0x1002f4d0  test    byte ptr [ebx], 8
0x1002f4d3  jnz     short loc_1002F537
0x1002f4d5  mov     dword ptr [esi+8], 0
0x1002f4dc  test    byte ptr [ebx], 8; jumptable 1002F45A default case
0x1002f4df  jnz     short loc_1002F537
0x1002f4e1  mov     edi, [esi+7Ch]
0x1002f4e4  test    edi, edi
0x1002f4e6  jz      short loc_1002F537
0x1002f4e8  lea     eax, [esi+0ECh]
0x1002f4ee  mov     ecx, esi
0x1002f4f0  push    eax
0x1002f4f1  call    ?IsInRange@IndexMover@@QAE?AW4RangeResult@@ABVQuickKey@@@Z; IndexMover::IsInRange(QuickKey const &)
0x1002f4f6  test    eax, eax
0x1002f4f8  jnz     short loc_1002F537
0x1002f4fa  lea     eax, [edi-1]; switch 4 cases
0x1002f4fd  cmp     eax, 3
0x1002f500  ja      short def_1002F502; jumptable 1002F502 default case
0x1002f502  jmp     ds:jpt_1002F502[eax*4]; switch jump
0x1002f509  mov     dword ptr [esi+8], 1; jumptable 1002F502 cases 1,2
0x1002f510  jmp     short def_1002F502; jumptable 1002F502 default case
0x1002f512  mov     dword ptr [esi+8], 2; jumptable 1002F502 cases 3,4
0x1002f519  push    ecx; jumptable 1002F502 default case
0x1002f51a  push    0FFFFF9BDh
0x1002f51f  mov     ecx, ebx
0x1002f521  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002f526  mov     dword ptr [esi+7Ch], 0
0x1002f52d  mov     dword ptr [esi+80h], 0
0x1002f537  mov     ecx, [ebp+arg_4]
0x1002f53a  mov     edi, 1
0x1002f53f  jmp     def_1002F2F8; jumptable 1002F2F8 default case
0x1002f544  mov     ecx, [esi+8]; jumptable 1002F2F8 case 4
0x1002f547  cmp     ecx, 3; switch 4 cases
0x1002f54a  ja      def_1002F550; jumptable 1002F550 default case
0x1002f550  jmp     ds:jpt_1002F550[ecx*4]; switch jump
0x1002f557  push    ebx; jumptable 1002F550 case 3
0x1002f558  lea     ecx, [esi+0B0h]; this
0x1002f55e  call    ?First@Btree@@QAEXAAVErr@@@Z; Btree::First(Err &)
0x1002f563  test    byte ptr [ebx], 8
0x1002f566  jnz     loc_1002F441
0x1002f56c  push    ebx; struct Err *
0x1002f56d  lea     ecx, [esi+0B0h]; this
0x1002f573  call    ?NextNE@Btree@@QAEXAAVErr@@@Z; Btree::NextNE(Err &)
0x1002f578  test    byte ptr [ebx], 8
0x1002f57b  jz      short loc_1002F5A2
0x1002f57d  jmp     short def_1002F550; jumptable 1002F550 default case
0x1002f57f  lea     ecx, [esi+0B0h]; jumptable 1002F550 case 0
0x1002f585  push    ebx; struct Err *
0x1002f586  call    ?NextNE@Btree@@QAEXAAVErr@@@Z; Btree::NextNE(Err &)
0x1002f58b  jmp     short def_1002F550; jumptable 1002F550 default case
0x1002f58d  lea     ecx, [esi+0B0h]; jumptable 1002F550 case 1
0x1002f593  push    ebx; struct Err *
0x1002f594  call    ?First@Btree@@QAEXAAVErr@@@Z; Btree::First(Err &)
0x1002f599  test    byte ptr [ebx], 8
0x1002f59c  jnz     loc_1002F441
0x1002f5a2  mov     dword ptr [esi+8], 0
0x1002f5a9  jmp     short def_1002F550; jumptable 1002F550 default case
0x1002f5ab  cmp     eax, 8; jumptable 1002F550 case 2
0x1002f5ae  jge     short def_1002F550; jumptable 1002F550 default case
0x1002f5b0  test    eax, 0FFFFFFFEh
0x1002f5b5  jz      short loc_1002F5D7
0x1002f5b7  mov     eax, [ebx+0Ch]
0x1002f5ba  test    eax, eax
0x1002f5bc  jz      short loc_1002F5C7
0x1002f5be  push    eax; Block
0x1002f5bf  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002f5c4  add     esp, 4
0x1002f5c7  mov     eax, [ebx+10h]
0x1002f5ca  test    eax, eax
0x1002f5cc  jz      short loc_1002F5D7
0x1002f5ce  push    eax; Block
0x1002f5cf  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002f5d4  add     esp, 4
0x1002f5d7  mov     dword ptr [ebx], 8
0x1002f5dd  mov     dword ptr [ebx+4], 0FFFFF9BDh
0x1002f5e4  mov     dword ptr [ebx+8], 0
0x1002f5eb  mov     dword ptr [ebx+0Ch], 0
0x1002f5f2  mov     dword ptr [ebx+10h], 0
0x1002f5f9  test    byte ptr [ebx], 8; jumptable 1002F550 default case
0x1002f5fc  jnz     loc_1002F441
0x1002f602  mov     edi, [esi+7Ch]
0x1002f605  test    edi, edi
0x1002f607  jz      loc_1002F441
0x1002f60d  lea     eax, [esi+0ECh]
0x1002f613  mov     ecx, esi
0x1002f615  push    eax
0x1002f616  call    ?IsInRange@IndexMover@@QAE?AW4RangeResult@@ABVQuickKey@@@Z; IndexMover::IsInRange(QuickKey const &)
0x1002f61b  test    eax, eax
0x1002f61d  jnz     loc_1002F441
0x1002f623  lea     eax, [edi-1]; switch 4 cases
0x1002f626  cmp     eax, 3
0x1002f629  ja      def_1002F40C; jumptable 1002F40C default case
0x1002f62f  jmp     ds:jpt_1002F62F[eax*4]; switch jump
0x1002f636  mov     ecx, [esi+8]; jumptable 1002F2F8 case 5
0x1002f639  cmp     ecx, 3; switch 4 cases
0x1002f63c  ja      def_1002F642; jumptable 1002F642 default case
0x1002f642  jmp     ds:jpt_1002F642[ecx*4]; switch jump
0x1002f649  lea     eax, [esi+0B0h]; jumptable 1002F642 case 0
0x1002f64f  mov     [ebp+var_40], 0
0x1002f656  lea     ecx, [ebp+var_30]
0x1002f659  mov     [ebp+var_48], eax
0x1002f65c  mov     [ebp+Block], ecx
0x1002f65f  mov     [ebp+var_38], 0
0x1002f666  mov     [ebp+var_34], 20h ; ' '
0x1002f66d  add     eax, 3Ch ; '<'
0x1002f670  mov     [ebp+var_4], 0
0x1002f677  push    ebx; struct Err *
0x1002f678  push    eax; struct QuickKey *
0x1002f679  lea     ecx, [ebp+var_40]; this
0x1002f67c  mov     [ebp+var_4C], eax
  ... truncated ...
```
