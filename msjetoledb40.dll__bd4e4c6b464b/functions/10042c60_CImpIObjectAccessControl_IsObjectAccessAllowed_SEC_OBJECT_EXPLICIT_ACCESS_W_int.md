# CImpIObjectAccessControl::IsObjectAccessAllowed(_SEC_OBJECT *,_EXPLICIT_ACCESS_W *,int *)

- ea: `0x10042c60`
- end: `0x10042ebd`
- name: `?IsObjectAccessAllowed@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAU_EXPLICIT_ACCESS_W@@PAH@Z`
- size: `605`
- prototype: `int(CImpIObjectAccessControl *__hidden this, struct _SEC_OBJECT *, struct _EXPLICIT_ACCESS_W *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10042c60`
- `0x10043840`
- `0x100438b0`
- `0x10043b80`
- `0x10044090`
- `0x100440d0`
- `0x10044130`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10042ea1`
- `KERNEL32!LeaveCriticalSection` at `0x10042ea1`
- `KERNEL32!EnterCriticalSection` at `0x10042cc2`
- `KERNEL32!EnterCriticalSection` at `0x10042cc2`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10042caf`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10042caf`
- `msjet40!__imp__JetGetAccess@32` at `0x10042e30`
- `msjet40!__imp__JetGetAccess@32` at `0x10042e30`

## pseudocode

```c
int __stdcall CImpIObjectAccessControl::IsObjectAccessAllowed(
        CImpIObjectAccessControl *this,
        struct _SEC_OBJECT *a2,
        struct _EXPLICIT_ACCESS_W *a3,
        int *a4)
{
  const wchar_t *v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // esi
  int v6; // edi
  CSecuritySession *v7; // ecx
  CSecuritySession *v8; // ecx
  unsigned int v9; // edx
  CSecuritySession *v10; // ecx
  int v11; // eax
  SEC_OBJECT_ELEMENT *prgObjects; // eax
  const wchar_t *pwszName; // eax
  const unsigned __int16 *v14; // ecx
  int Access; // eax
  const struct _GUID *v17; // [esp+0h] [ebp-34h]
  const struct _GUID *v18; // [esp+4h] [ebp-30h]
  int v19; // [esp+14h] [ebp-20h] BYREF
  unsigned int v20; // [esp+18h] [ebp-1Ch] BYREF
  int v21; // [esp+1Ch] [ebp-18h] BYREF
  const unsigned __int16 *v22; // [esp+20h] [ebp-14h]
  unsigned int v23[4]; // [esp+24h] [ebp-10h] BYREF

  v23[0] = 0;
  v4 = &word_100046A0;
  v20 = 0;
  v21 = 0;
  v19 = 0;
  SetErrorInfo(0, 0);
  v5 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v5);
  v23[3] = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v6 = -2147024809;
LABEL_38:
    CExtError::SendHRtoOLEAuto((int)&IID_IObjectAccessControl, 0, v17, (int)v18);
    goto LABEL_39;
  }
  v6 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v23);
  if ( v6 < 0 )
    goto LABEL_10;
  v6 = CSecuritySession::CheckForDatabaseDbid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v23);
  if ( v6 < 0 )
    goto LABEL_10;
  if ( !CSecuritySession::fIsValidTrusteeForm(v7, &a3->Trustee) )
  {
    v6 = -2147217807;
LABEL_10:
    v9 = v23[0];
    goto LABEL_11;
  }
  v6 = CSecuritySession::ValidateSecObject(v8, a2);
  if ( v6 < 0 )
    goto LABEL_10;
  v22 = CSecuritySession::MapSECOBJECTELEMENTtoContainerName(v10, a2->prgObjects);
  if ( !v22 )
  {
    v6 = -2147217811;
    goto LABEL_10;
  }
  v6 = CSecuritySession::MapAccessMaskToJetACMMask(
         (CSecuritySession *)a2->prgObjects,
         a3->grfAccessPermissions,
         &v20,
         &a2->prgObjects[a2->cObjects - 1].guidObjectType);
  if ( v6 < 0 )
    goto LABEL_10;
  v11 = wcscmp(L"Databases", v22);
  if ( v11 )
    v11 = v11 < 0 ? -1 : 1;
  if ( v11 )
  {
    prgObjects = a2->prgObjects;
    if ( prgObjects->ObjectID.eKind == 2 )
    {
      pwszName = prgObjects->ObjectID.uName.pwszName;
      v4 = &word_100046A0;
      if ( pwszName )
        v4 = pwszName;
    }
  }
  else
  {
    v4 = L"MSysDb";
  }
  if ( *v4 )
  {
    v14 = v22;
  }
  else
  {
    v4 = v22;
    v14 = 0;
  }
  Access = JetGetAccess(
             *(_DWORD *)(*((_DWORD *)this + 2) + 68),
             *(_DWORD *)(*((_DWORD *)this + 2) + 76),
             v14,
             v4,
             a3->Trustee.ptstrName,
             0,
             &v21,
             &v19);
  v9 = Access;
  if ( Access <= -1305 )
  {
    if ( Access == -1305 )
    {
      v6 = -2147217811;
      goto LABEL_11;
    }
    if ( Access == -1907 || Access == -1802 )
    {
      v6 = -2147217911;
      goto LABEL_11;
    }
  }
  if ( v20 == (v20 & v21) )
    *a4 = 1;
