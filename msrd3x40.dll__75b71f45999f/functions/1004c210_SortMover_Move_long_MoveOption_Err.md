# SortMover::Move(long,MoveOption,Err &)

- ea: `0x1004c210`
- end: `0x1004c5af`
- name: `?Move@SortMover@@UAEXJW4MoveOption@@AAVErr@@@Z`
- size: `927`
- prototype: `void __thiscall __high(int, enum MoveOption, struct Err *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1000eb60`
- `0x10010500`
- `0x10025ee0`
- `0x10046360`
- `0x10046400`
- `0x1004c210`
- `0x1004cee0`
- `0x1005e7e8`

## pseudocode

```c
int __thiscall SortMover::Move(_DWORD *this, void *a2, unsigned int a3, struct Err *a4)
{
  int result; // eax
  int v6; // eax
  Sort **v7; // edx
  struct SortItem ***v8; // esi
  int v9; // eax
  Sort *v10; // eax
  int v11; // ecx
  Sort *v12; // ecx
  struct SortItem **v13; // eax
  int v14; // esi
  struct SortItem *v15; // ecx
  int v16; // eax
  int v17; // ecx
  Sort *v18; // edx
  int v19; // ecx
  int v20; // eax
  struct SortItem ***v21; // edx
  struct SortItem **v22; // ecx
  int v23; // esi
  struct SortItem *v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // [esp+Ch] [ebp-24h]
  _DWORD **v28; // [esp+10h] [ebp-20h]
  Sort **v29; // [esp+10h] [ebp-20h]
  Sort **v30; // [esp+14h] [ebp-1Ch]
  struct SortItem ***v31; // [esp+18h] [ebp-18h]
  int v32; // [esp+1Ch] [ebp-14h]
  _DWORD v33[2]; // [esp+20h] [ebp-10h] BYREF
  _DWORD v34[2]; // [esp+28h] [ebp-8h] BYREF

  v27 = this[2];
  v28 = (_DWORD **)this[1];
  ((void (__thiscall *)(_DWORD **, struct Err *))(*v28)[31])(v28, a4);
  if ( !this[2] )
  {
    result = SortMover::WrapUpInput(this, a4);
    if ( result != 2 )
    {
      if ( (*(_BYTE *)a4 & 8) == 0 )
        return (*(int (__thiscall **)(_DWORD *, void *, unsigned int, struct Err *))(*v28[9] + 8))(v28[9], a2, a3, a4);
      return result;
    }
  }
  v6 = (int)a2;
  if ( !a2 )
  {
    if ( this[4] == *(_DWORD *)(this[3] + 24) )
      Err::SetError(a4, -1603, this[3]);
    goto LABEL_76;
  }
  if ( (int)a2 > 0 )
  {
    v7 = (Sort **)(this + 3);
    v29 = (Sort **)(this + 3);
    v8 = (struct SortItem ***)(this + 4);
    while ( 1 )
    {
      v31 = v8;
      v32 = v6 - 1;
      v9 = *(_DWORD *)a4;
      v30 = v7;
      if ( (*(_DWORD *)a4 & 8) != 0 )
        break;
      switch ( a3 )
      {
        case 0u:
          *v8 = Sort::First(*v7, a4);
          v27 = 3;
          goto LABEL_67;
        case 1u:
          v10 = *v7;
          v11 = *((_DWORD *)*v7 + 3);
          if ( v11 )
          {
            v27 = 3;
            *v8 = (struct SortItem **)(*((_DWORD *)v10 + 5) + 4 * v11 - 4);
          }
          else
          {
            *v8 = (struct SortItem **)*((_DWORD *)v10 + 6);
            v27 = 3;
          }
          goto LABEL_67;
        case 2u:
          v12 = *v7;
          if ( this[2] == 1 )
          {
            v13 = Sort::First(v12, a4);
            *v8 = v13;
            if ( v13 != *((struct SortItem ***)*v29 + 6) )
              this[2] = 2;
          }
          else
          {
            v13 = *v8;
            if ( *v8 != *((struct SortItem ***)v12 + 6) )
            {
              v13 = Sort::Next(v12, v13, a4);
              *v8 = v13;
            }
          }
          if ( (*(_BYTE *)a4 & 8) != 0 )
            goto LABEL_34;
          v14 = this[22];
          if ( !v14 )
            goto LABEL_34;
          v15 = *v13;
          v33[1] = (char *)*v13 + 4;
          v33[0] = *((unsigned __int16 *)v15 + 1);
          v16 = QuickKey::Compare((QuickKey *)v33, (struct QuickKey *)(this + 23));
          if ( v16 )
          {
            if ( v14 == 1 )
            {
LABEL_31:
              if ( v16 >= 0 )
                goto LABEL_34;
LABEL_32:
              Err::SetError(a4, -1603, v17);
              this[2] = 1;
              goto LABEL_33;
            }
          }
          else
          {
            if ( v14 == 1 )
              goto LABEL_32;
            if ( v14 == 3 )
              goto LABEL_30;
          }
          if ( v14 != 2 )
          {
            if ( v16 > 0 )
            {
LABEL_30:
              Err::SetError(a4, -1603, v17);
              this[2] = 3;
LABEL_33:
              this[23] = 0;
              this[22] = 0;
            }
LABEL_34:
            v27 = 3;
            goto LABEL_67;
          }
          goto LABEL_31;
        case 3u:
          v18 = *v7;
          if ( this[2] == 3 )
          {
            v19 = *((_DWORD *)v18 + 3);
            if ( v19 )
            {
              v20 = *((_DWORD *)v18 + 5);
              v21 = (struct SortItem ***)((char *)v18 + 24);
              v22 = (struct SortItem **)(v20 + 4 * (v19 - 1));
            }
            else
            {
              v22 = (struct SortItem **)*((_DWORD *)v18 + 6);
              v21 = (struct SortItem ***)((char *)v18 + 24);
            }
            *v8 = v22;
            if ( v22 != *v21 )
              this[2] = 2;
          }
          else
          {
            v22 = *v8;
            if ( *v8 != *((struct SortItem ***)v18 + 6) )
            {
              if ( (unsigned int)v22 <= *((_DWORD *)v18 + 5) )
                v22 = (struct SortItem **)*((_DWORD *)v18 + 6);
              else
                --v22;
              *v8 = v22;
            }
          }
          if ( (*(_BYTE *)a4 & 8) != 0 )
            goto LABEL_59;
          v23 = this[22];
          if ( !v23 )
            goto LABEL_59;
          v24 = *v22;
          v34[1] = (char *)v24 + 4;
          v34[0] = *((unsigned __int16 *)v24 + 1);
          v25 = QuickKey::Compare((QuickKey *)v34, (struct QuickKey *)(this + 23));
          if ( v25 )
          {
            if ( v23 == 1 )
              goto LABEL_56;
          }
          else
          {
            if ( v23 == 1 )
              goto LABEL_57;
            if ( v23 == 3 )
            {
LABEL_55:
              Err::SetError(a4, -1603, v26);
              this[2] = 3;
LABEL_58:
              this[23] = 0;
              this[22] = 0;
              goto LABEL_59;
            }
          }
          if ( v23 != 2 )
          {
            if ( v25 > 0 )
              goto LABEL_55;
            goto LABEL_59;
          }
LABEL_56:
          if ( v25 < 0 )
          {
LABEL_57:
            Err::SetError(a4, -1603, v26);
            this[2] = 1;
            goto LABEL_58;
          }
LABEL_59:
          v27 = 1;
LABEL_67:
          v7 = v30;
          v8 = v31;
          v29 = v30;
          if ( *v31 == *((struct SortItem ***)*v30 + 6) && *(int *)a4 < 8 )
          {
            if ( (*(_DWORD *)a4 & 0xFFFFFFFE) != 0 )
            {
              if ( *((_DWORD *)a4 + 3) )
                operator delete[](*((void **)a4 + 3));
              if ( *((_DWORD *)a4 + 4) )
                operator delete[](*((void **)a4 + 4));
            }
            v7 = v30;
            *(_DWORD *)a4 = 8;
            *((_DWORD *)a4 + 1) = -1603;
            *((_DWORD *)a4 + 2) = 0;
            *((_DWORD *)a4 + 3) = 0;
            *((_DWORD *)a4 + 4) = 0;
          }
          v6 = v32;
          if ( v32 <= 0 )
            goto LABEL_76;
          break;
        case 4u:
          if ( v9 < 8 )
          {
            if ( (v9 & 0xFFFFFFFE) != 0 )
            {
              if ( *((_DWORD *)a4 + 3) )
                operator delete[](*((void **)a4 + 3));
              if ( *((_DWORD *)a4 + 4) )
                operator delete[](*((void **)a4 + 4));
            }
            *(_DWORD *)a4 = 8;
            *((_DWORD *)a4 + 1) = -1906;
            *((_DWORD *)a4 + 2) = 0;
            *((_DWORD *)a4 + 3) = 0;
            *((_DWORD *)a4 + 4) = 0;
          }
          goto LABEL_67;
        default:
          goto LABEL_67;
      }
    }
  }
LABEL_76:
  result = 2;
  if ( (*(_BYTE *)a4 & 8) != 0 )
    result = v27;
  this[2] = result;
  return result;
}

```

