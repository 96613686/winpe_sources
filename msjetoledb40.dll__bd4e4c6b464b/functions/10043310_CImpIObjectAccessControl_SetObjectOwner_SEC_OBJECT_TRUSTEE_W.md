# CImpIObjectAccessControl::SetObjectOwner(_SEC_OBJECT *,_TRUSTEE_W *)

- ea: `0x10043310`
- end: `0x100434e0`
- name: `?SetObjectOwner@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAU_TRUSTEE_W@@@Z`
- size: `464`
- prototype: `int(CImpIObjectAccessControl *__hidden this, struct _SEC_OBJECT *, struct _TRUSTEE_W *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10043310`
- `0x10043840`
- `0x100438b0`
- `0x10044090`
- `0x100440d0`
- `0x10044130`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100434c4`
- `KERNEL32!LeaveCriticalSection` at `0x100434c4`
- `KERNEL32!EnterCriticalSection` at `0x10043358`
- `KERNEL32!EnterCriticalSection` at `0x10043358`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10043345`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10043345`
- `msjet40!__imp__JetSetOwner@20` at `0x1004344d`
- `msjet40!__imp__JetSetOwner@20` at `0x1004344d`

## pseudocode

```c
int __stdcall CImpIObjectAccessControl::SetObjectOwner(
        CImpIObjectAccessControl *this,
        struct _SEC_OBJECT *a2,
        struct _TRUSTEE_W *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  CSecuritySession *v4; // ecx
  int v5; // edi
  CSecuritySession *v6; // ecx
  CSecuritySession *v7; // ecx
  SEC_OBJECT_ELEMENT *prgObjects; // ebx
  const unsigned __int16 *v9; // eax
  const OLECHAR *pwszName; // ecx
  CImpIObjectAccessControl *v11; // ebx
  signed int v12; // eax
  bool v13; // zf
  const struct _GUID *v15; // [esp+0h] [ebp-24h]
  const struct _GUID *v16; // [esp+4h] [ebp-20h]
  unsigned int v17[4]; // [esp+14h] [ebp-10h] BYREF

  v17[0] = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  v17[3] = 0;
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    goto LABEL_37;
  }
  v5 = CSecuritySession::ValidateSecObject(v4, a2);
  if ( v5 >= 0 )
  {
    if ( a2->cObjects != 1 )
    {
      v5 = -2147217811;
      goto LABEL_37;
    }
    v5 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v17);
    if ( v5 < 0 )
      goto LABEL_14;
    v5 = CSecuritySession::CheckForDatabaseDbid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v17);
    if ( v5 < 0 )
      goto LABEL_14;
    if ( !CSecuritySession::fIsValidTrusteeForm(v6, a3) )
    {
      v5 = -2147217814;
LABEL_14:
      v11 = this;
      v12 = v17[0];
      goto LABEL_15;
    }
    prgObjects = a2->prgObjects;
    v9 = CSecuritySession::MapSECOBJECTELEMENTtoContainerName(v7, prgObjects);
    if ( v9 )
    {
      if ( prgObjects->ObjectID.eKind == 2 )
      {
        pwszName = prgObjects->ObjectID.uName.pwszName;
        if ( !pwszName )
          goto LABEL_13;
      }
      else
      {
        pwszName = &word_100046A0;
      }
      if ( *pwszName )
      {
        v17[0] = (unsigned int)v9;
      }
      else
      {
        v17[0] = 0;
        pwszName = v9;
      }
      v11 = this;
      v12 = JetSetOwner(
              *(_DWORD *)(*((_DWORD *)this + 2) + 68),
              *(_DWORD *)(*((_DWORD *)this + 2) + 76),
              v17[0],
              pwszName,
              a3->ptstrName);
      if ( v12 > -1802 )
      {
        if ( v12 == -1305 )
        {
          v5 = -2147217811;
          goto LABEL_15;
        }
        if ( !v12 )
          goto LABEL_34;
      }
      else
      {
        switch ( v12 )
        {
          case -1802:
          case -1907:
            goto LABEL_27;
          case -1903:
            v5 = -2147217808;
            goto LABEL_15;
          case -1809:
LABEL_27:
            v5 = -2147217911;
            goto LABEL_15;
        }
      }
      v13 = v12 == 0;
      if ( v12 >= 0 )
      {
LABEL_16:
        if ( !v13 )
        {
          CExtError::SendJetErrortoOLEAuto(
            v5,
            *(char **)(*((_DWORD *)v11 + 2) + 68),
            v12,
            (int)&IID_IObjectAccessControl,
            (int)v15,
            v16);
          goto LABEL_38;
        }
LABEL_34:
        if ( v5 >= 0 )
          goto LABEL_38;
        goto LABEL_37;
      }
      v5 = -2147467259;
LABEL_15:
      v13 = v12 == 0;
      goto LABEL_16;
    }
