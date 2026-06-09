# CImpIObjectAccessControl::GetObjectAccessRights(_SEC_OBJECT *,ulong *,_EXPLICIT_ACCESS_W * *)

- ea: `0x10042630`
- end: `0x1004298c`
- name: `?GetObjectAccessRights@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAKPAPAU_EXPLICIT_ACCESS_W@@@Z`
- size: `860`
- prototype: `int(CImpIObjectAccessControl *__hidden this, struct _SEC_OBJECT *, unsigned int *, struct _EXPLICIT_ACCESS_W **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10042630`
- `0x10043840`
- `0x100438b0`
- `0x10043d30`
- `0x100440d0`
- `0x10044130`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10042970`
- `KERNEL32!LeaveCriticalSection` at `0x10042970`
- `KERNEL32!EnterCriticalSection` at `0x1004268b`
- `KERNEL32!EnterCriticalSection` at `0x1004268b`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10042678`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10042678`
- `msjet40!__imp__JetGetAccess@32` at `0x10042860`
- `msjet40!__imp__JetGetAccess@32` at `0x10042860`

## pseudocode

```c
int __stdcall CImpIObjectAccessControl::GetObjectAccessRights(
        CImpIObjectAccessControl *this,
        struct _SEC_OBJECT *a2,
        unsigned int *a3,
        struct _EXPLICIT_ACCESS_W **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  int v5; // ebx
  CSecuritySession *v6; // ecx
  CSecuritySession *v7; // ecx
  SEC_OBJECT_ELEMENT *prgObjects; // edi
  unsigned int v9; // edi
  const GUID *v10; // ecx
  unsigned int v11; // edx
  bool v12; // cf
  unsigned int v13; // eax
  struct _EXPLICIT_ACCESS_W **v14; // edx
  unsigned int v15; // ecx
  struct _EXPLICIT_ACCESS_W *v16; // eax
  struct _EXPLICIT_ACCESS_W *v17; // ecx
  TRUSTEE_TYPE TrusteeType; // eax
  const GUID *v19; // ecx
  SEC_OBJECT_ELEMENT *v20; // edx
  unsigned int v21; // edi
  const OLECHAR *v22; // eax
  const unsigned __int16 *v23; // ecx
  const OLECHAR *v24; // edx
  signed int Access; // eax
  const struct _GUID *v27; // [esp+0h] [ebp-48h]
  const struct _GUID *v28; // [esp+4h] [ebp-44h]
  struct _EXPLICIT_ACCESS_W *v29; // [esp+14h] [ebp-34h]
  int v30; // [esp+18h] [ebp-30h]
  int v31; // [esp+1Ch] [ebp-2Ch]
  unsigned int v32; // [esp+20h] [ebp-28h]
  unsigned int v33; // [esp+24h] [ebp-24h]
  int v34; // [esp+28h] [ebp-20h] BYREF
  const unsigned __int16 *v35; // [esp+2Ch] [ebp-1Ch]
  int v36; // [esp+30h] [ebp-18h]
  LPOLESTR pwszName; // [esp+34h] [ebp-14h]
  unsigned int v38[4]; // [esp+38h] [ebp-10h] BYREF

  v38[0] = 0;
  v36 = 0;
  v31 = 0;
  v30 = 0;
  pwszName = (LPOLESTR)&word_100046A0;
  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v4);
  v38[3] = 0;
  if ( a3 && !*a3 && a4 )
    *a4 = 0;
  if ( !a2 || !a3 || !a4 || *a3 && !*a4 )
  {
    v5 = -2147024809;
    goto LABEL_61;
  }
  v5 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v38);
  if ( v5 < 0 )
    goto LABEL_15;
  v5 = CSecuritySession::CheckForDatabaseDbid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v38);
  if ( v5 < 0 )
    goto LABEL_15;
  v5 = CSecuritySession::ValidateSecObject(v6, a2);
  if ( v5 < 0 )
    goto LABEL_15;
  prgObjects = a2->prgObjects;
  v35 = CSecuritySession::MapSECOBJECTELEMENTtoContainerName(v7, prgObjects);
  if ( !v35 )
  {
    v5 = -2147217811;
    goto LABEL_15;
  }
  v10 = &DBOBJECT_DATABASE;
  v11 = 12;
  while ( v10->Data1 == prgObjects->guidObjectType.Data1 )
  {
    v10 = (const GUID *)((char *)v10 + 4);
    prgObjects = (SEC_OBJECT_ELEMENT *)((char *)prgObjects + 4);
    v12 = v11 < 4;
    v11 -= 4;
    if ( v12 )
    {
      pwszName = L"MSysDb";
      break;
    }
  }
  v13 = 0;
  v32 = 0;
  if ( !*a3 )
  {
LABEL_15:
    v9 = v38[0];
    goto LABEL_16;
  }
  v9 = v38[0];
  v14 = a4;
  while ( 1 )
  {
    v15 = v13;
    v38[0] = 0;
    v16 = *v14;
    v34 = 0;
    v33 = v15;
    v16[v15].grfAccessMode = NOT_USED_ACCESS;
    v17 = &(*v14)[v15];
    v29 = v17;
    if ( v17->Trustee.pMultipleTrustee )
      goto LABEL_47;
    if ( v17->Trustee.MultipleTrusteeOperation )
      goto LABEL_47;
    TrusteeType = v17->Trustee.TrusteeType;
    if ( TrusteeType != TRUSTEE_IS_USER && TrusteeType != TRUSTEE_IS_GROUP )
      goto LABEL_47;
    if ( v17->Trustee.TrusteeForm != TRUSTEE_IS_NAME || !v17->Trustee.ptstrName )
      goto LABEL_47;
    if ( a2->prgObjects->ObjectID.eKind == 2 )
    {
      v19 = &DBOBJECT_DATABASE;
      v20 = a2->prgObjects;
      v21 = 12;
      while ( v19->Data1 == v20->guidObjectType.Data1 )
      {
        v19 = (const GUID *)((char *)v19 + 4);
        v20 = (SEC_OBJECT_ELEMENT *)((char *)v20 + 4);
        v12 = v21 < 4;
        v21 -= 4;
        if ( v12 )
          goto LABEL_36;
      }
      pwszName = a2->prgObjects->ObjectID.uName.pwszName;
    }
LABEL_36:
    v22 = &word_100046A0;
    if ( pwszName )
      v22 = pwszName;
    pwszName = (LPOLESTR)v22;
    if ( *v22 )
    {
      v23 = v35;
      v24 = v22;
    }
    else
    {
      v24 = v35;
      v23 = 0;
    }
    Access = JetGetAccess(
               *(_DWORD *)(*((_DWORD *)this + 2) + 68),
               *(_DWORD *)(*((_DWORD *)this + 2) + 76),
               v23,
               v24,
               v29->Trustee.ptstrName,
               1,
               v38,
               &v34);
    v9 = Access;
    if ( Access == -1802 )
      break;
    if ( Access == -1305 )
    {
      v5 = -2147217811;
      goto LABEL_53;
    }
    if ( Access >= 0 )
    {
      v5 = CSecuritySession::MapJetACMMaskToAccessMask(
             (CSecuritySession *)(5 * a2->cObjects),
             v38[0],
             &(*a4)[v33].grfAccessPermissions,
             &a2->prgObjects[a2->cObjects - 1].guidObjectType);
      if ( v5 >= 0 )
      {
        v31 = 1;
        (*a4)[v33].grfInheritance = v34 & 1;
        (*a4)[v33].grfAccessMode = SET_ACCESS;
        v14 = a4;
        goto LABEL_48;
      }
      v14 = a4;
LABEL_47:
      v36 = 1;
      goto LABEL_48;
    }
    v36 = 1;
    CExtError::SendJetErrortoOLEAuto(
      -2147217887,
      *(char **)(*((_DWORD *)this + 2) + 68),
      Access,
      (int)&IID_IObjectAccessControl,
      (int)v27,
      v28);
    v14 = a4;
    v9 = 0;
    v30 = 1;
LABEL_48:
    v13 = v32 + 1;
    v32 = v13;
    if ( v13 >= *a3 )
      goto LABEL_53;
  }
  v5 = -2147217911;
