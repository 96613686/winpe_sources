# DomainV2MetadataCache::UpdateLinkPathInAd(_DFS_DOMAINV2_METADATA *)

- ea: `0x140043234`
- end: `0x14004352b`
- name: `?UpdateLinkPathInAd@DomainV2MetadataCache@@QEAAKPEAU_DFS_DOMAINV2_METADATA@@@Z`
- size: `759`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, struct _DFS_DOMAINV2_METADATA *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x140046d00`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b90`
- `0x140005dc8`
- `0x140041064`
- `0x1400411ec`
- `0x140043234`
- `0x140056d2c`
- `0x14005ce70`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140043295`
- `RPCRT4!UuidCreate` at `0x140043295`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14004340e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14004340e`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1400433f5`
- `WLDAP32!__imp_ldap_modify_sW` at `0x1400433f5`

## string_xrefs

- `0x140043347`: `msDFS-LinkPathv2`

## pseudocode

```c
RPC_STATUS __fastcall DomainV2MetadataCache::UpdateLinkPathInAd(
        DomainV2MetadataCache *this,
        struct _DFS_DOMAINV2_METADATA *a2)
{
  void *v3; // r14
  RPC_STATUS result; // eax
  unsigned int v6; // edx
  unsigned int UtcTimeString; // eax
  __int64 v8; // rdx
  int v9; // ebx
  LDAP *v10; // rcx
  ULONG v11; // eax
  ULONG v12; // r15d
  ULONG v13; // eax
  unsigned int *v14; // rcx
  PWSTR dn; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  UUID *p_Uuid; // [rsp+50h] [rbp-B0h]
  UUID Uuid; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  __int128 v21; // [rsp+78h] [rbp-88h] BYREF
  LDAPModW *mods[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v23; // [rsp+98h] [rbp-68h]
  int v24; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v25; // [rsp+B8h] [rbp-48h]
  __int128 *v26; // [rsp+C0h] [rbp-40h]
  int v27; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v28; // [rsp+D0h] [rbp-30h]
  __int128 *v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v31; // [rsp+E8h] [rbp-18h]
  __int128 *v32; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v33[20]; // [rsp+100h] [rbp+0h] BYREF

  v3 = 0;
  dn = 0;
  v16 = 0;
  *(_OWORD *)mods = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  Uuid = 0;
  result = UuidCreate(&Uuid);
  if ( !result )
  {
    UtcTimeString = DfsGetUtcTimeString(v33, v6);
    if ( UtcTimeString
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0xA00) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_SD(
        *((_QWORD *)pWppControl + 2),
        37,
        (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
        *((_QWORD *)a2 + 13),
        UtcTimeString);
    }
    v9 = anonymous_namespace_::DfspCreateLinkDn(*((_QWORD *)a2 + 13), *((_QWORD *)this + 143), &dn);
    if ( !v9 )
    {
      LOBYTE(v8) = 1;
      v3 = (void *)anonymous_namespace_::DfspSwitchSlashesInPath(*((_QWORD *)a2 + 14), v8);
      if ( v3 )
      {
        v25 = L"msDFS-LinkPathv2";
        v26 = &v20;
        mods[0] = (LDAPModW *)&v24;
        v28 = L"msDFS-LastModifiedv2";
        v29 = &v21;
        v21 = (unsigned __int64)v33;
        mods[1] = (LDAPModW *)&v27;
        v31 = L"msDFS-GenerationGUIDv2";
        v32 = &v16;
        p_Uuid = &Uuid;
        v16 = (unsigned __int64)&v17;
        v24 = 2;
        v27 = 2;
        v10 = (LDAP *)*((_QWORD *)this + 8);
        v23 = (unsigned __int64)&v30;
        v20 = (unsigned __int64)v3;
        v30 = 130;
        v17 = 16;
        v11 = ldap_modify_sW(v10, dn, mods);
        v12 = v11;
        if ( v11 )
        {
          v13 = LdapMapErrorToWin32(v11);
          v9 = v13;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_29;
          v14 = pWppControl;
          if ( pWppControl
            && (((1 << (v13 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
            && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 38, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v13);
            v14 = pWppControl;
          }
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_29;
          if ( !v14 || (v14[7] & 0xA00) == 0 || *((_BYTE *)v14 + 25) < 3u )
          {
LABEL_24:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && v14
              && (v14[7] & 0x20) != 0
              && *((_BYTE *)v14 + 25) >= 2u )
            {
              WPP_SF_SSd(
                *((_QWORD *)v14 + 2),
                40,
                (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
                *((_QWORD *)a2 + 14),
                *((_QWORD *)a2 + 13),
                v9);
            }
LABEL_29:
            operator delete(dn);
            operator delete(v3);
            return v9;
          }
          WPP_SF_D(*((_QWORD *)v14 + 2), 39, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v12);
        }
        else
        {
          v9 = 0;
        }
      }
      else
      {
        v9 = 8;
      }
    }
    v14 = pWppControl;
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x140043234  mov     [rsp-8+arg_10], rbx
0x140043239  mov     [rsp-8+arg_18], rsi
0x14004323e  push    rbp
0x14004323f  push    rdi
0x140043240  push    r13
0x140043242  push    r14
0x140043244  push    r15
0x140043246  lea     rbp, [rsp-30h]
0x14004324b  sub     rsp, 130h
0x140043252  mov     rax, cs:__security_cookie
0x140043259  xor     rax, rsp
0x14004325c  mov     [rbp+50h+var_28], rax
0x140043260  xorps   xmm0, xmm0
0x140043263  xorps   xmm1, xmm1
0x140043266  mov     r15, rcx
0x140043269  xor     r14d, r14d
0x14004326c  and     [rsp+150h+dn], r14
0x140043271  lea     rcx, [rsp+150h+Uuid]; Uuid
0x140043276  movups  [rsp+150h+var_118], xmm0
0x14004327b  mov     rsi, rdx
0x14004327e  movups  xmmword ptr [rbp+50h+mods], xmm1
0x140043282  movups  [rbp+50h+var_B8], xmm1
0x140043286  movups  [rsp+150h+var_E8], xmm0
0x14004328b  movups  [rsp+150h+var_D8], xmm0
0x140043290  movups  xmmword ptr [rsp+150h+Uuid.Data1], xmm0
0x140043295  call    cs:__imp_UuidCreate
0x14004329c  nop     dword ptr [rax+rax+00h]
0x1400432a1  test    eax, eax
0x1400432a3  jnz     loc_140043502
0x1400432a9  lea     rcx, [rbp+50h+var_50]; unsigned __int16 *
0x1400432ad  call    ?DfsGetUtcTimeString@@YAKPEAGK@Z; DfsGetUtcTimeString(ushort *,ulong)
0x1400432b2  lea     r13, WPP_GLOBAL_Control
0x1400432b9  mov     r8d, eax
0x1400432bc  mov     edi, 200h
0x1400432c1  test    eax, eax
0x1400432c3  jz      short loc_140043308
0x1400432c5  cmp     cs:WPP_GLOBAL_Control, r13
0x1400432cc  jz      short loc_140043308
0x1400432ce  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400432d5  test    rcx, rcx
0x1400432d8  jz      short loc_140043308
0x1400432da  mov     eax, edi
0x1400432dc  bts     eax, 0Bh
0x1400432e0  test    [rcx+1Ch], eax
0x1400432e3  jz      short loc_140043308
0x1400432e5  cmp     byte ptr [rcx+19h], 3
0x1400432e9  jb      short loc_140043308
0x1400432eb  mov     r9, [rsi+68h]
0x1400432ef  lea     edx, [r14+25h]
0x1400432f3  mov     rcx, [rcx+10h]
0x1400432f7  mov     dword ptr [rsp+150h+var_130], r8d
0x1400432fc  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140043303  call    WPP_SF_SD
0x140043308  mov     rdx, [r15+478h]
0x14004330f  lea     r8, [rsp+150h+dn]
0x140043314  mov     rcx, [rsi+68h]
0x140043318  call    _anonymous_namespace___DfspCreateLinkDn
0x14004331d  mov     ebx, eax
0x14004331f  test    eax, eax
0x140043321  jnz     loc_1400434A7
0x140043327  mov     rcx, [rsi+70h]
0x14004332b  mov     dl, 1
0x14004332d  call    _anonymous_namespace___DfspSwitchSlashesInPath
0x140043332  mov     r14, rax
0x140043335  test    rax, rax
0x140043338  jnz     short loc_140043342
0x14004333a  lea     ebx, [rax+8]
0x14004333d  jmp     loc_1400434A7
0x140043342  mov     rdx, [rsp+150h+dn]; dn
0x140043347  lea     rax, aMsdfsLinkpathv_0; "msDFS-LinkPathv2"
0x14004334e  and     qword ptr [rsp+150h+var_E8+8], 0
0x140043354  lea     r8, [rbp+50h+mods]; mods
0x140043358  and     qword ptr [rbp+50h+var_D8+8], 0
0x14004335d  mov     ecx, 2
0x140043362  and     qword ptr [rsp+150h+var_118+8], 0
0x140043368  and     qword ptr [rbp+50h+var_B8+8], 0
0x14004336d  mov     [rbp+50h+var_98], rax
0x140043371  lea     rax, [rsp+150h+var_E8]
0x140043376  mov     [rbp+50h+var_90], rax
0x14004337a  lea     rax, [rbp+50h+var_A0]
0x14004337e  mov     [rbp+50h+mods], rax
0x140043382  lea     rax, aMsdfsLastmodif; "msDFS-LastModifiedv2"
0x140043389  mov     [rbp+50h+var_80], rax
0x14004338d  lea     rax, [rsp+150h+var_D8]
0x140043392  mov     [rbp+50h+var_78], rax
0x140043396  lea     rax, [rbp+50h+var_50]
0x14004339a  mov     qword ptr [rsp+150h+var_D8], rax
0x14004339f  lea     rax, [rbp+50h+var_88]
0x1400433a3  mov     [rbp+50h+mods+8], rax
0x1400433a7  lea     rax, aMsdfsGeneratio; "msDFS-GenerationGUIDv2"
0x1400433ae  mov     [rbp+50h+var_68], rax
0x1400433b2  lea     rax, [rsp+150h+var_118]
0x1400433b7  mov     [rbp+50h+var_60], rax
0x1400433bb  lea     rax, [rsp+150h+Uuid]
0x1400433c0  mov     [rsp+150h+var_100], rax
0x1400433c5  lea     rax, [rsp+150h+var_108]
0x1400433ca  mov     qword ptr [rsp+150h+var_118], rax
0x1400433cf  lea     rax, [rbp+50h+var_70]
0x1400433d3  mov     [rbp+50h+var_A0], ecx
0x1400433d6  mov     [rbp+50h+var_88], ecx
0x1400433d9  mov     rcx, [r15+40h]; ld
0x1400433dd  mov     qword ptr [rbp+50h+var_B8], rax
0x1400433e1  mov     qword ptr [rsp+150h+var_E8], r14
0x1400433e6  mov     [rbp+50h+var_70], 82h
0x1400433ed  mov     [rsp+150h+var_108], 10h
0x1400433f5  call    cs:__imp_ldap_modify_sW
0x1400433fc  nop     dword ptr [rax+rax+00h]
0x140043401  mov     r15d, eax
0x140043404  test    eax, eax
0x140043406  jz      loc_1400434A5
0x14004340c  mov     ecx, eax; LdapError
0x14004340e  call    cs:__imp_LdapMapErrorToWin32
0x140043415  nop     dword ptr [rax+rax+00h]
0x14004341a  mov     ebx, eax
0x14004341c  cmp     cs:WPP_GLOBAL_Control, r13
0x140043423  jz      loc_1400434EE
0x140043429  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140043430  test    rcx, rcx
0x140043433  jz      short loc_14004346E
0x140043435  neg     eax
0x140043437  mov     eax, edi
0x140043439  sbb     edx, edx
0x14004343b  and     edx, 0FFFFFFECh
0x14004343e  add     edx, 1Fh
0x140043441  bts     eax, edx
0x140043444  test    [rcx+1Ch], eax
0x140043447  jz      short loc_14004346E
0x140043449  cmp     byte ptr [rcx+19h], 3
0x14004344d  jb      short loc_14004346E
0x14004344f  mov     rcx, [rcx+10h]
0x140043453  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14004345a  mov     edx, 26h ; '&'
0x14004345f  mov     r9d, ebx
0x140043462  call    WPP_SF_D
0x140043467  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004346e  cmp     cs:WPP_GLOBAL_Control, r13
0x140043475  jz      short loc_1400434EE
0x140043477  test    rcx, rcx
0x14004347a  jz      short loc_1400434AE
0x14004347c  bts     edi, 0Bh
0x140043480  test    [rcx+1Ch], edi
0x140043483  jz      short loc_1400434AE
0x140043485  cmp     byte ptr [rcx+19h], 3
0x140043489  jb      short loc_1400434AE
0x14004348b  mov     rcx, [rcx+10h]
0x14004348f  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140043496  mov     edx, 27h ; '''
0x14004349b  mov     r9d, r15d
0x14004349e  call    WPP_SF_D
0x1400434a3  jmp     short loc_1400434A7
0x1400434a5  xor     ebx, ebx
0x1400434a7  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400434ae  cmp     cs:WPP_GLOBAL_Control, r13
0x1400434b5  jz      short loc_1400434EE
0x1400434b7  test    rcx, rcx
0x1400434ba  jz      short loc_1400434EE
0x1400434bc  test    byte ptr [rcx+1Ch], 20h
0x1400434c0  jz      short loc_1400434EE
0x1400434c2  cmp     byte ptr [rcx+19h], 2
0x1400434c6  jb      short loc_1400434EE
0x1400434c8  mov     rax, [rsi+68h]
0x1400434cc  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x1400434d3  mov     r9, [rsi+70h]
0x1400434d7  mov     edx, 28h ; '('
0x1400434dc  mov     rcx, [rcx+10h]
0x1400434e0  mov     [rsp+150h+var_128], ebx
0x1400434e4  mov     [rsp+150h+var_130], rax
0x1400434e9  call    WPP_SF_SSd
0x1400434ee  mov     rcx, [rsp+150h+dn]; Block
0x1400434f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400434f8  mov     rcx, r14; Block
0x1400434fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140043500  mov     eax, ebx
0x140043502  mov     rcx, [rbp+50h+var_28]
0x140043506  xor     rcx, rsp; StackCookie
0x140043509  call    __security_check_cookie
0x14004350e  lea     r11, [rsp+150h+var_20]
0x140043516  mov     rbx, [r11+40h]
0x14004351a  mov     rsi, [r11+48h]
0x14004351e  mov     rsp, r11
0x140043521  pop     r15
0x140043523  pop     r14
0x140043525  pop     r13
0x140043527  pop     rdi
0x140043528  pop     rbp
0x140043529  retn
```
