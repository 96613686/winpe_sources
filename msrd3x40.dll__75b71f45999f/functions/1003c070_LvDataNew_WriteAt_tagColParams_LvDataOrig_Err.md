# LvDataNew::WriteAt(tagColParams *,LvDataOrig *,Err &)

- ea: `0x1003c070`
- end: `0x1003c792`
- name: `?WriteAt@LvDataNew@@QAEKPAUtagColParams@@PAVLvDataOrig@@AAVErr@@@Z`
- size: `1826`
- prototype: `unsigned int __thiscall(LvDataNew *__hidden this, struct tagColParams *, struct LvDataOrig *, struct Err *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, installer_update`

## callers

- `0x1003eca0`

## callees

- `0x1000da40`
- `0x1000eb60`
- `0x1000f750`
- `0x10010580`
- `0x10023690`
- `0x10023730`
- `0x10024f60`
- `0x100250e0`
- `0x10025300`
- `0x10025ee0`
- `0x1003ab80`
- `0x1003c070`
- `0x1003c9a0`
- `0x1003d170`
- `0x1003d300`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
int __thiscall LvDataNew::WriteAt(LvDataNew *this, struct tagColParams *a2, struct LvDataOrig *a3, void **a4)
{
  struct tagColParams *v4; // ebx
  bool v5; // zf
  LvDataNew *v6; // esi
  bool v7; // cf
  int v8; // eax
  struct tagColParams **v9; // ecx
  int v10; // ecx
  int v11; // eax
  struct tagColParams *v12; // ecx
  unsigned int v14; // ebx
  size_t v15; // eax
  size_t v16; // ecx
  unsigned int v17; // ecx
  int v18; // ebx
  size_t v19; // eax
  _DWORD *v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // ecx
  int v23; // ebx
  int v24; // esi
  size_t v25; // edx
  int v26; // eax
  int v27; // ecx
  int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // eax
  int v31; // ebx
  int v32; // eax
  int v33; // eax
  char *v34; // eax
  unsigned int v35; // ecx
  bool v36; // cc
  int v37; // eax
  struct Transaction **v38; // eax
  int v39; // eax
  unsigned int v40; // ecx
  unsigned int v41; // eax
  size_t v42; // eax
  _DWORD *v43; // esi
  size_t v44; // eax
  int v45; // ecx
  _DWORD *v46; // eax
  int v47; // ebx
  _DWORD *v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // ebx
  struct Transaction **v51; // eax
  int v52; // eax
  int v53; // ecx
  unsigned int v54; // edx
  unsigned int v55; // eax
  BOOL v56; // eax
  int v57; // edx
  int v58[3]; // [esp+10h] [ebp-80h] BYREF
  void *Block; // [esp+1Ch] [ebp-74h]
  void *v60; // [esp+20h] [ebp-70h]
  int v61; // [esp+24h] [ebp-6Ch] BYREF
  int v62; // [esp+28h] [ebp-68h]
  int v63; // [esp+34h] [ebp-5Ch] BYREF
  int v64; // [esp+38h] [ebp-58h]
  unsigned int *v65; // [esp+44h] [ebp-4Ch]
  unsigned int v66; // [esp+48h] [ebp-48h]
  int v67; // [esp+4Ch] [ebp-44h]
  char v68[4]; // [esp+50h] [ebp-40h] BYREF
  void *Src; // [esp+54h] [ebp-3Ch]
  size_t v70; // [esp+58h] [ebp-38h]
  struct tagColParams **v71; // [esp+5Ch] [ebp-34h]
  struct tagColParams *v72; // [esp+60h] [ebp-30h]
  _DWORD *v73; // [esp+64h] [ebp-2Ch]
  char *v74; // [esp+68h] [ebp-28h]
  BOOL v75; // [esp+6Ch] [ebp-24h]
  int v76; // [esp+70h] [ebp-20h]
  size_t Size; // [esp+74h] [ebp-1Ch]
  int v78; // [esp+78h] [ebp-18h]
  unsigned int v79; // [esp+7Ch] [ebp-14h]
  LvDataNew *v80; // [esp+80h] [ebp-10h]
  int v81; // [esp+8Ch] [ebp-4h]

  v80 = this;
  v4 = a2;
  v5 = *((_DWORD *)a3 + 515) == 0;
  v72 = (struct tagColParams *)(*((_DWORD *)a2 + 4) + *((_DWORD *)a2 + 2));
  if ( v5 )
    LvDataOrig::GetRecordData(a3, (int)a2, 0, (Err *)a4);
  if ( (*(_BYTE *)a4 & 8) != 0 )
  {
LABEL_11:
    v6 = v80;
    goto LABEL_12;
  }
  if ( !*((_DWORD *)a3 + 515) )
    LvDataOrig::GetRecordData(a3, (int)a2, 0, (Err *)a4);
  if ( (*(_BYTE *)a4 & 8) != 0 || (unsigned int)v72 >= *((_DWORD *)a3 + 516) )
  {
    if ( (unsigned int)v72 <= 0x3FFFFFFF )
    {
      v6 = v80;
      LvDataNew::SetupPreviousData(v80, a2, *((struct tagColParams **)a2 + 4), a3, (struct Err *)a4);
      goto LABEL_12;
    }
    Err::SetError(a4, -1047, this);
    goto LABEL_11;
  }
  v6 = v80;
  LvDataNew::SetupPreviousData(v80, a2, v72, a3, (struct Err *)a4);
LABEL_12:
  if ( (*(_BYTE *)a4 & 8) != 0 )
    return 0;
  v7 = *((_DWORD *)v6 + 516) < (unsigned int)v72;
  v71 = (struct tagColParams **)((char *)v6 + 2064);
  v75 = v7;
  v8 = *((_DWORD *)v6 + 514);
  if ( v8 && (unsigned int)v72 <= 0x6F0 && !*((_DWORD *)v6 + 513) )
  {
    memcpy((char *)v6 + *((_DWORD *)a2 + 4) + 4, *((const void **)a2 + 1), *((_DWORD *)a2 + 2));
    v9 = (struct tagColParams **)((char *)v6 + 2064);
    goto LABEL_123;
  }
  v10 = 0;
  v63 = 0;
  v64 = 0;
  v81 = 0;
  v76 = 0;
  if ( v8 || (v11 = *((_DWORD *)v6 + 518)) == 0 || *(int *)(v11 + 4) <= 0 || !**(_DWORD **)(v11 + 12) )
  {
    v12 = (struct tagColParams *)*((_DWORD *)v6 + 516);
    if ( (unsigned int)v12 <= *((_DWORD *)a2 + 4) )
      v12 = (struct tagColParams *)*((_DWORD *)a2 + 4);
    LvDataNew::CreateNewFirstPage(
      v6,
      v12,
      (struct DataPage *)&v63,
      (const char *)v6 + 4,
      (unsigned int)v12,
      (struct Err *)a4);
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
      if ( v63 )
        --*(_WORD *)(v63 + 76);
      return 0;
    }
    v10 = v63;
  }
  v14 = *((_DWORD *)a2 + 4) / 0x7F0u;
  v5 = (*(_BYTE *)a4 & 8) == 0;
  v78 = v14;
  if ( !v5 )
    goto LABEL_120;
  v71 = (struct tagColParams **)((char *)v6 + 2064);
  v15 = 0;
  while ( 1 )
  {
    v16 = *((_DWORD *)a2 + 2);
    if ( v15 >= v16 )
      break;
    v17 = v16 - v76;
    v18 = v76 + *((_DWORD *)a2 + 4) - 2032 * v14;
    v19 = 2032 - v18;
    if ( 2032 - v18 >= v17 )
      v19 = v17;
    Size = v19;
    v20 = (_DWORD *)*((_DWORD *)v6 + 518);
    if ( v78 >= v20[1] )
    {
      v79 = 0;
LABEL_37:
      *(_DWORD *)v68 = 0;
      LvDataNew::AllocatePage(v6, (struct tagColParams *)v17, (struct DataPage *)&v63, (struct Err *)a4);
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_73;
      v21 = DataPage::Insert((DataPage *)&v63, (const unsigned __int8 *)v68, 4u);
      v22 = v21;
      v79 = v21;
      if ( !v21 )
      {
        if ( (int)*a4 < 8 )
        {
          if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
          {
            if ( a4[3] )
              operator delete[](a4[3]);
            if ( a4[4] )
              operator delete[](a4[4]);
          }
          *a4 = (void *)8;
          a4[1] = (void *)-1012;
          a4[2] = 0;
          a4[3] = 0;
          a4[4] = 0;
LABEL_62:
          v22 = v79;
        }
        v31 = v63;
        if ( (*(_BYTE *)a4 & 8) != 0
          || (v32 = *(_DWORD *)(v63 + 24),
              *(_DWORD *)v68 = v22,
              *(_DWORD *)(v63 + 4 * v32 + 28) |= 8u,
              ++*(_DWORD *)(v31 + 64),
              Array::Set(*((Array **)v6 + 518), v78, v68, (struct Err *)a4),
              (*(_BYTE *)a4 & 8) != 0) )
        {
          v58[0] = 1;
          LOBYTE(v81) = 1;
          v33 = v31 ? *(_DWORD *)(v31 + 12) : 0;
          Transaction::FreePage(*((_DWORD *)v6 + 523), v33, 1, v58);
          LOBYTE(v81) = 0;
          if ( (v58[0] & 0xFFFFFFFE) != 0 )
          {
            if ( Block )
              operator delete[](Block);
            if ( v60 )
              operator delete[](v60);
          }
        }
LABEL_73:
        v73 = (_DWORD *)((char *)v6 + 2084);
        v34 = (char *)v6 + 2068;
LABEL_97:
        v74 = v34;
        goto LABEL_98;
      }
      v23 = v64;
      v24 = (unsigned __int8)v21;
      v25 = Size + 4;
      v26 = *(_WORD *)(v64 + 2 * (unsigned __int8)v21 + 10) & 0x3FFF;
      if ( (_BYTE)v22 )
        v27 = *(_WORD *)(v64 + 2 * (unsigned __int8)v22 + 8) & 0x3FFF;
      else
        v27 = 2048;
      v28 = v27 - v26;
      if ( v28 != v25 && v25 <= v28 + (unsigned int)*(unsigned __int16 *)(v64 + 2) )
        DataPage::AdjustGap(&v63, v24, 1, v25 - v28);
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        v29 = *(_WORD *)(v23 + 2 * v24 + 10) & 0x3FFF;
        if ( v29 <= 0x800 )
        {
          if ( v24 )
          {
            v30 = *(_WORD *)(v23 + 2 * v24 + 8) & 0x3FFF;
            if ( v30 <= 0x800 && v29 <= v30 )
              goto LABEL_58;
          }
          else
          {
            v30 = 2048;
LABEL_58:
            if ( v30 - v29 <= 0x800 )
              v67 = v29 + v23;
          }
        }
        memcpy((void *)(v67 + 4), (const void *)(v76 + *((_DWORD *)a2 + 1)), Size);
      }
      v6 = v80;
      goto LABEL_62;
    }
    v17 = *(_DWORD *)(v78 * *v20 + v20[3]);
    v79 = v17;
    if ( !v17 )
      goto LABEL_37;
    v35 = v17 >> 8;
    v36 = *((_DWORD *)v6 + 521) < 4;
    v74 = (char *)v6 + 2068;
    v37 = *((_DWORD *)v6 + 517);
    v73 = (_DWORD *)((char *)v6 + 2084);
    v66 = v35;
    v38 = *(struct Transaction ***)(v37 + 8);
    *(_DWORD *)v68 = v38;
    if ( v36 )
    {
      v39 = (*((int (__thiscall **)(_DWORD))*v38 + 14))(*(_DWORD *)v68);
      v6 = v80;
      Database::ReadPageForUpdate(
        *(Database **)(v39 + 16),
        (struct PageRef *)&v63,
        v66,
        (struct Err *)a4,
        *((struct Transaction **)v80 + 523),
        0);
    }
    else
    {
      Database::ReadPage(*((Database **)v38[10] + 2), (struct PageRef *)&v63, v35, 1, (struct Err *)a4, v38[10]);
    }
    v40 = *(_WORD *)(v64 + 2 * (unsigned __int8)v79 + 10) & 0x3FFF;
    if ( v40 <= 0x800 )
    {
      if ( (_BYTE)v79 )
      {
        v41 = *(_WORD *)(v64 + 2 * (unsigned __int8)v79 + 8) & 0x3FFF;
        if ( v41 > 0x800 || v40 > v41 )
          goto LABEL_84;
      }
      else
      {
        v41 = 2048;
      }
      v42 = v41 - v40;
      if ( v42 <= 0x800 )
      {
        v70 = v42;
        Src = (void *)(v64 + v40);
      }
    }
