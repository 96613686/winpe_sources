# DomainV2MetadataCache::WriteMetadataToAd(_DFS_DOMAINV2_METADATA *,int)

- ea: `0x140043690`
- end: `0x1400440ae`
- name: `?WriteMetadataToAd@DomainV2MetadataCache@@AEAAKPEAU_DFS_DOMAINV2_METADATA@@H@Z`
- size: `2590`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, struct _DFS_DOMAINV2_METADATA *, int)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003f044`
- `0x140040318`
- `0x14004046c`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x140005b90`
- `0x14003ff94`
- `0x1400402c4`
- `0x140040d5c`
- `0x140041064`
- `0x140043534`
- `0x140043690`
- `0x14004857c`
- `0x14004acf4`
- `0x140056d2c`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140043b9b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140043b9b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140043d9f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140043fd8`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140043d9f`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140043fd8`
- `WLDAP32!__imp_ldap_add_sW` at `0x140043d87`
- `WLDAP32!__imp_ldap_add_sW` at `0x140043d87`
- `WLDAP32!__imp_ldap_modify_sW` at `0x140043fc0`
- `WLDAP32!__imp_ldap_modify_sW` at `0x140043fc0`

## string_xrefs

- `0x140043a85`: `msDFS-Commentv2`
- `0x140043d0a`: `msDFS-LinkIdentityGUIDv2`
- `0x140043b56`: `msDFS-LinkSecurityDescriptorv2`
- `0x140043ae3`: `msDFS-Linkpathv2`
- `0x140043c3e`: `msDFS-Linkv2`

## pseudocode

```c
__int64 __fastcall DomainV2MetadataCache::WriteMetadataToAd(
        DomainV2MetadataCache *this,
        struct _DFS_DOMAINV2_METADATA *a2,
        int a3)
{
  DomainV2MetadataCache *v5; // r13
  WCHAR *v6; // r14
  unsigned int v7; // ecx
  void *v8; // r12
  unsigned int *v9; // r10
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rsi
  unsigned int v12; // edx
  unsigned int UtcTimeString; // eax
  __int64 v14; // rcx
  unsigned int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rcx
  _WORD *v18; // rax
  __int16 *v19; // rcx
  __int16 *i; // rdx
  __int16 v21; // ax
  int v22; // esi
  int v23; // r10d
  unsigned int v24; // r13d
  __int64 v25; // rbx
  __int64 v26; // r9
  __int64 v27; // rdx
  LDAPModW *v28; // r8
  void **v29; // rcx
  void *v30; // r8
  __int64 v31; // rax
  LDAPModW *v32; // rcx
  DWORD SecurityDescriptorLength; // eax
  __int64 v34; // r10
  __int64 v35; // r11
  __int64 v36; // rdx
  void **v37; // rcx
  __int64 v38; // rdx
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  LDAPModW *v42; // r8
  __int64 v43; // rax
  _QWORD *v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  LDAPModW *v49; // r8
  __int64 v50; // r10
  unsigned int **v51; // rdx
  __int64 v52; // rcx
  LDAP *v53; // rcx
  ULONG v54; // eax
  ULONG v55; // edi
  ULONG v56; // eax
  __int64 v57; // rdx
  unsigned int v59; // ebx
  __int64 v60; // rax
  void **v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  int *v64; // rdx
  const unsigned __int16 **v65; // rax
  ULONG v66; // eax
  ULONG v67; // eax
  char v68; // [rsp+30h] [rbp-D0h]
  unsigned int v69; // [rsp+34h] [rbp-CCh] BYREF
  void *v70; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v71; // [rsp+40h] [rbp-C0h]
  __int64 v72; // [rsp+48h] [rbp-B8h] BYREF
  int v73; // [rsp+50h] [rbp-B0h]
  int v74; // [rsp+54h] [rbp-ACh]
  void *Block; // [rsp+58h] [rbp-A8h]
  void *v76; // [rsp+60h] [rbp-A0h]
  void *v77; // [rsp+68h] [rbp-98h] BYREF
  void *v78; // [rsp+70h] [rbp-90h]
  DomainV2MetadataCache *v79; // [rsp+78h] [rbp-88h]
  _DWORD *v80; // [rsp+80h] [rbp-80h] BYREF
  __int64 v81; // [rsp+88h] [rbp-78h]
  unsigned int *v82; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h]
  _QWORD v84[6]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v85[2]; // [rsp+D0h] [rbp-30h] BYREF
  char *v86; // [rsp+D8h] [rbp-28h]
  unsigned int v87; // [rsp+E0h] [rbp-20h] BYREF
  void *v88; // [rsp+E8h] [rbp-18h]
  DWORD v89; // [rsp+F0h] [rbp-10h] BYREF
  void *v90; // [rsp+F8h] [rbp-8h]
  LDAPModW *attrs[3]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v92[11]; // [rsp+138h] [rbp+38h]
  void *v93; // [rsp+190h] [rbp+90h] BYREF
  __int64 v94; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v95[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v96[12]; // [rsp+1B0h] [rbp+B0h] BYREF
  _DWORD v97[2]; // [rsp+210h] [rbp+110h] BYREF
  const wchar_t *v98; // [rsp+218h] [rbp+118h]
  _QWORD *v99; // [rsp+220h] [rbp+120h]
  int v100; // [rsp+228h] [rbp+128h] BYREF
  const wchar_t *v101; // [rsp+230h] [rbp+130h]
  void **v102; // [rsp+238h] [rbp+138h]
  int v103; // [rsp+240h] [rbp+140h] BYREF
  const wchar_t *v104; // [rsp+248h] [rbp+148h]
  unsigned int **v105; // [rsp+250h] [rbp+150h]
  int v106; // [rsp+258h] [rbp+158h] BYREF
  const wchar_t *v107; // [rsp+260h] [rbp+160h]
  _QWORD *v108; // [rsp+268h] [rbp+168h]
  int v109; // [rsp+270h] [rbp+170h] BYREF
  const wchar_t *v110; // [rsp+278h] [rbp+178h]
  void *v111; // [rsp+280h] [rbp+180h]
  int v112; // [rsp+288h] [rbp+188h] BYREF
  const wchar_t *v113; // [rsp+290h] [rbp+190h]
  _QWORD *v114; // [rsp+298h] [rbp+198h]
  unsigned __int16 v115[20]; // [rsp+350h] [rbp+250h] BYREF

  v73 = a3;
  v79 = this;
  v5 = this;
  memset_0(&v80, 0, 0x50u);
  memset_0(attrs, 0, 0x70u);
  v68 = 0;
  Block = 0;
  v6 = 0;
  v72 = 0;
  memset_0(&v93, 0, 0x80u);
  v7 = *((_DWORD *)a2 + 46);
  v8 = 0;
  v76 = 0;
  v77 = 0;
  v69 = 0;
  v70 = 0;
  v74 = 0;
  v78 = (void *)DfsConvertUlongToString(v7);
  if ( v78 )
  {
    Block = (void *)DfsConvertUlongToString(*((_DWORD *)a2 + 15));
    if ( Block )
    {
      v71 = DfsConvertUlongToString(*((_DWORD *)a2 + 16));
      if ( !v71 )
      {
        v9 = pWppControl;
        v10 = 8;
        v11 = 0;
        goto LABEL_63;
      }
      UtcTimeString = DfsGetUtcTimeString(v115, v12);
      if ( UtcTimeString
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0xA00) != 0
        && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        WPP_SF_SD(
          *((_QWORD *)pWppControl + 2),
          69,
          (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
          *((_QWORD *)a2 + 13),
          UtcTimeString);
      }
      v76 = (void *)anonymous_namespace_::DfspConvertStateAndTypeToEntryProperties(
                      *((unsigned int *)a2 + 42),
                      *((unsigned int *)a2 + 43));
      if ( !v76 )
        goto LABEL_13;
      v10 = DfsConvertTargetListToXml(*((struct _DFS_DOMAINV2_TARGET **)a2 + 26), *((_DWORD *)a2 + 50), &v77, &v69);
      if ( v10 )
        goto LABEL_14;
      v14 = *((_QWORD *)a2 + 13);
      v15 = 2;
      v6 = (WCHAR *)*((_QWORD *)v5 + 143);
      if ( v14 )
      {
        v10 = anonymous_namespace_::DfspCreateLinkDn(v14, *((_QWORD *)v5 + 143), &v72);
        if ( v10 )
        {
          v6 = (WCHAR *)v72;
          v8 = 0;
          goto LABEL_14;
        }
        v16 = *((_QWORD *)a2 + 14);
        v17 = -1;
        v74 = 1;
        do
          ++v17;
        while ( *(_WORD *)(v16 + 2 * v17) );
        v18 = operator new(saturated_mul(v17 + 1, 2u));
        v70 = v18;
        if ( !v18 )
        {
          v6 = (WCHAR *)v72;
          v8 = 0;
LABEL_13:
          v10 = 8;
LABEL_14:
          v9 = pWppControl;
          v11 = (unsigned __int16 *)v71;
          goto LABEL_63;
        }
        v19 = (__int16 *)*((_QWORD *)a2 + 14);
        for ( i = v18; ; ++i )
        {
          v21 = *v19;
          if ( !*v19 )
            break;
          if ( v21 == 92 )
            v21 = 47;
          ++v19;
          *i = v21;
        }
        v6 = (WCHAR *)v72;
        *i = 0;
      }
      v22 = a3 == 0 ? 2 : 0;
      v10 = DomainV2MetadataCache::DfsAcquireLdapSessionReference(v5);
      if ( v10 )
      {
        v9 = pWppControl;
        v11 = (unsigned __int16 *)v71;
        goto LABEL_62;
      }
      v23 = v73;
      v98 = L"msDFS-GenerationGUIDv2";
      v24 = 4;
      v68 = 1;
      v99 = &v80;
      LODWORD(v25) = 5;
      v85[0] = 16;
      v86 = (char *)a2 + 152;
      v81 = 0;
      v80 = v85;
      v100 = v22;
      attrs[0] = (LDAPModW *)v97;
      v97[0] = v22 | 0x80;
      v101 = L"msDFS-Ttlv2";
      v102 = &v93;
      v93 = v78;
      attrs[1] = (LDAPModW *)&v100;
      v104 = L"msDFS-TargetListv2";
      v105 = &v82;
      v88 = v77;
      v87 = v69;
      v82 = &v87;
      attrs[2] = (LDAPModW *)&v103;
      v107 = L"msDFS-LastModifiedv2";
      v108 = v95;
      v95[0] = v115;
      v92[0] = &v106;
      v110 = L"msDFS-Propertiesv2";
      v111 = v76;
      v92[1] = &v109;
      v94 = 0;
      v103 = v22 | 0x80;
      v83 = 0;
      v69 = 4;
      v106 = v22;
      v95[1] = 0;
      v109 = v22;
      if ( !v73 || *((_QWORD *)a2 + 22) )
      {
        v112 = v22;
        v113 = L"msDFS-Commentv2";
        if ( *((_QWORD *)a2 + 22) )
        {
          v96[0] = *((_QWORD *)a2 + 22);
          v114 = v96;
          v24 = 6;
          v96[1] = 0;
        }
        else
        {
          v114 = 0;
        }
        LODWORD(v25) = 6;
        v92[2] = &v112;
      }
      if ( *((_QWORD *)a2 + 13) )
      {
        v26 = (unsigned int)v25;
        LODWORD(v25) = v25 + 1;
        v27 = 3 * v26;
        (&v98)[v27] = L"msDFS-Linkpathv2";
        v28 = (LDAPModW *)&v97[6 * v26];
        attrs[v26] = v28;
        v28->mod_op = v22;
        v29 = &v93 + v24;
        *v29 = v70;
        (&v99)[v27] = v29;
        *(&v93 + v24 + 1) = 0;
        v24 += 2;
      }
      if ( v23 && !*((_QWORD *)a2 + 24) )
        goto LABEL_43;
      v30 = (void *)*((_QWORD *)a2 + 24);
      v31 = (unsigned int)v25;
      (&v98)[3 * (unsigned int)v25] = L"msDFS-LinkSecurityDescriptorv2";
      v32 = (LDAPModW *)&v97[6 * (unsigned int)v25];
      v72 = (__int64)v32;
      if ( v30 )
      {
        v90 = v30;
        v32->mod_op = v22 | 0x80;
        (&v99)[3 * (unsigned int)v25] = v84;
        SecurityDescriptorLength = GetSecurityDescriptorLength(v30);
        v32 = (LDAPModW *)v72;
        v23 = v73;
        v15 = 3;
        v89 = SecurityDescriptorLength;
        v84[0] = &v89;
        v31 = (unsigned int)v25;
        v84[1] = 0;
        v69 = 6;
      }
      else
      {
        v32->mod_op = v22;
        (&v99)[3 * (unsigned int)v25] = 0;
      }
      v25 = (unsigned int)(v25 + 1);
      attrs[v31] = v32;
      if ( v23 )
      {
LABEL_43:
        v34 = *((_QWORD *)a2 + 13);
        v35 = (unsigned int)v25;
        v36 = 3LL * (unsigned int)v25;
        (&v98)[v36] = L"objectClass";
        v97[6 * (unsigned int)v25] = v22;
        v37 = &v93 + v24;
        (&v99)[v36] = v37;
        *v37 = L"top";
        v38 = v24 + 1;
        v39 = L"msDFS-Namespacev2";
        if ( v34 )
          v39 = L"msDFS-Linkv2";
        *(&v93 + v38) = (void *)v39;
        v72 = (int)v38 + 1LL;
        attrs[(unsigned int)v25] = (LDAPModW *)&v97[6 * (unsigned int)v25];
        *(&v93 + (int)v38 + 1) = 0;
        v40 = (unsigned int)(v25 + 1);
        v41 = 3 * v40;
        v42 = (LDAPModW *)&v97[6 * v40];
        v42->mod_op = v22 | 0x80;
        (&v98)[v41] = L"msDFS-NamespaceIdentityGUIDv2";
        v43 = v69;
        attrs[(unsigned int)(v25 + 1)] = v42;
        v44 = &(&v80)[v43];
        (&v99)[v41] = v44;
        v45 = 4LL * v15;
        (&v86)[(unsigned __int64)v45 / 2] = (char *)a2 + 120;
        *v44 = &v85[v45];
        v46 = v69;
        v85[v45] = 16;
        v47 = (unsigned int)(v25 + 2);
        v48 = 3 * v47;
        *(&v81 + v46) = 0;
        v49 = (LDAPModW *)&v97[6 * v47];
        v69 = v25 + 2;
        attrs[v47] = v49;
        if ( !v34 )
        {
          v59 = v69;
          (&v98)[3 * v47] = L"msDFS-SchemaMajorVersion";
          v60 = v72;
          v49->mod_op = v22;
          v61 = (void **)&v95[v60 - 1];
          (&v99)[v48] = v61;
          *v61 = Block;
          v62 = 3 * (v35 + 3);
          v63 = (int)v24 + 4LL;
          (&v98)[v62] = L"msDFS-SchemaMinorVersion";
          v64 = &v97[6 * v35 + 18];
          *v64 = v22;
          v92[v35] = v64;
          *(&v93 + v63) = 0;
          v65 = (const unsigned __int16 **)&v95[v63 - 1];
          v11 = (unsigned __int16 *)v71;
          v25 = v59 + 2;
          *v65 = v71;
          (&v99)[v62] = v65;
          v96[(int)v24 + 2] = 0;
LABEL_48:
          v5 = v79;
          attrs[v25] = 0;
          v53 = (LDAP *)*((_QWORD *)v5 + 8);
          if ( v73 )
          {
            v54 = ldap_add_sW(v53, v6, attrs);
            v55 = v54;
            if ( v54 )
            {
              v56 = LdapMapErrorToWin32(v54);
              v10 = v56;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
LABEL_61:
                v9 = pWppControl;
LABEL_62:
                v8 = v70;
                goto LABEL_63;
              }
              v9 = pWppControl;
              if ( pWppControl
                && (((1 << (v56 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_D(*((_QWORD *)pWppControl + 2), 70, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v56);
                v9 = pWppControl;
              }
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || !v9
                || (v9[7] & 0xA00) == 0
                || *((_BYTE *)v9 + 25) < 3u )
              {
                goto LABEL_62;
              }
              v57 = 71;
LABEL_60:
              WPP_SF_D(*((_QWORD *)v9 + 2), v57, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v55);
              goto LABEL_61;
            }
          }
          else
          {
            v66 = ldap_modify_sW(v53, v6, attrs);
            v55 = v66;
            if ( v66 )
            {
              v67 = LdapMapErrorToWin32(v66);
              v10 = v67;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_61;
              v9 = pWppControl;
              if ( pWppControl
                && (((1 << (v67 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_D(*((_QWORD *)pWppControl + 2), 72, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v67);
                v9 = pWppControl;
              }
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || !v9
                || (v9[7] & 0xA00) == 0
                || *((_BYTE *)v9 + 25) < 3u )
              {
                goto LABEL_62;
              }
              v57 = 73;
              goto LABEL_60;
            }
          }
          v10 = 0;
          DomainV2MetadataCache::UpdateSyncOptimisationInfo(v5, v6);
          goto LABEL_61;
        }
        v50 = (unsigned int)v46;
        (&v98)[3 * v47] = L"msDFS-LinkIdentityGUIDv2";
        v25 = (unsigned int)(v25 + 3);
        v49->mod_op = v22 | 0x80;
        v51 = &(&v82)[(unsigned int)v46];
        (&v99)[3 * v47] = v51;
        v52 = 4 * (v15 + 1LL);
        (&v86)[(unsigned __int64)v52 / 2] = (char *)a2 + 136;
        *v51 = &v85[v52];
        v84[v50 - 1] = 0;
        v85[v52] = 16;
      }
      v11 = (unsigned __int16 *)v71;
      goto LABEL_48;
    }
  }
  v9 = pWppControl;
  v10 = 8;
  v11 = 0;
LABEL_63:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v9
    && (((1 << (v10 != 0 ? 11 : 31)) | 0x200) & v9[7]) != 0
    && *((_BYTE *)v9 + 25) >= 3u )
  {
    WPP_SF_SD(*((_QWORD *)v9 + 2), 74, (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, (_DWORD)v6, v10);
  }
  if ( v74 )
    operator delete(v6);
  operator delete(Block);
  operator delete(v11);
  operator delete(v8);
  operator delete(v78);
  operator delete(v76);
  operator delete(v77);
  if ( v68 )
    DomainV2MetadataCache::DfsReleaseLdapSessionReference(v5);
  return v10;
}

```

## disassembly

```asm
0x140043690  mov     [rsp-8+arg_10], rbx
0x140043695  push    rbp
0x140043696  push    rsi
0x140043697  push    rdi
0x140043698  push    r12
0x14004369a  push    r13
0x14004369c  push    r14
0x14004369e  push    r15
0x1400436a0  lea     rbp, [rsp-280h]
0x1400436a8  sub     rsp, 380h
0x1400436af  mov     rax, cs:__security_cookie
0x1400436b6  xor     rax, rsp
0x1400436b9  mov     [rbp+2B0h+var_38], rax
0x1400436c0  mov     rdi, rdx
0x1400436c3  mov     [rsp+3B0h+var_360], r8d
0x1400436c8  xor     edx, edx; Val
0x1400436ca  mov     [rsp+3B0h+var_338], rcx
0x1400436cf  mov     esi, r8d
0x1400436d2  mov     r13, rcx
0x1400436d5  lea     rcx, [rbp+2B0h+var_330]; void *
0x1400436d9  lea     r8d, [rdx+50h]; Size
0x1400436dd  call    memset_0
0x1400436e2  xor     edx, edx; Val
0x1400436e4  lea     rcx, [rbp+2B0h+attrs]; void *
0x1400436e8  lea     r8d, [rdx+70h]; Size
0x1400436ec  call    memset_0
0x1400436f1  xor     ebx, ebx
0x1400436f3  lea     rcx, [rbp+2B0h+var_220]; void *
0x1400436fa  xor     edx, edx; Val
0x1400436fc  mov     [rsp+3B0h+var_380], bl
0x140043700  mov     r8d, 80h; Size
0x140043706  mov     [rsp+3B0h+Block], rbx
0x14004370b  mov     r14d, ebx
0x14004370e  mov     [rsp+3B0h+var_368], rbx
0x140043713  call    memset_0
0x140043718  mov     ecx, [rdi+0B8h]; Value
0x14004371e  mov     r12d, ebx
0x140043721  mov     [rsp+3B0h+var_350], rbx
0x140043726  mov     [rsp+3B0h+var_348], rbx
0x14004372b  mov     [rsp+3B0h+var_37C], ebx
0x14004372f  mov     [rsp+3B0h+var_378], rbx
0x140043734  mov     [rsp+3B0h+var_35C], ebx
0x140043738  call    ?DfsConvertUlongToString@@YAPEBGK@Z; DfsConvertUlongToString(ulong)
0x14004373d  xor     r9d, r9d
0x140043740  mov     [rsp+3B0h+var_340], rax
0x140043745  lea     rbx, WPP_GLOBAL_Control
0x14004374c  mov     r15d, 200h
0x140043752  test    rax, rax
0x140043755  jnz     short loc_14004376B
0x140043757  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004375e  mov     ebx, 8
0x140043763  mov     rsi, r9
0x140043766  jmp     loc_140043E4F
0x14004376b  mov     ecx, [rdi+3Ch]; Value
0x14004376e  call    ?DfsConvertUlongToString@@YAPEBGK@Z; DfsConvertUlongToString(ulong)
0x140043773  xor     r9d, r9d
0x140043776  mov     [rsp+3B0h+Block], rax
0x14004377b  test    rax, rax
0x14004377e  jz      short loc_140043757
0x140043780  mov     ecx, [rdi+40h]; Value
0x140043783  call    ?DfsConvertUlongToString@@YAPEBGK@Z; DfsConvertUlongToString(ulong)
0x140043788  mov     [rsp+3B0h+var_370], rax
0x14004378d  test    rax, rax
0x140043790  jnz     short loc_1400437A4
0x140043792  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140043799  lea     ebx, [rax+8]
0x14004379c  mov     rsi, rax
0x14004379f  jmp     loc_140043E4F
0x1400437a4  lea     rcx, [rbp+2B0h+var_60]; unsigned __int16 *
0x1400437ab  call    ?DfsGetUtcTimeString@@YAKPEAGK@Z; DfsGetUtcTimeString(ushort *,ulong)
0x1400437b0  test    eax, eax
0x1400437b2  jz      short loc_1400437FA
0x1400437b4  cmp     cs:WPP_GLOBAL_Control, rbx
0x1400437bb  jz      short loc_1400437FA
0x1400437bd  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400437c4  test    r10, r10
0x1400437c7  jz      short loc_1400437FA
0x1400437c9  mov     ecx, r15d
0x1400437cc  bts     ecx, 0Bh
0x1400437d0  test    [r10+1Ch], ecx
0x1400437d4  jz      short loc_1400437FA
0x1400437d6  cmp     byte ptr [r10+19h], 3
0x1400437db  jb      short loc_1400437FA
0x1400437dd  mov     r9, [rdi+68h]
0x1400437e1  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x1400437e8  mov     rcx, [r10+10h]
0x1400437ec  mov     edx, 45h ; 'E'
0x1400437f1  mov     [rsp+3B0h+var_390], eax
0x1400437f5  call    WPP_SF_SD
0x1400437fa  mov     edx, [rdi+0ACh]
0x140043800  mov     ecx, [rdi+0A8h]
0x140043806  call    _anonymous_namespace___DfspConvertStateAndTypeToEntryProperties
0x14004380b  mov     [rsp+3B0h+var_350], rax
0x140043810  test    rax, rax
0x140043813  jnz     short loc_14004382B
0x140043815  mov     ebx, 8
0x14004381a  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140043821  mov     rsi, [rsp+3B0h+var_370]
0x140043826  jmp     loc_140043E4F
0x14004382b  mov     edx, [rdi+0C8h]; unsigned int
0x140043831  lea     r9, [rsp+3B0h+var_37C]; unsigned int *
0x140043836  mov     rcx, [rdi+0D0h]; struct _DFS_DOMAINV2_TARGET *
0x14004383d  lea     r8, [rsp+3B0h+var_348]; void **
0x140043842  call    ?DfsConvertTargetListToXml@@YAKPEAU_DFS_DOMAINV2_TARGET@@KPEAPEAXPEAK@Z; DfsConvertTargetListToXml(_DFS_DOMAINV2_TARGET *,ulong,void * *,ulong *)
0x140043847  mov     ebx, eax
0x140043849  test    eax, eax
0x14004384b  jnz     short loc_14004381A
0x14004384d  mov     rcx, [rdi+68h]
0x140043851  lea     r12d, [rax+2]
0x140043855  mov     r14, [r13+478h]
0x14004385c  test    rcx, rcx
0x14004385f  jz      loc_1400438F9
0x140043865  lea     r8, [rsp+3B0h+var_368]
0x14004386a  mov     rdx, r14
0x14004386d  call    _anonymous_namespace___DfspCreateLinkDn
0x140043872  xor     r9d, r9d
0x140043875  mov     ebx, eax
0x140043877  test    eax, eax
0x140043879  jnz     loc_1400440A1
0x14004387f  mov     rax, [rdi+70h]
0x140043883  or      r8, 0FFFFFFFFFFFFFFFFh
0x140043887  mov     rcx, r8
0x14004388a  mov     [rsp+3B0h+var_35C], 1
0x140043892  inc     rcx
0x140043895  cmp     [rax+rcx*2], r9w
0x14004389a  jnz     short loc_140043892
0x14004389c  inc     rcx
0x14004389f  mov     rax, r12
0x1400438a2  mul     rcx
0x1400438a5  cmovo   rax, r8
0x1400438a9  mov     rcx, rax; Size
0x1400438ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400438b1  xor     r9d, r9d
0x1400438b4  mov     [rsp+3B0h+var_378], rax
0x1400438b9  test    rax, rax
0x1400438bc  jnz     short loc_1400438CB
0x1400438be  mov     r14, [rsp+3B0h+var_368]
0x1400438c3  mov     r12, rax
0x1400438c6  jmp     loc_140043815
0x1400438cb  mov     rcx, [rdi+70h]
0x1400438cf  mov     rdx, rax
0x1400438d2  jmp     short loc_1400438E8
0x1400438d4  cmp     ax, 5Ch ; '\'
0x1400438d8  jnz     short loc_1400438DF
0x1400438da  mov     eax, 2Fh ; '/'
0x1400438df  add     rcx, r12
0x1400438e2  mov     [rdx], ax
0x1400438e5  add     rdx, r12
0x1400438e8  movzx   eax, word ptr [rcx]
0x1400438eb  test    ax, ax
0x1400438ee  jnz     short loc_1400438D4
0x1400438f0  mov     r14, [rsp+3B0h+var_368]
0x1400438f5  mov     [rdx], r9w
0x1400438f9  mov     eax, esi
0x1400438fb  mov     rcx, r13; this
0x1400438fe  neg     eax
0x140043900  sbb     esi, esi
0x140043902  not     esi
0x140043904  and     esi, r12d
0x140043907  call    ?DfsAcquireLdapSessionReference@DomainV2MetadataCache@@QEAAKXZ; DomainV2MetadataCache::DfsAcquireLdapSessionReference(void)
0x14004390c  xor     r9d, r9d
0x14004390f  mov     ebx, eax
0x140043911  test    eax, eax
0x140043913  jnz     loc_140044090
0x140043919  mov     r10d, [rsp+3B0h+var_360]
0x14004391e  lea     rax, aMsdfsGeneratio; "msDFS-GenerationGUIDv2"
0x140043925  mov     [rbp+2B0h+var_198], rax
0x14004392c  lea     r13d, [rbx+4]
0x140043930  lea     rax, [rbp+2B0h+var_330]
0x140043934  mov     [rsp+3B0h+var_380], 1
0x140043939  mov     [rbp+2B0h+var_190], rax
0x140043940  lea     ebx, [r9+5]
0x140043944  lea     rax, [rdi+98h]
0x14004394b  mov     [rbp+2B0h+var_2E0], 10h
0x140043952  mov     [rbp+2B0h+var_2D8], rax
0x140043956  lea     edx, [rbx+1]
0x140043959  lea     rax, [rbp+2B0h+var_2E0]
0x14004395d  mov     [rbp+2B0h+var_328], r9
0x140043961  mov     [rbp+2B0h+var_330], rax
0x140043965  mov     ecx, esi
0x140043967  lea     rax, [rbp+2B0h+var_1A0]
0x14004396e  mov     [rbp+2B0h+var_188], esi
0x140043974  mov     [rbp+2B0h+attrs], rax
0x140043978  bts     ecx, 7
0x14004397c  mov     [rbp+2B0h+var_1A0], ecx
0x140043982  lea     rax, aMsdfsTtlv2; "msDFS-Ttlv2"
0x140043989  mov     [rbp+2B0h+var_180], rax
0x140043990  lea     rax, [rbp+2B0h+var_220]
0x140043997  mov     [rbp+2B0h+var_178], rax
0x14004399e  mov     rax, [rsp+3B0h+var_340]
0x1400439a3  mov     [rbp+2B0h+var_220], rax
0x1400439aa  lea     rax, [rbp+2B0h+var_188]
0x1400439b1  mov     [rbp+2B0h+var_288], rax
0x1400439b5  lea     rax, aMsdfsTargetlis; "msDFS-TargetListv2"
0x1400439bc  mov     [rbp+2B0h+var_168], rax
0x1400439c3  lea     rax, [rbp+2B0h+var_320]
0x1400439c7  mov     [rbp+2B0h+var_160], rax
0x1400439ce  mov     rax, [rsp+3B0h+var_348]
0x1400439d3  mov     [rbp+2B0h+var_2C8], rax
0x1400439d7  mov     eax, [rsp+3B0h+var_37C]
0x1400439db  mov     [rbp+2B0h+var_2D0], eax
0x1400439de  lea     rax, [rbp+2B0h+var_2D0]
0x1400439e2  mov     [rbp+2B0h+var_320], rax
0x1400439e6  lea     rax, [rbp+2B0h+var_170]
0x1400439ed  mov     [rbp+2B0h+var_280], rax
0x1400439f1  lea     rax, aMsdfsLastmodif; "msDFS-LastModifiedv2"
0x1400439f8  mov     [rbp+2B0h+var_150], rax
0x1400439ff  lea     rax, [rbp+2B0h+var_210]
0x140043a06  mov     [rbp+2B0h+var_148], rax
0x140043a0d  lea     rax, [rbp+2B0h+var_60]
0x140043a14  mov     [rbp+2B0h+var_210], rax
0x140043a1b  lea     rax, [rbp+2B0h+var_158]
0x140043a22  mov     [rbp+2B0h+var_278], rax
0x140043a26  lea     rax, aMsdfsPropertie; "msDFS-Propertiesv2"
0x140043a2d  mov     [rbp+2B0h+var_138], rax
0x140043a34  mov     rax, [rsp+3B0h+var_350]
0x140043a39  mov     [rbp+2B0h+var_130], rax
0x140043a40  lea     rax, [rbp+2B0h+var_140]
0x140043a47  mov     [rbp+2B0h+var_270], rax
0x140043a4b  mov     [rbp+2B0h+var_218], r9
0x140043a52  mov     [rbp+2B0h+var_170], ecx
0x140043a58  mov     [rbp+2B0h+var_318], r9
0x140043a5c  mov     [rsp+3B0h+var_37C], 4
0x140043a64  mov     [rbp+2B0h+var_158], esi
0x140043a6a  mov     [rbp+2B0h+var_208], r9
0x140043a71  mov     [rbp+2B0h+var_140], esi
0x140043a77  test    r10d, r10d
0x140043a7a  jz      short loc_140043A85
0x140043a7c  cmp     [rdi+0B0h], r9
0x140043a83  jz      short loc_140043ADA
0x140043a85  lea     rax, aMsdfsCommentv2; "msDFS-Commentv2"
0x140043a8c  mov     [rbp+2B0h+var_128], esi
0x140043a92  mov     [rbp+2B0h+var_120], rax
0x140043a99  mov     rax, [rdi+0B0h]
0x140043aa0  test    rax, rax
0x140043aa3  jnz     short loc_140043AAE
0x140043aa5  mov     [rbp+2B0h+var_118], r9
0x140043aac  jmp     short loc_140043ACD
0x140043aae  lea     rcx, [rbp+2B0h+var_200]
0x140043ab5  mov     [rbp+2B0h+var_200], rax
0x140043abc  mov     [rbp+2B0h+var_118], rcx
0x140043ac3  mov     r13d, edx
0x140043ac6  mov     [rbp+2B0h+var_1F8], r9
0x140043acd  lea     rax, [rbp+2B0h+var_128]
0x140043ad4  mov     ebx, edx
0x140043ad6  mov     [rbp+2B0h+var_268], rax
0x140043ada  cmp     [rdi+68h], r9
0x140043ade  jz      short loc_140043B3D
0x140043ae0  mov     r9d, ebx
0x140043ae3  lea     rax, aMsdfsLinkpathv; "msDFS-Linkpathv2"
0x140043aea  lea     rcx, [rbp+2B0h+var_220]
0x140043af1  inc     ebx
0x140043af3  lea     r8, [rbp+2B0h+var_1A0]
0x140043afa  lea     rdx, [r9+r9*2]
0x140043afe  mov     [rbp+rdx*8+2B0h+var_198], rax
0x140043b06  lea     r8, [r8+rdx*8]
0x140043b0a  mov     eax, r13d
0x140043b0d  mov     [rbp+r9*8+2B0h+attrs], r8
0x140043b12  mov     [r8], esi
0x140043b15  lea     rcx, [rcx+rax*8]
0x140043b19  mov     rax, [rsp+3B0h+var_378]
0x140043b1e  mov     [rcx], rax
0x140043b21  mov     [rbp+rdx*8+2B0h+var_190], rcx
0x140043b29  lea     ecx, [r13+1]
0x140043b2d  and     [rbp+rcx*8+2B0h+var_220], 0
0x140043b36  lea     r13d, [rcx+1]
0x140043b3a  xor     r9d, r9d
0x140043b3d  test    r10d, r10d
0x140043b40  jz      short loc_140043B4F
0x140043b42  cmp     [rdi+0C0h], r9
0x140043b49  jz      loc_140043BEF
0x140043b4f  mov     r8, [rdi+0C0h]
0x140043b56  lea     rcx, aMsdfsLinksecur; "msDFS-LinkSecurityDescriptorv2"
0x140043b5d  mov     eax, ebx
0x140043b5f  lea     rdx, [rax+rax*2]
0x140043b63  mov     [rbp+rdx*8+2B0h+var_198], rcx
0x140043b6b  lea     rcx, [rbp+2B0h+var_1A0]
0x140043b72  lea     rcx, [rcx+rdx*8]
0x140043b76  mov     [rsp+3B0h+var_368], rcx
0x140043b7b  test    r8, r8
0x140043b7e  jz      short loc_140043BD5
0x140043b80  mov     eax, esi
0x140043b82  mov     [rbp+2B0h+var_2B8], r8
0x140043b86  bts     eax, 7
0x140043b8a  mov     [rcx], eax
0x140043b8c  lea     rax, [rbp+2B0h+var_310]
0x140043b90  mov     rcx, r8; pSecurityDescriptor
0x140043b93  mov     [rbp+rdx*8+2B0h+var_190], rax
0x140043b9b  call    cs:__imp_GetSecurityDescriptorLength
0x140043ba2  nop     dword ptr [rax+rax+00h]
0x140043ba7  mov     rcx, [rsp+3B0h+var_368]
0x140043bac  xor     r9d, r9d
0x140043baf  mov     r10d, [rsp+3B0h+var_360]
0x140043bb4  mov     r12d, 3
0x140043bba  mov     [rbp+2B0h+var_2C0], eax
0x140043bbd  lea     rax, [rbp+2B0h+var_2C0]
0x140043bc1  mov     [rbp+2B0h+var_310], rax
0x140043bc5  mov     eax, ebx
0x140043bc7  mov     [rbp+2B0h+var_308], r9
0x140043bcb  mov     [rsp+3B0h+var_37C], 6
  ... truncated ...
```
