# UpdateSidNameCaches(_ApPluginPkg *,_ApPluginSubPkg * *,ushort * *,ushort const *,ushort const *,_APPLUGIN_USER_INFO *,ushort const *)

- ea: `0x18000498c`
- end: `0x180004e78`
- name: `?UpdateSidNameCaches@@YAJPEAU_ApPluginPkg@@PEAPEAU_ApPluginSubPkg@@PEAPEAGPEBG3PEAU_APPLUGIN_USER_INFO@@3@Z`
- size: `1260`
- prototype: `__int64 __usercall@<rax>(struct _ApPluginPkg *@<rcx>, struct _ApPluginSubPkg **@<rdx>, unsigned __int16 **@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct _APPLUGIN_USER_INFO *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004e7b0`
- `0x18004f600`

## callees

- `0x180003ef4`
- `0x1800046f4`
- `0x18000498c`
- `0x180004e80`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x18004cf50`
- `0x18004e1b8`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180004a8a`
- `ntdll!RtlReleaseResource` at `0x180004afe`
- `ntdll!RtlReleaseResource` at `0x180004b7d`
- `ntdll!RtlReleaseResource` at `0x180004c2c`
- `ntdll!RtlReleaseResource` at `0x180004a8a`
- `ntdll!RtlReleaseResource` at `0x180004afe`
- `ntdll!RtlReleaseResource` at `0x180004b7d`
- `ntdll!RtlReleaseResource` at `0x180004c2c`
- `ntdll!RtlAcquireResourceShared` at `0x180004a1b`
- `ntdll!RtlAcquireResourceShared` at `0x180004c16`
- `ntdll!RtlAcquireResourceShared` at `0x180004a1b`
- `ntdll!RtlAcquireResourceShared` at `0x180004c16`

## string_xrefs

- `0x180004b1e`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180004cdc`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180004de8`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180004b8a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180004c32`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180004d8b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180004e4a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180004acf`: `AddEntryInLookupCacheForSubPkgs`
- `0x180004b38`: `_AddEntryInLookupCache`
- `0x180004cf6`: `_AddEntryInLookupCache(SubPkg)`
- `0x180004dfe`: `FlushIdentityCache`

## pseudocode