LABEL_13:
    v5 = -2147217811;
    goto LABEL_14;
  }
LABEL_37:
  CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_IObjectAccessControl, 0, v15, (int)v16);
LABEL_38:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x10043310  mov     edi, edi
0x10043312  push    ebp
0x10043313  mov     ebp, esp
0x10043315  push    0FFFFFFFFh
0x10043317  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x1004331c  mov     eax, large fs:0
0x10043322  push    eax
0x10043323  sub     esp, 8
0x10043326  push    ebx
0x10043327  push    esi
0x10043328  push    edi; int
0x10043329  mov     eax, ___security_cookie
0x1004332e  xor     eax, ebp
0x10043330  push    eax; struct _GUID *
0x10043331  lea     eax, [ebp+var_C]
0x10043334  mov     large fs:0, eax
0x1004333a  push    0; perrinfo
0x1004333c  push    0; dwReserved
0x1004333e  mov     [ebp+var_10], 0
0x10043345  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004334b  mov     esi, [ebp+this]
0x1004334e  mov     esi, [esi+8]
0x10043351  add     esi, 64h ; 'd'
0x10043354  push    esi; lpCriticalSection
0x10043355  mov     [ebp+var_14], esi
0x10043358  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004335e  mov     ebx, [ebp+arg_4]
0x10043361  mov     [ebp+var_4], 0
0x10043368  test    ebx, ebx
0x1004336a  jz      loc_100434AC
0x10043370  cmp     [ebp+arg_8], 0
0x10043374  jz      loc_100434AC
0x1004337a  push    ebx; struct _SEC_OBJECT *
0x1004337b  call    ?ValidateSecObject@CSecuritySession@@QAEJPAU_SEC_OBJECT@@@Z; CSecuritySession::ValidateSecObject(_SEC_OBJECT *)
0x10043380  mov     edi, eax
0x10043382  test    edi, edi
0x10043384  js      loc_100434B1
0x1004338a  cmp     dword ptr [ebx], 1
0x1004338d  jz      short loc_10043399
0x1004338f  mov     edi, 80040E6Dh
0x10043394  jmp     loc_100434B1
0x10043399  mov     eax, [ebp+this]
0x1004339c  mov     ecx, [eax+8]
0x1004339f  lea     eax, [ebp+var_10]
0x100433a2  add     ecx, 40h ; '@'; this
0x100433a5  push    eax; int *
0x100433a6  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x100433ab  mov     edi, eax
0x100433ad  test    edi, edi
0x100433af  js      short loc_100433FB
0x100433b1  mov     eax, [ebp+this]
0x100433b4  mov     ecx, [eax+8]
0x100433b7  lea     eax, [ebp+var_10]
0x100433ba  add     ecx, 40h ; '@'; this
0x100433bd  push    eax; int *
0x100433be  call    ?CheckForDatabaseDbid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForDatabaseDbid(long &)
0x100433c3  mov     edi, eax
0x100433c5  test    edi, edi
0x100433c7  js      short loc_100433FB
0x100433c9  push    [ebp+arg_8]; struct _TRUSTEE_W *
0x100433cc  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x100433d1  test    eax, eax
0x100433d3  jnz     short loc_100433DC
0x100433d5  mov     edi, 80040E6Ah
0x100433da  jmp     short loc_100433FB
0x100433dc  mov     ebx, [ebx+4]
0x100433df  push    ebx; struct _SEC_OBJECT_ELEMENT *
0x100433e0  call    ?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z; CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)
0x100433e5  test    eax, eax
0x100433e7  jz      short loc_100433F6
0x100433e9  cmp     dword ptr [ebx+20h], 2
0x100433ed  jnz     short loc_10043421
0x100433ef  mov     ecx, [ebx+24h]
0x100433f2  test    ecx, ecx
0x100433f4  jnz     short loc_10043426
0x100433f6  mov     edi, 80040E6Dh
0x100433fb  mov     ebx, [ebp+this]
0x100433fe  mov     eax, [ebp+var_10]
0x10043401  test    eax, eax
0x10043403  jz      loc_100434A6
0x10043409  mov     ecx, [ebx+8]
0x1004340c  mov     edx, edi
0x1004340e  push    offset _IID_IObjectAccessControl; int
0x10043413  push    eax; unsigned int
0x10043414  mov     ecx, [ecx+44h]
0x10043417  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1004341c  jmp     loc_100434BF
0x10043421  mov     ecx, offset word_100046A0
0x10043426  xor     edx, edx
0x10043428  cmp     dx, [ecx]
0x1004342b  jz      short loc_10043432
0x1004342d  mov     [ebp+var_10], eax
0x10043430  jmp     short loc_10043437
0x10043432  mov     [ebp+var_10], edx
0x10043435  mov     ecx, eax
0x10043437  mov     edx, [ebp+arg_8]
0x1004343a  mov     ebx, [ebp+this]
0x1004343d  push    dword ptr [edx+10h]
0x10043440  mov     eax, [ebx+8]
0x10043443  push    ecx
0x10043444  push    [ebp+var_10]
0x10043447  push    dword ptr [eax+4Ch]
0x1004344a  push    dword ptr [eax+44h]
0x1004344d  call    ds:__imp__JetSetOwner@20; JetSetOwner(x,x,x,x,x)
0x10043453  cmp     eax, 0FFFFF8F6h
0x10043458  jg      short loc_1004347F
0x1004345a  jz      short loc_10043471
0x1004345c  cmp     eax, 0FFFFF88Dh
0x10043461  jz      short loc_10043471
0x10043463  cmp     eax, 0FFFFF891h
0x10043468  jz      short loc_10043478
0x1004346a  cmp     eax, 0FFFFF8EFh
0x1004346f  jnz     short loc_1004348A
0x10043471  mov     edi, 80040E09h
0x10043476  jmp     short loc_10043401
0x10043478  mov     edi, 80040E70h
0x1004347d  jmp     short loc_10043401
0x1004347f  cmp     eax, 0FFFFFAE7h
0x10043484  jz      short loc_1004349C
0x10043486  test    eax, eax
0x10043488  jz      short loc_100434A6
0x1004348a  test    eax, eax
0x1004348c  jns     loc_10043403
0x10043492  mov     edi, 80004005h
0x10043497  jmp     loc_10043401
0x1004349c  mov     edi, 80040E6Dh
0x100434a1  jmp     loc_10043401
0x100434a6  test    edi, edi
0x100434a8  jns     short loc_100434BF
0x100434aa  jmp     short loc_100434B1
0x100434ac  mov     edi, 80070057h
0x100434b1  push    0; int
0x100434b3  push    offset _IID_IObjectAccessControl; int
0x100434b8  mov     edx, edi
0x100434ba  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100434bf  test    esi, esi
0x100434c1  jz      short loc_100434CA
0x100434c3  push    esi; lpCriticalSection
0x100434c4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100434ca  mov     eax, edi
0x100434cc  mov     ecx, [ebp+var_C]
0x100434cf  mov     large fs:0, ecx
0x100434d6  pop     ecx
0x100434d7  pop     edi
0x100434d8  pop     esi
0x100434d9  pop     ebx
0x100434da  mov     esp, ebp
0x100434dc  pop     ebp
0x100434dd  retn    0Ch
0x1004dde0  lea     ecx, [ebp+var_14]; this
0x1004dde3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dded  nop
0x1004ddee  nop
0x1004ddef  mov     edx, [esp-4+arg_4]
0x1004ddf3  lea     eax, [edx+0Ch]
0x1004ddf6  mov     ecx, [edx-18h]
0x1004ddf9  xor     ecx, eax; StackCookie
0x1004ddfb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004de00  mov     eax, offset stru_1004F3D8
0x1004de05  jmp     ___CxxFrameHandler3
```
