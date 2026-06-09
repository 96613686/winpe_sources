# CImpIObjectAccessControl::SetObjectAccessRights(_SEC_OBJECT *,ulong,_EXPLICIT_ACCESS_W *)

- ea: `0x10042ed0`
- end: `0x100432f1`
- name: `?SetObjectAccessRights@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@KPAU_EXPLICIT_ACCESS_W@@@Z`
- size: `1057`
- prototype: `int(CImpIObjectAccessControl *__hidden this, struct _SEC_OBJECT *, unsigned int, struct _EXPLICIT_ACCESS_W *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x100198d0`
- `0x1001bdc0`
- `0x1001c380`
- `0x10042ed0`
- `0x10043840`
- `0x10043b80`
- `0x100440d0`
- `0x10044130`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100432d5`
- `KERNEL32!LeaveCriticalSection` at `0x100432d5`
- `KERNEL32!EnterCriticalSection` at `0x10042f29`
- `KERNEL32!EnterCriticalSection` at `0x10042f29`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10042f16`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10042f16`
- `msjet40!__imp__JetGetAccess@32` at `0x10043149`
- `msjet40!__imp__JetGetAccess@32` at `0x10043149`
- `msjet40!__imp__JetSetAccess@28` at `0x100431f3`
- `msjet40!__imp__JetSetAccess@28` at `0x100431f3`

## pseudocode

```c
int __stdcall CImpIObjectAccessControl::SetObjectAccessRights(
        CImpIObjectAccessControl *this,
        struct _SEC_OBJECT *a2,
        unsigned int a3,
        struct _EXPLICIT_ACCESS_W *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  struct _EXPLICIT_ACCESS_W *v5; // ecx
  int v6; // eax
  bool v7; // zf
  struct _EXPLICIT_ACCESS_W *v8; // ebx
  int v9; // edx
  TRUSTEE_TYPE TrusteeType; // eax
  CSecuritySession *v11; // ecx
  SEC_OBJECT_ELEMENT *prgObjects; // edi
  int v13; // ebx
  const GUID *v14; // ecx
  unsigned int v15; // edx
  bool v16; // cf
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int *p_grfAccessPermissions; // edx
  int v20; // ebx
  SEC_OBJECT_ELEMENT *v21; // ecx
  const GUID *v22; // edx
  unsigned int v23; // edi
  const wchar_t *v24; // eax
  const unsigned __int16 *v25; // ecx
  const wchar_t *v26; // edx
  unsigned int *v27; // edi
  unsigned int v28; // eax
  signed int Access; // eax
  unsigned int v30; // ecx
  signed int v31; // eax
  const struct _GUID *v33; // [esp+0h] [ebp-54h]
  const struct _GUID *v34; // [esp+4h] [ebp-50h]
  int v35; // [esp+14h] [ebp-40h]
  LPOLESTR pwszName; // [esp+18h] [ebp-3Ch]
  const wchar_t *v37; // [esp+18h] [ebp-3Ch]
  const unsigned __int16 *v38; // [esp+1Ch] [ebp-38h]
  int v39; // [esp+20h] [ebp-34h]
  unsigned int v40; // [esp+24h] [ebp-30h]
  const unsigned __int16 *v41; // [esp+28h] [ebp-2Ch]
  int v42; // [esp+2Ch] [ebp-28h] BYREF
  int v43; // [esp+30h] [ebp-24h] BYREF
  int v44; // [esp+34h] [ebp-20h]
  unsigned int *v45; // [esp+38h] [ebp-1Ch]
  const wchar_t *v46; // [esp+3Ch] [ebp-18h]
  int v47; // [esp+40h] [ebp-14h]
  unsigned int v48[4]; // [esp+44h] [ebp-10h] BYREF

  v48[0] = 0;
  v46 = &word_100046A0;
  v44 = 0;
  v35 = 0;
  v39 = 0;
  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v4);
  v48[3] = 0;
  if ( !a2 || !a4 )
  {
    v13 = -2147024809;
    goto LABEL_77;
  }
  v47 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v48);
  if ( v47 < 0 )
    goto LABEL_70;
  v5 = (struct _EXPLICIT_ACCESS_W *)*((_DWORD *)this + 2);
  v6 = 0;
  v7 = v5[2].Trustee.pMultipleTrustee == (struct _TRUSTEE_W *)-1;
  v47 = 0;
  if ( v7 )
  {
    v6 = CDataSource::JETOpenDatabase(
           (CDataSource *)v5[2].Trustee.MultipleTrusteeOperation,
           (unsigned int *)&v5[2].grfAccessMode,
           (unsigned int *)&v5[2].Trustee,
           v48,
           0,
           0);
    v47 = v6;
  }
  if ( v6 < 0 )
    goto LABEL_70;
  v8 = a4;
  v9 = 0;
  if ( a3 )
  {
    while ( 2 )
    {
      v5 = &a4[v9];
      if ( (v5->grfInheritance & 0xFFFFFFFE) == 0 )
      {
        switch ( v5->grfAccessMode )
        {
          case GRANT_ACCESS:
          case SET_ACCESS:
          case DENY_ACCESS:
          case REVOKE_ACCESS:
            if ( v5->Trustee.pMultipleTrustee )
              break;
            if ( v5->Trustee.MultipleTrusteeOperation )
              break;
            TrusteeType = v5->Trustee.TrusteeType;
            if ( TrusteeType != TRUSTEE_IS_USER && TrusteeType != TRUSTEE_IS_GROUP )
              break;
            if ( v5->Trustee.TrusteeForm != TRUSTEE_IS_NAME || !v5->Trustee.ptstrName )
              break;
            if ( ++v9 >= a3 )
              goto LABEL_17;
            continue;
          default:
            goto LABEL_20;
        }
      }
      break;
    }
LABEL_20:
    v13 = -2147217809;
    goto LABEL_71;
  }