```c
__int64 __fastcall UpdateSidNameCaches(
        struct _ApPluginPkg *a1,
        struct _RTL_BALANCED_NODE **a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _APPLUGIN_USER_INFO *a6,
        unsigned __int16 *a7)
{
  struct _APPLUGIN_USER_INFO *v10; // rsi
  struct _RTL_BALANCED_NODE *v11; // rdi
  const unsigned __int16 *v12; // rbp
  HKEY ParentValue; // r12
  HKEY v14; // rbx
  unsigned int v15; // eax
  void *v16; // rsi
  unsigned int v17; // ebx
  __int64 v18; // r10
  __int64 v19; // r8
  int v20; // ecx
  const char *v21; // rax
  const char *v22; // rdx
  const char *v24; // r9
  const char *v25; // rax
  const char *v26; // r8
  int v27; // eax
  const char *v28; // rdx
  _WORD *v29; // rcx
  _WORD *v30; // rcx
  _WORD *v31; // rcx
  WCHAR *v32; // rbx
  const char *v33; // r9
  const char *v34; // rax
  int v35; // eax
  struct _RTL_BALANCED_NODE *v36; // rdi
  int v37; // eax
  const char *v38; // r9
  const char *v39; // rax
  void *v40; // [rsp+20h] [rbp-88h]
  unsigned __int16 *v41; // [rsp+50h] [rbp-58h]
  unsigned int v42; // [rsp+B0h] [rbp+8h]
  int v43; // [rsp+B8h] [rbp+10h] BYREF
  int v44; // [rsp+C0h] [rbp+18h] BYREF
  unsigned __int16 *v45; // [rsp+C8h] [rbp+20h]

  v45 = a4;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v10 = a6;
  if ( (*((_DWORD *)a1 + 40) & 0xD) != 8
    || (v29 = (_WORD *)*((_QWORD *)a6 + 9)) == 0
    || !*v29
    || (v30 = (_WORD *)*((_QWORD *)a6 + 10)) == 0
    || !*v30
    || (v31 = (_WORD *)*((_QWORD *)a6 + 11)) == 0
    || !*v31 )
  {
    v11 = 0;
    v12 = (const unsigned __int16 *)((char *)a1 + 24);
    ParentValue = 0;
    goto LABEL_5;
  }
  v17 = RegisterSubPackage(0, a1, *((const unsigned __int16 **)a6 + 10), *((unsigned __int16 **)a6 + 11));
  if ( v17 )
  {
    v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v38, 5766, "RegisterSubPackage", &Class);
    return v17;
  }
  v32 = (WCHAR *)*((_QWORD *)v10 + 10);
  RtlAcquireResourceShared(*((PRTL_RESOURCE *)a1 + 45), 1u);
  if ( !v32 )
    goto LABEL_36;
  v11 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)a1 + 47);
  if ( !v11 )
    goto LABEL_50;
  while ( 1 )
  {
    v35 = SubPkgTable_CompareNames(v32, v11);
    if ( v35 >= 0 )
      break;
    v11 = v11->Children[0];
LABEL_48:
    if ( !v11 )
      goto LABEL_49;
  }
  if ( v35 > 0 )
  {
    v11 = v11->Children[1];
    goto LABEL_48;
  }
LABEL_49:
  if ( v11 )
    goto LABEL_56;
LABEL_50:
  v36 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)a1 + 48);
  if ( !v36 )
  {
LABEL_36:
    RtlReleaseResource(*((PRTL_RESOURCE *)a1 + 45));
    v17 = -2146893039;
    v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v33, 5769, "RefSubPackage", &Class);
    return v17;
  }
  while ( 2 )
  {
    v37 = SubPkgTable_CompareDnsNames(v32, v36);
    if ( v37 < 0 )
    {
      v36 = v36->Children[0];
      goto LABEL_53;
    }
    if ( v37 > 0 )
    {
      v36 = v36->Children[1];
LABEL_53:
      if ( !v36 )
        break;
      continue;
    }
    break;
  }
  if ( !v36 )
    goto LABEL_36;
  v11 = v36 - 1;
LABEL_56:
  ParentValue = (HKEY)v11[24].ParentValue;
  v12 = (const unsigned __int16 *)&v11[2];
LABEL_5:
  v14 = (HKEY)*((_QWORD *)a1 + 44);
  v41 = (unsigned __int16 *)*((_QWORD *)v10 + 5);
  v15 = *((_DWORD *)v10 + 32);
  v16 = (void *)*((_QWORD *)v10 + 2);
  v42 = v15;
  v43 = 0;
  v44 = 0;
  RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
  v17 = _AddEntryInLookupCache(v14, v12, v45, a5, v16, v42, a7, v41, &v43);
  if ( v17 )
  {
    v24 = "";
    do
      v25 = v24--;
    while ( *v24 != 92 && v24 > "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" );
    v26 = "_AddEntryInLookupCache";
    if ( *v24 == 92 )
      v24 = v25;
    v27 = 2289;
LABEL_23:
    LODWORD(v40) = v27;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v24, v40, v26, &Class);
    RtlReleaseResource(&g_LookupsCacheLock);
LABEL_24:
    v21 = "";
    do
      v28 = v21--;
    while ( *v21 != 92 && v21 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v18 = 0;
    v19 = v17;
    v20 = 5792;
    if ( *v21 == 92 )
      v21 = v28;
    v22 = "AddEntryInLookupCacheForSubPkgs";
LABEL_14:
    LODWORD(v40) = v20;
    WPPTraceLogA(v18, "0x%08x %s:%u : %s:%ws", v19, v21, v40, v22, &Class);
    if ( v11 )
      RtlReleaseResource(*((PRTL_RESOURCE *)a1 + 45));
  }
  else
  {
    if ( ParentValue )
    {
      v17 = _AddEntryInLookupCache(ParentValue, v12, v45, a5, v16, v42, a7, v41, &v44);
      if ( v17 )
      {
        v24 = "";
        do
          v34 = v24--;
        while ( *v24 != 92 && v24 > "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" );
        v26 = "_AddEntryInLookupCache(SubPkg)";
        if ( *v24 == 92 )
          v24 = v34;
        v27 = 2304;
        goto LABEL_23;
      }
    }
    RtlReleaseResource(&g_LookupsCacheLock);
    if ( v43 || v44 )
    {
      v17 = FlushIdentityCache(v16);
      if ( v17 )
      {
        v39 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(v40) = 2313;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v39, v40, "FlushIdentityCache", &Class);
        goto LABEL_24;
      }
    }
    if ( a3 )
    {
      v17 = DuplicateString(v12, 0, a3);
      if ( v17 )
      {
        v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v22 = "DuplicateString";
        v20 = 5797;
        goto LABEL_14;
      }
    }
    *a2 = v11;
    return 0;
  }
  return v17;
}

```

