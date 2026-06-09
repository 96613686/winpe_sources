# AllocateUserInfo(ulong,void *,ulong,void * *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_APPLUGIN_SSO_USER_INFO *,_APPLUGIN_PWD_EXPIRY_INFO *,_APPLUGIN_PUBLIC_CACHED_INFO *,ulong,_APPLUGIN_USER_INFO * *)

- ea: `0x18000c730`
- end: `0x18000ce47`
- name: `?AllocateUserInfo@@YAJKPEAXKPEAPEAXPEBG2222PEAU_APPLUGIN_SSO_USER_INFO@@PEAU_APPLUGIN_PWD_EXPIRY_INFO@@PEAU_APPLUGIN_PUBLIC_CACHED_INFO@@KPEAPEAU_APPLUGIN_USER_INFO@@@Z`
- size: `1815`
- prototype: `__int64 __fastcall(int, void *, unsigned int, void **, unsigned __int16 *, unsigned __int16 *Src, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _APPLUGIN_SSO_USER_INFO *, const unsigned __int16 **, struct _APPLUGIN_PUBLIC_CACHED_INFO *, unsigned int, struct _APPLUGIN_USER_INFO **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x18000c730`
- `0x18000ce50`
- `0x18002fd40`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000c857`
- `ntdll!RtlLengthSid` at `0x18000c857`

## string_xrefs

- `0x18000c914`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c96e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c9c1`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c9fe`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ca61`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ca95`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cad9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cb78`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cbb5`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cbe9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cc35`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cc86`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ccd3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cd2b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cd53`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cd80`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000cdb3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000ce06`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c89e`: `DuplicateSID`
- `0x18000cd41`: `DuplicateSID`
- `0x18000cca1`: `Group SIDs in NULL`

## pseudocode

```c
__int64 __fastcall AllocateUserInfo(
        int a1,
        void *a2,
        unsigned int a3,
        void **a4,
        unsigned __int16 *a5,
        unsigned __int16 *Src,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        struct _APPLUGIN_SSO_USER_INFO *a10,
        const unsigned __int16 **a11,
        struct _APPLUGIN_PUBLIC_CACHED_INFO *a12,
        unsigned int a13,
        struct _APPLUGIN_USER_INFO **a14)
{
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v21; // rsi
  void *v22; // rax
  bool v23; // zf
  const char *v24; // r10
  __int64 v25; // r11
  const char *v26; // rdx
  const char *v27; // rax
  int v28; // r8d
  unsigned int v29; // edi
  char v30; // dl
  const char *v31; // r8
  char v32; // dl
  const char *v33; // r8
  const unsigned __int16 *v34; // rcx
  const unsigned __int16 *v35; // rcx
  char v36; // dl
  const char *v37; // r8
  char v38; // dl
  const char *v39; // r8
  const unsigned __int16 *v40; // rcx
  unsigned int v41; // eax
  unsigned int v42; // ecx
  const char *v43; // rax
  const char *v44; // rax
  __int64 v45; // rax
  unsigned int i; // esi
  struct _LSA_SECPKG_FUNCTION_TABLE *v47; // rax
  void *v48; // rax