LABEL_53:
  if ( v36 == 1 )
  {
    v5 = -2147217887;
    if ( v31 == 1 )
      v5 = 265946;
  }
  if ( !v30 )
  {
LABEL_16:
    if ( v9 )
    {
      CExtError::SendJetErrortoOLEAuto(
        v5,
        *(char **)(*((_DWORD *)this + 2) + 68),
        v9,
        (int)&IID_IObjectAccessControl,
        (int)v27,
        v28);
      goto LABEL_62;
    }
    if ( v5 < 0 )
LABEL_61:
      CExtError::SendHRtoOLEAuto((int)&IID_IObjectAccessControl, 0, v27, (int)v28);
  }
LABEL_62:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v5;
}

```

## disassembly

```asm
0x10042630  mov     edi, edi
0x10042632  push    ebp
0x10042633  mov     ebp, esp
0x10042635  push    0FFFFFFFFh
0x10042637  push    offset ?GetObjectAccessRights@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAKPAPAU_EXPLICIT_ACCESS_W@@@Z_SEH
0x1004263c  mov     eax, large fs:0
0x10042642  push    eax
0x10042643  sub     esp, 2Ch
0x10042646  push    ebx
0x10042647  push    esi
0x10042648  push    edi; int
0x10042649  mov     eax, ___security_cookie
0x1004264e  xor     eax, ebp
0x10042650  push    eax; struct _GUID *
0x10042651  lea     eax, [ebp+var_C]
0x10042654  mov     large fs:0, eax
0x1004265a  xor     eax, eax
0x1004265c  mov     [ebp+var_10], 0
0x10042663  mov     [ebp+var_18], eax
0x10042666  mov     [ebp+var_2C], eax
0x10042669  mov     [ebp+var_30], eax
0x1004266c  mov     eax, offset word_100046A0
0x10042671  push    0; perrinfo
0x10042673  push    0; dwReserved
0x10042675  mov     [ebp+var_14], eax
0x10042678  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004267e  mov     ebx, [ebp+this]
0x10042681  mov     esi, [ebx+8]
0x10042684  add     esi, 64h ; 'd'
0x10042687  push    esi; lpCriticalSection
0x10042688  mov     [ebp+var_38], esi
0x1004268b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10042691  mov     ecx, [ebp+arg_8]
0x10042694  mov     eax, [ebp+arg_C]
0x10042697  mov     [ebp+var_4], 0
0x1004269e  test    ecx, ecx
0x100426a0  jz      short loc_100426B1
0x100426a2  cmp     dword ptr [ecx], 0
0x100426a5  jnz     short loc_100426B1
0x100426a7  test    eax, eax
0x100426a9  jz      short loc_100426B1
0x100426ab  mov     dword ptr [eax], 0
0x100426b1  mov     edi, [ebp+arg_4]
0x100426b4  test    edi, edi
0x100426b6  jz      loc_10042958
0x100426bc  test    ecx, ecx
0x100426be  jz      loc_10042958
0x100426c4  test    eax, eax
0x100426c6  jz      loc_10042958
0x100426cc  cmp     dword ptr [ecx], 0
0x100426cf  jz      short loc_100426DA
0x100426d1  cmp     dword ptr [eax], 0
0x100426d4  jz      loc_10042958
0x100426da  mov     ecx, [ebx+8]
0x100426dd  lea     eax, [ebp+var_10]
0x100426e0  add     ecx, 40h ; '@'; this
0x100426e3  push    eax; int *
0x100426e4  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x100426e9  mov     ebx, eax
0x100426eb  test    ebx, ebx
0x100426ed  js      short loc_10042728
0x100426ef  mov     ecx, [ebp+this]
0x100426f2  lea     eax, [ebp+var_10]
0x100426f5  push    eax; int *
0x100426f6  mov     ecx, [ecx+8]
0x100426f9  add     ecx, 40h ; '@'; this
0x100426fc  call    ?CheckForDatabaseDbid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForDatabaseDbid(long &)
0x10042701  mov     ebx, eax
0x10042703  test    ebx, ebx
0x10042705  js      short loc_10042728
0x10042707  push    edi; struct _SEC_OBJECT *
0x10042708  call    ?ValidateSecObject@CSecuritySession@@QAEJPAU_SEC_OBJECT@@@Z; CSecuritySession::ValidateSecObject(_SEC_OBJECT *)
0x1004270d  mov     ebx, eax
0x1004270f  test    ebx, ebx
0x10042711  js      short loc_10042728
0x10042713  mov     edi, [edi+4]
0x10042716  push    edi; struct _SEC_OBJECT_ELEMENT *
0x10042717  call    ?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z; CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)
0x1004271c  mov     [ebp+var_1C], eax
0x1004271f  test    eax, eax
0x10042721  jnz     short loc_1004274E
0x10042723  mov     ebx, 80040E6Dh
0x10042728  mov     edi, [ebp+var_10]
0x1004272b  test    edi, edi
0x1004272d  jz      loc_10042952
0x10042733  mov     eax, [ebp+this]
0x10042736  mov     edx, ebx
0x10042738  push    offset _IID_IObjectAccessControl; int
0x1004273d  push    edi; unsigned int
0x1004273e  mov     ecx, [eax+8]
0x10042741  mov     ecx, [ecx+44h]
0x10042744  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10042749  jmp     loc_1004296B
0x1004274e  mov     ecx, offset _DBOBJECT_DATABASE
0x10042753  mov     edx, 0Ch
0x10042758  mov     eax, [ecx]
0x1004275a  cmp     eax, [edi]
0x1004275c  jnz     short loc_10042771
0x1004275e  add     ecx, 4
0x10042761  add     edi, 4
0x10042764  sub     edx, 4
0x10042767  jnb     short loc_10042758
0x10042769  mov     eax, offset aMsysdb_0; "MSysDb"
0x1004276e  mov     [ebp+var_14], eax
0x10042771  mov     ecx, [ebp+arg_8]
0x10042774  xor     eax, eax
0x10042776  mov     [ebp+var_28], eax
0x10042779  cmp     [ecx], eax
0x1004277b  jbe     short loc_10042728
0x1004277d  mov     edi, [ebp+var_10]
0x10042780  mov     edx, [ebp+arg_C]
0x10042783  mov     ecx, eax
0x10042785  mov     [ebp+var_10], 0
0x1004278c  mov     eax, [edx]
0x1004278e  shl     ecx, 5
0x10042791  mov     [ebp+var_20], 0
0x10042798  mov     [ebp+var_24], ecx
0x1004279b  mov     dword ptr [ecx+eax+4], 0
0x100427a3  add     ecx, [edx]
0x100427a5  mov     [ebp+var_34], ecx
0x100427a8  cmp     dword ptr [ecx+0Ch], 0
0x100427ac  jnz     loc_100428DE
0x100427b2  cmp     dword ptr [ecx+10h], 0
0x100427b6  jnz     loc_100428DE
0x100427bc  mov     eax, [ecx+18h]
0x100427bf  cmp     eax, 1
0x100427c2  jz      short loc_100427CD
0x100427c4  cmp     eax, 2
0x100427c7  jnz     loc_100428DE
0x100427cd  cmp     dword ptr [ecx+14h], 1
0x100427d1  jnz     loc_100428DE
0x100427d7  cmp     dword ptr [ecx+1Ch], 0
0x100427db  jz      loc_100428DE
0x100427e1  mov     eax, [ebp+arg_4]
0x100427e4  mov     eax, [eax+4]
0x100427e7  cmp     dword ptr [eax+20h], 2
0x100427eb  jnz     short loc_1004281F
0x100427ed  mov     ecx, offset _DBOBJECT_DATABASE
0x100427f2  mov     edx, eax
0x100427f4  mov     edi, 0Ch
0x100427f9  nop     dword ptr [eax+00000000h]
0x10042800  mov     eax, [ecx]
0x10042802  cmp     eax, [edx]
0x10042804  jnz     short loc_10042813
0x10042806  add     ecx, 4
0x10042809  add     edx, 4
0x1004280c  sub     edi, 4
0x1004280f  jnb     short loc_10042800
0x10042811  jmp     short loc_1004281F
0x10042813  mov     ecx, [ebp+arg_4]
0x10042816  mov     eax, [ecx+4]
0x10042819  mov     eax, [eax+24h]
0x1004281c  mov     [ebp+var_14], eax
0x1004281f  mov     ecx, [ebp+var_14]
0x10042822  mov     eax, offset word_100046A0
0x10042827  test    ecx, ecx
0x10042829  cmovnz  eax, ecx
0x1004282c  xor     ecx, ecx
0x1004282e  mov     [ebp+var_14], eax
0x10042831  cmp     cx, [eax]
0x10042834  jz      short loc_1004283D
0x10042836  mov     ecx, [ebp+var_1C]
0x10042839  mov     edx, eax
0x1004283b  jmp     short loc_10042842
0x1004283d  mov     edx, [ebp+var_1C]
0x10042840  xor     ecx, ecx
0x10042842  mov     eax, [ebp+this]
0x10042845  lea     edi, [ebp+var_20]
0x10042848  push    edi
0x10042849  lea     edi, [ebp+var_10]
0x1004284c  push    edi
0x1004284d  mov     edi, [ebp+var_34]
0x10042850  mov     eax, [eax+8]
0x10042853  push    1
0x10042855  push    dword ptr [edi+1Ch]
0x10042858  push    edx
0x10042859  push    ecx
0x1004285a  push    dword ptr [eax+4Ch]
0x1004285d  push    dword ptr [eax+44h]
0x10042860  call    ds:__imp__JetGetAccess@32; JetGetAccess(x,x,x,x,x,x,x,x)
0x10042866  mov     edi, eax
0x10042868  cmp     edi, 0FFFFF8F6h
0x1004286e  jz      loc_1004292B
0x10042874  cmp     edi, 0FFFFFAE7h
0x1004287a  jz      loc_10042924
0x10042880  test    edi, edi
0x10042882  jns     short loc_100428B2
0x10042884  mov     eax, [ebp+this]
0x10042887  mov     edx, 80040E21h
0x1004288c  push    offset _IID_IObjectAccessControl; int
0x10042891  push    edi; unsigned int
0x10042892  mov     [ebp+var_18], 1
0x10042899  mov     ecx, [eax+8]
0x1004289c  mov     ecx, [ecx+44h]
0x1004289f  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100428a4  mov     edx, [ebp+arg_C]
0x100428a7  xor     edi, edi
0x100428a9  mov     [ebp+var_30], 1
0x100428b0  jmp     short loc_100428E5
0x100428b2  mov     edx, [ebp+arg_4]
0x100428b5  mov     eax, [edx]
0x100428b7  lea     ecx, [eax+eax*4]; this
0x100428ba  mov     eax, [edx+4]
0x100428bd  lea     eax, [eax+ecx*8]
0x100428c0  add     eax, 0FFFFFFD8h
0x100428c3  push    eax; struct _GUID *
0x100428c4  mov     eax, [ebp+arg_C]
0x100428c7  mov     eax, [eax]
0x100428c9  add     eax, [ebp+var_24]
0x100428cc  push    eax; unsigned int *
0x100428cd  push    [ebp+var_10]; unsigned int
0x100428d0  call    ?MapJetACMMaskToAccessMask@CSecuritySession@@QAEJKAAKPAU_GUID@@@Z; CSecuritySession::MapJetACMMaskToAccessMask(ulong,ulong &,_GUID *)
0x100428d5  mov     ebx, eax
0x100428d7  test    ebx, ebx
0x100428d9  jns     short loc_100428F9
0x100428db  mov     edx, [ebp+arg_C]
0x100428de  mov     [ebp+var_18], 1
0x100428e5  mov     eax, [ebp+var_28]
0x100428e8  mov     ecx, [ebp+arg_8]
0x100428eb  inc     eax
0x100428ec  mov     [ebp+var_28], eax
0x100428ef  cmp     eax, [ecx]
0x100428f1  jb      loc_10042783
0x100428f7  jmp     short loc_10042930
0x100428f9  mov     eax, [ebp+arg_C]
0x100428fc  mov     edx, [ebp+var_24]
0x100428ff  mov     ecx, [ebp+var_20]
0x10042902  and     ecx, 1
0x10042905  mov     [ebp+var_2C], 1
0x1004290c  mov     eax, [eax]
0x1004290e  mov     [edx+eax+8], ecx
0x10042912  mov     eax, [ebp+arg_C]
0x10042915  mov     eax, [eax]
0x10042917  mov     dword ptr [edx+eax+4], 2
0x1004291f  mov     edx, [ebp+arg_C]
0x10042922  jmp     short loc_100428E5
0x10042924  mov     ebx, 80040E6Dh
0x10042929  jmp     short loc_10042930
0x1004292b  mov     ebx, 80040E09h
0x10042930  cmp     [ebp+var_18], 1
0x10042934  jnz     short loc_10042947
0x10042936  cmp     [ebp+var_2C], 1
0x1004293a  mov     ebx, 80040E21h
0x1004293f  mov     ecx, 40EDAh
0x10042944  cmovz   ebx, ecx
0x10042947  cmp     [ebp+var_30], 0
0x1004294b  jnz     short loc_1004296B
0x1004294d  jmp     loc_1004272B
0x10042952  test    ebx, ebx
0x10042954  jns     short loc_1004296B
0x10042956  jmp     short loc_1004295D
0x10042958  mov     ebx, 80070057h
0x1004295d  push    0; int
0x1004295f  push    offset _IID_IObjectAccessControl; int
0x10042964  mov     edx, ebx
0x10042966  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1004296b  test    esi, esi
0x1004296d  jz      short loc_10042976
0x1004296f  push    esi; lpCriticalSection
0x10042970  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10042976  mov     eax, ebx
0x10042978  mov     ecx, [ebp+var_C]
0x1004297b  mov     large fs:0, ecx
0x10042982  pop     ecx
0x10042983  pop     edi
0x10042984  pop     esi
0x10042985  pop     ebx
0x10042986  mov     esp, ebp
0x10042988  pop     ebp
0x10042989  retn    10h
0x1004efd0  lea     ecx, [ebp+var_38]; this
0x1004efd3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004efdd  nop
0x1004efde  nop
0x1004efdf  mov     edx, [esp-4+arg_4]
0x1004efe3  lea     eax, [edx+0Ch]
0x1004efe6  mov     ecx, [edx-3Ch]
0x1004efe9  xor     ecx, eax; StackCookie
0x1004efeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004eff0  mov     eax, offset stru_1005012C
0x1004eff5  jmp     ___CxxFrameHandler3
```
