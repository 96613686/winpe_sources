# CCAInfo::Update(ldap *)

- ea: `0x1800365a4`
- end: `0x1800370f6`
- name: `?Update@CCAInfo@@QEAAJPEAUldap@@@Z`
- size: `2898`
- prototype: `__int64 __fastcall(CCAInfo *__hidden this, LDAP *ld)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002edb0`

## callees

- `0x180005944`
- `0x18000596c`
- `0x1800062d0`
- `0x180008400`
- `0x18000a320`
- `0x18000ac20`
- `0x18000e130`
- `0x180011600`
- `0x180012450`
- `0x18002e340`
- `0x1800365a4`
- `0x180038262`
- `0x1800382c0`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800368b1`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003690c`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036bc3`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036c07`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036c58`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036dba`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036f8a`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036f9e`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036fc5`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800368b1`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18003690c`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036bc3`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036c07`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036c58`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036dba`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036f8a`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036f9e`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180036fc5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180036ddd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180036ddd`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180036dcb`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180036dcb`
- `CRYPT32!CertNameToStrW` at `0x180036b9b`
- `CRYPT32!CertNameToStrW` at `0x180036c33`
- `CRYPT32!CertNameToStrW` at `0x180036b9b`
- `CRYPT32!CertNameToStrW` at `0x180036c33`
- `WLDAP32!__imp_ldap_unbind` at `0x1800370c1`
- `WLDAP32!__imp_ldap_unbind` at `0x1800370c1`
- `WLDAP32!__imp_ldap_add_ext_sW` at `0x180036f31`
- `WLDAP32!__imp_ldap_add_ext_sW` at `0x180036f31`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x180036f4c`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x180036f4c`

## string_xrefs

- `0x180036d61`: `nTSecurityDescriptor`
- `0x180036cfd`: `certificateTemplates`
- `0x18003695e`: `pKIEnrollmentService`

## pseudocode