LABEL_84:
    if ( v70 - 4 < Size + v18 || v75 )
    {
      v43 = (_DWORD *)((char *)v6 + 4);
      memcpy(v43, Src, v70);
      memcpy((char *)v80 + v18 + 8, (const void *)(v76 + *((_DWORD *)a2 + 1)), Size);
      v44 = Size;
      *v43 = 0;
      if ( !DataPage::Replace((DataPage *)&v63, v79, (const unsigned __int8 *)v43, v18 + v44 + 4) && (int)*a4 < 8 )
      {
        if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
        {
          if ( a4[3] )
            operator delete[](a4[3]);
          if ( a4[4] )
            operator delete[](a4[4]);
        }
        *a4 = (void *)8;
        a4[1] = (void *)-1012;
        a4[2] = 0;
        a4[3] = 0;
        a4[4] = 0;
      }
    }
    else
    {
      memcpy((char *)Src + v18 + 4, (const void *)(v76 + *((_DWORD *)a2 + 1)), Size);
    }
    v6 = v80;
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
      v45 = v63;
      *(_DWORD *)(v63 + 4 * *(_DWORD *)(v63 + 24) + 28) |= 8u;
      v46 = v73;
      ++*(_DWORD *)(v45 + 64);
      v73 = v46;
      v34 = v74;
      goto LABEL_97;
    }
