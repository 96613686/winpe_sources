# SanitizeSAMName(bool,_tagCallerContext *,ushort *,_APPLUGIN_USER_INFO *,_UNICODE_STRING *)

- ea: `0x180056684`
- end: `0x180056cf8`
- name: `?SanitizeSAMName@@YAJ_NPEAU_tagCallerContext@@PEAGPEAU_APPLUGIN_USER_INFO@@PEAU_UNICODE_STRING@@@Z`
- size: `1652`
- prototype: `int(bool, struct _tagCallerContext *, unsigned __int16 *, struct _APPLUGIN_USER_INFO *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800307d0`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180028318`
- `0x18002b260`
- `0x1800521bc`
- `0x180056684`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005679d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005679d`
- `ntdll!RtlInitUnicodeString` at `0x1800567ca`
- `ntdll!RtlInitUnicodeString` at `0x180056874`
- `ntdll!RtlInitUnicodeString` at `0x180056ac6`
- `ntdll!RtlInitUnicodeString` at `0x180056b5c`
- `ntdll!RtlInitUnicodeString` at `0x180056bf7`
- `ntdll!RtlInitUnicodeString` at `0x1800567ca`
- `ntdll!RtlInitUnicodeString` at `0x180056874`
- `ntdll!RtlInitUnicodeString` at `0x180056ac6`
- `ntdll!RtlInitUnicodeString` at `0x180056b5c`
- `ntdll!RtlInitUnicodeString` at `0x180056bf7`

## string_xrefs

- `0x1800566ed`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005672b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005680d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800568b8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005695e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800569b2`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800569fa`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056a66`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056b02`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056b9b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056c36`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056c6d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005678a`: `Software\Policies\Microsoft\AzureADAccount`

## pseudocode

