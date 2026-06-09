# WriteCellBlock

- ea: `0x1000c670`
- end: `0x1000c9df`
- name: `WriteCellBlock`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1000ca90`

## callees

- `0x1000c030`
- `0x1000c670`
- `0x1002611f`
- `0x10035510`
- `0x10035f40`

## pseudocode

```c
int __fastcall WriteCellBlock(int a1, _DWORD *a2, _WORD *a3, int a4)
{
  __int16 v4; // bx
  _DWORD *v5; // edi
  int v6; // ecx
  __int16 v7; // ax
  int i; // edx
  __int16 v9; // cx
  bool v10; // zf
  int v11; // esi
  _WORD *v12; // ebx
  int v13; // eax
  unsigned __int8 *v14; // ecx
  int v15; // eax
  int result; // eax
  int v17; // edx
  int v18; // eax
  int v19; // esi
  int v20; // ecx
  int v21; // ebx
  __int16 v22; // ax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  char *v26; // esi
  int v27; // ebx
  _DWORD *v28; // ecx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // ebx
  int v33; // eax
  __int16 v34; // [esp+10h] [ebp-88h]
  int v35; // [esp+14h] [ebp-84h]
  int v36; // [esp+1Ch] [ebp-7Ch]
  int v37; // [esp+20h] [ebp-78h]
  __int16 v38; // [esp+24h] [ebp-74h]
  int v39; // [esp+28h] [ebp-70h]
  __int16 v40; // [esp+2Ch] [ebp-6Ch] BYREF
  __int16 v41; // [esp+2Eh] [ebp-6Ah]
  int v42; // [esp+30h] [ebp-68h]
  _DWORD *v43; // [esp+34h] [ebp-64h]
  int v44; // [esp+38h] [ebp-60h]
  int v45; // [esp+3Ch] [ebp-5Ch]
  int v46; // [esp+40h] [ebp-58h] BYREF
  int v47; // [esp+44h] [ebp-54h]
  char v48[76]; // [esp+48h] [ebp-50h] BYREF

  v4 = 0;
  v5 = a2;
  v44 = a1;
  v43 = a2;
  v47 = a4;
  memset(v48, 0, 0x44u);
  v6 = a4;
  v40 = 215;
  if ( *(_DWORD *)(a4 + 8) && *(_DWORD *)(v47 + 132) )
  {
    v7 = 0;
    v4 = 31;
  }
  else
  {
    v7 = -1;
    for ( i = 0; i < 32; ++i )
    {
      if ( *(_DWORD *)(v6 + 4 * i + 8) )
      {
        v9 = i;
        v4 = i;
        if ( v7 != -1 )
          v9 = v7;
        v7 = v9;
        v6 = v47;
      }
    }
  }
  v10 = v5[9] == 5;
  v36 = v5[5];
  v42 = 4;
  if ( v10 && v4 > 0x3FFF )
    v4 = 0x3FFF;
  if ( v7 == -1 || (v11 = v7, v39 = v7, v45 = v4, v7 > v4) )
  {
LABEL_49:
    v31 = v5[5];
    *(_DWORD *)(v47 + 136) = v31;
    *(_DWORD *)v48 = v31 - v36;
    v41 = v42;
    v5[5] += (__int16)v42 + 4;
    if ( v5[6] != 1 )
      return 0;
    v32 = v44;
    v33 = BFWriteFile(*(_DWORD *)(v44 + 20), (char *)&v40, 4u);
    if ( !v33 )
    {
      v33 = BFWriteFile(*(_DWORD *)(v32 + 20), v48, v41);
      if ( !v33 )
        return 0;
    }
    result = dword_10001970[abs32(v33)];
    if ( result == -10 )
      return -10;
    return result;
  }
  v12 = pExcelRecordBuffer;
  v13 = v45;
  while ( 1 )
  {
    v14 = *(unsigned __int8 **)(v6 + 4 * v11 + 8);
    if ( v14 )
    {
      v46 = 1049096;
      *v12 = *(_WORD *)(v47 + 4) + v11;
      v12[1] = *v14;
      v12[2] = v14[1] + 1;
      v12[3] = *((_WORD *)v14 + 1);
      *((_DWORD *)v12 + 2) = 0;
      v12[6] = *((_WORD *)v14 + 2);
      v12[7] = *((_WORD *)v14 + 3);
      v5[5] += 20;
      if ( v5[6] == 1 )
      {
        v15 = BFWriteFile(*(_DWORD *)(v44 + 20), (char *)&v46, 4u);
        if ( v15 || (v15 = BFWriteFile(*(_DWORD *)(v44 + 20), (char *)v12, SHIWORD(v46))) != 0 )
        {
          result = dword_10001970[abs32(v15)];
          if ( result == -10 )
            result = -10;
          if ( result )
            return result;
        }
        v12 = pExcelRecordBuffer;
      }
      v13 = v45;
    }
    if ( ++v11 > v13 )
      break;
    v6 = v47;
  }
  v17 = v39;
  v18 = v5[5];
  v19 = v47;
  v20 = v45;
  v37 = v39;
  while ( 1 )
  {
    v21 = *(_DWORD *)(v19 + 4 * v17 + 8);
    v35 = v21;
    if ( v21 )
      break;
LABEL_48:
    v37 = ++v17;
    if ( v17 > v20 )
      goto LABEL_49;
  }
  if ( v17 == v39 )
    v22 = v18 - v36 - 20;
  else
    v22 = *((_WORD *)v5 + 10) - v18;
  v23 = v42;
  *(_WORD *)&v48[v42] = v22;
  v24 = v5[5];
  v42 = v23 + 2;
  v38 = v24;
  v25 = v17 + *(_DWORD *)(v19 + 4);
  v34 = v25;
  v46 = *(_DWORD *)(v21 + 16);
  if ( !v46 )
  {
LABEL_47:
    v20 = v45;
    LOWORD(v18) = v38;
    goto LABEL_48;
  }
  while ( 1 )
  {
    result = WriteCellRecord(v44, v5, a3, v25, &v46);
    if ( result )
      return result;
    v26 = *(char **)(v21 + 8);
    v27 = v46;
    if ( v26 )
    {
      while ( 1 )
      {
        if ( *((_WORD *)v26 + 3) == *(unsigned __int8 *)(v27 + 6) )
        {
          v28 = v43;
          v43[5] += *((__int16 *)v26 + 5) + 4;
          if ( v28[6] == 1 )
          {
            v29 = BFWriteFile(*(_DWORD *)(v44 + 20), v26 + 8, 4u);
            if ( v29 || (v29 = BFWriteFile(*(_DWORD *)(v44 + 20), v26 + 12, *((__int16 *)v26 + 5))) != 0 )
            {
              result = dword_10001970[abs32(v29)];
              if ( result == -10 )
                result = -10;
              if ( result )
                return result;
            }
          }
        }
        if ( (unsigned int)*((_WORD *)v26 + 3) <= *(unsigned __int8 *)(v27 + 6) )
        {
          v26 = *(char **)v26;
          if ( v26 )
            continue;
        }
        v5 = v43;
        break;
      }
    }
    v30 = *(_DWORD *)v27;
    v21 = v35;
    LOWORD(v25) = v34;
    v46 = v30;
    if ( !v30 )
    {
      v17 = v37;
      v19 = v47;
      goto LABEL_47;
    }
  }
}