LABEL_98:
    v47 = v78;
    if ( (*(_BYTE *)a4 & 8) != 0 || !v78 )
      goto LABEL_117;
    v48 = (_DWORD *)*((_DWORD *)v6 + 518);
    if ( v78 - 1 < v48[1] )
      v49 = *(_DWORD *)((v78 - 1) * *v48 + v48[3]);
    else
      v49 = 0;
    *(_DWORD *)v68 = v49;
    v61 = 0;
    v62 = 0;
    LOBYTE(v81) = 2;
    v50 = v49 >> 8;
    v36 = *v73 < 4;
    v51 = *(struct Transaction ***)(*(_DWORD *)v74 + 8);
    v66 = (unsigned int)v51;
    if ( v36 )
    {
      v52 = (*((int (__thiscall **)(unsigned int))*v51 + 14))(v66);
      Database::ReadPageForUpdate(
        *(Database **)(v52 + 16),
        (struct PageRef *)&v61,
        v50,
        (struct Err *)a4,
        *((struct Transaction **)v80 + 523),
        0);
    }
    else
    {
      Database::ReadPage(*((Database **)v51[10] + 2), (struct PageRef *)&v61, v50, 1, (struct Err *)a4, v51[10]);
    }
    v53 = v61;
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
      v54 = *(_WORD *)(v62 + 2 * (unsigned __int8)v68[0] + 10) & 0x3FFF;
      if ( v54 <= 0x800 )
      {
        if ( v68[0] )
        {
          v55 = *(_WORD *)(v62 + 2 * (unsigned __int8)v68[0] + 8) & 0x3FFF;
          if ( v55 <= 0x800 && v54 <= v55 )
            goto LABEL_112;
        }
        else
        {
          v55 = 2048;
LABEL_112:
          if ( v55 - v54 <= 0x800 )
            v65 = (unsigned int *)(v54 + v62);
        }
      }
      *v65 = v79;
      *(_DWORD *)(v53 + 4 * *(_DWORD *)(v53 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v53 + 64);
    }
    v47 = v78;
    LOBYTE(v81) = 0;
    if ( v53 )
      --*(_WORD *)(v53 + 76);
