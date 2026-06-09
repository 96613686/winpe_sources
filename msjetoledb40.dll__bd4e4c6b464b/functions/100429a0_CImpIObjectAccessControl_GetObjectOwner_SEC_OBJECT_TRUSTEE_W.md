# CImpIObjectAccessControl::GetObjectOwner(_SEC_OBJECT *,_TRUSTEE_W * *)

- ea: `0x100429a0`
- end: `0x10042c52`
- name: `?GetObjectOwner@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAPAU_TRUSTEE_W@@@Z`
- size: `690`
- prototype: `int(CImpIObjectAccessControl *__hidden this, struct _SEC_OBJECT *, struct _TRUSTEE_W **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x100429a0`
- `0x10043840`
- `0x100438b0`
- `0x100438f0`
- `0x10043a70`
- `0x10043f20`
- `0x100440d0`
- `0x10044130`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10042c2c`
- `KERNEL32!LeaveCriticalSection` at `0x10042c2c`
- `KERNEL32!EnterCriticalSection` at `0x10042a10`
- `KERNEL32!EnterCriticalSection` at `0x10042a10`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100429fd`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100429fd`
- `msjet40!__imp__JetGetOwner@24` at `0x10042b5f`
- `msjet40!__imp__JetGetOwner@24` at `0x10042b5f`

## pseudocode

```c
int __stdcall CImpIObjectAccessControl::GetObjectOwner(
        CImpIObjectAccessControl *this,
        struct _SEC_OBJECT *a2,
        struct _TRUSTEE_W **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  CSecuritySession *v4; // ecx
  int v5; // edi
  const GUID *v6; // ecx
  unsigned int v7; // edi
  SEC_OBJECT_ELEMENT *prgObjects; // edx
  bool v9; // cf
  CSecuritySession *v10; // ecx
  struct _SEC_OBJECT_ELEMENT *v11; // edi
  const unsigned __int16 *v12; // eax
  const OLECHAR *pwszName; // ecx
  const unsigned __int16 *v14; // edx
  signed int Owner; // eax
  CSecuritySession *v16; // ecx
  const struct _GUID *v18; // [esp+0h] [ebp-B8h]
  const struct _GUID *v19; // [esp+4h] [ebp-B4h]
  int v20; // [esp+14h] [ebp-A4h] BYREF
  struct _SEC_OBJECT *v21; // [esp+18h] [ebp-A0h]
  CImpIObjectAccessControl *v22; // [esp+1Ch] [ebp-9Ch]
  unsigned int v23; // [esp+20h] [ebp-98h] BYREF
  unsigned __int16 v24[66]; // [esp+24h] [ebp-94h] BYREF
  int v25; // [esp+B4h] [ebp-4h]

  v22 = this;
  v21 = a2;
  v23 = 0;
  v20 = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  v25 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    goto LABEL_42;
  }
  v5 = CSecuritySession::ValidateSecObject(v4, a2);
  if ( v5 < 0 )
  {
LABEL_42:
    CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_IObjectAccessControl, 0, v18, (int)v19);
    goto LABEL_43;
  }
  v6 = &DBOBJECT_DATABASE;
  v7 = 12;
  prgObjects = v21->prgObjects;
  while ( v6->Data1 == prgObjects->guidObjectType.Data1 )
  {
    v6 = (const GUID *)((char *)v6 + 4);
    prgObjects = (SEC_OBJECT_ELEMENT *)((char *)prgObjects + 4);
    v9 = v7 < 4;
    v7 -= 4;
    if ( v9 )
    {
      v5 = -2147217810;
      goto LABEL_42;
    }
  }
  if ( v21->cObjects > 1 )
  {
    v5 = -2147217811;
    goto LABEL_42;
  }
  v5 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)v22 + 2) + 64), (int *)&v23);
  if ( v5 >= 0 )
  {
    v5 = CSecuritySession::CheckForSecurityDbid((CSecuritySession *)(*((_DWORD *)v22 + 2) + 64), (int *)&v23, &v20);
    if ( v5 >= 0 )
    {
      v5 = CSecuritySession::CheckForDatabaseDbid((CSecuritySession *)(*((_DWORD *)v22 + 2) + 64), (int *)&v23);
      if ( v5 >= 0 )
      {
        v11 = v21->prgObjects;
        v12 = CSecuritySession::MapSECOBJECTELEMENTtoContainerName(v10, v11);
        if ( !v12 )
        {
LABEL_16:
          v5 = -2147217811;
          goto LABEL_36;
        }
        if ( v11->ObjectID.eKind == 2 )
        {
          pwszName = v11->ObjectID.uName.pwszName;
          if ( !pwszName )
          {
            v5 = -2147217811;
            goto LABEL_36;
          }
        }
        else
        {
          pwszName = &word_100046A0;
        }
        if ( *pwszName )
        {
          v14 = v12;
        }
        else
        {
          v14 = 0;
          pwszName = v12;
        }
        Owner = JetGetOwner(
                  *(_DWORD *)(*((_DWORD *)v22 + 2) + 68),
                  *(_DWORD *)(*((_DWORD *)v22 + 2) + 76),
                  v14,
                  pwszName,
                  v24,
                  64);
        v23 = Owner;
        if ( Owner <= -1305 )
        {
          if ( Owner == -1305 )
            goto LABEL_16;
          if ( Owner == -1907 || Owner == -1809 )
          {
            v5 = -2147217911;
            goto LABEL_36;
          }
          goto LABEL_30;
        }
        if ( Owner < 0 )
        {
LABEL_30:
          v5 = -2147467259;
          goto LABEL_36;
        }
        v5 = CSecuritySession::ConvertStringToTrustee(v16, v24, a3, (enum _TRUSTEE_TYPE)v16);
        if ( v5 >= 0 )
        {
          if ( CSecuritySession::fTrusteeExistsInDataSource(
                 (CSecuritySession *)(*((_DWORD *)v22 + 2) + 64),
                 *a3,
                 (int *)&v23) == -2147217813
            && *a3 )
          {
            (*a3)->TrusteeType = TRUSTEE_IS_GROUP;
          }
          v5 = 0;
          v23 = 0;
        }
      }
    }
LABEL_36:
    if ( v20 )
      goto LABEL_43;
  }
  if ( v23 )
  {
    CExtError::SendJetErrortoOLEAuto(
      v5,
      *(char **)(*((_DWORD *)v22 + 2) + 68),
      v23,
      (int)&IID_IObjectAccessControl,
      (int)v18,
      v19);
    goto LABEL_43;
  }
  if ( v5 < 0 )
    goto LABEL_42;
