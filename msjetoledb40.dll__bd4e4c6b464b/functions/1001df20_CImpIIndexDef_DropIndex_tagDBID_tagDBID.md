# CImpIIndexDef::DropIndex(tagDBID *,tagDBID *)

- ea: `0x1001df20`
- end: `0x1001e344`
- name: `?DropIndex@CImpIIndexDef@@UAGJPAUtagDBID@@0@Z`
- size: `1060`
- prototype: `int(CImpIIndexDef *__hidden this, struct tagDBID *, struct tagDBID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001df20`
- `0x1001e800`
- `0x1001e9d0`
- `0x1001eae0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001e043`
- `KERNEL32!LeaveCriticalSection` at `0x1001e043`
- `KERNEL32!EnterCriticalSection` at `0x1001df98`
- `KERNEL32!EnterCriticalSection` at `0x1001df98`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001df85`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001df85`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e013`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e028`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e013`
- `msjet40!__imp__JetCloseTable@8` at `0x1001e028`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001dfed`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001dfed`
- `msjet40!__imp__JetMove@16` at `0x1001e149`
- `msjet40!__imp__JetMove@16` at `0x1001e1f5`
- `msjet40!__imp__JetMove@16` at `0x1001e21a`
- `msjet40!__imp__JetMove@16` at `0x1001e149`
- `msjet40!__imp__JetMove@16` at `0x1001e1f5`
- `msjet40!__imp__JetMove@16` at `0x1001e21a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001e1d4`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1001e1d4`

## pseudocode

