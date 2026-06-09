# IndexMover::Seek(SeekOption,Err &)

- ea: `0x1002fc20`
- end: `0x1002ffb4`
- name: `?Seek@IndexMover@@UAEXW4SeekOption@@AAVErr@@@Z`
- size: `916`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10010790`
- `0x100109e0`
- `0x10010c60`
- `0x10010d60`
- `0x10011400`
- `0x10012d60`
- `0x10025e60`
- `0x10025ee0`
- `0x10025fc0`
- `0x10026020`
- `0x10026060`
- `0x1002fc20`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall IndexMover::Seek(char *this, int a2, struct Err *a3)
{
  _DWORD *v3; // edi
  Checksum *v4; // ecx
  unsigned __int8 *v5; // esi
  int v6; // edx
  int v7; // ecx
  bool v8; // zf
  _DWORD *v9; // esi
  _DWORD *v10; // eax
  unsigned int v11; // esi
  int v12; // edx
  unsigned int v13; // esi
  bool v14; // cf
  unsigned __int8 v15; // al
  unsigned __int8 v16; // al
  unsigned __int8 v17; // al
  int v18; // eax
  int v19; // ecx
  unsigned int Bookmark; // eax
  int v21; // ecx
  unsigned int v22; // eax
  int v23; // edx
  _DWORD v24[3]; // [esp+10h] [ebp-24h] BYREF
  void *Block; // [esp+1Ch] [ebp-18h]
  void *v26; // [esp+20h] [ebp-14h]
  char *v27; // [esp+24h] [ebp-10h]
  int v28; // [esp+30h] [ebp-4h]

  v27 = this;
  (*(void (__thiscall **)(_DWORD *, struct Err *))(**((_DWORD **)this + 1) + 124))(*((_DWORD **)this + 1), a3);
  v3 = v27;
  v4 = (Checksum *)*((_DWORD *)v27 + 19);
  if ( (unsigned int)v4 > 0xFF )
  {
    v5 = (unsigned __int8 *)(*((_DWORD *)v27 + 20) + 253);
    *(_WORD *)v5 = Checksum::ComputeCrc(v4, v5, (unsigned int)v4 - 253);
    v3[19] = 255;
  }
  Btree::Find((Btree *)(v3 + 44), (struct Key *)(v3 + 19), a3, a2 == 1);
  v3[2] = 0;
  v6 = *(_DWORD *)a3 & 1;
  v7 = *(_DWORD *)a3 & 8;
  if ( v7 )
  {
    if ( v6 || (v8 = *((_DWORD *)a3 + 1) == -1601, v9 = (_DWORD *)((char *)a3 + 4), v27 = (char *)a3 + 4, !v8) )
    {
      v3[2] = 2;
      v10 = (_DWORD *)((char *)a3 + 4);
      goto LABEL_66;
    }
  }
  else
  {
    v9 = (_DWORD *)((char *)a3 + 4);
    v27 = (char *)a3 + 4;
    if ( v6 )
      goto LABEL_10;
  }
  if ( *v9 == 1039 || *v9 == -1601 )
    goto LABEL_17;
LABEL_10:
  if ( v3[19] < (unsigned int)(v3[59] - 4) )
  {
LABEL_17:
    switch ( a2 )
    {
      case 0:
      case 1:
        if ( v7 )
          goto LABEL_38;
        v7 = *(_DWORD *)(v3[17] + 8);
        if ( v3[18] >= *(_DWORD *)(v7 + 32) )
          goto LABEL_38;
        if ( v6 || *v9 != 1039 )
          goto LABEL_39;
        v11 = v3[19];
        v7 = v3[60];
        v12 = v3[20];
        if ( v3[59] < v11 )
          v11 = v3[59];
        v14 = v11 < 4;
        v13 = v11 - 4;
        if ( v14 )
          goto LABEL_27;
        break;
      case 4:
      case 5:
        if ( v7 )
        {
          v3[2] = 2;
        }
        else
        {
          if ( a2 == 4 )
            Err::Reset(a3);
          v3[2] = 0;
        }
        goto LABEL_65;
      default:
        if ( v7 )
        {
          if ( (*(_DWORD *)a3 & 0xFFFFFFFE) != 0 )
          {
            if ( *((_DWORD *)a3 + 3) )
              operator delete[](*((void **)a3 + 3));
            if ( *((_DWORD *)a3 + 4) )
              operator delete[](*((void **)a3 + 4));
          }
          *(_DWORD *)a3 = 1;
          if ( a2 == 3 )
            Err::SetWarning(a3, 1039);
          Btree::Last((Btree *)(v3 + 44), a3);
          goto LABEL_65;
        }
        v24[0] = 1;
        v28 = 0;
        if ( a2 == 2 )
          Err::Reset(a3);
        Btree::Prior((Btree *)(v3 + 44), (struct Err *)v24);
        v19 = v24[0];
        if ( (v24[0] & 8) != 0 )
        {
          if ( v24[0] > *(_DWORD *)a3 )
          {
            Err::operator=(v24);
            v19 = v24[0];
          }
          v3[2] = 1;
        }
        v10 = v9;
        if ( (v19 & 0xFFFFFFFE) != 0 )
        {
          if ( Block )
            operator delete[](Block);
          v10 = v9;
          if ( v26 )
          {
            operator delete[](v26);
            goto LABEL_65;
          }
        }
        goto LABEL_66;
    }
    while ( *(_DWORD *)v7 == *(_DWORD *)v12 )
    {
      v7 += 4;
      v12 += 4;
      v14 = v13 < 4;
      v13 -= 4;
      if ( v14 )
      {
LABEL_27:
        if ( v13 == -4 )
          goto LABEL_36;
        break;
      }
    }
    v14 = *(_BYTE *)v7 < *(_BYTE *)v12;
    if ( *(_BYTE *)v7 != *(_BYTE *)v12
      || v13 != -3
      && ((v15 = *(_BYTE *)(v7 + 1), v14 = v15 < *(_BYTE *)(v12 + 1), v15 != *(_BYTE *)(v12 + 1))
       || v13 != -2
       && ((v16 = *(_BYTE *)(v7 + 2), v14 = v16 < *(_BYTE *)(v12 + 2), v16 != *(_BYTE *)(v12 + 2))
        || v13 != -1 && (v17 = *(_BYTE *)(v7 + 3), v14 = v17 < *(_BYTE *)(v12 + 3), v17 != *(_BYTE *)(v12 + 3)))) )
    {
      v18 = v14 ? -1 : 1;
      goto LABEL_37;
    }
LABEL_36:
    v18 = 0;
LABEL_37:
    if ( v18 )
    {
LABEL_38:
      Err::SetError(a3, -1601, v7);
      v3[2] = 2;
    }
LABEL_39:
    v10 = v27;
    goto LABEL_66;
  }
  if ( a2 == 4 )
  {
    Btree::NextNE((Btree *)(v3 + 44), a3);
    if ( (*(_BYTE *)a3 & 8) != 0 )
      v3[2] = 2;
    goto LABEL_65;
  }
  v10 = v9;
  if ( a2 == 2 )
  {
    Btree::Prior((Btree *)(v3 + 44), a3);
    v10 = v9;
    if ( (*(_BYTE *)a3 & 8) != 0 )
    {
      v3[2] = 1;
LABEL_65:
      v10 = v9;
    }
  }
LABEL_66:
  if ( v3[2] )
  {
    v3[3] = 0;
  }
  else
  {
    Bookmark = Btree::GetBookmark((Btree *)(v3 + 44), a3);
    v3[3] = Bookmark;
    v21 = v3[5];
    v22 = Bookmark >> 8;
    if ( v21 )
      v23 = *(_DWORD *)(v21 + 12);
    else
      v23 = 0;
    if ( v23 != v22 )
    {
      if ( v21 )
        --*(_WORD *)(v21 + 76);
      v3[6] = 0;
      v3[5] = 0;
    }
    v3[13] = 0;
    v10 = (_DWORD *)((char *)a3 + 4);
    v3[14] = 0;
    v3[15] = 0;
  }
  if ( (*(_DWORD *)a3 & 8) != 0 && (*(_DWORD *)a3 & 1) == 0 && *v10 == -1603 )
    Err::OverrideError(a3, -1601);
}

```

