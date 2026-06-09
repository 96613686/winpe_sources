# SaveCaches(_ApPluginPkg *,bool,bool,_CloudAPCache *,_USER_CACHE_ENTRY *,_APPLUGIN_USER_INFO *,_SEC_WINNT_AUTH_FIDO_DATA *,uchar *,ulong)

- ea: `0x180039090`
- end: `0x180039610`
- name: `?SaveCaches@@YAJPEAU_ApPluginPkg@@_N1PEAU_CloudAPCache@@PEAU_USER_CACHE_ENTRY@@PEAU_APPLUGIN_USER_INFO@@PEAU_SEC_WINNT_AUTH_FIDO_DATA@@PEAEK@Z`
- size: `1408`
- prototype: `__int64 __fastcall(const unsigned __int16 **, __int64, char, struct _CloudAPCache *, struct _USER_CACHE_ENTRY *, struct _APPLUGIN_USER_INFO *, struct _SEC_WINNT_AUTH_FIDO_DATA *, unsigned __int8 *, unsigned int)`
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800035b4`
- `0x180011960`
- `0x180016a10`
- `0x180017780`
- `0x18004a870`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000ed04`
- `0x18000fb70`
- `0x18000fd50`
- `0x180022980`
- `0x180037164`
- `0x180039090`
- `0x180059a8c`
- `0x18005f208`
- `0x18005f6b0`
- `0x180063d1c`
- `0x1800641e4`
- `0x180064658`
- `0x180081010`

## string_xrefs

- `0x180039106`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180039176`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003923e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003915e`: `CacheData`
- `0x18003922f`: `PublicCacheData`
- `0x1800395c3`: `PublicCacheData`
- `0x18003918e`: `SaveLogonCacheForUser`
- `0x180039266`: `GetLogonPublicCacheForUser`
- `0x180039419`: `GetRawCacheNode`
- `0x18003946f`: `FIDOValidatePublicCacheData`
- `0x180039121`: `Primary AP cache is currently designed for FIDO only`
- `0x180039301`: `AllocateCloudAPCache`
- `0x180039385`: `Plugin returned bad FIDO data`
- `0x1800394d9`: `FIDOCreatePublicCacheData`
- `0x180039526`: `AddRawCacheNode`
- `0x180039599`: `UpdateFidoPrimaryApCacheNode`
- `0x1800395f7`: `SaveLogonPublicCacheForUser`

## pseudocode

