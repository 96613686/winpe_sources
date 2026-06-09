# CConfigurationSettings::Initialise(void)

- ea: `0x140005fc8`
- end: `0x1400068b2`
- name: `?Initialise@CConfigurationSettings@@AEAAXXZ`
- size: `2282`
- prototype: `void __fastcall(CConfigurationSettings *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x140006bf0`

## callees

- `0x140005a94`
- `0x140005f20`
- `0x140005f44`
- `0x140005f74`
- `0x140005fc8`
- `0x1400068b8`
- `0x140006980`
- `0x140057f64`

## string_xrefs

- `0x140006041`: `System\CurrentControlSet\Services\Dfs`
- `0x140006124`: `System\CurrentControlSet\Services\Dfs\Parameters`
- `0x140006098`: `DfsDnsConfig`
- `0x1400061da`: `MaxClientsToCache`
- `0x140006272`: `NumWorkerThreads`
- `0x14000632f`: `MaxSitesToCache`

## pseudocode

```c
void __fastcall CConfigurationSettings::Initialise(CConfigurationSettings *this)
{
  unsigned int *v2; // rdi
  unsigned int *v3; // rsi
  unsigned int *v4; // r14
  unsigned int *v5; // r15
  unsigned int *v6; // r12
  unsigned int *v7; // r13
  _UNKNOWN **v8; // rax
  unsigned int *v9; // rcx
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+38h] [rbp-8h]
  unsigned int v12; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v13; // [rsp+88h] [rbp+48h] BYREF

  *(_BYTE *)this = 1;
  *((_DWORD *)this + 3) = 1;
  *((_BYTE *)this + 8) = 0;
  v2 = (unsigned int *)((char *)this + 4);
  v3 = (unsigned int *)((char *)this + 20);
  v10 = 0;
  v11 = 0;
  *((_DWORD *)this + 5) = 43200;
  *((_DWORD *)this + 11) = 43200;
  v4 = (unsigned int *)((char *)this + 28);
  *((_BYTE *)this + 56) = 0;
  *((_DWORD *)this + 18) = 1024;
  v5 = (unsigned int *)((char *)this + 32);
  *((_DWORD *)this + 19) = 1024;
  v6 = (unsigned int *)((char *)this + 36);
  *((_BYTE *)this + 16) = 0;
  v7 = (unsigned int *)((char *)this + 40);
  *((_BYTE *)this + 68) = 0;
  *((_DWORD *)this + 1) = 3600;
  *((_BYTE *)this + 24) = 1;
  *((_DWORD *)this + 7) = 30;
  *((_DWORD *)this + 8) = 200000;
  *((_DWORD *)this + 9) = 30;
  *((_DWORD *)this + 10) = 900;
  *((_QWORD *)this + 6) = 4;
  *((_DWORD *)this + 15) = 1000;
  *((_DWORD *)this + 16) = 256;
  if ( CRegistry::OpenKey((CRegistry *)&v10, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Dfs", 0x20019u) )
  {
    v13 = 1;
    v12 = 1;
    DfspLoadDwordSetting((struct CRegistry *)&v10, L"DfsDnsConfig", 0, &v13, &v12);
    *(_BYTE *)this = v12;
    DfspLoadDwordSetting(
      (struct CRegistry *)&v10,
      L"SyncIntervalInSeconds",
      *((_BYTE *)this + 16) != 0 ? 1 : 900,
      0,
      v2);
    v12 = 0;
    DfspLoadDwordSetting((struct CRegistry *)&v10, L"PreferLogonDc", 0, &v13, &v12);
    *((_BYTE *)this + 8) = v12;
    CRegistry::CloseKey((CRegistry *)&v10);
    if ( CRegistry::OpenKey(
           (CRegistry *)&v10,
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Dfs\\Parameters",
           0x20019u) )
    {
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"RootShareAcquireSuccessEvent", 0, 0, (unsigned int *)this + 3);
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"DomainNameIntervalInSeconds", 0x258u, 0, v3);
      v12 = 1;
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"SiteCostedReferrals", 0, &v13, &v12);
      *((_BYTE *)this + 24) = v12;
      DfspLoadDwordSetting(
        (struct CRegistry *)&v10,
        L"LdapTimeoutValueInSeconds",
        0,
        &CConfigurationSettings::gm_LdapTimeoutValueInSecondsMax,
        v4);
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"MaxClientsToCache", 0x4E20u, 0, v5);
      DfspLoadDwordSetting(
        (struct CRegistry *)&v10,
        L"QuerySiteCostTimeoutInSeconds",
        3u,
        &CConfigurationSettings::gm_LdapTimeoutValueInSecondsMax,
        v6);
      DfspLoadDwordSetting(
        (struct CRegistry *)&v10,
        L"RootReferralTimeoutInSeconds",
        *((_BYTE *)this + 16) != 0 ? 1 : 900,
        0,
        v7);
      DfspLoadDwordSetting(
        (struct CRegistry *)&v10,
        L"SiteSupportIntervalInSeconds",
        0x12Cu,
        0,
        (unsigned int *)this + 11);
      DfspLoadDwordSetting(
        (struct CRegistry *)&v10,
        L"NumWorkerThreads",
        2u,
        &CConfigurationSettings::gm_NumWorkerThreadsMax,
        (unsigned int *)this + 12);
      DfspLoadDwordSetting(
        (struct CRegistry *)&v10,
        L"ForceReferralVersionNumber",
        0,
        &CConfigurationSettings::gm_ForceReferralVersionNumberMax,
        (unsigned int *)this + 13);
      v12 = *((unsigned __int8 *)this + 56);
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"SysvolNetlogonTargetFailback", 0, &v13, &v12);
      *((_BYTE *)this + 56) = v12;
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"AllowableErrorsValue", 0, 0, (unsigned int *)this + 15);
      CConfigurationSettings::LoadDisableSiteAwarenessSetting(this, (struct CRegistry *)&v10);
      CConfigurationSettings::LoadDfsSkipResyncSetting(this);
      v12 = *((unsigned __int8 *)this + 66);
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"DomainFunctionalLevelOverride", 0, &v13, &v12);
      *((_BYTE *)this + 66) = v12;
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"MaxSitesToCache", 0x80u, 0, (unsigned int *)this + 18);
      DfspLoadDwordSetting((struct CRegistry *)&v10, L"SiteNameLength", 0x3Fu, 0, (unsigned int *)this + 19);
      CRegistry::CloseKey((CRegistry *)&v10);
    }
  }
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v9 = pWppControl;
    if ( pWppControl && (pWppControl[7] & 0x20) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_D(
        *((_QWORD *)pWppControl + 2),
        10,
        WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
        *((unsigned __int8 *)this + 16));
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v9 = pWppControl;
    }
    if ( v8 != &WPP_GLOBAL_Control )
    {
      if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
      {
        WPP_SF_D(*((_QWORD *)v9 + 2), 11, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *(unsigned __int8 *)this);
        v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
        v9 = pWppControl;
      }
      if ( v8 != &WPP_GLOBAL_Control )
      {
        if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
        {
          WPP_SF_D(*((_QWORD *)v9 + 2), 12, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *v2);
          v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
          v9 = pWppControl;
        }
        if ( v8 != &WPP_GLOBAL_Control )
        {
          if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
          {
            WPP_SF_D(
              *((_QWORD *)v9 + 2),
              13,
              WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
              *((unsigned __int8 *)this + 8));
            v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
            v9 = pWppControl;
          }
          if ( v8 != &WPP_GLOBAL_Control )
          {
            if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
            {
              WPP_SF_D(*((_QWORD *)v9 + 2), 14, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *v3);
              v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
              v9 = pWppControl;
            }
            if ( v8 != &WPP_GLOBAL_Control )
            {
              if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
              {
                WPP_SF_D(
                  *((_QWORD *)v9 + 2),
                  15,
                  WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                  *((unsigned __int8 *)this + 24));
                v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                v9 = pWppControl;
              }
              if ( v8 != &WPP_GLOBAL_Control )
              {
                if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                {
                  WPP_SF_D(*((_QWORD *)v9 + 2), 16, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *v4);
                  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                  v9 = pWppControl;
                }
                if ( v8 != &WPP_GLOBAL_Control )
                {
                  if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                  {
                    WPP_SF_D(*((_QWORD *)v9 + 2), 17, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *v5);
                    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                    v9 = pWppControl;
                  }
                  if ( v8 != &WPP_GLOBAL_Control )
                  {
                    if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                    {
                      WPP_SF_D(*((_QWORD *)v9 + 2), 18, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *v6);
                      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                      v9 = pWppControl;
                    }
                    if ( v8 != &WPP_GLOBAL_Control )
                    {
                      if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                      {
                        WPP_SF_D(*((_QWORD *)v9 + 2), 19, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids, *v7);
                        v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                        v9 = pWppControl;
                      }
                      if ( v8 != &WPP_GLOBAL_Control )
                      {
                        if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                        {
                          WPP_SF_D(
                            *((_QWORD *)v9 + 2),
                            20,
                            WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                            *((unsigned int *)this + 11));
                          v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                          v9 = pWppControl;
                        }
                        if ( v8 != &WPP_GLOBAL_Control )
                        {
                          if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                          {
                            WPP_SF_D(
                              *((_QWORD *)v9 + 2),
                              21,
                              WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                              *((unsigned int *)this + 12));
                            v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                            v9 = pWppControl;
                          }
                          if ( v8 != &WPP_GLOBAL_Control )
                          {
                            if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                            {
                              WPP_SF_D(
                                *((_QWORD *)v9 + 2),
                                22,
                                WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                *((unsigned int *)this + 13));
                              v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                              v9 = pWppControl;
                            }
                            if ( v8 != &WPP_GLOBAL_Control )
                            {
                              if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                              {
                                WPP_SF_D(
                                  *((_QWORD *)v9 + 2),
                                  23,
                                  WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                  *((unsigned __int8 *)this + 56));
                                v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                                v9 = pWppControl;
                              }
                              if ( v8 != &WPP_GLOBAL_Control )
                              {
                                if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                                {
                                  WPP_SF_D(
                                    *((_QWORD *)v9 + 2),
                                    24,
                                    WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                    *((unsigned int *)this + 15));
                                  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                                  v9 = pWppControl;
                                }
                                if ( v8 != &WPP_GLOBAL_Control )
                                {
                                  if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                                  {
                                    WPP_SF_D(
                                      *((_QWORD *)v9 + 2),
                                      25,
                                      WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                      *((unsigned __int8 *)this + 64));
                                    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                                    v9 = pWppControl;
                                  }
                                  if ( v8 != &WPP_GLOBAL_Control )
                                  {
                                    if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                                    {
                                      WPP_SF_D(
                                        *((_QWORD *)v9 + 2),
                                        26,
                                        WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                        *((unsigned __int8 *)this + 66));
                                      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                                      v9 = pWppControl;
                                    }
                                    if ( v8 != &WPP_GLOBAL_Control )
                                    {
                                      if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                                      {
                                        WPP_SF_D(
                                          *((_QWORD *)v9 + 2),
                                          27,
                                          WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                          *((unsigned int *)this + 18));
                                        v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                                        v9 = pWppControl;
                                      }
                                      if ( v8 != &WPP_GLOBAL_Control )
                                      {
                                        if ( v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 3u )
                                        {
                                          WPP_SF_D(
                                            *((_QWORD *)v9 + 2),
                                            28,
                                            WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                            *((unsigned int *)this + 19));
                                          v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
                                          v9 = pWppControl;
                                        }
                                        if ( v8 != &WPP_GLOBAL_Control
                                          && v9
                                          && (v9[7] & 0x20) != 0
                                          && *((_BYTE *)v9 + 25) >= 3u )
                                        {
                                          WPP_SF_D(
                                            *((_QWORD *)v9 + 2),
                                            29,
                                            WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids,
                                            *((unsigned int *)this + 3));
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
        }
      }
    }
  }
  CRegistry::~CRegistry((CRegistry *)&v10);
}

```

