# CImpITableDef::DropConstraint(tagDBID *,tagDBID *)

- ea: `0x10044ac0`
- end: `0x10044ed2`
- name: `?DropConstraint@CImpITableDef@@UAGJPAUtagDBID@@0@Z`
- size: `1042`
- prototype: `int(CImpITableDef *__hidden this, struct tagDBID *, struct tagDBID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x1000ba90`
- `0x10016e10`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001e800`
- `0x1001e9d0`
- `0x10044ac0`
- `0x1004d406`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10044c41`
- `msvcrt!_wcsicmp` at `0x10044c41`
- `KERNEL32!LeaveCriticalSection` at `0x10044ea7`
- `KERNEL32!LeaveCriticalSection` at `0x10044ea7`
- `KERNEL32!EnterCriticalSection` at `0x10044b26`
- `KERNEL32!EnterCriticalSection` at `0x10044b26`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10044b13`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10044b13`
- `msjet40!__imp__JetCloseTable@8` at `0x10044e56`
- `msjet40!__imp__JetCloseTable@8` at `0x10044e7e`
- `msjet40!__imp__JetCloseTable@8` at `0x10044e56`
- `msjet40!__imp__JetCloseTable@8` at `0x10044e7e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10044e2d`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10044e2d`
- `msjet40!__imp__JetMove@16` at `0x10044bd0`
- `msjet40!__imp__JetMove@16` at `0x10044c62`
- `msjet40!__imp__JetMove@16` at `0x10044bd0`
- `msjet40!__imp__JetMove@16` at `0x10044c62`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10044c09`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10044c09`
- `msjet40!__imp__JetSetTableProperty@32` at `0x10044d14`
- `msjet40!__imp__JetSetTableProperty@32` at `0x10044d14`
- `msjet40!__imp__JetDeleteRelationship@12` at `0x10044d62`
- `msjet40!__imp__JetDeleteRelationship@12` at `0x10044d62`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x10044b91`
- `msjet40!__imp__JetGetRelationshipInfo@24` at `0x10044b91`

## pseudocode