LABEL_117:
    v6 = v80;
    if ( (*(_BYTE *)a4 & 8) != 0 )
      break;
    v14 = v47 + 1;
    v15 = Size + v76;
    v78 = v14;
    v76 += Size;
  }
  v10 = v63;
LABEL_120:
  v4 = a2;
  if ( v10 )
    --*(_WORD *)(v10 + 76);
  v9 = v71;
LABEL_123:
  v56 = v75;
  if ( (*(_BYTE *)a4 & 8) != 0 )
    return 0;
  v57 = *((_DWORD *)v4 + 2);
  *((_DWORD *)v6 + 520) = 0;
  if ( v56 )
    *v9 = v72;
  if ( *((_DWORD *)v4 + 6) == 1 && !*((_DWORD *)v6 + 513) )
    *((_DWORD *)v6 + 513) = 1;
  return v57;
}

```

## disassembly

```asm
0x1003c070  mov     edi, edi
0x1003c072  push    ebp
0x1003c073  mov     ebp, esp
0x1003c075  push    0FFFFFFFFh
0x1003c077  push    offset ?WriteAt@LvDataNew@@QAEKPAUtagColParams@@PAVLvDataOrig@@AAVErr@@@Z_SEH
0x1003c07c  mov     eax, large fs:0
0x1003c082  push    eax
0x1003c083  sub     esp, 74h
0x1003c086  push    ebx
0x1003c087  push    esi
0x1003c088  push    edi; unsigned int
0x1003c089  mov     eax, ___security_cookie
0x1003c08e  xor     eax, ebp
0x1003c090  push    eax; void *
0x1003c091  lea     eax, [ebp+var_C]
0x1003c094  mov     large fs:0, eax
0x1003c09a  mov     [ebp+var_10], ecx
0x1003c09d  mov     ebx, [ebp+arg_0]
0x1003c0a0  mov     esi, [ebp+arg_4]
0x1003c0a3  mov     edi, [ebp+arg_8]
0x1003c0a6  mov     eax, [ebx+8]
0x1003c0a9  add     eax, [ebx+10h]
0x1003c0ac  cmp     dword ptr [esi+80Ch], 0
0x1003c0b3  mov     [ebp+var_30], eax
0x1003c0b6  jnz     short loc_1003C0C3
0x1003c0b8  push    edi
0x1003c0b9  push    0
0x1003c0bb  push    ebx
0x1003c0bc  mov     ecx, esi
0x1003c0be  call    ?GetRecordData@LvDataOrig@@QAEXPAUtagColParams@@W4LvNullWarningAction@@AAVErr@@@Z; LvDataOrig::GetRecordData(tagColParams *,LvNullWarningAction,Err &)
0x1003c0c3  test    byte ptr [edi], 8
0x1003c0c6  jnz     short loc_1003C110
0x1003c0c8  cmp     dword ptr [esi+80Ch], 0
0x1003c0cf  jnz     short loc_1003C0DC
0x1003c0d1  push    edi
0x1003c0d2  push    0
0x1003c0d4  push    ebx
0x1003c0d5  mov     ecx, esi
0x1003c0d7  call    ?GetRecordData@LvDataOrig@@QAEXPAUtagColParams@@W4LvNullWarningAction@@AAVErr@@@Z; LvDataOrig::GetRecordData(tagColParams *,LvNullWarningAction,Err &)
0x1003c0dc  test    byte ptr [edi], 8
0x1003c0df  mov     eax, [ebp+var_30]
0x1003c0e2  jnz     short loc_1003C0FC
0x1003c0e4  cmp     eax, [esi+810h]
0x1003c0ea  jnb     short loc_1003C0FC
0x1003c0ec  push    edi; struct Err *
0x1003c0ed  push    esi; struct LvDataOrig *
0x1003c0ee  mov     esi, [ebp+var_10]
0x1003c0f1  mov     ecx, esi; this
0x1003c0f3  push    eax; struct tagColParams *
0x1003c0f4  push    ebx; struct tagColParams *
0x1003c0f5  call    ?SetupPreviousData@LvDataNew@@AAEXPAUtagColParams@@KPAVLvDataOrig@@AAVErr@@@Z; LvDataNew::SetupPreviousData(tagColParams *,ulong,LvDataOrig *,Err &)
0x1003c0fa  jmp     short loc_1003C113
0x1003c0fc  cmp     eax, 3FFFFFFFh
0x1003c101  jbe     short loc_1003C16E
0x1003c103  push    ecx
0x1003c104  push    0FFFFFBE9h
0x1003c109  mov     ecx, edi
0x1003c10b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003c110  mov     esi, [ebp+var_10]
0x1003c113  test    byte ptr [edi], 8
0x1003c116  jnz     loc_1003C77A
0x1003c11c  mov     ecx, [ebp+var_30]
0x1003c11f  lea     eax, [esi+810h]
0x1003c125  cmp     [eax], ecx
0x1003c127  mov     [ebp+var_34], eax
0x1003c12a  sbb     eax, eax
0x1003c12c  neg     eax
0x1003c12e  mov     [ebp+var_24], eax
0x1003c131  mov     eax, [esi+808h]
0x1003c137  test    eax, eax
0x1003c139  jz      short loc_1003C180
0x1003c13b  cmp     ecx, 6F0h
0x1003c141  ja      short loc_1003C180
0x1003c143  cmp     dword ptr [esi+804h], 0
0x1003c14a  jnz     short loc_1003C180
0x1003c14c  push    dword ptr [ebx+8]; Size
0x1003c14f  mov     eax, [ebx+10h]
0x1003c152  push    dword ptr [ebx+4]; Src
0x1003c155  add     eax, 4
0x1003c158  add     eax, esi
0x1003c15a  push    eax; void *
0x1003c15b  call    _memcpy
0x1003c160  add     esp, 0Ch
0x1003c163  lea     ecx, [esi+810h]
0x1003c169  jmp     loc_1003C741
0x1003c16e  push    edi; struct Err *
0x1003c16f  push    esi; struct LvDataOrig *
0x1003c170  push    dword ptr [ebx+10h]; struct tagColParams *
0x1003c173  mov     esi, [ebp+var_10]
0x1003c176  mov     ecx, esi; this
0x1003c178  push    ebx; struct tagColParams *
0x1003c179  call    ?SetupPreviousData@LvDataNew@@AAEXPAUtagColParams@@KPAVLvDataOrig@@AAVErr@@@Z; LvDataNew::SetupPreviousData(tagColParams *,ulong,LvDataOrig *,Err &)
0x1003c17e  jmp     short loc_1003C113
0x1003c180  xor     ecx, ecx
0x1003c182  mov     [ebp+var_5C], ecx
0x1003c185  mov     [ebp+var_58], ecx
0x1003c188  xor     edx, edx
0x1003c18a  mov     [ebp+var_4], ecx
0x1003c18d  mov     [ebp+var_20], edx
0x1003c190  test    eax, eax
0x1003c192  jnz     short loc_1003C1AA
0x1003c194  mov     eax, [esi+818h]
0x1003c19a  test    eax, eax
0x1003c19c  jz      short loc_1003C1AA
0x1003c19e  cmp     [eax+4], edx
0x1003c1a1  jle     short loc_1003C1AA
0x1003c1a3  mov     eax, [eax+0Ch]
0x1003c1a6  cmp     [eax], edx
0x1003c1a8  jnz     short loc_1003C1F2
0x1003c1aa  mov     ecx, [esi+810h]
0x1003c1b0  lea     eax, [esi+4]
0x1003c1b3  cmp     ecx, [ebx+10h]
0x1003c1b6  push    edi; struct Err *
0x1003c1b7  cmovbe  ecx, [ebx+10h]
0x1003c1bb  push    ecx; unsigned int
0x1003c1bc  push    eax; Src
0x1003c1bd  lea     eax, [ebp+var_5C]
0x1003c1c0  push    eax; struct DataPage *
0x1003c1c1  push    ecx; struct tagColParams *
0x1003c1c2  mov     ecx, esi; this
0x1003c1c4  call    ?CreateNewFirstPage@LvDataNew@@AAEKPAUtagColParams@@AAVDataPage@@PBDKAAVErr@@@Z; LvDataNew::CreateNewFirstPage(tagColParams *,DataPage &,char const *,ulong,Err &)
0x1003c1c9  test    byte ptr [edi], 8
0x1003c1cc  jz      short loc_1003C1EF
0x1003c1ce  mov     eax, [ebp+var_5C]
0x1003c1d1  test    eax, eax
0x1003c1d3  jz      short loc_1003C1D9
0x1003c1d5  dec     word ptr [eax+4Ch]
0x1003c1d9  xor     eax, eax
0x1003c1db  mov     ecx, [ebp+var_C]
0x1003c1de  mov     large fs:0, ecx
0x1003c1e5  pop     ecx
0x1003c1e6  pop     edi
0x1003c1e7  pop     esi
0x1003c1e8  pop     ebx
0x1003c1e9  mov     esp, ebp
0x1003c1eb  pop     ebp
0x1003c1ec  retn    0Ch
0x1003c1ef  mov     ecx, [ebp+var_5C]
0x1003c1f2  mov     ebx, [ebx+10h]
0x1003c1f5  mov     eax, 2040811h
0x1003c1fa  mul     ebx
0x1003c1fc  sub     ebx, edx
0x1003c1fe  shr     ebx, 1
0x1003c200  add     ebx, edx
0x1003c202  shr     ebx, 0Ah
0x1003c205  test    byte ptr [edi], 8
0x1003c208  mov     [ebp+var_18], ebx
0x1003c20b  jnz     loc_1003C733
0x1003c211  lea     eax, [esi+810h]
0x1003c217  mov     [ebp+var_34], eax
0x1003c21a  mov     eax, [ebp+var_24]
0x1003c21d  mov     [ebp+var_24], eax
0x1003c220  xor     eax, eax
0x1003c222  mov     edx, [ebp+arg_0]
0x1003c225  mov     ecx, [edx+8]
0x1003c228  cmp     eax, ecx
0x1003c22a  jnb     loc_1003C730
0x1003c230  sub     ecx, [ebp+var_20]
0x1003c233  imul    eax, ebx, 7F0h
0x1003c239  mov     ebx, [edx+10h]
0x1003c23c  mov     edx, [ebp+var_18]
0x1003c23f  sub     ebx, eax
0x1003c241  mov     eax, 7F0h
0x1003c246  add     ebx, [ebp+var_20]
0x1003c249  sub     eax, ebx
0x1003c24b  cmp     eax, ecx
0x1003c24d  cmovnb  eax, ecx
0x1003c250  mov     [ebp+Size], eax
0x1003c253  mov     eax, [esi+818h]
0x1003c259  cmp     edx, [eax+4]
0x1003c25c  jl      short loc_1003C267
0x1003c25e  mov     [ebp+var_14], 0
0x1003c265  jmp     short loc_1003C27D
0x1003c267  mov     ecx, [eax]
0x1003c269  mov     eax, [eax+0Ch]
0x1003c26c  imul    ecx, edx
0x1003c26f  mov     ecx, [ecx+eax]
0x1003c272  mov     [ebp+var_14], ecx
0x1003c275  test    ecx, ecx
0x1003c277  jnz     loc_1003C454
0x1003c27d  push    edi; struct Err *
0x1003c27e  lea     eax, [ebp+var_5C]
0x1003c281  mov     dword ptr [ebp+var_40], 0
0x1003c288  push    eax; struct DataPage *
0x1003c289  push    ecx; struct tagColParams *
0x1003c28a  mov     ecx, esi; this
0x1003c28c  call    ?AllocatePage@LvDataNew@@QAEKPAUtagColParams@@AAVDataPage@@AAVErr@@@Z; LvDataNew::AllocatePage(tagColParams *,DataPage &,Err &)
0x1003c291  test    byte ptr [edi], 8
0x1003c294  jnz     loc_1003C440
0x1003c29a  push    4; unsigned int
0x1003c29c  lea     eax, [ebp+var_40]
0x1003c29f  push    eax; Src
0x1003c2a0  lea     ecx, [ebp+var_5C]; this
0x1003c2a3  call    ?Insert@DataPage@@QAEKPBEI@Z; DataPage::Insert(uchar const *,uint)
0x1003c2a8  mov     ecx, eax
0x1003c2aa  mov     [ebp+var_14], ecx
0x1003c2ad  test    ecx, ecx
0x1003c2af  jnz     short loc_1003C30A
0x1003c2b1  mov     eax, [edi]
0x1003c2b3  cmp     eax, 8
0x1003c2b6  jge     loc_1003C3BD
0x1003c2bc  test    eax, 0FFFFFFFEh
0x1003c2c1  jz      short loc_1003C2E3
0x1003c2c3  mov     eax, [edi+0Ch]
0x1003c2c6  test    eax, eax
0x1003c2c8  jz      short loc_1003C2D3
0x1003c2ca  push    eax; Block
0x1003c2cb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003c2d0  add     esp, 4
0x1003c2d3  mov     eax, [edi+10h]
0x1003c2d6  test    eax, eax
0x1003c2d8  jz      short loc_1003C2E3
0x1003c2da  push    eax; Block
0x1003c2db  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003c2e0  add     esp, 4
0x1003c2e3  mov     dword ptr [edi], 8
0x1003c2e9  mov     dword ptr [edi+4], 0FFFFFC0Ch
0x1003c2f0  mov     dword ptr [edi+8], 0
0x1003c2f7  mov     dword ptr [edi+0Ch], 0
0x1003c2fe  mov     dword ptr [edi+10h], 0
0x1003c305  jmp     loc_1003C3BA
0x1003c30a  mov     ebx, [ebp+var_58]
0x1003c30d  mov     edx, [ebp+Size]
0x1003c310  movzx   esi, cl
0x1003c313  add     edx, 4
0x1003c316  movzx   eax, word ptr [ebx+esi*2+0Ah]
0x1003c31b  and     eax, 3FFFh
0x1003c320  test    cl, cl
0x1003c322  jnz     short loc_1003C32B
0x1003c324  mov     ecx, 800h
0x1003c329  jmp     short loc_1003C336
0x1003c32b  movzx   ecx, word ptr [ebx+esi*2+8]
0x1003c330  and     ecx, 3FFFh
0x1003c336  sub     ecx, eax
0x1003c338  cmp     ecx, edx
0x1003c33a  jz      short loc_1003C354
0x1003c33c  movzx   eax, word ptr [ebx+2]
0x1003c340  add     eax, ecx
0x1003c342  cmp     edx, eax
0x1003c344  ja      short loc_1003C354
0x1003c346  sub     edx, ecx
0x1003c348  lea     ecx, [ebp+var_5C]
0x1003c34b  push    edx
0x1003c34c  push    1
0x1003c34e  push    esi
0x1003c34f  call    ?AdjustGap@DataPage@@AAEXIW4DPBool@@H@Z; DataPage::AdjustGap(uint,DPBool,int)
0x1003c354  test    byte ptr [edi], 8
0x1003c357  jnz     short loc_1003C3B7
0x1003c359  movzx   ecx, word ptr [ebx+esi*2+0Ah]
0x1003c35e  and     ecx, 3FFFh
0x1003c364  cmp     ecx, 800h
0x1003c36a  ja      short loc_1003C39B
0x1003c36c  test    esi, esi
0x1003c36e  jnz     short loc_1003C377
0x1003c370  mov     eax, 800h
0x1003c375  jmp     short loc_1003C38C
0x1003c377  movzx   eax, word ptr [ebx+esi*2+8]
0x1003c37c  and     eax, 3FFFh
0x1003c381  cmp     eax, 800h
0x1003c386  ja      short loc_1003C39B
0x1003c388  cmp     ecx, eax
0x1003c38a  ja      short loc_1003C39B
0x1003c38c  sub     eax, ecx
0x1003c38e  cmp     eax, 800h
0x1003c393  ja      short loc_1003C39B
0x1003c395  lea     eax, [ecx+ebx]
0x1003c398  mov     [ebp+var_44], eax
0x1003c39b  mov     eax, [ebp+arg_0]
0x1003c39e  push    [ebp+Size]; Size
0x1003c3a1  mov     eax, [eax+4]
0x1003c3a4  add     eax, [ebp+var_20]
0x1003c3a7  push    eax; Src
0x1003c3a8  mov     eax, [ebp+var_44]
0x1003c3ab  add     eax, 4
0x1003c3ae  push    eax; void *
0x1003c3af  call    _memcpy
0x1003c3b4  add     esp, 0Ch
0x1003c3b7  mov     esi, [ebp+var_10]
0x1003c3ba  mov     ecx, [ebp+var_14]
0x1003c3bd  test    byte ptr [edi], 8
0x1003c3c0  mov     ebx, [ebp+var_5C]
0x1003c3c3  jnz     short loc_1003C3EB
0x1003c3c5  mov     eax, [ebx+18h]
0x1003c3c8  push    edi; struct Err *
0x1003c3c9  mov     dword ptr [ebp+var_40], ecx
0x1003c3cc  or      dword ptr [ebx+eax*4+1Ch], 8
0x1003c3d1  lea     eax, [ebp+var_40]
0x1003c3d4  inc     dword ptr [ebx+40h]
0x1003c3d7  mov     ecx, [esi+818h]; this
0x1003c3dd  push    eax; Src
0x1003c3de  push    [ebp+var_18]; int
0x1003c3e1  call    ?Set@Array@@QAEXHPADAAVErr@@@Z; Array::Set(int,char *,Err &)
0x1003c3e6  test    byte ptr [edi], 8
0x1003c3e9  jz      short loc_1003C440
0x1003c3eb  mov     [ebp+var_80], 1
0x1003c3f2  mov     byte ptr [ebp+var_4], 1
0x1003c3f6  test    ebx, ebx
0x1003c3f8  jz      short loc_1003C3FF
0x1003c3fa  mov     eax, [ebx+0Ch]
0x1003c3fd  jmp     short loc_1003C401
  ... truncated ...
```