## disassembly

```asm
0x1004c210  mov     edi, edi
0x1004c212  push    ebp
0x1004c213  mov     ebp, esp
0x1004c215  and     esp, 0FFFFFFF8h
0x1004c218  sub     esp, 24h
0x1004c21b  push    ebx
0x1004c21c  mov     ebx, [ebp+arg_8]
0x1004c21f  push    esi
0x1004c220  push    edi; unsigned int
0x1004c221  mov     edi, ecx
0x1004c223  push    ebx; void *
0x1004c224  mov     eax, [edi+8]
0x1004c227  mov     [esp+34h+var_24], eax
0x1004c22b  mov     eax, [edi+4]
0x1004c22e  mov     [esp+34h+var_20], eax
0x1004c232  mov     eax, [eax]
0x1004c234  mov     esi, [eax+7Ch]
0x1004c237  mov     ecx, esi
0x1004c239  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004c23f  mov     ecx, [esp+34h+var_20]
0x1004c243  call    esi
0x1004c245  cmp     dword ptr [edi+8], 0
0x1004c249  jnz     short loc_1004C289
0x1004c24b  push    ebx
0x1004c24c  mov     ecx, edi
0x1004c24e  call    ?WrapUpInput@SortMover@@AAE?AW4SrtMvrMode@@AAVErr@@@Z; SortMover::WrapUpInput(Err &)
0x1004c253  cmp     eax, 2
0x1004c256  jz      short loc_1004C289
0x1004c258  test    byte ptr [ebx], 8
0x1004c25b  jnz     loc_1004C5A6
0x1004c261  mov     eax, [esp+30h+var_20]
0x1004c265  push    ebx
0x1004c266  push    [ebp+arg_4]; unsigned int
0x1004c269  mov     edi, [eax+24h]
0x1004c26c  push    [ebp+arg_0]; void *
0x1004c26f  mov     esi, [edi]
0x1004c271  mov     esi, [esi+8]
0x1004c274  mov     ecx, esi
0x1004c276  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004c27c  mov     ecx, edi
0x1004c27e  call    esi
0x1004c280  pop     edi
0x1004c281  pop     esi
0x1004c282  pop     ebx
0x1004c283  mov     esp, ebp
0x1004c285  pop     ebp
0x1004c286  retn    0Ch
0x1004c289  mov     eax, [ebp+arg_0]
0x1004c28c  test    eax, eax
0x1004c28e  jnz     short loc_1004C2B1
0x1004c290  mov     ecx, [edi+0Ch]
0x1004c293  mov     eax, [edi+10h]
0x1004c296  cmp     eax, [ecx+18h]
0x1004c299  jnz     loc_1004C596
0x1004c29f  push    ecx
0x1004c2a0  push    0FFFFF9BDh
0x1004c2a5  mov     ecx, ebx
0x1004c2a7  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004c2ac  jmp     loc_1004C596
0x1004c2b1  jle     loc_1004C596
0x1004c2b7  lea     edx, [edi+0Ch]
0x1004c2ba  mov     [esp+30h+var_20], edx
0x1004c2be  lea     esi, [edi+10h]
0x1004c2c1  dec     eax
0x1004c2c2  mov     [esp+30h+var_18], esi
0x1004c2c6  mov     [esp+30h+var_14], eax
0x1004c2ca  mov     eax, [ebx]
0x1004c2cc  mov     [esp+30h+var_1C], edx
0x1004c2d0  test    al, 8
0x1004c2d2  jnz     loc_1004C596
0x1004c2d8  mov     ecx, [ebp+arg_4]
0x1004c2db  cmp     ecx, 4; switch 5 cases
0x1004c2de  ja      def_1004C2E4; jumptable 1004C2E4 default case
0x1004c2e4  jmp     ds:jpt_1004C2E4[ecx*4]; switch jump
0x1004c2eb  mov     ecx, [edx]; jumptable 1004C2E4 case 0
0x1004c2ed  push    ebx; struct Err *
0x1004c2ee  call    ?First@Sort@@QAEPAPAVSortItem@@AAVErr@@@Z; Sort::First(Err &)
0x1004c2f3  mov     [esi], eax
0x1004c2f5  mov     [esp+30h+var_24], 3
0x1004c2fd  jmp     def_1004C2E4; jumptable 1004C2E4 default case
0x1004c302  mov     eax, [edx]; jumptable 1004C2E4 case 1
0x1004c304  mov     ecx, [eax+0Ch]
0x1004c307  test    ecx, ecx
0x1004c309  jz      short loc_1004C323
0x1004c30b  mov     eax, [eax+14h]
0x1004c30e  mov     [esp+30h+var_24], 3
0x1004c316  lea     eax, [eax+ecx*4]
0x1004c319  add     eax, 0FFFFFFFCh
0x1004c31c  mov     [esi], eax
0x1004c31e  jmp     def_1004C2E4; jumptable 1004C2E4 default case
0x1004c323  mov     eax, [eax+18h]
0x1004c326  mov     [esi], eax
0x1004c328  mov     [esp+30h+var_24], 3
0x1004c330  jmp     def_1004C2E4; jumptable 1004C2E4 default case
0x1004c335  cmp     dword ptr [edi+8], 1; jumptable 1004C2E4 case 2
0x1004c339  mov     ecx, [edx]; this
0x1004c33b  jnz     short loc_1004C359
0x1004c33d  push    ebx; struct Err *
0x1004c33e  call    ?First@Sort@@QAEPAPAVSortItem@@AAVErr@@@Z; Sort::First(Err &)
0x1004c343  mov     ecx, [esp+30h+var_20]
0x1004c347  mov     [esi], eax
0x1004c349  mov     ecx, [ecx]
0x1004c34b  cmp     eax, [ecx+18h]
0x1004c34e  jz      short loc_1004C369
0x1004c350  mov     dword ptr [edi+8], 2
0x1004c357  jmp     short loc_1004C369
0x1004c359  mov     eax, [esi]
0x1004c35b  cmp     eax, [ecx+18h]
0x1004c35e  jz      short loc_1004C369
0x1004c360  push    ebx; struct Err *
0x1004c361  push    eax; struct SortItem **
0x1004c362  call    ?Next@Sort@@QAEPAPAVSortItem@@PAPAV2@AAVErr@@@Z; Sort::Next(SortItem * *,Err &)
0x1004c367  mov     [esi], eax
0x1004c369  test    byte ptr [ebx], 8
0x1004c36c  jnz     short loc_1004C3ED
0x1004c36e  mov     esi, [edi+58h]
0x1004c371  test    esi, esi
0x1004c373  jz      short loc_1004C3ED
0x1004c375  mov     ecx, [eax]
0x1004c377  lea     eax, [ecx+4]
0x1004c37a  mov     [esp+30h+var_C], eax
0x1004c37e  movzx   eax, word ptr [ecx+2]
0x1004c382  lea     ecx, [esp+30h+var_10]; this
0x1004c386  mov     [esp+30h+var_10], eax
0x1004c38a  lea     eax, [edi+5Ch]
0x1004c38d  push    eax; struct QuickKey *
0x1004c38e  call    ?Compare@QuickKey@@QBEHAAV1@@Z; QuickKey::Compare(QuickKey &)
0x1004c393  test    eax, eax
0x1004c395  jnz     short loc_1004C3A3
0x1004c397  cmp     esi, 1
0x1004c39a  jz      short loc_1004C3CB
0x1004c39c  cmp     esi, 3
0x1004c39f  jnz     short loc_1004C3A8
0x1004c3a1  jmp     short loc_1004C3B1
0x1004c3a3  cmp     esi, 1
0x1004c3a6  jz      short loc_1004C3C7
0x1004c3a8  cmp     esi, 2
0x1004c3ab  jz      short loc_1004C3C7
0x1004c3ad  test    eax, eax
0x1004c3af  jle     short loc_1004C3ED
0x1004c3b1  push    ecx
0x1004c3b2  push    0FFFFF9BDh
0x1004c3b7  mov     ecx, ebx
0x1004c3b9  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004c3be  mov     dword ptr [edi+8], 3
0x1004c3c5  jmp     short loc_1004C3DF
0x1004c3c7  test    eax, eax
0x1004c3c9  jns     short loc_1004C3ED
0x1004c3cb  push    ecx
0x1004c3cc  push    0FFFFF9BDh
0x1004c3d1  mov     ecx, ebx
0x1004c3d3  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004c3d8  mov     dword ptr [edi+8], 1
0x1004c3df  mov     dword ptr [edi+5Ch], 0
0x1004c3e6  mov     dword ptr [edi+58h], 0
0x1004c3ed  mov     [esp+30h+var_24], 3
0x1004c3f5  jmp     def_1004C2E4; jumptable 1004C2E4 default case
0x1004c3fa  cmp     dword ptr [edi+8], 3; jumptable 1004C2E4 case 3
0x1004c3fe  mov     edx, [edx]
0x1004c400  jnz     short loc_1004C42A
0x1004c402  mov     ecx, [edx+0Ch]
0x1004c405  test    ecx, ecx
0x1004c407  jz      short loc_1004C415
0x1004c409  mov     eax, [edx+14h]
0x1004c40c  dec     ecx
0x1004c40d  add     edx, 18h
0x1004c410  lea     ecx, [eax+ecx*4]
0x1004c413  jmp     short loc_1004C41B
0x1004c415  mov     ecx, [edx+18h]
0x1004c418  add     edx, 18h
0x1004c41b  mov     [esi], ecx
0x1004c41d  cmp     ecx, [edx]
0x1004c41f  jz      short loc_1004C441
0x1004c421  mov     dword ptr [edi+8], 2
0x1004c428  jmp     short loc_1004C441
0x1004c42a  mov     ecx, [esi]
0x1004c42c  mov     eax, [edx+18h]
0x1004c42f  cmp     ecx, eax
0x1004c431  jz      short loc_1004C441
0x1004c433  cmp     ecx, [edx+14h]
0x1004c436  jbe     short loc_1004C43D
0x1004c438  add     ecx, 0FFFFFFFCh
0x1004c43b  jmp     short loc_1004C43F
0x1004c43d  mov     ecx, eax
0x1004c43f  mov     [esi], ecx
0x1004c441  test    byte ptr [ebx], 8
0x1004c444  jnz     short loc_1004C4C5
0x1004c446  mov     esi, [edi+58h]
0x1004c449  test    esi, esi
0x1004c44b  jz      short loc_1004C4C5
0x1004c44d  mov     ecx, [ecx]
0x1004c44f  lea     eax, [ecx+4]
0x1004c452  mov     [esp+30h+var_4], eax
0x1004c456  movzx   eax, word ptr [ecx+2]
0x1004c45a  lea     ecx, [esp+30h+var_8]; this
0x1004c45e  mov     [esp+30h+var_8], eax
0x1004c462  lea     eax, [edi+5Ch]
0x1004c465  push    eax; struct QuickKey *
0x1004c466  call    ?Compare@QuickKey@@QBEHAAV1@@Z; QuickKey::Compare(QuickKey &)
0x1004c46b  test    eax, eax
0x1004c46d  jnz     short loc_1004C47B
0x1004c46f  cmp     esi, 1
0x1004c472  jz      short loc_1004C4A3
0x1004c474  cmp     esi, 3
0x1004c477  jnz     short loc_1004C480
0x1004c479  jmp     short loc_1004C489
0x1004c47b  cmp     esi, 1
0x1004c47e  jz      short loc_1004C49F
0x1004c480  cmp     esi, 2
0x1004c483  jz      short loc_1004C49F
0x1004c485  test    eax, eax
0x1004c487  jle     short loc_1004C4C5
0x1004c489  push    ecx
0x1004c48a  push    0FFFFF9BDh
0x1004c48f  mov     ecx, ebx
0x1004c491  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004c496  mov     dword ptr [edi+8], 3
0x1004c49d  jmp     short loc_1004C4B7
0x1004c49f  test    eax, eax
0x1004c4a1  jns     short loc_1004C4C5
0x1004c4a3  push    ecx
0x1004c4a4  push    0FFFFF9BDh
0x1004c4a9  mov     ecx, ebx
0x1004c4ab  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004c4b0  mov     dword ptr [edi+8], 1
0x1004c4b7  mov     dword ptr [edi+5Ch], 0
0x1004c4be  mov     dword ptr [edi+58h], 0
0x1004c4c5  mov     [esp+30h+var_24], 1
0x1004c4cd  jmp     short def_1004C2E4; jumptable 1004C2E4 default case
0x1004c4cf  cmp     eax, 8; jumptable 1004C2E4 case 4
0x1004c4d2  jge     short def_1004C2E4; jumptable 1004C2E4 default case
0x1004c4d4  test    eax, 0FFFFFFFEh
0x1004c4d9  jz      short loc_1004C4FB
0x1004c4db  mov     eax, [ebx+0Ch]
0x1004c4de  test    eax, eax
0x1004c4e0  jz      short loc_1004C4EB
0x1004c4e2  push    eax; Block
0x1004c4e3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004c4e8  add     esp, 4
0x1004c4eb  mov     eax, [ebx+10h]
0x1004c4ee  test    eax, eax
0x1004c4f0  jz      short loc_1004C4FB
0x1004c4f2  push    eax; Block
0x1004c4f3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004c4f8  add     esp, 4
0x1004c4fb  mov     dword ptr [ebx], 8
0x1004c501  mov     dword ptr [ebx+4], 0FFFFF88Eh
0x1004c508  mov     dword ptr [ebx+8], 0
0x1004c50f  mov     dword ptr [ebx+0Ch], 0
0x1004c516  mov     dword ptr [ebx+10h], 0
0x1004c51d  mov     ecx, [esp+30h+var_1C]; jumptable 1004C2E4 default case
0x1004c521  mov     edx, ecx
0x1004c523  mov     eax, [esp+30h+var_18]
0x1004c527  mov     esi, eax
0x1004c529  mov     [esp+30h+var_20], edx
0x1004c52d  mov     ecx, [ecx]
0x1004c52f  mov     eax, [eax]
0x1004c531  cmp     eax, [ecx+18h]
0x1004c534  jnz     short loc_1004C58A
0x1004c536  mov     eax, [ebx]
0x1004c538  cmp     eax, 8
0x1004c53b  jge     short loc_1004C58A
0x1004c53d  test    eax, 0FFFFFFFEh
0x1004c542  jz      short loc_1004C564
0x1004c544  mov     eax, [ebx+0Ch]
0x1004c547  test    eax, eax
0x1004c549  jz      short loc_1004C554
0x1004c54b  push    eax; Block
0x1004c54c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004c551  add     esp, 4
0x1004c554  mov     eax, [ebx+10h]
0x1004c557  test    eax, eax
0x1004c559  jz      short loc_1004C564
0x1004c55b  push    eax; Block
0x1004c55c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004c561  add     esp, 4
0x1004c564  mov     edx, [esp+30h+var_20]
0x1004c568  mov     dword ptr [ebx], 8
0x1004c56e  mov     dword ptr [ebx+4], 0FFFFF9BDh
0x1004c575  mov     dword ptr [ebx+8], 0
0x1004c57c  mov     dword ptr [ebx+0Ch], 0
0x1004c583  mov     dword ptr [ebx+10h], 0
0x1004c58a  mov     eax, [esp+30h+var_14]
0x1004c58e  test    eax, eax
0x1004c590  jg      loc_1004C2C1
0x1004c596  test    byte ptr [ebx], 8
0x1004c599  mov     eax, 2
0x1004c59e  cmovnz  eax, [esp+30h+var_24]
0x1004c5a3  mov     [edi+8], eax
0x1004c5a6  pop     edi
0x1004c5a7  pop     esi
0x1004c5a8  pop     ebx
0x1004c5a9  mov     esp, ebp
0x1004c5ab  pop     ebp
0x1004c5ac  retn    0Ch
```