```c
__int64 __fastcall SanitizeSAMName(
        char a1,
        struct _tagCallerContext *a2,
        unsigned __int16 *a3,
        struct _APPLUGIN_USER_INFO *a4,
        struct _UNICODE_STRING *a5)
{
  const WCHAR *v6; // rsi
  struct _tagCallerContext *v7; // rbx
  unsigned __int16 *v8; // r13
  const WCHAR *v9; // rcx
  unsigned int v10; // ebx
  const char *v11; // r9
  const char *v12; // r9
  __int64 v13; // r8
  char v14; // r12
  const WCHAR *v15; // rdx
  int v16; // eax
  const WCHAR *v17; // rdi
  const WCHAR *v18; // rdx
  int v19; // eax
  const WCHAR *v20; // rdi
  __int64 v21; // rdx
  const WCHAR **v22; // r15
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // ecx
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  const WCHAR *v29; // rax
  const WCHAR *v30; // r9
  const char *v31; // r9
  struct _UNICODE_STRING v32; // xmm0
  void *v33; // r14
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int (*pdwType)(void *, struct _UNICODE_STRING *); // [rsp+20h] [rbp-50h]
  int (*pdwTypea)(void *, struct _UNICODE_STRING *); // [rsp+20h] [rbp-50h]
  const char *pvData; // [rsp+28h] [rbp-48h]
  LPDWORD pcbData; // [rsp+30h] [rbp-40h]
  DWORD v42; // [rsp+40h] [rbp-30h] BYREF
  int v43; // [rsp+44h] [rbp-2Ch] BYREF
  struct _UNICODE_STRING v44; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v46; // [rsp+B0h] [rbp+40h] BYREF
  void *v47; // [rsp+B8h] [rbp+48h]

  v47 = a2;
  v43 = 0;
  v42 = 0;
  v6 = a3;
  v7 = a2;
  v8 = 0;
  *a5 = 0;
  DestinationString = 0;
  v44 = 0;
  if ( a1 )
  {
    v9 = (const WCHAR *)*((_QWORD *)a4 + 9);
    if ( v9 )
    {
      v10 = DuplicateUnicodeString3(v9, &v44);
      if ( v10 )
      {
        v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v11, 957, "DuplicateUnicodeString3", &Class);
      }
LABEL_52:
      if ( (v10 & 0x80000000) != 0 )
        goto LABEL_77;
      goto LABEL_53;
    }
    v10 = -1073741595;
    if ( !a3 )
      v6 = &Class;
    pcbData = (LPDWORD)v6;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    pvData = "EnterpriseUser should have its NetBios name set";
    LODWORD(pdwType) = 963;
    goto LABEL_8;
  }
  v42 = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\AzureADAccount",
         L"RequireAsciiSamName",
         0x18u,
         0,
         &v43,
         &v42)
    || (v14 = 1, v43 != 1) )
  {
    v14 = 0;
  }
  v15 = (const WCHAR *)*((_QWORD *)a4 + 9);
  if ( v15 )
  {
    RtlInitUnicodeString(&DestinationString, v15);
    v16 = CheckAndSanitizeSAMName(0, &DestinationString, 0x14u, v7, pdwType, &v44);
    v10 = v16;
    if ( v16 >= 0 )
      goto LABEL_53;
    if ( v16 != -1073741725 && v16 != -1073741471 )
    {
      v17 = &Class;
      if ( *((_QWORD *)a4 + 5) )
        v17 = (const WCHAR *)*((_QWORD *)a4 + 5);
      pcbData = (LPDWORD)v17;
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      pvData = "CheckAndSanitizeSAMName";
      LODWORD(pdwType) = 1002;
      goto LABEL_8;
    }
    if ( v44.Buffer )
    {
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      v44 = 0;
    }
    v7 = (struct _tagCallerContext *)v47;
  }
  v18 = (const WCHAR *)*((_QWORD *)a4 + 5);
  if ( v18 )
  {
    RtlInitUnicodeString(&DestinationString, v18);
    v19 = CheckAndSanitizeSAMName(v14, &DestinationString, 0x14u, v7, pdwType, &v44);
    v10 = v19;
    if ( v19 >= 0 )
      goto LABEL_53;
    if ( v19 != -1073741725 && v19 != -1073741471 )
    {
      v20 = &Class;
      if ( *((_QWORD *)a4 + 5) )
        v20 = (const WCHAR *)*((_QWORD *)a4 + 5);
      pcbData = (LPDWORD)v20;
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      pvData = "CheckAndSanitizeSAMName";
      LODWORD(pdwType) = 1029;
      goto LABEL_8;
    }
    if ( v44.Buffer )
    {
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
      v44 = 0;
    }
  }
  v21 = *((_QWORD *)a4 + 6);
  v22 = (const WCHAR **)((char *)a4 + 56);
  v23 = -1;
  if ( v21 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(v21 + 2 * v24) );
  }
  else
  {
    if ( !*v22 )
    {
      v33 = v47;
      goto LABEL_61;
    }
    LODWORD(v24) = 0;
  }
  if ( *v22 )
  {
    do
      ++v23;
    while ( (*v22)[v23] );
    v25 = v24 + v23;
    if ( v25 < (unsigned int)v24 )
    {
      v10 = -1073741675;
      v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(pdwType) = 1049;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v27, v26, pdwType, "RtlDWordAdd", &Class);
      goto LABEL_77;
    }
  }
  else
  {
    v25 = v24;
  }
  if ( v25 + 1 < v25 )
  {
    v10 = -1073741675;
    pcbData = (LPDWORD)&Class;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    pvData = "RtlDWordAdd";
    LODWORD(pdwType) = 1053;
    goto LABEL_76;
  }
  v46 = v25 + 1;
  v10 = RtlULongLongToULong(2LL * (v25 + 1), &v46);
  if ( v10 )
  {
    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(pdwType) = 1056;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v28, pdwType, "RtlDWordAdd", &Class);
    goto LABEL_52;
  }
  v8 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v46);
  if ( !v8 )
  {
    v10 = -1073741801;
    pcbData = (LPDWORD)&Class;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    pvData = "AllocateLsaHeap";
    LODWORD(pdwType) = 1062;
LABEL_8:
    v13 = v10;
LABEL_76:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v12, pdwType, pvData, pcbData);
    goto LABEL_77;
  }
  v29 = &Class;
  if ( *v22 )
    v29 = *v22;
  v30 = &Class;
  if ( *((_QWORD *)a4 + 6) )
    v30 = (const WCHAR *)*((_QWORD *)a4 + 6);
  v10 = RtlStringCchPrintfW(v8, (unsigned __int64)v46 >> 1, L"%ws%ws", v30, v29);
  if ( v10 )
  {
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(pdwTypea) = 1071;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v31, pdwTypea, "RtlStringCchPrintfW", &Class);
    goto LABEL_52;
  }
  RtlInitUnicodeString(&DestinationString, v8);
  v33 = v47;
  v34 = CheckAndSanitizeSAMName(v14, &DestinationString, 0x14u, v47, pdwTypea, &v44);
  v10 = v34;
  if ( v34 >= 0 )
  {
LABEL_53:
    v32 = v44;
    v44 = 0;
    *a5 = v32;
    goto LABEL_77;
  }
  if ( v34 != -1073741725 && v34 != -1073741471 )
  {
    pcbData = (LPDWORD)v8;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    pvData = "CheckAndSanitizeSAMName";
    LODWORD(pdwType) = 1088;
    goto LABEL_8;
  }
  if ( v44.Buffer )
  {
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    v44 = 0;
  }
LABEL_61:
  RtlInitUnicodeString(&DestinationString, v6);
  v35 = CheckAndSanitizeSAMName(v14, &DestinationString, 5u, v33, pdwType, &v44);
  v10 = v35;
  if ( v35 >= 0 )
    goto LABEL_53;
  if ( v35 != -1073741725 && v35 != -1073741471 )
  {
    if ( !v6 )
      v6 = &Class;
    pcbData = (LPDWORD)v6;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    pvData = "CheckAndSanitizeSAMName";
    LODWORD(pdwType) = 1113;
    goto LABEL_8;
  }
  if ( v44.Buffer )
  {
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    v44 = 0;
  }
  RtlInitUnicodeString(&DestinationString, L"*");
  v36 = CheckAndSanitizeSAMName(v14, &DestinationString, 5u, v33, pdwType, &v44);
  v10 = v36;
  if ( v36 >= 0 )
    goto LABEL_53;
  if ( v36 != -1073741725 && v36 != -1073741471 )
  {
    if ( !v6 )
      v6 = &Class;
    pcbData = (LPDWORD)v6;
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    pvData = "CheckAndSanitizeSAMName";
    LODWORD(pdwType) = 1138;
    goto LABEL_8;
  }
LABEL_77:
  if ( v44.Buffer )
  {
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    v44 = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  return v10;
}

```

