# Table::AddReference(Instance *,ushort const *,ushort const *,ushort *,ushort const *,tagTblIdxDef *,IdxRefUpdate,IdxRefDelete,IdxRefEnforce,Err &)

- ea: `0x10056280`
- end: `0x10056b04`
- name: `?AddReference@Table@@QAEXPAVInstance@@PBG1PAG1PAUtagTblIdxDef@@W4IdxRefUpdate@@W4IdxRefDelete@@W4IdxRefEnforce@@AAVErr@@@Z`
- size: `2180`
- prototype: `void __thiscall __high(struct Instance *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, struct tagTblIdxDef *, enum IdxRefUpdate, enum IdxRefDelete, enum IdxRefEnforce, struct Err *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10029e50`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10025db0`
- `0x10025ee0`
- `0x10025fc0`
- `0x10026020`
- `0x100311c0`
- `0x10036910`
- `0x10044860`
- `0x10044950`
- `0x10044cb0`
- `0x1004dbb0`
- `0x10051890`
- `0x10054060`
- `0x10055260`
- `0x10055bc0`
- `0x10056280`
- `0x10056b70`
- `0x10057520`
- `0x10058fa0`
- `0x100591e0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7dc`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`

## string_xrefs

- `0x10056969`: `.TempBogusIndexName`
- `0x100569c9`: `.TempBogusIndexName`

## pseudocode

