# CImpITrusteeGroupAdmin::GetMemberships(_TRUSTEE_W *,ulong *,_TRUSTEE_W * *)

- ea: `0x10041f50`
- end: `0x1004261b`
- name: `?GetMemberships@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@PAKPAPAU2@@Z`
- size: `1739`
- prototype: `int(CImpITrusteeGroupAdmin *__hidden this, struct _TRUSTEE_W *, unsigned int *, struct _TRUSTEE_W **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000d4a0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001e800`
- `0x1001eb70`
- `0x10041f50`
- `0x10043840`
- `0x100438f0`
- `0x10043ea0`
- `0x10044090`
- `0x1004d406`
- `0x1004d420`
- `0x1004dc8d`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100425f5`
- `KERNEL32!LeaveCriticalSection` at `0x100425f5`
- `KERNEL32!EnterCriticalSection` at `0x10041ff5`
- `KERNEL32!EnterCriticalSection` at `0x10041ff5`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10041fc8`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10041fc8`
- `msjet40!__imp__JetCloseTable@8` at `0x10042544`
- `msjet40!__imp__JetCloseTable@8` at `0x10042544`
- `msjet40!__imp__JetGetNameFromSid@24` at `0x100423ce`
- `msjet40!__imp__JetGetNameFromSid@24` at `0x100423ce`
- `msjet40!__imp__JetMakeKey@20` at `0x10042184`
- `msjet40!__imp__JetMakeKey@20` at `0x10042184`
- `msjet40!__imp__JetMove@16` at `0x100420cd`
- `msjet40!__imp__JetMove@16` at `0x10042267`
- `msjet40!__imp__JetMove@16` at `0x100424a0`
- `msjet40!__imp__JetMove@16` at `0x100420cd`
- `msjet40!__imp__JetMove@16` at `0x10042267`
- `msjet40!__imp__JetMove@16` at `0x100424a0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004239b`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1004239b`
- `msjet40!__imp__JetSeek@12` at `0x100421b7`
- `msjet40!__imp__JetSeek@12` at `0x10042223`
- `msjet40!__imp__JetSeek@12` at `0x100422f1`
- `msjet40!__imp__JetSeek@12` at `0x100421b7`
- `msjet40!__imp__JetSeek@12` at `0x10042223`
- `msjet40!__imp__JetSeek@12` at `0x100422f1`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10042100`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10042100`
- `msjet40!__imp__JetSetIndexRange@12` at `0x100421f3`
- `msjet40!__imp__JetSetIndexRange@12` at `0x100421f3`

## string_xrefs

- `0x100420ef`: `UserSID`
- `0x10042333`: `GroupSID`

## pseudocode