LABEL_17:
  v47 = CSecuritySession::ValidateSecObject((CSecuritySession *)v5, a2);
  if ( v47 < 0 )
    goto LABEL_70;
  prgObjects = a2->prgObjects;
  v38 = CSecuritySession::MapSECOBJECTELEMENTtoContainerName(v11, prgObjects);
  if ( !v38 )
  {
    v13 = -2147217811;
LABEL_71:
    v18 = v48[0];
    goto LABEL_72;
  }
  v14 = &DBOBJECT_DATABASE;
  v15 = 12;
  while ( v14->Data1 == prgObjects->guidObjectType.Data1 )
  {
    v14 = (const GUID *)((char *)v14 + 4);
    prgObjects = (SEC_OBJECT_ELEMENT *)((char *)prgObjects + 4);
    v16 = v15 < 4;
    v15 -= 4;
    if ( v16 )
    {
      v46 = L"MSysDb";
      break;
    }
  }
  v17 = 0;
  v40 = 0;
  if ( !a3 )
  {
LABEL_70:
    v13 = v47;
    goto LABEL_71;
  }
  v18 = v48[0];
  while ( 1 )
  {
    p_grfAccessPermissions = &v8[v17].grfAccessPermissions;
    v42 = 0;
    v7 = p_grfAccessPermissions[2] == 0;
    v45 = p_grfAccessPermissions;
    v20 = !v7;
    v43 = 0;
    v47 = CSecuritySession::MapAccessMaskToJetACMMask(
            (CSecuritySession *)(5 * a2->cObjects),
            *p_grfAccessPermissions,
            v48,
            &a2->prgObjects[a2->cObjects - 1].guidObjectType);
    if ( v47 < 0 )
    {
      v44 = 1;
      v45[1] = 0;
LABEL_60:
      v8 = a4;
      goto LABEL_61;
    }
    v21 = a2->prgObjects;
    if ( v21->ObjectID.eKind == 2 )
    {
      pwszName = v21->ObjectID.uName.pwszName;
      if ( pwszName )
      {
        v22 = &DBOBJECT_DATABASE;
        v23 = 12;
        while ( v22->Data1 == v21->guidObjectType.Data1 )
        {
          v22 = (const GUID *)((char *)v22 + 4);
          v21 = (SEC_OBJECT_ELEMENT *)((char *)v21 + 4);
          v16 = v23 < 4;
          v23 -= 4;
          if ( v16 )
          {
            v24 = v46;
            goto LABEL_36;
          }
        }
        v24 = pwszName;
LABEL_36:
        v46 = v24;
      }
    }
    if ( *v46 )
    {
      v25 = v38;
      v26 = v46;
      v37 = v46;
    }
    else
    {
      v26 = v38;
      v25 = 0;
      v37 = v38;
    }
    v27 = v45;
    v41 = v25;
    v28 = v45[1];
    if ( v28 == 1 || v28 == 3 )
    {
      Access = JetGetAccess(
                 *(_DWORD *)(*((_DWORD *)this + 2) + 68),
                 *(_DWORD *)(*((_DWORD *)this + 2) + 76),
                 v25,
                 v26,
                 v45[7],
                 1,
                 &v42,
                 &v43);
      v18 = Access;
      if ( Access == -1802 )
        break;
      if ( Access == -1305 )
      {
LABEL_63:
        v13 = -2147217811;
        goto LABEL_65;
      }
      if ( Access < 0 )
      {
        v44 = 1;
        CExtError::SendJetErrortoOLEAuto(Access, (int)&IID_IObjectAccessControl, (int)v33, v34);
        v18 = 0;
        v39 = 1;
        v45[1] = 0;
        goto LABEL_60;
      }
      v27 = v45;
    }
    switch ( v27[1] )
    {
      case 1u:
        v20 |= v43;
        v30 = v42 | v48[0];
        break;
      case 3u:
        v20 = v43 & ~v20;
        v30 = v42 & ~v48[0];
        break;
      case 4u:
        v20 = 0;
        v30 = 0;
        break;
      default:
        v30 = v48[0];
        goto LABEL_55;
    }
    v48[0] = v30;
LABEL_55:
    v31 = JetSetAccess(
            *(_DWORD *)(*((_DWORD *)this + 2) + 68),
            *(_DWORD *)(*((_DWORD *)this + 2) + 76),
            v41,
            v37,
            v27[7],
            v30,
            v20);
    v18 = v31;
    if ( v31 == -1802 )
      break;
    if ( v31 == -1305 )
      goto LABEL_63;
    if ( v31 >= 0 )
    {
      v35 = 1;
      goto LABEL_60;
    }
    v8 = a4;
    a4[v40].grfAccessMode = NOT_USED_ACCESS;
    CExtError::SendJetErrortoOLEAuto(v31, (int)&IID_IObjectAccessControl, (int)v33, v34);
    v18 = 0;
    v39 = 1;
    v44 = 1;
LABEL_61:
    v17 = v40 + 1;
    v40 = v17;
    if ( v17 >= a3 )
    {
      v13 = v47;
      goto LABEL_65;
    }
  }
  v13 = -2147217911;