LABEL_43:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x100429a0  mov     edi, edi
0x100429a2  push    ebp
0x100429a3  mov     ebp, esp
0x100429a5  push    0FFFFFFFFh
0x100429a7  push    offset ?GetObjectOwner@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAPAU_TRUSTEE_W@@@Z_SEH
0x100429ac  mov     eax, large fs:0
0x100429b2  push    eax
0x100429b3  sub     esp, 9Ch
0x100429b9  mov     eax, ___security_cookie
0x100429be  xor     eax, ebp
0x100429c0  mov     [ebp+var_10], eax
0x100429c3  push    ebx
0x100429c4  push    esi
0x100429c5  push    edi; int
0x100429c6  push    eax; struct _GUID *
0x100429c7  lea     eax, [ebp+var_C]
0x100429ca  mov     large fs:0, eax
0x100429d0  mov     esi, [ebp+this]
0x100429d3  mov     edi, [ebp+arg_4]
0x100429d6  mov     ebx, [ebp+arg_8]
0x100429d9  push    0; perrinfo
0x100429db  push    0; dwReserved
0x100429dd  mov     [ebp+var_9C], esi
0x100429e3  mov     [ebp+var_A0], edi
0x100429e9  mov     [ebp+var_98], 0
0x100429f3  mov     [ebp+var_A4], 0
0x100429fd  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10042a03  mov     esi, [esi+8]
0x10042a06  add     esi, 64h ; 'd'
0x10042a09  push    esi; lpCriticalSection
0x10042a0a  mov     [ebp+var_A8], esi
0x10042a10  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10042a16  mov     [ebp+var_4], 0
0x10042a1d  test    ebx, ebx
0x10042a1f  jz      short loc_10042A27
0x10042a21  mov     dword ptr [ebx], 0
0x10042a27  test    edi, edi
0x10042a29  jz      loc_10042C14
0x10042a2f  test    ebx, ebx
0x10042a31  jz      loc_10042C14
0x10042a37  push    edi; struct _SEC_OBJECT *
0x10042a38  call    ?ValidateSecObject@CSecuritySession@@QAEJPAU_SEC_OBJECT@@@Z; CSecuritySession::ValidateSecObject(_SEC_OBJECT *)
0x10042a3d  mov     edi, eax
0x10042a3f  test    edi, edi
0x10042a41  js      loc_10042C19
0x10042a47  mov     edx, [ebp+var_A0]
0x10042a4d  mov     ecx, offset _DBOBJECT_DATABASE
0x10042a52  mov     edi, 0Ch
0x10042a57  mov     edx, [edx+4]
0x10042a5a  nop     word ptr [eax+eax+00h]
0x10042a60  mov     eax, [ecx]
0x10042a62  cmp     eax, [edx]
0x10042a64  jnz     short loc_10042A7B
0x10042a66  add     ecx, 4
0x10042a69  add     edx, 4
0x10042a6c  sub     edi, 4
0x10042a6f  jnb     short loc_10042A60
0x10042a71  mov     edi, 80040E6Eh
0x10042a76  jmp     loc_10042C19
0x10042a7b  mov     eax, [ebp+var_A0]
0x10042a81  cmp     dword ptr [eax], 1
0x10042a84  jbe     short loc_10042A90
0x10042a86  mov     edi, 80040E6Dh
0x10042a8b  jmp     loc_10042C19
0x10042a90  mov     ecx, [ebp+var_9C]
0x10042a96  lea     eax, [ebp+var_98]
0x10042a9c  push    eax; int *
0x10042a9d  mov     ecx, [ecx+8]
0x10042aa0  add     ecx, 40h ; '@'; this
0x10042aa3  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x10042aa8  mov     edi, eax
0x10042aaa  test    edi, edi
0x10042aac  js      loc_10042BE9
0x10042ab2  mov     eax, [ebp+var_9C]
0x10042ab8  mov     ecx, [eax+8]
0x10042abb  lea     eax, [ebp+var_A4]
0x10042ac1  push    eax; int *
0x10042ac2  lea     eax, [ebp+var_98]
0x10042ac8  add     ecx, 40h ; '@'; this
0x10042acb  push    eax; int *
0x10042acc  call    ?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z; CSecuritySession::CheckForSecurityDbid(long &,int &)
0x10042ad1  mov     edi, eax
0x10042ad3  test    edi, edi
0x10042ad5  js      loc_10042BE0
0x10042adb  mov     eax, [ebp+var_9C]
0x10042ae1  mov     ecx, [eax+8]
0x10042ae4  lea     eax, [ebp+var_98]
0x10042aea  add     ecx, 40h ; '@'; this
0x10042aed  push    eax; int *
0x10042aee  call    ?CheckForDatabaseDbid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForDatabaseDbid(long &)
0x10042af3  mov     edi, eax
0x10042af5  test    edi, edi
0x10042af7  js      loc_10042BE0
0x10042afd  mov     eax, [ebp+var_A0]
0x10042b03  mov     edi, [eax+4]
0x10042b06  push    edi; struct _SEC_OBJECT_ELEMENT *
0x10042b07  call    ?MapSECOBJECTELEMENTtoContainerName@CSecuritySession@@QBEPBGAAU_SEC_OBJECT_ELEMENT@@@Z; CSecuritySession::MapSECOBJECTELEMENTtoContainerName(_SEC_OBJECT_ELEMENT &)
0x10042b0c  test    eax, eax
0x10042b0e  jnz     short loc_10042B1A
0x10042b10  mov     edi, 80040E6Dh
0x10042b15  jmp     loc_10042BE0
0x10042b1a  cmp     dword ptr [edi+20h], 2
0x10042b1e  jnz     short loc_10042B31
0x10042b20  mov     ecx, [edi+24h]
0x10042b23  test    ecx, ecx
0x10042b25  jnz     short loc_10042B36
0x10042b27  mov     edi, 80040E6Dh
0x10042b2c  jmp     loc_10042BE0
0x10042b31  mov     ecx, offset word_100046A0
0x10042b36  xor     edx, edx
0x10042b38  cmp     dx, [ecx]
0x10042b3b  jz      short loc_10042B41
0x10042b3d  mov     edx, eax
0x10042b3f  jmp     short loc_10042B45
0x10042b41  xor     edx, edx
0x10042b43  mov     ecx, eax
0x10042b45  mov     eax, [ebp+var_9C]
0x10042b4b  lea     edi, [ebp+var_94]
0x10042b51  push    40h ; '@'
0x10042b53  push    edi
0x10042b54  push    ecx
0x10042b55  mov     eax, [eax+8]
0x10042b58  push    edx
0x10042b59  push    dword ptr [eax+4Ch]
0x10042b5c  push    dword ptr [eax+44h]
0x10042b5f  call    ds:__imp__JetGetOwner@24; JetGetOwner(x,x,x,x,x,x)
0x10042b65  mov     [ebp+var_98], eax
0x10042b6b  cmp     eax, 0FFFFFAE7h
0x10042b70  jg      short loc_10042B89
0x10042b72  jz      short loc_10042B10
0x10042b74  cmp     eax, 0FFFFF88Dh
0x10042b79  jz      short loc_10042B82
0x10042b7b  cmp     eax, 0FFFFF8EFh
0x10042b80  jnz     short loc_10042B8F
0x10042b82  mov     edi, 80040E09h
0x10042b87  jmp     short loc_10042BE0
0x10042b89  test    eax, eax
0x10042b8b  jz      short loc_10042B96
0x10042b8d  jns     short loc_10042B96
0x10042b8f  mov     edi, 80004005h
0x10042b94  jmp     short loc_10042BE0
0x10042b96  push    ecx; enum _TRUSTEE_TYPE
0x10042b97  push    ebx; struct _TRUSTEE_W **
0x10042b98  lea     eax, [ebp+var_94]
0x10042b9e  push    eax; unsigned __int16 *
0x10042b9f  call    ?ConvertStringToTrustee@CSecuritySession@@QAEJPAGPAPAU_TRUSTEE_W@@W4_TRUSTEE_TYPE@@@Z; CSecuritySession::ConvertStringToTrustee(ushort *,_TRUSTEE_W * *,_TRUSTEE_TYPE)
0x10042ba4  mov     edi, eax
0x10042ba6  test    edi, edi
0x10042ba8  js      short loc_10042BE0
0x10042baa  mov     eax, [ebp+var_9C]
0x10042bb0  mov     ecx, [eax+8]
0x10042bb3  lea     eax, [ebp+var_98]
0x10042bb9  push    eax; int *
0x10042bba  push    dword ptr [ebx]; struct _TRUSTEE_W *
0x10042bbc  add     ecx, 40h ; '@'; this
0x10042bbf  call    ?fTrusteeExistsInDataSource@CSecuritySession@@QAEJPAU_TRUSTEE_W@@AAJ@Z; CSecuritySession::fTrusteeExistsInDataSource(_TRUSTEE_W *,long &)
0x10042bc4  cmp     eax, 80040E6Bh
0x10042bc9  jnz     short loc_10042BD8
0x10042bcb  mov     eax, [ebx]
0x10042bcd  test    eax, eax
0x10042bcf  jz      short loc_10042BD8
0x10042bd1  mov     dword ptr [eax+0Ch], 2
0x10042bd8  xor     edi, edi
0x10042bda  mov     [ebp+var_98], edi
0x10042be0  cmp     [ebp+var_A4], 0
0x10042be7  jnz     short loc_10042C27
0x10042be9  mov     eax, [ebp+var_98]
0x10042bef  test    eax, eax
0x10042bf1  jz      short loc_10042C0E
0x10042bf3  push    offset _IID_IObjectAccessControl; int
0x10042bf8  push    eax; unsigned int
0x10042bf9  mov     eax, [ebp+var_9C]
0x10042bff  mov     edx, edi
0x10042c01  mov     ecx, [eax+8]
0x10042c04  mov     ecx, [ecx+44h]
0x10042c07  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10042c0c  jmp     short loc_10042C27
0x10042c0e  test    edi, edi
0x10042c10  jns     short loc_10042C27
0x10042c12  jmp     short loc_10042C19
0x10042c14  mov     edi, 80070057h
0x10042c19  push    0; int
0x10042c1b  push    offset _IID_IObjectAccessControl; int
0x10042c20  mov     edx, edi
0x10042c22  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10042c27  test    esi, esi
0x10042c29  jz      short loc_10042C32
0x10042c2b  push    esi; lpCriticalSection
0x10042c2c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10042c32  mov     eax, edi
0x10042c34  mov     ecx, [ebp+var_C]
0x10042c37  mov     large fs:0, ecx
0x10042c3e  pop     ecx
0x10042c3f  pop     edi
0x10042c40  pop     esi
0x10042c41  pop     ebx
0x10042c42  mov     ecx, [ebp+var_10]
0x10042c45  xor     ecx, ebp; StackCookie
0x10042c47  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10042c4c  mov     esp, ebp
0x10042c4e  pop     ebp
0x10042c4f  retn    0Ch
0x1004f000  lea     ecx, [ebp+var_A8]; this
0x1004f006  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004f010  nop
0x1004f011  nop
0x1004f012  mov     edx, [esp-4+arg_4]
0x1004f016  lea     eax, [edx+0Ch]
0x1004f019  mov     ecx, [edx-0ACh]
0x1004f01f  xor     ecx, eax; StackCookie
0x1004f021  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004f026  mov     ecx, [edx-4]
0x1004f029  xor     ecx, eax; StackCookie
0x1004f02b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004f030  mov     eax, offset stru_10050158
0x1004f035  jmp     ___CxxFrameHandler3
```