```c
void __thiscall Table::AddReference(
        struct Table *this,
        struct Instance *a2,
        int a3,
        int a4,
        const WCHAR *a5,
        _WORD *a6,
        _BYTE *a7,
        int a8,
        int a9,
        int a10,
        _BYTE *a11)
{
  _BYTE *v11; // edi
  int v12; // esi
  struct Session *v13; // edx
  int v14; // eax
  struct Session *v15; // edx
  int v16; // eax
  unsigned int v17; // ecx
  int v18; // edx
  Err *v19; // eax
  Err *v20; // ecx
  int v21; // ebx
  int v22; // eax
  unsigned int v23; // edx
  int v24; // edx
  int v25; // edx
  void *v26; // ebx
  int v27; // eax
  int v28; // edx
  __int16 v29; // si
  int v30; // eax
  struct Table *v31; // edx
  int v32; // ecx
  int v33; // ebx
  int v34; // ebx
  int v35; // esi
  void *v36; // eax
  int v37; // ecx
  struct Table *v38; // ecx
  int v39; // eax
  int v40; // eax
  int v41; // edx
  int v42; // ecx
  _DWORD *v43; // eax
  unsigned __int16 *v44; // ebx
  int v45; // ecx
  unsigned int v46; // edx
  unsigned int v47; // ecx
  int v48; // ebx
  char v49; // bl
  int v50; // ecx
  int v51; // eax
  int v52; // eax
  int v53; // ebx
  int v54; // edx
  int v55; // ecx
  unsigned __int16 *v56; // eax
  int v57; // ebx
  int v58; // eax
  struct Table *v59; // ebx
  int v60; // edx
  unsigned int v61; // ecx
  char v62; // al
  unsigned int v63; // ecx
  int v64; // edx
  struct Index *v65; // eax
  Table *v66; // ebx
  struct Table *v67; // [esp-10h] [ebp-9Ch]
  void (__thiscall ***v68)(_DWORD, int); // [esp+28h] [ebp-64h]
  int v69; // [esp+38h] [ebp-54h]
  int v70; // [esp+3Ch] [ebp-50h]
  struct Session *v71; // [esp+40h] [ebp-4Ch]
  IndexColumns *v72; // [esp+48h] [ebp-44h]
  char v73; // [esp+4Fh] [ebp-3Dh]
  struct Index *v74; // [esp+50h] [ebp-3Ch]
  struct Table *v75; // [esp+54h] [ebp-38h]
  unsigned __int16 *v76; // [esp+58h] [ebp-34h]
  unsigned __int16 *v77; // [esp+58h] [ebp-34h]
  unsigned __int16 *v78; // [esp+58h] [ebp-34h]
  unsigned __int16 *v79; // [esp+58h] [ebp-34h]
  unsigned __int16 *v80; // [esp+58h] [ebp-34h]
  char v82; // [esp+63h] [ebp-29h] BYREF
  int v83; // [esp+64h] [ebp-28h] BYREF
  _DWORD v84[2]; // [esp+68h] [ebp-24h] BYREF
  __int16 v85; // [esp+70h] [ebp-1Ch]
  void *Block; // [esp+74h] [ebp-18h]
  void *v87; // [esp+78h] [ebp-14h]
  int v88; // [esp+88h] [ebp-4h]

  v11 = a11;
  ++*((_DWORD *)this + 85);
  v12 = 0;
  v88 = 0;
  v13 = (struct Session *)*((_DWORD *)a2 + 3);
  v73 = 0;
  v74 = 0;
  v68 = 0;
  v75 = 0;
  v71 = v13;
  if ( *((_DWORD *)this + 11) == 2 || *((_DWORD *)this + 12) == 8 )
  {
    v14 = *(_DWORD *)(*((_DWORD *)this + 9) + 104);
    if ( v14 && v14 != 3 )
      goto LABEL_8;
    Err::SetError(a11, -1809, this);
  }
  else
  {
    Err::SetError(a11, -1309, this);
  }
  v13 = v71;
LABEL_8:
  if ( (*a11 & 8) != 0 )
    goto LABEL_18;
  Session::BeginTransaction(v13, 1, a11);
  if ( (*a11 & 8) != 0 )
    goto LABEL_18;
  v15 = v71;
  v16 = 0;
  v73 = 1;
  v17 = *((_DWORD *)v71 + 5);
  if ( v17 )
  {
    while ( 1 )
    {
      v11 = a11;
      if ( *(struct Table **)(*((_DWORD *)v71 + 3) + 4 * v16) == this )
        break;
      if ( ++v16 >= v17 )
      {
        v15 = v71;
        goto LABEL_14;
      }
    }
  }
  else
  {
LABEL_14:
    if ( v16 == v17 )
      Table::AddNotify(this, v15);
  }
  if ( (*v11 & 8) != 0 )
  {
LABEL_18:
    v18 = 0;
  }
  else
  {
    *a7 &= 0xE1u;
    v18 = Table::AddIndex(this, a2, a3, a7, a4, 0, v11, 1);
    v74 = (struct Index *)v18;
  }
  v19 = *(Err **)v11;
  v20 = *(Err **)v11;
  if ( (*(_DWORD *)v11 & 8) == 0 && a8 == 1 )
  {
    v21 = 0;
    do
    {
      v20 = v19;
      v22 = *(_DWORD *)(v18 + 8);
      if ( v21 >= *(_DWORD *)(v22 + 32) )
        break;
      v23 = *(_DWORD *)(*(_DWORD *)(v22 + 28) + 8 * v21);
      if ( v23 > 0xFE )
        v24 = 0;
      else
        v24 = *((_DWORD *)this + v23 + 94);
      if ( (*(_BYTE *)(v24 + 48) & 6) != 0 )
      {
        v76 = *(unsigned __int16 **)(v24 + 4);
        if ( ((unsigned int)v20 & 0xFFFFFFFE) != 0 )
        {
          if ( *((_DWORD *)v11 + 3) )
            operator delete[](*((void **)v11 + 3));
          if ( *((_DWORD *)v11 + 4) )
            operator delete[](*((void **)v11 + 4));
        }
        *(_DWORD *)v11 = 8;
        *((_DWORD *)v11 + 1) = -1048;
        *((_DWORD *)v11 + 2) = -8235;
        Err::CopyString(v20, (unsigned __int16 **)v11 + 3, v76);
        *((_DWORD *)v11 + 4) = 0;
        LOBYTE(v88) = 0;
      }
      v20 = *(Err **)v11;
      ++v21;
      v18 = (int)v74;
      v19 = *(Err **)v11;
    }
    while ( (*(_DWORD *)v11 & 8) == 0 );
    v12 = 0;
  }
  if ( ((unsigned __int8)v20 & 8) != 0 )
    goto LABEL_43;
  Table::GetName(this, a2);
  v25 = *((_DWORD *)this + 9);
  v26 = *(void **)(v25 + 224);
  if ( !v26 )
    v26 = (void *)*(unsigned __int16 *)(v25 + 86);
  v27 = *(_DWORD *)(v25 + 60);
  v28 = *(_DWORD *)(v25 + 92);
  Block = v26;
  v29 = *(_WORD *)(v27 + 100);
  v84[1] = v28;
  v85 = v29;
  v87 = 0;
  v30 = *(_DWORD *)this;
  v84[0] = *((_DWORD *)this + 1);
  v83 = v30;
  if ( !LString::Compare(&v83, a5, 2 * wcslen(a5), 0) )
  {
    v31 = this;
    v12 = 0;
    v32 = (int)this;
    v75 = this;
    goto LABEL_45;
  }
  v33 = Instance::OpenCursor(a2, a5, 2, v11, 0);
  v68 = (void (__thiscall ***)(_DWORD, int))v33;
  if ( (*v11 & 8) != 0 )
  {
    v12 = 0;
LABEL_43:
    v32 = 0;
    goto LABEL_44;
  }
  v32 = (*(int (__thiscall **)(int))(*(_DWORD *)v33 + 60))(v33);
  v12 = 0;
  v75 = (struct Table *)v32;
LABEL_44:
  v31 = this;
LABEL_45:
  if ( (*v11 & 8) == 0 )
  {
    v34 = 0;
    if ( a6 && *a6 )
    {
      v72 = (IndexColumns *)operator new(0xCu);
      LOBYTE(v88) = 2;
      v35 = 10;
      if ( *(_DWORD *)(*((_DWORD *)this + 9) + 68) == 1 )
        v35 = 255;
      v36 = operator new[](8 * v35);
      LOBYTE(v88) = 0;
      *((_DWORD *)v72 + 2) = v35;
      *(_DWORD *)v72 = v36;
      *((_DWORD *)v72 + 1) = 0;
      if ( (*v11 & 8) == 0 )
      {
        Table::BuildIndexColumns(v75, a6, v72, 0, v11);
        if ( (*v11 & 1) == 0 && *((_DWORD *)v11 + 1) == -1406 )
          Err::OverrideError((Err *)v11, -1404);
        if ( (*v11 & 8) == 0 )
        {
          if ( *((_DWORD *)v72 + 1) != *(_DWORD *)(*((_DWORD *)v74 + 2) + 32) )
            Err::SetError(v11, -1003, *((_DWORD *)v74 + 2));
          if ( (*v11 & 8) == 0 )
          {
            if ( v75 == this
              && IndexColumns::SameColumnNumbers(v72, (const struct IndexColumns *)(*((_DWORD *)v74 + 2) + 28)) )
            {
              Err::SetError(v11, -1407, v37);
            }
            if ( (*v11 & 8) == 0 )
            {
LABEL_62:
              v38 = v75;
              while ( 1 )
              {
                v39 = v34++;
                if ( v39 < 0 || v39 >= *((_DWORD *)v38 + 6) || *((_DWORD *)v38 + v39 + 381) == -1 )
                  break;
                _mm_lfence();
                v12 = *((_DWORD *)v38 + *((_DWORD *)v38 + v39 + 381) + 349);
                v70 = v12;
                if ( !v12 )
                  goto LABEL_93;
                v40 = *(_DWORD *)(v12 + 8);
                v77 = (unsigned __int16 *)v40;
                v41 = *((_DWORD *)v72 + 1);
                if ( v41 == *(_DWORD *)(v40 + 32) )
                {
                  v42 = 0;
                  if ( v41 > 0 )
                  {
                    v43 = *(_DWORD **)v72;
                    while ( 1 )
                    {
                      v12 = v70;
                      v11 = a11;
                      if ( v43[2 * v42] != *(_DWORD *)(*((_DWORD *)v77 + 7) + 8 * v42) )
                        goto LABEL_62;
                      v43 = *(_DWORD **)v72;
                      if ( ++v42 >= v41 )
                      {
                        v40 = *(_DWORD *)(v70 + 8);
                        break;
                      }
                    }
                  }
                  if ( (*(_BYTE *)(v40 + 64) & 1) != 0 )
                  {
                    Err::Reset((Err *)v11);
                    v44 = 0;
                    v78 = 0;
                    v45 = *((_DWORD *)v74 + 2);
                    if ( *(int *)(v45 + 32) <= 0 )
                      goto LABEL_93;
                    while ( 1 )
                    {
                      v46 = *(_DWORD *)(*(_DWORD *)(*(_DWORD *)(v12 + 8) + 28) + 8 * (_DWORD)v44);
                      v47 = *(_DWORD *)(*(_DWORD *)(v45 + 28) + 8 * (_DWORD)v44);
                      v48 = v46 > 0xFE ? 0 : *((_DWORD *)v75 + v46 + 94);
                      v69 = v47 > 0xFE ? 0 : *((_DWORD *)this + v47 + 94);
                      v49 = (*(int (__thiscall **)(int))(*(_DWORD *)v48 + 16))(v48);
                      if ( v49 != (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v69 + 16))(v69) )
                        break;
                      v12 = v70;
                      v44 = (unsigned __int16 *)((char *)v78 + 1);
                      v78 = v44;
                      v45 = *((_DWORD *)v74 + 2);
                      if ( (int)v44 >= *(_DWORD *)(v45 + 32) )
                        goto LABEL_93;
                    }
                    Err::SetError(v11, -3560, v50);
                    break;
                  }
                  v38 = v75;
                  if ( *(int *)v11 < 8 )
                  {
                    if ( (*(_DWORD *)v11 & 0xFFFFFFFE) != 0 )
                    {
                      if ( *((_DWORD *)v11 + 3) )
                        operator delete[](*((void **)v11 + 3));
                      if ( *((_DWORD *)v11 + 4) )
                        operator delete[](*((void **)v11 + 4));
                    }
                    *(_DWORD *)v11 = 8;
                    *((_DWORD *)v11 + 1) = -1522;
                    *((_DWORD *)v11 + 2) = 0;
                    *((_DWORD *)v11 + 3) = 0;
                    *((_DWORD *)v11 + 4) = 0;
                    goto LABEL_62;
                  }
                }
              }
            }
          }
        }
      }
      v12 = 0;
LABEL_93:
      if ( *(_DWORD *)v72 )
        operator delete[](*(void **)v72);
      operator delete(v72, 0xCu);
    }
    else
    {
      do
      {
        v51 = v34++;
        if ( v51 < 0 || v51 >= *(_DWORD *)(v32 + 24) || *(_DWORD *)(v32 + 4 * v51 + 1524) == -1 )
        {
          v12 = 0;
LABEL_109:
          if ( *(int *)v11 < 8 )
          {
            if ( (*(_DWORD *)v11 & 0xFFFFFFFE) != 0 )
            {
              if ( *((_DWORD *)v11 + 3) )
                operator delete[](*((void **)v11 + 3));
              if ( *((_DWORD *)v11 + 4) )
                operator delete[](*((void **)v11 + 4));
            }
            *(_DWORD *)v11 = 8;
            *((_DWORD *)v11 + 1) = -1404;
            *((_DWORD *)v11 + 2) = 0;
            *((_DWORD *)v11 + 3) = 0;
            *((_DWORD *)v11 + 4) = 0;
          }
          goto LABEL_116;
        }
        _mm_lfence();
        v12 = *(_DWORD *)(v32 + 4 * *(_DWORD *)(v32 + 4 * v51 + 1524) + 1396);
        if ( !v12 )
          goto LABEL_109;
      }
      while ( (*(_BYTE *)(v12 + 40) & 1) == 0 );
      if ( (struct Table *)v32 == v31 )
      {
        v52 = *(_DWORD *)(v12 + 8);
        v53 = *((_DWORD *)v74 + 2);
        v54 = *(_DWORD *)(v52 + 32);
        if ( v54 == *(_DWORD *)(v53 + 32) )
        {
          v55 = 0;
          if ( v54 <= 0 )
          {
LABEL_107:
            Err::SetError(v11, -1407, v55);
            v12 = 0;
          }
          else
          {
            v56 = *(unsigned __int16 **)(v52 + 28);
            v57 = *(_DWORD *)(v53 + 28);
            v79 = v56;
            while ( *(_DWORD *)&v56[4 * v55] == *(_DWORD *)(v57 + 8 * v55) )
            {
              v56 = v79;
              if ( ++v55 >= v54 )
                goto LABEL_107;
            }
          }
        }
      }
    }
  }
LABEL_116:
  v58 = *(_DWORD *)v11;
  if ( (*(_DWORD *)v11 & 8) != 0 )
    goto LABEL_125;
  if ( !v12 && v58 < 8 )
  {
    if ( (v58 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)v11 + 3) )
        operator delete[](*((void **)v11 + 3));
      if ( *((_DWORD *)v11 + 4) )
        operator delete[](*((void **)v11 + 4));
    }
    *(_DWORD *)v11 = 8;
    *((_DWORD *)v11 + 1) = -1522;
    *((_DWORD *)v11 + 2) = 0;
    *((_DWORD *)v11 + 3) = 0;
    *((_DWORD *)v11 + 4) = 0;
LABEL_125:
    v59 = v75;
    goto LABEL_126;
  }
  v64 = *(_DWORD *)(v12 + 8);
  v59 = v75;
  v82 = *(_BYTE *)(v64 + 64) & 1 | v82 & 0xFC;
  v82 ^= (v82 ^ (2 * *(_BYTE *)(v64 + 64))) & 4;
  v82 ^= (v82 ^ (2 * *(_BYTE *)(v64 + 64))) & 8;
  v82 ^= (v82 ^ (2 * *(_BYTE *)(v64 + 64))) & 0x10;
  v12 = Table::AddIndex(v75, a2, L".TempBogusIndexName", &v82, a6, 0, v11, 1);
LABEL_126:
  v80 = (unsigned __int16 *)(v12 + 36);
  if ( (*v11 & 8) != 0 )
  {
    v80 = (unsigned __int16 *)(v12 + 36);
  }
  else
  {
    v60 = *(_DWORD *)(v12 + 36);
    v61 = 2;
    for ( v84[0] = 7471150; v60; *((_WORD *)v84 + v61++) = (v62 & 0xF) + 65 )
    {
      if ( v61 >= 0xA )
        break;
      v62 = v60;
      v60 >>= 4;
    }
    v63 = 2 * v61;
    if ( v63 >= 0x14 )
      __report_rangecheckfailure();
    *(_WORD *)((char *)v84 + v63) = 0;
    Table::RenameIndex(v59, a2, L".TempBogusIndexName", v84, v11, 0);
  }
  if ( (*v11 & 8) != 0 )
  {
    v65 = v74;
  }
  else
  {
    *(_BYTE *)(v12 + 41) = 1;
    *(_DWORD *)(v12 + 48) = *((_DWORD *)this + 10);
    *(_DWORD *)(v12 + 44) = *((_DWORD *)v74 + 9);
    *(_DWORD *)(v12 + 52) = a8;
    *(_DWORD *)(v12 + 56) = a9;
    *(_DWORD *)(v12 + 60) = a10;
    *((_BYTE *)v74 + 41) = 2;
    *((_DWORD *)v74 + 12) = *((_DWORD *)v59 + 10);
    *((_DWORD *)v74 + 11) = *(_DWORD *)v80;
    v65 = v74;
    *((_DWORD *)v74 + 13) = a8;
    v11 = a11;
    *((_DWORD *)v74 + 14) = a9;
    *((_DWORD *)v74 + 15) = a10;
  }
  if ( (*v11 & 8) != 0 )
  {
    v66 = this;
  }
  else
  {
    v67 = v59;
    v66 = this;
    Table::CheckForOrphans(this, a2, v67, (struct Index *)v12, v65, (struct Err *)v11);
  }
  if ( v73 )
  {
    if ( (*v11 & 8) != 0 || (Session::CommitTransaction(v71, (struct Err *)v11, 0), (*v11 & 8) != 0) )
    {
      v84[0] = 1;
      LOBYTE(v88) = 3;
      Session::AbortTransaction(v71, (struct Err *)v84);
      LOBYTE(v88) = 0;
      if ( (v84[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v87 )
          operator delete[](v87);
      }
    }
    else if ( v68 )
    {
      (**v68)(v68, 1);
    }
  }
  Table::DDLPerformed(v66, a2);
  --*((_DWORD *)v66 + 85);
}

```

