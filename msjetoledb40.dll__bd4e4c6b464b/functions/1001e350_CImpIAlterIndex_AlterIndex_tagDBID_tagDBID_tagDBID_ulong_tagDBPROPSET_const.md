# CImpIAlterIndex::AlterIndex(tagDBID *,tagDBID *,tagDBID *,ulong,tagDBPROPSET * const)

- ea: `0x1001e350`
- end: `0x1001e7f3`
- name: `?AlterIndex@CImpIAlterIndex@@UAGJPAUtagDBID@@00KQAUtagDBPROPSET@@@Z`
- size: `1187`
- prototype: `int(CImpIAlterIndex *__hidden this, struct tagDBID *, struct tagDBID *, struct tagDBID *, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001e350`
- `0x10020410`
- `0x100207d0`
- `0x10020c40`
- `0x100225b0`
- `0x10022660`
- `0x10022740`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1001e6c2`
- `msvcrt!_wcsicmp` at `0x1001e6c2`
- `KERNEL32!LeaveCriticalSection` at `0x1001e474`
- `KERNEL32!LeaveCriticalSection` at `0x1001e474`
- `KERNEL32!EnterCriticalSection` at `0x1001e3d4`
- `KERNEL32!EnterCriticalSection` at `0x1001e3d4`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e454`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e469`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e454`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e469`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001e7d3`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001e7d3`
- `msjet40!__imp__JetGetTableIndexInfo@24` at `0x1001e589`
- `msjet40!__imp__JetGetTableIndexInfo@24` at `0x1001e589`
- `msjet40!__imp__JetOpenTable@28` at `0x1001e4ee`
- `msjet40!__imp__JetOpenTable@28` at `0x1001e4ee`
- `msjet40!__imp__JetRenameIndex@16` at `0x1001e6e7`
- `msjet40!__imp__JetRenameIndex@16` at `0x1001e6e7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001e5e7`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001e5e7`

## pseudocode