```c
__int64 __fastcall SaveCaches(
        const unsigned __int16 **a1,
        __int64 a2,
        char a3,
        struct _CloudAPCache *a4,
        struct _USER_CACHE_ENTRY *a5,
        struct _APPLUGIN_USER_INFO *a6,
        struct _SEC_WINNT_AUTH_FIDO_DATA *a7,
        unsigned __int8 *a8,
        unsigned int a9)
{
  unsigned __int8 *v9; // r13
  const unsigned __int16 **v10; // r10
  struct _CloudAPCache *v11; // r15
  unsigned __int8 *v13; // r8
  __int64 v14; // rcx
  unsigned int LogonCacheForUser; // ebx
  const char *v16; // rax
  unsigned __int16 *v17; // rax
  const char *v19; // rax
  const char *v20; // rax
  const char *v21; // rax
  struct _SEC_WINNT_AUTH_FIDO_DATA *v22; // rcx
  struct _APPLUGIN_FIDO_PUBLIC_CACHED_INFO *v23; // r9
  const char *v24; // rax
  const char *v25; // rax
  unsigned int v26; // r12d
  const char *v27; // rax
  int updated; // eax
  const char *v29; // rax
  __int64 v30; // r8
  unsigned __int8 **v31; // [rsp+20h] [rbp-60h]
  const char *v32; // [rsp+28h] [rbp-58h]
  unsigned int v33[2]; // [rsp+30h] [rbp-50h]
  bool v34[4]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int RawCacheNode; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v36; // [rsp+48h] [rbp-38h] BYREF
  struct _CloudAPCache *v37; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 *v38; // [rsp+58h] [rbp-28h] BYREF
  int v39; // [rsp+60h] [rbp-20h] BYREF
  int v40; // [rsp+64h] [rbp-1Ch]
  struct _tagCacheNodeIdentifier *v41; // [rsp+68h] [rbp-18h]
  unsigned __int16 *v42; // [rsp+70h] [rbp-10h]
  char v44; // [rsp+C8h] [rbp+48h] BYREF
  char v45; // [rsp+D0h] [rbp+50h] BYREF

  v45 = a3;
  v44 = a2;
  v9 = 0;
  v10 = a1;
  v39 = 259;
  v11 = 0;
  v38 = 0;
  v37 = 0;
  v13 = a8;
  v41 = (struct _USER_CACHE_ENTRY *)((char *)a5 + 296);
  v14 = *((unsigned int *)a5 + 74);
  v40 = *((_DWORD *)a5 + 74);
  v36 = 0;
  v34[0] = 0;
  if ( a8 && (_DWORD)v14 != 7 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, a2, a8, a4);
    LogonCacheForUser = -1073741637;
    RawCacheNode = -1073741637;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v32 = "Primary AP cache is currently designed for FIDO only";
    LODWORD(v31) = 2548;
LABEL_4:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v16, v31, v32, &Class);
    goto LABEL_13;
  }
  v17 = (unsigned __int16 *)((char *)a5 + 104);
  v42 = (unsigned __int16 *)((char *)a5 + 104);
  if ( (_BYTE)a2 )
  {
    RawCacheNode = _SaveLogonCacheForUser(v10[43], v17, L"CacheData", a4);
    LogonCacheForUser = RawCacheNode;
    if ( RawCacheNode )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v32 = "SaveLogonCacheForUser";
      LODWORD(v31) = 2559;
      goto LABEL_4;
    }
    v13 = a8;
    v17 = v42;
    v10 = a1;
  }
  if ( !a3 && !v13 )
    goto LABEL_11;
  LogonCacheForUser = _GetLogonCacheForUser(v10[43], v17, L"PublicCacheData", &v37);
  if ( (LogonCacheForUser & 0x80000000) != 0 )
  {
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v19, 2575, "GetLogonPublicCacheForUser", &Class);
    if ( LogonCacheForUser == -1073741801 || LogonCacheForUser == -1073741670 )
    {
      RawCacheNode = LogonCacheForUser;
      v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v31) = 2580;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCacheForUser, v20, v31, "GetLogonPublicCacheForUser", &Class);
LABEL_20:
      v11 = v37;
      goto LABEL_13;
    }
  }
  v11 = v37;
  if ( !v37 )
  {
    RawCacheNode = AllocateCloudAPCache(0, &stru_18009B180, &v37);
    LogonCacheForUser = RawCacheNode;
    if ( RawCacheNode )
    {
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v31) = 2591;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RawCacheNode, v21, v31, "AllocateCloudAPCache", &Class);
      goto LABEL_20;
    }
    v11 = v37;
  }
  v22 = a7;
  if ( !a3 )
  {
LABEL_46:
    if ( v22 )
    {
      updated = UpdateFidoPrimaryApCacheNode(
                  v11,
                  v22,
                  v34[0],
                  *((unsigned __int8 **)a5 + 38),
                  *((_DWORD *)a5 + 75),
                  a8,
                  a9);
      v39 = updated;
      if ( updated != -1073741275 )
      {
        if ( updated )
        {
          v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v31) = 2683;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v29, v31, "UpdateFidoPrimaryApCacheNode", &Class);
        }
      }
    }
    RawCacheNode = _SaveLogonCacheForUser(a1[43], v42, L"PublicCacheData", v11);
    LogonCacheForUser = RawCacheNode;
    if ( RawCacheNode )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v32 = "SaveLogonPublicCacheForUser";
      LODWORD(v31) = 2690;
      goto LABEL_4;
    }
    goto LABEL_12;
  }
  if ( !*((_DWORD *)a6 + 28) )
  {
LABEL_11:
    RawCacheNode = 0;
LABEL_12:
    LogonCacheForUser = 0;
    goto LABEL_13;
  }
  if ( *((_DWORD *)a6 + 28) != 6 )
  {
    LogonCacheForUser = -1073741637;
    RawCacheNode = -1073741637;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v32 = "Non FIDO key types aren't currently supported";
    LODWORD(v31) = 2656;
    goto LABEL_4;
  }
  v23 = (struct _APPLUGIN_FIDO_PUBLIC_CACHED_INFO *)*((_QWORD *)a6 + 15);
  if ( !v23 )
  {
    LogonCacheForUser = -1073741595;
    RawCacheNode = -1073741595;
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v32 = "Plugin returned bad FIDO data";
    LODWORD(v31) = 2608;
    goto LABEL_4;
  }
  if ( v40 != 7 )
  {
    LogonCacheForUser = -1073741788;
    RawCacheNode = -1073741788;
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v33[0] = *((_DWORD *)a5 + 74);
    LODWORD(v31) = 2615;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%u",
      3221225508LL,
      v24,
      v31,
      "Internal key type user state doesn't match the User Info",
      *(_QWORD *)v33);
    goto LABEL_13;
  }
  if ( a7 )
  {
    RawCacheNode = FIDOCreatePublicCacheData(*((unsigned __int16 **)a5 + 12), *((void **)a5 + 30), a7, v23, &v38, &v36);
    LogonCacheForUser = RawCacheNode;
    if ( RawCacheNode )
    {
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v31) = 2648;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RawCacheNode, v27, v31, "FIDOCreatePublicCacheData", &Class);
      goto LABEL_36;
    }
    v9 = v38;
    v26 = v36;
    v34[0] = 1;
    goto LABEL_43;
  }
  RawCacheNode = GetRawCacheNode(v11, v41, &v38, &v36);
  LogonCacheForUser = RawCacheNode;
  if ( !RawCacheNode )
  {
    v9 = v38;
    v26 = v36;
    RawCacheNode = FIDOValidatePublicCacheData(v38, v36);
    LogonCacheForUser = RawCacheNode;
    if ( RawCacheNode )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v32 = "FIDOValidatePublicCacheData";
      LODWORD(v31) = 2632;
      goto LABEL_4;
    }
    *((_QWORD *)v9 + 1) = *(_QWORD *)(*((_QWORD *)a6 + 15) + 4LL);
LABEL_43:
    RawCacheNode = AddRawCacheNode(v11, v41, v9, v26);
    LogonCacheForUser = RawCacheNode;
    if ( RawCacheNode )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v32 = "AddRawCacheNode";
      LODWORD(v31) = 2664;
      goto LABEL_4;
    }
    v22 = a7;
    goto LABEL_46;
  }
  v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  LODWORD(v31) = 2628;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", RawCacheNode, v25, v31, "GetRawCacheNode", &Class);
LABEL_36:
  v9 = v38;
LABEL_13:
  CloudAPProvider::SaveCachesStatus<long &,long &,unsigned long &,bool &,bool &,bool &>(
    (unsigned int)&RawCacheNode,
    (unsigned int)&v39,
    (_DWORD)v41,
    (unsigned int)&v44,
    (__int64)&v45,
    (__int64)v34);
  if ( v9 )
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  FreeCloudAPCache(v11);
  return LogonCacheForUser;
}

```

