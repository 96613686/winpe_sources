# CImpITrusteeGroupAdmin::IsMember(_TRUSTEE_W *,_TRUSTEE_W *,int *)

- ea: `0x100413c0`
- end: `0x10041886`
- name: `?IsMember@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@0PAH@Z`
- size: `1222`
- prototype: `int(CImpITrusteeGroupAdmin *__hidden this, struct _TRUSTEE_W *, struct _TRUSTEE_W *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001e800`
- `0x1001eb70`
- `0x100413c0`
- `0x10043840`
- `0x100438f0`
- `0x10043ea0`
- `0x10044090`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10041860`
- `KERNEL32!LeaveCriticalSection` at `0x10041860`
- `KERNEL32!EnterCriticalSection` at `0x1004145d`
- `KERNEL32!EnterCriticalSection` at `0x1004145d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004144a`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004144a`
- `msjet40!__imp__JetCloseTable@8` at `0x1004184b`
- `msjet40!__imp__JetCloseTable@8` at `0x1004184b`
- `msjet40!__imp__JetMakeKey@20` at `0x100415b1`
- `msjet40!__imp__JetMakeKey@20` at `0x100415b1`
- `msjet40!__imp__JetMove@16` at `0x1004178a`
- `msjet40!__imp__JetMove@16` at `0x1004178a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100416fe`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100416fe`
- `msjet40!__imp__JetSeek@12` at `0x100415db`
- `msjet40!__imp__JetSeek@12` at `0x100415db`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10041539`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10041539`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1004161d`
- `msjet40!__imp__JetSetIndexRange@12` at `0x1004161d`

## string_xrefs

- `0x1004152b`: `UserSID`
- `0x1004168e`: `GroupSID`

## pseudocode

