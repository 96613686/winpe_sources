# I_CAOIDCreateNew(ulong,ulong,ushort * *,ldap *)

- ea: `0x18002bd08`
- end: `0x18002c021`
- name: `?I_CAOIDCreateNew@@YAJKKPEAPEAGPEAUldap@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(int, __int64, unsigned __int16 **, struct ldap *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002cac0`
- `0x18002fa68`
- `0x1800315b4`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x18000e52c`
- `0x180011158`
- `0x180012680`
- `0x18002a7f4`
- `0x18002a8b0`
- `0x18002ab94`
- `0x18002b274`
- `0x18002b9a4`
- `0x18002bd08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bd86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bd86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002be4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bdd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bdd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bfe3`
- `WLDAP32!__imp_ldap_unbind` at `0x18002bffe`
- `WLDAP32!__imp_ldap_unbind` at `0x18002bffe`

## pseudocode

```c
__int64 __fastcall I_CAOIDCreateNew(int a1, __int64 a2, unsigned __int16 **a3, struct ldap *a4)
{
  struct ldap *v4; // r12
  LDAP *v5; // r13
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rsi
  HLOCAL v8; // rdi
  HLOCAL v9; // r15
  unsigned int v10; // ebx
  bool v11; // zf
  const unsigned __int16 *v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  struct ldap *v19; // rbx
  unsigned int i; // r12d
  int v21; // eax
  unsigned int v22; // ecx
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // edx
  unsigned int v26; // eax
  SIZE_T uBytes; // [rsp+20h] [rbp-60h] BYREF
  HLOCAL v29; // [rsp+28h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-50h] BYREF
  LDAP *ld; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-38h]
  _QWORD v34[2]; // [rsp+50h] [rbp-30h] BYREF
  int v35; // [rsp+60h] [rbp-20h]
  __int128 v36; // [rsp+64h] [rbp-1Ch]
  int v37; // [rsp+74h] [rbp-Ch]
  struct ldap *v40; // [rsp+D8h] [rbp+58h]

  v40 = a4;
  v4 = a4;
  ld = 0;
  v5 = 0;
  v32 = 0;
  v6 = 0;
  uBytes = 0;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  hMem = 0;
  v9 = 0;
  if ( !a3 )
  {
    v10 = -2147024809;
    CSPrintErrorLineFile(0x50F0336u, -2147024809);
    return v10;
  }
  v11 = g_fOidURL == 0;
  *a3 = 0;
  if ( !v11 )
  {
    EnterCriticalSection(&g_csOidURL);
    v12 = (const unsigned __int16 *)g_pwszEnterpriseRootOID;
    if ( g_pwszEnterpriseRootOID )
    {
      uBytes = 0;
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)g_pwszEnterpriseRootOID + v13) );
      v33 = v13 + 1;
      if ( v13 + 1 < v13 || (int)ULongLongMult(v13 + 1, 2u, &uBytes) < 0 )
      {
        v10 = -2147024362;
        goto LABEL_17;
      }
      v14 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes);
      uBytes = (SIZE_T)v14;
      v7 = v14;
      if ( !v14 )
      {
        v10 = -2147024882;
LABEL_17:
        LeaveCriticalSection(&g_csOidURL);
        goto LABEL_43;
      }
      StringCchCopyW(v14, v33, v12);
    }
    LeaveCriticalSection(&g_csOidURL);
  }
  if ( !v4 )
  {
    v15 = myTimeOutRobustLdapBind(&ld);
    v10 = v15;
    if ( v15 )
    {
      CSPrintErrorLineFile(0x9E0336u, v15);
      CSPrintErrorLineFile(0x5270336u, v10);
      v5 = ld;
      goto LABEL_43;
    }
    v5 = ld;
    v4 = ld;
    v40 = ld;
  }
  v16 = CAGetAuthoritativeDomainDn(v4, 0, &v32);
  v10 = v16;
  if ( !v16 )
  {
    v6 = v32;
    if ( !v7 )
    {
      v18 = CAOIDRetrieveEnterpriseRootWithConfig(v4, v32, v17, (unsigned __int16 **)&uBytes);
      v10 = v18;
      if ( v18 )
      {
        CSPrintErrorLineFile(0x5330336u, v18);
        v7 = (unsigned __int16 *)uBytes;
        goto LABEL_43;
      }
      v7 = (unsigned __int16 *)uBytes;
    }
    v19 = v40;
    for ( i = 0; i < 0x32; ++i )
    {
      v21 = CAOIDGetRandom((unsigned __int16 **)&hMem);
      v10 = v21;
      if ( v21 )
      {
        CSPrintErrorLineFile(0x53A0336u, v21);
        v9 = hMem;
        goto LABEL_39;
      }
      v9 = hMem;
      v23 = CAOIDBuildOIDWithRoot(v22, v7, (const unsigned __int16 *)hMem, (unsigned __int16 **)&v29);
      v10 = v23;
      if ( v23 )
      {
        CSPrintErrorLineFile(0x53D0336u, v23);
        v8 = v29;
        goto LABEL_39;
      }
      v8 = v29;
      v19 = v40;
      if ( !(unsigned int)DoesOIDExist(v40, v6, (const unsigned __int16 *)v29) )
        goto LABEL_36;
      LocalFree(v9);
      v9 = 0;
      hMem = 0;
      LocalFree(v8);
      v8 = 0;
      v29 = 0;
    }
    if ( i == 50 )
    {
      v10 = -2147467259;
      v24 = 88867638;
      v25 = -2147467259;
    }
    else
    {
LABEL_36:
      v34[0] = 15;
      v37 = 0;
      v35 = a1;
      v36 = 0;
      v34[1] = v8;
      v26 = CAOIDUpdateDS(v19, v6, (struct _ENT_OID_INFO *)v34);
      v10 = v26;
      if ( !v26 )
      {
        *a3 = (unsigned __int16 *)v8;
        v8 = 0;
        v10 = 0;
LABEL_39:
        if ( v9 )
          LocalFree(v9);
        if ( v8 )
          LocalFree(v8);
        goto LABEL_43;
      }
      v25 = v26;
      v24 = 89522998;
    }
    CSPrintErrorLineFile(v24, v25);
    goto LABEL_39;
  }
  CSPrintErrorLineFile(0x52D0336u, v16);
  v6 = v32;