```

## disassembly

```asm
0x1000c670  mov     edi, edi
0x1000c672  push    ebp
0x1000c673  mov     ebp, esp
0x1000c675  sub     esp, 8Ch
0x1000c67b  mov     eax, ___security_cookie
0x1000c680  xor     eax, ebp
0x1000c682  mov     [ebp+var_4], eax
0x1000c685  mov     eax, [ebp+arg_0]
0x1000c688  push    ebx
0x1000c689  push    esi
0x1000c68a  push    edi
0x1000c68b  push    44h ; 'D'; Size
0x1000c68d  mov     [ebp+var_80], eax
0x1000c690  xor     ebx, ebx
0x1000c692  mov     edi, edx
0x1000c694  mov     [ebp+var_60], ecx
0x1000c697  mov     edx, [ebp+arg_4]
0x1000c69a  lea     eax, [ebp+var_50]
0x1000c69d  push    ebx; Val
0x1000c69e  push    eax; void *
0x1000c69f  mov     [ebp+var_64], edi
0x1000c6a2  mov     [ebp+var_54], edx
0x1000c6a5  call    _memset
0x1000c6aa  mov     ecx, [ebp+var_54]
0x1000c6ad  add     esp, 0Ch
0x1000c6b0  mov     eax, 0D7h
0x1000c6b5  mov     [ebp+var_6C], ax
0x1000c6b9  cmp     [ecx+8], ebx
0x1000c6bc  jz      short loc_1000C6CD
0x1000c6be  cmp     [ecx+84h], ebx
0x1000c6c4  jz      short loc_1000C6CD
0x1000c6c6  xor     eax, eax
0x1000c6c8  lea     ebx, [eax+1Fh]
0x1000c6cb  jmp     short loc_1000C6F8
0x1000c6cd  or      eax, 0FFFFFFFFh
0x1000c6d0  xor     edx, edx
0x1000c6d2  cmp     dword ptr [ecx+edx*4+8], 0
0x1000c6d7  movzx   esi, ax
0x1000c6da  jz      short loc_1000C6F2
0x1000c6dc  movzx   eax, dx
0x1000c6df  cmp     si, 0FFFFh
0x1000c6e3  mov     ecx, eax
0x1000c6e5  mov     ebx, eax
0x1000c6e7  mov     eax, esi
0x1000c6e9  cmovnz  ecx, eax
0x1000c6ec  movzx   eax, cx
0x1000c6ef  mov     ecx, [ebp+var_54]
0x1000c6f2  inc     edx
0x1000c6f3  cmp     edx, 20h ; ' '
0x1000c6f6  jl      short loc_1000C6D2
0x1000c6f8  cmp     dword ptr [edi+24h], 5
0x1000c6fc  mov     edx, [edi+14h]
0x1000c6ff  mov     [ebp+var_7C], edx
0x1000c702  mov     [ebp+var_68], 4
0x1000c709  jnz     short loc_1000C716
0x1000c70b  mov     edx, 3FFFh
0x1000c710  cmp     bx, dx
0x1000c713  cmovg   ebx, edx
0x1000c716  mov     esi, 0FFFFFFF6h
0x1000c71b  cmp     ax, 0FFFFh
0x1000c71f  jz      loc_1000C954
0x1000c725  cwde
0x1000c726  movsx   ebx, bx
0x1000c729  mov     esi, eax
0x1000c72b  mov     [ebp+var_70], eax
0x1000c72e  mov     [ebp+var_5C], ebx
0x1000c731  cmp     esi, ebx
0x1000c733  jg      loc_1000C94F
0x1000c739  mov     ebx, _pExcelRecordBuffer
0x1000c73f  mov     edx, 208h
0x1000c744  mov     eax, [ebp+var_5C]
0x1000c747  nop     word ptr [eax+eax+00000000h]
0x1000c750  mov     ecx, [ecx+esi*4+8]
0x1000c754  test    ecx, ecx
0x1000c756  jz      loc_1000C7FE
0x1000c75c  mov     edx, [ebp+var_54]
0x1000c75f  mov     eax, esi
0x1000c761  mov     [ebp+var_58], 100208h
0x1000c768  add     ax, [edx+4]
0x1000c76c  mov     [ebx], ax
0x1000c76f  movzx   eax, byte ptr [ecx]
0x1000c772  mov     [ebx+2], ax
0x1000c776  movzx   eax, byte ptr [ecx+1]
0x1000c77a  inc     ax
0x1000c77c  mov     [ebx+4], ax
0x1000c780  movzx   eax, word ptr [ecx+2]
0x1000c784  mov     [ebx+6], ax
0x1000c788  xor     eax, eax
0x1000c78a  mov     [ebx+8], eax
0x1000c78d  movzx   eax, word ptr [ecx+4]
0x1000c791  mov     [ebx+0Ch], ax
0x1000c795  movzx   eax, word ptr [ecx+6]
0x1000c799  mov     [ebx+0Eh], ax
0x1000c79d  add     dword ptr [edi+14h], 14h
0x1000c7a1  cmp     dword ptr [edi+18h], 1
0x1000c7a5  jnz     short loc_1000C7F6
0x1000c7a7  mov     eax, [ebp+var_60]
0x1000c7aa  lea     edx, [ebp+var_58]
0x1000c7ad  push    4
0x1000c7af  mov     ecx, [eax+14h]
0x1000c7b2  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c7b7  test    eax, eax
0x1000c7b9  jnz     short loc_1000C7D1
0x1000c7bb  movsx   eax, word ptr [ebp+var_58+2]
0x1000c7bf  mov     edx, ebx
0x1000c7c1  push    eax
0x1000c7c2  mov     eax, [ebp+var_60]
0x1000c7c5  mov     ecx, [eax+14h]
0x1000c7c8  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c7cd  test    eax, eax
0x1000c7cf  jz      short loc_1000C7F0
0x1000c7d1  cdq
0x1000c7d2  mov     ecx, 0FFFFFFF6h
0x1000c7d7  xor     eax, edx
0x1000c7d9  sub     eax, edx
0x1000c7db  mov     eax, ds:dword_10001970[eax*4]
0x1000c7e2  cmp     eax, 0FFFFFFF6h
0x1000c7e5  cmovz   eax, ecx
0x1000c7e8  test    eax, eax
0x1000c7ea  jnz     loc_1000C9CC
0x1000c7f0  mov     ebx, _pExcelRecordBuffer
0x1000c7f6  mov     eax, [ebp+var_5C]
0x1000c7f9  mov     edx, 208h
0x1000c7fe  inc     esi
0x1000c7ff  cmp     esi, eax
0x1000c801  jg      short loc_1000C80B
0x1000c803  mov     ecx, [ebp+var_54]
0x1000c806  jmp     loc_1000C750
0x1000c80b  mov     edx, [ebp+var_70]
0x1000c80e  mov     eax, [edi+14h]
0x1000c811  mov     esi, [ebp+var_54]
0x1000c814  mov     ecx, [ebp+var_5C]
0x1000c817  mov     [ebp+var_78], edx
0x1000c81a  nop     word ptr [eax+eax+00h]
0x1000c820  mov     ebx, [esi+edx*4+8]
0x1000c824  mov     [ebp+var_84], ebx
0x1000c82a  test    ebx, ebx
0x1000c82c  jz      loc_1000C943
0x1000c832  movzx   ecx, ax
0x1000c835  cmp     edx, [ebp+var_70]
0x1000c838  jnz     short loc_1000C845
0x1000c83a  sub     ecx, [ebp+var_7C]
0x1000c83d  sub     ecx, 14h
0x1000c840  movzx   eax, cx
0x1000c843  jmp     short loc_1000C84F
0x1000c845  mov     ax, [edi+14h]
0x1000c849  sub     ax, cx
0x1000c84c  movzx   eax, ax
0x1000c84f  mov     ecx, [ebp+var_68]
0x1000c852  mov     word ptr [ebp+ecx+var_50], ax
0x1000c857  add     ecx, 2
0x1000c85a  mov     eax, [edi+14h]
0x1000c85d  mov     [ebp+var_68], ecx
0x1000c860  mov     ecx, [esi+4]
0x1000c863  mov     [ebp+var_74], eax
0x1000c866  add     ecx, edx
0x1000c868  mov     eax, [ebx+10h]
0x1000c86b  mov     [ebp+var_88], ecx
0x1000c871  mov     [ebp+var_58], eax
0x1000c874  test    eax, eax
0x1000c876  jz      loc_1000C93D
0x1000c87c  nop     dword ptr [eax+00h]
0x1000c880  lea     eax, [ebp+var_58]
0x1000c883  mov     edx, edi
0x1000c885  push    eax
0x1000c886  push    ecx
0x1000c887  push    [ebp+var_80]
0x1000c88a  mov     ecx, [ebp+var_60]
0x1000c88d  call    WriteCellRecord
0x1000c892  test    eax, eax
0x1000c894  jnz     loc_1000C9CC
0x1000c89a  mov     esi, [ebx+8]
0x1000c89d  mov     ebx, [ebp+var_58]
0x1000c8a0  test    esi, esi
0x1000c8a2  jz      short loc_1000C91E
0x1000c8a4  movzx   eax, byte ptr [ebx+6]
0x1000c8a8  cmp     [esi+6], ax
0x1000c8ac  jnz     short loc_1000C90B
0x1000c8ae  mov     ecx, [ebp+var_64]
0x1000c8b1  movsx   eax, word ptr [esi+0Ah]
0x1000c8b5  add     eax, 4
0x1000c8b8  add     [ecx+14h], eax
0x1000c8bb  cmp     dword ptr [ecx+18h], 1
0x1000c8bf  jnz     short loc_1000C90B
0x1000c8c1  mov     eax, [ebp+var_60]
0x1000c8c4  lea     edx, [esi+8]
0x1000c8c7  push    4
0x1000c8c9  mov     ecx, [eax+14h]
0x1000c8cc  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c8d1  test    eax, eax
0x1000c8d3  jnz     short loc_1000C8EC
0x1000c8d5  movsx   eax, word ptr [esi+0Ah]
0x1000c8d9  lea     edx, [esi+0Ch]
0x1000c8dc  push    eax
0x1000c8dd  mov     eax, [ebp+var_60]
0x1000c8e0  mov     ecx, [eax+14h]
0x1000c8e3  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c8e8  test    eax, eax
0x1000c8ea  jz      short loc_1000C90B
0x1000c8ec  cdq
0x1000c8ed  mov     ecx, 0FFFFFFF6h
0x1000c8f2  xor     eax, edx
0x1000c8f4  sub     eax, edx
0x1000c8f6  mov     eax, ds:dword_10001970[eax*4]
0x1000c8fd  cmp     eax, 0FFFFFFF6h
0x1000c900  cmovz   eax, ecx
0x1000c903  test    eax, eax
0x1000c905  jnz     loc_1000C9CC
0x1000c90b  movzx   eax, byte ptr [ebx+6]
0x1000c90f  cmp     [esi+6], ax
0x1000c913  ja      short loc_1000C91B
0x1000c915  mov     esi, [esi]
0x1000c917  test    esi, esi
0x1000c919  jnz     short loc_1000C8A4
0x1000c91b  mov     edi, [ebp+var_64]
0x1000c91e  mov     eax, [ebx]
0x1000c920  mov     ebx, [ebp+var_84]
0x1000c926  mov     ecx, [ebp+var_88]
0x1000c92c  mov     [ebp+var_58], eax
0x1000c92f  test    eax, eax
0x1000c931  jnz     loc_1000C880
0x1000c937  mov     edx, [ebp+var_78]
0x1000c93a  mov     esi, [ebp+var_54]
0x1000c93d  mov     ecx, [ebp+var_5C]
0x1000c940  mov     eax, [ebp+var_74]
0x1000c943  inc     edx
0x1000c944  mov     [ebp+var_78], edx
0x1000c947  cmp     edx, ecx
0x1000c949  jle     loc_1000C820
0x1000c94f  mov     esi, 0FFFFFFF6h
0x1000c954  mov     edx, [ebp+var_54]
0x1000c957  mov     eax, [edi+14h]
0x1000c95a  mov     [edx+88h], eax
0x1000c960  sub     eax, [ebp+var_7C]
0x1000c963  mov     dword ptr [ebp+var_50], eax
0x1000c966  mov     eax, [ebp+var_68]
0x1000c969  movzx   eax, ax
0x1000c96c  mov     [ebp+var_6A], ax
0x1000c970  cwde
0x1000c971  add     eax, 4
0x1000c974  add     [edi+14h], eax
0x1000c977  cmp     dword ptr [edi+18h], 1
0x1000c97b  jnz     short loc_1000C9CA
0x1000c97d  mov     ebx, [ebp+var_60]
0x1000c980  lea     edx, [ebp+var_6C]
0x1000c983  push    4
0x1000c985  mov     ecx, [ebx+14h]
0x1000c988  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c98d  test    eax, eax
0x1000c98f  jnz     short loc_1000C9A5
0x1000c991  movsx   eax, [ebp+var_6A]
0x1000c995  lea     edx, [ebp+var_50]
0x1000c998  mov     ecx, [ebx+14h]
0x1000c99b  push    eax
0x1000c99c  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000c9a1  test    eax, eax
0x1000c9a3  jz      short loc_1000C9CA
0x1000c9a5  cdq
0x1000c9a6  xor     eax, edx
0x1000c9a8  sub     eax, edx
0x1000c9aa  mov     eax, ds:dword_10001970[eax*4]
0x1000c9b1  cmp     eax, 0FFFFFFF6h
0x1000c9b4  cmovz   eax, esi
0x1000c9b7  pop     edi
0x1000c9b8  pop     esi
0x1000c9b9  pop     ebx
0x1000c9ba  mov     ecx, [ebp+var_4]
0x1000c9bd  xor     ecx, ebp; StackCookie
0x1000c9bf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000c9c4  mov     esp, ebp
0x1000c9c6  pop     ebp
0x1000c9c7  retn    8
0x1000c9ca  xor     eax, eax
0x1000c9cc  mov     ecx, [ebp+var_4]
0x1000c9cf  pop     edi
0x1000c9d0  pop     esi
0x1000c9d1  xor     ecx, ebp; StackCookie
0x1000c9d3  pop     ebx
0x1000c9d4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000c9d9  mov     esp, ebp
0x1000c9db  pop     ebp
0x1000c9dc  retn    8
```