```c
int __stdcall CImpITrusteeGroupAdmin::IsMember(
        CImpITrusteeGroupAdmin *this,
        struct _TRUSTEE_W *a2,
        struct _TRUSTEE_W *a3,
        int *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  CSecuritySession *v5; // ecx
  struct _TRUSTEE_W *v6; // edx
  CSecuritySession *v7; // ecx
  int SidFromName; // edi
  int Key; // ebx
  CImpITrusteeGroupAdmin *v10; // ebx
  JET_ERR v11; // eax
  CImpITrusteeGroupAdmin *v12; // ebx
  _BYTE *v13; // edx
  unsigned int *v14; // edi
  unsigned int v15; // ecx
  bool v16; // cf
  CImpITrusteeGroupAdmin *v17; // ebx
  unsigned int v19; // [esp-14h] [ebp-664h]
  unsigned __int16 *v20; // [esp-10h] [ebp-660h]
  unsigned int v21; // [esp-8h] [ebp-658h]
  struct _GUID *v22; // [esp+0h] [ebp-650h]
  struct _GUID *v23; // [esp+4h] [ebp-64Ch]
  unsigned __int16 v24[2]; // [esp+14h] [ebp-63Ch] BYREF
  unsigned int pcbActual; // [esp+18h] [ebp-638h] BYREF
  unsigned int cbData; // [esp+1Ch] [ebp-634h] BYREF
  int v27; // [esp+20h] [ebp-630h] BYREF
  unsigned int v28; // [esp+24h] [ebp-62Ch] BYREF
  JET_COLUMNID columnid; // [esp+28h] [ebp-628h] BYREF
  struct _TRUSTEE_W *v30; // [esp+2Ch] [ebp-624h]
  int *v31; // [esp+30h] [ebp-620h]
  JET_TABLEID tableid; // [esp+34h] [ebp-61Ch] BYREF
  CImpITrusteeGroupAdmin *v33; // [esp+38h] [ebp-618h]
  unsigned int v34; // [esp+3Ch] [ebp-614h] BYREF
  unsigned int v35[128]; // [esp+40h] [ebp-610h] BYREF
  _BYTE v36[512]; // [esp+240h] [ebp-410h] BYREF
  _BYTE pvData[512]; // [esp+440h] [ebp-210h] BYREF
  int v38; // [esp+64Ch] [ebp-4h]

  v30 = a3;
  v33 = this;
  columnid = (JET_COLUMNID)a2;
  v31 = a4;
  v34 = 0;
  tableid = -1;
  v28 = 0;
  v27 = 0;
  if ( a4 )
    *a4 = 0;
  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v4);
  v38 = 0;
  if ( !a2 || !v30 || !v31 )
  {
    SidFromName = -2147024809;
    goto LABEL_58;
  }
  if ( !CSecuritySession::fIsValidTrusteeForm(v5, a2) || !CSecuritySession::fIsValidTrusteeForm(v7, v6) )
  {
    SidFromName = -2147217814;
    goto LABEL_58;
  }
  if ( a2->TrusteeType != TRUSTEE_IS_GROUP )
  {
    SidFromName = -2147217812;
LABEL_58:
    CExtError::SendHRtoOLEAuto((int)&IID_ITrusteeGroupAdmin, 0, v22, (int)v23);
    goto LABEL_59;
  }
  SidFromName = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)&v34);
  if ( SidFromName >= 0 )
  {
    SidFromName = CSecuritySession::CheckForSecurityDbid(
                    (CSecuritySession *)(*((_DWORD *)this + 2) + 64),
                    (int *)&v34,
                    &v27);
    if ( SidFromName < 0 )
      goto LABEL_48;
    SidFromName = CJOLT::JOLTJetOpenTable(
                    (unsigned int)L"MSysGroups",
                    v19,
                    v20,
                    (const void *)0x20,
                    (unsigned int)&tableid,
                    (unsigned int)&v34,
                    &v22->Data1,
                    (int *)v23);
    if ( SidFromName < 0 )
      goto LABEL_48;
    Key = JetSetCurrentIndex(*(_DWORD *)(*((_DWORD *)this + 2) + 68), tableid, L"UserSID");
    v34 = Key;
    if ( Key < 0 )
    {
LABEL_14:
      SidFromName = -2147467259;
      goto LABEL_49;
    }
    v10 = v33;
    SidFromName = CJOLT::JOLTJetGetSidFromName(
                    (unsigned int)pvData,
                    (const unsigned __int16 *)&cbData,
                    &cbData,
                    (unsigned int)&v28,
                    &v34,
                    (int *)v22,
                    (int *)v23);
    if ( SidFromName < 0 )
      goto LABEL_48;
    Key = JetMakeKey(*(_DWORD *)(*((_DWORD *)v10 + 2) + 68), tableid, pvData, cbData, 1u);
    if ( Key < 0 )
    {
      SidFromName = -2147467259;
      goto LABEL_49;
    }
    v11 = JetSeek(*(_DWORD *)(*((_DWORD *)v33 + 2) + 68), tableid, 1u);
    Key = v11;
    if ( v11 == -1601 )
    {
      Key = 0;
      *v31 = 0;
      goto LABEL_49;
    }
    if ( v11 )
    {
      SidFromName = -2147467259;
      *v31 = 0;
      goto LABEL_49;
    }
    Key = JetSetIndexRange(*(_DWORD *)(*((_DWORD *)v33 + 2) + 68), tableid, 5u);
    v34 = Key;
    if ( Key < 0 )
    {
      SidFromName = -2147467259;
      goto LABEL_49;
    }
    v12 = v33;
    SidFromName = CJOLT::JOLTJetGetSidFromName(
                    (unsigned int)v35,
                    v24,
                    v24,
                    (unsigned int)&v28,
                    &v34,
                    (int *)v22,
                    (int *)v23);
    if ( SidFromName < 0
      || (SidFromName = CSecuritySession::FindColid(
                          (CSecuritySession *)(*((_DWORD *)v12 + 2) + 64),
                          tableid,
                          L"GroupSID",
                          &columnid,
                          (int *)&v34),
          v30 = (struct _TRUSTEE_W *)SidFromName,
          SidFromName < 0) )
    {
LABEL_48:
      Key = v34;
    }
    else
    {
      Key = v34;
      if ( *v31 )
      {
LABEL_43:
        if ( Key == -1603 )
          Key = 0;
      }
      else
      {
        while ( Key != -1603 )
        {
          Key = JetRetrieveColumn(
                  *(_DWORD *)(*((_DWORD *)v33 + 2) + 68),
                  tableid,
                  columnid,
                  v36,
                  0x1FFu,
                  &pcbActual,
                  0,
                  0);
          if ( Key < 0 )
            goto LABEL_14;
          if ( pcbActual && pcbActual == *(_DWORD *)v24 )
          {
            v13 = v36;
            v14 = v35;
            v15 = pcbActual - 4;
            if ( pcbActual < 4 )
            {
LABEL_33:
              if ( v15 == -4 )
                goto LABEL_45;
            }
            else
            {
              while ( *(_DWORD *)v13 == *v14 )
              {
                v13 += 4;
                ++v14;
                v16 = v15 < 4;
                v15 -= 4;
                if ( v16 )
                  goto LABEL_33;
              }
            }
            if ( *v13 == *(_BYTE *)v14
              && (v15 == -3
               || v13[1] == *((_BYTE *)v14 + 1)
               && (v15 == -2 || v13[2] == *((_BYTE *)v14 + 2) && (v15 == -1 || v13[3] == *((_BYTE *)v14 + 3)))) )
            {
LABEL_45:
              SidFromName = (int)v30;
              *v31 = 1;
              goto LABEL_49;
            }
          }
          Key = JetMove(*(_DWORD *)(*((_DWORD *)v33 + 2) + 68), tableid, 1, 0);
          if ( *v31 )
          {
            SidFromName = (int)v30;
            goto LABEL_43;
          }
        }
        SidFromName = (int)v30;
        Key = 0;
      }
    }
LABEL_49:
    if ( v27 )
      goto LABEL_59;
    goto LABEL_52;
  }
  Key = v34;
LABEL_52:
  if ( Key )
  {
    v21 = Key;
    v17 = v33;
    CExtError::SendJetErrortoOLEAuto(
      SidFromName,
      *(char **)(*((_DWORD *)v33 + 2) + 68),
      v21,
      (int)&IID_ITrusteeGroupAdmin,
      (int)v22,
      v23);
    goto LABEL_60;
  }
  if ( SidFromName < 0 )
    goto LABEL_58;
LABEL_59:
  v17 = v33;
LABEL_60:
  if ( tableid != -1 )
  {
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v17 + 2) + 68), tableid);
    tableid = -1;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return SidFromName;
}

```