## disassembly

```asm
0x18000498c  mov     [rsp+arg_18], r9
0x180004991  push    rbx
0x180004992  push    rbp
0x180004993  push    rsi
0x180004994  push    rdi
0x180004995  push    r12
0x180004997  push    r13
0x180004999  push    r14
0x18000499b  push    r15
0x18000499d  sub     rsp, 68h
0x1800049a1  mov     qword ptr [rdx], 0
0x1800049a8  mov     r15, r8
0x1800049ab  mov     r13, rdx
0x1800049ae  mov     r14, rcx
0x1800049b1  test    r8, r8
0x1800049b4  jnz     loc_180004D7F
0x1800049ba  mov     eax, [rcx+0A0h]
0x1800049c0  mov     rsi, [rsp+0A8h+arg_28]
0x1800049c8  and     al, 0Dh
0x1800049ca  cmp     al, 8
0x1800049cc  jz      loc_180004BAA
0x1800049d2  xor     edi, edi
0x1800049d4  lea     rbp, [r14+18h]
0x1800049d8  xor     r12d, r12d
0x1800049db  mov     rax, [rsi+28h]
0x1800049df  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800049e6  mov     rbx, [r14+160h]
0x1800049ed  mov     dl, 1; Wait
0x1800049ef  mov     [rsp+0A8h+var_58], rax
0x1800049f4  mov     eax, [rsi+80h]
0x1800049fa  mov     rsi, [rsi+10h]
0x1800049fe  mov     [rsp+0A8h+arg_0], eax
0x180004a05  mov     [rsp+0A8h+arg_8], 0
0x180004a10  mov     [rsp+0A8h+arg_10], 0
0x180004a1b  call    cs:__imp_RtlAcquireResourceShared
0x180004a21  mov     r9, [rsp+0A8h+arg_20]; unsigned __int16 *
0x180004a29  lea     rax, [rsp+0A8h+arg_8]
0x180004a31  mov     r8, [rsp+0A8h+arg_18]; unsigned __int16 *
0x180004a39  mov     rdx, rbp; unsigned __int16 *
0x180004a3c  mov     [rsp+0A8h+var_68], rax; int *
0x180004a41  mov     rcx, rbx; hKey
0x180004a44  mov     rax, [rsp+0A8h+var_58]
0x180004a49  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x180004a4e  mov     rax, [rsp+0A8h+arg_30]
0x180004a56  mov     [rsp+0A8h+var_78], rax; unsigned __int16 *
0x180004a5b  mov     eax, [rsp+0A8h+arg_0]
0x180004a62  mov     [rsp+0A8h+var_80], eax; unsigned int
0x180004a66  mov     [rsp+0A8h+var_88], rsi; void *
0x180004a6b  call    ?_AddEntryInLookupCache@@YAJPEAUHKEY__@@PEBG11PEAXK11PEAH@Z; _AddEntryInLookupCache(HKEY__ *,ushort const *,ushort const *,ushort const *,void *,ulong,ushort const *,ushort const *,int *)
0x180004a70  mov     ebx, eax
0x180004a72  test    eax, eax
0x180004a74  jnz     loc_180004B17
0x180004a7a  test    r12, r12
0x180004a7d  jnz     loc_180004C7C
0x180004a83  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180004a8a  call    cs:__imp_RtlReleaseResource
0x180004a90  cmp     [rsp+0A8h+arg_8], 0
0x180004a98  jnz     loc_180004DD6
0x180004a9e  cmp     [rsp+0A8h+arg_10], 0
0x180004aa6  jnz     loc_180004DD6
0x180004aac  test    r15, r15
0x180004aaf  jnz     loc_180004E30
0x180004ab5  mov     [r13+0], rdi
0x180004ab9  xor     ebx, ebx
0x180004abb  jmp     short loc_180004B04
0x180004abd  xor     r10d, r10d
0x180004ac0  mov     r8d, ebx
0x180004ac3  cmp     byte ptr [rax], 5Ch ; '\'
0x180004ac6  mov     ecx, 16A0h
0x180004acb  cmovz   rax, rdx
0x180004acf  lea     rdx, aAddentryinlook_0; "AddEntryInLookupCacheForSubPkgs"
0x180004ad6  mov     [rsp+0A8h+var_78], rbp
0x180004adb  mov     r9, rax
0x180004ade  mov     qword ptr [rsp+0A8h+var_80], rdx
0x180004ae3  mov     rdx, rsi
0x180004ae6  mov     dword ptr [rsp+0A8h+var_88], ecx
0x180004aea  mov     rcx, r10
0x180004aed  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180004af2  test    rdi, rdi
0x180004af5  jz      short loc_180004B04
0x180004af7  mov     rcx, [r14+168h]; Resource
0x180004afe  call    cs:__imp_RtlReleaseResource
0x180004b04  mov     eax, ebx
0x180004b06  add     rsp, 68h
0x180004b0a  pop     r15
0x180004b0c  pop     r14
0x180004b0e  pop     r13
0x180004b10  pop     r12
0x180004b12  pop     rdi
0x180004b13  pop     rsi
0x180004b14  pop     rbp
0x180004b15  pop     rbx
0x180004b16  retn
0x180004b17  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x180004b1e  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180004b25  mov     rax, r9
0x180004b28  dec     r9
0x180004b2b  cmp     byte ptr [r9], 5Ch ; '\'
0x180004b2f  jz      short loc_180004B36
0x180004b31  cmp     r9, rcx
0x180004b34  ja      short loc_180004B25
0x180004b36  xor     ecx, ecx
0x180004b38  lea     r8, aAddentryinlook_2; "_AddEntryInLookupCache"
0x180004b3f  cmp     byte ptr [r9], 5Ch ; '\'
0x180004b43  cmovz   r9, rax
0x180004b47  mov     eax, 8F1h
0x180004b4c  lea     rbp, Class
0x180004b53  mov     [rsp+0A8h+var_78], rbp
0x180004b58  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180004b5f  mov     qword ptr [rsp+0A8h+var_80], r8
0x180004b64  mov     r10, rbp
0x180004b67  mov     r8d, ebx
0x180004b6a  mov     dword ptr [rsp+0A8h+var_88], eax
0x180004b6e  mov     rdx, rsi
0x180004b71  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180004b76  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180004b7d  call    cs:__imp_RtlReleaseResource
0x180004b83  lea     rax, aOnecoreDsExtCl_6+27h; ""
0x180004b8a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180004b91  mov     rdx, rax
0x180004b94  dec     rax
0x180004b97  cmp     byte ptr [rax], 5Ch ; '\'
0x180004b9a  jz      loc_180004ABD
0x180004ba0  cmp     rax, rcx
0x180004ba3  ja      short loc_180004B91
0x180004ba5  jmp     loc_180004ABD
0x180004baa  mov     rcx, [rsi+48h]
0x180004bae  test    rcx, rcx
0x180004bb1  jz      loc_1800049D2
0x180004bb7  xor     eax, eax
0x180004bb9  cmp     ax, [rcx]
0x180004bbc  jz      loc_1800049D2
0x180004bc2  mov     rcx, [rsi+50h]
0x180004bc6  test    rcx, rcx
0x180004bc9  jz      loc_1800049D2
0x180004bcf  cmp     ax, [rcx]
0x180004bd2  jz      loc_1800049D2
0x180004bd8  mov     rcx, [rsi+58h]
0x180004bdc  test    rcx, rcx
0x180004bdf  jz      loc_1800049D2
0x180004be5  cmp     ax, [rcx]
0x180004be8  jz      loc_1800049D2
0x180004bee  mov     r8, [rsi+50h]; unsigned __int16 *
0x180004bf2  mov     r9, rcx; unsigned __int16 *
0x180004bf5  xor     ecx, ecx; int
0x180004bf7  mov     rdx, r14; struct _ApPluginPkg *
0x180004bfa  call    ?RegisterSubPackage@@YAJHPEAU_ApPluginPkg@@PEBG1@Z; RegisterSubPackage(int,_ApPluginPkg *,ushort const *,ushort const *)
0x180004bff  mov     ebx, eax
0x180004c01  test    eax, eax
0x180004c03  jnz     loc_180004D8B
0x180004c09  mov     rcx, [r14+168h]; Resource
0x180004c10  mov     dl, 1; Wait
0x180004c12  mov     rbx, [rsi+50h]
0x180004c16  call    cs:__imp_RtlAcquireResourceShared
0x180004c1c  test    rbx, rbx
0x180004c1f  jnz     loc_180004D0F
0x180004c25  mov     rcx, [r14+168h]; Resource
0x180004c2c  call    cs:__imp_RtlReleaseResource
0x180004c32  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180004c39  mov     ebx, 80090311h
0x180004c3e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004c43  mov     r9, rax
0x180004c46  lea     rbp, Class
0x180004c4d  mov     [rsp+0A8h+var_78], rbp
0x180004c52  lea     rax, aRefsubpackage; "RefSubPackage"
0x180004c59  mov     qword ptr [rsp+0A8h+var_80], rax
0x180004c5e  mov     dword ptr [rsp+0A8h+var_88], 1689h
0x180004c66  mov     r8d, ebx
0x180004c69  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180004c70  xor     ecx, ecx
0x180004c72  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180004c77  jmp     loc_180004B04
0x180004c7c  mov     r9, [rsp+0A8h+arg_20]; unsigned __int16 *
0x180004c84  lea     rax, [rsp+0A8h+arg_10]
0x180004c8c  mov     r8, [rsp+0A8h+arg_18]; unsigned __int16 *
0x180004c94  mov     rdx, rbp; unsigned __int16 *
0x180004c97  mov     [rsp+0A8h+var_68], rax; int *
0x180004c9c  mov     rcx, r12; hKey
0x180004c9f  mov     rax, [rsp+0A8h+var_58]
0x180004ca4  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x180004ca9  mov     rax, [rsp+0A8h+arg_30]
0x180004cb1  mov     [rsp+0A8h+var_78], rax; unsigned __int16 *
0x180004cb6  mov     eax, [rsp+0A8h+arg_0]
0x180004cbd  mov     [rsp+0A8h+var_80], eax; unsigned int
0x180004cc1  mov     [rsp+0A8h+var_88], rsi; void *
0x180004cc6  call    ?_AddEntryInLookupCache@@YAJPEAUHKEY__@@PEBG11PEAXK11PEAH@Z; _AddEntryInLookupCache(HKEY__ *,ushort const *,ushort const *,ushort const *,void *,ulong,ushort const *,ushort const *,int *)
0x180004ccb  mov     ebx, eax
0x180004ccd  test    eax, eax
0x180004ccf  jz      loc_180004A83
0x180004cd5  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x180004cdc  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180004ce3  mov     rax, r9
0x180004ce6  dec     r9
0x180004ce9  cmp     byte ptr [r9], 5Ch ; '\'
0x180004ced  jz      short loc_180004CF4
0x180004cef  cmp     r9, rcx
0x180004cf2  ja      short loc_180004CE3
0x180004cf4  xor     ecx, ecx
0x180004cf6  lea     r8, aAddentryinlook_1; "_AddEntryInLookupCache(SubPkg)"
0x180004cfd  cmp     byte ptr [r9], 5Ch ; '\'
0x180004d01  cmovz   r9, rax
0x180004d05  mov     eax, 900h
0x180004d0a  jmp     loc_180004B4C
0x180004d0f  mov     rdi, [r14+178h]
0x180004d16  test    rdi, rdi
0x180004d19  jz      short loc_180004D3B
0x180004d1b  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x180004d1e  mov     rcx, rbx; SourceString
0x180004d21  call    ?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)
0x180004d26  test    eax, eax
0x180004d28  jns     loc_180004DBF
0x180004d2e  mov     rdi, [rdi]
0x180004d31  test    rdi, rdi
0x180004d34  jnz     short loc_180004D1B
0x180004d36  test    rdi, rdi
0x180004d39  jnz     short loc_180004D6F
0x180004d3b  mov     rdi, [r14+180h]
0x180004d42  test    rdi, rdi
0x180004d45  jz      loc_180004C25
0x180004d4b  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x180004d4e  mov     rcx, rbx; void *
0x180004d51  call    ?SubPkgTable_CompareDnsNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareDnsNames(void *,_RTL_BALANCED_NODE *)
0x180004d56  test    eax, eax
0x180004d58  jns     short loc_180004DCE
0x180004d5a  mov     rdi, [rdi]
0x180004d5d  test    rdi, rdi
0x180004d60  jnz     short loc_180004D4B
0x180004d62  test    rdi, rdi
0x180004d65  jz      loc_180004C25
0x180004d6b  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180004d6f  mov     r12, [rdi+250h]
0x180004d76  lea     rbp, [rdi+30h]
0x180004d7a  jmp     loc_1800049DB
0x180004d7f  mov     qword ptr [r8], 0
0x180004d86  jmp     loc_1800049BA
0x180004d8b  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180004d92  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004d97  mov     r9, rax
0x180004d9a  lea     rbp, Class
0x180004da1  mov     [rsp+0A8h+var_78], rbp
0x180004da6  lea     rax, aRegistersubpac; "RegisterSubPackage"
0x180004dad  mov     qword ptr [rsp+0A8h+var_80], rax
0x180004db2  mov     dword ptr [rsp+0A8h+var_88], 1686h
0x180004dba  jmp     loc_180004C66
0x180004dbf  jle     loc_180004D36
0x180004dc5  mov     rdi, [rdi+8]
0x180004dc9  jmp     loc_180004D31
0x180004dce  jle     short loc_180004D62
0x180004dd0  mov     rdi, [rdi+8]
0x180004dd4  jmp     short loc_180004D5D
0x180004dd6  mov     rcx, rsi; SourceSid
0x180004dd9  call    ?FlushIdentityCache@@YAJPEAX@Z; FlushIdentityCache(void *)
0x180004dde  mov     ebx, eax
0x180004de0  test    eax, eax
0x180004de2  jz      loc_180004AAC
0x180004de8  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180004def  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004df4  mov     r9, rax
0x180004df7  lea     rbp, Class
0x180004dfe  lea     rax, aFlushidentityc_0; "FlushIdentityCache"
0x180004e05  mov     [rsp+0A8h+var_78], rbp
0x180004e0a  mov     qword ptr [rsp+0A8h+var_80], rax
0x180004e0f  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180004e16  mov     r8d, ebx
0x180004e19  mov     dword ptr [rsp+0A8h+var_88], 909h
0x180004e21  mov     rdx, rsi
0x180004e24  xor     ecx, ecx
0x180004e26  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180004e2b  jmp     loc_180004B83
0x180004e30  mov     r8, r15; unsigned __int16 **
0x180004e33  xor     edx, edx; int
0x180004e35  mov     rcx, rbp; Src
0x180004e38  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180004e3d  mov     ebx, eax
0x180004e3f  test    eax, eax
0x180004e41  jz      loc_180004AB5
0x180004e47  xor     r10d, r10d
0x180004e4a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180004e51  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180004e58  mov     r8d, eax
0x180004e5b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004e60  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x180004e67  mov     ecx, 16A5h
0x180004e6c  lea     rbp, Class
0x180004e73  jmp     loc_180004AD6
```
