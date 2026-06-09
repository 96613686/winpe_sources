# Instance::Instance(Session *,Database *,Err &)

- ea: `0x10035910`
- end: `0x10035dfd`
- name: `??0Instance@@QAE@PAVSession@@PAVDatabase@@AAVErr@@@Z`
- size: `1261`
- prototype: `Instance *__thiscall(Instance *__hidden this, struct Session *, struct Database *, struct Err *)`
- caller_count: `3`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10043f90`
- `0x10044340`
- `0x10044630`

## callees

- `0x1000eb60`
- `0x10012db0`
- `0x10012dd0`
- `0x10019240`
- `0x1001df90`
- `0x10020ab0`
- `0x10025ee0`
- `0x10025f50`
- `0x10035910`
- `0x100451d0`
- `0x100518a0`
- `0x10053400`
- `0x100536a0`
- `0x10053f40`
- `0x10056ff0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7f3`
- `0x1005f064`

## string_xrefs

- `0x10035cfe`: `DateCreate`
- `0x10035d15`: `DateCreate`
- `0x10035d2b`: `DateUpdate`
- `0x10035d42`: `DateUpdate`

## pseudocode

```c
Instance *__thiscall Instance::Instance(Instance *this, struct Session *a2, struct Database *a3, struct Err *a4)
{
  struct Session *v5; // esi
  unsigned int v6; // eax
  struct IAccMeth *AccessMethod; // eax
  Database *v8; // ecx
  struct Table *Table; // eax
  Table *v10; // eax
  int v11; // ecx
  Table *v12; // ecx
  struct Table *v13; // eax
  Table *v14; // esi
  int v15; // ecx
  int v16; // eax
  struct Err *v17; // ecx
  void *v18; // eax
  int v19; // eax
  int v20; // ecx
  int v21; // edx
  int v22; // eax
  Table *v23; // esi
  int ColumnFromName; // eax
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
  int v38; // eax
  int v39; // ecx
  int v40; // ecx
  unsigned int v41; // ecx
  int v42; // edx
  unsigned int v43; // eax
  unsigned int v44; // eax
  Table *Block; // [esp+14h] [ebp-18h]
  Table *Blocka; // [esp+14h] [ebp-18h]
  Table *v48; // [esp+18h] [ebp-14h]
  int v49; // [esp+1Ch] [ebp-10h]

  *((_DWORD *)this + 1) = 0;
  *((_DWORD *)this + 2) = 0;
  *(_DWORD *)this = operator new[](0xCCu);
  if ( (*(_BYTE *)a4 & 8) == 0 )
    *((_DWORD *)this + 1) = 50;
  v5 = a2;
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
  v49 = 0;
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    v6 = *((_DWORD *)a2 + 2);
    if ( v6 < *((_DWORD *)a2 + 1) || (Collection::Grow(a2, v6 + 1, a4), (*(_BYTE *)a4 & 8) == 0) )
      *(_DWORD *)(*(_DWORD *)a2 + 4 * (*((_DWORD *)a2 + 2))++) = this;
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
      AccessMethod = Session::GetAccessMethod(a2, a3, a4);
      v8 = (Database *)*((_DWORD *)this + 4);
      *((_DWORD *)this + 15) = AccessMethod;
      if ( *((_DWORD *)v8 + 17) == 1 )
        goto LABEL_66;
      if ( (*(_BYTE *)a4 & 8) != 0 )
      {
LABEL_67:
        v40 = *((_DWORD *)v5 + 2);
        if ( v40 )
        {
          *(_DWORD *)(*(_DWORD *)v5 + 4 * v40) = this;
          v41 = 0;
          v42 = *(_DWORD *)v5;
          if ( **(Instance ***)v5 != this )
          {
            do
              ++v41;
            while ( *(Instance **)(v42 + 4 * v41) != this );
          }
          v43 = *((_DWORD *)v5 + 2);
          if ( v41 < v43 )
          {
            v44 = v43 - 1;
            *((_DWORD *)v5 + 2) = v44;
            *(_DWORD *)(v42 + 4 * v41) = *(_DWORD *)(v42 + 4 * v44);
          }
        }
        return this;
      }
      if ( *((_DWORD *)a3 + 26) != 2 )
      {
        Table = Database::FindTable(v8, *((_DWORD *)v8 + 98));
        *((_DWORD *)this + 18) = Table;
        if ( Table )
        {
          Table::CompatibleMode(Table, *((_DWORD *)this + 3), 1, a4);
LABEL_21:
          if ( (*(_BYTE *)a4 & 8) == 0 )
            ++*(_DWORD *)(*((_DWORD *)this + 18) + 76);
          goto LABEL_23;
        }
        Block = (Table *)operator new(0x778u);
        v10 = Table::Table(Block, *((struct Database **)this + 4), a4);
        *((_DWORD *)this + 18) = v10;
        if ( !v10 )
          Err::SetError(a4, -1011, v11);
        if ( (*(_BYTE *)a4 & 8) == 0 )
        {
          Table::Open(*((_DWORD *)this + 18), this, *(_DWORD *)(*((_DWORD *)this + 4) + 392), 1, a4);
          if ( (*(_BYTE *)a4 & 8) == 0 )
            goto LABEL_19;
          v12 = (Table *)*((_DWORD *)this + 18);
          if ( v12 )
            Table::`scalar deleting destructor'(v12, *((_DWORD *)this + 18));
          *((_DWORD *)this + 18) = 0;
          if ( (*(_BYTE *)a4 & 8) == 0 )
          {
LABEL_19:
            Table::SetName(*((Table **)this + 18), L"MSysACEs", v12);
            goto LABEL_21;
          }
        }
      }
LABEL_23:
      v13 = Database::FindTable(*((Database **)this + 4), *(_DWORD *)(*((_DWORD *)this + 4) + 388));
      v14 = v13;
      v48 = v13;
      if ( v13 )
      {
        Table::CompatibleMode(v13, *((_DWORD *)this + 3), 1, a4);
      }
      else
      {
        Blocka = (Table *)operator new(0x778u);
        v14 = Table::Table(Blocka, *((struct Database **)this + 4), a4);
        v48 = v14;
        if ( v14 )
          v49 = 1;
        else
          Err::SetError(a4, -1011, v15);
        if ( (*(_BYTE *)a4 & 8) != 0 )
          goto LABEL_41;
        v16 = *((_DWORD *)this + 4);
        if ( *((_DWORD *)a3 + 26) == 2 )
          Table::Open(v14, this, *(_DWORD *)(v16 + 388), 6, a4);
        else
          Table::Open(v14, this, *(_DWORD *)(v16 + 388), 1, a4);
        if ( (*(_BYTE *)a4 & 8) != 0 )
          goto LABEL_41;
        Table::SetName(v14, L"MSysObjects", v17);
      }
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        v18 = operator new(0x16Cu);
        v19 = Cursor::Cursor(v18, this, v14, 1, 1, a4, 0);
        *((_DWORD *)this + 5) = v19;
        if ( v19 )
        {
          if ( (*(_BYTE *)a4 & 8) != 0 )
          {
            (**(void (__thiscall ***)(int, int))v19)(v19, 1);
            v21 = v49;
            *((_DWORD *)this + 5) = 0;
            if ( v49 == 1 )
              v21 = 0;
            goto LABEL_42;
          }
          *(_DWORD *)(v19 + 68) = 0;
        }
        else
        {
          Err::SetError(a4, -1011, v20);
        }
      }
LABEL_41:
      v21 = v49;
LABEL_42:
      v22 = *(_DWORD *)a4;
      if ( (*(_DWORD *)a4 & 8) != 0 && v21 == 1 )
      {
        if ( *((_DWORD *)v48 + 11) != 9 )
        {
          Table::`scalar deleting destructor'(v48, (unsigned int)v48);
          v22 = *(_DWORD *)a4;
        }
        v23 = 0;
      }
      else
      {
        v23 = v48;
      }
      if ( (v22 & 8) == 0 )
      {
        ColumnFromName = Table::FindColumnFromName(v23, L"ParentId");
        *((_DWORD *)this + 7) = ColumnFromName;
        if ( ColumnFromName == -1 )
          Err::SetError(a4, -1206, -8188, L"ParentId", 0, v25);
        v26 = Table::FindColumnFromName(v23, L"Id");
        *((_DWORD *)this + 8) = v26;
        if ( v26 == -1 )
          Err::SetError(a4, -1206, -8188, L"Id", 0, v27);
        v28 = Table::FindColumnFromName(v23, L"Name");
        *((_DWORD *)this + 9) = v28;
        if ( v28 == -1 )
          Err::SetError(a4, -1206, -8188, L"Name", 0, v29);
        v30 = Table::FindColumnFromName(v23, L"Type");
        *((_DWORD *)this + 10) = v30;
        if ( v30 == -1 )
          Err::SetError(a4, -1206, -8188, L"Type", 0, v31);
        v32 = Table::FindColumnFromName(v23, L"DateCreate");
        *((_DWORD *)this + 11) = v32;
        if ( v32 == -1 )
          Err::SetError(a4, -1206, -8188, L"DateCreate", 0, v33);
        v34 = Table::FindColumnFromName(v23, L"DateUpdate");
        *((_DWORD *)this + 12) = v34;
        if ( v34 == -1 )
          Err::SetError(a4, -1206, -8188, L"DateUpdate", 0, v35);
        v36 = Table::FindColumnFromName(v23, L"Owner");
        *((_DWORD *)this + 13) = v36;
        if ( v36 == -1 )
          Err::SetError(a4, -1206, -8188, L"Owner", 0, v37);
        v38 = Table::FindColumnFromName(v23, L"Flags");
        *((_DWORD *)this + 14) = v38;
        if ( v38 == -1 )
          Err::SetError(a4, -1206, -8188, L"Flags", 0, v39);
      }
      v5 = a2;
LABEL_66:
      if ( (*(_BYTE *)a4 & 8) == 0 )
        return this;
      goto LABEL_67;
    }
  }
  return this;
}

