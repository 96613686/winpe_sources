# GenericGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CDataSource *,CSettableProperties *,ulong)

- ea: `0x1004c660`
- end: `0x1004cc41`
- name: `?GenericGetProperties@@YGJKQBUtagDBPROPIDSET@@PAKPAPAUtagDBPROPSET@@PAVCDataSource@@PAVCSettableProperties@@K@Z`
- size: `1505`
- prototype: `int __stdcall(unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **, struct CDataSource *, struct CSettableProperties *, unsigned int)`
- caller_count: `7`
- callee_count: `13`
- tags: ``

## callers

- `0x10014c10`
- `0x100152a0`
- `0x100174a0`
- `0x1002dca0`
- `0x1002ef90`
- `0x10040ed0`
- `0x10047070`

## callees

- `0x1001c6d0`
- `0x1001f2d0`
- `0x10020d20`
- `0x1004b390`
- `0x1004b3f0`
- `0x1004b500`
- `0x1004b750`
- `0x1004b810`
- `0x1004b8b0`
- `0x1004ba50`
- `0x1004bbb0`
- `0x1004c660`
- `0x1004dc8d`

## pseudocode

```c
int __userpurge GenericGetProperties@<eax>(
        _DWORD *a1@<edx>,
        unsigned int a2@<ecx>,
        struct DBInfoProps **a3,
        const struct tagDBPROPIDSET *const a4,
        struct JoltProperties *a5,
        struct tagDBPROPSET **a6,
        struct CDataSource *a7,
        struct CSettableProperties *a8,
        unsigned int a9)
{
  struct DBInfoProps **v9; // eax
  unsigned int v10; // ebx
  _DWORD *v11; // esi
  const struct tagDBPROPIDSET *v12; // edx
  unsigned int i; // edi
  struct DBInfoProps **v14; // ebx
  const GUID *v15; // ecx
  _DWORD *v16; // edx
  unsigned int v17; // esi
  bool v18; // cf
  _DWORD *v19; // edx
  const GUID *v20; // ecx
  unsigned int v21; // esi
  unsigned int *v22; // ebx
  int v23; // edi
  _DWORD *v24; // edx
  _DWORD *v25; // edx
  const GUID *v26; // ecx
  unsigned int v27; // esi
  int result; // eax
  struct DBInfoProps *v29; // edx
  DBPROPID *v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // ecx
  int v33; // eax
  __int128 v34; // xmm0
  const struct DBPropMap *v35; // eax
  unsigned int v36; // ecx
  _DWORD *v37; // ebx
  _DWORD *v38; // esi
  _DWORD *v39; // edi
  int v40; // ebx
  int v41; // eax
  _OWORD *v42; // esi
  const struct DBPropMap *LookUpTableEntry; // edi
  int v44; // esi
  struct tagDBPROPSET *v45; // ecx
  const struct DBPropMap *PropertySet; // eax
  void *v47; // ecx
  struct _GUID *v48; // esi
  struct tagDBPROPSET *v49; // ecx
  unsigned int v50; // edi
  _DWORD *v51; // eax
  struct JoltProperties *v52; // esi
  const struct DBInfoProps *Prop; // eax
  struct CDataSource *v54; // ebx
  BOOL v55; // edx
  unsigned int v56; // eax
  int v57; // esi
  struct DBInfoProps **v58; // ecx
  unsigned int j; // esi
  struct tagDBPROP *v60; // [esp-8h] [ebp-4Ch]
  struct CDataSource *v61; // [esp-4h] [ebp-48h]
  struct JoltProperty *v62; // [esp+0h] [ebp-44h]
  struct tagDBPROPSET *v63; // [esp+4h] [ebp-40h]
  struct _GUID *v64; // [esp+8h] [ebp-3Ch]
  const struct _GUID *v65; // [esp+8h] [ebp-3Ch]
  _DWORD *v66; // [esp+10h] [ebp-34h]
  struct _GUID *v68; // [esp+18h] [ebp-2Ch]
  int v69; // [esp+1Ch] [ebp-28h]
  unsigned int v70; // [esp+20h] [ebp-24h]
  _DWORD *v71; // [esp+24h] [ebp-20h]
  int v72; // [esp+28h] [ebp-1Ch]
  int v74; // [esp+30h] [ebp-14h]
  int v75; // [esp+30h] [ebp-14h]
  struct DBInfoProps *v76; // [esp+34h] [ebp-10h]
  struct DBInfoProps *v77; // [esp+34h] [ebp-10h]
  struct DBInfoProps *v78; // [esp+34h] [ebp-10h]
  unsigned int v79; // [esp+38h] [ebp-Ch] BYREF
  struct JoltProperty *v80; // [esp+3Ch] [ebp-8h]
  _DWORD *k; // [esp+40h] [ebp-4h]

  v9 = a3;
  v74 = 0;
  v69 = 0;
  v10 = a2;
  v11 = a1;
  if ( a3 )
    *a3 = 0;
  v12 = a4;
  if ( a4 )
    a4->rgPropertyIDs = 0;
  if ( a2 && !v11 || !a3 || !a4 )
  {
    v23 = -2147024809;
    if ( a4 )
    {
      v22 = (unsigned int *)a3;
      goto LABEL_97;
    }
    goto LABEL_104;
  }
  for ( i = 0; i < a2; v11 = a1 )
  {
    v14 = (struct DBInfoProps **)&v11[6 * i];
    v76 = *v14;
    if ( !*v14 )
    {
      if ( v14[1] )
        goto LABEL_26;
    }
    v15 = &DBPROPSET_PROPERTIESINERROR;
    v16 = &v11[6 * i + 2];
    v17 = 12;
    do
    {
      if ( v15->Data1 != *v16 )
        goto LABEL_19;
      v15 = (const GUID *)((char *)v15 + 4);
      ++v16;
      v18 = v17 < 4;
      v17 -= 4;
    }
    while ( !v18 );
    if ( (char)a7 >= 0 && (a2 > 1 || v76 || v14[1]) )
      goto LABEL_26;
LABEL_19:
    v10 = a2;
    ++i;
  }
  if ( (char)a7 >= 0 && v10 )
  {
    v19 = v11 + 2;
    v20 = &DBPROPSET_PROPERTIESINERROR;
    v21 = 12;
    do
    {
      if ( v20->Data1 != *v19 )
      {
        v24 = a1;
        goto LABEL_31;
      }
      v20 = (const GUID *)((char *)v20 + 4);
      ++v19;
      v18 = v21 < 4;
      v21 -= 4;
    }
    while ( !v18 );
    if ( v10 > 1 || (v24 = a1, a1[1]) )
    {
LABEL_26:
      v22 = (unsigned int *)a3;
      v23 = -2147024809;
      v12 = a4;
LABEL_97:
      if ( v12->rgPropertyIDs )
      {
        if ( v22 )
        {
          for ( j = 0; j < *v22; ++j )
          {
            FreeMemory2(v63);
            v12 = a4;
          }
        }
      }
      if ( Sys )
        (*(void (__thiscall **)(_DWORD, int, DBPROPID *))(*(_DWORD *)Sys + 20))(
          *(_DWORD *)(*(_DWORD *)Sys + 20),
          Sys,
          v12->rgPropertyIDs);
      a4->rgPropertyIDs = 0;
      v9 = a3;
LABEL_104:
      if ( v9 )
        *v9 = 0;
      return v23;
    }
    if ( *a1 )
    {
      v22 = (unsigned int *)a3;
      v23 = -2147024809;
      v12 = a4;
      goto LABEL_97;
    }
LABEL_31:
    v25 = v24 + 2;
    v26 = &DBPROPSET_PROPERTIESINERROR;
    v27 = 12;
    while ( v26->Data1 == *v25 )
    {
      v26 = (const GUID *)((char *)v26 + 4);
      ++v25;
      v18 = v27 < 4;
      v27 -= 4;
      if ( v18 )
        return 0;
    }
  }
  else if ( !v10 )
  {
    GetcNeededPropThingySetsForTableDump((unsigned int)v63, &v64->Data1);
    v29 = v76;
    goto LABEL_38;
  }
  v29 = (struct DBInfoProps *)v10;
LABEL_38:
  *a3 = v29;
  v30 = (DBPROPID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                      *(_DWORD *)(*(_DWORD *)Sys + 12),
                      Sys,
                      24 * (_DWORD)v29);
  v12 = a4;
  a4->rgPropertyIDs = v30;
  if ( !v30 )
  {
    v22 = (unsigned int *)a3;
    v23 = -2147024882;
    goto LABEL_97;
  }
  v31 = 0;
  v70 = 0;
  if ( v10 )
  {
    v36 = 0;
    v70 = 0;
    v37 = a1;
    v38 = a1 + 2;
    for ( k = a1 + 2; ; v38 = k )
    {
      v39 = &v37[6 * v36];
      v40 = (int)&v12->rgPropertyIDs[6 * v36];
      v66 = v39;
      v71 = (_DWORD *)v40;
      v68 = (struct _GUID *)&v38[6 * v36];
      *(struct _GUID *)(v40 + 8) = *v68;
      *(_DWORD *)(v40 + 4) = v39[1];
      *(_DWORD *)v40 = 0;
      v41 = v39[1];
      if ( !v41 )
      {
        v42 = v39 + 2;
        LookUpTableEntry = FindLookUpTableEntry((const struct _GUID *)v63);
        *(_OWORD *)(v40 + 8) = *v42;
        if ( LookUpTableEntry )
        {
          if ( IsPropSetAllowed((unsigned int)v63, v64) == 1 || (v44 = 0, *v66) )
          {
            v44 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                    *(_DWORD *)(*(_DWORD *)Sys + 12),
                    Sys,
                    52 * *((_DWORD *)LookUpTableEntry + 2));
            *(_DWORD *)v40 = v44;
            if ( !v44 )
            {
LABEL_51:
              v22 = (unsigned int *)a3;
              v23 = -2147024882;
              v12 = a4;
              *a3 = (struct DBInfoProps *)v70;
              goto LABEL_97;
            }
          }
          if ( IsPropSetAllowed((unsigned int)v63, v65) == 1 )
          {
            if ( a6 )
              PropertySet = CSettableProperties::FindPropertySet((CSettableProperties *)a6, *v68);
            else
              PropertySet = 0;
            DumpPropSet(PropertySet, (const struct DBInfoProps *)v40, a5, v63, (struct CDataSource *)v64);
            v74 = 1;
          }
          else
          {
            if ( v44 )
              SetPropSetNotSupported(v45, (const struct tagDBPROPIDSET *)v63, (unsigned int)v64);
            v69 = 1;
          }
        }
        else
        {
          *(_DWORD *)(v40 + 4) = 0;
          v69 = 1;
        }
        goto LABEL_89;
      }
      v47 = (void *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                      *(_DWORD *)(*(_DWORD *)Sys + 12),
                      Sys,
                      52 * v41);
      *(_DWORD *)v40 = v47;
      if ( !v47 )
        goto LABEL_51;
      memset(v47, 0, 52 * v39[1]);
      v48 = v68;
      if ( !IsPropSetAllowed((unsigned int)v63, v64) )
      {
        SetPropSetNotSupported(v49, (const struct tagDBPROPIDSET *)v63, (unsigned int)v64);
        v69 = 1;
        goto LABEL_89;
      }
      v50 = 0;
      if ( v66[1] )
        break;
LABEL_89:
      v36 = v70 + 1;
      v70 = v36;
      if ( v36 >= a2 )
      {
        result = 0;
        if ( v69 == 1 )
        {
          result = -2147217887;
          if ( v74 == 1 )
            return 265946;
        }
        return result;
      }
      v12 = a4;
      v37 = a1;
    }
    v72 = *(_DWORD *)v40;
    v51 = v66;
    while ( 1 )
    {
      if ( a6 )
      {
        v52 = CSettableProperties::FindPropertySet((CSettableProperties *)a6, *v48);
        v51 = v66;
      }
      else
      {
        v52 = 0;
      }
      v78 = *(struct DBInfoProps **)(*v51 + 4 * v50);
      Prop = FindProp(*(struct _GUID *)(v40 + 8), (unsigned int)v63);
      v54 = Prop;
      v55 = v52 != 0;
      v80 = (struct JoltProperty *)v55;
      if ( v52 )
      {
        if ( Prop )
          break;
      }
      v57 = 52 * v50;
      v58 = (struct DBInfoProps **)(52 * v50 + v72);
      if ( Prop )
      {
        v62 = (struct JoltProperty *)v55;
        v61 = Prop;
        v60 = 0;
LABEL_84:
        CopyProp((int)a5, (int)v58, v60, v61, v62, (const struct DBInfoProps *)v63, (int)v64);
        v40 = (int)v71;
        goto LABEL_85;
      }
      v40 = (int)v71;
      *v58 = v78;
      *(_DWORD *)(*v71 + v57 + 8) = 1;
LABEL_85:
      v72 = *(_DWORD *)v40;
      if ( *(_DWORD *)(*(_DWORD *)v40 + v57 + 8) )
        v69 = 1;
      else
        v74 = 1;
      v51 = v66;
      ++v50;
      v48 = v68;
      if ( v50 >= v66[1] )
        goto LABEL_89;
    }
    if ( JoltProperties::BinarySearch(v52, (unsigned int)v78, &v79) < 0 )
    {
      v62 = v80;
      v57 = 52 * v50;
      v61 = v54;
      v60 = 0;
    }
    else
    {
      v62 = v80;
      v61 = v54;
      v56 = *((_DWORD *)v52 + 4) + 48 * v79;
      v57 = 52 * v50;
      v60 = (struct tagDBPROP *)v56;
    }
    v58 = (struct DBInfoProps **)(52 * v50 + v72);
    goto LABEL_84;
  }
  v32 = (unsigned int)a7;
  do
  {
    if ( !v32 || (v32 & dword_100037FC[4 * v10]) != 0 )
    {
      v77 = (struct DBInfoProps *)&v12->rgPropertyIDs[6 * v31];
      v75 = dword_100037F8[4 * v10];
      v33 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
              *(_DWORD *)(*(_DWORD *)Sys + 12),
              Sys,
              52 * v75);
      *(_DWORD *)v77 = v33;
      if ( !v33 )
        goto LABEL_51;
      v34 = (__int128)*(&off_100037F0)[4 * v10];
      *((_DWORD *)v77 + 1) = v75;
      *(_OWORD *)((char *)v77 + 8) = v34;
      if ( a6 )
        v35 = CSettableProperties::FindPropertySet((CSettableProperties *)a6, *(&off_100037F0)[4 * v10]);
      else
        v35 = 0;
      DumpPropSet(v35, v77, a5, v63, (struct CDataSource *)v64);
      v32 = (unsigned int)a7;
      v31 = v70 + 1;
      v12 = a4;
      ++v70;
    }
    ++v10;
  }
  while ( v10 < 0xF );
  return 0;
}

```