```c
__int64 __fastcall CCAInfo::Update(CCAInfo *this, LDAP *ld)
{
  LDAP *v2; // r15
  LDAP *v4; // r12
  unsigned int v5; // edi
  int v6; // edx
  unsigned int v7; // ecx
  unsigned int DoesDSExist; // eax
  void (*v9)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rdx
  unsigned int v15; // edi
  DWORD v16; // eax
  DWORD csz; // r13d
  unsigned __int16 *v18; // r9
  __int64 v19; // rdi
  void *v20; // rcx
  __int64 v21; // rdi
  WCHAR *v22; // rdx
  ULONG v23; // r14d
  unsigned __int16 *v24; // rcx
  __int64 v26; // [rsp+38h] [rbp-330h] BYREF
  LDAP *v27; // [rsp+40h] [rbp-328h]
  LDAP *v28; // [rsp+48h] [rbp-320h] BYREF
  __int64 v29; // [rsp+50h] [rbp-318h] BYREF
  const WCHAR *v30; // [rsp+58h] [rbp-310h]
  unsigned __int16 **v31; // [rsp+60h] [rbp-308h] BYREF
  __int64 v32; // [rsp+68h] [rbp-300h] BYREF
  const unsigned __int16 *v33; // [rsp+70h] [rbp-2F8h]
  unsigned __int16 **v34; // [rsp+78h] [rbp-2F0h] BYREF
  __int64 v35; // [rsp+80h] [rbp-2E8h] BYREF
  const unsigned __int16 *v36; // [rsp+88h] [rbp-2E0h]
  unsigned __int16 **v37; // [rsp+90h] [rbp-2D8h] BYREF
  __int64 v38; // [rsp+98h] [rbp-2D0h] BYREF
  const WCHAR *v39; // [rsp+A0h] [rbp-2C8h]
  unsigned __int16 **v40; // [rsp+A8h] [rbp-2C0h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-2B8h] BYREF
  const WCHAR *v42; // [rsp+B8h] [rbp-2B0h]
  unsigned __int16 **v43; // [rsp+C0h] [rbp-2A8h] BYREF
  unsigned __int16 *v44; // [rsp+C8h] [rbp-2A0h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-298h]
  __int64 v46; // [rsp+D8h] [rbp-290h] BYREF
  const unsigned __int16 *v47; // [rsp+E0h] [rbp-288h]
  unsigned __int16 **v48; // [rsp+E8h] [rbp-280h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-278h] BYREF
  const unsigned __int16 *v50; // [rsp+F8h] [rbp-270h]
  unsigned __int16 **v51; // [rsp+100h] [rbp-268h] BYREF
  _QWORD v52[3]; // [rsp+108h] [rbp-260h] BYREF
  char v53; // [rsp+120h] [rbp-248h]
  int v54; // [rsp+121h] [rbp-247h]
  __int16 v55; // [rsp+125h] [rbp-243h]
  char v56; // [rsp+127h] [rbp-241h]
  _QWORD v57[3]; // [rsp+128h] [rbp-240h] BYREF
  char v58; // [rsp+140h] [rbp-228h]
  int v59; // [rsp+141h] [rbp-227h]
  __int16 v60; // [rsp+145h] [rbp-223h]
  char v61; // [rsp+147h] [rbp-221h]
  _QWORD v62[3]; // [rsp+148h] [rbp-220h] BYREF
  char v63; // [rsp+160h] [rbp-208h]
  int v64; // [rsp+161h] [rbp-207h]
  __int16 v65; // [rsp+165h] [rbp-203h]
  char v66; // [rsp+167h] [rbp-201h]
  unsigned int v67; // [rsp+168h] [rbp-200h]
  LDAP *v68; // [rsp+170h] [rbp-1F8h]
  __int128 v69; // [rsp+178h] [rbp-1F0h] BYREF
  __int128 v70; // [rsp+188h] [rbp-1E0h] BYREF
  __int128 v71; // [rsp+198h] [rbp-1D0h] BYREF
  __int128 v72; // [rsp+1A8h] [rbp-1C0h] BYREF
  __int128 v73; // [rsp+1B8h] [rbp-1B0h] BYREF
  __int128 v74; // [rsp+1C8h] [rbp-1A0h] BYREF
  __int128 *v75; // [rsp+1D8h] [rbp-190h]
  __int128 v76; // [rsp+1E0h] [rbp-188h] BYREF
  __int128 *v77; // [rsp+1F0h] [rbp-178h]
  __int128 v78; // [rsp+1F8h] [rbp-170h] BYREF
  __int128 *v79; // [rsp+208h] [rbp-160h]
  __int128 v80; // [rsp+210h] [rbp-158h] BYREF
  unsigned __int16 **v81; // [rsp+220h] [rbp-148h]
  __int128 v82; // [rsp+228h] [rbp-140h] BYREF
  __int128 *v83; // [rsp+238h] [rbp-130h]
  void (*v84)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+240h] [rbp-128h]
  __int128 v85; // [rsp+250h] [rbp-118h] BYREF
  __int64 v86; // [rsp+260h] [rbp-108h]
  LDAPModW *attrs; // [rsp+270h] [rbp-F8h] BYREF
  __int64 *v88; // [rsp+278h] [rbp-F0h]
  LDAPModW *mods; // [rsp+280h] [rbp-E8h] BYREF
  PLDAPControlW ServerControls[3]; // [rsp+2E0h] [rbp-88h] BYREF
  PLDAPControlW v91[3]; // [rsp+2F8h] [rbp-70h] BYREF
  int v92; // [rsp+310h] [rbp-58h] BYREF
  char v93; // [rsp+314h] [rbp-54h]
  int v94; // [rsp+318h] [rbp-50h] BYREF
  char v95; // [rsp+31Ch] [rbp-4Ch]
  unsigned __int16 v96[12]; // [rsp+320h] [rbp-48h] BYREF

  v2 = ld;
  v27 = ld;
  v68 = ld;
  v4 = 0;
  v28 = 0;
  v74 = 0;
  v75 = 0;
  v41 = 0;
  v42 = 0;
  v29 = 0;
  v30 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v38 = 0;
  v39 = 0;
  v35 = 0;
  v36 = 0;
  v76 = 0;
  v77 = 0;
  v82 = 0;
  v83 = 0;
  v32 = 0;
  v33 = 0;
  v46 = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v26 = 0;
  v85 = 0;
  v86 = 0;
  v45 = 0;
  memset_0(&attrs, 0, 0x70u);
  v71 = 0;
  v73 = 0;
  v70 = 0;
  v72 = 0;
  v92 = 16909104;
  v93 = 7;
  v57[0] = L"1.2.840.113556.1.4.801";
  v57[1] = 5;
  v57[2] = &v92;
  v58 = 1;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v52[0] = L"1.2.840.113556.1.4.1413";
  v52[1] = 0;
  v52[2] = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  ServerControls[0] = (PLDAPControlW)v57;
  ServerControls[1] = (PLDAPControlW)v52;
  ServerControls[2] = 0;
  v94 = 16909104;
  v95 = 4;
  v62[0] = L"1.2.840.113556.1.4.801";
  v62[1] = 5;
  v62[2] = &v94;
  v63 = 1;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v91[0] = (PLDAPControlW)v62;
  v91[1] = (PLDAPControlW)v52;
  v91[2] = 0;
  v69 = 0;
  v44 = 0;
  v43 = 0;
  v31 = 0;
  v40 = 0;
  v37 = 0;
  v34 = 0;
  v48 = 0;
  v51 = 0;
  if ( !*(_QWORD *)this )
  {
    v5 = -2147467261;
    v6 = -2147467261;
    v7 = 67633957;
LABEL_3:
    CSPrintErrorLineFile(v7, v6);
    goto LABEL_55;
  }
  DoesDSExist = myDoesDSExist(1);
  v5 = DoesDSExist;
  if ( DoesDSExist )
  {
    v6 = DoesDSExist;
    v7 = 67961637;
    goto LABEL_3;
  }
  v9 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v84 = v9;
  if ( v2 )
  {
    v4 = v2;
    v28 = v2;
  }
  else
  {
    v10 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, &v28, 0);
    v5 = v10;
    if ( v10 )
    {
      CSPrintErrorLineFile(0x4200325u, v10);
      _set_se_translator(v9);
      v4 = v28;
      goto LABEL_55;
    }
    v4 = v28;
  }
  LODWORD(v74) = 2;
  *((_QWORD *)&v74 + 1) = L"objectclass";
  v75 = &v85;
  *(_QWORD *)&v85 = L"top";
  *((_QWORD *)&v85 + 1) = L"pKIEnrollmentService";
  v86 = 0;
  attrs = (LDAPModW *)&v74;
  v11 = 1;
  LODWORD(v41) = 2;
  v42 = L"cn";
  if ( (unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"cn", &v43) || !v43 )
  {
    v43 = (unsigned __int16 **)&v26;
    v12 = (_DWORD *)((char *)this + 40);
    if ( !*((_DWORD *)this + 10) )
    {
      v88 = &v41;
      v11 = 2;
    }
  }
  else
  {
    v88 = &v41;
    v11 = 2;
    v12 = (_DWORD *)((char *)this + 40);
  }
  LODWORD(v29) = 2;
  v30 = L"displayName";
  if ( !(unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"displayName", &v31) && v31
    || (v31 = (unsigned __int16 **)&v26, !*v12) )
  {
    *(&attrs + v11++) = (LDAPModW *)&v29;
  }
  LODWORD(v76) = 2;
  *((_QWORD *)&v76 + 1) = L"flags";
  v77 = &v69;
  *(_QWORD *)&v69 = v96;
  *((_QWORD *)&v69 + 1) = 0;
  StringCchPrintfW(v96, 0xCu, L"%lu", *((unsigned int *)this + 13));
  *(&attrs + v11) = (LDAPModW *)&v76;
  v13 = v11 + 1;
  LODWORD(v78) = 130;
  *((_QWORD *)&v78 + 1) = L"cACertificate";
  v79 = &v70;
  *(_QWORD *)&v70 = &v71;
  *((_QWORD *)&v70 + 1) = 0;
  v14 = *(_QWORD *)this;
  LODWORD(v71) = *(_DWORD *)(*(_QWORD *)this + 16LL);
  *((_QWORD *)&v71 + 1) = *(_QWORD *)(v14 + 8);
  *(&attrs + v13) = (LDAPModW *)&v78;
  v15 = v13 + 1;
  v67 = v15;
  LODWORD(v80) = 2;
  *((_QWORD *)&v80 + 1) = L"cACertificateDN";
  v81 = &v44;
  v16 = CertNameToStrW(1u, (PCERT_NAME_BLOB)(*(_QWORD *)(v14 + 24) + 80LL), 0x2000003u, 0, 0);
  csz = v16;
  if ( !v16 )
  {
    v5 = myHLastError();
    CSPrintErrorLineFile(0x46C0325u, v5);
    _set_se_translator(v9);
    v2 = v27;
    goto LABEL_55;
  }
  v18 = CertAllocStringLen(0, v16);
  v44 = v18;
  if ( !v18 )
  {
    v5 = -2147024882;
    CSPrintErrorLineFile(0x4720325u, -2147024882);
    _set_se_translator(v9);
    v2 = v27;
    goto LABEL_55;
  }
  if ( !CertNameToStrW(1u, (PCERT_NAME_BLOB)(*(_QWORD *)(*(_QWORD *)this + 24LL) + 80LL), 0x2000003u, v18, csz) )
  {
    v5 = myHLastError();
    CSPrintErrorLineFile(0x47C0325u, v5);
    _set_se_translator(v9);
    v2 = v27;
    goto LABEL_55;
  }
  v45 = 0;
  *(&attrs + v67) = (LDAPModW *)&v80;
  v19 = v15 + 1;
  LODWORD(v38) = 2;
  v39 = L"dNSHostName";
  if ( !(unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"dNSHostName", &v40) && v40
    || (v40 = (unsigned __int16 **)&v26, !*v12) )
  {
    *(&attrs + (unsigned int)v19) = (LDAPModW *)&v38;
    v19 = (unsigned int)(v19 + 1);
  }
  LODWORD(v35) = 2;
  v36 = L"certificateTemplates";
  if ( !(unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"certificateTemplates", &v37) && v37
    || (v37 = (unsigned __int16 **)&v26, !*v12) )
  {
    *(&attrs + v19) = (LDAPModW *)&v35;
    v19 = (unsigned int)(v19 + 1);
  }
  LODWORD(v82) = 130;
  *((_QWORD *)&v82 + 1) = L"nTSecurityDescriptor";
  v83 = &v72;
  *(_QWORD *)&v72 = &v73;
  *((_QWORD *)&v72 + 1) = 0;
  v20 = (void *)*((_QWORD *)this + 7);
  if ( !v20 )
  {
    v5 = -2147023558;
    CSPrintErrorLineFile(0x4AC0325u, -2147023558);
    _set_se_translator(v9);
    v2 = v27;
    goto LABEL_55;
  }
  if ( IsValidSecurityDescriptor(v20) )
  {
    LODWORD(v73) = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 7));
    *((_QWORD *)&v73 + 1) = *((_QWORD *)this + 7);
    *(&attrs + v19) = (LDAPModW *)&v82;
    v21 = (unsigned int)(v19 + 1);
    LODWORD(v32) = 2;
    v33 = L"Description";
    if ( !(unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"Description", &v34) && v34
      || (v34 = (unsigned __int16 **)&v26, !*v12) )
    {
      *(&attrs + (unsigned int)v21) = (LDAPModW *)&v32;
      v21 = (unsigned int)(v21 + 1);
    }
    LODWORD(v46) = 2;
    v47 = L"msPKI-Enrollment-Servers";
    if ( !(unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"msPKI-Enrollment-Servers", &v48) && v48 )
    {
      *(&attrs + v21) = (LDAPModW *)&v46;
      v21 = (unsigned int)(v21 + 1);
    }
    LODWORD(v49) = 2;
    v50 = L"msPKI-Site-Name";
    if ( !(unsigned int)CCAInfo::GetProperty((CCAProperty **)this, L"msPKI-Site-Name", &v51) && v51 )
    {
      *(&attrs + v21) = (LDAPModW *)&v49;
      v21 = (unsigned int)(v21 + 1);
    }
    *(&attrs + v21) = 0;
    v5 = 0;
    v22 = (WCHAR *)*((_QWORD *)this + 4);
    if ( *v12 )
    {
      v23 = ldap_add_ext_sW(v4, v22, &attrs, ServerControls, 0);
    }
    else
    {
      v23 = ldap_modify_ext_sW(v4, v22, &mods, v91, 0);
      if ( v23 == 20 )
      {
LABEL_53:
        *v12 = 0;
        _set_se_translator(v9);
        v2 = v27;
        goto LABEL_55;
      }
    }
    if ( v23 && v23 != 68 )
    {
      v5 = myHLdapError3(v4, v23, 0);
      CSPrintErrorLineFile(0x5020325u, v23);
      _set_se_translator(v9);
      v2 = v27;
      goto LABEL_55;
    }
    goto LABEL_53;
  }
  v5 = -2147023558;
  CSPrintErrorLineFile(0x4B70325u, -2147023558);
  _set_se_translator(v9);
  v2 = v27;
LABEL_55:
  v24 = v44;
  if ( v44 )
    CertFreeString(v44);
  if ( v37 && &v26 != (__int64 *)v37 )
    CAFreeCertTypeExtensions(v24, v37);
  if ( v40 && &v26 != (__int64 *)v40 )
    CAFreeCertTypeExtensions(v24, v40);
  if ( v43 && &v26 != (__int64 *)v43 )
    CAFreeCertTypeExtensions(v24, v43);
  if ( v31 && &v26 != (__int64 *)v31 )
    CAFreeCertTypeExtensions(v24, v31);
  if ( v34 && &v26 != (__int64 *)v34 )
    CAFreeCertTypeExtensions(v24, v34);
  if ( v48 && &v26 != (__int64 *)v48 )
    CAFreeCertTypeExtensions(v24, v48);
  if ( v51 && &v26 != (__int64 *)v51 )
    CAFreeCertTypeExtensions(v24, v51);
  if ( v4 && v4 != v2 )
    ldap_unbind(v4);
  return v5;
}

```