```c
int __stdcall CImpIIndexDef::DropIndex(CImpIIndexDef *this, struct tagDBID *a2, struct tagDBID *a3)
{
  CImpIIndexDef *v3; // edi
  struct _RTL_CRITICAL_SECTION *v4; // esi
  int IndexInfo; // ebx
  struct tagDBID *v6; // ecx
  const DBID *v7; // edx
  unsigned int v8; // ebx
  bool v9; // cf
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  unsigned int ulPropid; // ecx
  char *v15; // edx
  unsigned int v16; // ebx
  unsigned int v17; // edi
  CImpIIndexDef *v18; // esi
  JET_ERR v19; // eax
  int v20; // ecx
  unsigned int v21; // ecx
  int v22; // ecx
  struct tagDBID *v23; // eax
  int v24; // edi
  int v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // [esp-14h] [ebp-9Ch]
  const unsigned __int16 *v29; // [esp-14h] [ebp-9Ch]
  unsigned __int16 *v30; // [esp-10h] [ebp-98h]
  void *v31; // [esp-10h] [ebp-98h]
  JET_SESID v32; // [esp-10h] [ebp-98h]
  struct _GUID *v33; // [esp+0h] [ebp-88h]
  struct _GUID *v34; // [esp+4h] [ebp-84h]
  unsigned int pcbActual; // [esp+14h] [ebp-74h] BYREF
  int v36; // [esp+18h] [ebp-70h]
  JET_TABLEID tableid; // [esp+1Ch] [ebp-6Ch] BYREF
  CImpIIndexDef *v38; // [esp+20h] [ebp-68h]
  struct tagDBID *v39; // [esp+24h] [ebp-64h]
  struct _RTL_CRITICAL_SECTION *v40; // [esp+28h] [ebp-60h] BYREF
  int v41; // [esp+2Ch] [ebp-5Ch] BYREF
  void *Block; // [esp+30h] [ebp-58h]
  unsigned int v43; // [esp+34h] [ebp-54h] BYREF
  int v44; // [esp+38h] [ebp-50h]
  unsigned __int16 v45; // [esp+3Ch] [ebp-4Ch] BYREF
  JET_TABLEID v46; // [esp+40h] [ebp-48h]
  unsigned int v47; // [esp+44h] [ebp-44h]
  JET_COLUMNID columnid; // [esp+48h] [ebp-40h]
  int v49; // [esp+84h] [ebp-4h]

  v3 = this;
  v38 = this;
  v39 = a2;
  v41 = (int)a3;
  v43 = 0;
  tableid = -1;
  v44 = 0;
  Block = 0;
  v46 = -1;
  v36 = 0;
  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  v40 = v4;
  EnterCriticalSection(v4);
  v49 = 0;
  if ( !a2 )
  {
    IndexInfo = -2147024809;
LABEL_7:
    v10 = *((_DWORD *)this + 2);
    v11 = *(_DWORD *)(v10 + 20);
    v12 = *(_DWORD *)(v10 + 16);
LABEL_8:
    if ( !JetGetDatabaseInfo(v12, v11, &v40, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IIndexDefinition, 0, v33, (int)v34);
    goto LABEL_10;
  }
  v6 = a2;
  v7 = &DB_NULLID;
  v8 = 20;
  while ( v6->uGuid.guid.Data1 == v7->uGuid.guid.Data1 )
  {
    v6 = (struct tagDBID *)((char *)v6 + 4);
    v7 = (const DBID *)((char *)v7 + 4);
    v9 = v8 < 4;
    v8 -= 4;
    if ( v9 )
      goto LABEL_6;
  }
  if ( v39->eKind != 2 || (ulPropid = v39->uName.ulPropid) == 0 )
  {
LABEL_6:
    IndexInfo = -2147217865;
    goto LABEL_7;
  }
  if ( v41 && (*(_DWORD *)(v41 + 16) != 2 || !*(_DWORD *)(v41 + 20)) )
  {
    IndexInfo = -2147217867;
    goto LABEL_7;
  }
  IndexInfo = CJOLT::JOLTJetOpenTable(
                ulPropid,
                v28,
                v30,
                (const void *)2,
                (unsigned int)&tableid,
                (unsigned int)&v43,
                &v33->Data1,
                (int *)v34);
  if ( IndexInfo < 0 )
    goto LABEL_28;
  if ( v41 )
  {
    IndexInfo = CJOLT::JOLTJetDeleteIndex(
                  *(_DWORD *)(v41 + 20),
                  (unsigned int)&v43,
                  (const unsigned __int16 *)v33,
                  (int *)v34);
LABEL_28:
    v15 = 0;
    goto LABEL_29;
  }
  IndexInfo = CJOLT::JOLTJetGetIndexInfo(
                v39->uName.ulPropid,
                0,
                &v45,
                v29,
                v31,
                (unsigned int)&v43,
                0,
                &v41,
                (int)v33,
                (int *)v34);
  v41 = IndexInfo;
  if ( IndexInfo < 0 || !v47 )
    goto LABEL_28;
  v43 = JetMove(*(_DWORD *)(*((_DWORD *)this + 2) + 16), v46, 0x80000000, 0);
  if ( v43 )
  {
    IndexInfo = -2147467259;
    goto LABEL_28;
  }
  v16 = v47;
  if ( v47 )
  {
    v15 = (char *)operator new(saturated_mul(2u, 65 * v47));
    Block = v15;
    if ( !v15 )
    {
      IndexInfo = -2147024882;
      goto LABEL_29;
    }
    v16 = v47;
  }
  else
  {
    v15 = 0;
  }
  v17 = 0;
  if ( v16 )
  {
    v18 = v38;
    do
    {
      v19 = JetRetrieveColumn(
              *(_DWORD *)(*((_DWORD *)v18 + 2) + 16),
              v46,
              columnid,
              &v15[130 * v17],
              0x82u,
              &pcbActual,
              0,
              0);
      v20 = v44 + 1;
      v32 = *(_DWORD *)(*((_DWORD *)v18 + 2) + 16);
      if ( !v19 )
        v20 = v44;
      v44 = v20;
      v43 = JetMove(v32, v46, 1, 0);
      if ( v43 == -1603 && v17 < v47 )
        v43 = JetMove(*(_DWORD *)(*((_DWORD *)v18 + 2) + 16), v46, 0x80000000, 0);
      v15 = (char *)Block;
      v21 = 65 * v17++ + (pcbActual >> 1);
      *((_WORD *)Block + v21) = 0;
      v16 = v47;
    }
    while ( v17 < v47 );
    v22 = v44;
    v4 = v40;
  }
  else
  {
    v22 = 0;
  }
  v23 = 0;
  v39 = 0;
  if ( v16 )
  {
    do
    {
      v24 = 130 * (_DWORD)v23;
      if ( !v23 )
        goto LABEL_55;
      v25 = wcscmp((const unsigned __int16 *)&v15[v24], (const unsigned __int16 *)&v15[v24 - 130]);
      if ( v25 )
        v25 = v25 < 0 ? -1 : 1;
      if ( !v25 )
      {
        v22 = v44;
      }
      else
      {
LABEL_55:
        ++v36;
        v26 = CJOLT::JOLTJetDeleteIndex(
                (unsigned int)Block + v24,
                (unsigned int)&v43,
                (const unsigned __int16 *)v33,
                (int *)v34);
        v22 = v44;
        v16 = v47;
        v41 = v26;
        if ( v26 < 0 )
          v22 = ++v44;
      }
      v15 = (char *)Block;
      v23 = (struct tagDBID *)((char *)&v39->uGuid.guid.Data1 + 1);
      v39 = v23;
    }
    while ( (unsigned int)v23 < v16 );
    v4 = v40;
  }
  v3 = v38;
  v15 = (char *)Block;
  if ( v22 )
  {
    IndexInfo = 265946;
    if ( v22 == v36 )
      IndexInfo = -2147217887;
  }
  else
  {
    IndexInfo = v41;
  }
LABEL_29:
  v40 = (struct _RTL_CRITICAL_SECTION *)IndexInfo;
  if ( v43 )
  {
    CExtError::SendJetErrortoOLEAuto(v43, (int)&IID_IIndexDefinition, (int)v33, v34);
    goto LABEL_10;
  }
  if ( IndexInfo < 0 )
  {
    v27 = *((_DWORD *)v3 + 2);
    IndexInfo = (int)v40;
    Block = v15;
    v11 = *(_DWORD *)(v27 + 20);
    v12 = *(_DWORD *)(v27 + 16);
    if ( v40 != (struct _RTL_CRITICAL_SECTION *)-2147024882 )
      goto LABEL_8;
  }
LABEL_10:
  if ( tableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v3 + 2) + 16), tableid);
  if ( v46 != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v3 + 2) + 16), v46);
  if ( Block )
    operator delete(Block);
  if ( v4 )
    LeaveCriticalSection(v4);
  return IndexInfo;
}

```