## disassembly

```asm
0x1004c660  mov     edi, edi
0x1004c662  push    ebp
0x1004c663  mov     ebp, esp
0x1004c665  and     esp, 0FFFFFFF8h
0x1004c668  sub     esp, 34h
0x1004c66b  mov     eax, [ebp+arg_0]
0x1004c66e  mov     [esp+34h+var_14], 0
0x1004c676  mov     [esp+34h+var_28], 0
0x1004c67e  push    ebx
0x1004c67f  mov     ebx, ecx
0x1004c681  mov     [esp+38h+var_18], ebx
0x1004c685  push    esi; int
0x1004c686  mov     esi, edx
0x1004c688  mov     [esp+3Ch+var_30], esi
0x1004c68c  push    edi; struct tagDBPROPSET *
0x1004c68d  test    eax, eax
0x1004c68f  jz      short loc_1004C697
0x1004c691  mov     dword ptr [eax], 0
0x1004c697  mov     edx, [ebp+arg_4]
0x1004c69a  test    edx, edx
0x1004c69c  jz      short loc_1004C6A4
0x1004c69e  mov     dword ptr [edx], 0
0x1004c6a4  test    ebx, ebx
0x1004c6a6  jz      short loc_1004C6B0
0x1004c6a8  test    esi, esi
0x1004c6aa  jz      loc_1004CBD6
0x1004c6b0  test    eax, eax
0x1004c6b2  jz      loc_1004CBD6
0x1004c6b8  test    edx, edx
0x1004c6ba  jz      loc_1004CBD6
0x1004c6c0  xor     edi, edi
0x1004c6c2  test    ebx, ebx
0x1004c6c4  jz      short loc_1004C728
0x1004c6c6  lea     eax, [edi+edi*2]
0x1004c6c9  mov     ecx, [esi+eax*8]
0x1004c6cc  lea     ebx, [esi+eax*8]
0x1004c6cf  mov     [esp+40h+var_10], ecx
0x1004c6d3  test    ecx, ecx
0x1004c6d5  jnz     short loc_1004C6E0
0x1004c6d7  cmp     [ebx+4], ecx
0x1004c6da  jnz     loc_1004C766
0x1004c6e0  lea     edx, [esi+8]
0x1004c6e3  mov     ecx, offset _DBPROPSET_PROPERTIESINERROR
0x1004c6e8  lea     edx, [edx+eax*8]
0x1004c6eb  mov     esi, 0Ch
0x1004c6f0  mov     eax, [ecx]
0x1004c6f2  cmp     eax, [edx]
0x1004c6f4  jnz     short loc_1004C71B
0x1004c6f6  add     ecx, 4
0x1004c6f9  add     edx, 4
0x1004c6fc  sub     esi, 4
0x1004c6ff  jnb     short loc_1004C6F0
0x1004c701  test    byte ptr [ebp+arg_10], 80h
0x1004c705  jnz     short loc_1004C71B
0x1004c707  cmp     [esp+40h+var_18], 1
0x1004c70c  ja      short loc_1004C766
0x1004c70e  cmp     [esp+40h+var_10], 0
0x1004c713  jnz     short loc_1004C766
0x1004c715  cmp     dword ptr [ebx+4], 0
0x1004c719  jnz     short loc_1004C766
0x1004c71b  mov     ebx, [esp+40h+var_18]
0x1004c71f  inc     edi
0x1004c720  mov     esi, [esp+40h+var_30]
0x1004c724  cmp     edi, ebx
0x1004c726  jb      short loc_1004C6C6
0x1004c728  mov     eax, [ebp+arg_10]
0x1004c72b  test    al, al
0x1004c72d  js      loc_1004C7C2
0x1004c733  cmp     ebx, 1
0x1004c736  jb      loc_1004C7C2
0x1004c73c  lea     edx, [esi+8]
0x1004c73f  mov     ecx, offset _DBPROPSET_PROPERTIESINERROR
0x1004c744  mov     esi, 0Ch
0x1004c749  nop     dword ptr [eax+00000000h]
0x1004c750  mov     eax, [ecx]
0x1004c752  cmp     eax, [edx]
0x1004c754  jnz     short loc_1004C795
0x1004c756  add     ecx, 4
0x1004c759  add     edx, 4
0x1004c75c  sub     esi, 4
0x1004c75f  jnb     short loc_1004C750
0x1004c761  cmp     ebx, 1
0x1004c764  jbe     short loc_1004C776
0x1004c766  mov     ebx, [ebp+arg_0]
0x1004c769  mov     edi, 80070057h
0x1004c76e  mov     edx, [ebp+arg_4]
0x1004c771  jmp     loc_1004CBE1
0x1004c776  mov     edx, [esp+40h+var_30]
0x1004c77a  cmp     dword ptr [edx+4], 0
0x1004c77e  jnz     short loc_1004C766
0x1004c780  cmp     dword ptr [edx], 0
0x1004c783  jz      short loc_1004C799
0x1004c785  mov     ebx, [ebp+arg_0]
0x1004c788  mov     edi, 80070057h
0x1004c78d  mov     edx, [ebp+arg_4]
0x1004c790  jmp     loc_1004CBE1
0x1004c795  mov     edx, [esp+40h+var_30]
0x1004c799  add     edx, 8
0x1004c79c  mov     ecx, offset _DBPROPSET_PROPERTIESINERROR
0x1004c7a1  mov     esi, 0Ch
0x1004c7a6  mov     eax, [ecx]
0x1004c7a8  cmp     eax, [edx]
0x1004c7aa  jnz     short loc_1004C7D7
0x1004c7ac  add     ecx, 4
0x1004c7af  add     edx, 4
0x1004c7b2  sub     esi, 4
0x1004c7b5  jnb     short loc_1004C7A6
0x1004c7b7  xor     eax, eax
0x1004c7b9  pop     edi
0x1004c7ba  pop     esi
0x1004c7bb  pop     ebx
0x1004c7bc  mov     esp, ebp
0x1004c7be  pop     ebp
0x1004c7bf  retn    14h
0x1004c7c2  test    ebx, ebx
0x1004c7c4  jnz     short loc_1004C7D7
0x1004c7c6  lea     edx, [esp+40h+var_10]
0x1004c7ca  mov     ecx, eax
0x1004c7cc  call    ?GetcNeededPropThingySetsForTableDump@@YGJKAAK@Z; GetcNeededPropThingySetsForTableDump(ulong,ulong &)
0x1004c7d1  mov     edx, [esp+40h+var_10]
0x1004c7d5  jmp     short loc_1004C7D9
0x1004c7d7  mov     edx, ebx
0x1004c7d9  mov     eax, [ebp+arg_0]
0x1004c7dc  mov     [eax], edx
0x1004c7de  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1004c7e4  mov     eax, [ecx]
0x1004c7e6  mov     esi, [eax+0Ch]
0x1004c7e9  lea     eax, [edx+edx*2]
0x1004c7ec  shl     eax, 3
0x1004c7ef  push    eax
0x1004c7f0  push    ecx
0x1004c7f1  mov     ecx, esi
0x1004c7f3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004c7f9  call    esi
0x1004c7fb  mov     edx, [ebp+arg_4]
0x1004c7fe  mov     [edx], eax
0x1004c800  test    eax, eax
0x1004c802  jnz     short loc_1004C811
0x1004c804  mov     ebx, [ebp+arg_0]
0x1004c807  mov     edi, 8007000Eh
0x1004c80c  jmp     loc_1004CBE1
0x1004c811  xor     eax, eax
0x1004c813  mov     [esp+40h+var_24], eax
0x1004c817  test    ebx, ebx
0x1004c819  jnz     loc_1004C8F0
0x1004c81f  mov     ecx, [ebp+arg_10]
0x1004c822  mov     edi, ebx
0x1004c824  shl     edi, 4
0x1004c827  test    ecx, ecx
0x1004c829  jz      short loc_1004C837
0x1004c82b  test    ds:dword_100037FC[edi], ecx
0x1004c831  jz      loc_1004C8C5
0x1004c837  lea     ecx, [eax+eax*2]
0x1004c83a  mov     eax, [edx]
0x1004c83c  lea     eax, [eax+ecx*8]
0x1004c83f  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1004c845  mov     [esp+40h+var_10], eax
0x1004c849  mov     eax, ds:dword_100037F8[edi]
0x1004c84f  mov     [esp+40h+var_14], eax
0x1004c853  mov     edx, [ecx]
0x1004c855  imul    eax, 34h ; '4'
0x1004c858  mov     esi, [edx+0Ch]
0x1004c85b  push    eax
0x1004c85c  push    ecx
0x1004c85d  mov     ecx, esi
0x1004c85f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004c865  call    esi
0x1004c867  mov     esi, [esp+40h+var_10]
0x1004c86b  mov     [esi], eax
0x1004c86d  test    eax, eax
0x1004c86f  jz      short loc_1004C8DA
0x1004c871  mov     eax, ds:off_100037F0[edi]
0x1004c877  lea     edi, off_100037F0[edi]
0x1004c87d  mov     edx, [ebp+arg_C]
0x1004c880  movups  xmm0, xmmword ptr [eax]
0x1004c883  mov     eax, [esp+40h+var_14]
0x1004c887  mov     [esi+4], eax
0x1004c88a  movups  xmmword ptr [esi+8], xmm0
0x1004c88e  test    edx, edx
0x1004c890  jz      short loc_1004C8A8
0x1004c892  mov     eax, [edi]
0x1004c894  sub     esp, 10h
0x1004c897  mov     ecx, esp
0x1004c899  movups  xmm0, xmmword ptr [eax]
0x1004c89c  movups  xmmword ptr [ecx], xmm0
0x1004c89f  mov     ecx, edx; this
0x1004c8a1  call    ?FindPropertySet@CSettableProperties@@QAEPAVJoltProperties@@U_GUID@@@Z; CSettableProperties::FindPropertySet(_GUID)
0x1004c8a6  jmp     short loc_1004C8AA
0x1004c8a8  xor     eax, eax
0x1004c8aa  push    [ebp+arg_8]; struct JoltProperties *
0x1004c8ad  mov     ecx, edi
0x1004c8af  push    esi; struct DBInfoProps *
0x1004c8b0  push    eax; struct DBPropMap *
0x1004c8b1  call    ?DumpPropSet@@YGJPBUDBPropMap@@PBUDBInfoProps@@PBVJoltProperties@@PAUtagDBPROPSET@@PAVCDataSource@@@Z; DumpPropSet(DBPropMap const *,DBInfoProps const *,JoltProperties const *,tagDBPROPSET *,CDataSource *)
0x1004c8b6  mov     eax, [esp+40h+var_24]
0x1004c8ba  mov     ecx, [ebp+arg_10]
0x1004c8bd  inc     eax
0x1004c8be  mov     edx, [ebp+arg_4]
0x1004c8c1  mov     [esp+40h+var_24], eax
0x1004c8c5  inc     ebx
0x1004c8c6  cmp     ebx, 0Fh
0x1004c8c9  jb      loc_1004C822
0x1004c8cf  xor     eax, eax
0x1004c8d1  pop     edi
0x1004c8d2  pop     esi
0x1004c8d3  pop     ebx
0x1004c8d4  mov     esp, ebp
0x1004c8d6  pop     ebp
0x1004c8d7  retn    14h
0x1004c8da  mov     ebx, [ebp+arg_0]
0x1004c8dd  mov     edi, 8007000Eh
0x1004c8e2  mov     eax, [esp+40h+var_24]
0x1004c8e6  mov     edx, [ebp+arg_4]
0x1004c8e9  mov     [ebx], eax
0x1004c8eb  jmp     loc_1004CBE1
0x1004c8f0  xor     ecx, ecx
0x1004c8f2  mov     [esp+40h+var_24], ecx
0x1004c8f6  test    ebx, ebx
0x1004c8f8  jz      loc_1004CBAE
0x1004c8fe  mov     ebx, [esp+40h+var_30]
0x1004c902  lea     esi, [ebx+8]
0x1004c905  mov     [esp+40h+var_4], esi
0x1004c909  nop     dword ptr [eax+00000000h]
0x1004c910  lea     eax, [ecx+ecx*2]
0x1004c913  shl     eax, 3
0x1004c916  movups  xmm0, xmmword ptr [eax+esi]
0x1004c91a  lea     edi, [eax+ebx]
0x1004c91d  mov     ebx, [edx]
0x1004c91f  add     ebx, eax
0x1004c921  mov     [esp+40h+var_34], edi
0x1004c925  add     eax, esi
0x1004c927  mov     [esp+40h+var_20], ebx
0x1004c92b  mov     [esp+40h+var_2C], eax
0x1004c92f  movups  xmmword ptr [ebx+8], xmm0
0x1004c933  mov     eax, [edi+4]
0x1004c936  mov     [ebx+4], eax
0x1004c939  mov     dword ptr [ebx], 0
0x1004c93f  mov     eax, [edi+4]
0x1004c942  test    eax, eax
0x1004c944  jnz     loc_1004CA1B
0x1004c94a  lea     esi, [edi+8]
0x1004c94d  mov     ecx, esi
0x1004c94f  call    ?FindLookUpTableEntry@@YGPBUDBPropMap@@ABU_GUID@@@Z; FindLookUpTableEntry(_GUID const &)
0x1004c954  movups  xmm0, xmmword ptr [esi]
0x1004c957  mov     edi, eax
0x1004c959  movups  xmmword ptr [ebx+8], xmm0
0x1004c95d  test    edi, edi
0x1004c95f  jnz     short loc_1004C971
0x1004c961  mov     [ebx+4], eax
0x1004c964  mov     [esp+40h+var_28], 1
0x1004c96c  jmp     loc_1004CB8F
0x1004c971  mov     edx, [esp+40h+var_2C]
0x1004c975  mov     ecx, [ebp+arg_10]
0x1004c978  call    ?IsPropSetAllowed@@YGHKABU_GUID@@@Z; IsPropSetAllowed(ulong,_GUID const &)
0x1004c97d  cmp     eax, 1
0x1004c980  jz      short loc_1004C98C
0x1004c982  mov     eax, [esp+40h+var_34]
0x1004c986  xor     esi, esi
0x1004c988  cmp     [eax], esi
0x1004c98a  jz      short loc_1004C9B3
0x1004c98c  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1004c992  imul    eax, [edi+8], 34h ; '4'
0x1004c996  mov     edx, [ecx]
0x1004c998  push    eax
0x1004c999  push    ecx
0x1004c99a  mov     esi, [edx+0Ch]
0x1004c99d  mov     ecx, esi
0x1004c99f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004c9a5  call    esi
0x1004c9a7  mov     esi, eax
0x1004c9a9  mov     [ebx], esi
0x1004c9ab  test    esi, esi
0x1004c9ad  jz      loc_1004C8DA
0x1004c9b3  mov     edx, [esp+40h+var_2C]
0x1004c9b7  mov     ecx, [ebp+arg_10]
0x1004c9ba  call    ?IsPropSetAllowed@@YGHKABU_GUID@@@Z; IsPropSetAllowed(ulong,_GUID const &)
0x1004c9bf  cmp     eax, 1
0x1004c9c2  jnz     short loc_1004C9FE
0x1004c9c4  mov     esi, [ebp+arg_C]
0x1004c9c7  test    esi, esi
0x1004c9c9  jz      short loc_1004C9E3
0x1004c9cb  mov     ecx, [esp+40h+var_2C]
0x1004c9cf  sub     esp, 10h
0x1004c9d2  mov     eax, esp
0x1004c9d4  movups  xmm0, xmmword ptr [ecx]
0x1004c9d7  mov     ecx, esi; this
0x1004c9d9  movups  xmmword ptr [eax], xmm0
0x1004c9dc  call    ?FindPropertySet@CSettableProperties@@QAEPAVJoltProperties@@U_GUID@@@Z; CSettableProperties::FindPropertySet(_GUID)
0x1004c9e1  jmp     short loc_1004C9E5
0x1004c9e3  xor     eax, eax
0x1004c9e5  push    [ebp+arg_8]; struct JoltProperties *
0x1004c9e8  mov     ecx, edi
0x1004c9ea  push    ebx; struct DBInfoProps *
0x1004c9eb  push    eax; struct DBPropMap *
0x1004c9ec  call    ?DumpPropSet@@YGJPBUDBPropMap@@PBUDBInfoProps@@PBVJoltProperties@@PAUtagDBPROPSET@@PAVCDataSource@@@Z; DumpPropSet(DBPropMap const *,DBInfoProps const *,JoltProperties const *,tagDBPROPSET *,CDataSource *)
0x1004c9f1  mov     [esp+40h+var_14], 1
0x1004c9f9  jmp     loc_1004CB8F
0x1004c9fe  test    esi, esi
0x1004ca00  jz      short loc_1004CA0E
0x1004ca02  mov     edx, [esp+40h+var_34]
  ... truncated ...
```