## disassembly

```asm
0x1002fc20  mov     edi, edi
0x1002fc22  push    ebp
0x1002fc23  mov     ebp, esp
0x1002fc25  push    0FFFFFFFFh
0x1002fc27  push    offset ?WriteAt@CJetILockBytes@@UAGJT_ULARGE_INTEGER@@PBXKPAK@Z_SEH
0x1002fc2c  mov     eax, large fs:0
0x1002fc32  push    eax
0x1002fc33  sub     esp, 18h
0x1002fc36  push    ebx
0x1002fc37  push    esi
0x1002fc38  push    edi
0x1002fc39  mov     eax, ___security_cookie
0x1002fc3e  xor     eax, ebp
0x1002fc40  push    eax; unsigned int
0x1002fc41  lea     eax, [ebp+var_C]
0x1002fc44  mov     large fs:0, eax
0x1002fc4a  mov     [ebp+var_10], ecx
0x1002fc4d  mov     edi, [ecx+4]
0x1002fc50  mov     ebx, [ebp+arg_4]
0x1002fc53  push    ebx; void *
0x1002fc54  mov     eax, [edi]
0x1002fc56  mov     esi, [eax+7Ch]
0x1002fc59  mov     ecx, esi
0x1002fc5b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002fc61  mov     ecx, edi
0x1002fc63  call    esi
0x1002fc65  mov     edi, [ebp+var_10]
0x1002fc68  mov     ecx, [edi+4Ch]; this
0x1002fc6b  cmp     ecx, 0FFh
0x1002fc71  jbe     short loc_1002FC93
0x1002fc73  mov     esi, [edi+50h]
0x1002fc76  lea     eax, [ecx-0FDh]
0x1002fc7c  add     esi, 0FDh
0x1002fc82  push    eax; unsigned int
0x1002fc83  push    esi; unsigned __int8 *
0x1002fc84  call    ?ComputeCrc@Checksum@@QAEGPAEI@Z; Checksum::ComputeCrc(uchar *,uint)
0x1002fc89  mov     [esi], ax
0x1002fc8c  mov     dword ptr [edi+4Ch], 0FFh
0x1002fc93  xor     eax, eax
0x1002fc95  lea     ecx, [edi+0B0h]; this
0x1002fc9b  cmp     [ebp+arg_0], 1
0x1002fc9f  setz    al
0x1002fca2  push    eax; unsigned int
0x1002fca3  push    ebx; struct Err *
0x1002fca4  lea     eax, [edi+4Ch]
0x1002fca7  push    eax; struct Key *
0x1002fca8  call    ?Find@Btree@@QAEXAAVKey@@AAVErr@@I@Z; Btree::Find(Key &,Err &,uint)
0x1002fcad  mov     dword ptr [edi+8], 0
0x1002fcb4  mov     ecx, [ebx]
0x1002fcb6  mov     edx, ecx
0x1002fcb8  and     edx, 1
0x1002fcbb  and     ecx, 8
0x1002fcbe  jz      short loc_1002FCE2
0x1002fcc0  test    edx, edx
0x1002fcc2  jnz     short loc_1002FCD3
0x1002fcc4  cmp     dword ptr [ebx+4], 0FFFFF9BFh
0x1002fccb  lea     esi, [ebx+4]
0x1002fcce  mov     [ebp+var_10], esi
0x1002fcd1  jz      short loc_1002FCEC
0x1002fcd3  mov     dword ptr [edi+8], 2
0x1002fcda  lea     eax, [ebx+4]
0x1002fcdd  jmp     loc_1002FF1F
0x1002fce2  lea     esi, [ebx+4]
0x1002fce5  mov     [ebp+var_10], esi
0x1002fce8  test    edx, edx
0x1002fcea  jnz     short loc_1002FD00
0x1002fcec  cmp     dword ptr [esi], 40Fh
0x1002fcf2  jz      short loc_1002FD65
0x1002fcf4  test    edx, edx
0x1002fcf6  jnz     short loc_1002FD00
0x1002fcf8  cmp     dword ptr [esi], 0FFFFF9BFh
0x1002fcfe  jz      short loc_1002FD65
0x1002fd00  mov     eax, [edi+0ECh]
0x1002fd06  sub     eax, 4
0x1002fd09  cmp     [edi+4Ch], eax
0x1002fd0c  jb      short loc_1002FD65
0x1002fd0e  mov     ecx, [ebp+arg_0]
0x1002fd11  cmp     ecx, 4
0x1002fd14  jnz     short loc_1002FD37
0x1002fd16  push    ebx; struct Err *
0x1002fd17  lea     ecx, [edi+0B0h]; this
0x1002fd1d  call    ?NextNE@Btree@@QAEXAAVErr@@@Z; Btree::NextNE(Err &)
0x1002fd22  test    byte ptr [ebx], 8
0x1002fd25  jz      loc_1002FF1D
0x1002fd2b  mov     dword ptr [edi+8], 2
0x1002fd32  jmp     loc_1002FF1D
0x1002fd37  mov     eax, esi
0x1002fd39  cmp     ecx, 2
0x1002fd3c  jnz     loc_1002FF1F
0x1002fd42  push    ebx; struct Err *
0x1002fd43  lea     ecx, [edi+0B0h]; this
0x1002fd49  call    ?Prior@Btree@@QAEXAAVErr@@@Z; Btree::Prior(Err &)
0x1002fd4e  test    byte ptr [ebx], 8
0x1002fd51  mov     eax, esi
0x1002fd53  jz      loc_1002FF1F
0x1002fd59  mov     dword ptr [edi+8], 1
0x1002fd60  jmp     loc_1002FF1D
0x1002fd65  mov     eax, [ebp+arg_0]
0x1002fd68  cmp     eax, 5; switch 6 cases
0x1002fd6b  ja      def_1002FD71; jumptable 1002FD71 default case, cases 2,3
0x1002fd71  jmp     ds:jpt_1002FD71[eax*4]; switch jump
0x1002fd78  test    ecx, ecx; jumptable 1002FD71 cases 0,1
0x1002fd7a  jnz     loc_1002FE12
0x1002fd80  mov     eax, [edi+44h]
0x1002fd83  mov     ecx, [eax+8]
0x1002fd86  mov     eax, [edi+48h]
0x1002fd89  cmp     eax, [ecx+20h]
0x1002fd8c  jge     loc_1002FE12
0x1002fd92  test    edx, edx
0x1002fd94  jnz     loc_1002FE26
0x1002fd9a  cmp     dword ptr [esi], 40Fh
0x1002fda0  jnz     loc_1002FE26
0x1002fda6  mov     esi, [edi+4Ch]
0x1002fda9  mov     eax, [edi+0ECh]
0x1002fdaf  cmp     eax, esi
0x1002fdb1  mov     ecx, [edi+0F0h]
0x1002fdb7  mov     edx, [edi+50h]
0x1002fdba  cmovb   esi, eax
0x1002fdbd  sub     esi, 4
0x1002fdc0  jb      short loc_1002FDD3
0x1002fdc2  mov     eax, [ecx]
0x1002fdc4  cmp     eax, [edx]
0x1002fdc6  jnz     short loc_1002FDD8
0x1002fdc8  add     ecx, 4
0x1002fdcb  add     edx, 4
0x1002fdce  sub     esi, 4
0x1002fdd1  jnb     short loc_1002FDC2
0x1002fdd3  cmp     esi, 0FFFFFFFCh
0x1002fdd6  jz      short loc_1002FE0C
0x1002fdd8  mov     al, [ecx]
0x1002fdda  cmp     al, [edx]
0x1002fddc  jnz     short loc_1002FE05
0x1002fdde  cmp     esi, 0FFFFFFFDh
0x1002fde1  jz      short loc_1002FE0C
0x1002fde3  mov     al, [ecx+1]
0x1002fde6  cmp     al, [edx+1]
0x1002fde9  jnz     short loc_1002FE05
0x1002fdeb  cmp     esi, 0FFFFFFFEh
0x1002fdee  jz      short loc_1002FE0C
0x1002fdf0  mov     al, [ecx+2]
0x1002fdf3  cmp     al, [edx+2]
0x1002fdf6  jnz     short loc_1002FE05
0x1002fdf8  cmp     esi, 0FFFFFFFFh
0x1002fdfb  jz      short loc_1002FE0C
0x1002fdfd  mov     al, [ecx+3]
0x1002fe00  cmp     al, [edx+3]
0x1002fe03  jz      short loc_1002FE0C
0x1002fe05  sbb     eax, eax
0x1002fe07  or      eax, 1
0x1002fe0a  jmp     short loc_1002FE0E
0x1002fe0c  xor     eax, eax
0x1002fe0e  test    eax, eax
0x1002fe10  jz      short loc_1002FE26
0x1002fe12  push    ecx
0x1002fe13  push    0FFFFF9BFh
0x1002fe18  mov     ecx, ebx
0x1002fe1a  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002fe1f  mov     dword ptr [edi+8], 2
0x1002fe26  mov     eax, [ebp+var_10]
0x1002fe29  jmp     loc_1002FF1F
0x1002fe2e  test    ecx, ecx; jumptable 1002FD71 cases 4,5
0x1002fe30  jz      short loc_1002FE3F
0x1002fe32  mov     eax, 2
0x1002fe37  mov     [edi+8], eax
0x1002fe3a  jmp     loc_1002FF1D
0x1002fe3f  cmp     eax, 4
0x1002fe42  jnz     short loc_1002FE4B
0x1002fe44  mov     ecx, ebx; this
0x1002fe46  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x1002fe4b  xor     eax, eax
0x1002fe4d  mov     [edi+8], eax
0x1002fe50  jmp     loc_1002FF1D
0x1002fe55  test    ecx, ecx; jumptable 1002FD71 default case, cases 2,3
0x1002fe57  jz      short loc_1002FEA7
0x1002fe59  test    dword ptr [ebx], 0FFFFFFFEh
0x1002fe5f  jz      short loc_1002FE81
0x1002fe61  mov     eax, [ebx+0Ch]
0x1002fe64  test    eax, eax
0x1002fe66  jz      short loc_1002FE71
0x1002fe68  push    eax; Block
0x1002fe69  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002fe6e  add     esp, 4
0x1002fe71  mov     eax, [ebx+10h]
0x1002fe74  test    eax, eax
0x1002fe76  jz      short loc_1002FE81
0x1002fe78  push    eax; Block
0x1002fe79  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002fe7e  add     esp, 4
0x1002fe81  cmp     [ebp+arg_0], 3
0x1002fe85  mov     dword ptr [ebx], 1
0x1002fe8b  jnz     short loc_1002FE99
0x1002fe8d  push    40Fh; int
0x1002fe92  mov     ecx, ebx; this
0x1002fe94  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x1002fe99  push    ebx; struct Err *
0x1002fe9a  lea     ecx, [edi+0B0h]; this
0x1002fea0  call    ?Last@Btree@@QAEXAAVErr@@@Z; Btree::Last(Err &)
0x1002fea5  jmp     short loc_1002FF1D
0x1002fea7  mov     [ebp+var_24], 1
0x1002feae  mov     [ebp+var_4], 0
0x1002feb5  cmp     eax, 2
0x1002feb8  jnz     short loc_1002FEC1
0x1002feba  mov     ecx, ebx; this
0x1002febc  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x1002fec1  lea     eax, [ebp+var_24]
0x1002fec4  push    eax; struct Err *
0x1002fec5  lea     ecx, [edi+0B0h]; this
0x1002fecb  call    ?Prior@Btree@@QAEXAAVErr@@@Z; Btree::Prior(Err &)
0x1002fed0  mov     ecx, [ebp+var_24]
0x1002fed3  test    cl, 8
0x1002fed6  jz      short loc_1002FEF1
0x1002fed8  cmp     ecx, [ebx]
0x1002feda  jle     short loc_1002FEEA
0x1002fedc  lea     eax, [ebp+var_24]
0x1002fedf  mov     ecx, ebx
0x1002fee1  push    eax
0x1002fee2  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1002fee7  mov     ecx, [ebp+var_24]
0x1002feea  mov     dword ptr [edi+8], 1
0x1002fef1  mov     eax, esi
0x1002fef3  test    ecx, 0FFFFFFFEh
0x1002fef9  jz      short loc_1002FF1F
0x1002fefb  mov     eax, [ebp+Block]
0x1002fefe  test    eax, eax
0x1002ff00  jz      short loc_1002FF0B
0x1002ff02  push    eax; Block
0x1002ff03  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002ff08  add     esp, 4
0x1002ff0b  mov     ecx, [ebp+var_14]
0x1002ff0e  mov     eax, esi
0x1002ff10  test    ecx, ecx
0x1002ff12  jz      short loc_1002FF1F
0x1002ff14  push    ecx; Block
0x1002ff15  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002ff1a  add     esp, 4
0x1002ff1d  mov     eax, esi
0x1002ff1f  cmp     dword ptr [edi+8], 0
0x1002ff23  jnz     short loc_1002FF79
0x1002ff25  push    ebx; struct Err *
0x1002ff26  lea     ecx, [edi+0B0h]; this
0x1002ff2c  call    ?GetBookmark@Btree@@QAEKAAVErr@@@Z; Btree::GetBookmark(Err &)
0x1002ff31  mov     [edi+0Ch], eax
0x1002ff34  mov     ecx, [edi+14h]
0x1002ff37  shr     eax, 8
0x1002ff3a  test    ecx, ecx
0x1002ff3c  jz      short loc_1002FF43
0x1002ff3e  mov     edx, [ecx+0Ch]
0x1002ff41  jmp     short loc_1002FF45
0x1002ff43  xor     edx, edx
0x1002ff45  cmp     edx, eax
0x1002ff47  jz      short loc_1002FF5F
0x1002ff49  test    ecx, ecx
0x1002ff4b  jz      short loc_1002FF51
0x1002ff4d  dec     word ptr [ecx+4Ch]
0x1002ff51  mov     dword ptr [edi+18h], 0
0x1002ff58  mov     dword ptr [edi+14h], 0
0x1002ff5f  mov     dword ptr [edi+34h], 0
0x1002ff66  lea     eax, [ebx+4]
0x1002ff69  mov     dword ptr [edi+38h], 0
0x1002ff70  mov     dword ptr [edi+3Ch], 0
0x1002ff77  jmp     short loc_1002FF80
0x1002ff79  mov     dword ptr [edi+0Ch], 0
0x1002ff80  mov     ecx, [ebx]
0x1002ff82  test    cl, 8
0x1002ff85  jz      short loc_1002FFA0
0x1002ff87  test    cl, 1
0x1002ff8a  jnz     short loc_1002FFA0
0x1002ff8c  cmp     dword ptr [eax], 0FFFFF9BDh
0x1002ff92  jnz     short loc_1002FFA0
0x1002ff94  push    0FFFFF9BFh; int
0x1002ff99  mov     ecx, ebx; this
0x1002ff9b  call    ?OverrideError@Err@@QAEXJ@Z; Err::OverrideError(long)
0x1002ffa0  mov     ecx, [ebp+var_C]
0x1002ffa3  mov     large fs:0, ecx
0x1002ffaa  pop     ecx
0x1002ffab  pop     edi
0x1002ffac  pop     esi
0x1002ffad  pop     ebx
0x1002ffae  mov     esp, ebp
0x1002ffb0  pop     ebp
0x1002ffb1  retn    8
0x1005feb0  lea     ecx, [ebp+var_24]; this
0x1005feb3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1005febd  nop
0x1005febe  nop
0x1005febf  mov     edx, [esp-4+arg_4]
0x1005fec3  lea     eax, [edx+0Ch]
0x1005fec6  mov     ecx, [edx-28h]
0x1005fec9  xor     ecx, eax; StackCookie
0x1005fecb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fed0  mov     eax, offset stru_10062F54
0x1005fed5  jmp     ___CxxFrameHandler3
```
