# CImpITrusteeGroupAdmin::GetMembers(_TRUSTEE_W *,ulong *,_TRUSTEE_W * *)

- ea: `0x10041890`
- end: `0x10041f46`
- name: `?GetMembers@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@PAKPAPAU2@@Z`
- size: `1718`
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
- `0x10041890`
- `0x10043840`
- `0x100438f0`
- `0x10043ea0`
- `0x10044090`
- `0x1004d406`
- `0x1004d420`
- `0x1004dc8d`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10041f20`
- `KERNEL32!LeaveCriticalSection` at `0x10041f20`
- `KERNEL32!EnterCriticalSection` at `0x1004192f`
- `KERNEL32!EnterCriticalSection` at `0x1004192f`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10041916`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10041916`
- `msjet40!__imp__JetCloseTable@8` at `0x10041f15`
- `msjet40!__imp__JetCloseTable@8` at `0x10041f15`
- `msjet40!__imp__JetGetNameFromSid@24` at `0x10041cfd`
- `msjet40!__imp__JetGetNameFromSid@24` at `0x10041cfd`
- `msjet40!__imp__JetMakeKey@20` at `0x10041aad`
- `msjet40!__imp__JetMakeKey@20` at `0x10041aad`
- `msjet40!__imp__JetMove@16` at `0x10041b96`
- `msjet40!__imp__JetMove@16` at `0x10041dcf`
- `msjet40!__imp__JetMove@16` at `0x10041b96`
- `msjet40!__imp__JetMove@16` at `0x10041dcf`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10041cca`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10041cca`
- `msjet40!__imp__JetSeek@12` at `0x10041ae0`
- `msjet40!__imp__JetSeek@12` at `0x10041b4c`
- `msjet40!__imp__JetSeek@12` at `0x10041c20`
- `msjet40!__imp__JetSeek@12` at `0x10041ae0`
- `msjet40!__imp__JetSeek@12` at `0x10041b4c`
- `msjet40!__imp__JetSeek@12` at `0x10041c20`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10041a2c`
- `msjet40!__imp__JetSetCurrentIndex@12` at `0x10041a2c`
- `msjet40!__imp__JetSetIndexRange@12` at `0x10041b1c`
- `msjet40!__imp__JetSetIndexRange@12` at `0x10041b1c`

## string_xrefs

- `0x10041c62`: `UserSID`
- `0x10041a1e`: `GroupSID`

## pseudocode