```c
int __stdcall CImpITrusteeGroupAdmin::GetMemberships(
        CImpITrusteeGroupAdmin *this,
        struct _TRUSTEE_W *a2,
        unsigned int *a3,
        struct _TRUSTEE_W **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  CSecuritySession *v5; // ecx
  int SidFromName; // edi
  int Key; // ebx
  CImpITrusteeGroupAdmin *v8; // ebx
  JET_ERR v9; // eax
  JET_ERR v10; // eax
  CImpITrusteeGroupAdmin *v11; // esi
  int v12; // eax
  int (__thiscall *v13)(_DWORD, int, unsigned int); // ecx
  struct _TRUSTEE_W *v14; // eax
  CImpITrusteeGroupAdmin *v15; // edi
  JET_ERR v16; // eax
  CImpITrusteeGroupAdmin *v17; // edi
  struct _TRUSTEE_W **v18; // ecx
  struct _TRUSTEE_W *v19; // eax
  unsigned int v20; // edx
  int v21; // eax
  struct _TRUSTEE_W **v22; // edx
  unsigned int v23; // edi
  unsigned __int16 *v24; // ecx
  CImpITrusteeGroupAdmin *v25; // ebx
  struct _TRUSTEE_W **v26; // ebx
  unsigned int *v27; // edi
  int v28; // eax
  unsigned int v29; // ebx
  struct _TRUSTEE_W **v30; // esi
  unsigned int v32; // [esp-14h] [ebp-4F4h]
  unsigned __int16 *v33; // [esp-10h] [ebp-4F0h]
  unsigned int v34; // [esp-8h] [ebp-4E8h]
  struct _GUID *v35; // [esp+0h] [ebp-4E0h]
  struct _GUID *v36; // [esp+4h] [ebp-4DCh]
  unsigned __int16 *v37; // [esp+14h] [ebp-4CCh]
  unsigned int pcbActual; // [esp+18h] [ebp-4C8h] BYREF
  unsigned int v39; // [esp+1Ch] [ebp-4C4h] BYREF
  unsigned int cbData; // [esp+20h] [ebp-4C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v41; // [esp+24h] [ebp-4BCh]
  int v42; // [esp+28h] [ebp-4B8h] BYREF
  size_t Size; // [esp+2Ch] [ebp-4B4h] BYREF
  struct _TRUSTEE_W **v44; // [esp+30h] [ebp-4B0h]
  unsigned int *v45; // [esp+34h] [ebp-4ACh]
  unsigned int v46; // [esp+38h] [ebp-4A8h]
  unsigned int v47; // [esp+3Ch] [ebp-4A4h] BYREF
  JET_TABLEID tableid; // [esp+40h] [ebp-4A0h] BYREF
  CImpITrusteeGroupAdmin *v49; // [esp+44h] [ebp-49Ch]
  int v50; // [esp+48h] [ebp-498h]
  _BYTE v51[512]; // [esp+4Ch] [ebp-494h] BYREF
  _BYTE pvData[512]; // [esp+24Ch] [ebp-294h] BYREF
  unsigned __int16 v53[66]; // [esp+44Ch] [ebp-94h] BYREF
  int v54; // [esp+4DCh] [ebp-4h]

  v49 = this;
  Size = (size_t)a2;
  v45 = a3;
  v44 = a4;
  v47 = 0;
  v46 = 0;
  tableid = -1;
  v42 = 0;
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  v41 = v4;
  EnterCriticalSection(v4);
  v54 = 0;
  if ( !Size || !v45 || !a4 )
  {
    SidFromName = -2147024809;
    goto LABEL_54;
  }
  if ( !CSecuritySession::fIsValidTrusteeForm(v5, (struct _TRUSTEE_W *)Size) )
  {
    SidFromName = -2147217814;
LABEL_54:
    v50 = SidFromName;
LABEL_55:
    CExtError::SendHRtoOLEAuto((int)&IID_ITrusteeGroupAdmin, 0, v35, (int)v36);
    goto LABEL_56;
  }
  SidFromName = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)&v47);
  v50 = SidFromName;
  if ( SidFromName >= 0 )
  {
    SidFromName = CSecuritySession::CheckForSecurityDbid(
                    (CSecuritySession *)(*((_DWORD *)this + 2) + 64),
                    (int *)&v47,
                    &v42);
    v50 = SidFromName;
    if ( SidFromName >= 0 )
    {
      SidFromName = CJOLT::JOLTJetOpenTable(
                      (unsigned int)L"MSysGroups",
                      v32,
                      v33,
                      (const void *)0x20,
                      (unsigned int)&tableid,
                      (unsigned int)&v47,
                      &v35->Data1,
                      (int *)v36);
      v50 = SidFromName;
      if ( SidFromName >= 0 )
      {
        Key = JetMove(*(_DWORD *)(*((_DWORD *)this + 2) + 68), tableid, 0x80000000, 0);
        if ( Key < 0 )
        {
LABEL_14:
          SidFromName = -2147467259;
          v50 = -2147467259;
          goto LABEL_46;
        }
        Key = JetSetCurrentIndex(*(_DWORD *)(*((_DWORD *)v49 + 2) + 68), tableid, L"UserSID");
        v47 = Key;
        if ( Key < 0 )
        {
          SidFromName = -2147467259;
          v50 = -2147467259;
          goto LABEL_46;
        }
        v8 = v49;
        SidFromName = CJOLT::JOLTJetGetSidFromName(
                        (unsigned int)pvData,
                        (const unsigned __int16 *)&cbData,
                        &cbData,
                        (unsigned int)&v39,
                        &v47,
                        (int *)v35,
                        (int *)v36);
        v50 = SidFromName;
        if ( SidFromName >= 0 )
        {
          Key = JetMakeKey(*(_DWORD *)(*((_DWORD *)v8 + 2) + 68), tableid, pvData, cbData, 1u);
          if ( Key < 0 )
          {
            SidFromName = -2147467259;
            v50 = -2147467259;
            goto LABEL_46;
          }
          v9 = JetSeek(*(_DWORD *)(*((_DWORD *)v49 + 2) + 68), tableid, 0x80u);
          Key = v9;
          if ( v9 == -1601 )
            goto LABEL_44;
          if ( v9 )
          {
            SidFromName = -2147467259;
            v50 = -2147467259;
            goto LABEL_46;
          }
          Key = JetSetIndexRange(*(_DWORD *)(*((_DWORD *)v49 + 2) + 68), tableid, 5u);
          if ( Key < 0 )
          {
            SidFromName = -2147467259;
            v50 = -2147467259;
            goto LABEL_46;
          }
          v10 = JetSeek(*(_DWORD *)(*((_DWORD *)v49 + 2) + 68), tableid, 1u);
          Key = v10;
          if ( v10 == -1601 )
          {
LABEL_44:
            Key = 0;
            goto LABEL_46;
          }
          if ( v10 )
          {
            SidFromName = -2147467259;
            v50 = -2147467259;
            goto LABEL_46;
          }
          v11 = v49;
          do
          {
            v12 = *((_DWORD *)v11 + 2);
            ++v46;
          }
          while ( JetMove(*(_DWORD *)(v12 + 68), tableid, 1, 0) >= 0 );
          Key = 0;
          v13 = *(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12);
          Size = 20 * v46;
          v14 = (struct _TRUSTEE_W *)v13(v13, Sys, 20 * v46);
          v4 = v41;
          *v44 = v14;
          if ( !v14 )
          {
LABEL_31:
            SidFromName = -2147024882;
            v50 = -2147024882;
            goto LABEL_46;
          }
          memset(v14, 0, Size);
          v15 = v49;
          *v45 = v46;
          v16 = JetSeek(*(_DWORD *)(*((_DWORD *)v15 + 2) + 68), tableid, 1u);
          Key = v16;
          v47 = v16;
          if ( v16 == -1601 )
          {
            SidFromName = v50;
            Key = 0;
            goto LABEL_46;
          }
          if ( v16 )
          {
            SidFromName = -2147467259;
            v50 = -2147467259;
            goto LABEL_46;
          }
          SidFromName = CSecuritySession::FindColid(
                          (CSecuritySession *)(*((_DWORD *)v15 + 2) + 64),
                          tableid,
                          L"GroupSID",
                          &Size,
                          (int *)&v47);
          v50 = SidFromName;
          if ( SidFromName >= 0 )
          {
            v46 = 0;
            if ( *v45 )
            {
              v17 = v49;
              while ( 1 )
              {
                Key = JetRetrieveColumn(
                        *(_DWORD *)(*((_DWORD *)v17 + 2) + 68),
                        tableid,
                        Size,
                        v51,
                        0x1FFu,
                        &pcbActual,
                        0,
                        0);
                if ( Key < 0 )
                  goto LABEL_14;
                Key = JetGetNameFromSid(*(_DWORD *)(*((_DWORD *)v17 + 2) + 68), v51, pcbActual, v53, 64, &v39);
                if ( Key < 0 )
                  goto LABEL_14;
                v18 = v44;
                v19 = *v44;
                v20 = v46;
                v47 = v20 * 20;
                v19[v20].pMultipleTrustee = 0;
                (*v18)[v20].MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
                (*v18)[v20].TrusteeForm = TRUSTEE_IS_NAME;
                (*v18)[v20].TrusteeType = TRUSTEE_IS_GROUP;
                v37 = (unsigned __int16 *)(2 * wcslen(v53) + 2);
                v21 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
                        *(_DWORD *)(*(_DWORD *)Sys + 12),
                        Sys,
                        v37);
                v22 = v44;
                v23 = v47;
                *(LPWCH *)((char *)&(*v44)->ptstrName + v47) = (LPWCH)v21;
                v24 = *(LPWCH *)((char *)&(*v22)->ptstrName + v23);
                if ( !v24 )
                  goto LABEL_31;
                WCSCPY(v53, v24, v37, (const unsigned __int16 *)v35, (unsigned int)v36);
                v17 = v49;
                JetMove(*(_DWORD *)(*((_DWORD *)v49 + 2) + 68), tableid, 1, 0);
                if ( ++v46 >= *v45 )
                {
                  SidFromName = v50;
                  goto LABEL_46;
                }
              }
            }
          }
        }
      }
    }
    Key = v47;
LABEL_46:
    if ( v42 )
      goto LABEL_56;
    goto LABEL_49;
  }
  Key = v47;
LABEL_49:
  if ( Key )
  {
    v34 = Key;
    v25 = v49;
    CExtError::SendJetErrortoOLEAuto(v34, (int)&IID_ITrusteeGroupAdmin, (int)v35, v36);
    goto LABEL_57;
  }
  if ( SidFromName < 0 )
    goto LABEL_55;
LABEL_56:
  v25 = v49;
LABEL_57:
  if ( tableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v25 + 2) + 68), tableid);
  if ( SidFromName < 0 )
  {
    v26 = v44;
    if ( v44 )
    {
      if ( *v44 )
      {
        v27 = v45;
        if ( v45 && *v45 )
        {
          v28 = Sys;
          v29 = 0;
          v30 = v44;
          do
          {
            if ( (*v30)[v29].ptstrName && v28 )
            {
              (*(void (__thiscall **)(_DWORD, int, LPWCH))(*(_DWORD *)v28 + 20))(
                *(_DWORD *)(*(_DWORD *)v28 + 20),
                v28,
                (*v30)[v29].ptstrName);
              v28 = Sys;
              v27 = v45;
            }
            ++v29;
          }
          while ( v29 < *v27 );
          v4 = v41;
          v26 = v44;
          *v27 = 0;
        }
        if ( Sys )
          (*(void (__thiscall **)(_DWORD, int, struct _TRUSTEE_W *))(*(_DWORD *)Sys + 20))(
            *(_DWORD *)(*(_DWORD *)Sys + 20),
            Sys,
            *v26);
        SidFromName = v50;
        *v26 = 0;
      }
    }
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return SidFromName;
}

```

