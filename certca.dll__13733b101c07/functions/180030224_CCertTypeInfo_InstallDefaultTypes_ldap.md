# CCertTypeInfo::InstallDefaultTypes(ldap *)

- ea: `0x180030224`
- end: `0x1800308b7`
- name: `?InstallDefaultTypes@CCertTypeInfo@@SAJPEAUldap@@@Z`
- size: `1683`
- prototype: `__int64 __fastcall(struct ldap *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e6c0`

## callees

- `0x180005944`
- `0x180005f00`
- `0x1800062d0`
- `0x180008400`
- `0x180008420`
- `0x180008610`
- `0x18000a630`
- `0x18000d520`
- `0x18000e52c`
- `0x1800103cc`
- `0x180011600`
- `0x180012260`
- `0x180014fac`
- `0x18002fa14`
- `0x1800300f8`
- `0x180030224`
- `0x1800308c0`
- `0x180030c18`
- `0x180030ec0`
- `0x180031990`
- `0x1800328a4`
- `0x180033144`
- `0x180033314`
- `0x180033b78`
- `0x180033f70`
- `0x1800382c0`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800303a8`
- `msvcrt!wcsstr` at `0x1800303f6`
- `msvcrt!wcsstr` at `0x1800303a8`
- `msvcrt!wcsstr` at `0x1800303f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030315`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800307a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030315`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800307a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030855`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030863`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030871`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030855`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030863`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030871`
- `WLDAP32!__imp_ldap_unbind` at `0x18003087f`
- `WLDAP32!__imp_ldap_unbind` at `0x18003087f`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800303bd`
- `WLDAP32!__imp_ldap_add_sW` at `0x18003040b`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800304b5`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800307fb`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800303bd`
- `WLDAP32!__imp_ldap_add_sW` at `0x18003040b`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800304b5`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800307fb`

## string_xrefs