## disassembly

```asm
0x180039090  mov     rax, rsp
0x180039093  mov     [rax+20h], rbx
0x180039097  mov     [rax+18h], r8b
0x18003909b  mov     [rax+10h], dl
0x18003909e  mov     [rax+8], rcx
0x1800390a2  push    rbp
0x1800390a3  push    rsi
0x1800390a4  push    rdi
0x1800390a5  push    r12
0x1800390a7  push    r13
0x1800390a9  push    r14
0x1800390ab  push    r15
0x1800390ad  mov     rbp, rsp
0x1800390b0  sub     rsp, 80h
0x1800390b7  mov     rax, [rbp+arg_20]
0x1800390bb  xor     r13d, r13d
0x1800390be  mov     r10, rcx
0x1800390c1  mov     [rbp+var_20], 103h
0x1800390c8  xor     r15d, r15d
0x1800390cb  mov     [rbp+var_28], r13
0x1800390cf  mov     r12b, r8b
0x1800390d2  mov     [rbp+var_30], r15
0x1800390d6  mov     r8, [rbp+arg_38]
0x1800390da  lea     rcx, [rax+128h]
0x1800390e1  mov     [rbp+var_18], rcx
0x1800390e5  mov     ecx, [rcx]
0x1800390e7  mov     [rbp+var_1C], ecx
0x1800390ea  mov     [rbp+var_38], r13d
0x1800390ee  mov     [rbp+var_40], r13b
0x1800390f2  test    r8, r8
0x1800390f5  jz      short loc_18003914B
0x1800390f7  cmp     ecx, 7
0x1800390fa  jz      short loc_18003914B
0x1800390fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039101  mov     ebx, 0C00000BBh
0x180039106  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003910d  mov     [rbp+var_3C], ebx
0x180039110  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180039115  lea     r14, Class
0x18003911c  mov     qword ptr [rsp+80h+var_50], r14
0x180039121  lea     rcx, aPrimaryApCache; "Primary AP cache is currently designed "...
0x180039128  mov     [rsp+80h+var_58], rcx
0x18003912d  mov     dword ptr [rsp+80h+var_60], 9F4h
0x180039135  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003913c  mov     r9, rax
0x18003913f  mov     r8d, ebx
0x180039142  xor     ecx, ecx
0x180039144  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180039149  jmp     short loc_1800391C0
0x18003914b  add     rax, 68h ; 'h'
0x18003914f  mov     [rbp+var_10], rax
0x180039153  test    dl, dl
0x180039155  jz      short loc_1800391B0
0x180039157  mov     rcx, [r10+158h]; unsigned __int16 *
0x18003915e  lea     r8, aCachedata; "CacheData"
0x180039165  mov     rdx, rax; unsigned __int16 *
0x180039168  call    ?_SaveLogonCacheForUser@@YAJPEBG00PEAU_CloudAPCache@@@Z; _SaveLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache *)
0x18003916d  mov     [rbp+var_3C], eax
0x180039170  mov     ebx, eax
0x180039172  test    eax, eax
0x180039174  jz      short loc_1800391A4
0x180039176  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003917d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180039182  lea     r14, Class
0x180039189  mov     qword ptr [rsp+80h+var_50], r14
0x18003918e  lea     rcx, aSavelogoncache; "SaveLogonCacheForUser"
0x180039195  mov     [rsp+80h+var_58], rcx
0x18003919a  mov     dword ptr [rsp+80h+var_60], 9FFh
0x1800391a2  jmp     short loc_180039135
0x1800391a4  mov     r8, [rbp+arg_38]
0x1800391a8  mov     rax, [rbp+var_10]
0x1800391ac  mov     r10, [rbp+arg_0]
0x1800391b0  test    r12b, r12b
0x1800391b3  jnz     short loc_180039224
0x1800391b5  test    r8, r8
0x1800391b8  jnz     short loc_180039224
0x1800391ba  mov     [rbp+var_3C], r13d
0x1800391be  xor     ebx, ebx
0x1800391c0  mov     r8, [rbp+var_18]
0x1800391c4  lea     rax, [rbp+var_40]
0x1800391c8  mov     [rsp+80h+var_58], rax
0x1800391cd  lea     r9, [rbp+arg_8]
0x1800391d1  lea     rax, [rbp+arg_10]
0x1800391d5  lea     rdx, [rbp+var_20]
0x1800391d9  mov     [rsp+80h+var_60], rax
0x1800391de  lea     rcx, [rbp+var_3C]
0x1800391e2  call    ??$SaveCachesStatus@AEAJAEAJAEAKAEA_NAEA_NAEA_N@CloudAPProvider@@SAXAEAJ0AEAKAEA_N22@Z; CloudAPProvider::SaveCachesStatus<long &,long &,ulong &,bool &,bool &,bool &>(long &,long &,ulong &,bool &,bool &,bool &)
0x1800391e7  test    r13, r13
0x1800391ea  jz      short loc_1800391FF
0x1800391ec  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800391f3  mov     rcx, r13
0x1800391f6  mov     rax, [rax+30h]
0x1800391fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391ff  mov     rcx, r15; hMem
0x180039202  call    ?FreeCloudAPCache@@YAXPEAU_CloudAPCache@@@Z; FreeCloudAPCache(_CloudAPCache *)
0x180039207  mov     eax, ebx
0x180039209  mov     rbx, [rsp+80h+arg_18]
0x180039211  add     rsp, 80h
0x180039218  pop     r15
0x18003921a  pop     r14
0x18003921c  pop     r13
0x18003921e  pop     r12
0x180039220  pop     rdi
0x180039221  pop     rsi
0x180039222  pop     rbp
0x180039223  retn
0x180039224  mov     rcx, [r10+158h]; unsigned __int16 *
0x18003922b  lea     r9, [rbp+var_30]; struct _CloudAPCache **
0x18003922f  lea     r8, aPubliccachedat; "PublicCacheData"
0x180039236  mov     rdx, rax; unsigned __int16 *
0x180039239  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18003923e  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180039245  mov     ebx, eax
0x180039247  lea     r14, Class
0x18003924e  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180039255  test    eax, eax
0x180039257  jns     short loc_1800392D0
0x180039259  mov     rcx, rdi; char *
0x18003925c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180039261  mov     qword ptr [rsp+80h+var_50], r14
0x180039266  lea     r15, aGetlogonpublic; "GetLogonPublicCacheForUser"
0x18003926d  mov     [rsp+80h+var_58], r15
0x180039272  mov     r9, rax
0x180039275  mov     r8d, ebx
0x180039278  mov     dword ptr [rsp+80h+var_60], 0A0Fh
0x180039280  mov     rdx, rsi
0x180039283  xor     ecx, ecx
0x180039285  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003928a  cmp     ebx, 0C0000017h
0x180039290  jz      short loc_18003929A
0x180039292  cmp     ebx, 0C000009Ah
0x180039298  jnz     short loc_1800392D0
0x18003929a  mov     rcx, rdi; char *
0x18003929d  mov     [rbp+var_3C], ebx
0x1800392a0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800392a5  mov     qword ptr [rsp+80h+var_50], r14
0x1800392aa  mov     [rsp+80h+var_58], r15
0x1800392af  mov     dword ptr [rsp+80h+var_60], 0A14h
0x1800392b7  mov     r9, rax
0x1800392ba  mov     r8d, ebx
0x1800392bd  mov     rdx, rsi
0x1800392c0  xor     ecx, ecx
0x1800392c2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800392c7  mov     r15, [rbp+var_30]
0x1800392cb  jmp     loc_1800391C0
0x1800392d0  mov     r15, [rbp+var_30]
0x1800392d4  test    r15, r15
0x1800392d7  jnz     short loc_18003931B
0x1800392d9  lea     r8, [rbp+var_30]; struct _CloudAPCache **
0x1800392dd  xor     ecx, ecx; unsigned int
0x1800392df  lea     rdx, stru_18009B180; struct _GUID *
0x1800392e6  call    ?AllocateCloudAPCache@@YAJKPEAU_GUID@@PEAPEAU_CloudAPCache@@@Z; AllocateCloudAPCache(ulong,_GUID *,_CloudAPCache * *)
0x1800392eb  mov     [rbp+var_3C], eax
0x1800392ee  mov     ebx, eax
0x1800392f0  test    eax, eax
0x1800392f2  jz      short loc_180039317
0x1800392f4  mov     rcx, rdi; char *
0x1800392f7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800392fc  mov     qword ptr [rsp+80h+var_50], r14
0x180039301  lea     rcx, aAllocateclouda; "AllocateCloudAPCache"
0x180039308  mov     [rsp+80h+var_58], rcx
0x18003930d  mov     dword ptr [rsp+80h+var_60], 0A1Fh
0x180039315  jmp     short loc_1800392B7
0x180039317  mov     r15, [rbp+var_30]
0x18003931b  mov     rcx, [rbp+arg_30]
0x18003931f  test    r12b, r12b
0x180039322  jz      loc_180039543
0x180039328  mov     rax, [rbp+arg_28]
0x18003932c  cmp     [rax+70h], r13d
0x180039330  jz      loc_1800391BA
0x180039336  cmp     dword ptr [rax+70h], 6
0x18003933a  jz      short loc_180039367
0x18003933c  mov     ebx, 0C00000BBh
0x180039341  mov     rcx, rdi; char *
0x180039344  mov     [rbp+var_3C], ebx
0x180039347  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003934c  mov     qword ptr [rsp+80h+var_50], r14
0x180039351  lea     rcx, aNonFidoKeyType_0; "Non FIDO key types aren't currently sup"...
0x180039358  mov     [rsp+80h+var_58], rcx
0x18003935d  mov     dword ptr [rsp+80h+var_60], 0A60h
0x180039365  jmp     short loc_180039399
0x180039367  mov     r9, [rax+78h]; struct _APPLUGIN_FIDO_PUBLIC_CACHED_INFO *
0x18003936b  test    r9, r9
0x18003936e  jnz     short loc_1800393A1
0x180039370  mov     ebx, 0C00000E5h
0x180039375  mov     rcx, rdi; char *
0x180039378  mov     [rbp+var_3C], ebx
0x18003937b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180039380  mov     qword ptr [rsp+80h+var_50], r14
0x180039385  lea     rcx, aPluginReturned; "Plugin returned bad FIDO data"
0x18003938c  mov     [rsp+80h+var_58], rcx
0x180039391  mov     dword ptr [rsp+80h+var_60], 0A30h
0x180039399  mov     rdx, rsi
0x18003939c  jmp     loc_18003913C
0x1800393a1  cmp     [rbp+var_1C], 7
0x1800393a5  jz      short loc_1800393E6
0x1800393a7  mov     ebx, 0C0000024h
0x1800393ac  mov     rcx, rdi; char *
0x1800393af  mov     [rbp+var_3C], ebx
0x1800393b2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800393b7  mov     r9, [rbp+arg_20]
0x1800393bb  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x1800393c2  mov     ecx, [r9+128h]
0x1800393c9  mov     [rsp+80h+var_50], ecx
0x1800393cd  lea     rcx, aInternalKeyTyp; "Internal key type user state doesn't ma"...
0x1800393d4  mov     [rsp+80h+var_58], rcx
0x1800393d9  mov     dword ptr [rsp+80h+var_60], 0A37h
0x1800393e1  jmp     loc_18003913C
0x1800393e6  test    rcx, rcx
0x1800393e9  jnz     loc_18003949A
0x1800393ef  mov     rdx, [rbp+var_18]; struct _tagCacheNodeIdentifier *
0x1800393f3  lea     r9, [rbp+var_38]; unsigned int *
0x1800393f7  lea     r8, [rbp+var_28]; unsigned __int8 **
0x1800393fb  mov     rcx, r15; struct _CloudAPCache *
0x1800393fe  call    ?GetRawCacheNode@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAPEAEPEAK@Z; GetRawCacheNode(_CloudAPCache *,_tagCacheNodeIdentifier *,uchar * *,ulong *)
0x180039403  mov     [rbp+var_3C], eax
0x180039406  mov     ebx, eax
0x180039408  test    eax, eax
0x18003940a  jz      short loc_180039446
0x18003940c  mov     rcx, rdi; char *
0x18003940f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180039414  mov     qword ptr [rsp+80h+var_50], r14
0x180039419  lea     rcx, aGetrawcachenod; "GetRawCacheNode"
0x180039420  mov     [rsp+80h+var_58], rcx
0x180039425  mov     dword ptr [rsp+80h+var_60], 0A44h
0x18003942d  mov     r9, rax
0x180039430  mov     r8d, ebx
0x180039433  mov     rdx, rsi
0x180039436  xor     ecx, ecx
0x180039438  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003943d  mov     r13, [rbp+var_28]
0x180039441  jmp     loc_1800391C0
0x180039446  mov     r13, [rbp+var_28]
0x18003944a  mov     r12d, [rbp+var_38]
0x18003944e  mov     rcx, r13; unsigned __int8 *
0x180039451  mov     edx, r12d; unsigned int
0x180039454  call    ?FIDOValidatePublicCacheData@@YAJPEAEK@Z; FIDOValidatePublicCacheData(uchar *,ulong)
0x180039459  mov     [rbp+var_3C], eax
0x18003945c  mov     ebx, eax
0x18003945e  test    eax, eax
0x180039460  jz      short loc_180039488
0x180039462  mov     rcx, rdi; char *
0x180039465  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003946a  mov     qword ptr [rsp+80h+var_50], r14
0x18003946f  lea     rcx, aFidovalidatepu; "FIDOValidatePublicCacheData"
0x180039476  mov     [rsp+80h+var_58], rcx
0x18003947b  mov     dword ptr [rsp+80h+var_60], 0A48h
0x180039483  jmp     loc_180039399
0x180039488  mov     rax, [rbp+arg_28]
0x18003948c  mov     rax, [rax+78h]
0x180039490  mov     rcx, [rax+4]
0x180039494  mov     [r13+8], rcx
0x180039498  jmp     short loc_1800394FE
0x18003949a  lea     rax, [rbp+var_38]
0x18003949e  mov     r8, rcx; struct _SEC_WINNT_AUTH_FIDO_DATA *
0x1800394a1  mov     [rsp+80h+var_58], rax; unsigned int *
0x1800394a6  lea     rax, [rbp+var_28]
0x1800394aa  mov     [rsp+80h+var_60], rax; unsigned __int8 **
0x1800394af  mov     rax, [rbp+arg_20]
0x1800394b3  mov     rdx, [rax+0F0h]; void *
0x1800394ba  mov     rcx, [rax+60h]; Src
0x1800394be  call    ?FIDOCreatePublicCacheData@@YAJPEAGPEAXPEAU_SEC_WINNT_AUTH_FIDO_DATA@@PEAU_APPLUGIN_FIDO_PUBLIC_CACHED_INFO@@PEAPEAEPEAK@Z; FIDOCreatePublicCacheData(ushort *,void *,_SEC_WINNT_AUTH_FIDO_DATA *,_APPLUGIN_FIDO_PUBLIC_CACHED_INFO *,uchar * *,ulong *)
0x1800394c3  mov     [rbp+var_3C], eax
0x1800394c6  mov     ebx, eax
0x1800394c8  test    eax, eax
0x1800394ca  jz      short loc_1800394F2
0x1800394cc  mov     rcx, rdi; char *
0x1800394cf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800394d4  mov     qword ptr [rsp+80h+var_50], r14
0x1800394d9  lea     rcx, aFidocreatepubl; "FIDOCreatePublicCacheData"
0x1800394e0  mov     [rsp+80h+var_58], rcx
0x1800394e5  mov     dword ptr [rsp+80h+var_60], 0A58h
0x1800394ed  jmp     loc_18003942D
0x1800394f2  mov     r13, [rbp+var_28]
0x1800394f6  mov     r12d, [rbp+var_38]
0x1800394fa  mov     [rbp+var_40], 1
0x1800394fe  mov     rdx, [rbp+var_18]; struct _tagCacheNodeIdentifier *
0x180039502  mov     r9d, r12d; unsigned int
0x180039505  mov     r8, r13; unsigned __int8 *
0x180039508  mov     rcx, r15; struct _CloudAPCache *
0x18003950b  call    ?AddRawCacheNode@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAEK@Z; AddRawCacheNode(_CloudAPCache *,_tagCacheNodeIdentifier *,uchar *,ulong)
0x180039510  mov     [rbp+var_3C], eax
0x180039513  mov     ebx, eax
0x180039515  test    eax, eax
0x180039517  jz      short loc_18003953F
0x180039519  mov     rcx, rdi; char *
0x18003951c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180039521  mov     qword ptr [rsp+80h+var_50], r14
0x180039526  lea     rcx, aAddrawcachenod; "AddRawCacheNode"
0x18003952d  mov     [rsp+80h+var_58], rcx
0x180039532  mov     dword ptr [rsp+80h+var_60], 0A68h
0x18003953a  jmp     loc_180039399
0x18003953f  mov     rcx, [rbp+arg_30]
0x180039543  test    rcx, rcx
0x180039546  jz      short loc_1800395BF
0x180039548  mov     eax, [rbp+arg_40]
0x18003954e  mov     rdx, rcx; struct _SEC_WINNT_AUTH_FIDO_DATA *
0x180039551  mov     r9, [rbp+arg_20]
0x180039555  mov     rcx, r15; struct _CloudAPCache *
0x180039558  mov     r8b, [rbp+var_40]; bool
  ... truncated ...
```
