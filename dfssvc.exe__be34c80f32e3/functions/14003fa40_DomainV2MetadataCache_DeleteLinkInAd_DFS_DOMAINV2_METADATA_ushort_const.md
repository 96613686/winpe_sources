# DomainV2MetadataCache::DeleteLinkInAd(_DFS_DOMAINV2_METADATA *,ushort const * *)

- ea: `0x14003fa40`
- end: `0x14003ff8d`
- name: `?DeleteLinkInAd@DomainV2MetadataCache@@QEAAKPEAU_DFS_DOMAINV2_METADATA@@PEAPEBG@Z`
- size: `1357`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, struct _DFS_DOMAINV2_METADATA *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140042a60`
- `0x140046d00`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b90`
- `0x140005dc8`
- `0x14003fa40`
- `0x140040fa8`
- `0x140041064`
- `0x1400411ec`
- `0x140056d2c`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14003fdb6`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14003fe8c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14003ff0b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14003fdb6`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14003fe8c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14003ff0b`
- `WLDAP32!__imp_ldap_add_sW` at `0x14003fd9c`
- `WLDAP32!__imp_ldap_add_sW` at `0x14003fd9c`
- `WLDAP32!__imp_ldap_delete_sW` at `0x14003fe76`
- `WLDAP32!__imp_ldap_delete_sW` at `0x14003fef5`
- `WLDAP32!__imp_ldap_delete_sW` at `0x14003fe76`
- `WLDAP32!__imp_ldap_delete_sW` at `0x14003fef5`

## string_xrefs

- `0x14003fc64`: `msDFS-LinkPathv2`
- `0x14003fc42`: `msDFS-DeletedLinkv2`
- `0x14003fcbc`: `msDFS-Commentv2`
- `0x14003fcec`: `msDFS-LinkIdentityGUIDv2`

## pseudocode

```c
__int64 __fastcall DomainV2MetadataCache::DeleteLinkInAd(
        DomainV2MetadataCache *this,
        struct _DFS_DOMAINV2_METADATA *a2,
        WCHAR **a3)
{
  WCHAR *v6; // rsi
  void *v7; // r12
  unsigned int v8; // edx
  unsigned int UtcTimeString; // r8d
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int *v13; // r10
  unsigned int v15; // r8d
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rax
  LDAPModW *v19; // rcx
  __int64 v20; // rax
  LDAPModW *v21; // rcx
  LDAP *v22; // rcx
  ULONG v23; // eax
  ULONG v24; // eax
  ULONG v25; // eax
  ULONG v26; // eax
  ULONG v27; // eax
  ULONG v28; // eax
  PWSTR dn; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  char *v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  char *v34; // [rsp+58h] [rbp-A8h]
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+70h] [rbp-90h] BYREF
  LDAPModW *attrs[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v38[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-50h]
  _QWORD v40[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v41[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v42[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v43[2]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v44[2]; // [rsp+110h] [rbp+10h] BYREF
  const WCHAR *v45; // [rsp+118h] [rbp+18h]
  _QWORD *v46; // [rsp+120h] [rbp+20h]
  int v47; // [rsp+128h] [rbp+28h] BYREF
  const wchar_t *v48; // [rsp+130h] [rbp+30h]
  _QWORD *v49; // [rsp+138h] [rbp+38h]
  int v50; // [rsp+140h] [rbp+40h] BYREF
  const wchar_t *v51; // [rsp+148h] [rbp+48h]
  _QWORD *v52; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+158h] [rbp+58h] BYREF
  const wchar_t *v54; // [rsp+160h] [rbp+60h]
  _QWORD *v55; // [rsp+168h] [rbp+68h]
  unsigned __int16 v56[20]; // [rsp+1A0h] [rbp+A0h] BYREF

  Block = 0;
  v39 = 0;
  v6 = 0;
  dn = 0;
  v7 = 0;
  v35 = 0;
  v36 = 0;
  *(_OWORD *)attrs = 0;
  memset(v38, 0, sizeof(v38));
  memset_0(v40, 0, 0x50u);
  UtcTimeString = DfsGetUtcTimeString(v56, v8);
  if ( UtcTimeString
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0xA00) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SD(
      *((_QWORD *)pWppControl + 2),
      41,
      (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
      *((_QWORD *)a2 + 13),
      UtcTimeString);
  }
  v10 = anonymous_namespace_::DfspCreateLinkDn(*((_QWORD *)a2 + 13), *((_QWORD *)this + 143), &Block);
  if ( v10 )
    goto LABEL_12;
  v10 = anonymous_namespace_::DfspCreateDeletedLinkDn((char *)a2 + 136, *((_QWORD *)this + 143), &dn);
  if ( v10 )
    goto LABEL_11;
  LOBYTE(v11) = 1;
  v12 = anonymous_namespace_::DfspSwitchSlashesInPath(*((_QWORD *)a2 + 14), v11);
  v10 = 0;
  v7 = (void *)v12;
  if ( !v12 )
  {
    v10 = 8;
LABEL_11:
    v6 = dn;
    goto LABEL_12;
  }
  v44[0] = 0;
  v45 = L"objectClass";
  v40[3] = 0;
  v46 = v40;
  v15 = 3;
  v47 = 0;
  v40[0] = L"top";
  v16 = 3;
  v41[0] = v12;
  v40[1] = L"msDFS-DeletedLinkv2";
  v40[2] = L"dynamicObject";
  attrs[0] = (LDAPModW *)v44;
  v48 = L"msDFS-LinkPathv2";
  v49 = v41;
  attrs[1] = (LDAPModW *)&v47;
  v51 = L"msDFS-LastModifiedv2";
  v52 = v42;
  v42[0] = v56;
  *(_QWORD *)&v38[0] = &v50;
  v17 = *((_QWORD *)a2 + 22);
  v41[1] = 0;
  v50 = 0;
  v42[1] = 0;
  if ( v17 )
  {
    v43[0] = v17;
    v54 = L"msDFS-Commentv2";
    v53 = 0;
    v15 = 4;
    v55 = v43;
    v43[1] = 0;
    v16 = 4;
    *((_QWORD *)&v38[0] + 1) = &v53;
  }
  v32 = (char *)a2 + 136;
  v6 = dn;
  *((_QWORD *)&v35 + 1) = 0;
  v18 = 3LL * v15;
  *((_QWORD *)&v36 + 1) = 0;
  v19 = (LDAPModW *)&v44[6 * v15];
  (&v45)[v18] = L"msDFS-LinkIdentityGUIDv2";
  attrs[v15] = v19;
  (&v46)[v18] = &v35;
  v19->mod_op = 128;
  *(_QWORD *)&v35 = &v31;
  v31 = 16;
  v33 = 16;
  v20 = 3 * (v15 + 1LL);
  v21 = (LDAPModW *)&v44[6 * v15 + 6];
  (&v45)[v20] = L"msDFS-NamespaceIdentityGUIDv2";
  attrs[v15 + 1] = v21;
  (&v46)[v20] = &v36;
  v21->mod_op = 128;
  v22 = (LDAP *)*((_QWORD *)this + 8);
  v34 = (char *)a2 + 120;
  *(_QWORD *)&v36 = &v33;
  *((_QWORD *)v38 + v16) = 0;
  v23 = ldap_add_sW(v22, v6, attrs);
  LODWORD(dn) = v23;
  if ( !v23 )
  {
    v25 = ldap_delete_sW(*((LDAP **)this + 8), (const PWSTR)Block);
    if ( v25 )
    {
      v26 = LdapMapErrorToWin32(v25);
      v10 = v26;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (((1 << (v26 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
        && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        WPP_SF_SD(
          *((_QWORD *)pWppControl + 2),
          44,
          (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
          (_DWORD)Block,
          v26);
      }
      v27 = ldap_delete_sW(*((LDAP **)this + 8), v6);
      if ( v27 )
      {
        v28 = LdapMapErrorToWin32(v27);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_18;
        v13 = pWppControl;
        if ( !pWppControl
          || (((1 << (v28 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) == 0
          || *((_BYTE *)pWppControl + 25) < 3u )
        {
          goto LABEL_13;
        }
        WPP_SF_SD(
          *((_QWORD *)pWppControl + 2),
          45,
          (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
          (_DWORD)v6,
          v28);
      }
    }
    else if ( a3 )
    {
      *a3 = v6;
      v6 = 0;
    }
    goto LABEL_12;
  }
  v24 = LdapMapErrorToWin32(v23);
  v10 = v24;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v13 = pWppControl;
    if ( pWppControl
      && (((1 << (v24 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 42, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v24);
      v13 = pWppControl;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( !v13 || (v13[7] & 0xA00) == 0 || *((_BYTE *)v13 + 25) < 3u )
      {
LABEL_13:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && v13
          && (v13[7] & 0x20) != 0
          && *((_BYTE *)v13 + 25) >= 2u )
        {
          WPP_SF_SSd(
            *((_QWORD *)v13 + 2),
            46,
            (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
            *((_QWORD *)a2 + 14),
            *((_QWORD *)a2 + 13),
            v10);
        }
        goto LABEL_18;
      }
      WPP_SF_D(*((_QWORD *)v13 + 2), 43, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, (unsigned int)dn);
LABEL_12:
      v13 = pWppControl;
      goto LABEL_13;
    }
  }
LABEL_18:
  operator delete(v6);
  operator delete(Block);
  operator delete(v7);
  return v10;
}

```

## disassembly

```asm
0x14003fa40  mov     [rsp-8+arg_18], rbx
0x14003fa45  push    rbp
0x14003fa46  push    rsi
0x14003fa47  push    rdi
0x14003fa48  push    r12
0x14003fa4a  push    r13
0x14003fa4c  push    r14
0x14003fa4e  push    r15
0x14003fa50  lea     rbp, [rsp-0D0h]
0x14003fa58  sub     rsp, 1D0h
0x14003fa5f  mov     rax, cs:__security_cookie
0x14003fa66  xor     rax, rsp
0x14003fa69  mov     [rbp+100h+var_38], rax
0x14003fa70  xor     eax, eax
0x14003fa72  xorps   xmm1, xmm1
0x14003fa75  and     [rsp+200h+Block], rax
0x14003fa7a  xorps   xmm0, xmm0
0x14003fa7d  mov     r13, r8
0x14003fa80  mov     [rbp+100h+var_150], rax
0x14003fa84  mov     r14, rdx
0x14003fa87  mov     r15, rcx
0x14003fa8a  xor     esi, esi
0x14003fa8c  lea     r8d, [rax+50h]; Size
0x14003fa90  xor     edx, edx; Val
0x14003fa92  mov     [rsp+200h+dn], rsi
0x14003fa97  lea     rcx, [rbp+100h+var_140]; void *
0x14003fa9b  xor     r12d, r12d
0x14003fa9e  movups  [rsp+200h+var_1A0], xmm0
0x14003faa3  movups  [rsp+200h+var_190], xmm0
0x14003faa8  movups  xmmword ptr [rbp+100h+attrs], xmm1
0x14003faac  movups  [rbp+100h+var_170], xmm1
0x14003fab0  movups  [rbp+100h+var_160], xmm1
0x14003fab4  call    memset_0
0x14003fab9  lea     rcx, [rbp+100h+var_60]; unsigned __int16 *
0x14003fac0  call    ?DfsGetUtcTimeString@@YAKPEAGK@Z; DfsGetUtcTimeString(ushort *,ulong)
0x14003fac5  mov     r8d, eax
0x14003fac8  mov     edi, 200h
0x14003facd  lea     rax, WPP_GLOBAL_Control
0x14003fad4  test    r8d, r8d
0x14003fad7  jz      short loc_14003FB1B
0x14003fad9  cmp     cs:WPP_GLOBAL_Control, rax
0x14003fae0  jz      short loc_14003FB1B
0x14003fae2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003fae9  test    rcx, rcx
0x14003faec  jz      short loc_14003FB1B
0x14003faee  mov     eax, edi
0x14003faf0  bts     eax, 0Bh
0x14003faf4  test    [rcx+1Ch], eax
0x14003faf7  jz      short loc_14003FB1B
0x14003faf9  cmp     byte ptr [rcx+19h], 3
0x14003fafd  jb      short loc_14003FB1B
0x14003faff  mov     r9, [r14+68h]
0x14003fb03  lea     edx, [rsi+29h]
0x14003fb06  mov     rcx, [rcx+10h]
0x14003fb0a  mov     dword ptr [rsp+200h+var_1E0], r8d
0x14003fb0f  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003fb16  call    WPP_SF_SD
0x14003fb1b  mov     rdx, [r15+478h]
0x14003fb22  lea     r8, [rsp+200h+Block]
0x14003fb27  mov     rcx, [r14+68h]
0x14003fb2b  call    _anonymous_namespace___DfspCreateLinkDn
0x14003fb30  mov     ebx, eax
0x14003fb32  test    eax, eax
0x14003fb34  jnz     short loc_14003FB78
0x14003fb36  mov     rdx, [r15+478h]
0x14003fb3d  lea     rsi, [r14+88h]
0x14003fb44  mov     rcx, rsi
0x14003fb47  lea     r8, [rsp+200h+dn]
0x14003fb4c  call    _anonymous_namespace___DfspCreateDeletedLinkDn
0x14003fb51  mov     ebx, eax
0x14003fb53  test    eax, eax
0x14003fb55  jnz     short loc_14003FB73
0x14003fb57  mov     rcx, [r14+70h]
0x14003fb5b  mov     dl, 1
0x14003fb5d  call    _anonymous_namespace___DfspSwitchSlashesInPath
0x14003fb62  xor     ebx, ebx
0x14003fb64  mov     r12, rax
0x14003fb67  test    rax, rax
0x14003fb6a  jnz     loc_14003FC0F
0x14003fb70  lea     ebx, [rax+8]
0x14003fb73  mov     rsi, [rsp+200h+dn]
0x14003fb78  lea     r13, WPP_GLOBAL_Control
0x14003fb7f  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003fb86  cmp     cs:WPP_GLOBAL_Control, r13
0x14003fb8d  jz      short loc_14003FBC8
0x14003fb8f  test    r10, r10
0x14003fb92  jz      short loc_14003FBC8
0x14003fb94  test    byte ptr [r10+1Ch], 20h
0x14003fb99  jz      short loc_14003FBC8
0x14003fb9b  cmp     byte ptr [r10+19h], 2
0x14003fba0  jb      short loc_14003FBC8
0x14003fba2  mov     rax, [r14+68h]
0x14003fba6  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003fbad  mov     r9, [r14+70h]
0x14003fbb1  mov     edx, 2Eh ; '.'
0x14003fbb6  mov     rcx, [r10+10h]
0x14003fbba  mov     [rsp+200h+var_1D8], ebx
0x14003fbbe  mov     [rsp+200h+var_1E0], rax
0x14003fbc3  call    WPP_SF_SSd
0x14003fbc8  mov     rcx, rsi; Block
0x14003fbcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003fbd0  mov     rcx, [rsp+200h+Block]; Block
0x14003fbd5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003fbda  mov     rcx, r12; Block
0x14003fbdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003fbe2  mov     eax, ebx
0x14003fbe4  mov     rcx, [rbp+100h+var_38]
0x14003fbeb  xor     rcx, rsp; StackCookie
0x14003fbee  call    __security_check_cookie
0x14003fbf3  mov     rbx, [rsp+200h+arg_18]
0x14003fbfb  add     rsp, 1D0h
0x14003fc02  pop     r15
0x14003fc04  pop     r14
0x14003fc06  pop     r13
0x14003fc08  pop     r12
0x14003fc0a  pop     rdi
0x14003fc0b  pop     rsi
0x14003fc0c  pop     rbp
0x14003fc0d  retn
0x14003fc0f  lea     rax, attr; "objectClass"
0x14003fc16  mov     [rbp+100h+var_F0], ebx
0x14003fc19  mov     [rbp+100h+var_E8], rax
0x14003fc1d  mov     ecx, 3
0x14003fc22  lea     rax, [rbp+100h+var_140]
0x14003fc26  mov     [rbp+100h+var_128], rbx
0x14003fc2a  mov     [rbp+100h+var_E0], rax
0x14003fc2e  mov     r8d, ecx
0x14003fc31  lea     rax, aTop; "top"
0x14003fc38  mov     [rbp+100h+var_D8], ebx
0x14003fc3b  mov     [rbp+100h+var_140], rax
0x14003fc3f  mov     r9d, ecx
0x14003fc42  lea     rax, aMsdfsDeletedli; "msDFS-DeletedLinkv2"
0x14003fc49  mov     [rbp+100h+var_120], r12
0x14003fc4d  mov     [rbp+100h+var_138], rax
0x14003fc51  lea     rax, aDynamicobject; "dynamicObject"
0x14003fc58  mov     [rbp+100h+var_130], rax
0x14003fc5c  lea     rax, [rbp+100h+var_F0]
0x14003fc60  mov     [rbp+100h+attrs], rax
0x14003fc64  lea     rax, aMsdfsLinkpathv_0; "msDFS-LinkPathv2"
0x14003fc6b  mov     [rbp+100h+var_D0], rax
0x14003fc6f  lea     rax, [rbp+100h+var_120]
0x14003fc73  mov     [rbp+100h+var_C8], rax
0x14003fc77  lea     rax, [rbp+100h+var_D8]
0x14003fc7b  mov     [rbp+100h+attrs+8], rax
0x14003fc7f  lea     rax, aMsdfsLastmodif; "msDFS-LastModifiedv2"
0x14003fc86  mov     [rbp+100h+var_B8], rax
0x14003fc8a  lea     rax, [rbp+100h+var_110]
0x14003fc8e  mov     [rbp+100h+var_B0], rax
0x14003fc92  lea     rax, [rbp+100h+var_60]
0x14003fc99  mov     [rbp+100h+var_110], rax
0x14003fc9d  lea     rax, [rbp+100h+var_C0]
0x14003fca1  mov     qword ptr [rbp+100h+var_170], rax
0x14003fca5  mov     rax, [r14+0B0h]
0x14003fcac  mov     [rbp+100h+var_118], rbx
0x14003fcb0  mov     [rbp+100h+var_C0], ebx
0x14003fcb3  mov     [rbp+100h+var_108], rbx
0x14003fcb7  test    rax, rax
0x14003fcba  jz      short loc_14003FCE9
0x14003fcbc  lea     rcx, aMsdfsCommentv2; "msDFS-Commentv2"
0x14003fcc3  mov     [rbp+100h+var_100], rax
0x14003fcc7  mov     [rbp+100h+var_A0], rcx
0x14003fccb  lea     rax, [rbp+100h+var_A8]
0x14003fccf  lea     rcx, [rbp+100h+var_100]
0x14003fcd3  mov     [rbp+100h+var_A8], ebx
0x14003fcd6  lea     r8d, [r9+1]
0x14003fcda  mov     [rbp+100h+var_98], rcx
0x14003fcde  mov     [rbp+100h+var_F8], rbx
0x14003fce2  mov     r9d, r8d
0x14003fce5  mov     qword ptr [rbp+100h+var_170+8], rax
0x14003fce9  mov     edx, r8d
0x14003fcec  lea     r10, aMsdfsLinkident; "msDFS-LinkIdentityGUIDv2"
0x14003fcf3  mov     r11d, 80h
0x14003fcf9  mov     [rsp+200h+var_1B8], rsi
0x14003fcfe  mov     rsi, [rsp+200h+dn]
0x14003fd03  lea     rcx, [rbp+100h+var_F0]
0x14003fd07  mov     qword ptr [rsp+200h+var_1A0+8], rbx
0x14003fd0c  lea     rax, [rdx+rdx*2]
0x14003fd10  mov     qword ptr [rsp+200h+var_190+8], rbx
0x14003fd15  lea     rcx, [rcx+rax*8]
0x14003fd19  mov     [rbp+rax*8+100h+var_E8], r10
0x14003fd1e  mov     [rbp+rdx*8+100h+attrs], rcx
0x14003fd23  lea     r10, [rsp+200h+var_1A0]
0x14003fd28  mov     [rbp+rax*8+100h+var_E0], r10
0x14003fd2d  lea     r10d, [r11-70h]
0x14003fd31  mov     edx, r8d
0x14003fd34  lea     rax, [rsp+200h+var_1C0]
0x14003fd39  mov     [rcx], r11d
0x14003fd3c  lea     r8, aMsdfsNamespace; "msDFS-NamespaceIdentityGUIDv2"
0x14003fd43  mov     qword ptr [rsp+200h+var_1A0], rax
0x14003fd48  lea     rcx, [rbp+100h+var_F0]
0x14003fd4c  mov     [rsp+200h+var_1C0], r10d
0x14003fd51  lea     rax, [rdx+1]
0x14003fd55  mov     [rsp+200h+var_1B0], r10d
0x14003fd5a  lea     rax, [rax+rax*2]
0x14003fd5e  lea     rcx, [rcx+rax*8]
0x14003fd62  mov     [rbp+rax*8+100h+var_E8], r8
0x14003fd67  mov     [rbp+rdx*8+100h+attrs+8], rcx
0x14003fd6c  lea     r8, [rsp+200h+var_190]
0x14003fd71  mov     [rbp+rax*8+100h+var_E0], r8
0x14003fd76  mov     rdx, rsi; dn
0x14003fd79  lea     rax, [r14+78h]
0x14003fd7d  mov     [rcx], r11d
0x14003fd80  mov     rcx, [r15+40h]; ld
0x14003fd84  lea     r8, [rbp+100h+attrs]; attrs
0x14003fd88  mov     [rsp+200h+var_1A8], rax
0x14003fd8d  lea     rax, [rsp+200h+var_1B0]
0x14003fd92  mov     qword ptr [rsp+200h+var_190], rax
0x14003fd97  mov     qword ptr [rbp+r9*8+100h+var_170], rbx
0x14003fd9c  call    cs:__imp_ldap_add_sW
0x14003fda3  nop     dword ptr [rax+rax+00h]
0x14003fda8  mov     dword ptr [rsp+200h+dn], eax
0x14003fdac  test    eax, eax
0x14003fdae  jz      loc_14003FE6D
0x14003fdb4  mov     ecx, eax; LdapError
0x14003fdb6  call    cs:__imp_LdapMapErrorToWin32
0x14003fdbd  nop     dword ptr [rax+rax+00h]
0x14003fdc2  mov     ebx, eax
0x14003fdc4  lea     r13, WPP_GLOBAL_Control
0x14003fdcb  cmp     cs:WPP_GLOBAL_Control, r13
0x14003fdd2  jz      loc_14003FBC8
0x14003fdd8  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003fddf  test    r10, r10
0x14003fde2  jz      short loc_14003FE1F
0x14003fde4  neg     eax
0x14003fde6  mov     eax, edi
0x14003fde8  sbb     edx, edx
0x14003fdea  and     edx, 0FFFFFFECh
0x14003fded  add     edx, 1Fh
0x14003fdf0  bts     eax, edx
0x14003fdf3  test    [r10+1Ch], eax
0x14003fdf7  jz      short loc_14003FE1F
0x14003fdf9  cmp     byte ptr [r10+19h], 3
0x14003fdfe  jb      short loc_14003FE1F
0x14003fe00  mov     rcx, [r10+10h]
0x14003fe04  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003fe0b  mov     edx, 2Ah ; '*'
0x14003fe10  mov     r9d, ebx
0x14003fe13  call    WPP_SF_D
0x14003fe18  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003fe1f  cmp     cs:WPP_GLOBAL_Control, r13
0x14003fe26  jz      loc_14003FBC8
0x14003fe2c  test    r10, r10
0x14003fe2f  jz      loc_14003FB86
0x14003fe35  bts     edi, 0Bh
0x14003fe39  test    [r10+1Ch], edi
0x14003fe3d  jz      loc_14003FB86
0x14003fe43  cmp     byte ptr [r10+19h], 3
0x14003fe48  jb      loc_14003FB86
0x14003fe4e  mov     r9d, dword ptr [rsp+200h+dn]
0x14003fe53  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003fe5a  mov     rcx, [r10+10h]
0x14003fe5e  mov     edx, 2Bh ; '+'
0x14003fe63  call    WPP_SF_D
0x14003fe68  jmp     loc_14003FB7F
0x14003fe6d  mov     rdx, [rsp+200h+Block]; dn
0x14003fe72  mov     rcx, [r15+40h]; ld
0x14003fe76  call    cs:__imp_ldap_delete_sW
0x14003fe7d  nop     dword ptr [rax+rax+00h]
0x14003fe82  test    eax, eax
0x14003fe84  jz      loc_14003FF79
0x14003fe8a  mov     ecx, eax; LdapError
0x14003fe8c  call    cs:__imp_LdapMapErrorToWin32
0x14003fe93  nop     dword ptr [rax+rax+00h]
0x14003fe98  mov     ebx, eax
0x14003fe9a  lea     r13, WPP_GLOBAL_Control
0x14003fea1  cmp     cs:WPP_GLOBAL_Control, r13
0x14003fea8  jz      short loc_14003FEEE
0x14003feaa  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003feb1  test    rcx, rcx
0x14003feb4  jz      short loc_14003FEEE
0x14003feb6  neg     eax
0x14003feb8  mov     eax, edi
0x14003feba  sbb     edx, edx
0x14003febc  and     edx, 0FFFFFFECh
0x14003febf  add     edx, 1Fh
0x14003fec2  bts     eax, edx
0x14003fec5  test    [rcx+1Ch], eax
0x14003fec8  jz      short loc_14003FEEE
0x14003feca  cmp     byte ptr [rcx+19h], 3
0x14003fece  jb      short loc_14003FEEE
0x14003fed0  mov     r9, [rsp+200h+Block]
0x14003fed5  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003fedc  mov     rcx, [rcx+10h]
0x14003fee0  mov     edx, 2Ch ; ','
0x14003fee5  mov     dword ptr [rsp+200h+var_1E0], ebx
0x14003fee9  call    WPP_SF_SD
0x14003feee  mov     rcx, [r15+40h]; ld
0x14003fef2  mov     rdx, rsi; dn
0x14003fef5  call    cs:__imp_ldap_delete_sW
0x14003fefc  nop     dword ptr [rax+rax+00h]
0x14003ff01  test    eax, eax
0x14003ff03  jz      loc_14003FB7F
0x14003ff09  mov     ecx, eax; LdapError
0x14003ff0b  call    cs:__imp_LdapMapErrorToWin32
0x14003ff12  nop     dword ptr [rax+rax+00h]
0x14003ff17  cmp     cs:WPP_GLOBAL_Control, r13
0x14003ff1e  jz      loc_14003FBC8
0x14003ff24  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003ff2b  test    r10, r10
0x14003ff2e  jz      loc_14003FB86
  ... truncated ...
```
