# COfflineFilesMachineConfiguration::_Put(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x18001f820`
- end: `0x18001fda4`
- name: `?_Put@COfflineFilesMachineConfiguration@@EEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `1412`
- prototype: `int(COfflineFilesMachineConfiguration *__hidden this, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ac4`
- `0x18000f5cc`
- `0x1800140c8`
- `0x18001c4ec`
- `0x18001c598`
- `0x18001e4f8`
- `0x18001e964`
- `0x18001e9b8`
- `0x18001f820`
- `0x18002c010`

## string_xrefs

- `0x18001fc66`: `WorkOfflineButtonRemoved`
- `0x18001fc95`: `WorkOfflineButtonRemoved`
- `0x18001fcba`: `MakeAvailableOfflineButtonRemoved`
- `0x18001fce3`: `MakeAvailableOfflineButtonRemoved`
- `0x18001f8a0`: `OfflineFilesCacheEncrypted`
- `0x18001f8c9`: `OfflineFilesCacheEncrypted`
- `0x18001f94c`: `SlowLinkEnabled`
- `0x18001f975`: `SlowLinkEnabled`
- `0x18001fa12`: `SlowLinkParams`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::_Put(
        COfflineFilesMachineConfiguration *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5,
        struct IWbemServices *a6)
{
  unsigned int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  struct IWbemServices *v17; // rdx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // r8
  int v25; // eax

  v10 = (**((__int64 (__fastcall ***)(char *, struct IWbemContext *))this + 2))((char *)this + 16, a4);
  v11 = v10;
  v12 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 129, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v10);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 >= 0 )
  {
    v13 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"OfflineFilesCacheEncrypted", 0, (__int64)a2, 34);
    v11 = v13;
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        130,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"OfflineFilesCacheEncrypted",
        v13);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v11 >= 0 )
    {
      v14 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"Enabled", 0, (__int64)a2, 34);
      v11 = v14;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          131,
          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)L"Enabled",
          v14);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v11 >= 0 )
      {
        v15 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"SlowLinkEnabled", 0, (__int64)a2, 34);
        v11 = v15;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_SD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            132,
            (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
            (unsigned int)L"SlowLinkEnabled",
            v15);
          v12 = WPP_GLOBAL_Control;
        }
        if ( v11 >= 0 )
        {
          v16 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"SyncOnCostedNetworkEnabled", 0, (__int64)a2, 34);
          v11 = v16;
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_SD(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              133,
              (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
              (unsigned int)L"SyncOnCostedNetworkEnabled",
              v16);
            v12 = WPP_GLOBAL_Control;
          }
          if ( v11 >= 0 )
          {
            v18 = COfflineFilesMachineConfiguration::UpdateOrRemoveWMISlowLinkParamsProperty(a2, v17);
            v11 = v18;
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_SD(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                134,
                (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                (unsigned int)L"SlowLinkParams",
                v18);
              v12 = WPP_GLOBAL_Control;
            }
            if ( v11 >= 0 )
            {
              v19 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"BackgroundSyncEnabled", 0, (__int64)a2, 34);
              v11 = v19;
              v12 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
              {
                WPP_SF_SD(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  135,
                  (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                  (unsigned int)L"BackgroundSyncEnabled",
                  v19);
                v12 = WPP_GLOBAL_Control;
              }
              if ( v11 >= 0 )
              {
                v11 = UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesBackgroundSync>(a2, a3, a4, a5, a6);
                v12 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                {
                  WPP_SF_SD(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    136,
                    (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                    (unsigned int)L"BackgroundSyncParams",
                    v11);
                  v12 = WPP_GLOBAL_Control;
                }
                if ( v11 >= 0 )
                {
                  v11 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(
                          L"EconomicalAdminPinningEnabled",
                          0,
                          (__int64)a2,
                          34);
                  v12 = WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                  {
                    WPP_SF_SD(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      137,
                      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                      (unsigned int)L"EconomicalAdminPinningEnabled",
                      v11);
                    v12 = WPP_GLOBAL_Control;
                  }
                  if ( v11 >= 0 )
                  {
                    v11 = COfflineFilesMachineConfiguration::UpdateOrRemoveWMIExcludeFileTypesProperty(a2);
                    v12 = WPP_GLOBAL_Control;
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                    {
                      WPP_SF_SD(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        138,
                        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                        (unsigned int)L"ExcludedFileTypes",
                        v11);
                      v12 = WPP_GLOBAL_Control;
                    }
                    if ( v11 >= 0 )
                    {
                      v11 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"DiskSpaceLimitEnabled", 0, (__int64)a2, 34);
                      v12 = WPP_GLOBAL_Control;
                      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                      {
                        WPP_SF_SD(
                          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                          139,
                          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                          (unsigned int)L"DiskSpaceLimitEnabled",
                          v11);
                        v12 = WPP_GLOBAL_Control;
                      }
                      if ( v11 >= 0 )
                      {
                        v20 = UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesDiskSpaceLimit>(a2, a3, a4, a5, a6);
                        v11 = v20;
                        v12 = WPP_GLOBAL_Control;
                        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                        {
                          WPP_SF_SD(
                            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                            140,
                            (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                            (unsigned int)L"DiskSpaceLimitParams",
                            v20);
                          v12 = WPP_GLOBAL_Control;
                        }
                        if ( v11 >= 0 )
                        {
                          v21 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(
                                  L"WorkOfflineButtonRemoved",
                                  0,
                                  (__int64)a2,
                                  34);
                          v11 = v21;
                          v12 = WPP_GLOBAL_Control;
                          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                          {
                            WPP_SF_SD(
                              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                              141,
                              (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                              (unsigned int)L"WorkOfflineButtonRemoved",
                              v21);
                            v12 = WPP_GLOBAL_Control;
                          }
                          if ( v11 >= 0 )
                          {
                            v22 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(
                                    L"MakeAvailableOfflineButtonRemoved",
                                    0,
                                    (__int64)a2,
                                    34);
                            v11 = v22;
                            v12 = WPP_GLOBAL_Control;
                            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                            {
                              WPP_SF_SD(
                                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                142,
                                (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                                (unsigned int)L"MakeAvailableOfflineButtonRemoved",
                                v22);
                              v12 = WPP_GLOBAL_Control;
                            }
                            if ( v11 >= 0 )
                            {
                              v23 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(
                                      L"TransparentCachingLatencyThreshold",
                                      0,
                                      (__int64)a2,
                                      34);
                              v11 = v23;
                              v12 = WPP_GLOBAL_Control;
                              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                              {
                                WPP_SF_SD(
                                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                  143,
                                  (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                                  (unsigned int)L"TransparentCachingLatencyThreshold",
                                  v23);
                                v12 = WPP_GLOBAL_Control;
                              }
                              if ( v11 >= 0 )
                              {
                                v25 = ApplyCscPolicy(0, *((void **)this + 6), v24);
                                v12 = WPP_GLOBAL_Control;
                                v11 = v25;
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
  if ( (_UNKNOWN *)v12 != &WPP_GLOBAL_Control && (*(_DWORD *)(v12 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v12 + 16), 144, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001f820  push    rbx
0x18001f822  push    rbp
0x18001f823  push    rsi
0x18001f824  push    rdi
0x18001f825  push    r12
0x18001f827  push    r13
0x18001f829  push    r14
0x18001f82b  push    r15
0x18001f82d  sub     rsp, 48h
0x18001f831  mov     r15, rcx
0x18001f834  mov     rdi, rdx
0x18001f837  add     rcx, 10h
0x18001f83b  mov     rdx, r9
0x18001f83e  mov     rbp, r9
0x18001f841  mov     r14d, r8d
0x18001f844  mov     rax, [rcx]
0x18001f847  mov     rax, [rax]
0x18001f84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84f  mov     ebx, eax
0x18001f851  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f858  lea     rsi, WPP_GLOBAL_Control
0x18001f85f  lea     r13, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001f866  mov     r12d, 4000000h
0x18001f86c  cmp     rcx, rsi
0x18001f86f  jz      short loc_18001F892
0x18001f871  test    [rcx+1Ch], r12d
0x18001f875  jz      short loc_18001F892
0x18001f877  mov     rcx, [rcx+10h]
0x18001f87b  mov     edx, 81h
0x18001f880  mov     r9d, eax
0x18001f883  mov     r8, r13
0x18001f886  call    WPP_SF_d
0x18001f88b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f892  test    ebx, ebx
0x18001f894  js      loc_18001FD72
0x18001f89a  mov     r9d, 22h ; '"'
0x18001f8a0  lea     rcx, CSCWMI_STR_PROP_OFFLINEFILESCACHEENCRYPTED; "OfflineFilesCacheEncrypted"
0x18001f8a7  mov     r8, rdi
0x18001f8aa  xor     edx, edx
0x18001f8ac  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001f8b1  mov     ebx, eax
0x18001f8b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8ba  cmp     rcx, rsi
0x18001f8bd  jz      short loc_18001F8E8
0x18001f8bf  test    [rcx+1Ch], r12d
0x18001f8c3  jz      short loc_18001F8E8
0x18001f8c5  mov     rcx, [rcx+10h]
0x18001f8c9  lea     r9, CSCWMI_STR_PROP_OFFLINEFILESCACHEENCRYPTED; "OfflineFilesCacheEncrypted"
0x18001f8d0  mov     edx, 82h
0x18001f8d5  mov     dword ptr [rsp+88h+var_68], eax
0x18001f8d9  mov     r8, r13
0x18001f8dc  call    WPP_SF_SD
0x18001f8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8e8  test    ebx, ebx
0x18001f8ea  js      loc_18001FD72
0x18001f8f0  mov     r9d, 22h ; '"'
0x18001f8f6  lea     rcx, CSCWMI_STR_PROP_ENABLED; "Enabled"
0x18001f8fd  mov     r8, rdi
0x18001f900  xor     edx, edx
0x18001f902  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001f907  mov     ebx, eax
0x18001f909  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f910  cmp     rcx, rsi
0x18001f913  jz      short loc_18001F93E
0x18001f915  test    [rcx+1Ch], r12d
0x18001f919  jz      short loc_18001F93E
0x18001f91b  mov     rcx, [rcx+10h]
0x18001f91f  lea     r9, CSCWMI_STR_PROP_ENABLED; "Enabled"
0x18001f926  mov     edx, 83h
0x18001f92b  mov     dword ptr [rsp+88h+var_68], eax
0x18001f92f  mov     r8, r13
0x18001f932  call    WPP_SF_SD
0x18001f937  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f93e  test    ebx, ebx
0x18001f940  js      loc_18001FD72
0x18001f946  mov     r9d, 22h ; '"'
0x18001f94c  lea     rcx, CSCWMI_STR_PROP_SLOWLINKENABLED; "SlowLinkEnabled"
0x18001f953  mov     r8, rdi
0x18001f956  xor     edx, edx
0x18001f958  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001f95d  mov     ebx, eax
0x18001f95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f966  cmp     rcx, rsi
0x18001f969  jz      short loc_18001F994
0x18001f96b  test    [rcx+1Ch], r12d
0x18001f96f  jz      short loc_18001F994
0x18001f971  mov     rcx, [rcx+10h]
0x18001f975  lea     r9, CSCWMI_STR_PROP_SLOWLINKENABLED; "SlowLinkEnabled"
0x18001f97c  mov     edx, 84h
0x18001f981  mov     dword ptr [rsp+88h+var_68], eax
0x18001f985  mov     r8, r13
0x18001f988  call    WPP_SF_SD
0x18001f98d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f994  test    ebx, ebx
0x18001f996  js      loc_18001FD72
0x18001f99c  mov     r9d, 22h ; '"'
0x18001f9a2  lea     rcx, CSCWMI_STR_PROP_SYNCONCOSTEDNETWORKENABLED; "SyncOnCostedNetworkEnabled"
0x18001f9a9  mov     r8, rdi
0x18001f9ac  xor     edx, edx
0x18001f9ae  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001f9b3  mov     ebx, eax
0x18001f9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9bc  cmp     rcx, rsi
0x18001f9bf  jz      short loc_18001F9EA
0x18001f9c1  test    [rcx+1Ch], r12d
0x18001f9c5  jz      short loc_18001F9EA
0x18001f9c7  mov     rcx, [rcx+10h]
0x18001f9cb  lea     r9, CSCWMI_STR_PROP_SYNCONCOSTEDNETWORKENABLED; "SyncOnCostedNetworkEnabled"
0x18001f9d2  mov     edx, 85h
0x18001f9d7  mov     dword ptr [rsp+88h+var_68], eax
0x18001f9db  mov     r8, r13
0x18001f9de  call    WPP_SF_SD
0x18001f9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9ea  test    ebx, ebx
0x18001f9ec  js      loc_18001FD72
0x18001f9f2  mov     rcx, rdi; struct IWbemClassObject *
0x18001f9f5  call    ?UpdateOrRemoveWMISlowLinkParamsProperty@COfflineFilesMachineConfiguration@@CAJPEAUIWbemClassObject@@PEAUIWbemServices@@@Z; COfflineFilesMachineConfiguration::UpdateOrRemoveWMISlowLinkParamsProperty(IWbemClassObject *,IWbemServices *)
0x18001f9fa  mov     ebx, eax
0x18001f9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa03  cmp     rcx, rsi
0x18001fa06  jz      short loc_18001FA31
0x18001fa08  test    [rcx+1Ch], r12d
0x18001fa0c  jz      short loc_18001FA31
0x18001fa0e  mov     rcx, [rcx+10h]
0x18001fa12  lea     r9, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001fa19  mov     edx, 86h
0x18001fa1e  mov     dword ptr [rsp+88h+var_68], eax
0x18001fa22  mov     r8, r13
0x18001fa25  call    WPP_SF_SD
0x18001fa2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa31  test    ebx, ebx
0x18001fa33  js      loc_18001FD72
0x18001fa39  mov     r9d, 22h ; '"'
0x18001fa3f  lea     rcx, CSCWMI_STR_PROP_BACKGROUNDSYNCENABLED; "BackgroundSyncEnabled"
0x18001fa46  mov     r8, rdi
0x18001fa49  xor     edx, edx
0x18001fa4b  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fa50  mov     ebx, eax
0x18001fa52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa59  cmp     rcx, rsi
0x18001fa5c  jz      short loc_18001FA87
0x18001fa5e  test    [rcx+1Ch], r12d
0x18001fa62  jz      short loc_18001FA87
0x18001fa64  mov     rcx, [rcx+10h]
0x18001fa68  lea     r9, CSCWMI_STR_PROP_BACKGROUNDSYNCENABLED; "BackgroundSyncEnabled"
0x18001fa6f  mov     edx, 87h
0x18001fa74  mov     dword ptr [rsp+88h+var_68], eax
0x18001fa78  mov     r8, r13
0x18001fa7b  call    WPP_SF_SD
0x18001fa80  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa87  test    ebx, ebx
0x18001fa89  js      loc_18001FD72
0x18001fa8f  mov     rsi, [rsp+88h+arg_28]
0x18001fa97  mov     r8, rbp
0x18001fa9a  mov     r9, [rsp+88h+arg_20]
0x18001faa2  mov     edx, r14d
0x18001faa5  mov     rcx, rdi
0x18001faa8  mov     [rsp+88h+var_68], rsi
0x18001faad  call    ??$UpdateOrRemoveWMIPropertiesFromObject@VCWmiOfflineFilesBackgroundSync@@@@YAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@PEBGPEAX@Z; UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesBackgroundSync>(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *,ushort const *,void *)
0x18001fab2  mov     ebx, eax
0x18001fab4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fabb  lea     rax, WPP_GLOBAL_Control
0x18001fac2  cmp     rcx, rax
0x18001fac5  jz      short loc_18001FAF0
0x18001fac7  test    [rcx+1Ch], r12d
0x18001facb  jz      short loc_18001FAF0
0x18001facd  mov     rcx, [rcx+10h]
0x18001fad1  lea     r9, CSCWMI_STR_PROP_BACKGROUNDSYNCPARAMS; "BackgroundSyncParams"
0x18001fad8  mov     edx, 88h
0x18001fadd  mov     dword ptr [rsp+88h+var_68], ebx
0x18001fae1  mov     r8, r13
0x18001fae4  call    WPP_SF_SD
0x18001fae9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faf0  test    ebx, ebx
0x18001faf2  js      loc_18001FD6B
0x18001faf8  mov     r9d, 22h ; '"'
0x18001fafe  lea     rcx, CSCWMI_STR_PROP_ECONOMICALADMINPINNINGENABLED; "EconomicalAdminPinningEnabled"
0x18001fb05  mov     r8, rdi
0x18001fb08  xor     edx, edx
0x18001fb0a  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fb0f  mov     ebx, eax
0x18001fb11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb18  lea     rax, WPP_GLOBAL_Control
0x18001fb1f  cmp     rcx, rax
0x18001fb22  jz      short loc_18001FB4D
0x18001fb24  test    [rcx+1Ch], r12d
0x18001fb28  jz      short loc_18001FB4D
0x18001fb2a  mov     rcx, [rcx+10h]
0x18001fb2e  lea     r9, CSCWMI_STR_PROP_ECONOMICALADMINPINNINGENABLED; "EconomicalAdminPinningEnabled"
0x18001fb35  mov     edx, 89h
0x18001fb3a  mov     dword ptr [rsp+88h+var_68], ebx
0x18001fb3e  mov     r8, r13
0x18001fb41  call    WPP_SF_SD
0x18001fb46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb4d  test    ebx, ebx
0x18001fb4f  js      loc_18001FD6B
0x18001fb55  mov     rcx, rdi; struct IWbemClassObject *
0x18001fb58  call    ?UpdateOrRemoveWMIExcludeFileTypesProperty@COfflineFilesMachineConfiguration@@CAJPEAUIWbemClassObject@@@Z; COfflineFilesMachineConfiguration::UpdateOrRemoveWMIExcludeFileTypesProperty(IWbemClassObject *)
0x18001fb5d  mov     ebx, eax
0x18001fb5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb66  lea     rax, WPP_GLOBAL_Control
0x18001fb6d  cmp     rcx, rax
0x18001fb70  jz      short loc_18001FB9B
0x18001fb72  test    [rcx+1Ch], r12d
0x18001fb76  jz      short loc_18001FB9B
0x18001fb78  mov     rcx, [rcx+10h]
0x18001fb7c  lea     r9, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x18001fb83  mov     edx, 8Ah
0x18001fb88  mov     dword ptr [rsp+88h+var_68], ebx
0x18001fb8c  mov     r8, r13
0x18001fb8f  call    WPP_SF_SD
0x18001fb94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb9b  test    ebx, ebx
0x18001fb9d  js      loc_18001FD6B
0x18001fba3  mov     r9d, 22h ; '"'
0x18001fba9  lea     rcx, CSCWMI_STR_PROP_DISKSPACELIMITENABLED; "DiskSpaceLimitEnabled"
0x18001fbb0  mov     r8, rdi
0x18001fbb3  xor     edx, edx
0x18001fbb5  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fbba  mov     ebx, eax
0x18001fbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbc3  lea     rax, WPP_GLOBAL_Control
0x18001fbca  cmp     rcx, rax
0x18001fbcd  jz      short loc_18001FBF8
0x18001fbcf  test    [rcx+1Ch], r12d
0x18001fbd3  jz      short loc_18001FBF8
0x18001fbd5  mov     rcx, [rcx+10h]
0x18001fbd9  lea     r9, CSCWMI_STR_PROP_DISKSPACELIMITENABLED; "DiskSpaceLimitEnabled"
0x18001fbe0  mov     edx, 8Bh
0x18001fbe5  mov     dword ptr [rsp+88h+var_68], ebx
0x18001fbe9  mov     r8, r13
0x18001fbec  call    WPP_SF_SD
0x18001fbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbf8  test    ebx, ebx
0x18001fbfa  js      loc_18001FD6B
0x18001fc00  mov     r9, [rsp+88h+arg_20]
0x18001fc08  mov     r8, rbp
0x18001fc0b  mov     edx, r14d
0x18001fc0e  mov     [rsp+88h+var_68], rsi
0x18001fc13  mov     rcx, rdi
0x18001fc16  call    ??$UpdateOrRemoveWMIPropertiesFromObject@VCWmiOfflineFilesDiskSpaceLimit@@@@YAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@PEBGPEAX@Z; UpdateOrRemoveWMIPropertiesFromObject<CWmiOfflineFilesDiskSpaceLimit>(IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *,ushort const *,void *)
0x18001fc1b  mov     ebx, eax
0x18001fc1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc24  lea     rsi, WPP_GLOBAL_Control
0x18001fc2b  cmp     rcx, rsi
0x18001fc2e  jz      short loc_18001FC59
0x18001fc30  test    [rcx+1Ch], r12d
0x18001fc34  jz      short loc_18001FC59
0x18001fc36  mov     rcx, [rcx+10h]
0x18001fc3a  lea     r9, CSCWMI_STR_PROP_DISKSPACELIMITPARAMS; "DiskSpaceLimitParams"
0x18001fc41  mov     edx, 8Ch
0x18001fc46  mov     dword ptr [rsp+88h+var_68], eax
0x18001fc4a  mov     r8, r13
0x18001fc4d  call    WPP_SF_SD
0x18001fc52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc59  test    ebx, ebx
0x18001fc5b  js      loc_18001FD72
0x18001fc61  mov     ebp, 22h ; '"'
0x18001fc66  lea     rcx, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x18001fc6d  mov     r9d, ebp
0x18001fc70  mov     r8, rdi
0x18001fc73  xor     edx, edx
0x18001fc75  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fc7a  mov     ebx, eax
0x18001fc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc83  cmp     rcx, rsi
0x18001fc86  jz      short loc_18001FCAF
0x18001fc88  test    [rcx+1Ch], r12d
0x18001fc8c  jz      short loc_18001FCAF
0x18001fc8e  mov     rcx, [rcx+10h]
0x18001fc92  lea     edx, [rbp+6Bh]
0x18001fc95  lea     r9, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x18001fc9c  mov     dword ptr [rsp+88h+var_68], eax
0x18001fca0  mov     r8, r13
0x18001fca3  call    WPP_SF_SD
0x18001fca8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcaf  test    ebx, ebx
0x18001fcb1  js      loc_18001FD72
0x18001fcb7  mov     r9d, ebp
0x18001fcba  lea     rcx, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x18001fcc1  mov     r8, rdi
0x18001fcc4  xor     edx, edx
0x18001fcc6  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001fccb  mov     ebx, eax
0x18001fccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcd4  cmp     rcx, rsi
0x18001fcd7  jz      short loc_18001FD02
0x18001fcd9  test    [rcx+1Ch], r12d
0x18001fcdd  jz      short loc_18001FD02
0x18001fcdf  mov     rcx, [rcx+10h]
0x18001fce3  lea     r9, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x18001fcea  mov     edx, 8Eh
0x18001fcef  mov     dword ptr [rsp+88h+var_68], eax
0x18001fcf3  mov     r8, r13
0x18001fcf6  call    WPP_SF_SD
0x18001fcfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd02  test    ebx, ebx
0x18001fd04  js      short loc_18001FD72
0x18001fd06  mov     r9d, ebp
0x18001fd09  lea     rcx, CSCWMI_STR_PROP_TRANSPARENTCACHINGLATENCYTHRESHOLD; "TransparentCachingLatencyThreshold"
  ... truncated ...
```