```c
int __stdcall CImpITrusteeGroupAdmin::GetMembers(
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
  int (__thiscall *v13)(_DWORD, int, JET_COLUMNID); // ecx
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
  struct _TRUSTEE_W **v25; // ebx
  unsigned int *v26; // edi
  int v27; // eax
  unsigned int v28; // ebx
  struct _TRUSTEE_W **v29; // esi
  unsigned int v31; // [esp-14h] [ebp-4F4h]
  unsigned __int16 *v32; // [esp-10h] [ebp-4F0h]
  struct _GUID *v33; // [esp+0h] [ebp-4E0h]
  struct _GUID *v34; // [esp+4h] [ebp-4DCh]
  unsigned __int16 *v35; // [esp+14h] [ebp-4CCh]
  unsigned int pcbActual; // [esp+18h] [ebp-4C8h] BYREF
  unsigned int v37; // [esp+1Ch] [ebp-4C4h] BYREF
  unsigned int cbData; // [esp+20h] [ebp-4C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v39; // [esp+24h] [ebp-4BCh]
  int v40; // [esp+28h] [ebp-4B8h] BYREF
  JET_COLUMNID columnid; // [esp+2Ch] [ebp-4B4h] BYREF
  struct _TRUSTEE_W **v42; // [esp+30h] [ebp-4B0h]
  unsigned int *v43; // [esp+34h] [ebp-4ACh]
  size_t Size; // [esp+38h] [ebp-4A8h]
  CImpITrusteeGroupAdmin *v45; // [esp+3Ch] [ebp-4A4h]
  unsigned int v46; // [esp+40h] [ebp-4A0h] BYREF
  JET_TABLEID tableid; // [esp+44h] [ebp-49Ch] BYREF
  int v48; // [esp+48h] [ebp-498h]
  _BYTE v49[512]; // [esp+4Ch] [ebp-494h] BYREF
  _BYTE pvData[512]; // [esp+24Ch] [ebp-294h] BYREF
  unsigned __int16 v51[66]; // [esp+44Ch] [ebp-94h] BYREF
  int v52; // [esp+4DCh] [ebp-4h]

  Size = (size_t)a2;
  v45 = this;
  v43 = a3;
  v42 = a4;
  v46 = 0;
  columnid = 0;
  tableid = -1;
  v40 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  v39 = v4;
  EnterCriticalSection(v4);
  v52 = 0;
  if ( !Size || !v43 || !a4 )
  {
    SidFromName = -2147024809;
    goto LABEL_54;
  }
  if ( !CSecuritySession::fIsValidTrusteeForm(v5, (struct _TRUSTEE_W *)Size) )
  {
    SidFromName = -2147217814;
LABEL_54:
    v48 = SidFromName;
LABEL_55:
    CExtError::SendHRtoOLEAuto((int)&IID_ITrusteeGroupAdmin, 0, v33, (int)v34);
    goto LABEL_56;
  }
  SidFromName = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)&v46);
  v48 = SidFromName;
  if ( SidFromName >= 0 )
  {
    SidFromName = CSecuritySession::CheckForSecurityDbid(
                    (CSecuritySession *)(*((_DWORD *)this + 2) + 64),
                    (int *)&v46,
                    &v40);
    v48 = SidFromName;
    if ( SidFromName < 0 )
    {
LABEL_14:
      Key = v46;
      goto LABEL_15;
    }
    if ( *(_DWORD *)(Size + 12) != 2 )
    {
      SidFromName = -2147217812;
      v48 = -2147217812;
      goto LABEL_14;
    }
    SidFromName = CJOLT::JOLTJetOpenTable(
                    (unsigned int)L"MSysGroups",
                    v31,
                    v32,
                    (const void *)0x20,
                    (unsigned int)&tableid,
                    (unsigned int)&v46,
                    &v33->Data1,
                    (int *)v34);
    v48 = SidFromName;
    if ( SidFromName < 0 )
      goto LABEL_14;
    Key = JetSetCurrentIndex(*(_DWORD *)(*((_DWORD *)this + 2) + 68), tableid, L"GroupSID");
    v46 = Key;
    if ( Key < 0 )
      goto LABEL_19;
    v8 = v45;
    SidFromName = CJOLT::JOLTJetGetSidFromName(
                    (unsigned int)pvData,
                    (const unsigned __int16 *)&cbData,
                    &cbData,
                    (unsigned int)&v37,
                    &v46,
                    (int *)v33,
                    (int *)v34);
    v48 = SidFromName;
    if ( SidFromName < 0 )
      goto LABEL_14;
    Key = JetMakeKey(*(_DWORD *)(*((_DWORD *)v8 + 2) + 68), tableid, pvData, cbData, 1u);
    if ( Key < 0 )
    {
      SidFromName = -2147467259;
      v48 = -2147467259;
      goto LABEL_15;
    }
    v9 = JetSeek(*(_DWORD *)(*((_DWORD *)v45 + 2) + 68), tableid, 0x80u);
    Key = v9;
    if ( v9 == -1601 )
      goto LABEL_47;
    if ( v9 )
    {
      SidFromName = -2147467259;
      v48 = -2147467259;
      goto LABEL_15;
    }
    Key = JetSetIndexRange(*(_DWORD *)(*((_DWORD *)v45 + 2) + 68), tableid, 5u);
    if ( Key < 0 )
    {
      SidFromName = -2147467259;
      v48 = -2147467259;
      goto LABEL_15;
    }
    v10 = JetSeek(*(_DWORD *)(*((_DWORD *)v45 + 2) + 68), tableid, 1u);
    Key = v10;
    if ( v10 == -1601 )
    {
LABEL_47:
      Key = 0;
    }
    else if ( v10 )
    {
      SidFromName = -2147467259;
      v48 = -2147467259;
    }
    else
    {
      v11 = v45;
      do
      {
        v12 = *((_DWORD *)v11 + 2);
        ++columnid;
      }
      while ( JetMove(*(_DWORD *)(v12 + 68), tableid, 1, 0) >= 0 );
      Key = 0;
      v13 = *(int (__thiscall **)(_DWORD, int, JET_COLUMNID))(*(_DWORD *)Sys + 12);
      Size = 20 * columnid;
      v14 = (struct _TRUSTEE_W *)v13(v13, Sys, 20 * columnid);
      v4 = v39;
      *v42 = v14;
      if ( v14 )
      {
        memset(v14, 0, Size);
        v15 = v45;
        *v43 = columnid;
        v16 = JetSeek(*(_DWORD *)(*((_DWORD *)v15 + 2) + 68), tableid, 1u);
        Key = v16;
        v46 = v16;
        if ( v16 == -1601 )
        {
          SidFromName = v48;
          Key = 0;
        }
        else
        {
          if ( !v16 )
          {
            SidFromName = CSecuritySession::FindColid(
                            (CSecuritySession *)(*((_DWORD *)v15 + 2) + 64),
                            tableid,
                            L"UserSID",
                            &columnid,
                            (int *)&v46);
            v48 = SidFromName;
            if ( SidFromName < 0 )
              goto LABEL_14;
            Size = 0;
            if ( !*v43 )
              goto LABEL_14;
            v17 = v45;
            while ( 1 )
            {
              Key = JetRetrieveColumn(
                      *(_DWORD *)(*((_DWORD *)v17 + 2) + 68),
                      tableid,
                      columnid,
                      v49,
                      0x1FFu,
                      &pcbActual,
                      0,
                      0);
              if ( Key < 0 )
                break;
              Key = JetGetNameFromSid(*(_DWORD *)(*((_DWORD *)v17 + 2) + 68), v49, pcbActual, v51, 64, &v37);
              if ( Key < 0 )
                break;
              v18 = v42;
              v19 = *v42;
              v20 = Size;
              v46 = v20 * 20;
              v19[v20].pMultipleTrustee = 0;
              (*v18)[v20].MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
              (*v18)[v20].TrusteeForm = TRUSTEE_IS_NAME;
              (*v18)[v20].TrusteeType = TRUSTEE_IS_USER;
              v35 = (unsigned __int16 *)(2 * wcslen(v51) + 2);
              v21 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
                      *(_DWORD *)(*(_DWORD *)Sys + 12),
                      Sys,
                      v35);
              v22 = v42;
              v23 = v46;
              *(LPWCH *)((char *)&(*v42)->ptstrName + v46) = (LPWCH)v21;
              v24 = *(LPWCH *)((char *)&(*v22)->ptstrName + v23);
              if ( !v24 )
                goto LABEL_34;
              WCSCPY(v51, v24, v35, (const unsigned __int16 *)v33, (unsigned int)v34);
              v17 = v45;
              JetMove(*(_DWORD *)(*((_DWORD *)v45 + 2) + 68), tableid, 1, 0);
              if ( ++Size >= *v43 )
              {
                SidFromName = v48;
                goto LABEL_15;
              }
            }
LABEL_19:
            SidFromName = -2147467259;
            v48 = -2147467259;
            goto LABEL_15;
          }
          SidFromName = -2147467259;
          v48 = -2147467259;
        }
      }
      else
      {
LABEL_34:
        SidFromName = -2147024882;
        v48 = -2147024882;
      }
    }
LABEL_15:
    if ( v40 )
      goto LABEL_56;
    goto LABEL_49;
  }
  Key = v46;
LABEL_49:
  if ( !Key )
  {
    if ( SidFromName >= 0 )
      goto LABEL_70;
    goto LABEL_55;
  }
  CExtError::SendJetErrortoOLEAuto(Key, (int)&IID_ITrusteeGroupAdmin, (int)v33, v34);
LABEL_56:
  if ( SidFromName < 0 )
  {
    v25 = v42;
    if ( v42 )
    {
      if ( *v42 )
      {
        v26 = v43;
        if ( v43 && *v43 )
        {
          v27 = Sys;
          v28 = 0;
          v29 = v42;
          do
          {
            if ( (*v29)[v28].ptstrName && v27 )
            {
              (*(void (__thiscall **)(_DWORD, int, LPWCH))(*(_DWORD *)v27 + 20))(
                *(_DWORD *)(*(_DWORD *)v27 + 20),
                v27,
                (*v29)[v28].ptstrName);
              v27 = Sys;
              v26 = v43;
            }
            ++v28;
          }
          while ( v28 < *v26 );
          v4 = v39;
          v25 = v42;
          *v26 = 0;
        }
        if ( Sys )
          (*(void (__thiscall **)(_DWORD, int, struct _TRUSTEE_W *))(*(_DWORD *)Sys + 20))(
            *(_DWORD *)(*(_DWORD *)Sys + 20),
            Sys,
            *v25);
        SidFromName = v48;
        *v25 = 0;
      }
    }
  }
LABEL_70:
  if ( tableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v45 + 2) + 68), tableid);
  if ( v4 )
    LeaveCriticalSection(v4);
  return SidFromName;
}

```