- `0x180030487`: `CN=OID,CN=Public Key Services,CN=Services,`
- `0x180030340`: `CN=Certificate Templates,CN=Public Key Services,CN=Services,`
- `0x1800307c6`: `CN=Enrollment Services,CN=Public Key Services,CN=Services,`
- `0x18003039e`: `CN=Public Key Services`
- `0x1800303ec`: `CN=Certificate Templates`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::InstallDefaultTypes(struct ldap *a1)
{
  struct ldap *v1; // r14
  unsigned __int16 *v2; // rsi
  LDAP *v3; // r15
  int v4; // eax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // r12
  WCHAR *v7; // rdi
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // r13
  __int64 v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned __int64 v13; // rbx
  LDAP *v14; // rax
  int v15; // edx
  unsigned int v16; // ecx
  WCHAR *v17; // rax
  ULONG v18; // eax
  unsigned int v19; // r9d
  WCHAR *v20; // rax
  ULONG v21; // eax
  unsigned int v22; // r9d
  __int64 v23; // rax
  unsigned __int64 v24; // rbx
  unsigned __int16 *v25; // r10
  unsigned __int16 *v26; // r10
  ULONG v27; // eax
  unsigned int v28; // r9d
  unsigned int v29; // esi
  struct CCertTypeInfo *v30; // rdi
  PCNZWCH *v31; // rbx
  CCertTypeInfo *v32; // rsi
  int IsValidSecurityOwner; // ebx
  int IsValidKeySecurityOCSP; // eax
  int v35; // esi
  int v36; // ebx
  unsigned int v37; // edx
  int v38; // r8d
  int updated; // eax
  CCertTypeInfo *v40; // rax
  int v41; // eax
  int v42; // r8d
  unsigned int v43; // edx
  int v44; // eax
  unsigned int v45; // edx
  int v46; // edx
  unsigned int v47; // ecx
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned __int16 *v50; // rdi
  unsigned __int16 *v51; // rax
  int v52; // edx
  unsigned int v53; // ecx
  ULONG v54; // eax
  unsigned int v55; // r9d
  unsigned __int16 **v57; // [rsp+20h] [rbp-79h]
  unsigned __int16 **v58; // [rsp+20h] [rbp-79h]
  WCHAR *dn; // [rsp+30h] [rbp-69h]
  LDAP *ld; // [rsp+38h] [rbp-61h] BYREF
  int v61; // [rsp+40h] [rbp-59h]
  struct CCertTypeInfo *v62; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v63; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v64; // [rsp+58h] [rbp-41h]
  LDAPModW *attrs[2]; // [rsp+60h] [rbp-39h] BYREF
  __int128 v66; // [rsp+70h] [rbp-29h] BYREF
  __int128 *v67; // [rsp+80h] [rbp-19h]
  CCertTypeInfo *v68; // [rsp+88h] [rbp-11h]
  __int128 v69; // [rsp+90h] [rbp-9h] BYREF
  __int64 v70; // [rsp+A0h] [rbp+7h]

  v1 = a1;
  v66 = 0;
  v67 = 0;
  v2 = 0;
  v62 = 0;
  v69 = 0;
  v70 = 0;
  *(_OWORD *)attrs = 0;
  v63 = 0;
  v3 = 0;
  ld = 0;
  if ( !a1 )
  {
    v4 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, &ld, 0);
    v5 = v4;
    if ( v4 )
    {
      CSPrintErrorLineFile(0x9E0336u, v4);
      CSPrintErrorLineFile(0x1F050328u, v5);
      v3 = ld;
      goto LABEL_104;
    }
    v3 = ld;
    v1 = ld;
  }
  v6 = 0;
  v64 = 0;
  v7 = 0;
  v8 = CAGetAuthoritativeDomainDn(v1, 0, &v63);
  v5 = v8;
  if ( v8 )
  {
    v9 = 520618792;
LABEL_7:
    CSPrintErrorLineFile(v9, v8);
    goto LABEL_96;
  }
  v10 = -1;
  v11 = -1;
  v12 = v63;
  do
    ++v11;
  while ( v63[v11] );
  v13 = v11 + 61;
  v14 = (LDAP *)LocalAlloc(0, 2 * (v11 + 61));
  v2 = (unsigned __int16 *)v14;
  ld = v14;
  if ( !v14 )
  {
    v15 = -2147024882;
    v5 = -2147024882;
    v16 = 521077544;
LABEL_12:
    CSPrintErrorLineFile(v16, v15);
    v7 = 0;
    goto LABEL_96;
  }
  StringCchCopyW((unsigned __int16 *)v14, v13, L"CN=Certificate Templates,CN=Public Key Services,CN=Services,");
  StringCchCatW(v2, v13, v12);
  attrs[0] = (LDAPModW *)&v66;
  attrs[1] = 0;
  LODWORD(v66) = 0;
  *((_QWORD *)&v66 + 1) = L"objectclass";
  v67 = &v69;
  *(_QWORD *)&v69 = L"top";
  *((_QWORD *)&v69 + 1) = L"container";
  v70 = 0;
  v17 = wcsstr(v2, L"CN=Public Key Services");
  if ( v17 )
  {
    v18 = ldap_add_sW(v1, v17, attrs);
    if ( v18 )
    {
      if ( v18 != 68 && v18 != 50 )
      {
        v5 = myHLdapError3(v1, v18, 0, v19, v57);
        v15 = v5;
        v16 = 522781480;
        goto LABEL_12;
      }
    }
  }
  v20 = wcsstr(v2, L"CN=Certificate Templates");
  if ( v20 )
  {
    v21 = ldap_add_sW(v1, v20, attrs);
    if ( v21 )
    {
      if ( v21 != 68 && v21 != 50 )
      {
        v5 = myHLdapError3(v1, v21, 0, v22, v57);
        v15 = v5;
        v16 = 523567912;
        goto LABEL_12;
      }
    }
  }
  v23 = -1;
  do
    ++v23;
  while ( v12[v23] );
  v24 = v23 + 43;
  v25 = (unsigned __int16 *)LocalAlloc(0, 2 * (v23 + 43));
  dn = v25;
  if ( !v25 )
  {
    v5 = -2147024882;
    CSPrintErrorLineFile(0x1F3E0328u, -2147024882);
    v7 = 0;
    goto LABEL_96;
  }
  *((_QWORD *)&v69 + 1) = L"msPKI-Enterprise-Oid";
  StringCchCopyW(v25, v24, L"CN=OID,CN=Public Key Services,CN=Services,");
  StringCchCatW(v26, v24, v12);
  v7 = dn;
  v27 = ldap_add_sW(v1, dn, attrs);
  if ( v27 && v27 != 68 && v27 != 50 )
  {
    v8 = myHLdapError3(v1, v27, 0, v28, v57);
    v5 = v8;
    v9 = 524878632;
    goto LABEL_7;
  }
  v5 = CCertTypeInfo::_EnumFromDS(v1, 0x4C0u, 6u, 0, &v62);
  if ( v5 )
  {
    CSPrintErrorLineFile(0x1F530328u, v5);
    goto LABEL_94;
  }
  v29 = 0;
  v61 = 0;
  while ( (unsigned int)v6 < 0x21 )
  {
    v30 = v62;
    if ( v62 )
    {
      v31 = (PCNZWCH *)(&g_aDefaultCertTypes + 19 * (unsigned int)v6);
      v32 = 0;
      while ( (unsigned int)mylstrcmpNLSub(*v31, *((const unsigned __int16 **)v30 + 1), -1, 1) )
      {
        v30 = (struct CCertTypeInfo *)*((_QWORD *)v30 + 19);
        if ( !v30 )
          goto LABEL_55;
      }
      if ( (unsigned int)IsDSInfoNewer(v30, (struct _CERT_TYPE_DEFAULT *)v31) )
      {
        IsValidSecurityOwner = CCertTypeInfo::IsValidSecurityOwner(v30);
        IsValidKeySecurityOCSP = CCertTypeInfo::IsValidKeySecurityOCSP(v30);
        v35 = IsValidKeySecurityOCSP;
        if ( IsValidSecurityOwner )
        {
          if ( IsValidKeySecurityOCSP )
            goto LABEL_43;
LABEL_50:
          updated = CCertTypeInfo::_UpdateKeySecurityOCSP(v30);
          v36 = updated;
          if ( updated )
          {
            v38 = updated;
            v37 = 529466152;
            goto LABEL_48;
          }
LABEL_52:
          v36 = CCertTypeInfo::_UpdateToDS(v30, v1);
          if ( !v36 )
            goto LABEL_43;
          v37 = 529924904;
        }
        else
        {
          v36 = CCertTypeInfo::_UpdateSecurityOwner(v30);
          if ( !v36 )
          {
            if ( !v35 )
              goto LABEL_50;
            goto LABEL_52;
          }
          v37 = 528810792;
        }
        v38 = v36;
LABEL_48:
        CSPrintErrorLineFileData2(*((const unsigned __int16 **)v30 + 1), v37, v38, 0);
        goto LABEL_74;
      }
    }
    else
    {
      v32 = 0;
    }
LABEL_55:
    v40 = (CCertTypeInfo *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v40;
    if ( v40 )
      v32 = CCertTypeInfo::CCertTypeInfo(v40, 1);
    if ( !v32 )
    {
      v46 = -2147024882;
      v5 = -2147024882;
      v47 = 530449192;
LABEL_76:
      CSPrintErrorLineFile(v47, v46);
      v6 = v64;
      goto LABEL_93;
    }
    v41 = CCertTypeInfo::_LoadFromDefaults(
            v32,
            (struct _CERT_TYPE_DEFAULT *)(&g_aDefaultCertTypes + 19 * (unsigned int)v6),
            0);
    v36 = v41;
    if ( v41 )
    {
      v42 = v41;
      v43 = 531039016;
    }
    else
    {
      if ( !v30 )
        goto LABEL_69;
      v36 = CCertTypeInfo::SetSecurity(v32, *((void **)v30 + 17));
      if ( v36 )
      {
        v42 = v36;
        v43 = 531694376;
      }
      else
      {
        if ( !*((_DWORD *)v30 + 22) )
        {
          v44 = CCertTypeInfo::_UpdateSecurity(v32);
          v36 = v44;
          if ( v44 )
          {
            v43 = 532546344;
            goto LABEL_71;
          }
        }
        v36 = CCertTypeInfo::_UpdateSecurityOwner(v32);
        if ( !v36 )
        {
          *((_DWORD *)v32 + 30) = 0;
          *((_DWORD *)v32 + 32) = 1;
          *((_DWORD *)v32 + 47) = 1;
LABEL_69:
          v44 = CCertTypeInfo::_UpdateToDS(v32, v1);
          v36 = v44;
          if ( !v44 )
            goto LABEL_73;
          v43 = 533791528;
LABEL_71:
          v42 = v44;
          goto LABEL_72;
        }
        v42 = v36;
        v43 = 533136168;
      }
    }
LABEL_72:
    CSPrintErrorLineFileData2(*((const unsigned __int16 **)v32 + 1), v43, v42, 0);
LABEL_73:
    CCertTypeInfo::`scalar deleting destructor'(v32, v45);
    if ( !v36 )
    {
LABEL_43:
      v29 = v61;
      goto LABEL_44;
    }
LABEL_74:
    v29 = v36;
    v61 = v36;
LABEL_44:
    LODWORD(v6) = (_DWORD)v6 + 1;
  }
  if ( v62 )
  {
    CCertTypeInfo::Release(v62);
    v62 = 0;
  }
  v48 = CCertTypeInfo::_EnumFromDS(v1, 0x4C0u, 6u, 0, &v62);
  v5 = v48;
  if ( v48 )
  {
    v46 = v48;
    v47 = 535626536;
    goto LABEL_76;
  }
  v49 = InstallDefaultOID(v1);
  v5 = v49;
  if ( v49 )
  {
    v46 = v49;
    v47 = 535888680;
    goto LABEL_76;
  }
  v50 = v63;
  do
    ++v10;
  while ( v63[v10] );
  v51 = (unsigned __int16 *)LocalAlloc(0, 2 * (v10 + 59));
  v6 = v51;
  if ( !v51 )
  {
    v52 = -2147024882;
    v5 = -2147024882;
    v53 = 536412968;
    goto LABEL_87;
  }
  StringCchCopyW(v51, v10 + 59, L"CN=Enrollment Services,CN=Public Key Services,CN=Services,");
  StringCchCatW(v6, v10 + 59, v50);
  *((_QWORD *)&v69 + 1) = L"container";
  v54 = ldap_add_sW(v1, v6, attrs);
  if ( !v54 || v54 == 68 || v54 == 50 )
  {
    v5 = v29;
  }
  else
  {
    v5 = myHLdapError3(v1, v54, 0, v55, v58);
    v52 = v5;
    v53 = 537133864;
LABEL_87:
    CSPrintErrorLineFile(v53, v52);
  }
LABEL_93:
  v7 = dn;
  v2 = (unsigned __int16 *)ld;
LABEL_94:
  if ( v62 )
    CCertTypeInfo::Release(v62);
LABEL_96:
  if ( v63 )
    CertFreeString(v63);
  if ( v2 )
    LocalFree(v2);
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
LABEL_104:
  if ( v3 )
    ldap_unbind(v3);
  if ( v5 )
    CSPrintErrorLineFile(0x20230328u, v5);
  return v5;
}

```

## disassembly

```asm
0x180030224  push    rbp
0x180030226  push    rbx
0x180030227  push    rsi
0x180030228  push    rdi
0x180030229  push    r12
0x18003022b  push    r13
0x18003022d  push    r14
0x18003022f  push    r15
0x180030231  lea     rbp, [rsp-1Fh]
0x180030236  sub     rsp, 0B8h
0x18003023d  mov     rax, cs:__security_cookie
0x180030244  xor     rax, rsp
0x180030247  mov     [rbp+57h+var_48], rax
0x18003024b  mov     r14, rcx
0x18003024e  xorps   xmm0, xmm0
0x180030251  xor     eax, eax
0x180030253  movups  [rbp+57h+var_80], xmm0
0x180030257  mov     [rbp+57h+var_70], rax
0x18003025b  xor     esi, esi
0x18003025d  mov     [rbp+57h+var_A8], rsi
0x180030261  movups  [rbp+57h+var_60], xmm0
0x180030265  mov     [rbp+57h+var_50], rax
0x180030269  movups  xmmword ptr [rbp+57h+attrs], xmm0
0x18003026d  mov     [rbp+57h+var_A0], rsi
0x180030271  mov     r15d, esi
0x180030274  mov     [rbp+57h+ld], rsi
0x180030278  test    rcx, rcx
0x18003027b  jnz     short loc_1800302C8
0x18003027d  mov     [rsp+0F0h+var_C8], rsi
0x180030282  lea     rax, [rbp+57h+ld]
0x180030286  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 **
0x18003028b  xor     r9d, r9d
0x18003028e  lea     edx, [rcx+8]
0x180030291  lea     r8d, [rcx+2]
0x180030295  call    myRobustLdapBindEx
0x18003029a  mov     ebx, eax
0x18003029c  test    eax, eax
0x18003029e  jz      short loc_1800302C1
0x1800302a0  mov     edx, eax; int
0x1800302a2  mov     ecx, 9E0336h; unsigned int
0x1800302a7  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800302ac  mov     edx, ebx; int
0x1800302ae  mov     ecx, 1F050328h; unsigned int
0x1800302b3  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800302b8  mov     r15, [rbp+57h+ld]
0x1800302bc  jmp     loc_180030877
0x1800302c1  mov     r15, [rbp+57h+ld]
0x1800302c5  mov     r14, r15
0x1800302c8  mov     r12, rsi
0x1800302cb  mov     [rbp+57h+var_98], rsi
0x1800302cf  mov     rdi, rsi
0x1800302d2  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x1800302d6  xor     edx, edx; unsigned __int16 **
0x1800302d8  mov     rcx, r14; struct ldap *
0x1800302db  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x1800302e0  mov     ebx, eax
0x1800302e2  test    eax, eax
0x1800302e4  jz      short loc_1800302F7
0x1800302e6  mov     ecx, 1F080328h; unsigned int
0x1800302eb  mov     edx, eax; int
0x1800302ed  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800302f2  jmp     loc_18003083F
0x1800302f7  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800302fb  mov     rax, r13
0x1800302fe  mov     rdi, [rbp+57h+var_A0]
0x180030302  inc     rax
0x180030305  cmp     [rdi+rax*2], si
0x180030309  jnz     short loc_180030302
0x18003030b  lea     rbx, [rax+3Dh]
0x18003030f  lea     rdx, [rbx+rbx]; uBytes
0x180030313  xor     ecx, ecx; uFlags
0x180030315  call    cs:__imp_LocalAlloc
0x18003031b  mov     rsi, rax
0x18003031e  mov     [rbp+57h+ld], rax
0x180030322  test    rax, rax
0x180030325  jnz     short loc_180030340
0x180030327  mov     edx, 8007000Eh; int
0x18003032c  mov     ebx, edx
0x18003032e  mov     ecx, 1F0F0328h; unsigned int
0x180030333  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030338  mov     rdi, r12
0x18003033b  jmp     loc_18003083F
0x180030340  lea     r8, aCnCertificateT_0; "CN=Certificate Templates,CN=Public Key "...
0x180030347  mov     rdx, rbx; unsigned __int64
0x18003034a  mov     rcx, rsi; unsigned __int16 *
0x18003034d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030352  mov     r8, rdi; unsigned __int16 *
0x180030355  mov     rdx, rbx; unsigned __int64
0x180030358  mov     rcx, rsi; unsigned __int16 *
0x18003035b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030360  lea     rax, [rbp+57h+var_80]
0x180030364  mov     [rbp+57h+attrs], rax
0x180030368  xor     ebx, ebx
0x18003036a  mov     [rbp+57h+attrs+8], rbx
0x18003036e  mov     dword ptr [rbp+57h+var_80], ebx
0x180030371  lea     rax, aObjectclass_2; "objectclass"
0x180030378  mov     qword ptr [rbp+57h+var_80+8], rax
0x18003037c  lea     rax, [rbp+57h+var_60]
0x180030380  mov     [rbp+57h+var_70], rax
0x180030384  lea     rax, aTop; "top"
0x18003038b  mov     qword ptr [rbp+57h+var_60], rax
0x18003038f  lea     rax, aContainer; "container"
0x180030396  mov     qword ptr [rbp+57h+var_60+8], rax
0x18003039a  mov     [rbp+57h+var_50], rbx
0x18003039e  lea     rdx, aCnPublicKeySer; "CN=Public Key Services"
0x1800303a5  mov     rcx, rsi; Str
0x1800303a8  call    cs:__imp_wcsstr
0x1800303ae  test    rax, rax
0x1800303b1  jz      short loc_1800303EC
0x1800303b3  lea     r8, [rbp+57h+attrs]; attrs
0x1800303b7  mov     rdx, rax; dn
0x1800303ba  mov     rcx, r14; ld
0x1800303bd  call    cs:__imp_ldap_add_sW
0x1800303c3  test    eax, eax
0x1800303c5  jz      short loc_1800303EC
0x1800303c7  cmp     eax, 44h ; 'D'
0x1800303ca  jz      short loc_1800303EC
0x1800303cc  cmp     eax, 32h ; '2'
0x1800303cf  jz      short loc_1800303EC
0x1800303d1  xor     r8d, r8d; unsigned int
0x1800303d4  mov     edx, eax; unsigned int
0x1800303d6  mov     rcx, r14; ld
0x1800303d9  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x1800303de  mov     ebx, eax
0x1800303e0  mov     edx, eax
0x1800303e2  mov     ecx, 1F290328h
0x1800303e7  jmp     loc_180030333
0x1800303ec  lea     rdx, aCnCertificateT; "CN=Certificate Templates"
0x1800303f3  mov     rcx, rsi; Str
0x1800303f6  call    cs:__imp_wcsstr
0x1800303fc  test    rax, rax
0x1800303ff  jz      short loc_18003043A
0x180030401  lea     r8, [rbp+57h+attrs]; attrs
0x180030405  mov     rdx, rax; dn
0x180030408  mov     rcx, r14; ld
0x18003040b  call    cs:__imp_ldap_add_sW
0x180030411  test    eax, eax
0x180030413  jz      short loc_18003043A
0x180030415  cmp     eax, 44h ; 'D'
0x180030418  jz      short loc_18003043A
0x18003041a  cmp     eax, 32h ; '2'
0x18003041d  jz      short loc_18003043A
0x18003041f  xor     r8d, r8d; unsigned int
0x180030422  mov     edx, eax; unsigned int
0x180030424  mov     rcx, r14; ld
0x180030427  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18003042c  mov     ebx, eax
0x18003042e  mov     edx, eax
0x180030430  mov     ecx, 1F350328h
0x180030435  jmp     loc_180030333
0x18003043a  mov     rax, r13
0x18003043d  inc     rax
0x180030440  cmp     [rdi+rax*2], bx
0x180030444  jnz     short loc_18003043D
0x180030446  lea     rbx, [rax+2Bh]
0x18003044a  lea     rdx, [rbx+rbx]; uBytes
0x18003044e  xor     ecx, ecx; uFlags
0x180030450  call    cs:__imp_LocalAlloc
0x180030456  mov     r10, rax
0x180030459  mov     [rbp+57h+dn], rax
0x18003045d  test    rax, rax
0x180030460  jnz     short loc_18003047C
0x180030462  mov     edx, 8007000Eh; int
0x180030467  mov     ebx, edx
0x180030469  mov     ecx, 1F3E0328h; unsigned int
0x18003046e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030473  mov     rdi, [rbp+57h+dn]
0x180030477  jmp     loc_18003083F
0x18003047c  lea     rax, aMspkiEnterpris; "msPKI-Enterprise-Oid"
0x180030483  mov     qword ptr [rbp+57h+var_60+8], rax
0x180030487  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18003048e  mov     rdx, rbx; unsigned __int64
0x180030491  mov     rcx, r10; unsigned __int16 *
0x180030494  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030499  mov     r8, rdi; unsigned __int16 *
0x18003049c  mov     rdx, rbx; unsigned __int64
0x18003049f  mov     rcx, r10; unsigned __int16 *
0x1800304a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800304a7  lea     r8, [rbp+57h+attrs]; attrs
0x1800304ab  mov     rdi, [rbp+57h+dn]
0x1800304af  mov     rdx, rdi; dn
0x1800304b2  mov     rcx, r14; ld
0x1800304b5  call    cs:__imp_ldap_add_sW
0x1800304bb  test    eax, eax
0x1800304bd  jz      short loc_1800304E2
0x1800304bf  cmp     eax, 44h ; 'D'
0x1800304c2  jz      short loc_1800304E2
0x1800304c4  cmp     eax, 32h ; '2'
0x1800304c7  jz      short loc_1800304E2
0x1800304c9  xor     r8d, r8d; unsigned int
0x1800304cc  mov     edx, eax; unsigned int
0x1800304ce  mov     rcx, r14; ld
0x1800304d1  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x1800304d6  mov     ebx, eax
0x1800304d8  mov     ecx, 1F490328h
0x1800304dd  jmp     loc_1800302EB
0x1800304e2  lea     rax, [rbp+57h+var_A8]
0x1800304e6  mov     [rsp+0F0h+var_D0], rax; struct CCertTypeInfo **
0x1800304eb  xor     r9d, r9d; unsigned int
0x1800304ee  mov     edx, 4C0h; unsigned int
0x1800304f3  lea     r8d, [r9+6]; unsigned int
0x1800304f7  mov     rcx, r14; ld
0x1800304fa  call    ?_EnumFromDS@CCertTypeInfo@@KAJPEAUldap@@KKKPEAPEAV1@@Z; CCertTypeInfo::_EnumFromDS(ldap *,ulong,ulong,ulong,CCertTypeInfo * *)
0x1800304ff  mov     ebx, eax
0x180030501  xor     eax, eax
0x180030503  test    ebx, ebx
0x180030505  jz      short loc_180030518
0x180030507  mov     edx, ebx; int
0x180030509  mov     ecx, 1F530328h; unsigned int
0x18003050e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180030513  jmp     loc_180030831
0x180030518  mov     esi, eax
0x18003051a  mov     [rbp+57h+var_B0], eax
0x18003051d  lea     rbx, ?g_aDefaultCertTypes@@3PAU_CERT_TYPE_DEFAULT@@A; _CERT_TYPE_DEFAULT near * g_aDefaultCertTypes
0x180030524  cmp     r12d, 21h ; '!'
0x180030528  jnb     loc_180030730
0x18003052e  mov     rdi, [rbp+57h+var_A8]
0x180030532  test    rdi, rdi
0x180030535  jz      loc_180030609
0x18003053b  mov     eax, r12d
0x18003053e  imul    rcx, rax, 98h
0x180030545  add     rbx, rcx
0x180030548  xor     esi, esi
0x18003054a  mov     r9b, 1; bool
0x18003054d  mov     r8d, r13d; int
0x180030550  mov     rdx, [rdi+8]; unsigned __int16 *
0x180030554  mov     rcx, [rbx]; lpString1
0x180030557  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003055c  test    eax, eax
0x18003055e  jz      short loc_180030578
0x180030560  mov     rdi, [rdi+98h]
0x180030567  test    rdi, rdi
0x18003056a  jnz     short loc_18003054A
0x18003056c  lea     rbx, ?g_aDefaultCertTypes@@3PAU_CERT_TYPE_DEFAULT@@A; _CERT_TYPE_DEFAULT near * g_aDefaultCertTypes
0x180030573  jmp     loc_18003060B
0x180030578  mov     rdx, rbx; struct _CERT_TYPE_DEFAULT *
0x18003057b  mov     rcx, rdi; this
0x18003057e  call    ?IsDSInfoNewer@@YAHPEAVCCertTypeInfo@@PEAU_CERT_TYPE_DEFAULT@@@Z; IsDSInfoNewer(CCertTypeInfo *,_CERT_TYPE_DEFAULT *)
0x180030583  test    eax, eax
0x180030585  jz      short loc_18003056C
0x180030587  mov     rcx, rdi; this
0x18003058a  call    ?IsValidSecurityOwner@CCertTypeInfo@@QEAAHXZ; CCertTypeInfo::IsValidSecurityOwner(void)
0x18003058f  mov     ebx, eax
0x180030591  mov     rcx, rdi; this
0x180030594  call    ?IsValidKeySecurityOCSP@CCertTypeInfo@@QEAAHXZ; CCertTypeInfo::IsValidKeySecurityOCSP(void)
0x180030599  mov     esi, eax
0x18003059b  test    ebx, ebx
0x18003059d  jz      short loc_1800305AE
0x18003059f  test    eax, eax
0x1800305a1  jz      short loc_1800305D9
0x1800305a3  mov     esi, [rbp+57h+var_B0]
0x1800305a6  inc     r12d
0x1800305a9  jmp     loc_18003051D
0x1800305ae  mov     rcx, rdi; this
0x1800305b1  call    ?_UpdateSecurityOwner@CCertTypeInfo@@IEAAJXZ; CCertTypeInfo::_UpdateSecurityOwner(void)
0x1800305b6  mov     ebx, eax
0x1800305b8  test    eax, eax
0x1800305ba  jz      short loc_1800305D5
0x1800305bc  mov     edx, 1F850328h; unsigned int
0x1800305c1  mov     r8d, ebx; int
0x1800305c4  xor     r9d, r9d; int
0x1800305c7  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800305cb  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800305d0  jmp     loc_18003070C
0x1800305d5  test    esi, esi
0x1800305d7  jnz     short loc_1800305F1
0x1800305d9  mov     rcx, rdi; this
0x1800305dc  call    ?_UpdateKeySecurityOCSP@CCertTypeInfo@@IEAAJXZ; CCertTypeInfo::_UpdateKeySecurityOCSP(void)
0x1800305e1  mov     ebx, eax
0x1800305e3  test    eax, eax
0x1800305e5  jz      short loc_1800305F1
0x1800305e7  mov     r8d, eax
0x1800305ea  mov     edx, 1F8F0328h
0x1800305ef  jmp     short loc_1800305C4
0x1800305f1  mov     rdx, r14; struct ldap *
0x1800305f4  mov     rcx, rdi; this
0x1800305f7  call    ?_UpdateToDS@CCertTypeInfo@@IEAAJPEAUldap@@@Z; CCertTypeInfo::_UpdateToDS(ldap *)
0x1800305fc  mov     ebx, eax
0x1800305fe  test    eax, eax
0x180030600  jz      short loc_1800305A3
0x180030602  mov     edx, 1F960328h
0x180030607  jmp     short loc_1800305C1
0x180030609  xor     esi, esi
0x18003060b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030612  mov     ecx, 0C0h; unsigned __int64
0x180030617  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003061c  mov     [rbp+57h+var_68], rax
0x180030620  test    rax, rax
0x180030623  jz      short loc_180030635
0x180030625  mov     edx, 1; int
0x18003062a  mov     rcx, rax; this
0x18003062d  call    ??0CCertTypeInfo@@QEAA@H@Z; CCertTypeInfo::CCertTypeInfo(int)
0x180030632  mov     rsi, rax
0x180030635  test    rsi, rsi
0x180030638  jz      loc_180030716
0x18003063e  mov     eax, r12d
0x180030641  imul    rdx, rax, 98h
0x180030648  add     rdx, rbx; struct _CERT_TYPE_DEFAULT *
0x18003064b  xor     r8d, r8d; unsigned __int16 *
0x18003064e  mov     rcx, rsi; this
  ... truncated ...
```