## disassembly

```asm
0x10056280  mov     edi, edi
0x10056282  push    ebp
0x10056283  mov     ebp, esp
0x10056285  push    0FFFFFFFFh
0x10056287  push    offset ?AddReference@Table@@QAEXPAVInstance@@PBG1PAG1PAUtagTblIdxDef@@W4IdxRefUpdate@@W4IdxRefDelete@@W4IdxRefEnforce@@AAVErr@@@Z_SEH
0x1005628c  mov     eax, large fs:0
0x10056292  push    eax
0x10056293  sub     esp, 70h
0x10056296  mov     eax, ___security_cookie
0x1005629b  xor     eax, ebp
0x1005629d  mov     [ebp+var_10], eax
0x100562a0  push    ebx
0x100562a1  push    esi
0x100562a2  push    edi; unsigned int
0x100562a3  push    eax; unsigned int
0x100562a4  lea     eax, [ebp+var_C]
0x100562a7  mov     large fs:0, eax
0x100562ad  mov     [ebp+var_30], ecx
0x100562b0  mov     eax, [ebp+arg_4]
0x100562b3  mov     edx, [ebp+arg_0]
0x100562b6  mov     edi, [ebp+arg_24]
0x100562b9  mov     ebx, [ebp+arg_14]
0x100562bc  inc     dword ptr [ecx+154h]
0x100562c2  mov     [ebp+var_50], eax
0x100562c5  mov     eax, [ebp+arg_8]
0x100562c8  mov     [ebp+var_34], eax
0x100562cb  mov     eax, [ebp+arg_C]
0x100562ce  mov     [ebp+var_54], eax
0x100562d1  mov     eax, [ebp+arg_10]
0x100562d4  mov     [ebp+var_48], edx
0x100562d7  mov     [ebp+var_5C], eax
0x100562da  mov     [ebp+var_60], edi
0x100562dd  mov     [ebp+var_68], ecx
0x100562e0  xor     esi, esi
0x100562e2  mov     [ebp+var_4], 0
0x100562e9  cmp     dword ptr [ecx+2Ch], 2
0x100562ed  mov     edx, [edx+0Ch]
0x100562f0  mov     [ebp+var_3D], 0
0x100562f4  mov     [ebp+var_3C], esi
0x100562f7  mov     [ebp+var_64], esi
0x100562fa  mov     [ebp+var_38], esi
0x100562fd  mov     [ebp+var_4C], edx
0x10056300  jz      short loc_10056310
0x10056302  cmp     dword ptr [ecx+30h], 8
0x10056306  jz      short loc_10056310
0x10056308  push    ecx
0x10056309  push    0FFFFFAE3h
0x1005630e  jmp     short loc_10056325
0x10056310  mov     eax, [ecx+24h]
0x10056313  mov     eax, [eax+68h]
0x10056316  test    eax, eax
0x10056318  jz      short loc_1005631F
0x1005631a  cmp     eax, 3
0x1005631d  jnz     short loc_1005632F
0x1005631f  push    ecx
0x10056320  push    0FFFFF8EFh
0x10056325  mov     ecx, edi
0x10056327  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005632c  mov     edx, [ebp+var_4C]
0x1005632f  test    byte ptr [edi], 8
0x10056332  jnz     short loc_1005639C
0x10056334  push    edi
0x10056335  push    1
0x10056337  mov     ecx, edx
0x10056339  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x1005633e  test    byte ptr [edi], 8
0x10056341  jnz     short loc_1005639C
0x10056343  mov     edx, [ebp+var_4C]
0x10056346  xor     eax, eax
0x10056348  mov     [ebp+var_3D], 1
0x1005634c  mov     ecx, [edx+14h]
0x1005634f  test    ecx, ecx
0x10056351  jz      short loc_10056369
0x10056353  mov     edx, [edx+0Ch]
0x10056356  mov     edi, [ebp+var_30]
0x10056359  cmp     [edx+eax*4], edi
0x1005635c  mov     edi, [ebp+var_60]
0x1005635f  jz      short loc_10056376
0x10056361  inc     eax
0x10056362  cmp     eax, ecx
0x10056364  jb      short loc_10056356
0x10056366  mov     edx, [ebp+var_4C]
0x10056369  cmp     eax, ecx
0x1005636b  jnz     short loc_10056376
0x1005636d  mov     ecx, [ebp+var_30]; this
0x10056370  push    edx; struct Session *
0x10056371  call    ?AddNotify@Table@@AAEXPAVSession@@@Z; Table::AddNotify(Session *)
0x10056376  test    byte ptr [edi], 8
0x10056379  jnz     short loc_1005639C
0x1005637b  mov     ecx, [ebp+var_30]
0x1005637e  and     byte ptr [ebx], 0E1h
0x10056381  push    1
0x10056383  push    edi
0x10056384  push    0
0x10056386  push    [ebp+var_34]
0x10056389  push    ebx
0x1005638a  push    [ebp+var_50]
0x1005638d  push    [ebp+var_48]
0x10056390  call    ?AddIndex@Table@@QAEPAVIndex@@PAVInstance@@PBGPAUtagTblIdxDef@@1IAAVErr@@W4TblRefOrIdx@@@Z; Table::AddIndex(Instance *,ushort const *,tagTblIdxDef *,ushort const *,uint,Err &,TblRefOrIdx)
0x10056395  mov     edx, eax
0x10056397  mov     [ebp+var_3C], edx
0x1005639a  jmp     short loc_1005639E
0x1005639c  xor     edx, edx
0x1005639e  mov     eax, [edi]
0x100563a0  mov     ecx, eax
0x100563a2  test    al, 8
0x100563a4  jnz     loc_1005645D
0x100563aa  cmp     [ebp+arg_18], 1
0x100563ae  jnz     loc_1005645D
0x100563b4  mov     esi, [ebp+var_30]
0x100563b7  xor     ebx, ebx
0x100563b9  nop     dword ptr [eax+00000000h]
0x100563c0  mov     ecx, eax
0x100563c2  mov     eax, [edx+8]
0x100563c5  cmp     ebx, [eax+20h]
0x100563c8  jge     loc_1005645B
0x100563ce  mov     eax, [eax+1Ch]
0x100563d1  mov     edx, [eax+ebx*8]
0x100563d4  test    edx, edx
0x100563d6  js      short loc_100563E9
0x100563d8  cmp     edx, 0FFh
0x100563de  jnb     short loc_100563E9
0x100563e0  mov     edx, [esi+edx*4+178h]
0x100563e7  jmp     short loc_100563EB
0x100563e9  xor     edx, edx
0x100563eb  test    byte ptr [edx+30h], 6
0x100563ef  jz      short loc_1005644A
0x100563f1  mov     edx, [edx+4]
0x100563f4  mov     [ebp+var_34], edx
0x100563f7  test    ecx, 0FFFFFFFEh
0x100563fd  jz      short loc_1005641F
0x100563ff  mov     eax, [edi+0Ch]
0x10056402  test    eax, eax
0x10056404  jz      short loc_1005640F
0x10056406  push    eax; Block
0x10056407  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005640c  add     esp, 4
0x1005640f  mov     eax, [edi+10h]
0x10056412  test    eax, eax
0x10056414  jz      short loc_1005641F
0x10056416  push    eax; Block
0x10056417  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005641c  add     esp, 4
0x1005641f  push    [ebp+var_34]; unsigned __int16 *
0x10056422  lea     eax, [edi+0Ch]
0x10056425  mov     dword ptr [edi], 8
0x1005642b  push    eax; unsigned __int16 **
0x1005642c  mov     dword ptr [edi+4], 0FFFFFBE8h
0x10056433  mov     dword ptr [edi+8], 0FFFFDFD5h
0x1005643a  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x1005643f  mov     dword ptr [edi+10h], 0
0x10056446  mov     byte ptr [ebp+var_4], 0
0x1005644a  mov     ecx, [edi]
0x1005644c  inc     ebx
0x1005644d  mov     edx, [ebp+var_3C]
0x10056450  mov     eax, ecx
0x10056452  test    cl, 8
0x10056455  jz      loc_100563C0
0x1005645b  xor     esi, esi
0x1005645d  test    cl, 8
0x10056460  jnz     loc_10056517
0x10056466  push    [ebp+var_48]; struct Instance *
0x10056469  mov     ebx, [ebp+var_30]
0x1005646c  mov     ecx, ebx; this
0x1005646e  call    ?GetName@Table@@QAEPAGPAVInstance@@@Z; Table::GetName(Instance *)
0x10056473  mov     edx, [ebx+24h]
0x10056476  mov     ebx, [edx+0E0h]
0x1005647c  test    ebx, ebx
0x1005647e  jnz     short loc_10056484
0x10056480  movzx   ebx, word ptr [edx+56h]
0x10056484  mov     eax, [edx+3Ch]
0x10056487  mov     edx, [edx+5Ch]
0x1005648a  mov     [ebp+Block], ebx
0x1005648d  mov     ebx, [ebp+var_54]
0x10056490  movzx   esi, word ptr [eax+64h]
0x10056494  mov     eax, [ebp+var_30]
0x10056497  mov     [ebp+var_20], edx
0x1005649a  mov     [ebp+var_1C], si
0x1005649e  mov     [ebp+var_14], 0
0x100564a5  mov     ecx, [eax+4]
0x100564a8  mov     eax, [eax]
0x100564aa  mov     [ebp+var_24], ecx
0x100564ad  mov     ecx, ebx
0x100564af  mov     [ebp+var_28], eax
0x100564b2  lea     edx, [ecx+2]
0x100564b5  mov     ax, [ecx]
0x100564b8  add     ecx, 2
0x100564bb  test    ax, ax
0x100564be  jnz     short loc_100564B5
0x100564c0  sub     ecx, edx
0x100564c2  sar     ecx, 1
0x100564c4  push    0
0x100564c6  lea     eax, [ecx+ecx]
0x100564c9  push    eax
0x100564ca  push    ebx
0x100564cb  lea     ecx, [ebp+var_28]
0x100564ce  call    ?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z; LString::Compare(uchar *,uint,LSpec)
0x100564d3  test    eax, eax
0x100564d5  jnz     short loc_100564E3
0x100564d7  mov     edx, [ebp+var_30]
0x100564da  xor     esi, esi
0x100564dc  mov     ecx, edx
0x100564de  mov     [ebp+var_38], ecx
0x100564e1  jmp     short loc_1005651C
0x100564e3  mov     ecx, [ebp+var_48]
0x100564e6  push    0
0x100564e8  push    edi
0x100564e9  push    2
0x100564eb  push    ebx
0x100564ec  call    ?OpenCursor@Instance@@QAEPAVCursor@@PBGW4TblMode@@AAVErr@@E@Z; Instance::OpenCursor(ushort const *,TblMode,Err &,uchar)
0x100564f1  test    byte ptr [edi], 8
0x100564f4  mov     ebx, eax
0x100564f6  mov     [ebp+var_64], ebx
0x100564f9  jnz     short loc_10056515
0x100564fb  mov     eax, [ebx]
0x100564fd  mov     esi, [eax+3Ch]
0x10056500  mov     ecx, esi
0x10056502  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10056508  mov     ecx, ebx
0x1005650a  call    esi
0x1005650c  mov     ecx, eax
0x1005650e  xor     esi, esi
0x10056510  mov     [ebp+var_38], ecx
0x10056513  jmp     short loc_10056519
0x10056515  xor     esi, esi
0x10056517  xor     ecx, ecx
0x10056519  mov     edx, [ebp+var_30]
0x1005651c  test    byte ptr [edi], 8
0x1005651f  jnz     loc_100568B3
0x10056525  mov     eax, [ebp+var_5C]
0x10056528  xor     ebx, ebx
0x1005652a  test    eax, eax
0x1005652c  jz      loc_100567E2
0x10056532  cmp     [eax], bx
0x10056535  jz      loc_100567E2
0x1005653b  push    0Ch; Size
0x1005653d  call    ??2@YAPAXI@Z; operator new(uint)
0x10056542  mov     [ebp+var_44], eax
0x10056545  mov     [ebp+var_34], eax
0x10056548  mov     eax, [ebp+var_30]
0x1005654b  mov     ecx, 0FFh
0x10056550  mov     byte ptr [ebp+var_4], 2
0x10056554  mov     esi, 0Ah
0x10056559  mov     eax, [eax+24h]
0x1005655c  cmp     dword ptr [eax+44h], 1
0x10056560  cmovz   esi, ecx
0x10056563  lea     eax, ds:0[esi*8]
0x1005656a  push    eax; unsigned int
0x1005656b  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10056570  mov     edx, [ebp+var_44]
0x10056573  add     esp, 8
0x10056576  mov     byte ptr [ebp+var_4], bl
0x10056579  mov     [edx+8], esi
0x1005657c  mov     esi, [ebp+var_38]
0x1005657f  mov     [edx], eax
0x10056581  mov     [edx+4], ebx
0x10056584  test    byte ptr [edi], 8
0x10056587  jnz     loc_100567BE
0x1005658d  push    edi
0x1005658e  push    ebx
0x1005658f  push    edx
0x10056590  push    [ebp+var_5C]
0x10056593  mov     ecx, esi
0x10056595  call    ?BuildIndexColumns@Table@@AAEXPBGAAVIndexColumns@@W4TblIdxDirection@@AAVErr@@@Z; Table::BuildIndexColumns(ushort const *,IndexColumns &,TblIdxDirection,Err &)
0x1005659a  test    byte ptr [edi], 1
0x1005659d  jnz     short loc_100565B4
0x1005659f  cmp     dword ptr [edi+4], 0FFFFFA82h
0x100565a6  jnz     short loc_100565B4
0x100565a8  push    0FFFFFA84h; int
0x100565ad  mov     ecx, edi; this
0x100565af  call    ?OverrideError@Err@@QAEXJ@Z; Err::OverrideError(long)
0x100565b4  test    byte ptr [edi], 8
0x100565b7  mov     edx, [ebp+var_44]
0x100565ba  jnz     loc_100567BE
0x100565c0  mov     eax, [ebp+var_3C]
0x100565c3  mov     ecx, [eax+8]
0x100565c6  mov     eax, [edx+4]
0x100565c9  cmp     eax, [ecx+20h]
0x100565cc  jz      short loc_100565DB
0x100565ce  push    ecx
0x100565cf  push    0FFFFFC15h
0x100565d4  mov     ecx, edi
0x100565d6  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100565db  test    byte ptr [edi], 8
0x100565de  jnz     loc_100567BE
0x100565e4  cmp     esi, [ebp+var_30]
0x100565e7  jnz     short loc_1005660C
0x100565e9  mov     eax, [ebp+var_3C]
0x100565ec  mov     ecx, [ebp+var_44]; this
0x100565ef  mov     eax, [eax+8]
0x100565f2  add     eax, 1Ch
0x100565f5  push    eax; struct IndexColumns *
0x100565f6  call    ?SameColumnNumbers@IndexColumns@@QAEEABV1@@Z; IndexColumns::SameColumnNumbers(IndexColumns const &)
0x100565fb  test    al, al
0x100565fd  jz      short loc_1005660C
0x100565ff  push    ecx
0x10056600  push    0FFFFFA81h
0x10056605  mov     ecx, edi
0x10056607  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005660c  test    byte ptr [edi], 8
  ... truncated ...
```
