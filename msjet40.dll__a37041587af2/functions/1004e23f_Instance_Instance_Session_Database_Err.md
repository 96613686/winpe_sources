# Instance::Instance(Session *,Database *,Err &)

- ea: `0x1004e23f`
- end: `0x1004e67a`
- name: `??0Instance@@QAE@PAVSession@@PAVDatabase@@AAVErr@@@Z`
- size: `1083`
- prototype: `Instance *__thiscall(Instance *__hidden this, struct Session *, struct Database *, struct Err *)`
- caller_count: `3`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1005dec1`
- `0x1005e0ce`
- `0x1005e281`

## callees

- `0x1004e23f`
- `0x1004e680`
- `0x10050190`
- `0x1005426d`
- `0x10057a33`
- `0x10057c80`
- `0x10058f34`
- `0x10059131`
- `0x100596a3`
- `0x1005c239`
- `0x1005ec0b`
- `0x100618a3`
- `0x10061958`
- `0x10061993`
- `0x1006bf2d`
- `0x10074d41`
- `0x10074d75`
- `0x10123110`
- `0x10123c5a`
- `0x10123c92`
- `0x10124048`
- `0x1012410f`
- `0x1012413e`

## string_xrefs

- `0x1004e5a8`: `DateCreate`
- `0x1004e5bf`: `DateCreate`
- `0x1004e5d5`: `DateUpdate`
- `0x1004e5ec`: `DateUpdate`

## pseudocode

```c
Instance *__thiscall Instance::Instance(Instance *this, struct Session *a2, struct Database *a3, struct Err *a4)
{
  struct IAccMeth *AccessMethod; // eax
  Database *v6; // ecx
  struct Table *v7; // eax
  Table *v8; // eax
  int v9; // ecx
  struct Err *v10; // ecx
  struct Table *Table; // eax
  Table *v12; // esi
  int v13; // ecx
  int v14; // eax
  struct Err *v15; // ecx
  int v16; // ecx
  void *v17; // eax
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  Table *v21; // esi
  int ColumnFromName; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  int v36; // eax
  int v37; // ecx
  Table *Block; // [esp+14h] [ebp-1Ch]
  Table *Blocka; // [esp+14h] [ebp-1Ch]
  Table *v41; // [esp+1Ch] [ebp-14h]
  int v42; // [esp+20h] [ebp-10h]

  Collection::Collection(this, 0x32u, a4);
  *((_DWORD *)this + 3) = a2;
  *((_DWORD *)this + 4) = a3;
  *((_DWORD *)this + 5) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 7) = -1;
  *((_DWORD *)this + 8) = -1;
  *((_DWORD *)this + 9) = -1;
  *((_DWORD *)this + 10) = -1;
  *((_DWORD *)this + 11) = -1;
  *((_DWORD *)this + 12) = -1;
  *((_DWORD *)this + 13) = -1;
  *((_DWORD *)this + 14) = -1;
  *((_DWORD *)this + 16) = 1;
  *((_DWORD *)this + 15) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 18) = 0;
  v42 = 0;
  if ( (*(_BYTE *)a4 & 8) != 0 )
    return this;
  Collection::AddObject((struct Session *)((char *)a2 + 156), this, a4);
  if ( (*(_BYTE *)a4 & 8) != 0 )
    return this;
  AccessMethod = Session::GetAccessMethod(a2, a3, a4);
  v6 = (Database *)*((_DWORD *)this + 4);
  *((_DWORD *)this + 15) = AccessMethod;
  if ( *((_DWORD *)v6 + 18) != 1 )
  {
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
LABEL_64:
      Collection::RemoveObject((struct Session *)((char *)a2 + 156), this);
      return this;
    }
    if ( *((_DWORD *)a3 + 24) == 2 )
    {
LABEL_20:
      Table = Database::FindTable(*((Database **)this + 4), *(_DWORD *)(*((_DWORD *)this + 4) + 400));
      v12 = Table;
      v41 = Table;
      if ( Table )
      {
        Table::CompatibleMode(Table, *((_DWORD *)this + 3), 1, a4);
      }
      else
      {
        Blocka = (Table *)operator new(0x770u);
        v12 = Table::Table(Blocka, *((struct Database **)this + 4), a4);
        v41 = v12;
        if ( v12 )
          v42 = 1;
        else
          Err::SetError(a4, -1011, v13);
        if ( (*(_BYTE *)a4 & 8) == 0 )
        {
          v14 = *((_DWORD *)this + 4);
          if ( *((_DWORD *)a3 + 24) == 2 )
            Table::Open(v12, this, *(_DWORD *)(v14 + 400), 6, a4);
          else
            Table::Open(v12, this, *(_DWORD *)(v14 + 400), 1, a4);
          if ( (*(_BYTE *)a4 & 8) == 0 )
            Table::SetName(v12, L"MSysObjects", v15);
        }
      }
      v16 = v42;
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_40;
      v17 = operator new(0x198u);
      v18 = Cursor::Cursor(v17, this, v12, 1, 1, a4, 0, 0);
      *((_DWORD *)this + 5) = v18;
      if ( v18 )
      {
        if ( (*(_BYTE *)a4 & 8) != 0 )
        {
          (**(void (__thiscall ***)(int, int))v18)(v18, 1);
          v16 = 0;
          *((_DWORD *)this + 5) = 0;
          if ( v42 != 1 )
            v16 = v42;
          goto LABEL_40;
        }
        *(_DWORD *)(v18 + 68) = 0;
      }
      else
      {
        Err::SetError(a4, -1011, v19);
      }
      v16 = v42;
LABEL_40:
      v20 = *(_DWORD *)a4;
      if ( (*(_DWORD *)a4 & 8) != 0 && v16 == 1 )
      {
        if ( *((_DWORD *)v41 + 12) != 10 )
        {
          Table::`scalar deleting destructor'(v41, (unsigned int)v41);
          v20 = *(_DWORD *)a4;
        }
        v21 = 0;
      }
      else
      {
        v21 = v41;
      }
      if ( (v20 & 8) == 0 )
      {
        ColumnFromName = Table::FindColumnFromName(v21, L"ParentId");
        *((_DWORD *)this + 7) = ColumnFromName;
        if ( ColumnFromName == -1 )
          Err::SetError(a4, -1206, -8188, L"ParentId", 0, v23);
        v24 = Table::FindColumnFromName(v21, L"Id");
        *((_DWORD *)this + 8) = v24;
        if ( v24 == -1 )
          Err::SetError(a4, -1206, -8188, L"Id", 0, v25);
        v26 = Table::FindColumnFromName(v21, L"Name");
        *((_DWORD *)this + 9) = v26;
        if ( v26 == -1 )
          Err::SetError(a4, -1206, -8188, L"Name", 0, v27);
        v28 = Table::FindColumnFromName(v21, L"Type");
        *((_DWORD *)this + 10) = v28;
        if ( v28 == -1 )
          Err::SetError(a4, -1206, -8188, L"Type", 0, v29);
        v30 = Table::FindColumnFromName(v21, L"DateCreate");
        *((_DWORD *)this + 11) = v30;
        if ( v30 == -1 )
          Err::SetError(a4, -1206, -8188, L"DateCreate", 0, v31);
        v32 = Table::FindColumnFromName(v21, L"DateUpdate");
        *((_DWORD *)this + 12) = v32;
        if ( v32 == -1 )
          Err::SetError(a4, -1206, -8188, L"DateUpdate", 0, v33);
        v34 = Table::FindColumnFromName(v21, L"Owner");
        *((_DWORD *)this + 13) = v34;
        if ( v34 == -1 )
          Err::SetError(a4, -1206, -8188, L"Owner", 0, v35);
        v36 = Table::FindColumnFromName(v21, L"Flags");
        *((_DWORD *)this + 14) = v36;
        if ( v36 == -1 )
          Err::SetError(a4, -1206, -8188, L"Flags", 0, v37);
      }
      goto LABEL_63;
    }
    v7 = Database::FindTable(v6, *((_DWORD *)v6 + 101));
    *((_DWORD *)this + 18) = v7;
    if ( v7 )
    {
      Table::CompatibleMode(v7, *((_DWORD *)this + 3), 1, a4);
LABEL_18:
      if ( (*(_BYTE *)a4 & 8) == 0 )
        ++*(_DWORD *)(*((_DWORD *)this + 18) + 80);
      goto LABEL_20;
    }
    Block = (Table *)operator new(0x770u);
    v8 = Table::Table(Block, *((struct Database **)this + 4), a4);
    *((_DWORD *)this + 18) = v8;
    if ( !v8 )
      Err::SetError(a4, -1011, v9);
    if ( (*(_DWORD *)a4 & 8) != 0 )
      goto LABEL_18;
    Table::Open(*((_DWORD *)this + 18), this, *(_DWORD *)(*((_DWORD *)this + 4) + 404), 1, a4);
    if ( (*(_DWORD *)a4 & 8) == 0 )
    {
LABEL_16:
      Table::SetName(*((Table **)this + 18), L"MSysACEs", v10);
      goto LABEL_18;
    }
    v10 = (struct Err *)*((_DWORD *)this + 18);
    if ( v10 )
      Table::`scalar deleting destructor'(v10, *((_DWORD *)this + 18));
    *((_DWORD *)this + 18) = 0;
    if ( (*(_DWORD *)a4 & 1) != 0 || *((_DWORD *)a4 + 1) != -1206 )
    {
      if ( (*(_DWORD *)a4 & 8) != 0 )
        goto LABEL_18;
      goto LABEL_16;
    }
  }
LABEL_63:
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_64;
  return this;
}

```

## disassembly

```asm
0x1004e23f  push    14h
0x1004e241  mov     eax, offset loc_10124F50
0x1004e246  call    __EH_prolog3
0x1004e24b  mov     ebx, ecx
0x1004e24d  mov     [ebp+var_20], ebx
0x1004e250  mov     edi, [ebp+arg_8]
0x1004e253  push    edi; struct Err *
0x1004e254  push    32h ; '2'; unsigned int
0x1004e256  call    ??0Collection@@QAE@KAAVErr@@@Z; Collection::Collection(ulong,Err &)
0x1004e25b  mov     ecx, [ebp+arg_0]
0x1004e25e  xor     eax, eax
0x1004e260  mov     esi, [ebp+arg_4]
0x1004e263  or      edx, 0FFFFFFFFh
0x1004e266  mov     [ebp+var_4], eax
0x1004e269  mov     [ebx+0Ch], ecx
0x1004e26c  mov     [ebx+10h], esi
0x1004e26f  mov     [ebx+14h], eax
0x1004e272  mov     [ebx+18h], eax
0x1004e275  mov     [ebx+1Ch], edx
0x1004e278  mov     [ebx+20h], edx
0x1004e27b  mov     [ebx+24h], edx
0x1004e27e  mov     [ebx+28h], edx
0x1004e281  mov     [ebx+2Ch], edx
0x1004e284  mov     [ebx+30h], edx
0x1004e287  mov     [ebx+34h], edx
0x1004e28a  mov     [ebx+38h], edx
0x1004e28d  mov     dword ptr [ebx+40h], 1
0x1004e294  mov     [ebx+3Ch], eax
0x1004e297  mov     [ebx+44h], eax
0x1004e29a  mov     [ebx+48h], eax
0x1004e29d  test    byte ptr [edi], 8
0x1004e2a0  mov     [ebp+var_10], eax
0x1004e2a3  jnz     loc_1004E670
0x1004e2a9  push    edi; struct Err *
0x1004e2aa  add     ecx, 9Ch; this
0x1004e2b0  push    ebx; void *
0x1004e2b1  call    ?AddObject@Collection@@QAEXPBXAAVErr@@@Z; Collection::AddObject(void const *,Err &)
0x1004e2b6  test    byte ptr [edi], 8
0x1004e2b9  mov     ecx, [ebp+arg_0]; this
0x1004e2bc  jnz     loc_1004E670
0x1004e2c2  push    edi; struct Err *
0x1004e2c3  push    esi; struct Database *
0x1004e2c4  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x1004e2c9  mov     ecx, [ebx+10h]; this
0x1004e2cc  mov     [ebx+3Ch], eax
0x1004e2cf  cmp     dword ptr [ecx+48h], 1
0x1004e2d3  jz      loc_1004E65C
0x1004e2d9  test    byte ptr [edi], 8
0x1004e2dc  jnz     loc_1004E661
0x1004e2e2  cmp     dword ptr [esi+60h], 2
0x1004e2e6  jz      loc_1004E3AB
0x1004e2ec  push    dword ptr [ecx+194h]; unsigned int
0x1004e2f2  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x1004e2f7  mov     [ebx+48h], eax
0x1004e2fa  test    eax, eax
0x1004e2fc  jnz     loc_1004E393
0x1004e302  push    770h; Size
0x1004e307  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e30c  pop     ecx
0x1004e30d  mov     [ebp+Block], eax
0x1004e310  push    edi; struct Err *
0x1004e311  mov     byte ptr [ebp+var_4], 1
0x1004e315  mov     ecx, eax; this
0x1004e317  push    dword ptr [ebx+10h]; struct Database *
0x1004e31a  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x1004e31f  mov     byte ptr [ebp+var_4], 0
0x1004e323  mov     [ebx+48h], eax
0x1004e326  test    eax, eax
0x1004e328  jnz     short loc_1004E337
0x1004e32a  push    ecx
0x1004e32b  push    0FFFFFC0Dh
0x1004e330  mov     ecx, edi
0x1004e332  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004e337  mov     eax, [edi]
0x1004e339  test    al, 8
0x1004e33b  jnz     short loc_1004E3A0
0x1004e33d  mov     eax, [ebx+10h]
0x1004e340  mov     ecx, [ebx+48h]
0x1004e343  push    edi
0x1004e344  push    1
0x1004e346  push    dword ptr [eax+194h]
0x1004e34c  push    ebx
0x1004e34d  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x1004e352  mov     eax, [edi]
0x1004e354  test    al, 8
0x1004e356  jz      short loc_1004E383
0x1004e358  mov     ecx, [ebx+48h]; this
0x1004e35b  test    ecx, ecx
0x1004e35d  jz      short loc_1004E365
0x1004e35f  push    ecx; unsigned int
0x1004e360  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x1004e365  mov     dword ptr [ebx+48h], 0
0x1004e36c  mov     eax, [edi]
0x1004e36e  test    al, 1
0x1004e370  jnz     short loc_1004E37F
0x1004e372  cmp     dword ptr [edi+4], 0FFFFFB4Ah
0x1004e379  jz      loc_1004E65C
0x1004e37f  test    al, 8
0x1004e381  jnz     short loc_1004E3A0
0x1004e383  push    ecx; struct Err *
0x1004e384  mov     ecx, [ebx+48h]; this
0x1004e387  push    offset aMsysaces; "MSysACEs"
0x1004e38c  call    ?SetName@Table@@QAEXPAGAAVErr@@@Z; Table::SetName(ushort *,Err &)
0x1004e391  jmp     short loc_1004E3A0
0x1004e393  push    edi
0x1004e394  push    1
0x1004e396  push    dword ptr [ebx+0Ch]
0x1004e399  mov     ecx, eax
0x1004e39b  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x1004e3a0  test    byte ptr [edi], 8
0x1004e3a3  jnz     short loc_1004E3AB
0x1004e3a5  mov     eax, [ebx+48h]
0x1004e3a8  inc     dword ptr [eax+50h]
0x1004e3ab  mov     ecx, [ebx+10h]; this
0x1004e3ae  push    dword ptr [ecx+190h]; unsigned int
0x1004e3b4  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x1004e3b9  mov     esi, eax
0x1004e3bb  mov     [ebp+var_14], esi
0x1004e3be  test    esi, esi
0x1004e3c0  jnz     short loc_1004E43B
0x1004e3c2  push    770h; Size
0x1004e3c7  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e3cc  pop     ecx
0x1004e3cd  mov     [ebp+Block], eax
0x1004e3d0  push    edi; struct Err *
0x1004e3d1  mov     byte ptr [ebp+var_4], 2
0x1004e3d5  mov     ecx, eax; this
0x1004e3d7  push    dword ptr [ebx+10h]; struct Database *
0x1004e3da  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x1004e3df  mov     esi, eax
0x1004e3e1  mov     byte ptr [ebp+var_4], 0
0x1004e3e5  mov     [ebp+var_14], esi
0x1004e3e8  test    esi, esi
0x1004e3ea  jnz     short loc_1004E3FB
0x1004e3ec  push    ecx
0x1004e3ed  push    0FFFFFC0Dh
0x1004e3f2  mov     ecx, edi
0x1004e3f4  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004e3f9  jmp     short loc_1004E401
0x1004e3fb  xor     eax, eax
0x1004e3fd  inc     eax
0x1004e3fe  mov     [ebp+var_10], eax
0x1004e401  test    byte ptr [edi], 8
0x1004e404  jnz     short loc_1004E448
0x1004e406  mov     eax, [ebp+arg_4]
0x1004e409  mov     ecx, esi
0x1004e40b  push    edi
0x1004e40c  cmp     dword ptr [eax+60h], 2
0x1004e410  mov     eax, [ebx+10h]
0x1004e413  jnz     short loc_1004E419
0x1004e415  push    6
0x1004e417  jmp     short loc_1004E41B
0x1004e419  push    1
0x1004e41b  push    dword ptr [eax+190h]
0x1004e421  push    ebx
0x1004e422  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x1004e427  test    byte ptr [edi], 8
0x1004e42a  jnz     short loc_1004E448
0x1004e42c  push    ecx; struct Err *
0x1004e42d  push    offset aMsysobjects; "MSysObjects"
0x1004e432  mov     ecx, esi; this
0x1004e434  call    ?SetName@Table@@QAEXPAGAAVErr@@@Z; Table::SetName(ushort *,Err &)
0x1004e439  jmp     short loc_1004E448
0x1004e43b  push    edi
0x1004e43c  push    1
0x1004e43e  push    dword ptr [ebx+0Ch]
0x1004e441  mov     ecx, esi
0x1004e443  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x1004e448  test    byte ptr [edi], 8
0x1004e44b  mov     ecx, [ebp+var_10]
0x1004e44e  mov     [ebp+Block], ecx
0x1004e451  jnz     short loc_1004E4C9
0x1004e453  push    198h; Size
0x1004e458  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e45d  pop     ecx
0x1004e45e  mov     [ebp+var_18], eax
0x1004e461  push    0
0x1004e463  push    0
0x1004e465  push    edi
0x1004e466  push    1
0x1004e468  push    1
0x1004e46a  push    esi
0x1004e46b  push    ebx
0x1004e46c  mov     ecx, eax
0x1004e46e  mov     byte ptr [ebp+var_4], 3
0x1004e472  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@IW4CurLockMode@@@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint,CurLockMode)
0x1004e477  mov     byte ptr [ebp+var_4], 0
0x1004e47b  mov     [ebp+var_18], eax
0x1004e47e  mov     [ebx+14h], eax
0x1004e481  test    eax, eax
0x1004e483  jnz     short loc_1004E494
0x1004e485  push    ecx
0x1004e486  push    0FFFFFC0Dh
0x1004e48b  mov     ecx, edi
0x1004e48d  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004e492  jmp     short loc_1004E4C6
0x1004e494  test    byte ptr [edi], 8
0x1004e497  jz      short loc_1004E4BF
0x1004e499  mov     eax, [eax]
0x1004e49b  push    1; void *
0x1004e49d  mov     esi, [eax]
0x1004e49f  mov     ecx, esi
0x1004e4a1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004e4a7  mov     ecx, [ebp+var_18]
0x1004e4aa  call    esi
0x1004e4ac  xor     ecx, ecx
0x1004e4ae  mov     dword ptr [ebx+14h], 0
0x1004e4b5  cmp     [ebp+Block], 1
0x1004e4b9  cmovnz  ecx, [ebp+Block]
0x1004e4bd  jmp     short loc_1004E4C9
0x1004e4bf  mov     dword ptr [eax+44h], 0
0x1004e4c6  mov     ecx, [ebp+var_10]
0x1004e4c9  mov     eax, [edi]
0x1004e4cb  test    al, 8
0x1004e4cd  jz      short loc_1004E4E9
0x1004e4cf  cmp     ecx, 1
0x1004e4d2  jnz     short loc_1004E4E9
0x1004e4d4  mov     ecx, [ebp+var_14]; this
0x1004e4d7  cmp     dword ptr [ecx+30h], 0Ah
0x1004e4db  jz      short loc_1004E4E5
0x1004e4dd  push    ecx; unsigned int
0x1004e4de  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x1004e4e3  mov     eax, [edi]
0x1004e4e5  xor     esi, esi
0x1004e4e7  jmp     short loc_1004E4EC
0x1004e4e9  mov     esi, [ebp+var_14]
0x1004e4ec  test    al, 8
0x1004e4ee  jnz     loc_1004E65C
0x1004e4f4  push    offset aParentid_0; "ParentId"
0x1004e4f9  mov     ecx, esi; this
0x1004e4fb  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e500  mov     [ebx+1Ch], eax
0x1004e503  cmp     eax, 0FFFFFFFFh
0x1004e506  jnz     short loc_1004E521
0x1004e508  push    ecx
0x1004e509  push    0
0x1004e50b  push    offset aParentid_0; "ParentId"
0x1004e510  push    0FFFFE004h
0x1004e515  push    0FFFFFB4Ah
0x1004e51a  mov     ecx, edi
0x1004e51c  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e521  push    offset aId; "Id"
0x1004e526  mov     ecx, esi; this
0x1004e528  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e52d  mov     [ebx+20h], eax
0x1004e530  cmp     eax, 0FFFFFFFFh
0x1004e533  jnz     short loc_1004E54E
0x1004e535  push    ecx
0x1004e536  push    0
0x1004e538  push    offset aId; "Id"
0x1004e53d  push    0FFFFE004h
0x1004e542  push    0FFFFFB4Ah
0x1004e547  mov     ecx, edi
0x1004e549  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e54e  push    offset aName_0; "Name"
0x1004e553  mov     ecx, esi; this
0x1004e555  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e55a  mov     [ebx+24h], eax
0x1004e55d  cmp     eax, 0FFFFFFFFh
0x1004e560  jnz     short loc_1004E57B
0x1004e562  push    ecx
0x1004e563  push    0
0x1004e565  push    offset aName_0; "Name"
0x1004e56a  push    0FFFFE004h
0x1004e56f  push    0FFFFFB4Ah
0x1004e574  mov     ecx, edi
0x1004e576  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e57b  push    offset aType; "Type"
0x1004e580  mov     ecx, esi; this
0x1004e582  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e587  mov     [ebx+28h], eax
0x1004e58a  cmp     eax, 0FFFFFFFFh
0x1004e58d  jnz     short loc_1004E5A8
0x1004e58f  push    ecx
0x1004e590  push    0
0x1004e592  push    offset aType; "Type"
0x1004e597  push    0FFFFE004h
0x1004e59c  push    0FFFFFB4Ah
0x1004e5a1  mov     ecx, edi
0x1004e5a3  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e5a8  push    offset aDatecreate; "DateCreate"
0x1004e5ad  mov     ecx, esi; this
0x1004e5af  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e5b4  mov     [ebx+2Ch], eax
0x1004e5b7  cmp     eax, 0FFFFFFFFh
0x1004e5ba  jnz     short loc_1004E5D5
0x1004e5bc  push    ecx
0x1004e5bd  push    0
0x1004e5bf  push    offset aDatecreate; "DateCreate"
0x1004e5c4  push    0FFFFE004h
0x1004e5c9  push    0FFFFFB4Ah
0x1004e5ce  mov     ecx, edi
0x1004e5d0  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e5d5  push    offset aDateupdate; "DateUpdate"
0x1004e5da  mov     ecx, esi; this
0x1004e5dc  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e5e1  mov     [ebx+30h], eax
0x1004e5e4  cmp     eax, 0FFFFFFFFh
0x1004e5e7  jnz     short loc_1004E602
0x1004e5e9  push    ecx
  ... truncated ...
```