LABEL_43:
  if ( v7 )
    LocalFree(v7);
  if ( v6 )
    CertFreeString(v6);
  if ( v5 )
    ldap_unbind(v5);
  return v10;
}

```

## disassembly

```asm
0x18002bd08  mov     rax, rsp
0x18002bd0b  mov     [rax+10h], rbx
0x18002bd0f  mov     [rax+20h], r9
0x18002bd13  mov     [rax+18h], r8
0x18002bd17  mov     [rax+8], ecx
0x18002bd1a  push    rbp
0x18002bd1b  push    rsi
0x18002bd1c  push    rdi
0x18002bd1d  push    r12
0x18002bd1f  push    r13
0x18002bd21  push    r14
0x18002bd23  push    r15
0x18002bd25  mov     rbp, rsp
0x18002bd28  sub     rsp, 80h
0x18002bd2f  xor     ecx, ecx
0x18002bd31  mov     r12, r9
0x18002bd34  mov     [rbp+ld], rcx
0x18002bd38  mov     r13d, ecx
0x18002bd3b  mov     [rbp+var_40], rcx
0x18002bd3f  mov     r14d, ecx
0x18002bd42  mov     [rbp+uBytes], rcx
0x18002bd46  mov     esi, ecx
0x18002bd48  mov     [rbp+var_58], rcx
0x18002bd4c  mov     edi, ecx
0x18002bd4e  mov     [rbp+hMem], rcx
0x18002bd52  mov     r15d, ecx
0x18002bd55  test    r8, r8
0x18002bd58  jnz     short loc_18002BD70
0x18002bd5a  mov     ebx, 80070057h
0x18002bd5f  mov     ecx, 50F0336h; unsigned int
0x18002bd64  mov     edx, ebx; int
0x18002bd66  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002bd6b  jmp     loc_18002C004
0x18002bd70  cmp     cs:?g_fOidURL@@3HA, ecx; int g_fOidURL
0x18002bd76  mov     [r8], rcx
0x18002bd79  jz      loc_18002BE0E
0x18002bd7f  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002bd86  call    cs:__imp_EnterCriticalSection
0x18002bd8c  mov     rbx, cs:?g_pwszEnterpriseRootOID@@3PEAGEA; ushort * g_pwszEnterpriseRootOID
0x18002bd93  xor     r9d, r9d
0x18002bd96  test    rbx, rbx
0x18002bd99  jz      short loc_18002BE01
0x18002bd9b  mov     [rbp+uBytes], r9
0x18002bd9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bda3  inc     rax
0x18002bda6  cmp     [rbx+rax*2], r9w
0x18002bdab  jnz     short loc_18002BDA3
0x18002bdad  lea     rcx, [rax+1]; unsigned __int64
0x18002bdb1  mov     [rbp+var_38], rcx
0x18002bdb5  cmp     rcx, rax
0x18002bdb8  jb      loc_18002BE43
0x18002bdbe  lea     r8, [rbp+uBytes]; unsigned __int64 *
0x18002bdc2  mov     edx, 2; unsigned __int64
0x18002bdc7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002bdcc  test    eax, eax
0x18002bdce  js      short loc_18002BE43
0x18002bdd0  mov     rdx, [rbp+uBytes]; uBytes
0x18002bdd4  mov     ecx, 40h ; '@'; uFlags
0x18002bdd9  call    cs:__imp_LocalAlloc
0x18002bddf  mov     [rbp+uBytes], rax
0x18002bde3  mov     rsi, rax
0x18002bde6  test    rax, rax
0x18002bde9  jnz     short loc_18002BDF2
0x18002bdeb  mov     ebx, 8007000Eh
0x18002bdf0  jmp     short loc_18002BE48
0x18002bdf2  mov     rdx, [rbp+var_38]; unsigned __int64
0x18002bdf6  mov     r8, rbx; unsigned __int16 *
0x18002bdf9  mov     rcx, rax; unsigned __int16 *
0x18002bdfc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002be01  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002be08  call    cs:__imp_LeaveCriticalSection
0x18002be0e  test    r12, r12
0x18002be11  jnz     short loc_18002BE65
0x18002be13  lea     rcx, [rbp+ld]; struct ldap **
0x18002be17  call    ?myTimeOutRobustLdapBind@@YAJPEAPEAUldap@@@Z; myTimeOutRobustLdapBind(ldap * *)
0x18002be1c  mov     ebx, eax
0x18002be1e  test    eax, eax
0x18002be20  jz      short loc_18002BE5A
0x18002be22  mov     edx, eax; int
0x18002be24  mov     ecx, 9E0336h; unsigned int
0x18002be29  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002be2e  mov     edx, ebx; int
0x18002be30  mov     ecx, 5270336h; unsigned int
0x18002be35  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002be3a  mov     r13, [rbp+ld]
0x18002be3e  jmp     loc_18002BFDB
0x18002be43  mov     ebx, 80070216h
0x18002be48  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002be4f  call    cs:__imp_LeaveCriticalSection
0x18002be55  jmp     loc_18002BFDB
0x18002be5a  mov     r13, [rbp+ld]
0x18002be5e  mov     r12, r13
0x18002be61  mov     [rbp+arg_18], r13
0x18002be65  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18002be69  xor     edx, edx; unsigned __int16 **
0x18002be6b  mov     rcx, r12; struct ldap *
0x18002be6e  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x18002be73  mov     ebx, eax
0x18002be75  test    eax, eax
0x18002be77  jz      short loc_18002BE8E
0x18002be79  mov     edx, eax; int
0x18002be7b  mov     ecx, 52D0336h; unsigned int
0x18002be80  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002be85  mov     r14, [rbp+var_40]
0x18002be89  jmp     loc_18002BFDB
0x18002be8e  mov     r14, [rbp+var_40]
0x18002be92  test    rsi, rsi
0x18002be95  jnz     short loc_18002BEC5
0x18002be97  lea     r9, [rbp+uBytes]; unsigned __int16 **
0x18002be9b  mov     rdx, r14; unsigned __int16 *
0x18002be9e  mov     rcx, r12; ld
0x18002bea1  call    ?CAOIDRetrieveEnterpriseRootWithConfig@@YAJPEAUldap@@PEAGKPEAPEAG@Z; CAOIDRetrieveEnterpriseRootWithConfig(ldap *,ushort *,ulong,ushort * *)
0x18002bea6  mov     ebx, eax
0x18002bea8  test    eax, eax
0x18002beaa  jz      short loc_18002BEC1
0x18002beac  mov     edx, eax; int
0x18002beae  mov     ecx, 5330336h; unsigned int
0x18002beb3  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002beb8  mov     rsi, [rbp+uBytes]
0x18002bebc  jmp     loc_18002BFDB
0x18002bec1  mov     rsi, [rbp+uBytes]
0x18002bec5  mov     rbx, [rbp+arg_18]
0x18002bec9  xor     r12d, r12d
0x18002becc  cmp     r12d, 32h ; '2'
0x18002bed0  jnb     loc_18002BF60
0x18002bed6  lea     rcx, [rbp+hMem]; unsigned __int16 **
0x18002beda  call    ?CAOIDGetRandom@@YAJPEAPEAG@Z; CAOIDGetRandom(ushort * *)
0x18002bedf  mov     ebx, eax
0x18002bee1  test    eax, eax
0x18002bee3  jnz     short loc_18002BF4E
0x18002bee5  mov     r15, [rbp+hMem]
0x18002bee9  lea     r9, [rbp+var_58]; unsigned __int16 **
0x18002beed  mov     r8, r15; unsigned __int16 *
0x18002bef0  mov     rdx, rsi; unsigned __int16 *
0x18002bef3  call    ?CAOIDBuildOIDWithRoot@@YAJKPEBG0PEAPEAG@Z; CAOIDBuildOIDWithRoot(ulong,ushort const *,ushort const *,ushort * *)
0x18002bef8  mov     ebx, eax
0x18002befa  test    eax, eax
0x18002befc  jnz     short loc_18002BF3C
0x18002befe  mov     rdi, [rbp+var_58]
0x18002bf02  mov     rdx, r14; unsigned __int16 *
0x18002bf05  mov     rbx, [rbp+arg_18]
0x18002bf09  mov     r8, rdi; unsigned __int16 *
0x18002bf0c  mov     rcx, rbx; ld
0x18002bf0f  call    ?DoesOIDExist@@YAHPEAUldap@@PEAGPEBG@Z; DoesOIDExist(ldap *,ushort *,ushort const *)
0x18002bf14  test    eax, eax
0x18002bf16  jz      short loc_18002BF75
0x18002bf18  mov     rcx, r15; hMem
0x18002bf1b  call    cs:__imp_LocalFree
0x18002bf21  xor     r15d, r15d
0x18002bf24  mov     rcx, rdi; hMem
0x18002bf27  mov     [rbp+hMem], r15
0x18002bf2b  call    cs:__imp_LocalFree
0x18002bf31  xor     edi, edi
0x18002bf33  mov     [rbp+var_58], rdi
0x18002bf37  inc     r12d
0x18002bf3a  jmp     short loc_18002BECC
0x18002bf3c  mov     edx, eax; int
0x18002bf3e  mov     ecx, 53D0336h; unsigned int
0x18002bf43  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002bf48  mov     rdi, [rbp+var_58]
0x18002bf4c  jmp     short loc_18002BFBF
0x18002bf4e  mov     edx, eax; int
0x18002bf50  mov     ecx, 53A0336h; unsigned int
0x18002bf55  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002bf5a  mov     r15, [rbp+hMem]
0x18002bf5e  jmp     short loc_18002BFBF
0x18002bf60  jnz     short loc_18002BF75
0x18002bf62  mov     ebx, 80004005h
0x18002bf67  mov     ecx, 54C0336h; unsigned int
0x18002bf6c  mov     edx, ebx; int
0x18002bf6e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002bf73  jmp     short loc_18002BFBF
0x18002bf75  mov     eax, [rbp+arg_0]
0x18002bf78  lea     r8, [rbp+var_30]; struct _ENT_OID_INFO *
0x18002bf7c  xorps   xmm0, xmm0
0x18002bf7f  mov     [rbp+var_30], 0Fh
0x18002bf87  mov     rdx, r14; unsigned __int16 *
0x18002bf8a  mov     [rbp+var_C], 0
0x18002bf91  mov     rcx, rbx; struct ldap *
0x18002bf94  mov     [rbp+var_20], eax
0x18002bf97  movdqu  [rbp+var_1C], xmm0
0x18002bf9c  mov     [rbp+var_28], rdi
0x18002bfa0  call    ?CAOIDUpdateDS@@YAJPEAUldap@@PEAGPEAU_ENT_OID_INFO@@@Z; CAOIDUpdateDS(ldap *,ushort *,_ENT_OID_INFO *)
0x18002bfa5  mov     ebx, eax
0x18002bfa7  test    eax, eax
0x18002bfa9  jz      short loc_18002BFB4
0x18002bfab  mov     edx, eax
0x18002bfad  mov     ecx, 5560336h
0x18002bfb2  jmp     short loc_18002BF6E
0x18002bfb4  mov     rax, [rbp+arg_10]
0x18002bfb8  mov     [rax], rdi
0x18002bfbb  xor     edi, edi
0x18002bfbd  xor     ebx, ebx
0x18002bfbf  test    r15, r15
0x18002bfc2  jz      short loc_18002BFCD
0x18002bfc4  mov     rcx, r15; hMem
0x18002bfc7  call    cs:__imp_LocalFree
0x18002bfcd  test    rdi, rdi
0x18002bfd0  jz      short loc_18002BFDB
0x18002bfd2  mov     rcx, rdi; hMem
0x18002bfd5  call    cs:__imp_LocalFree
0x18002bfdb  test    rsi, rsi
0x18002bfde  jz      short loc_18002BFE9
0x18002bfe0  mov     rcx, rsi; hMem
0x18002bfe3  call    cs:__imp_LocalFree
0x18002bfe9  test    r14, r14
0x18002bfec  jz      short loc_18002BFF6
0x18002bfee  mov     rcx, r14; unsigned __int16 *
0x18002bff1  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x18002bff6  test    r13, r13
0x18002bff9  jz      short loc_18002C004
0x18002bffb  mov     rcx, r13; ld
0x18002bffe  call    cs:__imp_ldap_unbind
0x18002c004  mov     eax, ebx
0x18002c006  mov     rbx, [rsp+80h+arg_8]
0x18002c00e  add     rsp, 80h
0x18002c015  pop     r15
0x18002c017  pop     r14
0x18002c019  pop     r13
0x18002c01b  pop     r12
0x18002c01d  pop     rdi
0x18002c01e  pop     rsi
0x18002c01f  pop     rbp
0x18002c020  retn
```