## disassembly

```asm
0x10041890  mov     edi, edi
0x10041892  push    ebp
0x10041893  mov     ebp, esp
0x10041895  push    0FFFFFFFFh
0x10041897  push    offset ?GetMemberships@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@PAKPAPAU2@@Z_SEH
0x1004189c  mov     eax, large fs:0
0x100418a2  push    eax
0x100418a3  sub     esp, 4C4h
0x100418a9  mov     eax, ___security_cookie
0x100418ae  xor     eax, ebp
0x100418b0  mov     [ebp+var_10], eax
0x100418b3  push    ebx
0x100418b4  push    esi
0x100418b5  push    edi; int
0x100418b6  push    eax; struct _GUID *
0x100418b7  lea     eax, [ebp+var_C]
0x100418ba  mov     large fs:0, eax
0x100418c0  mov     eax, [ebp+arg_4]
0x100418c3  xor     ecx, ecx
0x100418c5  mov     ebx, [ebp+this]
0x100418c8  mov     edi, [ebp+arg_C]
0x100418cb  mov     [ebp+Size], eax
0x100418d1  mov     eax, [ebp+arg_8]
0x100418d4  mov     [ebp+var_4A4], ebx
0x100418da  mov     [ebp+var_4AC], eax
0x100418e0  mov     [ebp+var_4B0], edi
0x100418e6  mov     [ebp+var_4A0], 0
0x100418f0  mov     [ebp+columnid], ecx
0x100418f6  mov     [ebp+tableid], 0FFFFFFFFh
0x10041900  mov     [ebp+var_4B8], ecx
0x10041906  test    eax, eax
0x10041908  jz      short loc_1004190C
0x1004190a  mov     [eax], ecx
0x1004190c  test    edi, edi
0x1004190e  jz      short loc_10041912
0x10041910  mov     [edi], ecx
0x10041912  push    0; perrinfo
0x10041914  push    0; dwReserved
0x10041916  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004191c  mov     esi, [ebx+8]
0x1004191f  add     esi, 64h ; 'd'
0x10041922  push    esi; lpCriticalSection
0x10041923  mov     [ebp+var_4BC], esi
0x10041929  mov     [ebp+var_4D0], esi
0x1004192f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10041935  mov     eax, [ebp+Size]
0x1004193b  mov     [ebp+var_4], 0
0x10041942  test    eax, eax
0x10041944  jz      loc_10041E3E
0x1004194a  cmp     [ebp+var_4AC], 0
0x10041951  jz      loc_10041E3E
0x10041957  test    edi, edi
0x10041959  jz      loc_10041E3E
0x1004195f  push    eax; struct _TRUSTEE_W *
0x10041960  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x10041965  test    eax, eax
0x10041967  jnz     short loc_10041973
0x10041969  mov     edi, 80040E6Ah
0x1004196e  jmp     loc_10041E43
0x10041973  mov     ecx, [ebx+8]
0x10041976  lea     eax, [ebp+var_4A0]
0x1004197c  add     ecx, 40h ; '@'; this
0x1004197f  push    eax; int *
0x10041980  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x10041985  mov     edi, eax
0x10041987  mov     [ebp+var_498], edi
0x1004198d  test    edi, edi
0x1004198f  js      loc_10041E0F
0x10041995  mov     ecx, [ebx+8]
0x10041998  lea     eax, [ebp+var_4B8]
0x1004199e  push    eax; int *
0x1004199f  lea     eax, [ebp+var_4A0]
0x100419a5  add     ecx, 40h ; '@'; this
0x100419a8  push    eax; int *
0x100419a9  call    ?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z; CSecuritySession::CheckForSecurityDbid(long &,int &)
0x100419ae  mov     edi, eax
0x100419b0  mov     [ebp+var_498], edi
0x100419b6  test    edi, edi
0x100419b8  js      short loc_100419D1
0x100419ba  mov     eax, [ebp+Size]
0x100419c0  cmp     dword ptr [eax+0Ch], 2
0x100419c4  jz      short loc_100419E9
0x100419c6  mov     edi, 80040E6Ch
0x100419cb  mov     [ebp+var_498], edi
0x100419d1  mov     ebx, [ebp+var_4A0]
0x100419d7  cmp     [ebp+var_4B8], 0
0x100419de  jnz     loc_10041E57
0x100419e4  jmp     loc_10041E15
0x100419e9  mov     eax, [ebx+8]
0x100419ec  lea     ecx, [ebp+var_4A0]
0x100419f2  push    ecx; unsigned int
0x100419f3  lea     ecx, [ebp+tableid]
0x100419f9  push    ecx; unsigned int
0x100419fa  mov     edx, [eax+48h]
0x100419fd  mov     ecx, [eax+44h]
0x10041a00  push    20h ; ' '; void *
0x10041a02  sub     esp, 8
0x10041a05  push    offset aMsysgroups; "MSysGroups"
0x10041a0a  call    ?JOLTJetOpenTable@CJOLT@@SGJKKPAGPBXKKPAKAAJ@Z; CJOLT::JOLTJetOpenTable(ulong,ulong,ushort *,void const *,ulong,ulong,ulong *,long &)
0x10041a0f  mov     edi, eax
0x10041a11  mov     [ebp+var_498], eax
0x10041a17  test    edi, edi
0x10041a19  js      short loc_100419D1
0x10041a1b  mov     eax, [ebx+8]
0x10041a1e  push    offset aGroupsid; "GroupSID"
0x10041a23  push    [ebp+tableid]
0x10041a29  push    dword ptr [eax+44h]
0x10041a2c  call    ds:__imp__JetSetCurrentIndex@12; JetSetCurrentIndex(x,x,x)
0x10041a32  mov     ebx, eax
0x10041a34  mov     [ebp+var_4A0], ebx
0x10041a3a  test    ebx, ebx
0x10041a3c  jns     short loc_10041A4B
0x10041a3e  mov     edi, 80004005h
0x10041a43  mov     [ebp+var_498], edi
0x10041a49  jmp     short loc_100419D7
0x10041a4b  mov     ebx, [ebp+var_4A4]
0x10041a51  lea     ecx, [ebp+var_4A0]
0x10041a57  mov     edx, [ebp+Size]
0x10041a5d  push    ecx; unsigned int *
0x10041a5e  lea     ecx, [ebp+var_4C4]
0x10041a64  mov     eax, [ebx+8]
0x10041a67  mov     edx, [edx+10h]
0x10041a6a  push    ecx; unsigned int
0x10041a6b  lea     ecx, [ebp+cbData]
0x10041a71  push    ecx; void *
0x10041a72  push    ecx; unsigned __int16 *
0x10041a73  lea     ecx, [ebp+pvData]
0x10041a79  push    ecx; unsigned int
0x10041a7a  mov     ecx, [eax+44h]
0x10041a7d  call    ?JOLTJetGetSidFromName@CJOLT@@SGJKPBGPAXKPAKPAJAAJ@Z; CJOLT::JOLTJetGetSidFromName(ulong,ushort const *,void *,ulong,ulong *,long *,long &)
0x10041a82  mov     edi, eax
0x10041a84  mov     [ebp+var_498], edi
0x10041a8a  test    edi, edi
0x10041a8c  js      loc_100419D1
0x10041a92  push    1; grbit
0x10041a94  push    [ebp+cbData]; cbData
0x10041a9a  lea     eax, [ebp+pvData]
0x10041aa0  push    eax; pvData
0x10041aa1  mov     eax, [ebx+8]
0x10041aa4  push    [ebp+tableid]; tableid
0x10041aaa  push    dword ptr [eax+44h]; sesid
0x10041aad  call    ds:__imp__JetMakeKey@20; JetMakeKey(x,x,x,x,x)
0x10041ab3  mov     ebx, eax
0x10041ab5  test    ebx, ebx
0x10041ab7  jns     short loc_10041AC9
0x10041ab9  mov     edi, 80004005h
0x10041abe  mov     [ebp+var_498], edi
0x10041ac4  jmp     loc_100419D7
0x10041ac9  mov     eax, [ebp+var_4A4]
0x10041acf  push    80h; grbit
0x10041ad4  push    [ebp+tableid]; tableid
0x10041ada  mov     eax, [eax+8]
0x10041add  push    dword ptr [eax+44h]; sesid
0x10041ae0  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x10041ae6  mov     ebx, eax
0x10041ae8  cmp     ebx, 0FFFFF9BFh
0x10041aee  jz      loc_10041E08
0x10041af4  test    ebx, ebx
0x10041af6  jz      short loc_10041B08
0x10041af8  mov     edi, 80004005h
0x10041afd  mov     [ebp+var_498], edi
0x10041b03  jmp     loc_100419D7
0x10041b08  mov     eax, [ebp+var_4A4]
0x10041b0e  push    5; grbit
0x10041b10  push    [ebp+tableid]; tableidSrc
0x10041b16  mov     eax, [eax+8]
0x10041b19  push    dword ptr [eax+44h]; sesid
0x10041b1c  call    ds:__imp__JetSetIndexRange@12; JetSetIndexRange(x,x,x)
0x10041b22  mov     ebx, eax
0x10041b24  test    ebx, ebx
0x10041b26  jns     short loc_10041B38
0x10041b28  mov     edi, 80004005h
0x10041b2d  mov     [ebp+var_498], edi
0x10041b33  jmp     loc_100419D7
0x10041b38  mov     eax, [ebp+var_4A4]
0x10041b3e  push    1; grbit
0x10041b40  push    [ebp+tableid]; tableid
0x10041b46  mov     eax, [eax+8]
0x10041b49  push    dword ptr [eax+44h]; sesid
0x10041b4c  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x10041b52  mov     ebx, eax
0x10041b54  cmp     ebx, 0FFFFF9BFh
0x10041b5a  jz      loc_10041E08
0x10041b60  test    ebx, ebx
0x10041b62  jz      short loc_10041B74
0x10041b64  mov     edi, 80004005h
0x10041b69  mov     [ebp+var_498], edi
0x10041b6f  jmp     loc_100419D7
0x10041b74  mov     esi, [ebp+var_4A4]
0x10041b7a  nop     word ptr [eax+eax+00h]
0x10041b80  mov     eax, [esi+8]
0x10041b83  inc     [ebp+columnid]
0x10041b89  push    0; grbit
0x10041b8b  push    1; cRow
0x10041b8d  push    [ebp+tableid]; tableid
0x10041b93  push    dword ptr [eax+44h]; sesid
0x10041b96  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10041b9c  test    eax, eax
0x10041b9e  jns     short loc_10041B80
0x10041ba0  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10041ba6  xor     ebx, ebx
0x10041ba8  mov     eax, [ecx]
0x10041baa  mov     edi, [eax+0Ch]
0x10041bad  mov     eax, [ebp+columnid]
0x10041bb3  lea     eax, [eax+eax*4]
0x10041bb6  shl     eax, 2
0x10041bb9  push    eax
0x10041bba  push    ecx
0x10041bbb  mov     ecx, edi
0x10041bbd  mov     [ebp+Size], eax
0x10041bc3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10041bc9  call    edi
0x10041bcb  mov     ecx, [ebp+var_4B0]
0x10041bd1  mov     esi, [ebp+var_4BC]
0x10041bd7  mov     [ecx], eax
0x10041bd9  test    eax, eax
0x10041bdb  jnz     short loc_10041BED
0x10041bdd  mov     edi, 8007000Eh
0x10041be2  mov     [ebp+var_498], edi
0x10041be8  jmp     loc_100419D7
0x10041bed  push    [ebp+Size]; Size
0x10041bf3  push    0; Val
0x10041bf5  push    eax; void *
0x10041bf6  call    _memset
0x10041bfb  mov     eax, [ebp+var_4AC]
0x10041c01  add     esp, 0Ch
0x10041c04  mov     edi, [ebp+var_4A4]
0x10041c0a  mov     ecx, [ebp+columnid]
0x10041c10  mov     [eax], ecx
0x10041c12  mov     eax, [edi+8]
0x10041c15  push    1; grbit
0x10041c17  push    [ebp+tableid]; tableid
0x10041c1d  push    dword ptr [eax+44h]; sesid
0x10041c20  call    ds:__imp__JetSeek@12; JetSeek(x,x,x)
0x10041c26  mov     ebx, eax
0x10041c28  mov     [ebp+var_4A0], ebx
0x10041c2e  cmp     ebx, 0FFFFF9BFh
0x10041c34  jz      loc_10041DFB
0x10041c3a  test    ebx, ebx
0x10041c3c  jz      short loc_10041C4E
0x10041c3e  mov     edi, 80004005h
0x10041c43  mov     [ebp+var_498], edi
0x10041c49  jmp     loc_100419D7
0x10041c4e  mov     ecx, [edi+8]
0x10041c51  lea     eax, [ebp+var_4A0]
0x10041c57  push    eax; int *
0x10041c58  lea     eax, [ebp+columnid]
0x10041c5e  add     ecx, 40h ; '@'; this
0x10041c61  push    eax; unsigned int *
0x10041c62  push    offset aUsersid; "UserSID"
0x10041c67  push    [ebp+tableid]; unsigned int
0x10041c6d  call    ?FindColid@CSecuritySession@@QAEJKPBGAAKAAJ@Z; CSecuritySession::FindColid(ulong,ushort const *,ulong &,long &)
0x10041c72  mov     edi, eax
0x10041c74  mov     [ebp+var_498], edi
0x10041c7a  test    edi, edi
0x10041c7c  js      loc_100419D1
0x10041c82  mov     eax, [ebp+var_4AC]
0x10041c88  mov     [ebp+Size], 0
0x10041c92  cmp     dword ptr [eax], 0
0x10041c95  jbe     loc_100419D1
0x10041c9b  mov     edi, [ebp+var_4A4]
0x10041ca1  push    0; pretinfo
0x10041ca3  push    0; grbit
0x10041ca5  lea     eax, [ebp+pcbActual]
0x10041cab  push    eax; pcbActual
0x10041cac  push    1FFh; cbData
0x10041cb1  lea     eax, [ebp+var_494]
0x10041cb7  push    eax; pvData
0x10041cb8  push    [ebp+columnid]; columnid
0x10041cbe  mov     eax, [edi+8]
0x10041cc1  push    [ebp+tableid]; tableid
0x10041cc7  push    dword ptr [eax+44h]; sesid
0x10041cca  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10041cd0  mov     ebx, eax
0x10041cd2  test    ebx, ebx
0x10041cd4  js      loc_10041A3E
0x10041cda  lea     eax, [ebp+var_4C4]
0x10041ce0  push    eax
0x10041ce1  push    40h ; '@'
0x10041ce3  lea     eax, [ebp+var_94]
0x10041ce9  push    eax
0x10041cea  push    [ebp+pcbActual]
0x10041cf0  lea     eax, [ebp+var_494]
0x10041cf6  push    eax
0x10041cf7  mov     eax, [edi+8]
0x10041cfa  push    dword ptr [eax+44h]
0x10041cfd  call    ds:__imp__JetGetNameFromSid@24; JetGetNameFromSid(x,x,x,x,x,x)
0x10041d03  mov     ebx, eax
0x10041d05  test    ebx, ebx
0x10041d07  js      loc_10041A3E
0x10041d0d  mov     ecx, [ebp+var_4B0]
0x10041d13  mov     eax, [ebp+Size]
0x10041d19  lea     edx, [eax+eax*4]
0x10041d1c  mov     eax, [ecx]
0x10041d1e  shl     edx, 2
0x10041d21  mov     [ebp+var_4A0], edx
0x10041d27  mov     dword ptr [edx+eax], 0
0x10041d2e  mov     eax, [ecx]
0x10041d30  mov     dword ptr [edx+eax+4], 0
0x10041d38  mov     eax, [ecx]
  ... truncated ...
```