## disassembly

```asm
0x140005fc8  mov     [rsp-38h+arg_10], rbx
0x140005fcd  push    rbp
0x140005fce  push    rsi
0x140005fcf  push    rdi
0x140005fd0  push    r12
0x140005fd2  push    r13
0x140005fd4  push    r14
0x140005fd6  push    r15
0x140005fd8  mov     rbp, rsp
0x140005fdb  sub     rsp, 40h
0x140005fdf  mov     rbx, rcx
0x140005fe2  mov     byte ptr [rcx], 1
0x140005fe5  xor     edx, edx
0x140005fe7  mov     dword ptr [rcx+0Ch], 1
0x140005fee  mov     [rcx+8], dl
0x140005ff1  lea     rdi, [rcx+4]
0x140005ff5  lea     rsi, [rcx+14h]
0x140005ff9  mov     [rbp+var_10], rdx
0x140005ffd  mov     ecx, 0A8C0h
0x140006002  mov     [rbp+var_8], edx
0x140006005  lea     eax, [rdx+1Eh]
0x140006008  mov     [rsi], ecx
0x14000600a  mov     [rbx+2Ch], ecx
0x14000600d  lea     r14, [rbx+1Ch]
0x140006011  mov     ecx, 400h
0x140006016  mov     [rbx+38h], dl
0x140006019  mov     [rbx+48h], ecx
0x14000601c  lea     r15, [rbx+20h]
0x140006020  mov     [rbx+4Ch], ecx
0x140006023  lea     r12, [rbx+24h]
0x140006027  mov     [rbx+10h], dl
0x14000602a  lea     r13, [rbx+28h]
0x14000602e  mov     [rbx+44h], dl
0x140006031  lea     rcx, [rbp+var_10]; this
0x140006035  mov     r9d, 20019h; unsigned int
0x14000603b  mov     dword ptr [rdi], 0E10h
0x140006041  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Df"...
0x140006048  mov     byte ptr [rbx+18h], 1
0x14000604c  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140006053  mov     [r14], eax
0x140006056  mov     dword ptr [r15], 30D40h
0x14000605d  mov     [r12], eax
0x140006061  mov     dword ptr [r13+0], 384h
0x140006069  mov     qword ptr [rbx+30h], 4
0x140006071  mov     dword ptr [rbx+3Ch], 3E8h
0x140006078  mov     dword ptr [rbx+40h], 100h
0x14000607f  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x140006084  test    eax, eax
0x140006086  jz      loc_14000637D
0x14000608c  mov     eax, 1
0x140006091  lea     r9, [rbp+arg_8]; unsigned int *
0x140006095  mov     [rbp+arg_8], eax
0x140006098  lea     rdx, aDfsdnsconfig; "DfsDnsConfig"
0x14000609f  mov     [rbp+arg_0], eax
0x1400060a2  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400060a6  lea     rax, [rbp+arg_0]
0x1400060aa  xor     r8d, r8d; unsigned int
0x1400060ad  mov     [rsp+40h+var_20], rax; unsigned int *
0x1400060b2  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400060b7  mov     al, byte ptr [rbp+arg_0]
0x1400060ba  lea     rdx, aSyncintervalin; "SyncIntervalInSeconds"
0x1400060c1  mov     [rbx], al
0x1400060c3  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400060c7  mov     al, [rbx+10h]
0x1400060ca  neg     al
0x1400060cc  mov     [rsp+40h+var_20], rdi; unsigned int *
0x1400060d1  sbb     r8d, r8d
0x1400060d4  xor     r9d, r9d; unsigned int *
0x1400060d7  and     r8d, 0FFFFFC7Dh
0x1400060de  add     r8d, 384h; unsigned int
0x1400060e5  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400060ea  xor     edx, edx
0x1400060ec  lea     rax, [rbp+arg_0]
0x1400060f0  mov     [rbp+arg_0], edx
0x1400060f3  lea     r9, [rbp+arg_8]; unsigned int *
0x1400060f7  lea     rdx, aPreferlogondc; "PreferLogonDc"
0x1400060fe  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006103  xor     r8d, r8d; unsigned int
0x140006106  lea     rcx, [rbp+var_10]; struct CRegistry *
0x14000610a  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x14000610f  mov     al, byte ptr [rbp+arg_0]
0x140006112  lea     rcx, [rbp+var_10]; this
0x140006116  mov     [rbx+8], al
0x140006119  call    ?CloseKey@CRegistry@@QEAAXXZ; CRegistry::CloseKey(void)
0x14000611e  mov     r9d, 20019h; unsigned int
0x140006124  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Df"...
0x14000612b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140006132  lea     rcx, [rbp+var_10]; this
0x140006136  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x14000613b  test    eax, eax
0x14000613d  jz      loc_14000637D
0x140006143  lea     rax, [rbx+0Ch]
0x140006147  xor     r9d, r9d; unsigned int *
0x14000614a  xor     r8d, r8d; unsigned int
0x14000614d  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006152  lea     rdx, aRootshareacqui; "RootShareAcquireSuccessEvent"
0x140006159  lea     rcx, [rbp+var_10]; struct CRegistry *
0x14000615d  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x140006162  xor     r9d, r9d; unsigned int *
0x140006165  mov     [rsp+40h+var_20], rsi; unsigned int *
0x14000616a  mov     r8d, 258h; unsigned int
0x140006170  lea     rdx, aDomainnameinte; "DomainNameIntervalInSeconds"
0x140006177  lea     rcx, [rbp+var_10]; struct CRegistry *
0x14000617b  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x140006180  lea     rax, [rbp+arg_0]
0x140006184  mov     [rbp+arg_0], 1
0x14000618b  lea     r9, [rbp+arg_8]; unsigned int *
0x14000618f  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006194  xor     r8d, r8d; unsigned int
0x140006197  lea     rdx, aSitecostedrefe; "SiteCostedReferrals"
0x14000619e  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400061a2  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400061a7  mov     al, byte ptr [rbp+arg_0]
0x1400061aa  lea     r9, ?gm_LdapTimeoutValueInSecondsMax@CConfigurationSettings@@0KB; unsigned int *
0x1400061b1  xor     r8d, r8d; unsigned int
0x1400061b4  mov     [rbx+18h], al
0x1400061b7  lea     rdx, aLdaptimeoutval; "LdapTimeoutValueInSeconds"
0x1400061be  mov     [rsp+40h+var_20], r14; unsigned int *
0x1400061c3  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400061c7  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400061cc  xor     r9d, r9d; unsigned int *
0x1400061cf  mov     [rsp+40h+var_20], r15; unsigned int *
0x1400061d4  mov     r8d, 4E20h; unsigned int
0x1400061da  lea     rdx, aMaxclientstoca; "MaxClientsToCache"
0x1400061e1  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400061e5  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400061ea  lea     r9, ?gm_LdapTimeoutValueInSecondsMax@CConfigurationSettings@@0KB; unsigned int *
0x1400061f1  mov     [rsp+40h+var_20], r12; unsigned int *
0x1400061f6  mov     r8d, 3; unsigned int
0x1400061fc  lea     rdx, aQuerysitecostt; "QuerySiteCostTimeoutInSeconds"
0x140006203  lea     rcx, [rbp+var_10]; struct CRegistry *
0x140006207  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x14000620c  mov     al, [rbx+10h]
0x14000620f  lea     rdx, aRootreferralti; "RootReferralTimeoutInSeconds"
0x140006216  neg     al
0x140006218  mov     [rsp+40h+var_20], r13; unsigned int *
0x14000621d  lea     rcx, [rbp+var_10]; struct CRegistry *
0x140006221  sbb     r8d, r8d
0x140006224  xor     r9d, r9d; unsigned int *
0x140006227  and     r8d, 0FFFFFC7Dh
0x14000622e  add     r8d, 384h; unsigned int
0x140006235  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x14000623a  lea     rax, [rbx+2Ch]
0x14000623e  xor     r9d, r9d; unsigned int *
0x140006241  mov     r8d, 12Ch; unsigned int
0x140006247  mov     [rsp+40h+var_20], rax; unsigned int *
0x14000624c  lea     rdx, aSitesupportint; "SiteSupportIntervalInSeconds"
0x140006253  lea     rcx, [rbp+var_10]; struct CRegistry *
0x140006257  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x14000625c  lea     rax, [rbx+30h]
0x140006260  mov     r8d, 2; unsigned int
0x140006266  lea     r9, ?gm_NumWorkerThreadsMax@CConfigurationSettings@@0KB; unsigned int *
0x14000626d  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006272  lea     rdx, aNumworkerthrea; "NumWorkerThreads"
0x140006279  lea     rcx, [rbp+var_10]; struct CRegistry *
0x14000627d  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x140006282  lea     rax, [rbx+34h]
0x140006286  xor     r8d, r8d; unsigned int
0x140006289  lea     r9, ?gm_ForceReferralVersionNumberMax@CConfigurationSettings@@0KB; unsigned int *
0x140006290  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006295  lea     rdx, aForcereferralv; "ForceReferralVersionNumber"
0x14000629c  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400062a0  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400062a5  movzx   eax, byte ptr [rbx+38h]
0x1400062a9  lea     r9, [rbp+arg_8]; unsigned int *
0x1400062ad  mov     [rbp+arg_0], eax
0x1400062b0  lea     rdx, aSysvolnetlogon; "SysvolNetlogonTargetFailback"
0x1400062b7  lea     rax, [rbp+arg_0]
0x1400062bb  xor     r8d, r8d; unsigned int
0x1400062be  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400062c2  mov     [rsp+40h+var_20], rax; unsigned int *
0x1400062c7  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400062cc  mov     al, byte ptr [rbp+arg_0]
0x1400062cf  lea     rdx, aAllowableerror; "AllowableErrorsValue"
0x1400062d6  mov     [rbx+38h], al
0x1400062d9  lea     rcx, [rbp+var_10]; struct CRegistry *
0x1400062dd  lea     rax, [rbx+3Ch]
0x1400062e1  xor     r9d, r9d; unsigned int *
0x1400062e4  xor     r8d, r8d; unsigned int
0x1400062e7  mov     [rsp+40h+var_20], rax; unsigned int *
0x1400062ec  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x1400062f1  lea     rdx, [rbp+var_10]; struct CRegistry *
0x1400062f5  mov     rcx, rbx; this
0x1400062f8  call    ?LoadDisableSiteAwarenessSetting@CConfigurationSettings@@AEAAXAEAVCRegistry@@@Z; CConfigurationSettings::LoadDisableSiteAwarenessSetting(CRegistry &)
0x1400062fd  mov     rcx, rbx; this
0x140006300  call    ?LoadDfsSkipResyncSetting@CConfigurationSettings@@QEAAXXZ; CConfigurationSettings::LoadDfsSkipResyncSetting(void)
0x140006305  movzx   eax, byte ptr [rbx+42h]
0x140006309  lea     r9, [rbp+arg_8]; unsigned int *
0x14000630d  mov     [rbp+arg_0], eax
0x140006310  lea     rdx, aDomainfunction_0; "DomainFunctionalLevelOverride"
0x140006317  lea     rax, [rbp+arg_0]
0x14000631b  xor     r8d, r8d; unsigned int
0x14000631e  lea     rcx, [rbp+var_10]; struct CRegistry *
0x140006322  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006327  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x14000632c  mov     al, byte ptr [rbp+arg_0]
0x14000632f  lea     rdx, aMaxsitestocach; "MaxSitesToCache"
0x140006336  mov     [rbx+42h], al
0x140006339  lea     rcx, [rbp+var_10]; struct CRegistry *
0x14000633d  lea     rax, [rbx+48h]
0x140006341  xor     r9d, r9d; unsigned int *
0x140006344  mov     r8d, 80h; unsigned int
0x14000634a  mov     [rsp+40h+var_20], rax; unsigned int *
0x14000634f  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x140006354  xor     r9d, r9d; unsigned int *
0x140006357  lea     rax, [rbx+4Ch]
0x14000635b  lea     rdx, aSitenamelength; "SiteNameLength"
0x140006362  mov     [rsp+40h+var_20], rax; unsigned int *
0x140006367  lea     rcx, [rbp+var_10]; struct CRegistry *
0x14000636b  lea     r8d, [r9+3Fh]; unsigned int
0x14000636f  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x140006374  lea     rcx, [rbp+var_10]; this
0x140006378  call    ?CloseKey@CRegistry@@QEAAXXZ; CRegistry::CloseKey(void)
0x14000637d  mov     rax, cs:WPP_GLOBAL_Control
0x140006384  lea     rcx, WPP_GLOBAL_Control
0x14000638b  cmp     rax, rcx
0x14000638e  jz      loc_140006890
0x140006394  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000639b  test    rcx, rcx
0x14000639e  jz      short loc_1400063D4
0x1400063a0  test    byte ptr [rcx+1Ch], 20h
0x1400063a4  jz      short loc_1400063D4
0x1400063a6  cmp     byte ptr [rcx+19h], 3
0x1400063aa  jb      short loc_1400063D4
0x1400063ac  movzx   r9d, byte ptr [rbx+10h]
0x1400063b1  lea     r8, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids
0x1400063b8  mov     rcx, [rcx+10h]
0x1400063bc  mov     edx, 0Ah
0x1400063c1  call    WPP_SF_D
0x1400063c6  mov     rax, cs:WPP_GLOBAL_Control
0x1400063cd  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400063d4  lea     rdx, WPP_GLOBAL_Control
0x1400063db  cmp     rax, rdx
0x1400063de  jz      loc_140006890
0x1400063e4  test    rcx, rcx
0x1400063e7  jz      short loc_140006423
0x1400063e9  test    byte ptr [rcx+1Ch], 20h
0x1400063ed  jz      short loc_140006423
0x1400063ef  cmp     byte ptr [rcx+19h], 3
0x1400063f3  jb      short loc_140006423
0x1400063f5  movzx   r9d, byte ptr [rbx]
0x1400063f9  lea     r8, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids
0x140006400  mov     rcx, [rcx+10h]
0x140006404  mov     edx, 0Bh
0x140006409  call    WPP_SF_D
0x14000640e  mov     rax, cs:WPP_GLOBAL_Control
0x140006415  lea     rdx, WPP_GLOBAL_Control
0x14000641c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140006423  cmp     rax, rdx
0x140006426  jz      loc_140006890
0x14000642c  test    rcx, rcx
0x14000642f  jz      short loc_14000646A
0x140006431  test    byte ptr [rcx+1Ch], 20h
0x140006435  jz      short loc_14000646A
0x140006437  cmp     byte ptr [rcx+19h], 3
0x14000643b  jb      short loc_14000646A
0x14000643d  mov     r9d, [rdi]
0x140006440  lea     r8, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids
0x140006447  mov     rcx, [rcx+10h]
0x14000644b  mov     edx, 0Ch
0x140006450  call    WPP_SF_D
0x140006455  mov     rax, cs:WPP_GLOBAL_Control
0x14000645c  lea     rdx, WPP_GLOBAL_Control
0x140006463  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000646a  cmp     rax, rdx
0x14000646d  jz      loc_140006890
0x140006473  mov     dil, 20h ; ' '
0x140006476  test    rcx, rcx
0x140006479  jz      short loc_1400064B6
0x14000647b  test    [rcx+1Ch], dil
0x14000647f  jz      short loc_1400064B6
0x140006481  cmp     byte ptr [rcx+19h], 3
0x140006485  jb      short loc_1400064B6
0x140006487  movzx   r9d, byte ptr [rbx+8]
0x14000648c  lea     r8, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids
0x140006493  mov     rcx, [rcx+10h]
0x140006497  mov     edx, 0Dh
0x14000649c  call    WPP_SF_D
0x1400064a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400064a8  lea     rdx, WPP_GLOBAL_Control
0x1400064af  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400064b6  cmp     rax, rdx
0x1400064b9  jz      loc_140006890
0x1400064bf  test    rcx, rcx
0x1400064c2  jz      short loc_1400064F6
0x1400064c4  test    [rcx+1Ch], dil
0x1400064c8  jz      short loc_1400064F6
0x1400064ca  cmp     byte ptr [rcx+19h], 3
0x1400064ce  jb      short loc_1400064F6
0x1400064d0  mov     r9d, [rsi]
0x1400064d3  lea     r8, WPP_54a7e64a20b33eee1d74ce0009d323fc_Traceguids
0x1400064da  mov     rcx, [rcx+10h]
0x1400064de  mov     edx, 0Eh
0x1400064e3  call    WPP_SF_D
0x1400064e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400064ef  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400064f6  lea     rsi, WPP_GLOBAL_Control
0x1400064fd  cmp     rax, rsi
0x140006500  jz      loc_140006890
0x140006506  test    rcx, rcx
  ... truncated ...
```