```c
int __stdcall CImpITableDef::DropConstraint(CImpITableDef *this, struct tagDBID *a2, struct tagDBID *a3)
{
  int v3; // edi
  struct _RTL_CRITICAL_SECTION *v4; // esi
  LPOLESTR pwszName; // ecx
  int RelationshipInfo; // eax
  bool v7; // zf
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  JET_SESID *v13; // ebx
  unsigned int v15; // [esp-14h] [ebp-FCh]
  unsigned __int16 *v16; // [esp-10h] [ebp-F8h]
  struct _GUID *v17; // [esp+0h] [ebp-E8h]
  struct _GUID *v18; // [esp+4h] [ebp-E4h]
  unsigned int pcbActual; // [esp+18h] [ebp-D0h] BYREF
  JET_TABLEID v20; // [esp+1Ch] [ebp-CCh] BYREF
  unsigned int v21; // [esp+20h] [ebp-C8h] BYREF
  struct tagDBID *v22; // [esp+24h] [ebp-C4h]
  _BYTE v23[4]; // [esp+28h] [ebp-C0h] BYREF
  JET_TABLEID tableid; // [esp+2Ch] [ebp-BCh]
  JET_COLUMNID columnid; // [esp+34h] [ebp-B4h]
  wchar_t pvData[66]; // [esp+54h] [ebp-94h] BYREF
  int v27; // [esp+E4h] [ebp-4h]

  v3 = 0;
  v22 = a3;
  v20 = -1;
  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v4);
  v27 = 0;
  tableid = -1;
  if ( !a2 || !v22 )
  {
    v3 = -2147024809;
    goto LABEL_50;
  }
  if ( a2->eKind != 2 || (pwszName = a2->uName.pwszName) == 0 )
  {
    v3 = -2147217865;
    goto LABEL_50;
  }
  if ( v22->eKind != 2 || !v22->uName.ulPropid )
  {
    v3 = -2147217781;
LABEL_50:
    v12 = *((_DWORD *)this + 2);
    v10 = *(_DWORD *)(v12 + 20);
    v11 = *(_DWORD *)(v12 + 16);
LABEL_51:
    if ( !JetGetDatabaseInfo(v11, v10, &pcbActual, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_ITableDefinitionWithConstraints, 0, v17, (int)v18);
    goto LABEL_53;
  }
  RelationshipInfo = JetGetRelationshipInfo(
                       *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                       *(_DWORD *)(*((_DWORD *)this + 2) + 20),
                       pwszName,
                       0,
                       v23,
                       44);
  if ( RelationshipInfo == -1305 || RelationshipInfo == -1001 )
    goto LABEL_16;
  if ( RelationshipInfo < 0 )
  {
LABEL_10:
    v3 = -2147467259;
    goto LABEL_42;
  }
  if ( JetMove(*(_DWORD *)(*((_DWORD *)this + 2) + 16), tableid, 0x80000000, 0) < 0 )
  {
LABEL_16:
    v21 = 0;
    v3 = CJOLT::JOLTJetOpenTable(
           a2->uName.ulPropid,
           v15,
           v16,
           (const void *)2,
           (unsigned int)&v20,
           (unsigned int)&v21,
           &v17->Data1,
           (int *)v18);
    if ( v3 < 0 )
    {
      RelationshipInfo = v21;
      goto LABEL_42;
    }
    v3 = CJOLT::JOLTJetDeleteIndex(v22->uName.ulPropid, (unsigned int)&v21, (const unsigned __int16 *)v17, (int *)v18);
    RelationshipInfo = v21;
    if ( v21 == -1404 || v21 == -1305 || v21 == -1001 )
    {
      v3 = 0;
      RelationshipInfo = JetSetTableProperty(
                           *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                           v20,
                           0,
                           v22->uName.ulPropid,
                           0,
                           0,
                           12,
                           68);
      if ( RelationshipInfo > -1305 )
      {
        if ( RelationshipInfo != -1002 && RelationshipInfo != -1001 )
        {
          if ( RelationshipInfo < 0 )
            v3 = -2147467259;
          goto LABEL_42;
        }
      }
      else if ( RelationshipInfo != -1305 && RelationshipInfo != -3815 && RelationshipInfo != -3600 )
      {
        if ( RelationshipInfo != -1809 )
          goto LABEL_10;
LABEL_25:
        v3 = -2147217911;
        goto LABEL_42;
      }
      v3 = -2147217781;
    }
  }
  else
  {
    while ( 1 )
    {
      RelationshipInfo = JetRetrieveColumn(
                           *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                           tableid,
                           columnid,
                           pvData,
                           0x82u,
                           &pcbActual,
                           0,
                           0);
      if ( RelationshipInfo < 0 )
        goto LABEL_10;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
        __report_rangecheckfailure();
      *(wchar_t *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
      v7 = __wcsicmp(pvData, v22->uName.pwszName) == 0;
      v8 = *((_DWORD *)this + 2);
      if ( v7 )
        break;
      v21 = JetMove(*(_DWORD *)(v8 + 16), tableid, 1, 0);
      if ( (v21 & 0x80000000) != 0 )
        goto LABEL_16;
    }
    RelationshipInfo = JetDeleteRelationship(*(_DWORD *)(v8 + 16), *(_DWORD *)(v8 + 20), v22->uName.ulPropid);
    if ( RelationshipInfo <= -1305 )
    {
      if ( RelationshipInfo == -1305 )
        goto LABEL_16;
      if ( RelationshipInfo != -1907 && RelationshipInfo != -1809 )
      {
        if ( RelationshipInfo == -1404 )
          goto LABEL_16;
LABEL_34:
        if ( RelationshipInfo <= 0 )
          v3 = -2147467259;
        goto LABEL_42;
      }
      goto LABEL_25;
    }
    if ( RelationshipInfo == -1001 )
      goto LABEL_16;
    if ( RelationshipInfo )
      goto LABEL_34;
  }
LABEL_42:
  if ( RelationshipInfo )
  {
    CExtError::SendJetErrortoOLEAuto(RelationshipInfo, (int)&IID_ITableDefinitionWithConstraints, (int)v17, v18);
    goto LABEL_53;
  }
  if ( v3 < 0 )
  {
    v9 = *((_DWORD *)this + 2);
    v10 = *(_DWORD *)(v9 + 20);
    v11 = *(_DWORD *)(v9 + 16);
    if ( v3 != -2147024882 )
      goto LABEL_51;
  }
LABEL_53:
  if ( tableid != -1 )
  {
    JetCloseTable(*(_DWORD *)(*((_DWORD *)this + 2) + 16), tableid);
    tableid = -1;
  }
  pcbActual = v20;
  if ( v20 != -1 )
  {
    v13 = (JET_SESID *)*((_DWORD *)this + 2);
    if ( JetCloseTable(v13[4], v20) == -1108 )
      CDBSession::AddJetTableId((CDBSession *)v13, pcbActual);
    v20 = -1;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return v3;
}

```

