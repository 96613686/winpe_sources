# TblPage::CreatePhysicalIndexes(Table *,tagPhysIndexDef *,long,Err &)

- ea: `0x1005bdb0`
- end: `0x1005c0dc`
- name: `?CreatePhysicalIndexes@TblPage@@AAEJPAVTable@@PAUtagPhysIndexDef@@JAAVErr@@@Z`
- size: `812`
- prototype: `int __thiscall(TblPage *__hidden this, struct Table *, struct tagPhysIndexDef *, int, struct Err *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1005ab70`

## callees

- `0x10031210`
- `0x10031850`
- `0x1005bdb0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f180`

## pseudocode

```c
int __thiscall TblPage::CreatePhysicalIndexes(
        TblPage *this,
        struct Table *a2,
        struct tagPhysIndexDef *a3,
        int a4,
        struct Err *a5)
{
  int v5; // ecx
  struct Err *v6; // ebx
  bool v7; // zf
  int v8; // ebx
  char *v9; // edi
  int v10; // ecx
  __int16 v11; // si
  int v12; // edx
  int v13; // edi
  PhysicalIndex *v14; // esi
  char v15; // t0
  char v16; // al
  char v17; // cl
  int i; // edi
  char *v19; // edx
  struct Table *v20; // eax
  int v21; // ecx
  int j; // edi
  void **v24; // esi
  _DWORD *v25; // ebx
  PhysicalIndex *Block; // [esp+10h] [ebp-20h]
  int v28; // [esp+18h] [ebp-18h]
  char *v29; // [esp+1Ch] [ebp-14h]
  int v30; // [esp+20h] [ebp-10h]

  v30 = *((_DWORD *)this + 1);
  v5 = *(_DWORD *)(v30 + 23);
  if ( v5 <= 32 )
  {
    v8 = 0;
    if ( v5 <= 0 )
    {
LABEL_14:
      v13 = 0;
      v28 = 0;
      if ( v5 <= 0 )
        return 39 * v13;
      v6 = a5;
      while ( 1 )
      {
        v29 = (char *)a3 + 39 * v13;
        Block = (PhysicalIndex *)operator new(0x4Cu);
        v14 = PhysicalIndex::PhysicalIndex(Block, a2, 10, v6);
        if ( !v14 && *(int *)v6 < 8 )
        {
          if ( (*(_DWORD *)v6 & 0xFFFFFFFE) != 0 )
          {
            if ( *((_DWORD *)v6 + 3) )
              operator delete[](*((void **)v6 + 3));
            if ( *((_DWORD *)v6 + 4) )
              operator delete[](*((void **)v6 + 4));
          }
          *(_DWORD *)v6 = 8;
          *((_DWORD *)v6 + 1) = -1011;
          *((_DWORD *)v6 + 2) = 0;
          *((_DWORD *)v6 + 3) = 0;
          *((_DWORD *)v6 + 4) = 0;
        }
        if ( (*(_BYTE *)v6 & 8) != 0 )
        {
          if ( v14 )
          {
            if ( *((_DWORD *)v14 + 7) )
              operator delete[](*((void **)v14 + 7));
            if ( *(_DWORD *)v14 )
              operator delete[](*(void **)v14);
            operator delete(v14, 0x4Cu);
          }
          goto LABEL_46;
        }
        v15 = *((_BYTE *)v14 + 64) ^ (*((_BYTE *)v14 + 64) ^ v29[38]) & 1;
        *((_BYTE *)v14 + 64) = v15;
        v16 = v15 ^ (v15 ^ v29[38]) & 2;
        *((_BYTE *)v14 + 64) = v16;
        v17 = v16 ^ (v16 ^ v29[38]) & 4;
        *((_BYTE *)v14 + 64) = v17;
        *((_BYTE *)v14 + 64) = v17 ^ (v17 ^ v29[38]) & 8;
        *((_DWORD *)v14 + 14) = *(_DWORD *)(v29 + 30);
        *((_DWORD *)v14 + 6) = *(_DWORD *)(v29 + 34);
        *((_DWORD *)v14 + 10) = *(_DWORD *)(v30 + 8 * v13 + 35);
        *((_DWORD *)v14 + 12) = *(_DWORD *)(v30 + 8 * v13 + 39);
        memset(*((void **)v14 + 7), 0, 0x50u);
        for ( i = 0; i < 10; ++i )
        {
          v19 = &v29[2 * i];
          *(_DWORD *)(*((_DWORD *)v14 + 7) + 8 * i) = *(__int16 *)&v19[i];
          *(_BYTE *)(*((_DWORD *)v14 + 7) + 8 * i + 4) = v19[i + 2];
          if ( *(_DWORD *)(*((_DWORD *)v14 + 7) + 8 * i) == -1 )
            break;
          ++*((_DWORD *)v14 + 8);
        }
        v20 = a2;
        v21 = *((_DWORD *)v14 + 8);
        v6 = a5;
        if ( v21 > *((_DWORD *)a2 + 3) || v21 < 0 )
          break;
        *((_DWORD *)v14 + 15) = v28;
        *((_DWORD *)a2 + v28 + 413) = v14;
        PhysicalIndex::SetColumnTracking(v14, a5);
        v13 = v28 + 1;
        *((_DWORD *)v14 + 4) = 0;
        v28 = v13;
        if ( v13 >= *(_DWORD *)(*((_DWORD *)this + 1) + 23) )
          return 39 * v13;
      }
      if ( *(int *)a5 >= 8 )
        goto LABEL_47;
      v7 = (*(_DWORD *)a5 & 0xFFFFFFFE) == 0;
      goto LABEL_34;
    }
LABEL_5:
    v9 = (char *)a3 + 39 * v8;
    if ( (*(_DWORD *)(v9 + 30) & 0xFFFFFF00) <= 0x8000000 && *(_DWORD *)(v9 + 34) <= 0x80000u )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = *(_WORD *)&v9[2 * v10 + v10];
        if ( v11 != -1 )
        {
          v12 = *((_DWORD *)a2 + 3);
          if ( v10 >= v12 || v11 < 0 || v11 > v12 )
            break;
        }
        if ( ++v10 >= 10 )
        {
          ++v8;
          v5 = *(_DWORD *)(v30 + 23);
          if ( v8 < v5 )
            goto LABEL_5;
          goto LABEL_14;
        }
      }
    }
  }
  v6 = a5;
  if ( *(int *)a5 >= 8 )
    goto LABEL_46;
  v7 = (*(_DWORD *)a5 & 0xFFFFFFFE) == 0;
LABEL_34:
  if ( !v7 )
  {
    if ( *((_DWORD *)v6 + 3) )
      operator delete[](*((void **)v6 + 3));
    if ( *((_DWORD *)v6 + 4) )
      operator delete[](*((void **)v6 + 4));
  }
  *(_DWORD *)v6 = 8;
  *((_DWORD *)v6 + 1) = -1206;
  *((_DWORD *)v6 + 2) = 0;
  *((_DWORD *)v6 + 3) = 0;
  *((_DWORD *)v6 + 4) = 0;
LABEL_46:
  v20 = a2;
LABEL_47:
  for ( j = 413; j != 445; ++j )
  {
    v24 = (void **)*((_DWORD *)v20 + j);
    v25 = (_DWORD *)((char *)v20 + 4 * j);
    if ( v24 )
    {
      if ( v24[7] )
        operator delete[](v24[7]);
      if ( *v24 )
        operator delete[](*v24);
      operator delete(v24, 0x4Cu);
      v20 = a2;
      *v25 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1005bdb0  mov     edi, edi
0x1005bdb2  push    ebp
0x1005bdb3  mov     ebp, esp
0x1005bdb5  push    0FFFFFFFFh
0x1005bdb7  push    offset ?CreatePhysicalIndexes@TblPage@@AAEJPAVTable@@PAUtagPhysIndexDef@@JAAVErr@@@Z_SEH
0x1005bdbc  mov     eax, large fs:0
0x1005bdc2  push    eax
0x1005bdc3  sub     esp, 14h
0x1005bdc6  push    ebx
0x1005bdc7  push    esi
0x1005bdc8  push    edi
0x1005bdc9  mov     eax, ___security_cookie
0x1005bdce  xor     eax, ebp
0x1005bdd0  push    eax
0x1005bdd1  lea     eax, [ebp+var_C]
0x1005bdd4  mov     large fs:0, eax
0x1005bdda  mov     eax, ecx
0x1005bddc  mov     [ebp+var_1C], eax
0x1005bddf  mov     eax, [eax+4]
0x1005bde2  mov     [ebp+var_10], eax
0x1005bde5  mov     ecx, [eax+17h]
0x1005bde8  cmp     ecx, 20h ; ' '
0x1005bdeb  jle     short loc_1005BE05
0x1005bded  mov     ebx, [ebp+arg_C]
0x1005bdf0  mov     eax, [ebx]
0x1005bdf2  cmp     eax, 8
0x1005bdf5  jge     loc_1005C073
0x1005bdfb  test    eax, 0FFFFFFFEh
0x1005be00  jmp     loc_1005BFFF
0x1005be05  xor     ebx, ebx
0x1005be07  test    ecx, ecx
0x1005be09  jle     short loc_1005BE66
0x1005be0b  nop     dword ptr [eax+eax+00h]
0x1005be10  imul    edi, ebx, 27h ; '''
0x1005be13  add     edi, [ebp+arg_4]
0x1005be16  mov     eax, [edi+1Eh]
0x1005be19  and     eax, 0FFFFFF00h
0x1005be1e  cmp     eax, 8000000h
0x1005be23  ja      short loc_1005BDED
0x1005be25  cmp     dword ptr [edi+22h], 80000h
0x1005be2c  ja      short loc_1005BDED
0x1005be2e  xor     ecx, ecx
0x1005be30  lea     eax, [edi+ecx*2]
0x1005be33  movzx   eax, word ptr [ecx+eax]
0x1005be37  mov     esi, eax
0x1005be39  cmp     ax, 0FFFFh
0x1005be3d  jz      short loc_1005BE55
0x1005be3f  mov     eax, [ebp+arg_0]
0x1005be42  mov     edx, [eax+0Ch]
0x1005be45  cmp     ecx, edx
0x1005be47  jge     short loc_1005BDED
0x1005be49  test    si, si
0x1005be4c  js      short loc_1005BDED
0x1005be4e  movsx   eax, si
0x1005be51  cmp     eax, edx
0x1005be53  jg      short loc_1005BDED
0x1005be55  inc     ecx
0x1005be56  cmp     ecx, 0Ah
0x1005be59  jl      short loc_1005BE30
0x1005be5b  mov     eax, [ebp+var_10]
0x1005be5e  inc     ebx
0x1005be5f  mov     ecx, [eax+17h]
0x1005be62  cmp     ebx, ecx
0x1005be64  jl      short loc_1005BE10
0x1005be66  xor     edi, edi
0x1005be68  mov     [ebp+var_18], edi
0x1005be6b  test    ecx, ecx
0x1005be6d  jle     loc_1005BFDB
0x1005be73  mov     ebx, [ebp+arg_C]
0x1005be76  imul    eax, edi, 27h ; '''
0x1005be79  push    4Ch ; 'L'; Size
0x1005be7b  add     eax, [ebp+arg_4]
0x1005be7e  mov     [ebp+var_14], eax
0x1005be81  call    ??2@YAPAXI@Z; operator new(uint)
0x1005be86  add     esp, 4
0x1005be89  mov     [ebp+Block], eax
0x1005be8c  push    ebx; struct Err *
0x1005be8d  push    0Ah; int
0x1005be8f  push    [ebp+arg_0]; struct Table *
0x1005be92  mov     ecx, eax; this
0x1005be94  mov     [ebp+var_4], 0
0x1005be9b  call    ??0PhysicalIndex@@QAE@PAVTable@@HAAVErr@@@Z; PhysicalIndex::PhysicalIndex(Table *,int,Err &)
0x1005bea0  mov     esi, eax
0x1005bea2  mov     [ebp+var_4], 0FFFFFFFFh
0x1005bea9  test    esi, esi
0x1005beab  jnz     short loc_1005BEFD
0x1005bead  mov     eax, [ebx]
0x1005beaf  cmp     eax, 8
0x1005beb2  jge     short loc_1005BEFD
0x1005beb4  test    eax, 0FFFFFFFEh
0x1005beb9  jz      short loc_1005BEDB
0x1005bebb  mov     eax, [ebx+0Ch]
0x1005bebe  test    eax, eax
0x1005bec0  jz      short loc_1005BECB
0x1005bec2  push    eax; Block
0x1005bec3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005bec8  add     esp, 4
0x1005becb  mov     eax, [ebx+10h]
0x1005bece  test    eax, eax
0x1005bed0  jz      short loc_1005BEDB
0x1005bed2  push    eax; Block
0x1005bed3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005bed8  add     esp, 4
0x1005bedb  mov     dword ptr [ebx], 8
0x1005bee1  mov     dword ptr [ebx+4], 0FFFFFC0Dh
0x1005bee8  mov     dword ptr [ebx+8], 0
0x1005beef  mov     dword ptr [ebx+0Ch], 0
0x1005bef6  mov     dword ptr [ebx+10h], 0
0x1005befd  test    byte ptr [ebx], 8
0x1005bf00  jnz     loc_1005C045
0x1005bf06  mov     edx, [ebp+var_14]
0x1005bf09  push    50h ; 'P'; Size
0x1005bf0b  push    0; Val
0x1005bf0d  mov     cl, [edx+26h]
0x1005bf10  xor     cl, [esi+40h]
0x1005bf13  and     cl, 1
0x1005bf16  xor     cl, [esi+40h]
0x1005bf19  mov     [esi+40h], cl
0x1005bf1c  mov     al, [edx+26h]
0x1005bf1f  xor     al, cl
0x1005bf21  and     al, 2
0x1005bf23  xor     al, cl
0x1005bf25  mov     [esi+40h], al
0x1005bf28  mov     cl, [edx+26h]
0x1005bf2b  xor     cl, al
0x1005bf2d  and     cl, 4
0x1005bf30  xor     cl, al
0x1005bf32  mov     [esi+40h], cl
0x1005bf35  movzx   eax, byte ptr [edx+26h]
0x1005bf39  xor     al, cl
0x1005bf3b  and     al, 8
0x1005bf3d  xor     al, cl
0x1005bf3f  mov     ecx, [ebp+var_10]
0x1005bf42  mov     [esi+40h], al
0x1005bf45  mov     eax, [edx+1Eh]
0x1005bf48  mov     [esi+38h], eax
0x1005bf4b  mov     eax, [edx+22h]
0x1005bf4e  mov     [esi+18h], eax
0x1005bf51  mov     eax, [ecx+edi*8+23h]
0x1005bf55  mov     [esi+28h], eax
0x1005bf58  mov     eax, [ecx+edi*8+27h]
0x1005bf5c  mov     [esi+30h], eax
0x1005bf5f  push    dword ptr [esi+1Ch]; void *
0x1005bf62  call    _memset
0x1005bf67  mov     ebx, [ebp+var_14]
0x1005bf6a  add     esp, 0Ch
0x1005bf6d  xor     edi, edi
0x1005bf6f  nop
0x1005bf70  mov     eax, [esi+1Ch]
0x1005bf73  lea     edx, [ebx+edi*2]
0x1005bf76  movsx   ecx, word ptr [edx+edi]
0x1005bf7a  mov     [eax+edi*8], ecx
0x1005bf7d  mov     ecx, [esi+1Ch]
0x1005bf80  mov     al, [edx+edi+2]
0x1005bf84  mov     [ecx+edi*8+4], al
0x1005bf88  mov     eax, [esi+1Ch]
0x1005bf8b  cmp     dword ptr [eax+edi*8], 0FFFFFFFFh
0x1005bf8f  jz      short loc_1005BF9A
0x1005bf91  inc     dword ptr [esi+20h]
0x1005bf94  inc     edi
0x1005bf95  cmp     edi, 0Ah
0x1005bf98  jl      short loc_1005BF70
0x1005bf9a  mov     eax, [ebp+arg_0]
0x1005bf9d  mov     ecx, [esi+20h]
0x1005bfa0  mov     ebx, [ebp+arg_C]
0x1005bfa3  cmp     ecx, [eax+0Ch]
0x1005bfa6  jg      short loc_1005BFF2
0x1005bfa8  test    ecx, ecx
0x1005bfaa  js      short loc_1005BFF2
0x1005bfac  mov     edi, [ebp+var_18]
0x1005bfaf  mov     ecx, esi; this
0x1005bfb1  mov     [esi+3Ch], edi
0x1005bfb4  push    ebx; struct Err *
0x1005bfb5  mov     [eax+edi*4+674h], esi
0x1005bfbc  call    ?SetColumnTracking@PhysicalIndex@@QAEXAAVErr@@@Z; PhysicalIndex::SetColumnTracking(Err &)
0x1005bfc1  mov     eax, [ebp+var_1C]
0x1005bfc4  inc     edi
0x1005bfc5  mov     dword ptr [esi+10h], 0
0x1005bfcc  mov     [ebp+var_18], edi
0x1005bfcf  mov     eax, [eax+4]
0x1005bfd2  cmp     edi, [eax+17h]
0x1005bfd5  jl      loc_1005BE76
0x1005bfdb  imul    eax, edi, 27h ; '''
0x1005bfde  mov     ecx, [ebp+var_C]
0x1005bfe1  mov     large fs:0, ecx
0x1005bfe8  pop     ecx
0x1005bfe9  pop     edi
0x1005bfea  pop     esi
0x1005bfeb  pop     ebx
0x1005bfec  mov     esp, ebp
0x1005bfee  pop     ebp
0x1005bfef  retn    10h
0x1005bff2  mov     ecx, [ebx]
0x1005bff4  cmp     ecx, 8
0x1005bff7  jge     short loc_1005C076
0x1005bff9  test    ecx, 0FFFFFFFEh
0x1005bfff  jz      short loc_1005C021
0x1005c001  mov     eax, [ebx+0Ch]
0x1005c004  test    eax, eax
0x1005c006  jz      short loc_1005C011
0x1005c008  push    eax; Block
0x1005c009  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c00e  add     esp, 4
0x1005c011  mov     eax, [ebx+10h]
0x1005c014  test    eax, eax
0x1005c016  jz      short loc_1005C021
0x1005c018  push    eax; Block
0x1005c019  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c01e  add     esp, 4
0x1005c021  mov     dword ptr [ebx], 8
0x1005c027  mov     dword ptr [ebx+4], 0FFFFFB4Ah
0x1005c02e  mov     dword ptr [ebx+8], 0
0x1005c035  mov     dword ptr [ebx+0Ch], 0
0x1005c03c  mov     dword ptr [ebx+10h], 0
0x1005c043  jmp     short loc_1005C073
0x1005c045  test    esi, esi
0x1005c047  jz      short loc_1005C073
0x1005c049  mov     eax, [esi+1Ch]
0x1005c04c  test    eax, eax
0x1005c04e  jz      short loc_1005C059
0x1005c050  push    eax; Block
0x1005c051  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c056  add     esp, 4
0x1005c059  mov     eax, [esi]
0x1005c05b  test    eax, eax
0x1005c05d  jz      short loc_1005C068
0x1005c05f  push    eax; Block
0x1005c060  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c065  add     esp, 4
0x1005c068  push    4Ch ; 'L'; unsigned int
0x1005c06a  push    esi; Block
0x1005c06b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005c070  add     esp, 8
0x1005c073  mov     eax, [ebp+arg_0]
0x1005c076  mov     edi, 19Dh
0x1005c07b  nop     dword ptr [eax+eax+00h]
0x1005c080  mov     esi, [eax+edi*4]
0x1005c083  lea     ebx, [eax+edi*4]
0x1005c086  test    esi, esi
0x1005c088  jz      short loc_1005C0BD
0x1005c08a  mov     eax, [esi+1Ch]
0x1005c08d  test    eax, eax
0x1005c08f  jz      short loc_1005C09A
0x1005c091  push    eax; Block
0x1005c092  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c097  add     esp, 4
0x1005c09a  mov     eax, [esi]
0x1005c09c  test    eax, eax
0x1005c09e  jz      short loc_1005C0A9
0x1005c0a0  push    eax; Block
0x1005c0a1  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005c0a6  add     esp, 4
0x1005c0a9  push    4Ch ; 'L'; unsigned int
0x1005c0ab  push    esi; Block
0x1005c0ac  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005c0b1  mov     eax, [ebp+arg_0]
0x1005c0b4  add     esp, 8
0x1005c0b7  mov     dword ptr [ebx], 0
0x1005c0bd  inc     edi
0x1005c0be  cmp     edi, 1BDh
0x1005c0c4  jnz     short loc_1005C080
0x1005c0c6  xor     eax, eax
0x1005c0c8  mov     ecx, [ebp+var_C]
0x1005c0cb  mov     large fs:0, ecx
0x1005c0d2  pop     ecx
0x1005c0d3  pop     edi
0x1005c0d4  pop     esi
0x1005c0d5  pop     ebx
0x1005c0d6  mov     esp, ebp
0x1005c0d8  pop     ebp
0x1005c0d9  retn    10h
0x10062500  push    4Ch ; 'L'; unsigned int
0x10062502  mov     eax, [ebp+Block]
0x10062505  push    eax; Block
0x10062506  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006250b  add     esp, 8
0x1006250e  retn
0x10062514  nop
0x10062515  nop
0x10062516  mov     edx, [esp-4+arg_4]
0x1006251a  lea     eax, [edx+0Ch]
0x1006251d  mov     ecx, [edx-24h]
0x10062520  xor     ecx, eax; StackCookie
0x10062522  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10062527  mov     eax, offset stru_10064B24
0x1006252c  jmp     ___CxxFrameHandler3
```