  if ( !a2 && a1 != 50000 )
  {
    v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v43, 1008, "Invalid Arg(s)", &Class);
    return 3221225485LL;
  }
  v18 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(136);
  v19 = v18;
  if ( v18 )
  {
    *(_DWORD *)v18 = a1;
    *(_QWORD *)(v18 + 16) = 0;
    if ( a2 )
    {
      v21 = RtlLengthSid(a2);
      v22 = (void *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(v21);
      *(_QWORD *)(v19 + 16) = v22;
      if ( !v22 )
      {
        v29 = -1073741801;
        v27 = "";
        do
        {
          v36 = *(v27 - 1);
          v37 = v27--;
        }
        while ( v36 != 92 && v27 > "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" );
        v23 = v36 == 92;
        v24 = "0x%08x %s:%u : %s:%ws";
        v25 = 0;
        v26 = "DuplicateSID";
        if ( v23 )
          v27 = v37;
        v28 = 1021;
        goto LABEL_21;
      }
      memcpy_0(v22, a2, (unsigned int)v21);
    }
    if ( a5 )
    {
      v29 = DuplicateString(a5, 0, (unsigned __int16 **)(v19 + 40));
      if ( v29 )
      {
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "DuplicateString";
        v28 = 1026;
LABEL_21:
        WPPTraceLogA(v25, v24, v29, v27, v28, v26, &Class);
        FreeUserInfo((struct _APPLUGIN_USER_INFO *)v19);
        return v29;
      }
    }
    if ( a3 )
    {
      if ( !a4 )
      {
        v29 = -1073741811;
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "Group SIDs in NULL";
        v28 = 1034;
        goto LABEL_21;
      }
      v45 = ((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(8 * a3);
      *(_QWORD *)(v19 + 32) = v45;
      if ( !v45 )
      {
        v29 = -1073741801;
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v28 = 1041;
        goto LABEL_84;
      }
      *(_DWORD *)(v19 + 24) = a3;
      for ( i = 0; i < a3; ++i )
      {
        v29 = DuplicateSID(a4[i], (void **)(8LL * i + *(_QWORD *)(v19 + 32)));
        if ( v29 )
        {
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "DuplicateSID";
          v28 = 1048;
          goto LABEL_21;
        }
      }
    }
    if ( Src )
    {
      v29 = DuplicateString(Src, 0, (unsigned __int16 **)(v19 + 8));
      if ( v29 )
      {
        v27 = "";
        do
        {
          v30 = *(v27 - 1);
          v31 = v27--;
        }
        while ( v30 != 92 && v27 > "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" );
        v23 = v30 == 92;
        v24 = "0x%08x %s:%u : %s:%ws";
        v25 = 0;
        v26 = "DuplicateString";
        if ( v23 )
          v27 = v31;
        v28 = 1055;
        goto LABEL_21;
      }
    }
    if ( a7 )
    {
      v29 = DuplicateString(a7, 0, (unsigned __int16 **)(v19 + 48));
      if ( v29 )
      {
        v27 = "";
        do
        {
          v32 = *(v27 - 1);
          v33 = v27--;
        }
        while ( v32 != 92 && v27 > "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" );
        v23 = v32 == 92;
        v24 = "0x%08x %s:%u : %s:%ws";
        v25 = 0;
        v26 = "DuplicateString";
        if ( v23 )
          v27 = v33;
        v28 = 1061;
        goto LABEL_21;
      }
    }
    if ( a8 )
    {
      v29 = DuplicateString(a8, 0, (unsigned __int16 **)(v19 + 56));
      if ( v29 )
      {
        v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
        v26 = "DuplicateString";
        v28 = 1067;
        goto LABEL_21;
      }
    }
    if ( a9 )
    {
      v29 = DuplicateString(a9, 0, (unsigned __int16 **)(v19 + 64));
      if ( v29 )
      {
        v27 = "";
        do
        {
          v38 = *(v27 - 1);
          v39 = v27--;
        }
        while ( v38 != 92 && v27 > "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" );
        v23 = v38 == 92;
        v24 = "0x%08x %s:%u : %s:%ws";
        v25 = 0;
        v26 = "DuplicateString";
        if ( v23 )
          v27 = v39;
        v28 = 1073;
        goto LABEL_21;
      }
    }
    if ( a10 )
    {
      v34 = (const unsigned __int16 *)*((_QWORD *)a10 + 2);
      if ( v34 )
      {
        v29 = DuplicateString(v34, 0, (unsigned __int16 **)(v19 + 88));
        if ( v29 )
        {
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "DuplicateString";
          v28 = 1081;
          goto LABEL_21;
        }
      }
      if ( *(_QWORD *)a10 )
      {
        v29 = DuplicateString(*(const unsigned __int16 **)a10, 0, (unsigned __int16 **)(v19 + 72));
        if ( v29 )
        {
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "DuplicateString";
          v28 = 1087;
          goto LABEL_21;
        }
      }
      v35 = (const unsigned __int16 *)*((_QWORD *)a10 + 1);
      if ( v35 )
      {
        v29 = DuplicateString(v35, 0, (unsigned __int16 **)(v19 + 80));
        if ( v29 )
        {
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
          v26 = "DuplicateString";
          v28 = 1093;
          goto LABEL_21;
        }
      }
    }
    if ( !a11 )
      goto LABEL_12;
    v40 = *a11;
    if ( !*a11 || !*v40 )
      goto LABEL_12;
    v29 = DuplicateString(v40, 0, (unsigned __int16 **)(v19 + 96));
    if ( v29 )
    {
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "DuplicateString";
      v28 = 1114;
      goto LABEL_21;
    }
    v41 = *((_DWORD *)a11 + 2);
    *(_DWORD *)(v19 + 104) = v41;
    v42 = *((_DWORD *)a11 + 3);
    *(_DWORD *)(v19 + 108) = v42;
    if ( !__PAIR64__(v42, v41) )
LABEL_12:
      *(union _LARGE_INTEGER *)(v19 + 104) = g_TimeForever;
    if ( !a12 )
    {
      *(_DWORD *)(v19 + 112) = 0;
LABEL_15:
      *(_DWORD *)(v19 + 128) = a13;
      *a14 = (struct _APPLUGIN_USER_INFO *)v19;
      return 0;
    }
    if ( *(_DWORD *)a12 != 6 )
    {
      v29 = -1073741637;
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "Non FIDO keytypes currently not supported";
      v28 = 1137;
      goto LABEL_21;
    }
    if ( !*((_QWORD *)a12 + 1) )
    {
      v29 = -1073741637;
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      v26 = "Null Arg";
      v28 = 1143;
      goto LABEL_21;
    }
    v47 = g_pLsaFunctionTable;
    *(_DWORD *)(v19 + 112) = 6;
    v48 = (void *)((__int64 (__fastcall *)(_QWORD))v47->AllocateLsaHeap)(**((unsigned int **)a12 + 1));
    *(_QWORD *)(v19 + 120) = v48;
    if ( v48 )
    {
      memcpy_0(v48, *((const void **)a12 + 1), **((unsigned int **)a12 + 1));
      goto LABEL_15;
    }
    v29 = -1073741801;
    v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    v28 = 1151;
LABEL_84:
    v26 = "AllocateLsaHeap";
    goto LABEL_21;
  }
  v44 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v44, 1015, "AllocateLsaHeap", &Class);
  return 3221225495LL;
}

```

## disassembly

```asm
0x18000c730  mov     [rsp+arg_10], rbp
0x18000c735  push    rsi
0x18000c736  push    rdi
0x18000c737  push    r14
0x18000c739  sub     rsp, 40h
0x18000c73d  mov     r14, r9
0x18000c740  mov     ebp, r8d
0x18000c743  mov     rdi, rdx
0x18000c746  mov     esi, ecx
0x18000c748  test    rdx, rdx
0x18000c74b  jz      loc_18000CBDD
0x18000c751  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c758  mov     ecx, 88h
0x18000c75d  mov     [rsp+58h+arg_0], rbx
0x18000c762  mov     rax, [rax+28h]
0x18000c766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c76b  mov     rbx, rax
0x18000c76e  test    rax, rax
0x18000c771  jz      loc_18000CC35
0x18000c777  mov     [rsp+58h+arg_8], r15
0x18000c77c  xor     r15d, r15d
0x18000c77f  mov     [rax], esi
0x18000c781  mov     [rax+10h], r15
0x18000c785  test    rdi, rdi
0x18000c788  jnz     loc_18000C854
0x18000c78e  mov     rcx, [rsp+58h+arg_20]; Src
0x18000c796  test    rcx, rcx
0x18000c799  jnz     loc_18000C9AC
0x18000c79f  test    ebp, ebp
0x18000c7a1  jnz     loc_18000CC81
0x18000c7a7  mov     rcx, [rsp+58h+Src]; Src
0x18000c7af  test    rcx, rcx
0x18000c7b2  jnz     loc_18000C8F8
0x18000c7b8  mov     rcx, [rsp+58h+arg_30]; Src
0x18000c7c0  test    rcx, rcx
0x18000c7c3  jnz     loc_18000C952
0x18000c7c9  mov     rcx, [rsp+58h+arg_38]; Src
0x18000c7d1  test    rcx, rcx
0x18000c7d4  jnz     loc_18000C9E9
0x18000c7da  mov     rcx, [rsp+58h+arg_40]; Src
0x18000c7e2  test    rcx, rcx
0x18000c7e5  jnz     loc_18000CABD
0x18000c7eb  mov     rsi, [rsp+58h+arg_48]
0x18000c7f3  test    rsi, rsi
0x18000c7f6  jnz     loc_18000CA26
0x18000c7fc  mov     rsi, [rsp+58h+arg_50]
0x18000c804  test    rsi, rsi
0x18000c807  jnz     loc_18000CB17
0x18000c80d  mov     eax, dword ptr cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18000c813  mov     [rbx+68h], eax
0x18000c816  mov     eax, dword ptr cs:?g_TimeForever@@3T_LARGE_INTEGER@@A+4; _LARGE_INTEGER g_TimeForever
0x18000c81c  mov     [rbx+6Ch], eax
0x18000c81f  mov     rdi, [rsp+58h+arg_58]
0x18000c827  test    rdi, rdi
0x18000c82a  jnz     loc_18000CD7B
0x18000c830  mov     [rbx+70h], r15d
0x18000c834  mov     eax, [rsp+58h+arg_60]
0x18000c83b  mov     [rbx+80h], eax
0x18000c841  mov     rax, [rsp+58h+arg_68]
0x18000c849  mov     [rax], rbx
0x18000c84c  mov     eax, r15d
0x18000c84f  jmp     loc_18000C8E0
0x18000c854  mov     rcx, rdi; Sid
0x18000c857  call    cs:__imp_RtlLengthSid
0x18000c85d  mov     rcx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c864  mov     esi, eax
0x18000c866  mov     rax, [rcx+28h]
0x18000c86a  mov     ecx, esi
0x18000c86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c871  mov     [rbx+10h], rax
0x18000c875  test    rax, rax
0x18000c878  jz      loc_18000CA89
0x18000c87e  mov     r8d, esi; Size
0x18000c881  mov     rdx, rdi; Src
0x18000c884  mov     rcx, rax; void *
0x18000c887  call    memcpy_0
0x18000c88c  jmp     loc_18000C78E
0x18000c891  cmp     dl, 5Ch ; '\'
0x18000c894  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c89b  mov     r11, r15
0x18000c89e  lea     rdx, aDuplicatesid; "DuplicateSID"
0x18000c8a5  cmovz   rax, r8
0x18000c8a9  mov     r8d, 3FDh
0x18000c8af  lea     rcx, Class
0x18000c8b6  mov     [rsp+58h+var_28], rcx
0x18000c8bb  mov     r9, rax
0x18000c8be  mov     [rsp+58h+var_30], rdx
0x18000c8c3  mov     rcx, r11
0x18000c8c6  mov     [rsp+58h+var_38], r8d
0x18000c8cb  mov     rdx, r10
0x18000c8ce  mov     r8d, edi
0x18000c8d1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000c8d6  mov     rcx, rbx; struct _APPLUGIN_USER_INFO *
0x18000c8d9  call    ?FreeUserInfo@@YAXPEAU_APPLUGIN_USER_INFO@@@Z; FreeUserInfo(_APPLUGIN_USER_INFO *)
0x18000c8de  mov     eax, edi
0x18000c8e0  mov     r15, [rsp+58h+arg_8]
0x18000c8e5  mov     rbx, [rsp+58h+arg_0]
0x18000c8ea  mov     rbp, [rsp+58h+arg_10]
0x18000c8ef  add     rsp, 40h
0x18000c8f3  pop     r14
0x18000c8f5  pop     rdi
0x18000c8f6  pop     rsi
0x18000c8f7  retn
0x18000c8f8  lea     r8, [rbx+8]; unsigned __int16 **
0x18000c8fc  xor     edx, edx; int
0x18000c8fe  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000c903  mov     edi, eax
0x18000c905  test    eax, eax
0x18000c907  jz      loc_18000C7B8
0x18000c90d  lea     rax, aOnecoreDsExtCl_16+26h; ""
0x18000c914  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c91b  movzx   edx, byte ptr [rax-1]
0x18000c91f  mov     r8, rax
0x18000c922  dec     rax
0x18000c925  cmp     dl, 5Ch ; '\'
0x18000c928  jz      short loc_18000C92F
0x18000c92a  cmp     rax, rcx
0x18000c92d  ja      short loc_18000C91B
0x18000c92f  cmp     dl, 5Ch ; '\'
0x18000c932  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c939  mov     r11, r15
0x18000c93c  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000c943  cmovz   rax, r8
0x18000c947  mov     r8d, 41Fh
0x18000c94d  jmp     loc_18000C8AF
0x18000c952  lea     r8, [rbx+30h]; unsigned __int16 **
0x18000c956  xor     edx, edx; int
0x18000c958  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000c95d  mov     edi, eax
0x18000c95f  test    eax, eax
0x18000c961  jz      loc_18000C7C9
0x18000c967  lea     rax, aOnecoreDsExtCl_16+26h; ""
0x18000c96e  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c975  movzx   edx, byte ptr [rax-1]
0x18000c979  mov     r8, rax
0x18000c97c  dec     rax
0x18000c97f  cmp     dl, 5Ch ; '\'
0x18000c982  jz      short loc_18000C989
0x18000c984  cmp     rax, rcx
0x18000c987  ja      short loc_18000C975
0x18000c989  cmp     dl, 5Ch ; '\'
0x18000c98c  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c993  mov     r11, r15
0x18000c996  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000c99d  cmovz   rax, r8
0x18000c9a1  mov     r8d, 425h
0x18000c9a7  jmp     loc_18000C8AF
0x18000c9ac  lea     r8, [rbx+28h]; unsigned __int16 **
0x18000c9b0  xor     edx, edx; int
0x18000c9b2  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000c9b7  mov     edi, eax
0x18000c9b9  test    eax, eax
0x18000c9bb  jz      loc_18000C79F
0x18000c9c1  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c9c8  mov     r11, r15
0x18000c9cb  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c9d2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c9d7  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000c9de  mov     r8d, 402h
0x18000c9e4  jmp     loc_18000C8AF
0x18000c9e9  lea     r8, [rbx+38h]; unsigned __int16 **
0x18000c9ed  xor     edx, edx; int
0x18000c9ef  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000c9f4  mov     edi, eax
0x18000c9f6  test    eax, eax
0x18000c9f8  jz      loc_18000C7DA
0x18000c9fe  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ca05  mov     r11, r15
0x18000ca08  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ca0f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ca14  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000ca1b  mov     r8d, 42Bh
0x18000ca21  jmp     loc_18000C8AF
0x18000ca26  mov     rcx, [rsi+10h]; Src
0x18000ca2a  test    rcx, rcx
0x18000ca2d  jnz     loc_18000CBA0
0x18000ca33  mov     rcx, [rsi]; Src
0x18000ca36  test    rcx, rcx
0x18000ca39  jnz     loc_18000CB63
0x18000ca3f  mov     rcx, [rsi+8]; Src
0x18000ca43  test    rcx, rcx
0x18000ca46  jz      loc_18000C7FC
0x18000ca4c  lea     r8, [rbx+50h]; unsigned __int16 **
0x18000ca50  xor     edx, edx; int
0x18000ca52  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000ca57  mov     edi, eax
0x18000ca59  test    eax, eax
0x18000ca5b  jz      loc_18000C7FC
0x18000ca61  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ca68  mov     r11, r15
0x18000ca6b  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ca72  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ca77  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000ca7e  mov     r8d, 445h
0x18000ca84  jmp     loc_18000C8AF
0x18000ca89  mov     edi, 0C0000017h
0x18000ca8e  lea     rax, aOnecoreDsExtCl_16+26h; ""
0x18000ca95  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000ca9c  nop     dword ptr [rax+00h]
0x18000caa0  movzx   edx, byte ptr [rax-1]
0x18000caa4  mov     r8, rax
0x18000caa7  dec     rax
0x18000caaa  cmp     dl, 5Ch ; '\'
0x18000caad  jz      loc_18000C891
0x18000cab3  cmp     rax, rcx
0x18000cab6  ja      short loc_18000CAA0
0x18000cab8  jmp     loc_18000C891
0x18000cabd  lea     r8, [rbx+40h]; unsigned __int16 **
0x18000cac1  xor     edx, edx; int
0x18000cac3  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000cac8  mov     edi, eax
0x18000caca  test    eax, eax
0x18000cacc  jz      loc_18000C7EB
0x18000cad2  lea     rax, aOnecoreDsExtCl_16+26h; ""
0x18000cad9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000cae0  movzx   edx, byte ptr [rax-1]
0x18000cae4  mov     r8, rax
0x18000cae7  dec     rax
0x18000caea  cmp     dl, 5Ch ; '\'
0x18000caed  jz      short loc_18000CAF4
0x18000caef  cmp     rax, rcx
0x18000caf2  ja      short loc_18000CAE0
0x18000caf4  cmp     dl, 5Ch ; '\'
0x18000caf7  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000cafe  mov     r11, r15
0x18000cb01  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000cb08  cmovz   rax, r8
0x18000cb0c  mov     r8d, 431h
0x18000cb12  jmp     loc_18000C8AF
0x18000cb17  mov     rcx, [rsi]; Src
0x18000cb1a  test    rcx, rcx
0x18000cb1d  jz      loc_18000C80D
0x18000cb23  cmp     r15w, [rcx]
0x18000cb27  jz      loc_18000C80D
0x18000cb2d  lea     r8, [rbx+60h]; unsigned __int16 **
0x18000cb31  xor     edx, edx; int
0x18000cb33  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000cb38  mov     edi, eax
0x18000cb3a  test    eax, eax
0x18000cb3c  jnz     loc_18000CD53
0x18000cb42  mov     eax, [rsi+8]
0x18000cb45  mov     [rbx+68h], eax
0x18000cb48  mov     ecx, [rsi+0Ch]
0x18000cb4b  mov     [rbx+6Ch], ecx
0x18000cb4e  test    eax, eax
0x18000cb50  jnz     loc_18000C81F
0x18000cb56  test    ecx, ecx
0x18000cb58  jnz     loc_18000C81F
0x18000cb5e  jmp     loc_18000C80D
0x18000cb63  lea     r8, [rbx+48h]; unsigned __int16 **
0x18000cb67  xor     edx, edx; int
0x18000cb69  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000cb6e  mov     edi, eax
0x18000cb70  test    eax, eax
0x18000cb72  jz      loc_18000CA3F
0x18000cb78  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000cb7f  mov     r11, r15
0x18000cb82  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000cb89  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cb8e  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000cb95  mov     r8d, 43Fh
0x18000cb9b  jmp     loc_18000C8AF
0x18000cba0  lea     r8, [rbx+58h]; unsigned __int16 **
0x18000cba4  xor     edx, edx; int
0x18000cba6  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000cbab  mov     edi, eax
0x18000cbad  test    eax, eax
0x18000cbaf  jz      loc_18000CA33
0x18000cbb5  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000cbbc  mov     r11, r15
0x18000cbbf  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000cbc6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cbcb  lea     rdx, aDuplicatestrin_1; "DuplicateString"
0x18000cbd2  mov     r8d, 439h
0x18000cbd8  jmp     loc_18000C8AF
0x18000cbdd  cmp     esi, 0C350h
0x18000cbe3  jz      loc_18000C751
0x18000cbe9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000cbf0  mov     edi, 0C000000Dh
0x18000cbf5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cbfa  mov     r9, rax
0x18000cbfd  lea     rcx, Class
0x18000cc04  mov     [rsp+58h+var_28], rcx
0x18000cc09  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000cc10  mov     [rsp+58h+var_30], rax
0x18000cc15  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000cc1c  mov     r8d, edi
0x18000cc1f  mov     [rsp+58h+var_38], 3F0h
0x18000cc27  xor     ecx, ecx
0x18000cc29  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000cc2e  mov     eax, edi
0x18000cc30  jmp     loc_18000C8EA
0x18000cc35  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000cc3c  mov     edi, 0C0000017h
0x18000cc41  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cc46  lea     rcx, Class
0x18000cc4d  mov     r9, rax
0x18000cc50  mov     [rsp+58h+var_28], rcx
0x18000cc55  lea     rdx, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000cc5c  mov     [rsp+58h+var_30], rdx
  ... truncated ...
```