```

## disassembly

```asm
0x10035910  mov     edi, edi
0x10035912  push    ebp
0x10035913  mov     ebp, esp
0x10035915  push    0FFFFFFFFh
0x10035917  push    offset ??0Instance@@QAE@PAVSession@@PAVDatabase@@AAVErr@@@Z_SEH
0x1003591c  mov     eax, large fs:0
0x10035922  push    eax
0x10035923  sub     esp, 10h
0x10035926  push    ebx
0x10035927  push    esi
0x10035928  push    edi
0x10035929  mov     eax, ___security_cookie
0x1003592e  xor     eax, ebp
0x10035930  push    eax; unsigned int
0x10035931  lea     eax, [ebp+var_C]
0x10035934  mov     large fs:0, eax
0x1003593a  mov     edi, ecx
0x1003593c  mov     [ebp+var_1C], edi
0x1003593f  mov     ebx, [ebp+arg_8]
0x10035942  push    0CCh; unsigned int
0x10035947  mov     dword ptr [edi+4], 0
0x1003594e  mov     dword ptr [edi+8], 0
0x10035955  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1003595a  add     esp, 4
0x1003595d  mov     [edi], eax
0x1003595f  test    byte ptr [ebx], 8
0x10035962  jnz     short loc_1003596B
0x10035964  mov     dword ptr [edi+4], 32h ; '2'
0x1003596b  mov     esi, [ebp+arg_0]
0x1003596e  xor     ecx, ecx
0x10035970  mov     eax, [ebp+arg_4]
0x10035973  mov     [ebp+var_4], 0
0x1003597a  mov     [edi+0Ch], esi
0x1003597d  mov     [edi+10h], eax
0x10035980  mov     dword ptr [edi+14h], 0
0x10035987  mov     dword ptr [edi+18h], 0
0x1003598e  mov     dword ptr [edi+1Ch], 0FFFFFFFFh
0x10035995  mov     dword ptr [edi+20h], 0FFFFFFFFh
0x1003599c  mov     dword ptr [edi+24h], 0FFFFFFFFh
0x100359a3  mov     dword ptr [edi+28h], 0FFFFFFFFh
0x100359aa  mov     dword ptr [edi+2Ch], 0FFFFFFFFh
0x100359b1  mov     dword ptr [edi+30h], 0FFFFFFFFh
0x100359b8  mov     dword ptr [edi+34h], 0FFFFFFFFh
0x100359bf  mov     dword ptr [edi+38h], 0FFFFFFFFh
0x100359c6  mov     dword ptr [edi+40h], 1
0x100359cd  mov     dword ptr [edi+3Ch], 0
0x100359d4  mov     dword ptr [edi+44h], 0
0x100359db  mov     dword ptr [edi+48h], 0
0x100359e2  test    byte ptr [ebx], 8
0x100359e5  mov     [ebp+var_10], ecx
0x100359e8  jnz     loc_10035DE7
0x100359ee  mov     eax, [esi+8]
0x100359f1  cmp     eax, [esi+4]
0x100359f4  jb      short loc_10035A05
0x100359f6  push    ebx; struct Err *
0x100359f7  inc     eax
0x100359f8  mov     ecx, esi; this
0x100359fa  push    eax; unsigned int
0x100359fb  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10035a00  test    byte ptr [ebx], 8
0x10035a03  jnz     short loc_10035A10
0x10035a05  mov     ecx, [esi+8]
0x10035a08  mov     eax, [esi]
0x10035a0a  mov     [eax+ecx*4], edi
0x10035a0d  inc     dword ptr [esi+8]
0x10035a10  test    byte ptr [ebx], 8
0x10035a13  mov     eax, [ebp+arg_4]
0x10035a16  jnz     loc_10035DE7
0x10035a1c  push    ebx; struct Err *
0x10035a1d  push    eax; struct Database *
0x10035a1e  mov     ecx, esi; this
0x10035a20  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x10035a25  mov     ecx, [edi+10h]; this
0x10035a28  mov     [edi+3Ch], eax
0x10035a2b  cmp     dword ptr [ecx+44h], 1
0x10035a2f  jz      loc_10035DB5
0x10035a35  test    byte ptr [ebx], 8
0x10035a38  jnz     loc_10035DBA
0x10035a3e  mov     eax, [ebp+arg_4]
0x10035a41  cmp     dword ptr [eax+68h], 2
0x10035a45  jz      loc_10035AF4
0x10035a4b  push    dword ptr [ecx+188h]; unsigned int
0x10035a51  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x10035a56  mov     [edi+48h], eax
0x10035a59  test    eax, eax
0x10035a5b  jnz     short loc_10035ADC
0x10035a5d  push    778h; Size
0x10035a62  call    ??2@YAPAXI@Z; operator new(uint)
0x10035a67  add     esp, 4
0x10035a6a  mov     [ebp+Block], eax
0x10035a6d  push    ebx; struct Err *
0x10035a6e  mov     byte ptr [ebp+var_4], 1
0x10035a72  mov     ecx, eax; this
0x10035a74  push    dword ptr [edi+10h]; struct Database *
0x10035a77  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10035a7c  mov     byte ptr [ebp+var_4], 0
0x10035a80  mov     [edi+48h], eax
0x10035a83  test    eax, eax
0x10035a85  jnz     short loc_10035A94
0x10035a87  push    ecx
0x10035a88  push    0FFFFFC0Dh
0x10035a8d  mov     ecx, ebx
0x10035a8f  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10035a94  test    byte ptr [ebx], 8
0x10035a97  jnz     short loc_10035AF4
0x10035a99  mov     eax, [edi+10h]
0x10035a9c  mov     ecx, [edi+48h]
0x10035a9f  push    ebx
0x10035aa0  push    1
0x10035aa2  push    dword ptr [eax+188h]
0x10035aa8  push    edi
0x10035aa9  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x10035aae  test    byte ptr [ebx], 8
0x10035ab1  jz      short loc_10035ACC
0x10035ab3  mov     ecx, [edi+48h]; this
0x10035ab6  test    ecx, ecx
0x10035ab8  jz      short loc_10035AC0
0x10035aba  push    ecx; unsigned int
0x10035abb  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x10035ac0  mov     dword ptr [edi+48h], 0
0x10035ac7  test    byte ptr [ebx], 8
0x10035aca  jnz     short loc_10035AF4
0x10035acc  push    ecx; struct Err *
0x10035acd  mov     ecx, [edi+48h]; this
0x10035ad0  push    offset Src; "MSysACEs"
0x10035ad5  call    ?SetName@Table@@QAEXPBGAAVErr@@@Z; Table::SetName(ushort const *,Err &)
0x10035ada  jmp     short loc_10035AE9
0x10035adc  push    ebx
0x10035add  push    1
0x10035adf  push    dword ptr [edi+0Ch]
0x10035ae2  mov     ecx, eax
0x10035ae4  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x10035ae9  test    byte ptr [ebx], 8
0x10035aec  jnz     short loc_10035AF4
0x10035aee  mov     eax, [edi+48h]
0x10035af1  inc     dword ptr [eax+4Ch]
0x10035af4  mov     ecx, [edi+10h]; this
0x10035af7  push    dword ptr [ecx+184h]; unsigned int
0x10035afd  call    ?FindTable@Database@@QAEPAVTable@@K@Z; Database::FindTable(ulong)
0x10035b02  mov     esi, eax
0x10035b04  mov     [ebp+var_14], esi
0x10035b07  test    esi, esi
0x10035b09  jnz     loc_10035B94
0x10035b0f  push    778h; Size
0x10035b14  call    ??2@YAPAXI@Z; operator new(uint)
0x10035b19  add     esp, 4
0x10035b1c  mov     [ebp+Block], eax
0x10035b1f  push    ebx; struct Err *
0x10035b20  mov     byte ptr [ebp+var_4], 2
0x10035b24  mov     ecx, eax; this
0x10035b26  push    dword ptr [edi+10h]; struct Database *
0x10035b29  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10035b2e  mov     esi, eax
0x10035b30  mov     byte ptr [ebp+var_4], 0
0x10035b34  mov     [ebp+var_14], esi
0x10035b37  test    esi, esi
0x10035b39  jnz     short loc_10035B4A
0x10035b3b  push    ecx
0x10035b3c  push    0FFFFFC0Dh
0x10035b41  mov     ecx, ebx
0x10035b43  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10035b48  jmp     short loc_10035B52
0x10035b4a  mov     ecx, 1
0x10035b4f  mov     [ebp+var_10], ecx
0x10035b52  test    byte ptr [ebx], 8
0x10035b55  jnz     loc_10035C19
0x10035b5b  mov     eax, [ebp+arg_4]
0x10035b5e  mov     ecx, esi
0x10035b60  push    ebx
0x10035b61  cmp     dword ptr [eax+68h], 2
0x10035b65  mov     eax, [edi+10h]
0x10035b68  jnz     short loc_10035B6E
0x10035b6a  push    6
0x10035b6c  jmp     short loc_10035B70
0x10035b6e  push    1
0x10035b70  push    dword ptr [eax+184h]
0x10035b76  push    edi
0x10035b77  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x10035b7c  test    byte ptr [ebx], 8
0x10035b7f  jnz     loc_10035C19
0x10035b85  push    ecx; struct Err *
0x10035b86  push    offset aMsysobjects; "MSysObjects"
0x10035b8b  mov     ecx, esi; this
0x10035b8d  call    ?SetName@Table@@QAEXPBGAAVErr@@@Z; Table::SetName(ushort const *,Err &)
0x10035b92  jmp     short loc_10035BA1
0x10035b94  push    ebx
0x10035b95  push    1
0x10035b97  push    dword ptr [edi+0Ch]
0x10035b9a  mov     ecx, esi
0x10035b9c  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x10035ba1  test    byte ptr [ebx], 8
0x10035ba4  jnz     short loc_10035C19
0x10035ba6  push    16Ch; Size
0x10035bab  call    ??2@YAPAXI@Z; operator new(uint)
0x10035bb0  add     esp, 4
0x10035bb3  mov     [ebp+Block], eax
0x10035bb6  push    0
0x10035bb8  push    ebx
0x10035bb9  push    1
0x10035bbb  push    1
0x10035bbd  push    esi
0x10035bbe  push    edi
0x10035bbf  mov     ecx, eax
0x10035bc1  mov     byte ptr [ebp+var_4], 3
0x10035bc5  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x10035bca  mov     byte ptr [ebp+var_4], 0
0x10035bce  mov     [ebp+Block], eax
0x10035bd1  mov     [edi+14h], eax
0x10035bd4  test    eax, eax
0x10035bd6  jnz     short loc_10035BE7
0x10035bd8  push    ecx
0x10035bd9  push    0FFFFFC0Dh
0x10035bde  mov     ecx, ebx
0x10035be0  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10035be5  jmp     short loc_10035C19
0x10035be7  test    byte ptr [ebx], 8
0x10035bea  jz      short loc_10035C12
0x10035bec  mov     eax, [eax]
0x10035bee  push    1; void *
0x10035bf0  mov     esi, [eax]
0x10035bf2  mov     ecx, esi
0x10035bf4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10035bfa  mov     ecx, [ebp+Block]
0x10035bfd  call    esi
0x10035bff  mov     edx, [ebp+var_10]
0x10035c02  mov     dword ptr [edi+14h], 0
0x10035c09  cmp     edx, 1
0x10035c0c  jnz     short loc_10035C1C
0x10035c0e  xor     edx, edx
0x10035c10  jmp     short loc_10035C1C
0x10035c12  mov     dword ptr [eax+44h], 0
0x10035c19  mov     edx, [ebp+var_10]
0x10035c1c  mov     ecx, [ebx]
0x10035c1e  mov     eax, ecx
0x10035c20  test    cl, 8
0x10035c23  jz      short loc_10035C3F
0x10035c25  cmp     edx, 1
0x10035c28  jnz     short loc_10035C3F
0x10035c2a  mov     ecx, [ebp+var_14]; this
0x10035c2d  cmp     dword ptr [ecx+2Ch], 9
0x10035c31  jz      short loc_10035C3B
0x10035c33  push    ecx; unsigned int
0x10035c34  call    ??_GTable@@QAEPAXI@Z; Table::`scalar deleting destructor'(uint)
0x10035c39  mov     eax, [ebx]
0x10035c3b  xor     esi, esi
0x10035c3d  jmp     short loc_10035C42
0x10035c3f  mov     esi, [ebp+var_14]
0x10035c42  test    al, 8
0x10035c44  jnz     loc_10035DB2
0x10035c4a  push    offset aParentid_0; "ParentId"
0x10035c4f  mov     ecx, esi; this
0x10035c51  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10035c56  mov     [edi+1Ch], eax
0x10035c59  cmp     eax, 0FFFFFFFFh
0x10035c5c  jnz     short loc_10035C77
0x10035c5e  push    ecx
0x10035c5f  push    0
0x10035c61  push    offset aParentid_0; "ParentId"
0x10035c66  push    0FFFFE004h
0x10035c6b  push    0FFFFFB4Ah
0x10035c70  mov     ecx, ebx
0x10035c72  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10035c77  push    offset aId; "Id"
0x10035c7c  mov     ecx, esi; this
0x10035c7e  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10035c83  mov     [edi+20h], eax
0x10035c86  cmp     eax, 0FFFFFFFFh
0x10035c89  jnz     short loc_10035CA4
0x10035c8b  push    ecx
0x10035c8c  push    0
0x10035c8e  push    offset aId; "Id"
0x10035c93  push    0FFFFE004h
0x10035c98  push    0FFFFFB4Ah
0x10035c9d  mov     ecx, ebx
0x10035c9f  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10035ca4  push    offset aName_0; "Name"
0x10035ca9  mov     ecx, esi; this
0x10035cab  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10035cb0  mov     [edi+24h], eax
0x10035cb3  cmp     eax, 0FFFFFFFFh
0x10035cb6  jnz     short loc_10035CD1
0x10035cb8  push    ecx
0x10035cb9  push    0
0x10035cbb  push    offset aName_0; "Name"
0x10035cc0  push    0FFFFE004h
0x10035cc5  push    0FFFFFB4Ah
0x10035cca  mov     ecx, ebx
0x10035ccc  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10035cd1  push    offset aType; "Type"
0x10035cd6  mov     ecx, esi; this
0x10035cd8  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10035cdd  mov     [edi+28h], eax
0x10035ce0  cmp     eax, 0FFFFFFFFh
0x10035ce3  jnz     short loc_10035CFE
0x10035ce5  push    ecx
0x10035ce6  push    0
0x10035ce8  push    offset aType; "Type"
0x10035ced  push    0FFFFE004h
0x10035cf2  push    0FFFFFB4Ah
0x10035cf7  mov     ecx, ebx
  ... truncated ...
```
