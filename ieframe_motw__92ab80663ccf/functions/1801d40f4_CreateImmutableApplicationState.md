# _CreateImmutableApplicationState

- ea: `0x1801d40f4`
- end: `0x1801d45df`
- name: `_CreateImmutableApplicationState`
- size: `1259`
- prototype: `__int64 __fastcall(PCWSTR pszFirst)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801d3c00`

## callees

- `0x180074e98`
- `0x18009b8d4`
- `0x1800a2320`
- `0x1800b6304`
- `0x1801ce39c`
- `0x1801d40f4`
- `0x1801d52dc`
- `0x180591f80`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1801d4591`
- `KERNEL32!GetCurrentProcessId` at `0x1801d4591`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801d43b9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrTrimW` at `0x1801d43b9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrW` at `0x1801d433e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrW` at `0x1801d433e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrRChrW` at `0x1801d437e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrRChrW` at `0x1801d437e`
- `iertutil!__imp_?IAS_Create@@YAJAEBU_GUID@@PEBG@Z` at `0x1801d45ae`
- `iertutil!__imp_?IAS_Create@@YAJAEBU_GUID@@PEBG@Z` at `0x1801d45ae`
- `iertutil!__imp_GetValue` at `0x1801d4523`
- `iertutil!__imp_GetValue` at `0x1801d4523`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d44dc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d455e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d44dc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d455e`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4129`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d415a`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d41e2`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4218`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4244`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4291`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d42ca`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d42fe`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4404`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d444f`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d44c1`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d457f`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4129`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d415a`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d41e2`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4218`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4244`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4291`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d42ca`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d42fe`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d4404`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d444f`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d44c1`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1801d457f`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801d41ae`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801d4541`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801d41ae`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801d4541`
- `iertutil!__imp_?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z` at `0x1801d43a1`
- `iertutil!__imp_?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z` at `0x1801d43a1`

## pseudocode

```c
__int64 __fastcall CreateImmutableApplicationState(unsigned __int16 *pszFirst)
{
  __int64 v2; // rdx
  char v3; // si
  __int64 v4; // rdx
  int Value; // ebx
  __int64 v6; // rdx
  UINT v7; // eax
  __int64 v8; // rdx
  char v9; // si
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  char v14; // r14
  __int64 v15; // rsi
  const WCHAR *v16; // rbx
  __int64 v17; // rax
  PWSTR v18; // rax
  __int64 v19; // rdx
  bool v20; // al
  __int64 v21; // rdx
  bool v22; // al
  __int64 v23; // rdx
  __int64 v24; // rdx
  bool v25; // al
  char Bool; // al
  __int64 v27; // rdx
  char v28; // di
  int v29; // ebx
  __int64 v30; // rdx
  DWORD CurrentProcessId; // eax
  unsigned int v33; // [rsp+40h] [rbp-38h] BYREF
  struct _GUID pszSrch; // [rsp+48h] [rbp-30h] BYREF

  LOBYTE(v2) = SetHangRecoveryOptions(0, pszFirst);
  v3 = v2;
  Value = IEConfiguration_SetBool(268435460, v2);
  if ( Value >= 0 )
  {
    if ( !v3 || (LOBYTE(v4) = 1, g_fNoAlternateOwner) )
      LOBYTE(v4) = 0;
    Value = IEConfiguration_SetBool(268435461, v4);
    if ( Value >= 0 )
    {
      v6 = 0;
      if ( v3 )
      {
        v6 = 250;
        if ( !g_fTabWindow_HungTab_NoNotificationDelay )
        {
          v7 = g_cTabWindow_SyncTMO_Failing;
          if ( g_cTabWindow_HungTab_NotificationDelay < g_cTabWindow_SyncTMO_Failing )
            v7 = g_cTabWindow_HungTab_NotificationDelay;
          if ( v7 > 0xFA )
          {
            v6 = g_cTabWindow_SyncTMO_Failing;
            if ( g_cTabWindow_HungTab_NotificationDelay < g_cTabWindow_SyncTMO_Failing )
              v6 = g_cTabWindow_HungTab_NotificationDelay;
          }
        }
      }
      Value = IEConfiguration_SetDWORD(268435470, v6);
      if ( Value >= 0 )
      {
        LOBYTE(v8) = FindAndRemoveBooleanCommandLineOption(8, L"-private", pszFirst);
        v9 = v8;
        Value = IEConfiguration_SetBool(268435462, v8);
        if ( Value >= 0 )
        {
          if ( !v9 || (Value = DisableTelemetryForCurrentProcess(1), Value >= 0) )
          {
            Value = IEConfiguration_SetBool(268435512, 0);
            if ( Value >= 0 )
            {
              LOBYTE(v10) = IsCommandSwitchPresent(pszFirst, L"-extoff");
              Value = IEConfiguration_SetBool(268435493, v10);
              if ( Value >= 0 )
              {
                if ( !IsCommandSwitchPresent(pszFirst, L"-debug")
                  || (v33 = 0,
                      GetBOOL((__int64 *)SettingStore::IEVALUE_Browser_ScriptDebugger_EnableHiddenTabs[0], &v33),
                      LOBYTE(v11) = 1,
                      v33) )
                {
                  LOBYTE(v11) = 0;
                }
                Value = IEConfiguration_SetBool(268435494, v11);
                if ( Value >= 0 )
                {
                  v33 = 1;
                  GetBOOL((__int64 *)SettingStore::IEVALUE_PrivacIE_DisableToolbars[0], &v33);
                  LOBYTE(v12) = v33 != 0;
                  Value = IEConfiguration_SetBool(268435463, v12);
                  if ( Value >= 0 )
                  {
                    LOBYTE(v13) = FindAndRemoveBooleanCommandLineOption(2, L"-w", pszFirst);
                    v14 = v13;
                    Value = IEConfiguration_SetBool(268435465, v13);
                    if ( Value >= 0 )
                    {
                      v15 = -1;
                      if ( !v14 )
                        goto LABEL_63;
                      wcscpy((wchar_t *)&pszSrch, L".website");
                      v16 = StrStrW(pszFirst, (PCWSTR)&pszSrch);
                      if ( !v16 )
                        return (unsigned int)-2147467259;
                      v17 = -1;
                      do
                        ++v17;
                      while ( *((_WORD *)&pszSrch.Data1 + v17) );
                      if ( v16[v17] != 34 )
                        return (unsigned int)-2147467259;
                      v18 = StrRChrW(pszFirst, v16, 0x22u);
                      if ( v18 )
                      {
                        Value = IEConfiguration_SetString(268435466, v18, ((char *)v16 - (char *)v18 + 18) >> 1);
                        StrTrimW(pszFirst, asc_180619510);
                      }
                      else
                      {
                        Value = -2147467259;
                      }
                      if ( Value >= 0 )
                      {
LABEL_63:
                        if ( !IsCommandSwitchPresent(pszFirst, L"-embedding")
                          || (v20 = IsCommandSwitchPresent(pszFirst, L"-startmanager"), LOBYTE(v19) = 1, v20) )
                        {
                          LOBYTE(v19) = 0;
                        }
                        Value = IEConfiguration_SetBool(268435542, v19);
                        if ( Value >= 0 )
                        {
                          if ( !IsCommandSwitchPresent(pszFirst, L"-embedding")
                            || (v22 = FindAndRemoveBooleanCommandLineOption(13, L"-startmanager", pszFirst),
                                LOBYTE(v21) = 1,
                                !v22) )
                          {
                            LOBYTE(v21) = 0;
                          }
                          Value = IEConfiguration_SetBool(268435468, v21);
                          if ( Value >= 0 )
                          {
                            v23 = -1;
                            do
                              ++v23;
                            while ( pszFirst[v23] );
                            if ( !FindOrRemoveCommandArg(pszFirst, v23 + 1, L"-DualEngineAdapter=", 0, 0) )
                              goto LABEL_47;
                            do
                              ++v15;
                            while ( pszFirst[v15] );
                            v25 = FindOrRemoveCommandArg(pszFirst, v15 + 1, L"-DualEnginePipe=", 0, 0);
                            LOBYTE(v24) = 1;
                            if ( !v25 )
LABEL_47:
                              LOBYTE(v24) = 0;
                            Value = IEConfiguration_SetBool(268435535, v24);
                            if ( Value >= 0 )
                            {
                              Bool = IEConfiguration_GetBool(268435482);
                              v27 = 0;
                              v28 = Bool;
                              v33 = 0;
                              if ( Bool && g_fHangRecovery )
                              {
                                Value = GetValue((__int64 *)SettingStore::IEVALUE_LCIE_TSEnable[0], 1, 1, &v33, 4, 0, 0);
                                if ( Value < 0 )
                                  return (unsigned int)Value;
                                v27 = v33;
                              }
                              Value = IEConfiguration_SetDWORD(268435492, v27);
                              if ( Value >= 0 )
                              {
                                v29 = v33 & 9;
                                if ( !(unsigned __int8)IEConfiguration_GetBool(268435495)
                                  || !v28
                                  || v29 != 9
                                  || (LOBYTE(v30) = 1, Value = IEConfiguration_SetBool(268435496, v30), Value >= 0) )
                                {
                                  CurrentProcessId = GetCurrentProcessId();
                                  *(_QWORD *)&pszSrch.Data2 = 0;
                                  pszSrch.Data1 = CurrentProcessId;
                                  *(_DWORD *)&pszSrch.Data4[4] = 0;
                                  return (unsigned int)IAS_Create(&pszSrch, 0);
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1801d40f4  push    rbp
0x1801d40f6  push    rbx
0x1801d40f7  push    rsi
0x1801d40f8  push    rdi
0x1801d40f9  push    r14
0x1801d40fb  push    r15
0x1801d40fd  mov     rbp, rsp
0x1801d4100  sub     rsp, 78h
0x1801d4104  mov     rax, cs:__security_cookie
0x1801d410b  xor     rax, rsp
0x1801d410e  mov     [rbp+var_18], rax
0x1801d4112  mov     rdi, rcx
0x1801d4115  mov     rdx, rcx
0x1801d4118  xor     ecx, ecx
0x1801d411a  call    _SetHangRecoveryOptions
0x1801d411f  mov     dl, al
0x1801d4121  mov     ecx, 10000004h
0x1801d4126  mov     sil, al
0x1801d4129  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d4130  nop     dword ptr [rax+rax+00h]
0x1801d4135  xor     r15d, r15d
0x1801d4138  mov     ebx, eax
0x1801d413a  test    eax, eax
0x1801d413c  js      loc_1801D45BC
0x1801d4142  test    sil, sil
0x1801d4145  jz      short loc_1801D4152
0x1801d4147  cmp     cs:?g_fNoAlternateOwner@@3_NA, r15b; bool g_fNoAlternateOwner
0x1801d414e  mov     dl, 1
0x1801d4150  jz      short loc_1801D4155
0x1801d4152  mov     dl, r15b
0x1801d4155  mov     ecx, 10000005h
0x1801d415a  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d4161  nop     dword ptr [rax+rax+00h]
0x1801d4166  mov     ebx, eax
0x1801d4168  test    eax, eax
0x1801d416a  js      loc_1801D45BC
0x1801d4170  mov     edx, r15d
0x1801d4173  test    sil, sil
0x1801d4176  jz      short loc_1801D41A9
0x1801d4178  cmp     cs:?g_fTabWindow_HungTab_NoNotificationDelay@@3_NA, r15b; bool g_fTabWindow_HungTab_NoNotificationDelay
0x1801d417f  mov     edx, 0FAh
0x1801d4184  jnz     short loc_1801D41A9
0x1801d4186  mov     ecx, cs:?g_cTabWindow_SyncTMO_Failing@@3KA; ulong g_cTabWindow_SyncTMO_Failing
0x1801d418c  mov     eax, ecx
0x1801d418e  mov     r8d, cs:?g_cTabWindow_HungTab_NotificationDelay@@3KA; ulong g_cTabWindow_HungTab_NotificationDelay
0x1801d4195  cmp     r8d, ecx
0x1801d4198  cmovb   eax, r8d
0x1801d419c  cmp     eax, edx
0x1801d419e  jbe     short loc_1801D41A9
0x1801d41a0  cmp     r8d, ecx
0x1801d41a3  mov     edx, ecx
0x1801d41a5  cmovb   edx, r8d
0x1801d41a9  mov     ecx, 1000000Eh
0x1801d41ae  call    cs:__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x1801d41b5  nop     dword ptr [rax+rax+00h]
0x1801d41ba  mov     ebx, eax
0x1801d41bc  test    eax, eax
0x1801d41be  js      loc_1801D45BC
0x1801d41c4  mov     r8, rdi; unsigned __int16 *
0x1801d41c7  lea     rdx, aPrivate_0; "-private"
0x1801d41ce  mov     ecx, 8; int
0x1801d41d3  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801d41d8  mov     dl, al
0x1801d41da  mov     ecx, 10000006h
0x1801d41df  mov     sil, al
0x1801d41e2  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d41e9  nop     dword ptr [rax+rax+00h]
0x1801d41ee  mov     ebx, eax
0x1801d41f0  test    eax, eax
0x1801d41f2  js      loc_1801D45BC
0x1801d41f8  test    sil, sil
0x1801d41fb  jz      short loc_1801D4211
0x1801d41fd  mov     ecx, 1
0x1801d4202  call    ?DisableTelemetryForCurrentProcess@@YAJW4MarkProcessTelemetryStateFailed_Trigger@@@Z; DisableTelemetryForCurrentProcess(MarkProcessTelemetryStateFailed_Trigger)
0x1801d4207  mov     ebx, eax
0x1801d4209  test    eax, eax
0x1801d420b  js      loc_1801D45BC
0x1801d4211  xor     edx, edx
0x1801d4213  mov     ecx, 10000038h
0x1801d4218  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d421f  nop     dword ptr [rax+rax+00h]
0x1801d4224  mov     ebx, eax
0x1801d4226  test    eax, eax
0x1801d4228  js      loc_1801D45BC
0x1801d422e  lea     rdx, aExtoff_0; "-extoff"
0x1801d4235  mov     rcx, rdi; unsigned __int16 *
0x1801d4238  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1801d423d  mov     dl, al
0x1801d423f  mov     ecx, 10000025h
0x1801d4244  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d424b  nop     dword ptr [rax+rax+00h]
0x1801d4250  mov     ebx, eax
0x1801d4252  test    eax, eax
0x1801d4254  js      loc_1801D45BC
0x1801d425a  lea     rdx, aDebug_1; "-debug"
0x1801d4261  mov     rcx, rdi; unsigned __int16 *
0x1801d4264  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1801d4269  test    al, al
0x1801d426b  jz      short loc_1801D4289
0x1801d426d  mov     rcx, cs:?IEVALUE_Browser_ScriptDebugger_EnableHiddenTabs@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Browser_ScriptDebugger_EnableHiddenTabs
0x1801d4274  lea     rdx, [rbp+var_38]
0x1801d4278  mov     [rbp+var_38], r15d
0x1801d427c  call    GetBOOL
0x1801d4281  mov     dl, 1
0x1801d4283  cmp     [rbp+var_38], r15d
0x1801d4287  jz      short loc_1801D428C
0x1801d4289  mov     dl, r15b
0x1801d428c  mov     ecx, 10000026h
0x1801d4291  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d4298  nop     dword ptr [rax+rax+00h]
0x1801d429d  mov     ebx, eax
0x1801d429f  test    eax, eax
0x1801d42a1  js      loc_1801D45BC
0x1801d42a7  mov     rcx, cs:?IEVALUE_PrivacIE_DisableToolbars@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableToolbars
0x1801d42ae  lea     rdx, [rbp+var_38]
0x1801d42b2  mov     [rbp+var_38], 1
0x1801d42b9  call    GetBOOL
0x1801d42be  cmp     [rbp+var_38], r15d
0x1801d42c2  mov     ecx, 10000007h
0x1801d42c7  setnz   dl
0x1801d42ca  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d42d1  nop     dword ptr [rax+rax+00h]
0x1801d42d6  mov     ebx, eax
0x1801d42d8  test    eax, eax
0x1801d42da  js      loc_1801D45BC
0x1801d42e0  mov     r8, rdi; unsigned __int16 *
0x1801d42e3  lea     rdx, aW_0; "-w"
0x1801d42ea  mov     ecx, 2; int
0x1801d42ef  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801d42f4  mov     dl, al
0x1801d42f6  mov     ecx, 10000009h
0x1801d42fb  mov     r14b, al
0x1801d42fe  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d4305  nop     dword ptr [rax+rax+00h]
0x1801d430a  mov     ebx, eax
0x1801d430c  test    eax, eax
0x1801d430e  js      loc_1801D45BC
0x1801d4314  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801d4318  test    r14b, r14b
0x1801d431b  jz      loc_1801D43D4
0x1801d4321  movups  xmm0, xmmword ptr cs:aWebsite_1; ".website"
0x1801d4328  movzx   eax, word ptr cs:aWebsite_1+10h; ""
0x1801d432f  lea     rdx, [rbp+pszSrch]; pszSrch
0x1801d4333  mov     rcx, rdi; pszFirst
0x1801d4336  mov     [rbp+var_20], ax
0x1801d433a  movups  xmmword ptr [rbp+pszSrch.Data1], xmm0
0x1801d433e  call    cs:__imp_StrStrW
0x1801d4345  nop     dword ptr [rax+rax+00h]
0x1801d434a  mov     rbx, rax
0x1801d434d  test    rax, rax
0x1801d4350  jz      loc_1801D45D8
0x1801d4356  lea     rcx, [rbp+pszSrch]
0x1801d435a  mov     rax, rsi
0x1801d435d  inc     rax
0x1801d4360  cmp     [rcx+rax*2], r15w
0x1801d4365  jnz     short loc_1801D435D
0x1801d4367  mov     r8d, 22h ; '"'; wMatch
0x1801d436d  cmp     [rbx+rax*2], r8w
0x1801d4372  jnz     loc_1801D45D8
0x1801d4378  mov     rdx, rbx; pszEnd
0x1801d437b  mov     rcx, rdi; pszStart
0x1801d437e  call    cs:__imp_StrRChrW
0x1801d4385  nop     dword ptr [rax+rax+00h]
0x1801d438a  test    rax, rax
0x1801d438d  jz      short loc_1801D43C7
0x1801d438f  sub     rbx, rax
0x1801d4392  mov     rdx, rax
0x1801d4395  mov     ecx, 1000000Ah
0x1801d439a  lea     r8, [rbx+12h]
0x1801d439e  sar     r8, 1
0x1801d43a1  call    cs:__imp_?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z; IEConfiguration_SetString(IEConfigurationID,ushort *,ulong)
0x1801d43a8  nop     dword ptr [rax+rax+00h]
0x1801d43ad  lea     rdx, asc_180619510; " \t"
0x1801d43b4  mov     rcx, rdi; psz
0x1801d43b7  mov     ebx, eax
0x1801d43b9  call    cs:__imp_StrTrimW
0x1801d43c0  nop     dword ptr [rax+rax+00h]
0x1801d43c5  jmp     short loc_1801D43CC
0x1801d43c7  mov     ebx, 80004005h
0x1801d43cc  test    ebx, ebx
0x1801d43ce  js      loc_1801D45BC
0x1801d43d4  lea     rdx, aEmbedding; "-embedding"
0x1801d43db  mov     rcx, rdi; unsigned __int16 *
0x1801d43de  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1801d43e3  test    al, al
0x1801d43e5  jz      short loc_1801D43FC
0x1801d43e7  lea     rdx, aStartmanager; "-startmanager"
0x1801d43ee  mov     rcx, rdi; unsigned __int16 *
0x1801d43f1  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1801d43f6  mov     dl, 1
0x1801d43f8  test    al, al
0x1801d43fa  jz      short loc_1801D43FF
0x1801d43fc  mov     dl, r15b
0x1801d43ff  mov     ecx, 10000056h
0x1801d4404  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d440b  nop     dword ptr [rax+rax+00h]
0x1801d4410  mov     ebx, eax
0x1801d4412  test    eax, eax
0x1801d4414  js      loc_1801D45BC
0x1801d441a  lea     rdx, aEmbedding; "-embedding"
0x1801d4421  mov     rcx, rdi; unsigned __int16 *
0x1801d4424  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x1801d4429  test    al, al
0x1801d442b  jz      short loc_1801D4447
0x1801d442d  mov     r8, rdi; unsigned __int16 *
0x1801d4430  lea     rdx, aStartmanager; "-startmanager"
0x1801d4437  mov     ecx, 0Dh; int
0x1801d443c  call    ?FindAndRemoveBooleanCommandLineOption@@YA_NHPEAG0@Z; FindAndRemoveBooleanCommandLineOption(int,ushort *,ushort *)
0x1801d4441  mov     dl, 1
0x1801d4443  test    al, al
0x1801d4445  jnz     short loc_1801D444A
0x1801d4447  mov     dl, r15b
0x1801d444a  mov     ecx, 1000000Ch
0x1801d444f  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d4456  nop     dword ptr [rax+rax+00h]
0x1801d445b  mov     ebx, eax
0x1801d445d  test    eax, eax
0x1801d445f  js      loc_1801D45BC
0x1801d4465  mov     rdx, rsi
0x1801d4468  inc     rdx
0x1801d446b  cmp     [rdi+rdx*2], r15w
0x1801d4470  jnz     short loc_1801D4468
0x1801d4472  inc     edx; unsigned int
0x1801d4474  mov     [rsp+78h+var_58], r15b; bool
0x1801d4479  xor     r9d, r9d; unsigned __int16 **
0x1801d447c  lea     r8, aDualengineadap; "-DualEngineAdapter="
0x1801d4483  mov     rcx, rdi; pszFirst
0x1801d4486  call    ?FindOrRemoveCommandArg@@YA_NPEAGKPEBGPEAPEAG_N@Z; FindOrRemoveCommandArg(ushort *,ulong,ushort const *,ushort * *,bool)
0x1801d448b  test    al, al
0x1801d448d  jz      short loc_1801D44B9
0x1801d448f  inc     rsi
0x1801d4492  cmp     [rdi+rsi*2], r15w
0x1801d4497  jnz     short loc_1801D448F
0x1801d4499  lea     edx, [rsi+1]; unsigned int
0x1801d449c  mov     [rsp+78h+var_58], r15b; bool
0x1801d44a1  xor     r9d, r9d; unsigned __int16 **
0x1801d44a4  lea     r8, aDualenginepipe; "-DualEnginePipe="
0x1801d44ab  mov     rcx, rdi; pszFirst
0x1801d44ae  call    ?FindOrRemoveCommandArg@@YA_NPEAGKPEBGPEAPEAG_N@Z; FindOrRemoveCommandArg(ushort *,ulong,ushort const *,ushort * *,bool)
0x1801d44b3  mov     dl, 1
0x1801d44b5  test    al, al
0x1801d44b7  jnz     short loc_1801D44BC
0x1801d44b9  mov     dl, r15b
0x1801d44bc  mov     ecx, 1000004Fh
0x1801d44c1  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d44c8  nop     dword ptr [rax+rax+00h]
0x1801d44cd  mov     ebx, eax
0x1801d44cf  test    eax, eax
0x1801d44d1  js      loc_1801D45BC
0x1801d44d7  mov     ecx, 1000001Ah
0x1801d44dc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d44e3  nop     dword ptr [rax+rax+00h]
0x1801d44e8  mov     edx, r15d
0x1801d44eb  mov     dil, al
0x1801d44ee  mov     [rbp+var_38], edx
0x1801d44f1  test    al, al
0x1801d44f3  jz      short loc_1801D453C
0x1801d44f5  cmp     cs:?g_fHangRecovery@@3_NA, r15b; bool g_fHangRecovery
0x1801d44fc  jz      short loc_1801D453C
0x1801d44fe  mov     rcx, cs:?IEVALUE_LCIE_TSEnable@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_LCIE_TSEnable
0x1801d4505  lea     r9, [rbp+var_38]
0x1801d4509  mov     edx, 1
0x1801d450e  mov     [rsp+78h+var_48], r15
0x1801d4513  mov     r8d, edx
0x1801d4516  mov     [rsp+78h+var_50], r15
0x1801d451b  mov     dword ptr [rsp+78h+var_58], 4
0x1801d4523  call    cs:__imp_GetValue
0x1801d452a  nop     dword ptr [rax+rax+00h]
0x1801d452f  mov     ebx, eax
0x1801d4531  test    eax, eax
0x1801d4533  js      loc_1801D45BC
0x1801d4539  mov     edx, [rbp+var_38]
0x1801d453c  mov     ecx, 10000024h
0x1801d4541  call    cs:__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x1801d4548  nop     dword ptr [rax+rax+00h]
0x1801d454d  mov     ebx, eax
0x1801d454f  test    eax, eax
0x1801d4551  js      short loc_1801D45BC
0x1801d4553  mov     ebx, [rbp+var_38]
0x1801d4556  mov     ecx, 10000027h
0x1801d455b  and     ebx, 9
0x1801d455e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d4565  nop     dword ptr [rax+rax+00h]
0x1801d456a  test    al, al
0x1801d456c  jz      short loc_1801D4591
0x1801d456e  test    dil, dil
0x1801d4571  jz      short loc_1801D4591
0x1801d4573  cmp     ebx, 9
0x1801d4576  jnz     short loc_1801D4591
0x1801d4578  mov     dl, 1
0x1801d457a  mov     ecx, 10000028h
0x1801d457f  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1801d4586  nop     dword ptr [rax+rax+00h]
0x1801d458b  mov     ebx, eax
0x1801d458d  test    eax, eax
0x1801d458f  js      short loc_1801D45BC
0x1801d4591  call    cs:__imp_GetCurrentProcessId
0x1801d4598  nop     dword ptr [rax+rax+00h]
0x1801d459d  xor     edx, edx
0x1801d459f  mov     qword ptr [rbp+pszSrch.Data2], r15
  ... truncated ...
```