## disassembly

```asm
0x100413c0  mov     edi, edi
0x100413c2  push    ebp
0x100413c3  mov     ebp, esp
0x100413c5  push    0FFFFFFFFh
0x100413c7  push    offset ?IsMember@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@0PAH@Z_SEH
0x100413cc  mov     eax, large fs:0
0x100413d2  push    eax
0x100413d3  sub     esp, 634h
0x100413d9  mov     eax, ___security_cookie
0x100413de  xor     eax, ebp
0x100413e0  mov     [ebp+var_10], eax
0x100413e3  push    ebx
0x100413e4  push    esi
0x100413e5  push    edi; int
0x100413e6  push    eax; struct _GUID *
0x100413e7  lea     eax, [ebp+var_C]
0x100413ea  mov     large fs:0, eax
0x100413f0  mov     eax, [ebp+arg_8]
0x100413f3  mov     ebx, [ebp+this]
0x100413f6  mov     edi, [ebp+arg_4]
0x100413f9  mov     [ebp+var_624], eax
0x100413ff  mov     eax, [ebp+arg_C]
0x10041402  mov     [ebp+var_618], ebx
0x10041408  mov     [ebp+columnid], edi
0x1004140e  mov     [ebp+var_620], eax
0x10041414  mov     [ebp+var_614], 0
0x1004141e  mov     [ebp+tableid], 0FFFFFFFFh
0x10041428  mov     [ebp+var_62C], 0
0x10041432  mov     [ebp+var_630], 0
0x1004143c  test    eax, eax
0x1004143e  jz      short loc_10041446
0x10041440  mov     dword ptr [eax], 0
0x10041446  push    0; perrinfo
0x10041448  push    0; dwReserved
0x1004144a  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10041450  mov     esi, [ebx+8]
0x10041453  add     esi, 64h ; 'd'
0x10041456  push    esi; lpCriticalSection
0x10041457  mov     [ebp+var_640], esi
0x1004145d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10041463  mov     [ebp+var_4], 0
0x1004146a  test    edi, edi
0x1004146c  jz      loc_10041820
0x10041472  mov     edx, [ebp+var_624]
0x10041478  test    edx, edx
0x1004147a  jz      loc_10041820
0x10041480  cmp     [ebp+var_620], 0
0x10041487  jz      loc_10041820
0x1004148d  push    edi; struct _TRUSTEE_W *
0x1004148e  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x10041493  test    eax, eax
0x10041495  jz      loc_10041819
0x1004149b  push    edx; struct _TRUSTEE_W *
0x1004149c  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x100414a1  test    eax, eax
0x100414a3  jz      loc_10041819
0x100414a9  cmp     dword ptr [edi+0Ch], 2
0x100414ad  jz      short loc_100414B9
0x100414af  mov     edi, 80040E6Ch
0x100414b4  jmp     loc_10041825
0x100414b9  mov     ecx, [ebx+8]
0x100414bc  lea     eax, [ebp+var_614]
0x100414c2  add     ecx, 40h ; '@'; this
0x100414c5  push    eax; int *
0x100414c6  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x100414cb  mov     edi, eax
0x100414cd  test    edi, edi
0x100414cf  js      loc_100417EE
0x100414d5  mov     ecx, [ebx+8]
0x100414d8  lea     eax, [ebp+var_630]
0x100414de  push    eax; int *
0x100414df  lea     eax, [ebp+var_614]
0x100414e5  add     ecx, 40h ; '@'; this
0x100414e8  push    eax; int *
0x100414e9  call    ?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z; CSecuritySession::CheckForSecurityDbid(long &,int &)
0x100414ee  mov     edi, eax
0x100414f0  test    edi, edi
0x100414f2  js      loc_100417DD
0x100414f8  mov     eax, [ebx+8]
0x100414fb  lea     ecx, [ebp+var_614]
0x10041501  push    ecx; unsigned int
0x10041502  lea     ecx, [ebp+tableid]
0x10041508  push    ecx; unsigned int
0x10041509  mov     edx, [eax+48h]
0x1004150c  mov     ecx, [eax+44h]
0x1004150f  push    20h ; ' '; void *
0x10041511  sub     esp, 8
0x10041514  push    offset aMsysgroups; "MSysGroups"
0x10041519  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x1004151e  mov     edi, eax
0x10041520  test    edi, edi
0x10041522  js      loc_100417DD
0x10041528  mov     eax, [ebx+8]
0x1004152b  push    offset aUsersid; "UserSID"
0x10041530  push    [ebp+tableid]
0x10041536  push    dword ptr [eax+44h]
0x10041539  call    ds:__imp__JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x1004153f  mov     ebx, eax
0x10041541  mov     [ebp+var_614], ebx
0x10041547  test    ebx, ebx
0x10041549  jns     short loc_10041555
0x1004154b  mov     edi, 80004005h
0x10041550  jmp     loc_100417E3
0x10041555  mov     ebx, [ebp+var_618]
0x1004155b  lea     ecx, [ebp+var_614]
0x10041561  mov     edx, [ebp+var_624]
0x10041567  push    ecx; unsigned int *
0x10041568  lea     ecx, [ebp+var_62C]
0x1004156e  mov     eax, [ebx+8]
0x10041571  mov     edx, [edx+10h]
0x10041574  push    ecx; unsigned int
0x10041575  lea     ecx, [ebp+cbData]
0x1004157b  push    ecx; void *
0x1004157c  push    ecx; unsigned __int16 *
0x1004157d  lea     ecx, [ebp+pvData]
0x10041583  push    ecx; unsigned int
0x10041584  mov     ecx, [eax+44h]
0x10041587  call    ?JOLTJetGetSidFromName@CJOLT@@SGJKPBGPAXKPAKPAJAAJ@Z; CJOLT::JOLTJetGetSidFromName(ulong,ushort const *,void *,ulong,ulong *,long *,long &)
0x1004158c  mov     edi, eax
0x1004158e  test    edi, edi
0x10041590  js      loc_100417DD
0x10041596  push    1; grbit
0x10041598  push    [ebp+cbData]; cbData
0x1004159e  lea     eax, [ebp+pvData]
0x100415a4  push    eax; pvData
0x100415a5  mov     eax, [ebx+8]
0x100415a8  push    [ebp+tableid]; tableid
0x100415ae  push    dword ptr [eax+44h]; sesid
0x100415b1  call    ds:__imp__JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x100415b7  mov     ebx, eax
0x100415b9  test    ebx, ebx
0x100415bb  jns     short loc_100415C7
0x100415bd  mov     edi, 80004005h
0x100415c2  jmp     loc_100417E3
0x100415c7  mov     eax, [ebp+var_618]
0x100415cd  push    1; grbit
0x100415cf  push    [ebp+tableid]; tableid
0x100415d5  mov     eax, [eax+8]
0x100415d8  push    dword ptr [eax+44h]; sesid
0x100415db  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x100415e1  mov     ebx, eax
0x100415e3  cmp     ebx, 0FFFFF9BFh
0x100415e9  jz      loc_100417D1
0x100415ef  test    ebx, ebx
0x100415f1  jz      short loc_10041609
0x100415f3  mov     eax, [ebp+var_620]
0x100415f9  mov     edi, 80004005h
0x100415fe  mov     dword ptr [eax], 0
0x10041604  jmp     loc_100417E3
0x10041609  mov     eax, [ebp+var_618]
0x1004160f  push    5; grbit
0x10041611  push    [ebp+tableid]; tableidSrc
0x10041617  mov     eax, [eax+8]
0x1004161a  push    dword ptr [eax+44h]; sesid
0x1004161d  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x10041623  mov     ebx, eax
0x10041625  mov     [ebp+var_614], ebx
0x1004162b  test    ebx, ebx
0x1004162d  jns     short loc_10041639
0x1004162f  mov     edi, 80004005h
0x10041634  jmp     loc_100417E3
0x10041639  mov     ebx, [ebp+var_618]
0x1004163f  lea     ecx, [ebp+var_614]
0x10041645  mov     edx, [ebp+columnid]
0x1004164b  push    ecx; unsigned int *
0x1004164c  lea     ecx, [ebp+var_62C]
0x10041652  mov     eax, [ebx+8]
0x10041655  mov     edx, [edx+10h]
0x10041658  push    ecx; unsigned int
0x10041659  lea     ecx, [ebp+var_63C]
0x1004165f  push    ecx; void *
0x10041660  push    ecx; unsigned __int16 *
0x10041661  lea     ecx, [ebp+var_610]
0x10041667  push    ecx; unsigned int
0x10041668  mov     ecx, [eax+44h]
0x1004166b  call    ?JOLTJetGetSidFromName@CJOLT@@SGJKPBGPAXKPAKPAJAAJ@Z; CJOLT::JOLTJetGetSidFromName(ulong,ushort const *,void *,ulong,ulong *,long *,long &)
0x10041670  mov     edi, eax
0x10041672  test    edi, edi
0x10041674  js      loc_100417DD
0x1004167a  mov     ecx, [ebx+8]
0x1004167d  lea     eax, [ebp+var_614]
0x10041683  push    eax; int *
0x10041684  lea     eax, [ebp+columnid]
0x1004168a  add     ecx, 40h ; '@'; this
0x1004168d  push    eax; unsigned int *
0x1004168e  push    offset aGroupsid; "GroupSID"
0x10041693  push    [ebp+tableid]; unsigned int
0x10041699  call    ?FindColid@CSecuritySession@@QAEJKPBGAAKAAJ@Z; CSecuritySession::FindColid(ulong,ushort const *,ulong &,long &)
0x1004169e  mov     edi, eax
0x100416a0  mov     [ebp+var_624], edi
0x100416a6  test    edi, edi
0x100416a8  js      loc_100417DD
0x100416ae  mov     eax, [ebp+var_620]
0x100416b4  mov     ebx, [ebp+var_614]
0x100416ba  cmp     dword ptr [eax], 0
0x100416bd  jnz     loc_100417A7
0x100416c3  cmp     ebx, 0FFFFF9BDh
0x100416c9  jz      loc_100417C7
0x100416cf  push    0; pretinfo
0x100416d1  push    0; grbit
0x100416d3  lea     eax, [ebp+pcbActual]
0x100416d9  push    eax; pcbActual
0x100416da  push    1FFh; cbData
0x100416df  lea     eax, [ebp+var_410]
0x100416e5  push    eax; pvData
0x100416e6  mov     eax, [ebp+var_618]
0x100416ec  push    [ebp+columnid]; columnid
0x100416f2  push    [ebp+tableid]; tableid
0x100416f8  mov     eax, [eax+8]
0x100416fb  push    dword ptr [eax+44h]; sesid
0x100416fe  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10041704  mov     ebx, eax
0x10041706  test    ebx, ebx
0x10041708  js      loc_1004154B
0x1004170e  mov     ecx, [ebp+pcbActual]
0x10041714  test    ecx, ecx
0x10041716  jz      short loc_10041774
0x10041718  cmp     ecx, dword ptr [ebp+var_63C]
0x1004171e  jnz     short loc_10041774
0x10041720  lea     edx, [ebp+var_410]
0x10041726  lea     edi, [ebp+var_610]
0x1004172c  sub     ecx, 4
0x1004172f  jb      short loc_10041742
0x10041731  mov     eax, [edx]
0x10041733  cmp     eax, [edi]
0x10041735  jnz     short loc_10041747
0x10041737  add     edx, 4
0x1004173a  add     edi, 4
0x1004173d  sub     ecx, 4
0x10041740  jnb     short loc_10041731
0x10041742  cmp     ecx, 0FFFFFFFCh
0x10041745  jz      short loc_100417B3
0x10041747  mov     al, [edx]
0x10041749  cmp     al, [edi]
0x1004174b  jnz     short loc_10041774
0x1004174d  cmp     ecx, 0FFFFFFFDh
0x10041750  jz      short loc_100417B3
0x10041752  mov     al, [edx+1]
0x10041755  cmp     al, [edi+1]
0x10041758  jnz     short loc_10041774
0x1004175a  cmp     ecx, 0FFFFFFFEh
0x1004175d  jz      short loc_100417B3
0x1004175f  mov     al, [edx+2]
0x10041762  cmp     al, [edi+2]
0x10041765  jnz     short loc_10041774
0x10041767  cmp     ecx, 0FFFFFFFFh
0x1004176a  jz      short loc_100417B3
0x1004176c  mov     al, [edx+3]
0x1004176f  cmp     al, [edi+3]
0x10041772  jz      short loc_100417B3
0x10041774  mov     eax, [ebp+var_618]
0x1004177a  push    0; grbit
0x1004177c  push    1; cRow
0x1004177e  push    [ebp+tableid]; tableid
0x10041784  mov     eax, [eax+8]
0x10041787  push    dword ptr [eax+44h]; sesid
0x1004178a  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10041790  mov     ebx, eax
0x10041792  mov     eax, [ebp+var_620]
0x10041798  cmp     dword ptr [eax], 0
0x1004179b  jz      loc_100416C3
0x100417a1  mov     edi, [ebp+var_624]
0x100417a7  cmp     ebx, 0FFFFF9BDh
0x100417ad  jnz     short loc_100417E3
0x100417af  xor     ebx, ebx
0x100417b1  jmp     short loc_100417E3
0x100417b3  mov     eax, [ebp+var_620]
0x100417b9  mov     edi, [ebp+var_624]
0x100417bf  mov     dword ptr [eax], 1
0x100417c5  jmp     short loc_100417E3
0x100417c7  mov     edi, [ebp+var_624]
0x100417cd  xor     ebx, ebx
0x100417cf  jmp     short loc_100417E3
0x100417d1  mov     eax, [ebp+var_620]
0x100417d7  xor     ebx, ebx
0x100417d9  mov     [eax], ebx
0x100417db  jmp     short loc_100417E3
0x100417dd  mov     ebx, [ebp+var_614]
0x100417e3  cmp     [ebp+var_630], 0
0x100417ea  jnz     short loc_10041833
0x100417ec  jmp     short loc_100417F4
0x100417ee  mov     ebx, [ebp+var_614]
0x100417f4  test    ebx, ebx
0x100417f6  jz      short loc_10041813
0x100417f8  push    offset _IID_ITrusteeGroupAdmin; int
0x100417fd  push    ebx; unsigned int
0x100417fe  mov     ebx, [ebp+var_618]
0x10041804  mov     edx, edi
0x10041806  mov     ecx, [ebx+8]
0x10041809  mov     ecx, [ecx+44h]
0x1004180c  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10041811  jmp     short loc_10041839
0x10041813  test    edi, edi
0x10041815  jns     short loc_10041833
0x10041817  jmp     short loc_10041825
0x10041819  mov     edi, 80040E6Ah
0x1004181e  jmp     short loc_10041825
0x10041820  mov     edi, 80070057h
0x10041825  push    0; int
0x10041827  push    offset _IID_ITrusteeGroupAdmin; int
  ... truncated ...
```
