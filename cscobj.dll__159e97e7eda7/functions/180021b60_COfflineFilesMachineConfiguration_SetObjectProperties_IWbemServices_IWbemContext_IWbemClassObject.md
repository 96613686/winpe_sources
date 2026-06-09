# COfflineFilesMachineConfiguration::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x180021b60`
- end: `0x18002201b`
- name: `?_SetObjectProperties@COfflineFilesMachineConfiguration@@EEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `1211`
- prototype: `int(COfflineFilesMachineConfiguration *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f5cc`
- `0x1800140c8`
- `0x18001c644`
- `0x18001c700`
- `0x18001ee5c`
- `0x18001ef70`
- `0x18001f1c4`
- `0x18001f22c`
- `0x180021b60`
- `0x180028508`
- `0x1800296a0`
- `0x18002c010`

## string_xrefs

- `0x180021f3b`: `WorkOfflineButtonRemoved`
- `0x180021f64`: `WorkOfflineButtonRemoved`
- `0x180021f87`: `MakeAvailableOfflineButtonRemoved`
- `0x180021fb0`: `MakeAvailableOfflineButtonRemoved`
- `0x180021bd6`: `OfflineFilesCacheEncrypted`
- `0x180021c06`: `OfflineFilesCacheEncrypted`
- `0x180021c70`: `SlowLinkEnabled`
- `0x180021c99`: `SlowLinkEnabled`
- `0x180021d74`: `SlowLinkParams`
- `0x180021ff2`: `IsConfiguredByWMI`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::_SetObjectProperties(
        COfflineFilesMachineConfiguration *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject *a4)
{
  unsigned int v7; // eax
  int v8; // ebx
  int updated; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  struct IWbemContext *v14; // rdx
  struct IWbemServices *v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  struct IWbemContext *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  struct IWbemClassObject *v27; // [rsp+20h] [rbp-78h]
  struct IWbemClassObject *v28; // [rsp+20h] [rbp-78h]
  _WORD v29[52]; // [rsp+30h] [rbp-68h] BYREF

  v7 = (**((__int64 (__fastcall ***)(char *, struct IWbemContext *))this + 2))((char *)this + 16, a3);
  v8 = v7;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 114, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v7);
  }
  if ( v8 >= 0 )
  {
    updated = CSCWmiConfig::UpdateWbemClassObjectProp(L"OfflineFilesCacheEncrypted", 0, a4, 2);
    v8 = updated;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        115,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"OfflineFilesCacheEncrypted",
        updated);
    }
    if ( v8 >= 0 )
    {
      v10 = CSCWmiConfig::UpdateWbemClassObjectProp(L"Enabled", 0, a4, 2);
      v8 = v10;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          116,
          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)L"Enabled",
          v10);
      }
      if ( v8 >= 0 )
      {
        v11 = CSCWmiConfig::UpdateWbemClassObjectProp(L"SlowLinkEnabled", 0, a4, 2);
        v8 = v11;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          WPP_SF_SD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            117,
            (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
            (unsigned int)L"SlowLinkEnabled",
            v11);
        }
        if ( v8 >= 0 )
        {
          v12 = CSCWmiConfig::UpdateWbemClassObjectProp(L"TransparentCachingLatencyThreshold", 0, a4, 2);
          v8 = v12;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_SD(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              118,
              (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
              (unsigned int)L"TransparentCachingLatencyThreshold",
              v12);
          }
          if ( v8 >= 0 )
          {
            v13 = CSCWmiConfig::UpdateWbemClassObjectProp(L"SyncOnCostedNetworkEnabled", 0, a4, 34);
            v8 = v13;
            v15 = (struct IWbemServices *)WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_SD(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                119,
                (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                (unsigned int)L"SyncOnCostedNetworkEnabled",
                v13);
            }
            if ( v8 >= 0 )
            {
              v16 = COfflineFilesMachineConfiguration::UpdateWbemClassObjectSlowLinkParamsProp(v15, v14, a4);
              v8 = v16;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
              {
                WPP_SF_SD(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  120,
                  (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                  (unsigned int)L"SlowLinkParams",
                  v16);
              }
              if ( v8 >= 0 )
              {
                v17 = CSCWmiConfig::UpdateWbemClassObjectProp(L"BackgroundSyncEnabled", 0, a4, 2);
                v8 = v17;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                {
                  WPP_SF_SD(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    121,
                    (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                    (unsigned int)L"BackgroundSyncEnabled",
                    v17);
                }
                if ( v8 >= 0 )
                {
                  v18 = UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesBackgroundSync>(a2, a3, v27);
                  v8 = v18;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                  {
                    WPP_SF_SD(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      122,
                      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                      (unsigned int)L"BackgroundSyncParams",
                      v18);
                  }
                  if ( v8 >= 0 )
                  {
                    v19 = CSCWmiConfig::UpdateWbemClassObjectProp(L"EconomicalAdminPinningEnabled", 0, a4, 2);
                    v8 = v19;
                    v20 = (struct IWbemContext *)WPP_GLOBAL_Control;
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                    {
                      WPP_SF_SD(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        123,
                        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                        (unsigned int)L"EconomicalAdminPinningEnabled",
                        v19);
                    }
                    if ( v8 >= 0 )
                    {
                      v21 = COfflineFilesMachineConfiguration::UpdateWbemClassObjectExcludedFilesTypeProp(v20, a4);
                      v8 = v21;
                      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                      {
                        WPP_SF_SD(
                          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                          124,
                          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                          (unsigned int)L"ExcludedFileTypes",
                          v21);
                      }
                      if ( v8 >= 0 )
                      {
                        v22 = COfflineFilesMachineConfiguration::UpdateWbemClassObjectEnableDiskSpaceLimitProp(a4);
                        v8 = v22;
                        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                        {
                          WPP_SF_SD(
                            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                            125,
                            (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                            (unsigned int)L"DiskSpaceLimitEnabled",
                            v22);
                        }
                        if ( v8 >= 0 )
                        {
                          v23 = UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesDiskSpaceLimit>(a2, a3, v28);
                          v8 = v23;
                          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                          {
                            WPP_SF_SD(
                              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                              126,
                              (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                              (unsigned int)L"DiskSpaceLimitParams",
                              v23);
                          }
                          if ( v8 >= 0 )
                          {
                            v24 = CSCWmiConfig::UpdateWbemClassObjectProp(L"WorkOfflineButtonRemoved", 0, a4, 2);
                            v8 = v24;
                            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                            {
                              WPP_SF_SD(
                                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                127,
                                (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                                (unsigned int)L"WorkOfflineButtonRemoved",
                                v24);
                            }
                            if ( v8 >= 0 )
                            {
                              v25 = CSCWmiConfig::UpdateWbemClassObjectProp(
                                      L"MakeAvailableOfflineButtonRemoved",
                                      0,
                                      a4,
                                      2);
                              v8 = v25;
                              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
                              {
                                WPP_SF_SD(
                                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                  128,
                                  (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                                  (unsigned int)L"MakeAvailableOfflineButtonRemoved",
                                  v25);
                              }
                              if ( v8 >= 0 )
                              {
                                v29[0] = 11;
                                v29[4] = ((unsigned int)GetSettingAuthority(3) != 1) - 1;
                                return (unsigned int)WmiProp_SetProperty(a4, L"IsConfiguredByWMI", v29);
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
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021b60  push    rbx
0x180021b62  push    rbp
0x180021b63  push    rsi
0x180021b64  push    rdi
0x180021b65  push    r12
0x180021b67  push    r13
0x180021b69  push    r14
0x180021b6b  push    r15
0x180021b6d  sub     rsp, 58h
0x180021b71  add     rcx, 10h
0x180021b75  mov     rbp, rdx
0x180021b78  mov     rdx, r8
0x180021b7b  mov     rdi, r9
0x180021b7e  mov     rsi, r8
0x180021b81  mov     rax, [rcx]
0x180021b84  mov     rax, [rax]
0x180021b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b8c  mov     ebx, eax
0x180021b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b95  lea     r12, WPP_GLOBAL_Control
0x180021b9c  lea     r15, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180021ba3  mov     r14d, 4000000h
0x180021ba9  cmp     rcx, r12
0x180021bac  jz      short loc_180021BC8
0x180021bae  test    [rcx+1Ch], r14d
0x180021bb2  jz      short loc_180021BC8
0x180021bb4  mov     rcx, [rcx+10h]
0x180021bb8  mov     edx, 72h ; 'r'
0x180021bbd  mov     r9d, eax
0x180021bc0  mov     r8, r15
0x180021bc3  call    WPP_SF_d
0x180021bc8  test    ebx, ebx
0x180021bca  js      loc_180022008
0x180021bd0  mov     r13d, 2
0x180021bd6  lea     rcx, CSCWMI_STR_PROP_OFFLINEFILESCACHEENCRYPTED; "OfflineFilesCacheEncrypted"
0x180021bdd  mov     r9d, r13d
0x180021be0  mov     r8, rdi
0x180021be3  xor     edx, edx
0x180021be5  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021bea  mov     ebx, eax
0x180021bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bf3  cmp     rcx, r12
0x180021bf6  jz      short loc_180021C19
0x180021bf8  test    [rcx+1Ch], r14d
0x180021bfc  jz      short loc_180021C19
0x180021bfe  mov     rcx, [rcx+10h]
0x180021c02  lea     edx, [r13+71h]
0x180021c06  lea     r9, CSCWMI_STR_PROP_OFFLINEFILESCACHEENCRYPTED; "OfflineFilesCacheEncrypted"
0x180021c0d  mov     dword ptr [rsp+98h+var_78], eax
0x180021c11  mov     r8, r15
0x180021c14  call    WPP_SF_SD
0x180021c19  test    ebx, ebx
0x180021c1b  js      loc_180022008
0x180021c21  mov     r9d, r13d
0x180021c24  lea     rcx, CSCWMI_STR_PROP_ENABLED; "Enabled"
0x180021c2b  mov     r8, rdi
0x180021c2e  xor     edx, edx
0x180021c30  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021c35  mov     ebx, eax
0x180021c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c3e  cmp     rcx, r12
0x180021c41  jz      short loc_180021C65
0x180021c43  test    [rcx+1Ch], r14d
0x180021c47  jz      short loc_180021C65
0x180021c49  mov     rcx, [rcx+10h]
0x180021c4d  lea     r9, CSCWMI_STR_PROP_ENABLED; "Enabled"
0x180021c54  mov     edx, 74h ; 't'
0x180021c59  mov     dword ptr [rsp+98h+var_78], eax
0x180021c5d  mov     r8, r15
0x180021c60  call    WPP_SF_SD
0x180021c65  test    ebx, ebx
0x180021c67  js      loc_180022008
0x180021c6d  mov     r9d, r13d
0x180021c70  lea     rcx, CSCWMI_STR_PROP_SLOWLINKENABLED; "SlowLinkEnabled"
0x180021c77  mov     r8, rdi
0x180021c7a  xor     edx, edx
0x180021c7c  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021c81  mov     ebx, eax
0x180021c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c8a  cmp     rcx, r12
0x180021c8d  jz      short loc_180021CB1
0x180021c8f  test    [rcx+1Ch], r14d
0x180021c93  jz      short loc_180021CB1
0x180021c95  mov     rcx, [rcx+10h]
0x180021c99  lea     r9, CSCWMI_STR_PROP_SLOWLINKENABLED; "SlowLinkEnabled"
0x180021ca0  mov     edx, 75h ; 'u'
0x180021ca5  mov     dword ptr [rsp+98h+var_78], eax
0x180021ca9  mov     r8, r15
0x180021cac  call    WPP_SF_SD
0x180021cb1  test    ebx, ebx
0x180021cb3  js      loc_180022008
0x180021cb9  mov     r9d, r13d
0x180021cbc  lea     rcx, CSCWMI_STR_PROP_TRANSPARENTCACHINGLATENCYTHRESHOLD; "TransparentCachingLatencyThreshold"
0x180021cc3  mov     r8, rdi
0x180021cc6  xor     edx, edx
0x180021cc8  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021ccd  mov     ebx, eax
0x180021ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cd6  cmp     rcx, r12
0x180021cd9  jz      short loc_180021CFD
0x180021cdb  test    [rcx+1Ch], r14d
0x180021cdf  jz      short loc_180021CFD
0x180021ce1  mov     rcx, [rcx+10h]
0x180021ce5  lea     r9, CSCWMI_STR_PROP_TRANSPARENTCACHINGLATENCYTHRESHOLD; "TransparentCachingLatencyThreshold"
0x180021cec  mov     edx, 76h ; 'v'
0x180021cf1  mov     dword ptr [rsp+98h+var_78], eax
0x180021cf5  mov     r8, r15
0x180021cf8  call    WPP_SF_SD
0x180021cfd  test    ebx, ebx
0x180021cff  js      loc_180022008
0x180021d05  mov     r9d, 22h ; '"'
0x180021d0b  lea     rcx, CSCWMI_STR_PROP_SYNCONCOSTEDNETWORKENABLED; "SyncOnCostedNetworkEnabled"
0x180021d12  mov     r8, rdi
0x180021d15  xor     edx, edx
0x180021d17  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021d1c  mov     ebx, eax
0x180021d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d25  cmp     rcx, r12
0x180021d28  jz      short loc_180021D4C
0x180021d2a  test    [rcx+1Ch], r14d
0x180021d2e  jz      short loc_180021D4C
0x180021d30  mov     rcx, [rcx+10h]
0x180021d34  lea     r9, CSCWMI_STR_PROP_SYNCONCOSTEDNETWORKENABLED; "SyncOnCostedNetworkEnabled"
0x180021d3b  mov     edx, 77h ; 'w'
0x180021d40  mov     dword ptr [rsp+98h+var_78], eax
0x180021d44  mov     r8, r15
0x180021d47  call    WPP_SF_SD
0x180021d4c  test    ebx, ebx
0x180021d4e  js      loc_180022008
0x180021d54  mov     r8, rdi; struct IWbemClassObject *
0x180021d57  call    ?UpdateWbemClassObjectSlowLinkParamsProp@COfflineFilesMachineConfiguration@@CAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z; COfflineFilesMachineConfiguration::UpdateWbemClassObjectSlowLinkParamsProp(IWbemServices *,IWbemContext *,IWbemClassObject *)
0x180021d5c  mov     ebx, eax
0x180021d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d65  cmp     rcx, r12
0x180021d68  jz      short loc_180021D8C
0x180021d6a  test    [rcx+1Ch], r14d
0x180021d6e  jz      short loc_180021D8C
0x180021d70  mov     rcx, [rcx+10h]
0x180021d74  lea     r9, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x180021d7b  mov     edx, 78h ; 'x'
0x180021d80  mov     dword ptr [rsp+98h+var_78], eax
0x180021d84  mov     r8, r15
0x180021d87  call    WPP_SF_SD
0x180021d8c  test    ebx, ebx
0x180021d8e  js      loc_180022008
0x180021d94  mov     r9d, r13d
0x180021d97  lea     rcx, CSCWMI_STR_PROP_BACKGROUNDSYNCENABLED; "BackgroundSyncEnabled"
0x180021d9e  mov     r8, rdi
0x180021da1  xor     edx, edx
0x180021da3  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021da8  mov     ebx, eax
0x180021daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021db1  cmp     rcx, r12
0x180021db4  jz      short loc_180021DD8
0x180021db6  test    [rcx+1Ch], r14d
0x180021dba  jz      short loc_180021DD8
0x180021dbc  mov     rcx, [rcx+10h]
0x180021dc0  lea     r9, CSCWMI_STR_PROP_BACKGROUNDSYNCENABLED; "BackgroundSyncEnabled"
0x180021dc7  mov     edx, 79h ; 'y'
0x180021dcc  mov     dword ptr [rsp+98h+var_78], eax; struct IWbemClassObject *
0x180021dd0  mov     r8, r15
0x180021dd3  call    WPP_SF_SD
0x180021dd8  test    ebx, ebx
0x180021dda  js      loc_180022008
0x180021de0  mov     r8, rdi
0x180021de3  mov     rdx, rsi; struct IWbemContext *
0x180021de6  mov     rcx, rbp; struct IWbemServices *
0x180021de9  call    ??$UpdateWbemClassObjectPropertyObject@VCWmiOfflineFilesBackgroundSync@@@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@PEBGPEAX@Z; UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesBackgroundSync>(IWbemServices *,IWbemContext *,IWbemClassObject *,ushort const *,void *)
0x180021dee  mov     ebx, eax
0x180021df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021df7  cmp     rcx, r12
0x180021dfa  jz      short loc_180021E1E
0x180021dfc  test    [rcx+1Ch], r14d
0x180021e00  jz      short loc_180021E1E
0x180021e02  mov     rcx, [rcx+10h]
0x180021e06  lea     r9, CSCWMI_STR_PROP_BACKGROUNDSYNCPARAMS; "BackgroundSyncParams"
0x180021e0d  mov     edx, 7Ah ; 'z'
0x180021e12  mov     dword ptr [rsp+98h+var_78], eax
0x180021e16  mov     r8, r15
0x180021e19  call    WPP_SF_SD
0x180021e1e  test    ebx, ebx
0x180021e20  js      loc_180022008
0x180021e26  mov     r9d, r13d
0x180021e29  lea     rcx, CSCWMI_STR_PROP_ECONOMICALADMINPINNINGENABLED; "EconomicalAdminPinningEnabled"
0x180021e30  mov     r8, rdi
0x180021e33  xor     edx, edx
0x180021e35  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021e3a  mov     ebx, eax
0x180021e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e43  cmp     rcx, r12
0x180021e46  jz      short loc_180021E6A
0x180021e48  test    [rcx+1Ch], r14d
0x180021e4c  jz      short loc_180021E6A
0x180021e4e  mov     rcx, [rcx+10h]
0x180021e52  lea     r9, CSCWMI_STR_PROP_ECONOMICALADMINPINNINGENABLED; "EconomicalAdminPinningEnabled"
0x180021e59  mov     edx, 7Bh ; '{'
0x180021e5e  mov     dword ptr [rsp+98h+var_78], eax
0x180021e62  mov     r8, r15
0x180021e65  call    WPP_SF_SD
0x180021e6a  test    ebx, ebx
0x180021e6c  js      loc_180022008
0x180021e72  mov     rdx, rdi; struct IWbemClassObject *
0x180021e75  call    ?UpdateWbemClassObjectExcludedFilesTypeProp@COfflineFilesMachineConfiguration@@CAJPEAUIWbemContext@@PEAUIWbemClassObject@@@Z; COfflineFilesMachineConfiguration::UpdateWbemClassObjectExcludedFilesTypeProp(IWbemContext *,IWbemClassObject *)
0x180021e7a  mov     ebx, eax
0x180021e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e83  cmp     rcx, r12
0x180021e86  jz      short loc_180021EAA
0x180021e88  test    [rcx+1Ch], r14d
0x180021e8c  jz      short loc_180021EAA
0x180021e8e  mov     rcx, [rcx+10h]
0x180021e92  lea     r9, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x180021e99  mov     edx, 7Ch ; '|'
0x180021e9e  mov     dword ptr [rsp+98h+var_78], eax
0x180021ea2  mov     r8, r15
0x180021ea5  call    WPP_SF_SD
0x180021eaa  test    ebx, ebx
0x180021eac  js      loc_180022008
0x180021eb2  mov     rcx, rdi; struct IWbemClassObject *
0x180021eb5  call    ?UpdateWbemClassObjectEnableDiskSpaceLimitProp@COfflineFilesMachineConfiguration@@CAJPEAUIWbemClassObject@@@Z; COfflineFilesMachineConfiguration::UpdateWbemClassObjectEnableDiskSpaceLimitProp(IWbemClassObject *)
0x180021eba  mov     ebx, eax
0x180021ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ec3  cmp     rcx, r12
0x180021ec6  jz      short loc_180021EEA
0x180021ec8  test    [rcx+1Ch], r14d
0x180021ecc  jz      short loc_180021EEA
0x180021ece  mov     rcx, [rcx+10h]
0x180021ed2  lea     r9, CSCWMI_STR_PROP_DISKSPACELIMITENABLED; "DiskSpaceLimitEnabled"
0x180021ed9  mov     edx, 7Dh ; '}'
0x180021ede  mov     dword ptr [rsp+98h+var_78], eax; struct IWbemClassObject *
0x180021ee2  mov     r8, r15
0x180021ee5  call    WPP_SF_SD
0x180021eea  test    ebx, ebx
0x180021eec  js      loc_180022008
0x180021ef2  mov     r8, rdi
0x180021ef5  mov     rdx, rsi; struct IWbemContext *
0x180021ef8  mov     rcx, rbp; struct IWbemServices *
0x180021efb  call    ??$UpdateWbemClassObjectPropertyObject@VCWmiOfflineFilesDiskSpaceLimit@@@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@PEBGPEAX@Z; UpdateWbemClassObjectPropertyObject<CWmiOfflineFilesDiskSpaceLimit>(IWbemServices *,IWbemContext *,IWbemClassObject *,ushort const *,void *)
0x180021f00  mov     ebx, eax
0x180021f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f09  cmp     rcx, r12
0x180021f0c  jz      short loc_180021F30
0x180021f0e  test    [rcx+1Ch], r14d
0x180021f12  jz      short loc_180021F30
0x180021f14  mov     rcx, [rcx+10h]
0x180021f18  lea     r9, CSCWMI_STR_PROP_DISKSPACELIMITPARAMS; "DiskSpaceLimitParams"
0x180021f1f  mov     edx, 7Eh ; '~'
0x180021f24  mov     dword ptr [rsp+98h+var_78], eax
0x180021f28  mov     r8, r15
0x180021f2b  call    WPP_SF_SD
0x180021f30  test    ebx, ebx
0x180021f32  js      loc_180022008
0x180021f38  mov     r9d, r13d
0x180021f3b  lea     rcx, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x180021f42  mov     r8, rdi
0x180021f45  xor     edx, edx
0x180021f47  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021f4c  mov     ebx, eax
0x180021f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f55  cmp     rcx, r12
0x180021f58  jz      short loc_180021F7C
0x180021f5a  test    [rcx+1Ch], r14d
0x180021f5e  jz      short loc_180021F7C
0x180021f60  mov     rcx, [rcx+10h]
0x180021f64  lea     r9, CSCWMI_STR_PROP_WORKOFFLINEBUTTONREMOVED; "WorkOfflineButtonRemoved"
0x180021f6b  mov     edx, 7Fh
0x180021f70  mov     dword ptr [rsp+98h+var_78], eax
0x180021f74  mov     r8, r15
0x180021f77  call    WPP_SF_SD
0x180021f7c  test    ebx, ebx
0x180021f7e  js      loc_180022008
0x180021f84  mov     r9d, r13d
0x180021f87  lea     rcx, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x180021f8e  mov     r8, rdi
0x180021f91  xor     edx, edx
0x180021f93  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x180021f98  mov     ebx, eax
0x180021f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fa1  cmp     rcx, r12
0x180021fa4  jz      short loc_180021FC8
0x180021fa6  test    [rcx+1Ch], r14d
0x180021faa  jz      short loc_180021FC8
0x180021fac  mov     rcx, [rcx+10h]
0x180021fb0  lea     r9, CSCWMI_STR_PROP_MAKEAVAILABLEOFFLINEBUTTONREMOVED; "MakeAvailableOfflineButtonRemoved"
0x180021fb7  mov     edx, 80h
0x180021fbc  mov     dword ptr [rsp+98h+var_78], eax
0x180021fc0  mov     r8, r15
0x180021fc3  call    WPP_SF_SD
0x180021fc8  test    ebx, ebx
0x180021fca  js      short loc_180022008
0x180021fcc  mov     ecx, 3
0x180021fd1  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x180021fd6  mov     ecx, 0Bh
0x180021fdb  lea     r8, [rsp+98h+var_68]
0x180021fe0  mov     [rsp+98h+var_68], cx
0x180021fe5  xor     ecx, ecx
0x180021fe7  lea     edx, [rcx+1]
0x180021fea  cmp     eax, edx
0x180021fec  setnz   cl
0x180021fef  sub     cx, dx
0x180021ff2  lea     rdx, CSCWMI_STR_PROP_ISCONFIGUREDBYWMI; "IsConfiguredByWMI"
  ... truncated ...
```