```c
int __stdcall CImpIAlterIndex::AlterIndex(
        CImpIAlterIndex *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        struct tagDBID *a4,
        unsigned int a5,
        struct tagDBPROPSET *const a6)
{
  int Only; // edi
  struct _RTL_CRITICAL_SECTION *v7; // esi
  LPOLESTR pwszName; // ebx
  CImpIAlterIndex *v9; // ebx
  int v11; // ecx
  int v12; // eax
  JET_ERR v13; // ebx
  CImpIAlterIndex *v14; // edi
  int TableIndexInfo; // eax
  unsigned int v16; // ebx
  unsigned int i; // esi
  _DWORD *v18; // edx
  const GUID *v19; // ecx
  bool v20; // cf
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  unsigned int v26; // [esp-8h] [ebp-A8h]
  const struct _GUID *v27; // [esp+0h] [ebp-A0h]
  const struct _GUID *v28; // [esp+4h] [ebp-9Ch]
  unsigned int pcbActual[2]; // [esp+10h] [ebp-90h] BYREF
  struct tagDBPROPSET *v30; // [esp+18h] [ebp-88h]
  unsigned int pvData; // [esp+1Ch] [ebp-84h] BYREF
  _DWORD v32[4]; // [esp+20h] [ebp-80h] BYREF
  JET_ERR v33; // [esp+30h] [ebp-70h] BYREF
  int v34; // [esp+34h] [ebp-6Ch]
  int v35; // [esp+38h] [ebp-68h]
  struct tagDBID *v36; // [esp+3Ch] [ebp-64h]
  struct _RTL_CRITICAL_SECTION *v37; // [esp+40h] [ebp-60h]
  JET_TABLEID tableid; // [esp+44h] [ebp-5Ch] BYREF
  struct tagDBID *v39; // [esp+48h] [ebp-58h]
  unsigned int v40; // [esp+4Ch] [ebp-54h]
  CImpIAlterIndex *v41; // [esp+50h] [ebp-50h]
  _BYTE v42[4]; // [esp+54h] [ebp-4Ch] BYREF
  JET_TABLEID v43; // [esp+58h] [ebp-48h]
  JET_COLUMNID columnid; // [esp+64h] [ebp-3Ch]
  int v45; // [esp+9Ch] [ebp-4h]

  Only = 0;
  v39 = a3;
  v36 = a4;
  v41 = this;
  v40 = (unsigned int)a6;
  tableid = -1;
  v35 = 0;
  v34 = 0;
  memset(&v32[1], 0, 12);
  v32[0] = &CIndexProperties::`vftable';
  v45 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  v43 = -1;
  v37 = v7;
  pcbActual[1] = (unsigned int)v7;
  EnterCriticalSection(v7);
  LOBYTE(v45) = 1;
  if ( !a2 || !v39 )
    goto LABEL_86;
  if ( a2->eKind != 2 || (pwszName = a2->uName.pwszName) == 0 )
  {
    Only = -2147217860;
    goto LABEL_87;
  }
  if ( v39->eKind != 2 || !v39->uName.ulPropid )
  {
    Only = -2147217867;
    goto LABEL_87;
  }
  if ( !v36 || v36->eKind == 2 && v36->uName.ulPropid )
  {
    if ( !a5 )
    {
      if ( !v36 )
      {
        Only = 0;
        goto LABEL_14;
      }
LABEL_23:
      v11 = 0;
      if ( a5 )
      {
        do
        {
          v7 = v37;
          if ( *(_DWORD *)(v40 + 24 * v11 + 4) )
          {
            v7 = v37;
            if ( !*(_DWORD *)(v40 + 24 * v11) )
              goto LABEL_86;
          }
        }
        while ( ++v11 < a5 );
      }
      v12 = JetOpenTable(
              *(_DWORD *)(*((_DWORD *)v41 + 2) + 16),
              *(_DWORD *)(*((_DWORD *)v41 + 2) + 20),
              pwszName,
              0,
              0,
              3,
              &tableid);
      v13 = v12;
      if ( v12 <= -1304 )
      {
        if ( v12 != -1304 )
        {
          if ( v12 != -1809 )
          {
            if ( v12 == -1305 )
            {
              Only = -2147217865;
LABEL_80:
              v26 = v13;
              v9 = v41;
              CExtError::SendJetErrortoOLEAuto(
                Only,
                *(char **)(*((_DWORD *)v41 + 2) + 16),
                v26,
                (int)&IID_IAlterTable,
                (int)v27,
                v28);
              goto LABEL_15;
            }
            goto LABEL_34;
          }
LABEL_42:
          Only = -2147217911;
          goto LABEL_80;
        }
        goto LABEL_78;
      }
      if ( v12 == -1302 )
      {
LABEL_78:
        Only = -2147217856;
        goto LABEL_79;
      }
      if ( v12 )
      {
LABEL_34:
        Only = -2147467259;
        goto LABEL_79;
      }
      if ( a5 )
      {
        Only = CIndexProperties::FInit((CIndexProperties *)v32);
        if ( Only < 0 )
          goto LABEL_81;
        Only = CIndexProperties::CopyPropertiesFromStaticTable(
                 (CIndexProperties *)v32,
                 (const struct DBInfoProps *)&rgDBInfoProps);
        if ( Only < 0 )
          goto LABEL_81;
        v14 = v41;
        TableIndexInfo = JetGetTableIndexInfo(
                           *(_DWORD *)(*((_DWORD *)v41 + 2) + 16),
                           tableid,
                           v39->uName.ulPropid,
                           v42,
                           60,
                           0);
        v13 = TableIndexInfo;
        if ( TableIndexInfo <= -1404 )
        {
          if ( TableIndexInfo != -1404 )
          {
            if ( TableIndexInfo == -1907 || TableIndexInfo == -1809 )
              goto LABEL_42;
            goto LABEL_34;
          }
LABEL_67:
          Only = -2147217867;
          goto LABEL_80;
        }
        if ( TableIndexInfo )
        {
          Only = -2147467259;
          goto LABEL_79;
        }
        v13 = JetRetrieveColumn(*(_DWORD *)(*((_DWORD *)v14 + 2) + 16), v43, columnid, &pvData, 4u, pcbActual, 0, 0);
        v33 = v13;
        if ( v13 < 0 )
        {
          Only = -2147467259;
          goto LABEL_80;
        }
        Only = CIndexProperties::MapGrbitToJoltProperties((CIndexProperties *)v32, pvData);
        if ( Only < 0 )
          goto LABEL_79;
        Only = CSettableProperties::SetPropertiesReadOnly((CSettableProperties *)v32);
        if ( Only < 0 )
          goto LABEL_79;
        v16 = v40;
        for ( i = 0; i < a5; ++i )
        {
          v40 = 12;
          v18 = (_DWORD *)(24 * i + v16 + 8);
          v30 = (struct tagDBPROPSET *)(24 * i + v16);
          v19 = &DBPROPSET_INDEX;
          while ( v19->Data1 == *v18 )
          {
            v19 = (const GUID *)((char *)v19 + 4);
            ++v18;
            v20 = v40 < 4;
            v40 -= 4;
            if ( v20 )
            {
              Only = CSettableProperties::SetProperties((CSettableProperties *)v32, 1u, v30, 0);
              break;
            }
          }
          if ( Only < 0 || Only == 265946 )
            v35 = 1;
          else
            v34 = 1;
        }
        v7 = v37;
        v13 = v33;
      }
      if ( v36 && __wcsicmp(v39->uName.pwszName, v36->uName.pwszName) )
      {
        v21 = JetRenameIndex(*(_DWORD *)(*((_DWORD *)v41 + 2) + 16), tableid, v39->uName.ulPropid, v36->uName.ulPropid);
        v13 = v21;
        if ( v21 <= -1403 )
        {
          if ( v21 == -1403 )
          {
            Only = -2147217868;
            goto LABEL_80;
          }
          if ( v21 == -1907 || v21 == -1809 )
            goto LABEL_42;
          if ( v21 != -1404 )
            goto LABEL_34;
          goto LABEL_67;
        }
        if ( v21 == -1002 )
        {
          Only = -2147217806;
          goto LABEL_80;
        }
        if ( v21 )
        {
          Only = -2147467259;
          goto LABEL_79;
        }
      }
      if ( Only >= 0 && v35 == 1 )
      {
        Only = -2147217887;
        if ( v34 == 1 )
          Only = 265946;
      }
LABEL_79:
      if ( v13 )
        goto LABEL_80;
LABEL_81:
      if ( Only < 0 )
      {
        v9 = v41;
        v22 = *((_DWORD *)v41 + 2);
        v23 = *(_DWORD *)(v22 + 20);
        v24 = *(_DWORD *)(v22 + 16);
        if ( Only == -2147024882 )
          goto LABEL_15;
        goto LABEL_88;
      }
LABEL_14:
      v9 = v41;
      goto LABEL_15;
    }
    if ( v40 )
      goto LABEL_23;
LABEL_86:
    Only = -2147024809;
    goto LABEL_87;
  }
  Only = -2147217806;