LABEL_11:
  if ( v9 )
  {
    CExtError::SendJetErrortoOLEAuto(
      v6,
      *(char **)(*((_DWORD *)this + 2) + 68),
      v9,
      (int)&IID_IObjectAccessControl,
      (int)v17,
      v18);
    goto LABEL_39;
  }
  if ( v6 < 0 )
    goto LABEL_38;
LABEL_39:
  if ( v5 )
    LeaveCriticalSection(v5);
  return v6;
}

```

## disassembly

```asm
0x10042c60  mov     edi, edi
0x10042c62  push    ebp
0x10042c63  mov     ebp, esp
0x10042c65  push    0FFFFFFFFh
0x10042c67  push    offset ?IsObjectAccessAllowed@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAU_EXPLICIT_ACCESS_W@@PAH@Z_SEH
0x10042c6c  mov     eax, large fs:0
0x10042c72  push    eax
0x10042c73  sub     esp, 18h
0x10042c76  push    ebx
0x10042c77  push    esi
0x10042c78  push    edi; int
0x10042c79  mov     eax, ___security_cookie
0x10042c7e  xor     eax, ebp
0x10042c80  push    eax; struct _GUID *
0x10042c81  lea     eax, [ebp+var_C]
0x10042c84  mov     large fs:0, eax
0x10042c8a  push    0; perrinfo
0x10042c8c  push    0; dwReserved
0x10042c8e  mov     [ebp+var_10], 0
0x10042c95  mov     ebx, offset word_100046A0
0x10042c9a  mov     [ebp+var_1C], 0
0x10042ca1  mov     [ebp+var_18], 0
0x10042ca8  mov     [ebp+var_20], 0
0x10042caf  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10042cb5  mov     edi, [ebp+this]
0x10042cb8  mov     esi, [edi+8]
0x10042cbb  add     esi, 64h ; 'd'
0x10042cbe  push    esi; lpCriticalSection
0x10042cbf  mov     [ebp+var_24], esi
0x10042cc2  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10042cc8  mov     eax, [ebp+arg_C]
0x10042ccb  mov     [ebp+var_4], 0
0x10042cd2  test    eax, eax
0x10042cd4  jz      short loc_10042CDC
0x10042cd6  mov     dword ptr [eax], 0
0x10042cdc  cmp     [ebp+arg_4], 0
0x10042ce0  jz      loc_10042E89
0x10042ce6  cmp     [ebp+arg_8], 0
0x10042cea  jz      loc_10042E89
0x10042cf0  test    eax, eax
0x10042cf2  jz      loc_10042E89
0x10042cf8  mov     ecx, [edi+8]
0x10042cfb  lea     eax, [ebp+var_10]
0x10042cfe  add     ecx, 40h ; '@'; this
0x10042d01  push    eax; int *
0x10042d02  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x10042d07  mov     edi, eax
0x10042d09  test    edi, edi
0x10042d0b  js      short loc_10042D3A
0x10042d0d  mov     ecx, [ebp+this]
0x10042d10  lea     eax, [ebp+var_10]
0x10042d13  push    eax; int *
0x10042d14  mov     ecx, [ecx+8]
0x10042d17  add     ecx, 40h ; '@'; this
0x10042d1a  call    ?CheckForDatabaseDbid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForDatabaseDbid(long &)
0x10042d1f  mov     edi, eax
0x10042d21  test    edi, edi
0x10042d23  js      short loc_10042D3A
0x10042d25  mov     eax, [ebp+arg_8]
0x10042d28  add     eax, 0Ch
0x10042d2b  push    eax; struct _TRUSTEE_W *
0x10042d2c  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x10042d31  test    eax, eax
0x10042d33  jnz     short loc_10042D60
0x10042d35  mov     edi, 80040E71h
0x10042d3a  mov     edx, [ebp+var_10]
0x10042d3d  test    edx, edx
0x10042d3f  jz      loc_10042E83
0x10042d45  mov     eax, [ebp+this]
0x10042d48  push    offset _IID_IObjectAccessControl; int
0x10042d4d  push    edx; unsigned int
0x10042d4e  mov     edx, edi
0x10042d50  mov     ecx, [eax+8]
0x10042d53  mov     ecx, [ecx+44h]
0x10042d56  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10042d5b  jmp     loc_10042E9C
0x10042d60  push    [ebp+arg_4]; struct _SEC_OBJECT *
0x10042d63  call    ?ValidateSecObject@CSecuritySession@@QAEJPAU_SEC_OBJECT@@@Z; CSecuritySession::ValidateSecObject(_SEC_OBJECT *)
0x10042d68  mov     edi, eax
0x10042d6a  test    edi, edi
0x10042d6c  js      short loc_10042D3A
0x10042d6e  mov     edi, [ebp+arg_4]
0x10042d71  push    dword ptr [edi+4]; struct _SEC_OBJECT_ELEMENT *
0x10042d74  call    ?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z; CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)
0x10042d79  mov     [ebp+var_14], eax
0x10042d7c  test    eax, eax
0x10042d7e  jnz     short loc_10042D87
0x10042d80  mov     edi, 80040E6Dh
0x10042d85  jmp     short loc_10042D3A
0x10042d87  mov     eax, [edi]
0x10042d89  mov     ecx, [edi+4]; this
0x10042d8c  lea     eax, [eax+eax*4]
0x10042d8f  lea     eax, [eax-5]
0x10042d92  lea     eax, [ecx+eax*8]
0x10042d95  push    eax; struct _GUID *
0x10042d96  lea     eax, [ebp+var_1C]
0x10042d99  push    eax; unsigned int *
0x10042d9a  mov     eax, [ebp+arg_8]
0x10042d9d  push    dword ptr [eax]; unsigned int
0x10042d9f  call    ?MapAccessMaskToJetACMMask@CSecuritySession@@QAEJKAAKPAU_GUID@@@Z; CSecuritySession::MapAccessMaskToJetACMMask(ulong,ulong &,_GUID *)
0x10042da4  mov     edi, eax
0x10042da6  test    edi, edi
0x10042da8  js      short loc_10042D3A
0x10042daa  mov     ecx, [ebp+var_14]
0x10042dad  mov     eax, offset aDatabases; "Databases"
0x10042db2  mov     dx, [eax]
0x10042db5  cmp     dx, [ecx]
0x10042db8  jnz     short loc_10042DD8
0x10042dba  test    dx, dx
0x10042dbd  jz      short loc_10042DD4
0x10042dbf  mov     dx, [eax+2]
0x10042dc3  cmp     dx, [ecx+2]
0x10042dc7  jnz     short loc_10042DD8
0x10042dc9  add     eax, 4
0x10042dcc  add     ecx, 4
0x10042dcf  test    dx, dx
0x10042dd2  jnz     short loc_10042DB2
0x10042dd4  xor     eax, eax
0x10042dd6  jmp     short loc_10042DDD
0x10042dd8  sbb     eax, eax
0x10042dda  or      eax, 1
0x10042ddd  test    eax, eax
0x10042ddf  jnz     short loc_10042DE8
0x10042de1  mov     ebx, offset aMsysdb_0; "MSysDb"
0x10042de6  jmp     short loc_10042E01
0x10042de8  mov     eax, [ebp+arg_4]
0x10042deb  mov     eax, [eax+4]
0x10042dee  cmp     dword ptr [eax+20h], 2
0x10042df2  jnz     short loc_10042E01
0x10042df4  mov     eax, [eax+24h]
0x10042df7  mov     ebx, offset word_100046A0
0x10042dfc  test    eax, eax
0x10042dfe  cmovnz  ebx, eax
0x10042e01  xor     eax, eax
0x10042e03  cmp     ax, [ebx]
0x10042e06  jz      short loc_10042E0D
0x10042e08  mov     ecx, [ebp+var_14]
0x10042e0b  jmp     short loc_10042E12
0x10042e0d  mov     ebx, [ebp+var_14]
0x10042e10  xor     ecx, ecx
0x10042e12  mov     eax, [ebp+this]
0x10042e15  lea     edx, [ebp+var_20]
0x10042e18  push    edx
0x10042e19  lea     edx, [ebp+var_18]
0x10042e1c  push    edx
0x10042e1d  mov     edx, [ebp+arg_8]
0x10042e20  mov     eax, [eax+8]
0x10042e23  push    0
0x10042e25  push    dword ptr [edx+1Ch]
0x10042e28  push    ebx
0x10042e29  push    ecx
0x10042e2a  push    dword ptr [eax+4Ch]
0x10042e2d  push    dword ptr [eax+44h]
0x10042e30  call    ds:__imp__JetGetAccess@32; JetGetAccess(x,x,x,x,x,x,x,x)
0x10042e36  mov     edx, eax
0x10042e38  cmp     edx, 0FFFFFAE7h
0x10042e3e  jg      short loc_10042E66
0x10042e40  jz      short loc_10042E5C
0x10042e42  cmp     edx, 0FFFFF88Dh
0x10042e48  jz      short loc_10042E52
0x10042e4a  cmp     edx, 0FFFFF8F6h
0x10042e50  jnz     short loc_10042E66
0x10042e52  mov     edi, 80040E09h
0x10042e57  jmp     loc_10042D3D
0x10042e5c  mov     edi, 80040E6Dh
0x10042e61  jmp     loc_10042D3D
0x10042e66  mov     ecx, [ebp+var_18]
0x10042e69  and     ecx, [ebp+var_1C]
0x10042e6c  cmp     [ebp+var_1C], ecx
0x10042e6f  jnz     loc_10042D3D
0x10042e75  mov     eax, [ebp+arg_C]
0x10042e78  mov     dword ptr [eax], 1
0x10042e7e  jmp     loc_10042D3D
0x10042e83  test    edi, edi
0x10042e85  jns     short loc_10042E9C
0x10042e87  jmp     short loc_10042E8E
0x10042e89  mov     edi, 80070057h
0x10042e8e  push    0; int
0x10042e90  push    offset _IID_IObjectAccessControl; int
0x10042e95  mov     edx, edi
0x10042e97  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10042e9c  test    esi, esi
0x10042e9e  jz      short loc_10042EA7
0x10042ea0  push    esi; lpCriticalSection
0x10042ea1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10042ea7  mov     eax, edi
0x10042ea9  mov     ecx, [ebp+var_C]
0x10042eac  mov     large fs:0, ecx
0x10042eb3  pop     ecx
0x10042eb4  pop     edi
0x10042eb5  pop     esi
0x10042eb6  pop     ebx
0x10042eb7  mov     esp, ebp
0x10042eb9  pop     ebp
0x10042eba  retn    10h
0x1004dfd0  lea     ecx, [ebp+var_24]; this
0x1004dfd3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dfdd  nop
0x1004dfde  nop
0x1004dfdf  mov     edx, [esp-4+arg_4]
0x1004dfe3  lea     eax, [edx+0Ch]
0x1004dfe6  mov     ecx, [edx-28h]
0x1004dfe9  xor     ecx, eax; StackCookie
0x1004dfeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dff0  mov     eax, offset stru_1004F550
0x1004dff5  jmp     ___CxxFrameHandler3
```