## disassembly

```asm
0x10044ac0  mov     edi, edi
0x10044ac2  push    ebp
0x10044ac3  mov     ebp, esp
0x10044ac5  push    0FFFFFFFFh
0x10044ac7  push    offset ?DropConstraint@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x10044acc  mov     eax, large fs:0
0x10044ad2  push    eax
0x10044ad3  sub     esp, 0CCh
0x10044ad9  mov     eax, ___security_cookie
0x10044ade  xor     eax, ebp
0x10044ae0  mov     [ebp+var_10], eax
0x10044ae3  push    ebx
0x10044ae4  push    esi
0x10044ae5  push    edi; int
0x10044ae6  push    eax; struct _GUID *
0x10044ae7  lea     eax, [ebp+var_C]
0x10044aea  mov     large fs:0, eax
0x10044af0  mov     ecx, [ebp+arg_4]
0x10044af3  xor     edi, edi
0x10044af5  mov     eax, [ebp+arg_8]
0x10044af8  mov     ebx, [ebp+this]
0x10044afb  push    edi; perrinfo
0x10044afc  push    edi; dwReserved
0x10044afd  mov     [ebp+var_D4], ecx
0x10044b03  mov     [ebp+var_C4], eax
0x10044b09  mov     [ebp+var_CC], 0FFFFFFFFh
0x10044b13  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10044b19  mov     esi, [ebx+8]
0x10044b1c  add     esi, 68h ; 'h'
0x10044b1f  push    esi; lpCriticalSection
0x10044b20  mov     [ebp+var_D8], esi
0x10044b26  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10044b2c  mov     ecx, [ebp+var_D4]
0x10044b32  mov     [ebp+var_4], edi
0x10044b35  mov     [ebp+tableid], 0FFFFFFFFh
0x10044b3f  test    ecx, ecx
0x10044b41  jz      loc_10044E12
0x10044b47  mov     eax, [ebp+var_C4]
0x10044b4d  test    eax, eax
0x10044b4f  jz      loc_10044E12
0x10044b55  cmp     dword ptr [ecx+10h], 2
0x10044b59  jnz     loc_10044E0B
0x10044b5f  mov     ecx, [ecx+14h]
0x10044b62  test    ecx, ecx
0x10044b64  jz      loc_10044E0B
0x10044b6a  cmp     dword ptr [eax+10h], 2
0x10044b6e  jnz     loc_10044E04
0x10044b74  cmp     [eax+14h], edi
0x10044b77  jz      loc_10044E04
0x10044b7d  mov     eax, [ebx+8]
0x10044b80  lea     edx, [ebp+var_C0]
0x10044b86  push    2Ch ; ','
0x10044b88  push    edx
0x10044b89  push    edi
0x10044b8a  push    ecx
0x10044b8b  push    dword ptr [eax+14h]
0x10044b8e  push    dword ptr [eax+10h]
0x10044b91  call    ds:__imp__JetGetRelationshipInfo@24; JetGetRelationshipInfo(x,x,x,x,x,x)
0x10044b97  cmp     eax, 0FFFFFAE7h
0x10044b9c  jz      loc_10044C76
0x10044ba2  cmp     eax, 0FFFFFC17h
0x10044ba7  jz      loc_10044C76
0x10044bad  test    eax, eax
0x10044baf  jz      short loc_10044BBD
0x10044bb1  jg      short loc_10044BBD
0x10044bb3  mov     edi, 80004005h
0x10044bb8  jmp     loc_10044DD2
0x10044bbd  mov     eax, [ebx+8]
0x10044bc0  push    0; grbit
0x10044bc2  push    80000000h; cRow
0x10044bc7  push    [ebp+tableid]; tableid
0x10044bcd  push    dword ptr [eax+10h]; sesid
0x10044bd0  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10044bd6  test    eax, eax
0x10044bd8  js      loc_10044C76
0x10044bde  mov     edi, edi
0x10044be0  push    0; pretinfo
0x10044be2  push    0; grbit
0x10044be4  lea     eax, [ebp+pcbActual]
0x10044bea  push    eax; pcbActual
0x10044beb  push    82h; cbData
0x10044bf0  lea     eax, [ebp+pvData]
0x10044bf6  push    eax; unsigned int
0x10044bf7  push    [ebp+columnid]; columnid
0x10044bfd  mov     eax, [ebx+8]
0x10044c00  push    [ebp+tableid]; tableid
0x10044c06  push    dword ptr [eax+10h]; sesid
0x10044c09  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10044c0f  test    eax, eax
0x10044c11  js      short loc_10044BB3
0x10044c13  mov     eax, [ebp+pcbActual]
0x10044c19  and     eax, 0FFFFFFFEh
0x10044c1c  cmp     eax, 82h
0x10044c21  jnb     loc_10044ECD
0x10044c27  xor     ecx, ecx
0x10044c29  mov     [ebp+eax+pvData], cx
0x10044c31  mov     eax, [ebp+var_C4]
0x10044c37  push    dword ptr [eax+14h]; String2
0x10044c3a  lea     eax, [ebp+pvData]
0x10044c40  push    eax; String1
0x10044c41  call    ds:__imp___wcsicmp
0x10044c47  add     esp, 8
0x10044c4a  test    eax, eax
0x10044c4c  mov     eax, [ebx+8]
0x10044c4f  jz      loc_10044D53
0x10044c55  push    0; grbit
0x10044c57  push    1; cRow
0x10044c59  push    [ebp+tableid]; tableid
0x10044c5f  push    dword ptr [eax+10h]; unsigned __int16 *
0x10044c62  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10044c68  mov     [ebp+var_C8], eax
0x10044c6e  test    eax, eax
0x10044c70  jns     loc_10044BE0
0x10044c76  mov     eax, [ebx+8]
0x10044c79  lea     ecx, [ebp+var_C8]
0x10044c7f  push    ecx; unsigned int
0x10044c80  lea     ecx, [ebp+var_CC]
0x10044c86  mov     [ebp+var_C8], 0
0x10044c90  push    ecx; unsigned int
0x10044c91  mov     ecx, [ebp+var_D4]
0x10044c97  mov     edx, [eax+14h]
0x10044c9a  push    2; void *
0x10044c9c  sub     esp, 8
0x10044c9f  push    dword ptr [ecx+14h]; unsigned int
0x10044ca2  mov     ecx, [eax+10h]
0x10044ca5  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x10044caa  mov     edi, eax
0x10044cac  test    edi, edi
0x10044cae  js      loc_10044DCC
0x10044cb4  mov     eax, [ebx+8]
0x10044cb7  lea     ecx, [ebp+var_C8]
0x10044cbd  mov     edx, [ebp+var_CC]
0x10044cc3  push    ecx; unsigned int
0x10044cc4  mov     ecx, [ebp+var_C4]
0x10044cca  push    dword ptr [ecx+14h]; unsigned int
0x10044ccd  mov     ecx, [eax+10h]
0x10044cd0  call    ?JOLTJetDeleteIndex@CJOLT@@SGJKKPBGAAJ@Z; CJOLT::JOLTJetDeleteIndex(ulong,ulong,ushort const *,long &)
0x10044cd5  mov     edi, eax
0x10044cd7  mov     eax, [ebp+var_C8]
0x10044cdd  cmp     eax, 0FFFFFA84h
0x10044ce2  jz      short loc_10044CF6
0x10044ce4  cmp     eax, 0FFFFFAE7h
0x10044ce9  jz      short loc_10044CF6
0x10044ceb  cmp     eax, 0FFFFFC17h
0x10044cf0  jnz     loc_10044DD2
0x10044cf6  mov     eax, [ebp+var_C4]
0x10044cfc  xor     edi, edi
0x10044cfe  push    44h ; 'D'
0x10044d00  push    0Ch
0x10044d02  push    edi
0x10044d03  push    edi
0x10044d04  push    dword ptr [eax+14h]
0x10044d07  mov     eax, [ebx+8]
0x10044d0a  push    edi
0x10044d0b  push    [ebp+var_CC]
0x10044d11  push    dword ptr [eax+10h]
0x10044d14  call    ds:__imp__JetSetTableProperty@32; JetSetTableProperty(x,x,x,x,x,x,x,x)
0x10044d1a  cmp     eax, 0FFFFFAE7h
0x10044d1f  jg      loc_10044DAA
0x10044d25  jz      loc_10044DC5
0x10044d2b  cmp     eax, 0FFFFF119h
0x10044d30  jz      loc_10044DC5
0x10044d36  cmp     eax, 0FFFFF1F0h
0x10044d3b  jz      loc_10044DC5
0x10044d41  cmp     eax, 0FFFFF8EFh
0x10044d46  jnz     loc_10044BB3
0x10044d4c  mov     edi, 80040E09h
0x10044d51  jmp     short loc_10044DD2
0x10044d53  mov     ecx, [ebp+var_C4]
0x10044d59  push    dword ptr [ecx+14h]
0x10044d5c  push    dword ptr [eax+14h]
0x10044d5f  push    dword ptr [eax+10h]
0x10044d62  call    ds:__imp__JetDeleteRelationship@12; JetDeleteRelationship(x,x,x)
0x10044d68  cmp     eax, 0FFFFFAE7h
0x10044d6d  jg      short loc_10044D90
0x10044d6f  jz      loc_10044C76
0x10044d75  cmp     eax, 0FFFFF88Dh
0x10044d7a  jz      short loc_10044D4C
0x10044d7c  cmp     eax, 0FFFFF8EFh
0x10044d81  jz      short loc_10044D4C
0x10044d83  cmp     eax, 0FFFFFA84h
0x10044d88  jz      loc_10044C76
0x10044d8e  jmp     short loc_10044D9F
0x10044d90  cmp     eax, 0FFFFFC17h
0x10044d95  jz      loc_10044C76
0x10044d9b  test    eax, eax
0x10044d9d  jz      short loc_10044DD2
0x10044d9f  test    eax, eax
0x10044da1  jg      short loc_10044DD2
0x10044da3  mov     edi, 80004005h
0x10044da8  jmp     short loc_10044DD2
0x10044daa  cmp     eax, 0FFFFFC16h
0x10044daf  jz      short loc_10044DC5
0x10044db1  cmp     eax, 0FFFFFC17h
0x10044db6  jz      short loc_10044DC5
0x10044db8  test    eax, eax
0x10044dba  jz      short loc_10044DD2
0x10044dbc  jg      short loc_10044DD2
0x10044dbe  mov     edi, 80004005h
0x10044dc3  jmp     short loc_10044DD2
0x10044dc5  mov     edi, 80040E8Bh
0x10044dca  jmp     short loc_10044DD2
0x10044dcc  mov     eax, [ebp+var_C8]
0x10044dd2  mov     edx, edi
0x10044dd4  test    eax, eax
0x10044dd6  jz      short loc_10044DEB
0x10044dd8  mov     ecx, [ebx+8]
0x10044ddb  push    offset _IID_ITableDefinitionWithConstraints; int
0x10044de0  push    eax; unsigned int
0x10044de1  mov     ecx, [ecx+10h]
0x10044de4  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10044de9  jmp     short loc_10044E44
0x10044deb  test    edi, edi
0x10044ded  jns     short loc_10044E44
0x10044def  mov     eax, [ebx+8]
0x10044df2  mov     edi, edx
0x10044df4  mov     ecx, [eax+14h]
0x10044df7  mov     eax, [eax+10h]
0x10044dfa  cmp     edx, 8007000Eh
0x10044e00  jz      short loc_10044E44
0x10044e02  jmp     short loc_10044E20
0x10044e04  mov     edi, 80040E8Bh
0x10044e09  jmp     short loc_10044E17
0x10044e0b  mov     edi, 80040E37h
0x10044e10  jmp     short loc_10044E17
0x10044e12  mov     edi, 80070057h
0x10044e17  mov     eax, [ebx+8]
0x10044e1a  mov     ecx, [eax+14h]
0x10044e1d  mov     eax, [eax+10h]
0x10044e20  push    3
0x10044e22  push    4
0x10044e24  lea     edx, [ebp+pcbActual]
0x10044e2a  push    edx
0x10044e2b  push    ecx
0x10044e2c  push    eax
0x10044e2d  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10044e33  test    eax, eax
0x10044e35  jnz     short loc_10044E44
0x10044e37  push    eax; int
0x10044e38  push    offset _IID_ITableDefinitionWithConstraints; int
0x10044e3d  mov     edx, edi
0x10044e3f  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10044e44  mov     eax, [ebp+tableid]
0x10044e4a  cmp     eax, 0FFFFFFFFh
0x10044e4d  jz      short loc_10044E66
0x10044e4f  push    eax; tableid
0x10044e50  mov     eax, [ebx+8]
0x10044e53  push    dword ptr [eax+10h]; sesid
0x10044e56  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10044e5c  mov     [ebp+tableid], 0FFFFFFFFh
0x10044e66  mov     eax, [ebp+var_CC]
0x10044e6c  mov     [ebp+pcbActual], eax
0x10044e72  cmp     eax, 0FFFFFFFFh
0x10044e75  jz      short loc_10044EA2
0x10044e77  mov     ebx, [ebx+8]
0x10044e7a  push    eax; tableid
0x10044e7b  push    dword ptr [ebx+10h]; sesid
0x10044e7e  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10044e84  cmp     eax, 0FFFFFBACh
0x10044e89  jnz     short loc_10044E98
0x10044e8b  push    [ebp+pcbActual]; unsigned int
0x10044e91  mov     ecx, ebx; this
0x10044e93  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x10044e98  mov     [ebp+var_CC], 0FFFFFFFFh
0x10044ea2  test    esi, esi
0x10044ea4  jz      short loc_10044EAD
0x10044ea6  push    esi; lpCriticalSection
0x10044ea7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10044ead  mov     eax, edi
0x10044eaf  mov     ecx, [ebp+var_C]
0x10044eb2  mov     large fs:0, ecx
0x10044eb9  pop     ecx
0x10044eba  pop     edi
0x10044ebb  pop     esi
0x10044ebc  pop     ebx
0x10044ebd  mov     ecx, [ebp+var_10]
0x10044ec0  xor     ecx, ebp; StackCookie
0x10044ec2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10044ec7  mov     esp, ebp
0x10044ec9  pop     ebp
0x10044eca  retn    0Ch
0x10044ecd  call    ___report_rangecheckfailure
0x1004f070  lea     ecx, [ebp+var_D8]; this
0x1004f076  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004f080  nop
0x1004f081  nop
0x1004f082  mov     edx, [esp-4+arg_4]
0x1004f086  lea     eax, [edx+0Ch]
0x1004f089  mov     ecx, [edx-0DCh]
0x1004f08f  xor     ecx, eax; StackCookie
0x1004f091  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004f096  mov     ecx, [edx-4]
0x1004f099  xor     ecx, eax; StackCookie
0x1004f09b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004f0a0  mov     eax, offset stru_100501B0
0x1004f0a5  jmp     ___CxxFrameHandler3
```