LABEL_87:
  v9 = v41;
  v25 = *((_DWORD *)v41 + 2);
  v23 = *(_DWORD *)(v25 + 20);
  v24 = *(_DWORD *)(v25 + 16);
LABEL_88:
  if ( !JetGetDatabaseInfo(v24, v23, &v33, 4, 3) )
    CExtError::SendHRtoOLEAuto((int)&IID_IAlterTable, 0, v27, (int)v28);
LABEL_15:
  if ( tableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v9 + 2) + 16), tableid);
  if ( v43 != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v9 + 2) + 16), v43);
  if ( v7 )
    LeaveCriticalSection(v7);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v32);
  return Only;
}

```

## disassembly

```asm
0x1001e350  mov     edi, edi
0x1001e352  push    ebp
0x1001e353  mov     ebp, esp
0x1001e355  push    0FFFFFFFFh
0x1001e357  push    offset ?AlterIndex@CImpIAlterIndex@@UAGJPAUtagDBID@@00KQAUtagDBPROPSET@@@Z_SEH
0x1001e35c  mov     eax, large fs:0
0x1001e362  push    eax
0x1001e363  sub     esp, 84h
0x1001e369  mov     eax, ___security_cookie
0x1001e36e  xor     eax, ebp
0x1001e370  mov     [ebp+var_10], eax
0x1001e373  push    ebx
0x1001e374  push    esi
0x1001e375  push    edi; int
0x1001e376  push    eax; struct _GUID *
0x1001e377  lea     eax, [ebp+var_C]
0x1001e37a  mov     large fs:0, eax
0x1001e380  mov     ecx, [ebp+arg_8]
0x1001e383  xor     edi, edi
0x1001e385  mov     eax, [ebp+this]
0x1001e388  mov     ebx, [ebp+arg_4]
0x1001e38b  mov     [ebp+var_58], ecx
0x1001e38e  mov     ecx, [ebp+arg_C]
0x1001e391  mov     [ebp+var_64], ecx
0x1001e394  mov     ecx, [ebp+arg_14]
0x1001e397  mov     [ebp+var_50], eax
0x1001e39a  mov     [ebp+var_54], ecx
0x1001e39d  mov     [ebp+tableid], 0FFFFFFFFh
0x1001e3a4  mov     [ebp+var_68], edi
0x1001e3a7  mov     [ebp+var_6C], edi
0x1001e3aa  mov     [ebp+var_7C], edi
0x1001e3ad  mov     [ebp+var_78], edi
0x1001e3b0  mov     [ebp+var_74], edi
0x1001e3b3  mov     [ebp+var_80], offset ??_7CIndexProperties@@6B@; const CIndexProperties::`vftable'
0x1001e3ba  mov     [ebp+var_4], edi
0x1001e3bd  mov     esi, [eax+8]
0x1001e3c0  add     esi, 68h ; 'h'
0x1001e3c3  mov     [ebp+var_48], 0FFFFFFFFh
0x1001e3ca  push    esi; lpCriticalSection
0x1001e3cb  mov     [ebp+var_60], esi
0x1001e3ce  mov     [ebp+var_8C], esi
0x1001e3d4  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001e3da  mov     byte ptr [ebp+var_4], 1
0x1001e3de  test    ebx, ebx
0x1001e3e0  jz      loc_1001E7B8
0x1001e3e6  mov     eax, [ebp+var_58]
0x1001e3e9  test    eax, eax
0x1001e3eb  jz      loc_1001E7B8
0x1001e3f1  cmp     dword ptr [ebx+10h], 2
0x1001e3f5  jnz     loc_1001E7B1
0x1001e3fb  mov     ebx, [ebx+14h]
0x1001e3fe  test    ebx, ebx
0x1001e400  jz      loc_1001E7B1
0x1001e406  cmp     dword ptr [eax+10h], 2
0x1001e40a  jnz     loc_1001E7AA
0x1001e410  cmp     [eax+14h], edi
0x1001e413  jz      loc_1001E7AA
0x1001e419  mov     eax, [ebp+var_64]
0x1001e41c  test    eax, eax
0x1001e41e  jz      short loc_1001E435
0x1001e420  cmp     dword ptr [eax+10h], 2
0x1001e424  jnz     short loc_1001E42B
0x1001e426  cmp     [eax+14h], edi
0x1001e429  jnz     short loc_1001E435
0x1001e42b  mov     edi, 80040E72h
0x1001e430  jmp     loc_1001E7BD
0x1001e435  mov     edx, [ebp+arg_10]
0x1001e438  test    edx, edx
0x1001e43a  jnz     short loc_1001E4A2
0x1001e43c  test    eax, eax
0x1001e43e  jnz     short loc_1001E4AC
0x1001e440  xor     edi, edi
0x1001e442  mov     ebx, [ebp+var_50]
0x1001e445  mov     eax, [ebp+tableid]
0x1001e448  cmp     eax, 0FFFFFFFFh
0x1001e44b  jz      short loc_1001E45A
0x1001e44d  push    eax; tableid
0x1001e44e  mov     eax, [ebx+8]
0x1001e451  push    dword ptr [eax+10h]; sesid
0x1001e454  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1001e45a  mov     eax, [ebp+var_48]
0x1001e45d  cmp     eax, 0FFFFFFFFh
0x1001e460  jz      short loc_1001E46F
0x1001e462  push    eax; tableid
0x1001e463  mov     eax, [ebx+8]
0x1001e466  push    dword ptr [eax+10h]; sesid
0x1001e469  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1001e46f  test    esi, esi
0x1001e471  jz      short loc_1001E47A
0x1001e473  push    esi; lpCriticalSection
0x1001e474  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001e47a  lea     ecx, [ebp+var_80]; this
0x1001e47d  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x1001e482  mov     eax, edi
0x1001e484  mov     ecx, [ebp+var_C]
0x1001e487  mov     large fs:0, ecx
0x1001e48e  pop     ecx
0x1001e48f  pop     edi
0x1001e490  pop     esi
0x1001e491  pop     ebx
0x1001e492  mov     ecx, [ebp+var_10]
0x1001e495  xor     ecx, ebp; StackCookie
0x1001e497  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001e49c  mov     esp, ebp
0x1001e49e  pop     ebp
0x1001e49f  retn    18h
0x1001e4a2  cmp     [ebp+var_54], 0
0x1001e4a6  jz      loc_1001E7B8
0x1001e4ac  xor     ecx, ecx
0x1001e4ae  test    edx, edx
0x1001e4b0  jz      short loc_1001E4D7
0x1001e4b2  mov     esi, [ebp+var_54]
0x1001e4b5  lea     eax, [ecx+ecx*2]
0x1001e4b8  cmp     dword ptr [esi+eax*8+4], 0
0x1001e4bd  mov     esi, [ebp+var_60]
0x1001e4c0  jz      short loc_1001E4D2
0x1001e4c2  mov     esi, [ebp+var_54]
0x1001e4c5  cmp     dword ptr [esi+eax*8], 0
0x1001e4c9  mov     esi, [ebp+var_60]
0x1001e4cc  jz      loc_1001E7B8
0x1001e4d2  inc     ecx
0x1001e4d3  cmp     ecx, edx
0x1001e4d5  jb      short loc_1001E4B2
0x1001e4d7  mov     eax, [ebp+var_50]
0x1001e4da  lea     ecx, [ebp+tableid]
0x1001e4dd  push    ecx
0x1001e4de  push    3
0x1001e4e0  push    0
0x1001e4e2  mov     eax, [eax+8]
0x1001e4e5  push    0
0x1001e4e7  push    ebx
0x1001e4e8  push    dword ptr [eax+14h]
0x1001e4eb  push    dword ptr [eax+10h]
0x1001e4ee  call    ds:__imp__JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x1001e4f4  mov     ebx, eax
0x1001e4f6  cmp     ebx, 0FFFFFAE8h
0x1001e4fc  jg      short loc_1001E522
0x1001e4fe  jz      loc_1001E762
0x1001e504  cmp     ebx, 0FFFFF8EFh
0x1001e50a  jz      loc_1001E5AF
0x1001e510  cmp     ebx, 0FFFFFAE7h
0x1001e516  jnz     short loc_1001E532
0x1001e518  mov     edi, 80040E37h
0x1001e51d  jmp     loc_1001E76B
0x1001e522  cmp     ebx, 0FFFFFAEAh
0x1001e528  jz      loc_1001E762
0x1001e52e  test    ebx, ebx
0x1001e530  jz      short loc_1001E53C
0x1001e532  mov     edi, 80004005h
0x1001e537  jmp     loc_1001E767
0x1001e53c  cmp     [ebp+arg_10], 0
0x1001e540  jz      loc_1001E6AE
0x1001e546  lea     ecx, [ebp+var_80]; this
0x1001e549  call    ?FInit@CIndexProperties@@QAEJXZ; CIndexProperties::FInit(void)
0x1001e54e  mov     edi, eax
0x1001e550  test    edi, edi
0x1001e552  js      loc_1001E786
0x1001e558  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x1001e55d  lea     ecx, [ebp+var_80]; this
0x1001e560  call    ?CopyPropertiesFromStaticTable@CIndexProperties@@QAEJPBUDBInfoProps@@@Z; CIndexProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x1001e565  mov     edi, eax
0x1001e567  test    edi, edi
0x1001e569  js      loc_1001E786
0x1001e56f  mov     edi, [ebp+var_50]
0x1001e572  lea     ecx, [ebp+var_4C]
0x1001e575  push    0
0x1001e577  push    3Ch ; '<'
0x1001e579  push    ecx
0x1001e57a  mov     ecx, [ebp+var_58]
0x1001e57d  mov     eax, [edi+8]
0x1001e580  push    dword ptr [ecx+14h]
0x1001e583  push    [ebp+tableid]
0x1001e586  push    dword ptr [eax+10h]
0x1001e589  call    ds:__imp__JetGetTableIndexInfo@24; JetGetTableIndexInfo(x,x,x,x,x,x)
0x1001e58f  mov     ebx, eax
0x1001e591  cmp     ebx, 0FFFFFA84h
0x1001e597  jg      short loc_1001E5B9
0x1001e599  jz      loc_1001E71D
0x1001e59f  cmp     ebx, 0FFFFF88Dh
0x1001e5a5  jz      short loc_1001E5AF
0x1001e5a7  cmp     ebx, 0FFFFF8EFh
0x1001e5ad  jnz     short loc_1001E532
0x1001e5af  mov     edi, 80040E09h
0x1001e5b4  jmp     loc_1001E76B
0x1001e5b9  test    ebx, ebx
0x1001e5bb  jz      short loc_1001E5C7
0x1001e5bd  mov     edi, 80004005h
0x1001e5c2  jmp     loc_1001E767
0x1001e5c7  push    0; pretinfo
0x1001e5c9  push    0; grbit
0x1001e5cb  lea     eax, [ebp+pcbActual]
0x1001e5d1  push    eax; pcbActual
0x1001e5d2  push    4; cbData
0x1001e5d4  lea     eax, [ebp+pvData]
0x1001e5da  push    eax; pvData
0x1001e5db  push    [ebp+columnid]; columnid
0x1001e5de  mov     eax, [edi+8]
0x1001e5e1  push    [ebp+var_48]; tableid
0x1001e5e4  push    dword ptr [eax+10h]; sesid
0x1001e5e7  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1001e5ed  mov     ebx, eax
0x1001e5ef  mov     [ebp+var_70], ebx
0x1001e5f2  test    ebx, ebx
0x1001e5f4  jns     short loc_1001E600
0x1001e5f6  mov     edi, 80004005h
0x1001e5fb  jmp     loc_1001E76B
0x1001e600  push    [ebp+pvData]; unsigned int
0x1001e606  lea     ecx, [ebp+var_80]; this
0x1001e609  call    ?MapGrbitToJoltProperties@CIndexProperties@@QAEJK@Z; CIndexProperties::MapGrbitToJoltProperties(ulong)
0x1001e60e  mov     edi, eax
0x1001e610  test    edi, edi
0x1001e612  js      loc_1001E767
0x1001e618  lea     ecx, [ebp+var_80]; this
0x1001e61b  call    ?SetPropertiesReadOnly@CSettableProperties@@QAEJXZ; CSettableProperties::SetPropertiesReadOnly(void)
0x1001e620  mov     edi, eax
0x1001e622  test    edi, edi
0x1001e624  js      loc_1001E767
0x1001e62a  cmp     [ebp+arg_10], 0
0x1001e62e  jbe     short loc_1001E6AE
0x1001e630  mov     ebx, [ebp+var_54]
0x1001e633  xor     esi, esi
0x1001e635  nop     word ptr [eax+eax+00000000h]
0x1001e640  lea     eax, [esi+esi*2]
0x1001e643  mov     [ebp+var_54], 0Ch
0x1001e64a  shl     eax, 3
0x1001e64d  lea     edx, [ebx+8]
0x1001e650  add     edx, eax
0x1001e652  lea     ecx, [eax+ebx]
0x1001e655  mov     [ebp+var_88], ecx
0x1001e65b  mov     ecx, offset _DBPROPSET_INDEX
0x1001e660  mov     eax, [ecx]
0x1001e662  cmp     eax, [edx]
0x1001e664  jnz     short loc_1001E686
0x1001e666  add     ecx, 4
0x1001e669  add     edx, 4
0x1001e66c  sub     [ebp+var_54], 4
0x1001e670  jnb     short loc_1001E660
0x1001e672  push    0; struct CDBSession *
0x1001e674  push    [ebp+var_88]; struct tagDBPROPSET *
0x1001e67a  lea     ecx, [ebp+var_80]; this
0x1001e67d  push    1; unsigned int
0x1001e67f  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1001e684  mov     edi, eax
0x1001e686  test    edi, edi
0x1001e688  js      short loc_1001E69B
0x1001e68a  cmp     edi, 40EDAh
0x1001e690  jz      short loc_1001E69B
0x1001e692  mov     [ebp+var_6C], 1
0x1001e699  jmp     short loc_1001E6A2
0x1001e69b  mov     [ebp+var_68], 1
0x1001e6a2  inc     esi
0x1001e6a3  cmp     esi, [ebp+arg_10]
0x1001e6a6  jb      short loc_1001E640
0x1001e6a8  mov     esi, [ebp+var_60]
0x1001e6ab  mov     ebx, [ebp+var_70]
0x1001e6ae  mov     eax, [ebp+var_64]
0x1001e6b1  test    eax, eax
0x1001e6b3  jz      loc_1001E745
0x1001e6b9  push    dword ptr [eax+14h]; String2
0x1001e6bc  mov     eax, [ebp+var_58]
0x1001e6bf  push    dword ptr [eax+14h]; String1
0x1001e6c2  call    ds:__imp___wcsicmp
0x1001e6c8  add     esp, 8
0x1001e6cb  test    eax, eax
0x1001e6cd  jz      short loc_1001E745
0x1001e6cf  mov     ecx, [ebp+var_64]
0x1001e6d2  mov     eax, [ebp+var_50]
0x1001e6d5  push    dword ptr [ecx+14h]
0x1001e6d8  mov     ecx, [ebp+var_58]
0x1001e6db  mov     eax, [eax+8]
0x1001e6de  push    dword ptr [ecx+14h]
0x1001e6e1  push    [ebp+tableid]
0x1001e6e4  push    dword ptr [eax+10h]
0x1001e6e7  call    ds:__imp__JetRenameIndex@16; JetRenameIndex(x,x,x,x)
0x1001e6ed  mov     ebx, eax
0x1001e6ef  cmp     ebx, 0FFFFFA85h
0x1001e6f5  jg      short loc_1001E72B
0x1001e6f7  jz      short loc_1001E724
0x1001e6f9  cmp     ebx, 0FFFFF88Dh
0x1001e6ff  jz      loc_1001E5AF
0x1001e705  cmp     ebx, 0FFFFF8EFh
0x1001e70b  jz      loc_1001E5AF
0x1001e711  cmp     ebx, 0FFFFFA84h
0x1001e717  jnz     loc_1001E532
0x1001e71d  mov     edi, 80040E35h
0x1001e722  jmp     short loc_1001E76B
0x1001e724  mov     edi, 80040E34h
0x1001e729  jmp     short loc_1001E76B
0x1001e72b  cmp     ebx, 0FFFFFC16h
0x1001e731  jz      short loc_1001E73E
0x1001e733  test    ebx, ebx
0x1001e735  jz      short loc_1001E745
0x1001e737  mov     edi, 80004005h
0x1001e73c  jmp     short loc_1001E767
0x1001e73e  mov     edi, 80040E72h
0x1001e743  jmp     short loc_1001E76B
0x1001e745  test    edi, edi
0x1001e747  js      short loc_1001E767
0x1001e749  cmp     [ebp+var_68], 1
0x1001e74d  jnz     short loc_1001E767
  ... truncated ...
```