## disassembly

```asm
0x1800365a4  mov     r11, rsp
0x1800365a7  mov     [r11+18h], rbx
0x1800365ab  mov     [r11+20h], rsi
0x1800365af  push    rdi
0x1800365b0  push    r12
0x1800365b2  push    r13
0x1800365b4  push    r14
0x1800365b6  push    r15
0x1800365b8  sub     rsp, 340h
0x1800365bf  mov     rax, cs:__security_cookie
0x1800365c6  xor     rax, rsp
0x1800365c9  mov     [rsp+368h+var_30], rax
0x1800365d1  mov     r15, rdx
0x1800365d4  mov     [rsp+368h+var_328], rdx
0x1800365d9  mov     r14, rcx
0x1800365dc  mov     [rsp+368h+var_1F8], rdx
0x1800365e4  xor     esi, esi
0x1800365e6  mov     r12d, esi
0x1800365e9  mov     [rsp+368h+var_320], rsi
0x1800365ee  xorps   xmm0, xmm0
0x1800365f1  xor     eax, eax
0x1800365f3  movups  [rsp+368h+var_1A0], xmm0
0x1800365fb  mov     [r11-190h], rax
0x180036602  mov     [r11-2B8h], rsi
0x180036609  mov     [r11-2B0h], rsi
0x180036610  mov     [rsp+368h+var_318], rsi
0x180036615  mov     [rsp+368h+var_310], rsi
0x18003661a  movups  [rsp+368h+var_170], xmm0
0x180036622  mov     [r11-160h], rax
0x180036629  xorps   xmm1, xmm1
0x18003662c  movups  [rsp+368h+var_158], xmm1
0x180036634  mov     [r11-148h], rax
0x18003663b  mov     [r11-2D0h], rsi
0x180036642  mov     [r11-2C8h], rsi
0x180036649  mov     [r11-2E8h], rsi
0x180036650  mov     [r11-2E0h], rsi
0x180036657  movups  [rsp+368h+var_188], xmm0
0x18003665f  mov     [r11-178h], rax
0x180036666  movups  [rsp+368h+var_140], xmm1
0x18003666e  mov     [r11-130h], rax
0x180036675  mov     [rsp+368h+var_300], rsi
0x18003667a  mov     [rsp+368h+var_2F8], rsi
0x18003667f  mov     [r11-290h], rsi
0x180036686  mov     [r11-288h], rsi
0x18003668d  mov     [r11-278h], rsi
0x180036694  mov     [r11-270h], rsi
0x18003669b  mov     [rsp+368h+var_330], rsi
0x1800366a0  movups  [rsp+368h+var_118], xmm0
0x1800366a8  mov     [r11-108h], rax
0x1800366af  mov     [r11-298h], rsi
0x1800366b6  xor     edx, edx; Val
0x1800366b8  lea     r8d, [rsi+70h]; Size
0x1800366bc  lea     rcx, [r11-0F8h]; void *
0x1800366c3  call    memset_0
0x1800366c8  xorps   xmm0, xmm0
0x1800366cb  movups  [rsp+368h+var_1D0], xmm0
0x1800366d3  xorps   xmm1, xmm1
0x1800366d6  movups  [rsp+368h+var_1B0], xmm1
0x1800366de  movups  [rsp+368h+var_1E0], xmm0
0x1800366e6  movups  [rsp+368h+var_1C0], xmm1
0x1800366ee  mov     [rsp+368h+var_58], 1020330h
0x1800366f9  lea     r13d, [rsi+1]
0x1800366fd  mov     [rsp+368h+var_54], 7
0x180036705  lea     rdx, a12840113556148; "1.2.840.113556.1.4.801"
0x18003670c  mov     [rsp+368h+var_240], rdx
0x180036714  mov     [rsp+368h+var_238], 5
0x180036720  lea     rax, [rsp+368h+var_58]
0x180036728  mov     [rsp+368h+var_230], rax
0x180036730  mov     [rsp+368h+var_228], r13b
0x180036738  xor     eax, eax
0x18003673a  mov     [rsp+368h+var_227], eax
0x180036741  mov     [rsp+368h+var_223], ax
0x180036749  mov     [rsp+368h+var_221], al
0x180036750  lea     rax, a12840113556141; "1.2.840.113556.1.4.1413"
0x180036757  mov     [rsp+368h+var_260], rax
0x18003675f  mov     [rsp+368h+var_258], rsi
0x180036767  mov     [rsp+368h+var_250], rsi
0x18003676f  mov     [rsp+368h+var_248], sil
0x180036777  xor     eax, eax
0x180036779  mov     [rsp+368h+var_247], eax
0x180036780  mov     [rsp+368h+var_243], ax
0x180036788  mov     [rsp+368h+var_241], al
0x18003678f  lea     rax, [rsp+368h+var_240]
0x180036797  mov     [rsp+368h+ServerControls], rax
0x18003679f  lea     rax, [rsp+368h+var_260]
0x1800367a7  mov     [rsp+368h+var_80], rax
0x1800367af  mov     [rsp+368h+var_78], rsi
0x1800367b7  mov     [rsp+368h+var_50], 1020330h
0x1800367c2  mov     [rsp+368h+var_4C], 4
0x1800367ca  mov     [rsp+368h+var_220], rdx
0x1800367d2  mov     [rsp+368h+var_218], 5
0x1800367de  lea     rax, [rsp+368h+var_50]
0x1800367e6  mov     [rsp+368h+var_210], rax
0x1800367ee  mov     [rsp+368h+var_208], r13b
0x1800367f6  xor     eax, eax
0x1800367f8  mov     [rsp+368h+var_207], eax
0x1800367ff  mov     [rsp+368h+var_203], ax
0x180036807  mov     [rsp+368h+var_201], al
0x18003680e  lea     rax, [rsp+368h+var_220]
0x180036816  mov     [rsp+368h+var_70], rax
0x18003681e  lea     rax, [rsp+368h+var_260]
0x180036826  mov     [rsp+368h+var_68], rax
0x18003682e  mov     [rsp+368h+var_60], rsi
0x180036836  movups  [rsp+368h+var_1F0], xmm0
0x18003683e  mov     [rsp+368h+var_2A0], rsi
0x180036846  mov     [rsp+368h+var_2A8], rsi
0x18003684e  mov     [rsp+368h+var_308], rsi
0x180036853  mov     [rsp+368h+var_2C0], rsi
0x18003685b  mov     [rsp+368h+var_2D8], rsi
0x180036863  mov     [rsp+368h+var_2F0], rsi
0x180036868  mov     [rsp+368h+var_280], rsi
0x180036870  mov     [rsp+368h+var_268], rsi
0x180036878  cmp     [r14], rsi
0x18003687b  jnz     short loc_180036893
0x18003687d  mov     edi, 80004003h
0x180036882  mov     edx, edi; int
0x180036884  mov     ecx, 4080325h; unsigned int
0x180036889  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003688e  jmp     loc_180036FE4
0x180036893  mov     ecx, r13d; int
0x180036896  call    ?myDoesDSExist@@YAJH@Z; myDoesDSExist(int)
0x18003689b  mov     edi, eax
0x18003689d  test    eax, eax
0x18003689f  jz      short loc_1800368AA
0x1800368a1  mov     edx, eax
0x1800368a3  mov     ecx, 40D0325h
0x1800368a8  jmp     short loc_180036889
0x1800368aa  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x1800368b1  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800368b7  mov     rbx, rax
0x1800368ba  mov     [rsp+368h+var_128], rax
0x1800368c2  test    r15, r15
0x1800368c5  jz      short loc_1800368D1
0x1800368c7  mov     r12, r15
0x1800368ca  mov     [rsp+368h+var_320], r15
0x1800368cf  jmp     short loc_180036922
0x1800368d1  mov     [rsp+368h+var_340], rsi
0x1800368d6  lea     rax, [rsp+368h+var_320]
0x1800368db  mov     qword ptr [rsp+368h+csz], rax
0x1800368e0  xor     r9d, r9d
0x1800368e3  lea     edx, [r9+8]
0x1800368e7  xor     ecx, ecx
0x1800368e9  lea     r8d, [r9+2]
0x1800368ed  call    myRobustLdapBindEx
0x1800368f2  mov     edi, eax
0x1800368f4  mov     [rsp+368h+var_334], eax
0x1800368f8  test    eax, eax
0x1800368fa  jz      short loc_18003691D
0x1800368fc  mov     edx, eax; int
0x1800368fe  mov     ecx, 4200325h; unsigned int
0x180036903  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180036908  nop
0x180036909  mov     rcx, rbx
0x18003690c  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180036912  nop
0x180036913  mov     r12, [rsp+368h+var_320]
0x180036918  jmp     loc_180036FE4
0x18003691d  mov     r12, [rsp+368h+var_320]
0x180036922  mov     r15d, 2
0x180036928  mov     dword ptr [rsp+368h+var_1A0], r15d
0x180036930  lea     rax, aObjectclass_2; "objectclass"
0x180036937  mov     qword ptr [rsp+368h+var_1A0+8], rax
0x18003693f  lea     rax, [rsp+368h+var_118]
0x180036947  mov     [rsp+368h+var_190], rax
0x18003694f  lea     rax, aTop; "top"
0x180036956  mov     qword ptr [rsp+368h+var_118], rax
0x18003695e  lea     rax, aPkienrollments; "pKIEnrollmentService"
0x180036965  mov     qword ptr [rsp+368h+var_118+8], rax
0x18003696d  mov     [rsp+368h+var_108], rsi
0x180036975  lea     rax, [rsp+368h+var_1A0]
0x18003697d  mov     [rsp+368h+attrs], rax
0x180036985  mov     edi, r13d
0x180036988  mov     [rsp+368h+var_338], r13d
0x18003698d  mov     dword ptr [rsp+368h+var_2B8], r15d
0x180036995  lea     rdx, aCn_1; "cn"
0x18003699c  mov     [rsp+368h+var_2B0], rdx
0x1800369a4  lea     r8, [rsp+368h+var_2A8]; unsigned __int16 ***
0x1800369ac  mov     rcx, r14; this
0x1800369af  call    ?GetProperty@CCAInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCAInfo::GetProperty(ushort const *,ushort * * *)
0x1800369b4  mov     [rsp+368h+var_334], eax
0x1800369b8  test    eax, eax
0x1800369ba  jnz     short loc_1800369E4
0x1800369bc  cmp     [rsp+368h+var_2A8], rsi
0x1800369c4  jz      short loc_1800369E4
0x1800369c6  lea     rax, [rsp+368h+var_2B8]
0x1800369ce  mov     [rsp+368h+var_F0], rax
0x1800369d6  mov     edi, r15d
0x1800369d9  mov     [rsp+368h+var_338], r15d
0x1800369de  lea     r15, [r14+28h]
0x1800369e2  jmp     short loc_180036A13
0x1800369e4  lea     rax, [rsp+368h+var_330]
0x1800369e9  mov     [rsp+368h+var_2A8], rax
0x1800369f1  lea     r15, [r14+28h]
0x1800369f5  cmp     [r15], esi
0x1800369f8  jnz     short loc_180036A13
0x1800369fa  lea     rax, [rsp+368h+var_2B8]
0x180036a02  mov     [rsp+368h+var_F0], rax
0x180036a0a  mov     edi, 2
0x180036a0f  mov     [rsp+368h+var_338], edi
0x180036a13  mov     dword ptr [rsp+368h+var_318], 2
0x180036a1b  lea     rdx, aDisplayname_0; "displayName"
0x180036a22  mov     [rsp+368h+var_310], rdx
0x180036a27  lea     r8, [rsp+368h+var_308]; unsigned __int16 ***
0x180036a2c  mov     rcx, r14; this
0x180036a2f  call    ?GetProperty@CCAInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCAInfo::GetProperty(ushort const *,ushort * * *)
0x180036a34  mov     [rsp+368h+var_334], eax
0x180036a38  test    eax, eax
0x180036a3a  jnz     short loc_180036A43
0x180036a3c  cmp     [rsp+368h+var_308], rsi
0x180036a41  jnz     short loc_180036A52
0x180036a43  lea     rax, [rsp+368h+var_330]
0x180036a48  mov     [rsp+368h+var_308], rax
0x180036a4d  cmp     [r15], esi
0x180036a50  jnz     short loc_180036A68
0x180036a52  mov     eax, edi
0x180036a54  lea     rcx, [rsp+368h+var_318]
0x180036a59  mov     [rsp+rax*8+368h+attrs], rcx
0x180036a61  add     edi, r13d
0x180036a64  mov     [rsp+368h+var_338], edi
0x180036a68  mov     dword ptr [rsp+368h+var_188], 2
0x180036a73  lea     rax, attr; "flags"
0x180036a7a  mov     qword ptr [rsp+368h+var_188+8], rax
0x180036a82  lea     rax, [rsp+368h+var_1F0]
0x180036a8a  mov     [rsp+368h+var_178], rax
0x180036a92  lea     rax, [rsp+368h+var_48]
0x180036a9a  mov     qword ptr [rsp+368h+var_1F0], rax
0x180036aa2  mov     qword ptr [rsp+368h+var_1F0+8], rsi
0x180036aaa  mov     r9d, [r14+34h]
0x180036aae  lea     r8, aLu; "%lu"
0x180036ab5  mov     edx, 0Ch; unsigned __int64
0x180036aba  lea     rcx, [rsp+368h+var_48]; unsigned __int16 *
0x180036ac2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036ac7  mov     eax, edi
0x180036ac9  lea     rcx, [rsp+368h+var_188]
0x180036ad1  mov     [rsp+rax*8+368h+attrs], rcx
0x180036ad9  add     edi, r13d
0x180036adc  mov     [rsp+368h+var_338], edi
0x180036ae0  mov     dword ptr [rsp+368h+var_170], 82h
0x180036aeb  lea     rax, aCacertificate; "cACertificate"
0x180036af2  mov     qword ptr [rsp+368h+var_170+8], rax
0x180036afa  lea     rax, [rsp+368h+var_1E0]
0x180036b02  mov     [rsp+368h+var_160], rax
0x180036b0a  lea     rax, [rsp+368h+var_1D0]
0x180036b12  mov     qword ptr [rsp+368h+var_1E0], rax
0x180036b1a  mov     qword ptr [rsp+368h+var_1E0+8], rsi
0x180036b22  mov     rdx, [r14]
0x180036b25  mov     eax, [rdx+10h]
0x180036b28  mov     dword ptr [rsp+368h+var_1D0], eax
0x180036b2f  mov     rax, [rdx+8]
0x180036b33  mov     qword ptr [rsp+368h+var_1D0+8], rax
0x180036b3b  lea     rax, [rsp+368h+var_170]
0x180036b43  mov     [rsp+rdi*8+368h+attrs], rax
0x180036b4b  add     edi, r13d
0x180036b4e  mov     [rsp+368h+var_338], edi
0x180036b52  mov     [rsp+368h+var_200], edi
0x180036b59  mov     dword ptr [rsp+368h+var_158], 2
0x180036b64  lea     rax, aCacertificated_0; "cACertificateDN"
0x180036b6b  mov     qword ptr [rsp+368h+var_158+8], rax
0x180036b73  lea     rax, [rsp+368h+var_2A0]
0x180036b7b  mov     [rsp+368h+var_148], rax
0x180036b83  mov     rdx, [rdx+18h]
0x180036b87  add     rdx, 50h ; 'P'; pName
0x180036b8b  mov     [rsp+368h+csz], esi; csz
0x180036b8f  xor     r9d, r9d; psz
0x180036b92  mov     r8d, 2000003h; dwStrType
0x180036b98  mov     ecx, r13d; dwCertEncodingType
0x180036b9b  call    cs:__imp_CertNameToStrW
0x180036ba1  mov     r13d, eax
0x180036ba4  test    eax, eax
0x180036ba6  jnz     short loc_180036BD4
0x180036ba8  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180036bad  mov     edi, eax
0x180036baf  mov     [rsp+368h+var_334], eax
0x180036bb3  mov     edx, eax; int
0x180036bb5  mov     ecx, 46C0325h; unsigned int
0x180036bba  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180036bbf  nop
0x180036bc0  mov     rcx, rbx
0x180036bc3  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180036bc9  nop
0x180036bca  mov     r15, [rsp+368h+var_328]
0x180036bcf  jmp     loc_180036FE4
0x180036bd4  mov     edx, r13d; unsigned int
0x180036bd7  xor     ecx, ecx; Src
0x180036bd9  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x180036bde  mov     r9, rax; psz
0x180036be1  mov     [rsp+368h+var_2A0], rax
0x180036be9  test    rax, rax
0x180036bec  jnz     short loc_180036C18
0x180036bee  mov     edi, 8007000Eh
0x180036bf3  mov     [rsp+368h+var_334], edi
0x180036bf7  mov     edx, edi; int
0x180036bf9  mov     ecx, 4720325h; unsigned int
0x180036bfe  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180036c03  nop
0x180036c04  mov     rcx, rbx
0x180036c07  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180036c0d  nop
0x180036c0e  mov     r15, [rsp+368h+var_328]
0x180036c13  jmp     loc_180036FE4
  ... truncated ...
```