## disassembly

```asm
0x10041f50  mov     edi, edi
0x10041f52  push    ebp
0x10041f53  mov     ebp, esp
0x10041f55  push    0FFFFFFFFh
0x10041f57  push    offset ?GetMemberships@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@PAKPAPAU2@@Z_SEH
0x10041f5c  mov     eax, large fs:0
0x10041f62  push    eax
0x10041f63  sub     esp, 4C4h
0x10041f69  mov     eax, ___security_cookie
0x10041f6e  xor     eax, ebp
0x10041f70  mov     [ebp+var_10], eax
0x10041f73  push    ebx
0x10041f74  push    esi
0x10041f75  push    edi; int
0x10041f76  push    eax; struct _GUID *
0x10041f77  lea     eax, [ebp+var_C]
0x10041f7a  mov     large fs:0, eax
0x10041f80  mov     edx, [ebp+arg_4]
0x10041f83  xor     ecx, ecx
0x10041f85  mov     ebx, [ebp+this]
0x10041f88  mov     esi, [ebp+arg_8]
0x10041f8b  mov     edi, [ebp+arg_C]
0x10041f8e  push    ecx; perrinfo
0x10041f8f  push    ecx; dwReserved
0x10041f90  mov     [ebp+var_49C], ebx
0x10041f96  mov     [ebp+Size], edx
0x10041f9c  mov     [ebp+var_4AC], esi
0x10041fa2  mov     [ebp+var_4B0], edi
0x10041fa8  mov     [ebp+var_4A4], 0
0x10041fb2  mov     [ebp+var_4A8], ecx
0x10041fb8  mov     [ebp+tableid], 0FFFFFFFFh
0x10041fc2  mov     [ebp+var_4B8], ecx
0x10041fc8  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10041fce  test    esi, esi
0x10041fd0  jz      short loc_10041FD8
0x10041fd2  mov     dword ptr [esi], 0
0x10041fd8  test    edi, edi
0x10041fda  jz      short loc_10041FE2
0x10041fdc  mov     dword ptr [edi], 0
0x10041fe2  mov     esi, [ebx+8]
0x10041fe5  add     esi, 64h ; 'd'
0x10041fe8  push    esi; lpCriticalSection
0x10041fe9  mov     [ebp+var_4BC], esi
0x10041fef  mov     [ebp+var_4D0], esi
0x10041ff5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10041ffb  mov     [ebp+var_4], 0
0x10042002  mov     eax, [ebp+Size]
0x10042008  test    eax, eax
0x1004200a  jz      loc_10042513
0x10042010  cmp     [ebp+var_4AC], 0
0x10042017  jz      loc_10042513
0x1004201d  test    edi, edi
0x1004201f  jz      loc_10042513
0x10042025  push    eax; struct _TRUSTEE_W *
0x10042026  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x1004202b  test    eax, eax
0x1004202d  jnz     short loc_10042039
0x1004202f  mov     edi, 80040E6Ah
0x10042034  jmp     loc_10042518
0x10042039  mov     ecx, [ebx+8]
0x1004203c  lea     eax, [ebp+var_4A4]
0x10042042  add     ecx, 40h ; '@'; this
0x10042045  push    eax; int *
0x10042046  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x1004204b  mov     edi, eax
0x1004204d  mov     [ebp+var_498], edi
0x10042053  test    edi, edi
0x10042055  js      loc_100424E8
0x1004205b  mov     ecx, [ebx+8]
0x1004205e  lea     eax, [ebp+var_4B8]
0x10042064  push    eax; int *
0x10042065  lea     eax, [ebp+var_4A4]
0x1004206b  add     ecx, 40h ; '@'; this
0x1004206e  push    eax; int *
0x1004206f  call    ?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z; CSecuritySession::CheckForSecurityDbid(long &,int &)
0x10042074  mov     edi, eax
0x10042076  mov     [ebp+var_498], edi
0x1004207c  test    edi, edi
0x1004207e  js      loc_100424D7
0x10042084  mov     eax, [ebx+8]
0x10042087  lea     ecx, [ebp+var_4A4]
0x1004208d  push    ecx; unsigned int
0x1004208e  lea     ecx, [ebp+tableid]
0x10042094  push    ecx; unsigned int
0x10042095  mov     edx, [eax+48h]
0x10042098  mov     ecx, [eax+44h]
0x1004209b  push    20h ; ' '; void *
0x1004209d  sub     esp, 8
0x100420a0  push    offset aMsysgroups; "MSysGroups"
0x100420a5  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x100420aa  mov     edi, eax
0x100420ac  mov     [ebp+var_498], eax
0x100420b2  test    edi, edi
0x100420b4  js      loc_100424D7
0x100420ba  mov     eax, [ebx+8]
0x100420bd  push    0; grbit
0x100420bf  push    80000000h; cRow
0x100420c4  push    [ebp+tableid]; tableid
0x100420ca  push    dword ptr [eax+44h]; sesid
0x100420cd  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x100420d3  mov     ebx, eax
0x100420d5  test    ebx, ebx
0x100420d7  jns     short loc_100420E9
0x100420d9  mov     edi, 80004005h
0x100420de  mov     [ebp+var_498], edi
0x100420e4  jmp     loc_100424DD
0x100420e9  mov     eax, [ebp+var_49C]
0x100420ef  push    offset aUsersid; "UserSID"
0x100420f4  push    [ebp+tableid]
0x100420fa  mov     eax, [eax+8]
0x100420fd  push    dword ptr [eax+44h]
0x10042100  call    ds:__imp__JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x10042106  mov     ebx, eax
0x10042108  mov     [ebp+var_4A4], ebx
0x1004210e  test    ebx, ebx
0x10042110  jns     short loc_10042122
0x10042112  mov     edi, 80004005h
0x10042117  mov     [ebp+var_498], edi
0x1004211d  jmp     loc_100424DD
0x10042122  mov     ebx, [ebp+var_49C]
0x10042128  lea     ecx, [ebp+var_4A4]
0x1004212e  mov     edx, [ebp+Size]
0x10042134  push    ecx; unsigned int *
0x10042135  lea     ecx, [ebp+var_4C4]
0x1004213b  mov     eax, [ebx+8]
0x1004213e  mov     edx, [edx+10h]
0x10042141  push    ecx; unsigned int
0x10042142  lea     ecx, [ebp+cbData]
0x10042148  push    ecx; void *
0x10042149  push    ecx; unsigned __int16 *
0x1004214a  lea     ecx, [ebp+pvData]
0x10042150  push    ecx; unsigned int
0x10042151  mov     ecx, [eax+44h]
0x10042154  call    ?JOLTJetGetSidFromName@CJOLT@@SGJKPBGPAXKPAKPAJAAJ@Z; CJOLT::JOLTJetGetSidFromName(ulong,ushort const *,void *,ulong,ulong *,long *,long &)
0x10042159  mov     edi, eax
0x1004215b  mov     [ebp+var_498], edi
0x10042161  test    edi, edi
0x10042163  js      loc_100424D7
0x10042169  push    1; grbit
0x1004216b  push    [ebp+cbData]; cbData
0x10042171  lea     eax, [ebp+pvData]
0x10042177  push    eax; pvData
0x10042178  mov     eax, [ebx+8]
0x1004217b  push    [ebp+tableid]; tableid
0x10042181  push    dword ptr [eax+44h]; sesid
0x10042184  call    ds:__imp__JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x1004218a  mov     ebx, eax
0x1004218c  test    ebx, ebx
0x1004218e  jns     short loc_100421A0
0x10042190  mov     edi, 80004005h
0x10042195  mov     [ebp+var_498], edi
0x1004219b  jmp     loc_100424DD
0x100421a0  mov     eax, [ebp+var_49C]
0x100421a6  push    80h; grbit
0x100421ab  push    [ebp+tableid]; tableid
0x100421b1  mov     eax, [eax+8]
0x100421b4  push    dword ptr [eax+44h]; sesid
0x100421b7  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x100421bd  mov     ebx, eax
0x100421bf  cmp     ebx, 0FFFFF9BFh
0x100421c5  jz      loc_100424D3
0x100421cb  test    ebx, ebx
0x100421cd  jz      short loc_100421DF
0x100421cf  mov     edi, 80004005h
0x100421d4  mov     [ebp+var_498], edi
0x100421da  jmp     loc_100424DD
0x100421df  mov     eax, [ebp+var_49C]
0x100421e5  push    5; grbit
0x100421e7  push    [ebp+tableid]; tableidSrc
0x100421ed  mov     eax, [eax+8]
0x100421f0  push    dword ptr [eax+44h]; sesid
0x100421f3  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x100421f9  mov     ebx, eax
0x100421fb  test    ebx, ebx
0x100421fd  jns     short loc_1004220F
0x100421ff  mov     edi, 80004005h
0x10042204  mov     [ebp+var_498], edi
0x1004220a  jmp     loc_100424DD
0x1004220f  mov     eax, [ebp+var_49C]
0x10042215  push    1; grbit
0x10042217  push    [ebp+tableid]; tableid
0x1004221d  mov     eax, [eax+8]
0x10042220  push    dword ptr [eax+44h]; sesid
0x10042223  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x10042229  mov     ebx, eax
0x1004222b  cmp     ebx, 0FFFFF9BFh
0x10042231  jz      loc_100424D3
0x10042237  test    ebx, ebx
0x10042239  jz      short loc_1004224B
0x1004223b  mov     edi, 80004005h
0x10042240  mov     [ebp+var_498], edi
0x10042246  jmp     loc_100424DD
0x1004224b  mov     esi, [ebp+var_49C]
0x10042251  mov     eax, [esi+8]
0x10042254  inc     [ebp+var_4A8]
0x1004225a  push    0; grbit
0x1004225c  push    1; cRow
0x1004225e  push    [ebp+tableid]; tableid
0x10042264  push    dword ptr [eax+44h]; sesid
0x10042267  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1004226d  test    eax, eax
0x1004226f  jns     short loc_10042251
0x10042271  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10042277  xor     ebx, ebx
0x10042279  mov     eax, [ecx]
0x1004227b  mov     edi, [eax+0Ch]
0x1004227e  mov     eax, [ebp+var_4A8]
0x10042284  lea     eax, [eax+eax*4]
0x10042287  shl     eax, 2
0x1004228a  push    eax
0x1004228b  push    ecx
0x1004228c  mov     ecx, edi
0x1004228e  mov     [ebp+Size], eax
0x10042294  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004229a  call    edi
0x1004229c  mov     ecx, [ebp+var_4B0]
0x100422a2  mov     esi, [ebp+var_4BC]
0x100422a8  mov     [ecx], eax
0x100422aa  test    eax, eax
0x100422ac  jnz     short loc_100422BE
0x100422ae  mov     edi, 8007000Eh
0x100422b3  mov     [ebp+var_498], edi
0x100422b9  jmp     loc_100424DD
0x100422be  push    [ebp+Size]; Size
0x100422c4  push    0; Val
0x100422c6  push    eax; void *
0x100422c7  call    _memset
0x100422cc  mov     eax, [ebp+var_4AC]
0x100422d2  add     esp, 0Ch
0x100422d5  mov     edi, [ebp+var_49C]
0x100422db  mov     ecx, [ebp+var_4A8]
0x100422e1  mov     [eax], ecx
0x100422e3  mov     eax, [edi+8]
0x100422e6  push    1; grbit
0x100422e8  push    [ebp+tableid]; tableid
0x100422ee  push    dword ptr [eax+44h]; sesid
0x100422f1  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x100422f7  mov     ebx, eax
0x100422f9  mov     [ebp+var_4A4], ebx
0x100422ff  cmp     ebx, 0FFFFF9BFh
0x10042305  jz      loc_100424C9
0x1004230b  test    ebx, ebx
0x1004230d  jz      short loc_1004231F
0x1004230f  mov     edi, 80004005h
0x10042314  mov     [ebp+var_498], edi
0x1004231a  jmp     loc_100424DD
0x1004231f  mov     ecx, [edi+8]
0x10042322  lea     eax, [ebp+var_4A4]
0x10042328  push    eax; int *
0x10042329  lea     eax, [ebp+Size]
0x1004232f  add     ecx, 40h ; '@'; this
0x10042332  push    eax; unsigned int *
0x10042333  push    offset aGroupsid; "GroupSID"
0x10042338  push    [ebp+tableid]; unsigned int
0x1004233e  call    ?FindColid@CSecuritySession@@QAEJKPBGAAKAAJ@Z; CSecuritySession::FindColid(ulong,ushort const *,ulong &,long &)
0x10042343  mov     edi, eax
0x10042345  mov     [ebp+var_498], edi
0x1004234b  test    edi, edi
0x1004234d  js      loc_100424D7
0x10042353  mov     eax, [ebp+var_4AC]
0x10042359  mov     [ebp+var_4A8], 0
0x10042363  cmp     dword ptr [eax], 0
0x10042366  jbe     loc_100424D7
0x1004236c  mov     edi, [ebp+var_49C]
0x10042372  push    0; pretinfo
0x10042374  push    0; grbit
0x10042376  lea     eax, [ebp+pcbActual]
0x1004237c  push    eax; pcbActual
0x1004237d  push    1FFh; cbData
0x10042382  lea     eax, [ebp+var_494]
0x10042388  push    eax; pvData
0x10042389  push    [ebp+Size]; columnid
0x1004238f  mov     eax, [edi+8]
0x10042392  push    [ebp+tableid]; tableid
0x10042398  push    dword ptr [eax+44h]; sesid
0x1004239b  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x100423a1  mov     ebx, eax
0x100423a3  test    ebx, ebx
0x100423a5  js      loc_100420D9
0x100423ab  lea     eax, [ebp+var_4C4]
0x100423b1  push    eax
0x100423b2  push    40h ; '@'
0x100423b4  lea     eax, [ebp+var_94]
0x100423ba  push    eax
0x100423bb  push    [ebp+pcbActual]
0x100423c1  lea     eax, [ebp+var_494]
0x100423c7  push    eax
0x100423c8  mov     eax, [edi+8]
0x100423cb  push    dword ptr [eax+44h]
0x100423ce  call    ds:__imp__JetGetNameFromSid@24; JetGetNameFromSid(x,x,x,x,x,x)
0x100423d4  mov     ebx, eax
0x100423d6  test    ebx, ebx
0x100423d8  js      loc_100420D9
0x100423de  mov     ecx, [ebp+var_4B0]
0x100423e4  mov     eax, [ebp+var_4A8]
0x100423ea  lea     edx, [eax+eax*4]
0x100423ed  mov     eax, [ecx]
0x100423ef  shl     edx, 2
0x100423f2  mov     [ebp+var_4A4], edx
0x100423f8  mov     dword ptr [edx+eax], 0
  ... truncated ...
```