## disassembly

```asm
0x180056684  mov     [rsp-38h+arg_10], rbx
0x180056689  mov     [rsp-38h+arg_8], rdx
0x18005668e  push    rbp
0x18005668f  push    rsi
0x180056690  push    rdi
0x180056691  push    r12
0x180056693  push    r13
0x180056695  push    r14
0x180056697  push    r15
0x180056699  mov     rbp, rsp
0x18005669c  sub     rsp, 70h
0x1800566a0  mov     rax, [rbp+arg_20]
0x1800566a4  xor     r15d, r15d
0x1800566a7  mov     [rbp+var_2C], r15d
0x1800566ab  xorps   xmm0, xmm0
0x1800566ae  mov     [rbp+var_30], r15d
0x1800566b2  mov     r14, r9
0x1800566b5  mov     rsi, r8
0x1800566b8  mov     rbx, rdx
0x1800566bb  mov     r13d, r15d
0x1800566be  movups  xmmword ptr [rax], xmm0
0x1800566c1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800566c5  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x1800566c9  test    cl, cl
0x1800566cb  jz      loc_180056764
0x1800566d1  mov     rcx, [r9+48h]; SourceString
0x1800566d5  test    rcx, rcx
0x1800566d8  jz      short loc_180056721
0x1800566da  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x1800566de  call    ?DuplicateUnicodeString3@@YAJPEBGPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeString3(ushort const *,_UNICODE_STRING *)
0x1800566e3  mov     ebx, eax
0x1800566e5  test    eax, eax
0x1800566e7  jz      loc_180056A9F
0x1800566ed  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800566f4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800566f9  mov     r9, rax
0x1800566fc  lea     rdi, Class
0x180056703  mov     [rsp+70h+pcbData], rdi
0x180056708  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x18005670f  mov     [rsp+70h+pvData], rax
0x180056714  mov     dword ptr [rsp+70h+pdwType], 3BDh
0x18005671c  jmp     loc_180056A8E
0x180056721  test    rsi, rsi
0x180056724  lea     rdi, Class
0x18005672b  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056732  mov     ebx, 0C00000E5h
0x180056737  cmovz   rsi, rdi
0x18005673b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056740  mov     [rsp+70h+pcbData], rsi
0x180056745  mov     r9, rax
0x180056748  lea     rax, aEnterpriseuser; "EnterpriseUser should have its NetBios "...
0x18005674f  mov     [rsp+70h+pvData], rax
0x180056754  mov     dword ptr [rsp+70h+pdwType], 3C3h
0x18005675c  mov     r8d, ebx
0x18005675f  jmp     loc_180056C98
0x180056764  lea     rax, [rbp+var_30]
0x180056768  mov     [rbp+var_30], 4
0x18005676f  mov     [rsp+70h+pcbData], rax; pcbData
0x180056774  lea     r8, aRequireasciisa; "RequireAsciiSamName"
0x18005677b  lea     rax, [rbp+var_2C]
0x18005677f  mov     r9d, 18h; dwFlags
0x180056785  mov     [rsp+70h+pvData], rax; pvData
0x18005678a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\AzureADA"...
0x180056791  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180056798  mov     [rsp+70h+pdwType], r15; int (*)(void *, struct _UNICODE_STRING *)
0x18005679d  call    cs:__imp_RegGetValueW
0x1800567a3  test    eax, eax
0x1800567a5  jnz     short loc_1800567B1
0x1800567a7  lea     r12d, [rax+1]
0x1800567ab  cmp     [rbp+var_2C], r12d
0x1800567af  jz      short loc_1800567B4
0x1800567b1  mov     r12b, r15b
0x1800567b4  mov     rdx, [r14+48h]; SourceString
0x1800567b8  mov     edi, 0C0000161h
0x1800567bd  test    rdx, rdx
0x1800567c0  jz      loc_180056863
0x1800567c6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800567ca  call    cs:__imp_RtlInitUnicodeString
0x1800567d0  lea     rax, [rbp+var_28]
0x1800567d4  mov     r9, rbx; void *
0x1800567d7  mov     r8d, 14h; unsigned int
0x1800567dd  mov     [rsp+70h+pvData], rax; struct _UNICODE_STRING *
0x1800567e2  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1800567e6  xor     ecx, ecx; bool
0x1800567e8  call    ?CheckAndSanitizeSAMName@@YAJ_NPEAU_UNICODE_STRING@@KPEAXP6AH21@Z1@Z; CheckAndSanitizeSAMName(bool,_UNICODE_STRING *,ulong,void *,int (*)(void *,_UNICODE_STRING *),_UNICODE_STRING *)
0x1800567ed  mov     ebx, eax
0x1800567ef  test    eax, eax
0x1800567f1  jns     loc_180056AA7
0x1800567f7  cmp     eax, 0C0000063h
0x1800567fc  jz      short loc_18005683F
0x1800567fe  cmp     eax, edi
0x180056800  jz      short loc_18005683F
0x180056802  cmp     [r14+28h], r15
0x180056806  lea     rdi, Class
0x18005680d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056814  cmovnz  rdi, [r14+28h]
0x180056819  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005681e  mov     [rsp+70h+pcbData], rdi
0x180056823  mov     r9, rax
0x180056826  lea     rax, aCheckandsaniti; "CheckAndSanitizeSAMName"
0x18005682d  mov     [rsp+70h+pvData], rax
0x180056832  mov     dword ptr [rsp+70h+pdwType], 3EAh
0x18005683a  jmp     loc_18005675C
0x18005683f  mov     rcx, [rbp+var_28.Buffer]
0x180056843  test    rcx, rcx
0x180056846  jz      short loc_18005685F
0x180056848  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005684f  mov     rax, [rax+30h]
0x180056853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056858  xorps   xmm0, xmm0
0x18005685b  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x18005685f  mov     rbx, [rbp+arg_8]
0x180056863  mov     rdx, [r14+28h]; SourceString
0x180056867  test    rdx, rdx
0x18005686a  jz      loc_18005690A
0x180056870  lea     rcx, [rbp+DestinationString]; DestinationString
0x180056874  call    cs:__imp_RtlInitUnicodeString
0x18005687a  lea     rax, [rbp+var_28]
0x18005687e  mov     r9, rbx; void *
0x180056881  mov     r8d, 14h; unsigned int
0x180056887  mov     [rsp+70h+pvData], rax; struct _UNICODE_STRING *
0x18005688c  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180056890  mov     cl, r12b; bool
0x180056893  call    ?CheckAndSanitizeSAMName@@YAJ_NPEAU_UNICODE_STRING@@KPEAXP6AH21@Z1@Z; CheckAndSanitizeSAMName(bool,_UNICODE_STRING *,ulong,void *,int (*)(void *,_UNICODE_STRING *),_UNICODE_STRING *)
0x180056898  mov     ebx, eax
0x18005689a  test    eax, eax
0x18005689c  jns     loc_180056AA7
0x1800568a2  cmp     eax, 0C0000063h
0x1800568a7  jz      short loc_1800568EA
0x1800568a9  cmp     eax, edi
0x1800568ab  jz      short loc_1800568EA
0x1800568ad  cmp     [r14+28h], r15
0x1800568b1  lea     rdi, Class
0x1800568b8  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800568bf  cmovnz  rdi, [r14+28h]
0x1800568c4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800568c9  mov     [rsp+70h+pcbData], rdi
0x1800568ce  mov     r9, rax
0x1800568d1  lea     rax, aCheckandsaniti; "CheckAndSanitizeSAMName"
0x1800568d8  mov     [rsp+70h+pvData], rax
0x1800568dd  mov     dword ptr [rsp+70h+pdwType], 405h
0x1800568e5  jmp     loc_18005675C
0x1800568ea  mov     rcx, [rbp+var_28.Buffer]
0x1800568ee  test    rcx, rcx
0x1800568f1  jz      short loc_18005690A
0x1800568f3  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800568fa  mov     rax, [rax+30h]
0x1800568fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056903  xorps   xmm0, xmm0
0x180056906  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x18005690a  mov     rdx, [r14+30h]
0x18005690e  lea     r15, [r14+38h]
0x180056912  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180056916  lea     rdi, Class
0x18005691d  xor     r11d, r11d
0x180056920  test    rdx, rdx
0x180056923  jnz     short loc_180056933
0x180056925  cmp     [r15], r11
0x180056928  jz      loc_180056B51
0x18005692e  mov     eax, r11d
0x180056931  jmp     short loc_180056940
0x180056933  mov     rax, rcx
0x180056936  inc     rax
0x180056939  cmp     [rdx+rax*2], r11w
0x18005693e  jnz     short loc_180056936
0x180056940  mov     rdx, [r15]
0x180056943  test    rdx, rdx
0x180056946  jz      short loc_18005698E
0x180056948  inc     rcx
0x18005694b  cmp     [rdx+rcx*2], r11w
0x180056950  jnz     short loc_180056948
0x180056952  add     ecx, eax
0x180056954  cmp     ecx, eax
0x180056956  jnb     short loc_180056990
0x180056958  mov     r8d, 0C0000095h
0x18005695e  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056965  mov     ebx, r8d
0x180056968  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005696d  mov     [rsp+70h+pcbData], rdi
0x180056972  mov     r9, rax
0x180056975  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18005697c  mov     [rsp+70h+pvData], rax
0x180056981  mov     dword ptr [rsp+70h+pdwType], 419h
0x180056989  jmp     loc_180056C98
0x18005698e  mov     ecx, eax
0x180056990  lea     eax, [rcx+1]
0x180056993  cmp     eax, ecx
0x180056995  jb      loc_180056C67
0x18005699b  mov     ecx, eax
0x18005699d  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800569a1  add     rcx, rcx; unsigned __int64
0x1800569a4  mov     [rbp+arg_0], eax
0x1800569a7  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x1800569ac  mov     ebx, eax
0x1800569ae  test    eax, eax
0x1800569b0  jz      short loc_1800569DF
0x1800569b2  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800569b9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800569be  mov     [rsp+70h+pcbData], rdi
0x1800569c3  mov     r9, rax
0x1800569c6  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x1800569cd  mov     [rsp+70h+pvData], rax
0x1800569d2  mov     dword ptr [rsp+70h+pdwType], 420h
0x1800569da  jmp     loc_180056A8E
0x1800569df  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800569e6  mov     ecx, [rbp+arg_0]
0x1800569e9  mov     rax, [rax+28h]
0x1800569ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569f2  mov     r13, rax
0x1800569f5  test    rax, rax
0x1800569f8  jnz     short loc_180056A2C
0x1800569fa  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056a01  mov     ebx, 0C0000017h
0x180056a06  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056a0b  mov     [rsp+70h+pcbData], rdi
0x180056a10  mov     r9, rax
0x180056a13  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180056a1a  mov     [rsp+70h+pvData], rax
0x180056a1f  mov     dword ptr [rsp+70h+pdwType], 426h
0x180056a27  jmp     loc_18005675C
0x180056a2c  cmp     qword ptr [r15], 0
0x180056a30  lea     r8, aWsWs; "%ws%ws"
0x180056a37  mov     edx, [rbp+arg_0]
0x180056a3a  mov     rax, rdi
0x180056a3d  cmovnz  rax, [r15]
0x180056a41  mov     r9, rdi
0x180056a44  xor     r15d, r15d
0x180056a47  mov     [rsp+70h+pdwType], rax; int (*)(void *, struct _UNICODE_STRING *)
0x180056a4c  cmp     [r14+30h], r15
0x180056a50  mov     rcx, r13; unsigned __int16 *
0x180056a53  cmovnz  r9, [r14+30h]
0x180056a58  shr     rdx, 1; unsigned __int64
0x180056a5b  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056a60  mov     ebx, eax
0x180056a62  test    eax, eax
0x180056a64  jz      short loc_180056ABF
0x180056a66  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056a6d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056a72  mov     [rsp+70h+pcbData], rdi
0x180056a77  mov     r9, rax
0x180056a7a  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x180056a81  mov     [rsp+70h+pvData], rax
0x180056a86  mov     dword ptr [rsp+70h+pdwType], 42Fh
0x180056a8e  mov     r8d, ebx
0x180056a91  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180056a98  xor     ecx, ecx
0x180056a9a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180056a9f  test    ebx, ebx
0x180056aa1  js      loc_180056CA6
0x180056aa7  movups  xmm0, xmmword ptr [rbp+var_28.Length]
0x180056aab  mov     rax, [rbp+arg_20]
0x180056aaf  xorps   xmm1, xmm1
0x180056ab2  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x180056ab6  movdqu  xmmword ptr [rax], xmm0
0x180056aba  jmp     loc_180056CA6
0x180056abf  mov     rdx, r13; SourceString
0x180056ac2  lea     rcx, [rbp+DestinationString]; DestinationString
0x180056ac6  call    cs:__imp_RtlInitUnicodeString
0x180056acc  mov     r14, [rbp+arg_8]
0x180056ad0  lea     rax, [rbp+var_28]
0x180056ad4  mov     r9, r14; void *
0x180056ad7  mov     [rsp+70h+pvData], rax; struct _UNICODE_STRING *
0x180056adc  mov     r8d, 14h; unsigned int
0x180056ae2  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180056ae6  mov     cl, r12b; bool
0x180056ae9  call    ?CheckAndSanitizeSAMName@@YAJ_NPEAU_UNICODE_STRING@@KPEAXP6AH21@Z1@Z; CheckAndSanitizeSAMName(bool,_UNICODE_STRING *,ulong,void *,int (*)(void *,_UNICODE_STRING *),_UNICODE_STRING *)
0x180056aee  mov     ebx, eax
0x180056af0  test    eax, eax
0x180056af2  jns     short loc_180056AA7
0x180056af4  cmp     eax, 0C0000063h
0x180056af9  jz      short loc_180056B2F
0x180056afb  cmp     eax, 0C0000161h
0x180056b00  jz      short loc_180056B2F
0x180056b02  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056b09  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056b0e  mov     [rsp+70h+pcbData], r13
0x180056b13  mov     r9, rax
0x180056b16  lea     rax, aCheckandsaniti; "CheckAndSanitizeSAMName"
0x180056b1d  mov     [rsp+70h+pvData], rax
0x180056b22  mov     dword ptr [rsp+70h+pdwType], 440h
0x180056b2a  jmp     loc_18005675C
0x180056b2f  mov     rcx, [rbp+var_28.Buffer]
0x180056b33  test    rcx, rcx
0x180056b36  jz      short loc_180056B55
0x180056b38  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180056b3f  mov     rax, [rax+30h]
0x180056b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b48  xorps   xmm0, xmm0
0x180056b4b  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x180056b4f  jmp     short loc_180056B55
0x180056b51  mov     r14, [rbp+arg_8]
0x180056b55  mov     rdx, rsi; SourceString
0x180056b58  lea     rcx, [rbp+DestinationString]; DestinationString
0x180056b5c  call    cs:__imp_RtlInitUnicodeString
0x180056b62  lea     rax, [rbp+var_28]
0x180056b66  mov     r9, r14; void *
0x180056b69  mov     r8d, 5; unsigned int
0x180056b6f  mov     [rsp+70h+pvData], rax; struct _UNICODE_STRING *
0x180056b74  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180056b78  mov     cl, r12b; bool
  ... truncated ...
```
