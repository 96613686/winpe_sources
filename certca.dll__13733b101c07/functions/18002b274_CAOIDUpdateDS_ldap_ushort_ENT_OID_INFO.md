# CAOIDUpdateDS(ldap *,ushort *,_ENT_OID_INFO *)

- ea: `0x18002b274`
- end: `0x18002b8d2`
- name: `?CAOIDUpdateDS@@YAJPEAUldap@@PEAGPEAU_ENT_OID_INFO@@@Z`
- size: `1630`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, struct _ENT_OID_INFO *)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x18002bbb8`
- `0x18002bd08`
- `0x18002c6a4`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x18000a320`
- `0x18000e130`
- `0x180011600`
- `0x18002b274`
- `0x18002c830`
- `0x1800382c0`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b7b3`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b866`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b878`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b7b3`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b866`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002b878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b89a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b89a`
- `WLDAP32!__imp_ldap_add_ext_sW` at `0x18002b7e6`
- `WLDAP32!__imp_ldap_add_ext_sW` at `0x18002b7e6`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18002b810`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18002b810`

## string_xrefs

- `0x18002b621`: `msPKI-Cert-Template-OID`
- `0x18002b551`: `CN=OID,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CAOIDUpdateDS(struct ldap *a1, unsigned __int16 *a2, struct _ENT_OID_INFO *a3)
{
  int v4; // ebx
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // esi
  unsigned __int16 *v7; // r15
  int v8; // r14d
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rsi
  unsigned int v13; // ecx
  unsigned __int16 *v14; // rax
  int v15; // r14d
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int16 *v18; // rbx
  LDAP *v19; // rsi
  ULONG v20; // eax
  ULONG v21; // r14d
  unsigned int v22; // ecx
  int v23; // edx
  unsigned int v24; // r9d
  unsigned __int16 *v25; // r12
  unsigned __int16 **ClientControls; // [rsp+20h] [rbp-268h]
  HLOCAL hMem; // [rsp+38h] [rbp-250h] BYREF
  unsigned __int16 *v29; // [rsp+40h] [rbp-248h]
  LDAP *ld; // [rsp+48h] [rbp-240h]
  _QWORD v31[3]; // [rsp+50h] [rbp-238h] BYREF
  char v32; // [rsp+68h] [rbp-220h]
  int v33; // [rsp+69h] [rbp-21Fh]
  __int16 v34; // [rsp+6Dh] [rbp-21Bh]
  char v35; // [rsp+6Fh] [rbp-219h]
  __int128 v36; // [rsp+70h] [rbp-218h] BYREF
  __int128 *v37; // [rsp+80h] [rbp-208h]
  __int128 v38; // [rsp+88h] [rbp-200h] BYREF
  __int128 *v39; // [rsp+98h] [rbp-1F0h]
  _QWORD v40[3]; // [rsp+A0h] [rbp-1E8h] BYREF
  char v41; // [rsp+B8h] [rbp-1D0h]
  int v42; // [rsp+B9h] [rbp-1CFh]
  __int16 v43; // [rsp+BDh] [rbp-1CBh]
  char v44; // [rsp+BFh] [rbp-1C9h]
  _QWORD v45[3]; // [rsp+C0h] [rbp-1C8h] BYREF
  char v46; // [rsp+D8h] [rbp-1B0h]
  int v47; // [rsp+D9h] [rbp-1AFh]
  __int16 v48; // [rsp+DDh] [rbp-1ABh]
  char v49; // [rsp+DFh] [rbp-1A9h]
  unsigned __int16 *v50; // [rsp+E0h] [rbp-1A8h]
  __int128 v51; // [rsp+E8h] [rbp-1A0h] BYREF
  __int128 v52; // [rsp+F8h] [rbp-190h] BYREF
  __int128 v53; // [rsp+108h] [rbp-180h] BYREF
  __int128 v54; // [rsp+118h] [rbp-170h] BYREF
  __int128 v55; // [rsp+128h] [rbp-160h] BYREF
  __int128 v56; // [rsp+138h] [rbp-150h] BYREF
  __int128 *v57; // [rsp+148h] [rbp-140h]
  __int128 v58; // [rsp+150h] [rbp-138h] BYREF
  __int128 *v59; // [rsp+160h] [rbp-128h]
  __int128 v60; // [rsp+168h] [rbp-120h] BYREF
  __int128 *v61; // [rsp+178h] [rbp-110h]
  __int128 v62; // [rsp+180h] [rbp-108h] BYREF
  __int128 *v63; // [rsp+190h] [rbp-F8h]
  __int128 v64; // [rsp+1A0h] [rbp-E8h] BYREF
  __int64 v65; // [rsp+1B0h] [rbp-D8h]
  LDAPModW *attrs[2]; // [rsp+1B8h] [rbp-D0h] BYREF
  LDAPModW *mods[2]; // [rsp+1C8h] [rbp-C0h] BYREF
  __int128 v68; // [rsp+1D8h] [rbp-B0h]
  __int64 v69; // [rsp+1E8h] [rbp-A0h]
  PLDAPControlW ServerControls[3]; // [rsp+1F0h] [rbp-98h] BYREF
  PLDAPControlW v71[3]; // [rsp+208h] [rbp-80h] BYREF
  int v72; // [rsp+220h] [rbp-68h] BYREF
  char v73; // [rsp+224h] [rbp-64h]
  int v74; // [rsp+228h] [rbp-60h] BYREF
  char v75; // [rsp+22Ch] [rbp-5Ch]
  unsigned __int16 v76[12]; // [rsp+230h] [rbp-58h] BYREF

  v29 = a2;
  ld = a1;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v62 = 0;
  v63 = 0;
  v60 = 0;
  v61 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  *(_OWORD *)attrs = 0;
  *(_OWORD *)mods = 0;
  v68 = 0;
  v69 = 0;
  v64 = 0;
  v65 = 0;
  v51 = 0;
  v55 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v72 = 16909104;
  v4 = 3;
  v73 = 7;
  v40[0] = L"1.2.840.113556.1.4.801";
  v40[1] = 5;
  v40[2] = &v72;
  v41 = 1;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v31[0] = L"1.2.840.113556.1.4.1413";
  v31[1] = 0;
  v31[2] = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  ServerControls[0] = (PLDAPControlW)v40;
  ServerControls[1] = (PLDAPControlW)v31;
  ServerControls[2] = 0;
  v74 = 16909104;
  v75 = 4;
  v45[0] = L"1.2.840.113556.1.4.801";
  v45[1] = 5;
  v45[2] = &v74;
  v46 = 1;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v71[0] = (PLDAPControlW)v45;
  v71[1] = (PLDAPControlW)v31;
  v71[2] = 0;
  hMem = 0;
  v5 = (const unsigned __int16 *)*((_QWORD *)a3 + 1);
  if ( !v5 )
  {
    v6 = -2147024809;
    CSPrintErrorLineFile(0x24E0336u, -2147024809);
    return v6;
  }
  v7 = 0;
  v8 = *(_DWORD *)a3;
  v9 = myOIDHashOIDToString(v5, (unsigned __int16 **)&hMem);
  v6 = v9;
  if ( !v9 )
  {
    v25 = (unsigned __int16 *)hMem;
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)hMem + v11) );
    do
      ++v10;
    while ( v29[v10] );
    v12 = v11 + v10 + 47;
    if ( v12 > 0x10000 )
    {
      v6 = -2147024362;
      v13 = 39519030;
LABEL_10:
      CSPrintErrorLineFile(v13, v6);
      goto LABEL_37;
    }
    v14 = CertAllocStringLen(0, (int)v12 - 1);
    v7 = v14;
    v50 = v14;
    if ( !v14 )
    {
      v6 = -2147024882;
      v13 = 39912246;
      goto LABEL_10;
    }
    v15 = v8 & 1;
    StringCchCopyW(v14, v12, L"CN=");
    StringCchCatW(v7, v12, v25);
    StringCchCatW(v7, v12, L",");
    StringCchCatW(v7, v12, L"CN=OID,CN=Public Key Services,CN=Services,");
    StringCchCatW(v7, v12, v29);
    LODWORD(v56) = 2;
    *((_QWORD *)&v56 + 1) = L"objectclass";
    v57 = &v64;
    *(_QWORD *)&v64 = L"top";
    *((_QWORD *)&v64 + 1) = L"msPKI-Enterprise-Oid";
    v65 = 0;
    attrs[0] = (LDAPModW *)&v56;
    LODWORD(v58) = 2;
    *((_QWORD *)&v58 + 1) = L"cn";
    v59 = &v51;
    v51 = (unsigned __int64)v25;
    attrs[1] = (LDAPModW *)&v58;
    LODWORD(v60) = 2;
    *((_QWORD *)&v60 + 1) = L"msPKI-Cert-Template-OID";
    v61 = &v52;
    v52 = *((unsigned __int64 *)a3 + 1);
    mods[0] = (LDAPModW *)&v60;
    if ( (*(_BYTE *)a3 & 4) != 0 )
    {
      LODWORD(v36) = 2;
      *((_QWORD *)&v36 + 1) = L"displayName";
      v16 = *((_QWORD *)a3 + 3);
      if ( v16 )
      {
        v37 = &v53;
        v53 = v16;
      }
      else
      {
        v37 = 0;
      }
      if ( !v15 )
      {
        mods[1] = (LDAPModW *)&v36;
        v4 = 4;
      }
    }
    if ( (*(_BYTE *)a3 & 8) != 0 )
    {
      LODWORD(v38) = 2;
      *((_QWORD *)&v38 + 1) = L"msPKI-OID-CPS";
      v17 = *((_QWORD *)a3 + 4);
      if ( v17 )
      {
        v39 = &v54;
        v54 = v17;
      }
      else
      {
        v39 = 0;
      }
      if ( !v15 )
        attrs[v4++] = (LDAPModW *)&v38;
    }
    if ( (*(_BYTE *)a3 & 2) != 0 )
    {
      LODWORD(v62) = 2;
      *((_QWORD *)&v62 + 1) = L"flags";
      v63 = &v55;
      *(_QWORD *)&v55 = v76;
      *((_QWORD *)&v55 + 1) = 0;
      StringCchPrintfW(v76, 0xCu, L"%d", *((unsigned int *)a3 + 4));
      attrs[v4++] = (LDAPModW *)&v62;
    }
    attrs[v4] = 0;
    v18 = (unsigned __int16 *)_set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
    v29 = v18;
    v19 = ld;
    if ( v15 )
    {
      v20 = ldap_add_ext_sW(ld, v7, attrs, ServerControls, 0);
      v21 = v20;
      if ( !v20 )
        goto LABEL_36;
      v22 = 45679414;
      v23 = v20;
    }
    else
    {
      v21 = ldap_modify_ext_sW(ld, v7, mods, v71, 0);
      if ( v21 == 20 )
        v21 = 0;
      v23 = v21;
      if ( !v21 )
        goto LABEL_36;
      v22 = 46596918;
    }
    CSPrintErrorLineFile(v22, v23);
    if ( v21 != 68 )
    {
      v6 = myHLdapError3(v19, v21, 0, v24, ClientControls);
      CSPrintErrorLineFile(0x2CD0336u, v21);
      _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v18);
      goto LABEL_37;
    }
LABEL_36:
    v6 = 0;
    _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))v18);
    goto LABEL_37;
  }
  CSPrintErrorLineFile(0x2550336u, v9);
  v25 = (unsigned __int16 *)hMem;
LABEL_37:
  if ( v25 )
    LocalFree(v25);
  if ( v7 )
    CertFreeString(v7);
  return v6;
}

```