LABEL_65:
  if ( v44 == 1 )
  {
    v13 = -2147217887;
    if ( v35 == 1 )
      v13 = 265946;
  }
  if ( !v39 )
  {
LABEL_72:
    if ( v18 )
    {
      CExtError::SendJetErrortoOLEAuto(v18, (int)&IID_IObjectAccessControl, (int)v33, v34);
      goto LABEL_78;
    }
    if ( v13 < 0 )
LABEL_77:
      CExtError::SendHRtoOLEAuto((int)&IID_IObjectAccessControl, 0, v33, (int)v34);
  }
LABEL_78:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v13;
}

```

## disassembly

```asm
0x10042ed0  mov     edi, edi
0x10042ed2  push    ebp
0x10042ed3  mov     ebp, esp
0x10042ed5  push    0FFFFFFFFh
0x10042ed7  push    offset ?SetObjectAccessRights@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@KPAU_EXPLICIT_ACCESS_W@@@Z_SEH
0x10042edc  mov     eax, large fs:0
0x10042ee2  push    eax
0x10042ee3  sub     esp, 38h
0x10042ee6  push    ebx
0x10042ee7  push    esi
0x10042ee8  push    edi; int
0x10042ee9  mov     eax, ___security_cookie
0x10042eee  xor     eax, ebp
0x10042ef0  push    eax; struct _GUID *
0x10042ef1  lea     eax, [ebp+var_C]
0x10042ef4  mov     large fs:0, eax
0x10042efa  mov     eax, offset word_100046A0
0x10042eff  mov     [ebp+var_10], 0
0x10042f06  mov     [ebp+var_18], eax
0x10042f09  xor     eax, eax
0x10042f0b  push    eax; perrinfo
0x10042f0c  push    eax; dwReserved
0x10042f0d  mov     [ebp+var_20], eax
0x10042f10  mov     [ebp+var_40], eax
0x10042f13  mov     [ebp+var_34], eax
0x10042f16  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10042f1c  mov     ebx, [ebp+this]
0x10042f1f  mov     esi, [ebx+8]
0x10042f22  add     esi, 64h ; 'd'
0x10042f25  push    esi; lpCriticalSection
0x10042f26  mov     [ebp+var_44], esi
0x10042f29  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10042f2f  mov     edi, [ebp+arg_4]
0x10042f32  mov     [ebp+var_4], 0
0x10042f39  test    edi, edi
0x10042f3b  jz      loc_100432BD
0x10042f41  cmp     [ebp+arg_C], 0
0x10042f45  jz      loc_100432BD
0x10042f4b  mov     ecx, [ebx+8]
0x10042f4e  lea     eax, [ebp+var_10]
0x10042f51  add     ecx, 40h ; '@'; this
0x10042f54  push    eax; int *
0x10042f55  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x10042f5a  mov     [ebp+var_14], eax
0x10042f5d  test    eax, eax
0x10042f5f  js      loc_10043295
0x10042f65  mov     ecx, [ebx+8]
0x10042f68  xor     eax, eax
0x10042f6a  cmp     dword ptr [ecx+4Ch], 0FFFFFFFFh
0x10042f6e  lea     edx, [ecx+4Ch]
0x10042f71  mov     [ebp+var_14], eax
0x10042f74  jnz     short loc_10042F8C
0x10042f76  push    eax; unsigned int *
0x10042f77  push    eax; unsigned __int16 *
0x10042f78  lea     eax, [ebp+var_10]
0x10042f7b  push    eax; int *
0x10042f7c  lea     eax, [ecx+44h]
0x10042f7f  mov     ecx, [ecx+50h]; this
0x10042f82  push    edx; unsigned int *
0x10042f83  push    eax; unsigned int *
0x10042f84  call    ?JETOpenDatabase@CDataSource@@QAEJAAK0AAJPAGPAK@Z; CDataSource::JETOpenDatabase(ulong &,ulong &,long &,ushort *,ulong *)
0x10042f89  mov     [ebp+var_14], eax
0x10042f8c  test    eax, eax
0x10042f8e  js      loc_10043295
0x10042f94  mov     ebx, [ebp+arg_C]
0x10042f97  xor     edx, edx
0x10042f99  cmp     [ebp+arg_8], edx
0x10042f9c  jbe     short loc_10042FEB
0x10042f9e  mov     edi, edi
0x10042fa0  mov     ecx, edx
0x10042fa2  shl     ecx, 5
0x10042fa5  add     ecx, ebx; this
0x10042fa7  test    dword ptr [ecx+8], 0FFFFFFFEh
0x10042fae  jnz     short def_10042FB9; jumptable 10042FB9 default case
0x10042fb0  mov     eax, [ecx+4]
0x10042fb3  dec     eax; switch 4 cases
0x10042fb4  cmp     eax, 3
0x10042fb7  ja      short def_10042FB9; jumptable 10042FB9 default case
0x10042fb9  jmp     ds:jpt_10042FB9[eax*4]; switch jump
0x10042fc0  cmp     dword ptr [ecx+0Ch], 0; jumptable 10042FB9 cases 1-4
0x10042fc4  jnz     short def_10042FB9; jumptable 10042FB9 default case
0x10042fc6  cmp     dword ptr [ecx+10h], 0
0x10042fca  jnz     short def_10042FB9; jumptable 10042FB9 default case
0x10042fcc  mov     eax, [ecx+18h]
0x10042fcf  cmp     eax, 1
0x10042fd2  jz      short loc_10042FD9
0x10042fd4  cmp     eax, 2
0x10042fd7  jnz     short def_10042FB9; jumptable 10042FB9 default case
0x10042fd9  cmp     dword ptr [ecx+14h], 1
0x10042fdd  jnz     short def_10042FB9; jumptable 10042FB9 default case
0x10042fdf  cmp     dword ptr [ecx+1Ch], 0
0x10042fe3  jz      short def_10042FB9; jumptable 10042FB9 default case
0x10042fe5  inc     edx
0x10042fe6  cmp     edx, [ebp+arg_8]
0x10042fe9  jb      short loc_10042FA0
0x10042feb  push    edi; struct _SEC_OBJECT *
0x10042fec  call    ?ValidateSecObject@CSecuritySession@@QAEJPAU_SEC_OBJECT@@@Z; CSecuritySession::ValidateSecObject(_SEC_OBJECT *)
0x10042ff1  mov     [ebp+var_14], eax
0x10042ff4  test    eax, eax
0x10042ff6  js      loc_10043295
0x10042ffc  mov     edi, [edi+4]
0x10042fff  push    edi; struct _SEC_OBJECT_ELEMENT *
0x10043000  call    ?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z; CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)
0x10043005  mov     [ebp+var_38], eax
0x10043008  test    eax, eax
0x1004300a  jnz     short loc_10043020
0x1004300c  mov     ebx, 80040E6Dh
0x10043011  jmp     loc_10043298
0x10043016  mov     ebx, 80040E6Fh; jumptable 10042FB9 default case
0x1004301b  jmp     loc_10043298
0x10043020  mov     ecx, offset _DBOBJECT_DATABASE
0x10043025  mov     edx, 0Ch
0x1004302a  nop     word ptr [eax+eax+00h]
0x10043030  mov     eax, [ecx]
0x10043032  cmp     eax, [edi]
0x10043034  jnz     short loc_10043049
0x10043036  add     ecx, 4
0x10043039  add     edi, 4
0x1004303c  sub     edx, 4
0x1004303f  jnb     short loc_10043030
0x10043041  mov     eax, offset aMsysdb_0; "MSysDb"
0x10043046  mov     [ebp+var_18], eax
0x10043049  xor     eax, eax
0x1004304b  mov     [ebp+var_30], eax
0x1004304e  cmp     [ebp+arg_8], eax
0x10043051  jbe     loc_10043295
0x10043057  mov     edi, [ebp+var_10]
0x1004305a  nop     word ptr [eax+eax+00h]
0x10043060  shl     eax, 5
0x10043063  lea     edx, [eax+ebx]
0x10043066  mov     [ebp+var_28], 0
0x1004306d  mov     eax, [ebp+arg_4]
0x10043070  xor     ebx, ebx
0x10043072  cmp     [edx+8], ebx
0x10043075  mov     [ebp+var_1C], edx
0x10043078  setnz   bl
0x1004307b  mov     [ebp+var_24], 0
0x10043082  mov     eax, [eax]
0x10043084  lea     ecx, [eax+eax*4]; this
0x10043087  mov     eax, [ebp+arg_4]
0x1004308a  mov     eax, [eax+4]
0x1004308d  lea     eax, [eax+ecx*8]
0x10043090  add     eax, 0FFFFFFD8h
0x10043093  push    eax; struct _GUID *
0x10043094  lea     eax, [ebp+var_10]
0x10043097  push    eax; unsigned int *
0x10043098  push    dword ptr [edx]; unsigned int
0x1004309a  call    ?MapAccessMaskToJetACMMask@CSecuritySession@@QAEJKAAKPAU_GUID@@@Z; CSecuritySession::MapAccessMaskToJetACMMask(ulong,ulong &,_GUID *)
0x1004309f  mov     [ebp+var_14], eax
0x100430a2  test    eax, eax
0x100430a4  jns     short loc_100430BC
0x100430a6  mov     eax, [ebp+var_1C]
0x100430a9  mov     [ebp+var_20], 1
0x100430b0  mov     dword ptr [eax+4], 0
0x100430b7  jmp     loc_10043252
0x100430bc  mov     eax, [ebp+arg_4]
0x100430bf  mov     ecx, [eax+4]
0x100430c2  cmp     dword ptr [ecx+20h], 2
0x100430c6  jnz     short loc_100430FC
0x100430c8  mov     eax, [ecx+24h]
0x100430cb  mov     [ebp+var_3C], eax
0x100430ce  test    eax, eax
0x100430d0  jz      short loc_100430FC
0x100430d2  mov     edx, offset _DBOBJECT_DATABASE
0x100430d7  mov     edi, 0Ch
0x100430dc  nop     dword ptr [eax+00h]
0x100430e0  mov     eax, [edx]
0x100430e2  cmp     eax, [ecx]
0x100430e4  jnz     short loc_100430F6
0x100430e6  add     edx, 4
0x100430e9  add     ecx, 4
0x100430ec  sub     edi, 4
0x100430ef  jnb     short loc_100430E0
0x100430f1  mov     eax, [ebp+var_18]
0x100430f4  jmp     short loc_100430F9
0x100430f6  mov     eax, [ebp+var_3C]
0x100430f9  mov     [ebp+var_18], eax
0x100430fc  mov     eax, [ebp+var_18]
0x100430ff  xor     ecx, ecx
0x10043101  cmp     cx, [eax]
0x10043104  jz      short loc_10043110
0x10043106  mov     ecx, [ebp+var_38]
0x10043109  mov     edx, eax
0x1004310b  mov     [ebp+var_3C], eax
0x1004310e  jmp     short loc_10043118
0x10043110  mov     edx, [ebp+var_38]
0x10043113  xor     ecx, ecx
0x10043115  mov     [ebp+var_3C], edx
0x10043118  mov     edi, [ebp+var_1C]
0x1004311b  mov     [ebp+var_2C], ecx
0x1004311e  mov     eax, [edi+4]
0x10043121  cmp     eax, 1
0x10043124  jz      short loc_1004312B
0x10043126  cmp     eax, 3
0x10043129  jnz     short loc_100431A4
0x1004312b  mov     eax, [ebp+this]
0x1004312e  lea     ecx, [ebp+var_24]
0x10043131  push    ecx
0x10043132  lea     ecx, [ebp+var_28]
0x10043135  push    ecx
0x10043136  mov     eax, [eax+8]
0x10043139  mov     ecx, [ebp+var_2C]
0x1004313c  push    1
0x1004313e  push    dword ptr [edi+1Ch]
0x10043141  push    edx
0x10043142  push    ecx
0x10043143  push    dword ptr [eax+4Ch]
0x10043146  push    dword ptr [eax+44h]
0x10043149  call    ds:__imp__JetGetAccess@32; JetGetAccess(x,x,x,x,x,x,x,x)
0x1004314f  mov     edi, eax
0x10043151  cmp     edi, 0FFFFF8F6h
0x10043157  jz      loc_10043271
0x1004315d  cmp     edi, 0FFFFFAE7h
0x10043163  jz      loc_1004326A
0x10043169  test    edi, edi
0x1004316b  jns     short loc_100431A1
0x1004316d  mov     eax, [ebp+this]
0x10043170  mov     edx, 40EDAh
0x10043175  push    offset _IID_IObjectAccessControl; int
0x1004317a  push    edi; unsigned int
0x1004317b  mov     [ebp+var_20], 1
0x10043182  mov     ecx, [eax+8]
0x10043185  mov     ecx, [ecx+44h]
0x10043188  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1004318d  mov     eax, [ebp+var_1C]
0x10043190  xor     edi, edi
0x10043192  mov     [ebp+var_34], 1
0x10043199  mov     [eax+4], edi
0x1004319c  jmp     loc_10043252
0x100431a1  mov     edi, [ebp+var_1C]
0x100431a4  mov     eax, [edi+4]
0x100431a7  sub     eax, 1
0x100431aa  jz      short loc_100431D0
0x100431ac  sub     eax, 2
0x100431af  jz      short loc_100431C1
0x100431b1  sub     eax, 1
0x100431b4  jnz     short loc_100431BC
0x100431b6  xor     ebx, ebx
0x100431b8  xor     ecx, ecx
0x100431ba  jmp     short loc_100431D9
0x100431bc  mov     ecx, [ebp+var_10]
0x100431bf  jmp     short loc_100431DC
0x100431c1  mov     ecx, [ebp+var_10]
0x100431c4  not     ebx
0x100431c6  and     ebx, [ebp+var_24]
0x100431c9  not     ecx
0x100431cb  and     ecx, [ebp+var_28]
0x100431ce  jmp     short loc_100431D9
0x100431d0  mov     ecx, [ebp+var_10]
0x100431d3  or      ebx, [ebp+var_24]
0x100431d6  or      ecx, [ebp+var_28]
0x100431d9  mov     [ebp+var_10], ecx
0x100431dc  mov     eax, [ebp+this]
0x100431df  push    ebx
0x100431e0  push    ecx
0x100431e1  push    dword ptr [edi+1Ch]
0x100431e4  mov     eax, [eax+8]
0x100431e7  push    [ebp+var_3C]
0x100431ea  push    [ebp+var_2C]
0x100431ed  push    dword ptr [eax+4Ch]
0x100431f0  push    dword ptr [eax+44h]
0x100431f3  call    ds:__imp__JetSetAccess@28; JetSetAccess(x,x,x,x,x,x,x)
0x100431f9  mov     edi, eax
0x100431fb  cmp     edi, 0FFFFF8F6h
0x10043201  jz      short loc_10043271
0x10043203  cmp     edi, 0FFFFFAE7h
0x10043209  jz      short loc_1004326A
0x1004320b  test    edi, edi
0x1004320d  jns     short loc_1004324B
0x1004320f  mov     eax, [ebp+var_30]
0x10043212  mov     edx, 40EDAh
0x10043217  mov     ebx, [ebp+arg_C]
0x1004321a  shl     eax, 5
0x1004321d  push    offset _IID_IObjectAccessControl; int
0x10043222  push    edi; unsigned int
0x10043223  mov     dword ptr [eax+ebx+4], 0
0x1004322b  mov     eax, [ebp+this]
0x1004322e  mov     ecx, [eax+8]
0x10043231  mov     ecx, [ecx+44h]
0x10043234  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10043239  xor     edi, edi
0x1004323b  mov     [ebp+var_34], 1
0x10043242  mov     [ebp+var_20], 1
0x10043249  jmp     short loc_10043255
0x1004324b  mov     [ebp+var_40], 1
0x10043252  mov     ebx, [ebp+arg_C]
0x10043255  mov     eax, [ebp+var_30]
0x10043258  inc     eax
0x10043259  mov     [ebp+var_30], eax
0x1004325c  cmp     eax, [ebp+arg_8]
0x1004325f  jb      loc_10043060
0x10043265  mov     ebx, [ebp+var_14]
0x10043268  jmp     short loc_10043276
0x1004326a  mov     ebx, 80040E6Dh
0x1004326f  jmp     short loc_10043276
0x10043271  mov     ebx, 80040E09h
0x10043276  cmp     [ebp+var_20], 1
0x1004327a  jnz     short loc_1004328D
0x1004327c  cmp     [ebp+var_40], 1
0x10043280  mov     ebx, 80040E21h
  ... truncated ...
```
