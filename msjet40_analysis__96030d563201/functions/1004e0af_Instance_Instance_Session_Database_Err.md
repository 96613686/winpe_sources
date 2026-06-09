# Instance::Instance(Session *,Database *,Err &)

- ea: `0x1004e0af`
- end: `0x1004e4ea`
- name: `??0Instance@@QAE@PAVSession@@PAVDatabase@@AAVErr@@@Z`
- size: `1083`
- prototype: `Instance *__thiscall(Instance *__hidden this, struct Session *, struct Database *, struct Err *)`
- caller_count: `3`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1005dd31`
- `0x1005df3e`
- `0x1005e0f1`

## callees

- `0x1004e0af`
- `0x1004e4f0`
- `0x10050000`
- `0x100540dd`
- `0x100578a3`
- `0x10057af0`
- `0x10058da4`
- `0x10058fa1`
- `0x10059513`
- `0x1005c0a9`
- `0x1005ea7b`
- `0x10061713`
- `0x100617c8`
- `0x10061803`
- `0x1006bd9d`
- `0x10074bb1`
- `0x10074be5`
- `0x10122f60`
- `0x10123aaa`
- `0x10123ae2`
- `0x10123e98`
- `0x10123f5f`
- `0x10123f8e`

## string_xrefs

- `0x1004e418`: `DateCreate`
- `0x1004e42f`: `DateCreate`
- `0x1004e445`: `DateUpdate`
- `0x1004e45c`: `DateUpdate`

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
0x1004e0af  push    14h
0x1004e0b1  mov     eax, offset loc_10124DA0
0x1004e0b6  call    __EH_prolog3
0x1004e0bb  mov     ebx, ecx
0x1004e0bd  mov     [ebp+var_20], ebx
0x1004e0c0  mov     edi, [ebp+arg_8]
0x1004e0c3  push    edi; struct Err *
0x1004e0c4  push    32h ; '2'; unsigned int
0x1004e0c6  call    ??0Collection@@QAE@KAAVErr@@@Z; Collection::Collection(ulong,Err &)
0x1004e0cb  mov     ecx, [ebp+arg_0]
0x1004e0ce  xor     eax, eax
0x1004e0d0  mov     esi, [ebp+arg_4]
0x1004e0d3  or      edx, 0FFFFFFFFh
0x1004e0d6  mov     [ebp+var_4], eax
0x1004e0d9  mov     [ebx+0Ch], ecx
0x1004e0dc  mov     [ebx+10h], esi
0x1004e0df  mov     [ebx+14h], eax
0x1004e0e2  mov     [ebx+18h], eax
0x1004e0e5  mov     [ebx+1Ch], edx
0x1004e0e8  mov     [ebx+20h], edx
0x1004e0eb  mov     [ebx+24h], edx
0x1004e0ee  mov     [ebx+28h], edx
0x1004e0f1  mov     [ebx+2Ch], edx
0x1004e0f4  mov     [ebx+30h], edx
0x1004e0f7  mov     [ebx+34h], edx
0x1004e0fa  mov     [ebx+38h], edx
0x1004e0fd  mov     dword ptr [ebx+40h], 1
0x1004e104  mov     [ebx+3Ch], eax
0x1004e107  mov     [ebx+44h], eax
0x1004e10a  mov     [ebx+48h], eax
0x1004e10d  test    byte ptr [edi], 8
0x1004e110  mov     [ebp+var_10], eax
0x1004e113  jnz     loc_1004E4E0
0x1004e119  push    edi; struct Err *
0x1004e11a  add     ecx, 9Ch; this
0x1004e120  push    ebx; void *
0x1004e121  call    ?AddObject@Collection@@QAEXPBXAAVErr@@@Z; Collection::AddObject(void const *,Err &)
0x1004e126  test    byte ptr [edi], 8
0x1004e129  mov     ecx, [ebp+arg_0]; this
0x1004e12c  jnz     loc_1004E4E0
0x1004e132  push    edi; struct Err *
0x1004e133  push    esi; struct Database *
0x1004e134  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x1004e139  mov     ecx, [ebx+10h]; this
0x1004e13c  mov     [ebx+3Ch], eax
0x1004e13f  cmp     dword ptr [ecx+48h], 1
0x1004e143  jz      loc_1004E4CC
0x1004e149  test    byte ptr [edi], 8
0x1004e14c  jnz     loc_1004E4D1
0x1004e152  cmp     dword ptr [esi+60h], 2
0x1004e156  jz      loc_1004E21B
0x1004e15c  push    dword ptr [ecx+194h]; unsigned int
0x1004e162  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x1004e167  mov     [ebx+48h], eax
0x1004e16a  test    eax, eax
0x1004e16c  jnz     loc_1004E203
0x1004e172  push    770h; Size
0x1004e177  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e17c  pop     ecx
0x1004e17d  mov     [ebp+Block], eax
0x1004e180  push    edi; struct Err *
0x1004e181  mov     byte ptr [ebp+var_4], 1
0x1004e185  mov     ecx, eax; this
0x1004e187  push    dword ptr [ebx+10h]; struct Database *
0x1004e18a  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x1004e18f  mov     byte ptr [ebp+var_4], 0
0x1004e193  mov     [ebx+48h], eax
0x1004e196  test    eax, eax
0x1004e198  jnz     short loc_1004E1A7
0x1004e19a  push    ecx
0x1004e19b  push    0FFFFFC0Dh
0x1004e1a0  mov     ecx, edi
0x1004e1a2  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004e1a7  mov     eax, [edi]
0x1004e1a9  test    al, 8
0x1004e1ab  jnz     short loc_1004E210
0x1004e1ad  mov     eax, [ebx+10h]
0x1004e1b0  mov     ecx, [ebx+48h]
0x1004e1b3  push    edi
0x1004e1b4  push    1
0x1004e1b6  push    dword ptr [eax+194h]
0x1004e1bc  push    ebx
0x1004e1bd  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x1004e1c2  mov     eax, [edi]
0x1004e1c4  test    al, 8
0x1004e1c6  jz      short loc_1004E1F3
0x1004e1c8  mov     ecx, [ebx+48h]; this
0x1004e1cb  test    ecx, ecx
0x1004e1cd  jz      short loc_1004E1D5
0x1004e1cf  push    ecx; unsigned int
0x1004e1d0  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x1004e1d5  mov     dword ptr [ebx+48h], 0
0x1004e1dc  mov     eax, [edi]
0x1004e1de  test    al, 1
0x1004e1e0  jnz     short loc_1004E1EF
0x1004e1e2  cmp     dword ptr [edi+4], 0FFFFFB4Ah
0x1004e1e9  jz      loc_1004E4CC
0x1004e1ef  test    al, 8
0x1004e1f1  jnz     short loc_1004E210
0x1004e1f3  push    ecx; struct Err *
0x1004e1f4  mov     ecx, [ebx+48h]; this
0x1004e1f7  push    offset aMsysaces; "MSysACEs"
0x1004e1fc  call    ?SetName@Table@@QAEXPAGAAVErr@@@Z; Table::SetName(ushort *,Err &)
0x1004e201  jmp     short loc_1004E210
0x1004e203  push    edi
0x1004e204  push    1
0x1004e206  push    dword ptr [ebx+0Ch]
0x1004e209  mov     ecx, eax
0x1004e20b  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x1004e210  test    byte ptr [edi], 8
0x1004e213  jnz     short loc_1004E21B
0x1004e215  mov     eax, [ebx+48h]
0x1004e218  inc     dword ptr [eax+50h]
0x1004e21b  mov     ecx, [ebx+10h]; this
0x1004e21e  push    dword ptr [ecx+190h]; unsigned int
0x1004e224  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x1004e229  mov     esi, eax
0x1004e22b  mov     [ebp+var_14], esi
0x1004e22e  test    esi, esi
0x1004e230  jnz     short loc_1004E2AB
0x1004e232  push    770h; Size
0x1004e237  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e23c  pop     ecx
0x1004e23d  mov     [ebp+Block], eax
0x1004e240  push    edi; struct Err *
0x1004e241  mov     byte ptr [ebp+var_4], 2
0x1004e245  mov     ecx, eax; this
0x1004e247  push    dword ptr [ebx+10h]; struct Database *
0x1004e24a  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x1004e24f  mov     esi, eax
0x1004e251  mov     byte ptr [ebp+var_4], 0
0x1004e255  mov     [ebp+var_14], esi
0x1004e258  test    esi, esi
0x1004e25a  jnz     short loc_1004E26B
0x1004e25c  push    ecx
0x1004e25d  push    0FFFFFC0Dh
0x1004e262  mov     ecx, edi
0x1004e264  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004e269  jmp     short loc_1004E271
0x1004e26b  xor     eax, eax
0x1004e26d  inc     eax
0x1004e26e  mov     [ebp+var_10], eax
0x1004e271  test    byte ptr [edi], 8
0x1004e274  jnz     short loc_1004E2B8
0x1004e276  mov     eax, [ebp+arg_4]
0x1004e279  mov     ecx, esi
0x1004e27b  push    edi
0x1004e27c  cmp     dword ptr [eax+60h], 2
0x1004e280  mov     eax, [ebx+10h]
0x1004e283  jnz     short loc_1004E289
0x1004e285  push    6
0x1004e287  jmp     short loc_1004E28B
0x1004e289  push    1
0x1004e28b  push    dword ptr [eax+190h]
0x1004e291  push    ebx
0x1004e292  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x1004e297  test    byte ptr [edi], 8
0x1004e29a  jnz     short loc_1004E2B8
0x1004e29c  push    ecx; struct Err *
0x1004e29d  push    offset aMsysobjects; "MSysObjects"
0x1004e2a2  mov     ecx, esi; this
0x1004e2a4  call    ?SetName@Table@@QAEXPAGAAVErr@@@Z; Table::SetName(ushort *,Err &)
0x1004e2a9  jmp     short loc_1004E2B8
0x1004e2ab  push    edi
0x1004e2ac  push    1
0x1004e2ae  push    dword ptr [ebx+0Ch]
0x1004e2b1  mov     ecx, esi
0x1004e2b3  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x1004e2b8  test    byte ptr [edi], 8
0x1004e2bb  mov     ecx, [ebp+var_10]
0x1004e2be  mov     [ebp+Block], ecx
0x1004e2c1  jnz     short loc_1004E339
0x1004e2c3  push    198h; Size
0x1004e2c8  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e2cd  pop     ecx
0x1004e2ce  mov     [ebp+var_18], eax
0x1004e2d1  push    0
0x1004e2d3  push    0
0x1004e2d5  push    edi
0x1004e2d6  push    1
0x1004e2d8  push    1
0x1004e2da  push    esi
0x1004e2db  push    ebx
0x1004e2dc  mov     ecx, eax
0x1004e2de  mov     byte ptr [ebp+var_4], 3
0x1004e2e2  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@IW4CurLockMode@@@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint,CurLockMode)
0x1004e2e7  mov     byte ptr [ebp+var_4], 0
0x1004e2eb  mov     [ebp+var_18], eax
0x1004e2ee  mov     [ebx+14h], eax
0x1004e2f1  test    eax, eax
0x1004e2f3  jnz     short loc_1004E304
0x1004e2f5  push    ecx
0x1004e2f6  push    0FFFFFC0Dh
0x1004e2fb  mov     ecx, edi
0x1004e2fd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004e302  jmp     short loc_1004E336
0x1004e304  test    byte ptr [edi], 8
0x1004e307  jz      short loc_1004E32F
0x1004e309  mov     eax, [eax]
0x1004e30b  push    1; void *
0x1004e30d  mov     esi, [eax]
0x1004e30f  mov     ecx, esi
0x1004e311  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004e317  mov     ecx, [ebp+var_18]
0x1004e31a  call    esi
0x1004e31c  xor     ecx, ecx
0x1004e31e  mov     dword ptr [ebx+14h], 0
0x1004e325  cmp     [ebp+Block], 1
0x1004e329  cmovnz  ecx, [ebp+Block]
0x1004e32d  jmp     short loc_1004E339
0x1004e32f  mov     dword ptr [eax+44h], 0
0x1004e336  mov     ecx, [ebp+var_10]
0x1004e339  mov     eax, [edi]
0x1004e33b  test    al, 8
0x1004e33d  jz      short loc_1004E359
0x1004e33f  cmp     ecx, 1
0x1004e342  jnz     short loc_1004E359
0x1004e344  mov     ecx, [ebp+var_14]; this
0x1004e347  cmp     dword ptr [ecx+30h], 0Ah
0x1004e34b  jz      short loc_1004E355
0x1004e34d  push    ecx; unsigned int
0x1004e34e  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x1004e353  mov     eax, [edi]
0x1004e355  xor     esi, esi
0x1004e357  jmp     short loc_1004E35C
0x1004e359  mov     esi, [ebp+var_14]
0x1004e35c  test    al, 8
0x1004e35e  jnz     loc_1004E4CC
0x1004e364  push    offset aParentid_0; "ParentId"
0x1004e369  mov     ecx, esi; this
0x1004e36b  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e370  mov     [ebx+1Ch], eax
0x1004e373  cmp     eax, 0FFFFFFFFh
0x1004e376  jnz     short loc_1004E391
0x1004e378  push    ecx
0x1004e379  push    0
0x1004e37b  push    offset aParentid_0; "ParentId"
0x1004e380  push    0FFFFE004h
0x1004e385  push    0FFFFFB4Ah
0x1004e38a  mov     ecx, edi
0x1004e38c  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e391  push    offset aId; "Id"
0x1004e396  mov     ecx, esi; this
0x1004e398  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e39d  mov     [ebx+20h], eax
0x1004e3a0  cmp     eax, 0FFFFFFFFh
0x1004e3a3  jnz     short loc_1004E3BE
0x1004e3a5  push    ecx
0x1004e3a6  push    0
0x1004e3a8  push    offset aId; "Id"
0x1004e3ad  push    0FFFFE004h
0x1004e3b2  push    0FFFFFB4Ah
0x1004e3b7  mov     ecx, edi
0x1004e3b9  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e3be  push    offset aName_0; "Name"
0x1004e3c3  mov     ecx, esi; this
0x1004e3c5  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e3ca  mov     [ebx+24h], eax
0x1004e3cd  cmp     eax, 0FFFFFFFFh
0x1004e3d0  jnz     short loc_1004E3EB
0x1004e3d2  push    ecx
0x1004e3d3  push    0
0x1004e3d5  push    offset aName_0; "Name"
0x1004e3da  push    0FFFFE004h
0x1004e3df  push    0FFFFFB4Ah
0x1004e3e4  mov     ecx, edi
0x1004e3e6  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e3eb  push    offset aType; "Type"
0x1004e3f0  mov     ecx, esi; this
0x1004e3f2  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e3f7  mov     [ebx+28h], eax
0x1004e3fa  cmp     eax, 0FFFFFFFFh
0x1004e3fd  jnz     short loc_1004E418
0x1004e3ff  push    ecx
0x1004e400  push    0
0x1004e402  push    offset aType; "Type"
0x1004e407  push    0FFFFE004h
0x1004e40c  push    0FFFFFB4Ah
0x1004e411  mov     ecx, edi
0x1004e413  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e418  push    offset aDatecreate; "DateCreate"
0x1004e41d  mov     ecx, esi; this
0x1004e41f  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e424  mov     [ebx+2Ch], eax
0x1004e427  cmp     eax, 0FFFFFFFFh
0x1004e42a  jnz     short loc_1004E445
0x1004e42c  push    ecx
0x1004e42d  push    0
0x1004e42f  push    offset aDatecreate; "DateCreate"
0x1004e434  push    0FFFFE004h
0x1004e439  push    0FFFFFB4Ah
0x1004e43e  mov     ecx, edi
0x1004e440  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x1004e445  push    offset aDateupdate; "DateUpdate"
0x1004e44a  mov     ecx, esi; this
0x1004e44c  call    ?FindColumnFromName@Table@@QAEHPAG@Z; Table::FindColumnFromName(ushort *)
0x1004e451  mov     [ebx+30h], eax
0x1004e454  cmp     eax, 0FFFFFFFFh
0x1004e457  jnz     short loc_1004E472
0x1004e459  push    ecx
  ... truncated ...
```