## disassembly

```asm
0x18002b274  mov     r11, rsp
0x18002b277  push    rbx
0x18002b278  push    rsi
0x18002b279  push    rdi
0x18002b27a  push    r12
0x18002b27c  push    r13
0x18002b27e  push    r14
0x18002b280  push    r15
0x18002b282  sub     rsp, 250h
0x18002b289  mov     rax, cs:__security_cookie
0x18002b290  xor     rax, rsp
0x18002b293  mov     [rsp+288h+var_40], rax
0x18002b29b  mov     r13, r8
0x18002b29e  mov     [rsp+288h+var_248], rdx
0x18002b2a3  mov     [rsp+288h+ld], rcx
0x18002b2a8  xorps   xmm0, xmm0
0x18002b2ab  xor     eax, eax
0x18002b2ad  movups  [rsp+288h+var_150], xmm0
0x18002b2b5  mov     [r11-140h], rax
0x18002b2bc  xorps   xmm1, xmm1
0x18002b2bf  movups  [rsp+288h+var_138], xmm1
0x18002b2c7  mov     [r11-128h], rax
0x18002b2ce  movups  [rsp+288h+var_108], xmm0
0x18002b2d6  mov     [r11-0F8h], rax
0x18002b2dd  movups  [rsp+288h+var_120], xmm1
0x18002b2e5  mov     [r11-110h], rax
0x18002b2ec  movups  [rsp+288h+var_218], xmm0
0x18002b2f1  mov     [r11-208h], rax
0x18002b2f8  movups  [rsp+288h+var_200], xmm1
0x18002b300  mov     [r11-1F0h], rax
0x18002b307  movups  xmmword ptr [rsp+288h+attrs], xmm0
0x18002b30f  movups  xmmword ptr [rsp+288h+mods], xmm0
0x18002b317  movups  [rsp+288h+var_B0], xmm0
0x18002b31f  mov     [r11-0A0h], rax
0x18002b326  movups  [rsp+288h+var_E8], xmm0
0x18002b32e  mov     [r11-0D8h], rax
0x18002b335  movups  [rsp+288h+var_1A0], xmm0
0x18002b33d  movups  [rsp+288h+var_160], xmm1
0x18002b345  movups  [rsp+288h+var_190], xmm0
0x18002b34d  movups  [rsp+288h+var_180], xmm1
0x18002b355  movups  [rsp+288h+var_170], xmm0
0x18002b35d  mov     dword ptr [r11-68h], 1020330h
0x18002b365  lea     ebx, [rax+3]
0x18002b368  mov     byte ptr [r11-64h], 7
0x18002b36d  lea     rdx, a12840113556148; "1.2.840.113556.1.4.801"
0x18002b374  mov     [r11-1E8h], rdx
0x18002b37b  mov     qword ptr [r11-1E0h], 5
0x18002b386  lea     rax, [r11-68h]
0x18002b38a  mov     [r11-1D8h], rax
0x18002b391  mov     [rsp+288h+var_1D0], 1
0x18002b399  xor     eax, eax
0x18002b39b  mov     [rsp+288h+var_1CF], eax
0x18002b3a2  mov     [rsp+288h+var_1CB], ax
0x18002b3aa  mov     [rsp+288h+var_1C9], al
0x18002b3b1  lea     rax, a12840113556141; "1.2.840.113556.1.4.1413"
0x18002b3b8  mov     [rsp+288h+var_238], rax
0x18002b3bd  xor     edi, edi
0x18002b3bf  mov     [rsp+288h+var_230], rdi
0x18002b3c4  mov     [rsp+288h+var_228], rdi
0x18002b3c9  mov     [rsp+288h+var_220], dil
0x18002b3ce  xor     eax, eax
0x18002b3d0  mov     [rsp+288h+var_21F], eax
0x18002b3d4  mov     [rsp+288h+var_21B], ax
0x18002b3d9  mov     [rsp+288h+var_219], al
0x18002b3dd  lea     rax, [r11-1E8h]
0x18002b3e4  mov     [r11-98h], rax
0x18002b3eb  lea     rax, [rsp+288h+var_238]
0x18002b3f0  mov     [r11-90h], rax
0x18002b3f7  mov     [r11-88h], rdi
0x18002b3fe  mov     dword ptr [r11-60h], 1020330h
0x18002b406  mov     byte ptr [r11-5Ch], 4
0x18002b40b  mov     [r11-1C8h], rdx
0x18002b412  mov     qword ptr [r11-1C0h], 5
0x18002b41d  lea     rax, [r11-60h]
0x18002b421  mov     [r11-1B8h], rax
0x18002b428  mov     [rsp+288h+var_1B0], 1
0x18002b430  xor     eax, eax
0x18002b432  mov     [rsp+288h+var_1AF], eax
0x18002b439  mov     [rsp+288h+var_1AB], ax
0x18002b441  mov     [rsp+288h+var_1A9], al
0x18002b448  lea     rax, [r11-1C8h]
0x18002b44f  mov     [r11-80h], rax
0x18002b453  lea     rax, [rsp+288h+var_238]
0x18002b458  mov     [r11-78h], rax
0x18002b45c  mov     [r11-70h], rdi
0x18002b460  mov     [rsp+288h+hMem], rdi
0x18002b465  mov     rcx, [r8+8]; unsigned __int16 *
0x18002b469  test    rcx, rcx
0x18002b46c  jnz     short loc_18002B484
0x18002b46e  mov     esi, 80070057h
0x18002b473  mov     edx, esi; int
0x18002b475  mov     ecx, 24E0336h; unsigned int
0x18002b47a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b47f  jmp     loc_18002B8AD
0x18002b484  mov     r15, rdi
0x18002b487  mov     r14d, [r8]
0x18002b48a  lea     rdx, [rsp+288h+hMem]; unsigned __int16 **
0x18002b48f  call    ?myOIDHashOIDToString@@YAJPEBGPEAPEAG@Z; myOIDHashOIDToString(ushort const *,ushort * *)
0x18002b494  mov     esi, eax
0x18002b496  test    eax, eax
0x18002b498  jz      short loc_18002B4AB
0x18002b49a  mov     edx, eax; int
0x18002b49c  mov     ecx, 2550336h; unsigned int
0x18002b4a1  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b4a6  jmp     loc_18002B88D
0x18002b4ab  mov     r12, [rsp+288h+hMem]
0x18002b4b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b4b4  mov     rcx, rax
0x18002b4b7  inc     rcx
0x18002b4ba  cmp     [r12+rcx*2], di
0x18002b4bf  jnz     short loc_18002B4B7
0x18002b4c1  mov     rdx, [rsp+288h+var_248]
0x18002b4c6  inc     rax
0x18002b4c9  cmp     [rdx+rax*2], di
0x18002b4cd  jnz     short loc_18002B4C6
0x18002b4cf  lea     rsi, [rax+2Fh]
0x18002b4d3  add     rsi, rcx
0x18002b4d6  cmp     rsi, 10000h
0x18002b4dd  jbe     short loc_18002B4F5
0x18002b4df  mov     esi, 80070216h
0x18002b4e4  mov     ecx, 25B0336h; unsigned int
0x18002b4e9  mov     edx, esi; int
0x18002b4eb  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b4f0  jmp     loc_18002B892
0x18002b4f5  lea     edx, [rsi-1]; unsigned int
0x18002b4f8  xor     ecx, ecx; Src
0x18002b4fa  call    ?CertAllocStringLen@@YAPEAGPEBGI@Z; CertAllocStringLen(ushort const *,uint)
0x18002b4ff  mov     r15, rax
0x18002b502  mov     [rsp+288h+var_1A8], rax
0x18002b50a  test    rax, rax
0x18002b50d  jnz     short loc_18002B51B
0x18002b50f  mov     esi, 8007000Eh
0x18002b514  mov     ecx, 2610336h
0x18002b519  jmp     short loc_18002B4E9
0x18002b51b  and     r14d, 1
0x18002b51f  lea     r8, aCn_2; "CN="
0x18002b526  mov     rdx, rsi; unsigned __int64
0x18002b529  mov     rcx, r15; unsigned __int16 *
0x18002b52c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b531  mov     r8, r12; unsigned __int16 *
0x18002b534  mov     rdx, rsi; unsigned __int64
0x18002b537  mov     rcx, r15; unsigned __int16 *
0x18002b53a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b53f  lea     r8, asc_180063424; ","
0x18002b546  mov     rdx, rsi; unsigned __int64
0x18002b549  mov     rcx, r15; unsigned __int16 *
0x18002b54c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b551  lea     r8, aCnOidCnPublicK; "CN=OID,CN=Public Key Services,CN=Servic"...
0x18002b558  mov     rdx, rsi; unsigned __int64
0x18002b55b  mov     rcx, r15; unsigned __int16 *
0x18002b55e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b563  mov     r8, [rsp+288h+var_248]; unsigned __int16 *
0x18002b568  mov     rdx, rsi; unsigned __int64
0x18002b56b  mov     rcx, r15; unsigned __int16 *
0x18002b56e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b573  mov     edx, 2
0x18002b578  mov     dword ptr [rsp+288h+var_150], edx
0x18002b57f  lea     rax, aObjectclass_2; "objectclass"
0x18002b586  mov     qword ptr [rsp+288h+var_150+8], rax
0x18002b58e  lea     rax, [rsp+288h+var_E8]
0x18002b596  mov     [rsp+288h+var_140], rax
0x18002b59e  lea     rax, aTop; "top"
0x18002b5a5  mov     qword ptr [rsp+288h+var_E8], rax
0x18002b5ad  lea     rax, aMspkiEnterpris; "msPKI-Enterprise-Oid"
0x18002b5b4  mov     qword ptr [rsp+288h+var_E8+8], rax
0x18002b5bc  mov     [rsp+288h+var_D8], rdi
0x18002b5c4  lea     rax, [rsp+288h+var_150]
0x18002b5cc  mov     [rsp+288h+attrs], rax
0x18002b5d4  mov     dword ptr [rsp+288h+var_138], edx
0x18002b5db  lea     rax, aCn_1; "cn"
0x18002b5e2  mov     qword ptr [rsp+288h+var_138+8], rax
0x18002b5ea  lea     rax, [rsp+288h+var_1A0]
0x18002b5f2  mov     [rsp+288h+var_128], rax
0x18002b5fa  mov     qword ptr [rsp+288h+var_1A0], r12
0x18002b602  mov     qword ptr [rsp+288h+var_1A0+8], rdi
0x18002b60a  lea     rax, [rsp+288h+var_138]
0x18002b612  mov     [rsp+288h+attrs+8], rax
0x18002b61a  mov     dword ptr [rsp+288h+var_120], edx
0x18002b621  lea     rax, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002b628  mov     qword ptr [rsp+288h+var_120+8], rax
0x18002b630  lea     rax, [rsp+288h+var_190]
0x18002b638  mov     [rsp+288h+var_110], rax
0x18002b640  mov     rax, [r13+8]
0x18002b644  mov     qword ptr [rsp+288h+var_190], rax
0x18002b64c  mov     qword ptr [rsp+288h+var_190+8], rdi
0x18002b654  lea     rax, [rsp+288h+var_120]
0x18002b65c  mov     [rsp+288h+mods], rax
0x18002b664  test    byte ptr [r13+0], 4
0x18002b669  jz      short loc_18002B6C4
0x18002b66b  mov     dword ptr [rsp+288h+var_218], edx
0x18002b66f  lea     rax, aDisplayname_0; "displayName"
0x18002b676  mov     qword ptr [rsp+288h+var_218+8], rax
0x18002b67b  mov     rax, [r13+18h]
0x18002b67f  test    rax, rax
0x18002b682  jz      short loc_18002B6A6
0x18002b684  lea     rcx, [rsp+288h+var_180]
0x18002b68c  mov     [rsp+288h+var_208], rcx
0x18002b694  mov     qword ptr [rsp+288h+var_180], rax
0x18002b69c  mov     qword ptr [rsp+288h+var_180+8], rdi
0x18002b6a4  jmp     short loc_18002B6AE
0x18002b6a6  mov     [rsp+288h+var_208], rdi
0x18002b6ae  test    r14d, r14d
0x18002b6b1  jnz     short loc_18002B6C4
0x18002b6b3  lea     rax, [rsp+288h+var_218]
0x18002b6b8  mov     [rsp+288h+mods+8], rax
0x18002b6c0  lea     ebx, [r14+4]
0x18002b6c4  test    byte ptr [r13+0], 8
0x18002b6c9  jz      short loc_18002B72D
0x18002b6cb  mov     dword ptr [rsp+288h+var_200], edx
0x18002b6d2  lea     rax, aMspkiOidCps; "msPKI-OID-CPS"
0x18002b6d9  mov     qword ptr [rsp+288h+var_200+8], rax
0x18002b6e1  mov     rax, [r13+20h]
0x18002b6e5  test    rax, rax
0x18002b6e8  jz      short loc_18002B70C
0x18002b6ea  lea     rcx, [rsp+288h+var_170]
0x18002b6f2  mov     [rsp+288h+var_1F0], rcx
0x18002b6fa  mov     qword ptr [rsp+288h+var_170], rax
0x18002b702  mov     qword ptr [rsp+288h+var_170+8], rdi
0x18002b70a  jmp     short loc_18002B714
0x18002b70c  mov     [rsp+288h+var_1F0], rdi
0x18002b714  test    r14d, r14d
0x18002b717  jnz     short loc_18002B72D
0x18002b719  mov     eax, ebx
0x18002b71b  lea     rcx, [rsp+288h+var_200]
0x18002b723  mov     [rsp+rax*8+288h+attrs], rcx
0x18002b72b  inc     ebx
0x18002b72d  test    [r13+0], dl
0x18002b731  jz      short loc_18002B7A2
0x18002b733  mov     dword ptr [rsp+288h+var_108], edx
0x18002b73a  lea     rax, attr; "flags"
0x18002b741  mov     qword ptr [rsp+288h+var_108+8], rax
0x18002b749  lea     rax, [rsp+288h+var_160]
0x18002b751  mov     [rsp+288h+var_F8], rax
0x18002b759  lea     rax, [rsp+288h+var_58]
0x18002b761  mov     qword ptr [rsp+288h+var_160], rax
0x18002b769  mov     qword ptr [rsp+288h+var_160+8], rdi
0x18002b771  mov     r9d, [r13+10h]
0x18002b775  lea     r8, aD; "%d"
0x18002b77c  mov     edx, 0Ch; unsigned __int64
0x18002b781  lea     rcx, [rsp+288h+var_58]; unsigned __int16 *
0x18002b789  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b78e  mov     eax, ebx
0x18002b790  lea     rcx, [rsp+288h+var_108]
0x18002b798  mov     [rsp+rax*8+288h+attrs], rcx
0x18002b7a0  inc     ebx
0x18002b7a2  mov     eax, ebx
0x18002b7a4  mov     [rsp+rax*8+288h+attrs], rdi
0x18002b7ac  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18002b7b3  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002b7b9  mov     rbx, rax
0x18002b7bc  mov     [rsp+288h+var_248], rax
0x18002b7c1  mov     [rsp+288h+ClientControls], rdi; unsigned __int16 **
0x18002b7c6  mov     rdx, r15; dn
0x18002b7c9  mov     rsi, [rsp+288h+ld]
0x18002b7ce  mov     rcx, rsi; ld
0x18002b7d1  test    r14d, r14d
0x18002b7d4  jz      short loc_18002B800
0x18002b7d6  lea     r9, [rsp+288h+ServerControls]; ServerControls
0x18002b7de  lea     r8, [rsp+288h+attrs]; attrs
0x18002b7e6  call    cs:__imp_ldap_add_ext_sW
0x18002b7ec  mov     r14d, eax
0x18002b7ef  mov     [rsp+288h+var_254], eax
0x18002b7f3  test    eax, eax
0x18002b7f5  jz      short loc_18002B86F
0x18002b7f7  mov     ecx, 2B90336h
0x18002b7fc  mov     edx, eax
0x18002b7fe  jmp     short loc_18002B836
0x18002b800  lea     r9, [rsp+288h+var_80]; ServerControls
0x18002b808  lea     r8, [rsp+288h+mods]; mods
0x18002b810  call    cs:__imp_ldap_modify_ext_sW
0x18002b816  mov     r14d, eax
0x18002b819  mov     [rsp+288h+var_254], eax
0x18002b81d  cmp     eax, 14h
0x18002b820  cmovz   r14d, edi
0x18002b824  mov     [rsp+288h+var_254], r14d
0x18002b829  mov     edx, r14d; int
0x18002b82c  test    r14d, r14d
0x18002b82f  jz      short loc_18002B86F
0x18002b831  mov     ecx, 2C70336h; unsigned int
0x18002b836  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b83b  cmp     r14d, 44h ; 'D'
0x18002b83f  jz      short loc_18002B86F
0x18002b841  xor     r8d, r8d; unsigned int
0x18002b844  mov     edx, r14d; unsigned int
0x18002b847  mov     rcx, rsi; ld
0x18002b84a  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x18002b84f  mov     esi, eax
0x18002b851  mov     [rsp+288h+var_258], eax
0x18002b855  mov     edx, r14d; int
0x18002b858  mov     ecx, 2CD0336h; unsigned int
0x18002b85d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b862  nop
0x18002b863  mov     rcx, rbx
0x18002b866  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002b86c  nop
0x18002b86d  jmp     short loc_18002B892
0x18002b86f  mov     esi, edi
0x18002b871  mov     [rsp+288h+var_258], edi
0x18002b875  mov     rcx, rbx
0x18002b878  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
  ... truncated ...
```