## disassembly

```asm
0x1001df20  mov     edi, edi
0x1001df22  push    ebp
0x1001df23  mov     ebp, esp
0x1001df25  push    0FFFFFFFFh
0x1001df27  push    offset ?DropIndex@CImpIIndexDef@@UAGJPAUtagDBID@@0@Z_SEH
0x1001df2c  mov     eax, large fs:0
0x1001df32  push    eax
0x1001df33  sub     esp, 6Ch
0x1001df36  mov     eax, ___security_cookie
0x1001df3b  xor     eax, ebp
0x1001df3d  mov     [ebp+var_10], eax
0x1001df40  push    ebx
0x1001df41  push    esi
0x1001df42  push    edi; int *
0x1001df43  push    eax; unsigned __int16 *
0x1001df44  lea     eax, [ebp+var_C]
0x1001df47  mov     large fs:0, eax
0x1001df4d  mov     ecx, [ebp+arg_8]
0x1001df50  xor     eax, eax
0x1001df52  mov     edi, [ebp+this]
0x1001df55  mov     ebx, [ebp+arg_4]
0x1001df58  push    eax; perrinfo
0x1001df59  push    eax; dwReserved
0x1001df5a  mov     [ebp+var_68], edi
0x1001df5d  mov     [ebp+var_64], ebx
0x1001df60  mov     [ebp+var_5C], ecx
0x1001df63  mov     [ebp+var_54], 0
0x1001df6a  mov     [ebp+tableid], 0FFFFFFFFh
0x1001df71  mov     [ebp+var_50], 0
0x1001df78  mov     [ebp+Block], eax
0x1001df7b  mov     [ebp+var_48], 0FFFFFFFFh
0x1001df82  mov     [ebp+var_70], eax
0x1001df85  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001df8b  mov     esi, [edi+8]
0x1001df8e  add     esi, 68h ; 'h'
0x1001df91  push    esi; lpCriticalSection
0x1001df92  mov     [ebp+var_60], esi
0x1001df95  mov     [ebp+var_78], esi
0x1001df98  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001df9e  mov     [ebp+var_4], 0
0x1001dfa5  test    ebx, ebx
0x1001dfa7  jnz     short loc_1001DFB0
0x1001dfa9  mov     ebx, 80070057h
0x1001dfae  jmp     short loc_1001DFDA
0x1001dfb0  mov     ecx, ebx
0x1001dfb2  mov     edx, offset _DB_NULLID
0x1001dfb7  mov     ebx, 14h
0x1001dfbc  nop     dword ptr [eax+00h]
0x1001dfc0  mov     eax, [ecx]
0x1001dfc2  cmp     eax, [edx]
0x1001dfc4  jnz     loc_1001E069
0x1001dfca  add     ecx, 4
0x1001dfcd  add     edx, 4
0x1001dfd0  sub     ebx, 4
0x1001dfd3  jnb     short loc_1001DFC0
0x1001dfd5  mov     ebx, 80040E37h
0x1001dfda  mov     eax, [edi+8]
0x1001dfdd  mov     ecx, [eax+14h]
0x1001dfe0  mov     eax, [eax+10h]
0x1001dfe3  push    3
0x1001dfe5  push    4
0x1001dfe7  lea     edx, [ebp+var_60]
0x1001dfea  push    edx
0x1001dfeb  push    ecx
0x1001dfec  push    eax
0x1001dfed  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001dff3  test    eax, eax
0x1001dff5  jnz     short loc_1001E004
0x1001dff7  push    eax; int
0x1001dff8  push    offset _IID_IIndexDefinition; int
0x1001dffd  mov     edx, ebx
0x1001dfff  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1001e004  mov     eax, [ebp+tableid]
0x1001e007  cmp     eax, 0FFFFFFFFh
0x1001e00a  jz      short loc_1001E019
0x1001e00c  push    eax; tableid
0x1001e00d  mov     eax, [edi+8]
0x1001e010  push    dword ptr [eax+10h]; sesid
0x1001e013  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1001e019  mov     eax, [ebp+var_48]
0x1001e01c  cmp     eax, 0FFFFFFFFh
0x1001e01f  jz      short loc_1001E02E
0x1001e021  push    eax; tableid
0x1001e022  mov     eax, [edi+8]
0x1001e025  push    dword ptr [eax+10h]; sesid
0x1001e028  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x1001e02e  mov     eax, [ebp+Block]
0x1001e031  test    eax, eax
0x1001e033  jz      short loc_1001E03E
0x1001e035  push    eax; Block
0x1001e036  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001e03b  add     esp, 4
0x1001e03e  test    esi, esi
0x1001e040  jz      short loc_1001E049
0x1001e042  push    esi; lpCriticalSection
0x1001e043  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001e049  mov     eax, ebx
0x1001e04b  mov     ecx, [ebp+var_C]
0x1001e04e  mov     large fs:0, ecx
0x1001e055  pop     ecx
0x1001e056  pop     edi
0x1001e057  pop     esi
0x1001e058  pop     ebx
0x1001e059  mov     ecx, [ebp+var_10]
0x1001e05c  xor     ecx, ebp; StackCookie
0x1001e05e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001e063  mov     esp, ebp
0x1001e065  pop     ebp
0x1001e066  retn    0Ch
0x1001e069  mov     eax, [ebp+var_64]
0x1001e06c  cmp     dword ptr [eax+10h], 2
0x1001e070  jnz     loc_1001DFD5
0x1001e076  mov     ecx, [eax+14h]
0x1001e079  test    ecx, ecx
0x1001e07b  jz      loc_1001DFD5
0x1001e081  mov     eax, [ebp+var_5C]
0x1001e084  test    eax, eax
0x1001e086  jz      short loc_1001E09E
0x1001e088  cmp     dword ptr [eax+10h], 2
0x1001e08c  jnz     short loc_1001E094
0x1001e08e  cmp     dword ptr [eax+14h], 0
0x1001e092  jnz     short loc_1001E09E
0x1001e094  mov     ebx, 80040E35h
0x1001e099  jmp     loc_1001DFDA
0x1001e09e  mov     eax, [edi+8]
0x1001e0a1  lea     edx, [ebp+var_54]
0x1001e0a4  push    edx; unsigned int
0x1001e0a5  lea     edx, [ebp+tableid]
0x1001e0a8  push    edx; unsigned int
0x1001e0a9  mov     edx, [eax+14h]
0x1001e0ac  push    2; void *
0x1001e0ae  sub     esp, 8
0x1001e0b1  push    ecx; unsigned int
0x1001e0b2  mov     ecx, [eax+10h]
0x1001e0b5  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x1001e0ba  mov     ebx, eax
0x1001e0bc  test    ebx, ebx
0x1001e0be  js      short loc_1001E0DE
0x1001e0c0  mov     ecx, [ebp+var_5C]
0x1001e0c3  mov     eax, [edi+8]
0x1001e0c6  test    ecx, ecx
0x1001e0c8  jz      short loc_1001E106
0x1001e0ca  lea     edx, [ebp+var_54]
0x1001e0cd  push    edx; unsigned int
0x1001e0ce  push    dword ptr [ecx+14h]; unsigned int
0x1001e0d1  mov     edx, [ebp+tableid]
0x1001e0d4  mov     ecx, [eax+10h]
0x1001e0d7  call    ?JOLTJetDeleteIndex@CJOLT@@SGJKKPBGAAJ@Z; CJOLT::JOLTJetDeleteIndex(ulong,ulong,ushort const *,long &)
0x1001e0dc  mov     ebx, eax
0x1001e0de  xor     edx, edx
0x1001e0e0  mov     eax, [ebp+var_54]
0x1001e0e3  mov     [ebp+var_60], ebx
0x1001e0e6  test    eax, eax
0x1001e0e8  jz      loc_1001E31C
0x1001e0ee  mov     ecx, [edi+8]
0x1001e0f1  mov     edx, ebx
0x1001e0f3  push    offset _IID_IIndexDefinition; int
0x1001e0f8  push    eax; unsigned int
0x1001e0f9  mov     ecx, [ecx+10h]
0x1001e0fc  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1001e101  jmp     loc_1001E004
0x1001e106  mov     edx, [eax+14h]
0x1001e109  lea     ecx, [ebp+var_5C]
0x1001e10c  push    ecx; int *
0x1001e10d  push    0; unsigned int
0x1001e10f  lea     ecx, [ebp+var_54]
0x1001e112  push    ecx; unsigned int
0x1001e113  sub     esp, 8
0x1001e116  lea     ecx, [ebp+var_4C]
0x1001e119  push    ecx; unsigned __int16 *
0x1001e11a  mov     ecx, [ebp+var_64]
0x1001e11d  push    0; unsigned int
0x1001e11f  push    dword ptr [ecx+14h]; unsigned int
0x1001e122  mov     ecx, [eax+10h]
0x1001e125  call    ?JOLTJetGetIndexInfo@CJOLT@@SGJKKPBG0PAXKKAAJHAAH@Z; CJOLT::JOLTJetGetIndexInfo(ulong,ulong,ushort const *,ushort const *,void *,ulong,ulong,long &,int,int &)
0x1001e12a  mov     ebx, eax
0x1001e12c  mov     [ebp+var_5C], ebx
0x1001e12f  test    ebx, ebx
0x1001e131  js      short loc_1001E0DE
0x1001e133  cmp     [ebp+var_44], 0
0x1001e137  jz      short loc_1001E0DE
0x1001e139  mov     eax, [edi+8]
0x1001e13c  push    0; grbit
0x1001e13e  push    80000000h; cRow
0x1001e143  push    [ebp+var_48]; tableid
0x1001e146  push    dword ptr [eax+10h]; sesid
0x1001e149  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1001e14f  mov     [ebp+var_54], eax
0x1001e152  test    eax, eax
0x1001e154  jz      short loc_1001E15D
0x1001e156  mov     ebx, 80004005h
0x1001e15b  jmp     short loc_1001E0DE
0x1001e15d  mov     ebx, [ebp+var_44]
0x1001e160  test    ebx, ebx
0x1001e162  jz      short loc_1001E19B
0x1001e164  mov     eax, ebx
0x1001e166  mov     ecx, 2
0x1001e16b  shl     eax, 6
0x1001e16e  add     eax, ebx
0x1001e170  mul     ecx
0x1001e172  mov     ecx, 0FFFFFFFFh
0x1001e177  cmovb   eax, ecx
0x1001e17a  push    eax; Size
0x1001e17b  call    ??2@YAPAXI@Z; operator new(uint)
0x1001e180  mov     edx, eax
0x1001e182  add     esp, 4
0x1001e185  mov     [ebp+Block], edx
0x1001e188  test    edx, edx
0x1001e18a  jnz     short loc_1001E196
0x1001e18c  mov     ebx, 8007000Eh
0x1001e191  jmp     loc_1001E0E0
0x1001e196  mov     ebx, [ebp+var_44]
0x1001e199  jmp     short loc_1001E19D
0x1001e19b  xor     edx, edx
0x1001e19d  xor     edi, edi
0x1001e19f  test    ebx, ebx
0x1001e1a1  jz      loc_1001E251
0x1001e1a7  mov     esi, [ebp+var_68]
0x1001e1aa  nop     word ptr [eax+eax+00h]
0x1001e1b0  push    0; pretinfo
0x1001e1b2  push    0; grbit
0x1001e1b4  lea     eax, [ebp+pcbActual]
0x1001e1b7  push    eax; pcbActual
0x1001e1b8  mov     eax, edi
0x1001e1ba  shl     eax, 6
0x1001e1bd  add     eax, edi
0x1001e1bf  push    82h; cbData
0x1001e1c4  lea     eax, [edx+eax*2]
0x1001e1c7  push    eax; pvData
0x1001e1c8  push    [ebp+columnid]; columnid
0x1001e1cb  mov     eax, [esi+8]
0x1001e1ce  push    [ebp+var_48]; tableid
0x1001e1d1  push    dword ptr [eax+10h]; sesid
0x1001e1d4  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1001e1da  mov     edx, [ebp+var_50]
0x1001e1dd  test    eax, eax
0x1001e1df  mov     eax, [esi+8]
0x1001e1e2  push    0; grbit
0x1001e1e4  push    1; cRow
0x1001e1e6  push    [ebp+var_48]; tableid
0x1001e1e9  lea     ecx, [edx+1]
0x1001e1ec  push    dword ptr [eax+10h]; sesid
0x1001e1ef  cmovz   ecx, edx
0x1001e1f2  mov     [ebp+var_50], ecx
0x1001e1f5  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1001e1fb  mov     [ebp+var_54], eax
0x1001e1fe  cmp     eax, 0FFFFF9BDh
0x1001e203  jnz     short loc_1001E223
0x1001e205  cmp     edi, [ebp+var_44]
0x1001e208  jnb     short loc_1001E223
0x1001e20a  mov     eax, [esi+8]
0x1001e20d  push    0; grbit
0x1001e20f  push    80000000h; cRow
0x1001e214  push    [ebp+var_48]; tableid
0x1001e217  push    dword ptr [eax+10h]; sesid
0x1001e21a  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1001e220  mov     [ebp+var_54], eax
0x1001e223  mov     ecx, [ebp+pcbActual]
0x1001e226  mov     eax, edi
0x1001e228  mov     edx, [ebp+Block]
0x1001e22b  shl     eax, 6
0x1001e22e  add     eax, edi
0x1001e230  shr     ecx, 1
0x1001e232  add     ecx, eax
0x1001e234  inc     edi
0x1001e235  xor     eax, eax
0x1001e237  mov     [edx+ecx*2], ax
0x1001e23b  mov     ebx, [ebp+var_44]
0x1001e23e  cmp     edi, ebx
0x1001e240  jb      loc_1001E1B0
0x1001e246  mov     ecx, [ebp+var_50]
0x1001e249  mov     esi, [ebp+var_60]
0x1001e24c  mov     [ebp+var_50], ecx
0x1001e24f  jmp     short loc_1001E253
0x1001e251  xor     ecx, ecx
0x1001e253  xor     eax, eax
0x1001e255  mov     [ebp+var_64], eax
0x1001e258  test    ebx, ebx
0x1001e25a  jz      loc_1001E2F5
0x1001e260  mov     esi, [ebp+var_68]
0x1001e263  mov     edi, eax
0x1001e265  shl     edi, 6
0x1001e268  add     edi, eax
0x1001e26a  add     edi, edi
0x1001e26c  test    eax, eax
0x1001e26e  jz      short loc_1001E2AF
0x1001e270  lea     eax, [edi+edx]
0x1001e273  lea     ecx, [eax-82h]
0x1001e279  nop     dword ptr [eax+00000000h]
0x1001e280  mov     dx, [eax]
0x1001e283  cmp     dx, [ecx]
0x1001e286  jnz     short loc_1001E2A6
0x1001e288  test    dx, dx
0x1001e28b  jz      short loc_1001E2A2
0x1001e28d  mov     dx, [eax+2]
0x1001e291  cmp     dx, [ecx+2]
0x1001e295  jnz     short loc_1001E2A6
0x1001e297  add     eax, 4
0x1001e29a  add     ecx, 4
0x1001e29d  test    dx, dx
  ... truncated ...
```
