# CTscSettings::LoadFromStore(ITsSettingsStore *)

- ea: `0x140037188`
- end: `0x1400396eb`
- name: `?LoadFromStore@CTscSettings@@QEAAJPEAVITsSettingsStore@@@Z`
- size: `9571`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this, struct ITsSettingsStore *)`
- caller_count: `3`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003568c`
- `0x1400360ec`
- `0x14004291c`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e130`
- `0x14001e158`
- `0x14001e210`
- `0x140029468`
- `0x14002a77c`
- `0x140037188`
- `0x14003a128`
- `0x14003a3d0`
- `0x14003b66c`
- `0x14003b898`
- `0x14003ba80`
- `0x14003e5c0`
- `0x14003e688`
- `0x140040b9c`
- `0x14009d6f8`
- `0x14009d824`
- `0x14009d9e8`
- `0x14009e410`
- `0x1400a8ecc`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!ReleaseDC` at `0x140037834`
- `USER32!ReleaseDC` at `0x140037834`
- `USER32!GetDC` at `0x1400377ce`
- `USER32!GetDC` at `0x1400377ce`
- `msvcrt!_wcsicmp` at `0x1400383ee`
- `msvcrt!_wcsicmp` at `0x1400383ee`
- `msvcrt!swscanf_s` at `0x140037457`
- `msvcrt!swscanf_s` at `0x14003752a`
- `msvcrt!swscanf_s` at `0x140037457`
- `msvcrt!swscanf_s` at `0x14003752a`
- `GDI32!GetDeviceCaps` at `0x1400377e4`
- `GDI32!GetDeviceCaps` at `0x1400377e4`

## string_xrefs

- `0x140038aac`: `StringCchCopy failed`
- `0x140037de3`: `Negotiate Security Layer`
- `0x14003841d`: `Shell Working Directory`
- `0x1400385e2`: `RemoteApplicationFileExtensions`
- `0x140038c01`: `RedirectCOMPorts`
- `0x140037b9e`: `allowed security protocols`
- `0x140037c03`: `GatewayAccessToken`
- `0x140037f1a`: `IgnoreServerGeneratedMouseMoves`
- `0x1400386f3`: `RemoteAppMouseMoveInject`
- `0x140038825`: `Compression`
- `0x1400388c0`: `BitmapPersistCacheSize`
- `0x140038975`: `BitmapPersistCacheSize`
- `0x140038892`: `BitmapCacheSize`
- `0x14003891c`: `BitmapPersistCache24Size`
- `0x1400389b4`: `BitmapPersistCache24Size`
- `0x1400388eb`: `BitmapPersistCache16Size`
- `0x140038991`: `BitmapPersistCache16Size`
- `0x140038950`: `BitmapPersistCache32Size`
- `0x1400389d6`: `BitmapPersistCache32Size`
- `0x140038f99`: `ClxCommandLine`
- `0x140039064`: `HvSocketServiceId`
- `0x1400392b5`: `GatewayBrokeringType`
- `0x140039609`: `SetClientProtocolSpecMode`
- `0x140039693`: `diagnosticserviceurl`

## pseudocode

```c
__int64 __fastcall CTscSettings::LoadFromStore(CTscSettings *this, struct ITsSettingsStore *a2)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  bool v8; // zf
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _DWORD *v10; // rbx
  unsigned int *v11; // r13
  PVOID *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int *v18; // r13
  PVOID *v19; // rcx
  unsigned int v20; // ebx
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rdx
  int v24; // ebx
  int v25; // ecx
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // ecx
  unsigned int v29; // ecx
  int v30; // eax
  HDC DC; // rax
  HDC v32; // rbx
  unsigned int DeviceCaps; // r13d
  unsigned int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // r8
  unsigned int v37; // ebx
  unsigned int v38; // eax
  int v39; // ecx
  unsigned int ServerAuthValue; // eax
  unsigned int v41; // eax
  __int64 v42; // rdx
  unsigned int v43; // eax
  PVOID *v44; // rax
  int v45; // ebx
  unsigned int v46; // eax
  int v47; // ebx
  unsigned int v48; // eax
  _DWORD *v49; // rbx
  unsigned int v50; // eax
  __int64 v51; // rax
  unsigned int v52; // eax
  __int64 v53; // rax
  unsigned int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  unsigned int v58; // eax
  unsigned int RegistryInt; // eax
  __int64 v60; // rax
  int v61; // ecx
  __int64 v62; // rax
  __int64 v63; // rax
  unsigned int v64; // eax
  __int64 v65; // rax
  int v66; // ebx
  unsigned int v67; // eax
  unsigned int v68; // eax
  int v69; // ebx
  unsigned int v70; // eax
  _DWORD *v71; // rbx
  _DWORD *v72; // r13
  int v73; // eax
  __int64 v74; // r8
  int v75; // eax
  __int64 v76; // r8
  int v77; // eax
  __int64 v78; // r8
  unsigned int v79; // edx
  int UserNameFromStore; // ebx
  int v81; // r11d
  unsigned int v82; // eax
  int v83; // edx
  const char *v84; // rcx
  const unsigned __int16 *v85; // rcx
  unsigned int v86; // eax
  __int64 v87; // rax
  unsigned int v88; // eax
  _DWORD *v89; // rbx
  _DWORD *v90; // rbx
  _DWORD *v91; // rbx
  _DWORD *v92; // rbx
  _DWORD *v93; // rbx
  _DWORD *v94; // r9
  unsigned int v95; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v96; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v97; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v98; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v99; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v100; // [rsp+54h] [rbp-ACh] BYREF
  int v101; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v102; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v103; // [rsp+60h] [rbp-A0h] BYREF
  int v104; // [rsp+64h] [rbp-9Ch] BYREF
  int v105; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v106; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v107; // [rsp+70h] [rbp-90h] BYREF
  int v108; // [rsp+74h] [rbp-8Ch] BYREF
  int v109; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v110[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v111[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v112[256]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v113[128]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v114[128]; // [rsp+3C0h] [rbp+2C0h] BYREF
  wchar_t Buffer[256]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v116[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  if ( a2 )
  {
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *))(*(_QWORD *)a2 + 64LL))(a2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids);
      }
      return 2147500037LL;
    }
    *((_DWORD *)this + 51532) = CUT::UT_ReadRegistryInt(&pszPassword, L"DisablePrinterRedirection", 0, 2);
    *((_DWORD *)this + 51531) = CUT::UT_ReadRegistryInt(&pszPassword, L"DisableClipboardRedirection", 0, 2);
    *((_DWORD *)this + 16492) = CUT::UT_ReadRegistryInt(&pszPassword, L"EnableLocationSimulation", 0, 2);
    v5 = *(_QWORD *)a2;
    v104 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, int *))(v5 + 168))(
            a2,
            L"Public Mode",
            0,
            &v104) )
      return 2147500037LL;
    if ( v104 )
      *((_DWORD *)this + 51529) = 1;
    v6 = *(_QWORD *)a2;
    v105 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, int *))(v6 + 144))(
            a2,
            L"Screen Mode ID",
            0,
            &v105) )
      return 2147500037LL;
    if ( v105 )
    {
      v8 = v105 == 2;
    }
    else
    {
      v7 = *(_QWORD *)a2;
      v95 = 0;
      if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, unsigned int *))(v7 + 144))(
              a2,
              L"Desktop Size ID",
              0xFFFFFFFFLL,
              &v95) )
        return 2147500037LL;
      v8 = v95 == -1;
    }
    *((_DWORD *)this + 50336) = v8;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const wchar_t *, wchar_t *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"WinPosStr",
            L"0,3,0,0,800,600",
            Buffer,
            256) )
      return 2147500037LL;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)Buffer);
    }
    v10 = (_DWORD *)((char *)this + 92);
    v11 = (unsigned int *)((char *)this + 68);
    v95 = swscanf_s(
            Buffer,
            L"%u,%u,%d,%d,%d,%d",
            (char *)this + 68,
            (char *)this + 72,
            (char *)this + 92,
            (char *)this + 96,
            (char *)this + 100,
            (char *)this + 104);
    if ( v95 == 6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v14);
      }
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, Buffer);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DLD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
            v13,
            v95,
            6);
        }
      }
      wcscpy(v110, L"0,3,0,0,800,600");
      swscanf_s(
        v110,
        L"%u,%u,%d,%d,%d,%d",
        (char *)this + 68,
        (char *)this + 72,
        (char *)this + 92,
        (char *)this + 96,
        (char *)this + 100,
        (char *)this + 104);
    }
    v15 = *v11;
    *((_DWORD *)this + 16) = 44;
    v95 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v16, v95);
      }
      *v11 = 0;
    }
    v95 = *((_DWORD *)this + 18);
    if ( ((v95 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
          v17,
          v95,
          1);
      }
      *((_DWORD *)this + 18) = 1;
    }
    if ( *((_DWORD *)this + 25) - *v10 < 200 )
    {
      *v10 = 0;
      *((_DWORD *)this + 25) = 800;
    }
    if ( *((_DWORD *)this + 26) - *((_DWORD *)this + 24) < 200 )
    {
      *((_DWORD *)this + 24) = 0;
      *((_DWORD *)this + 26) = 600;
    }
    v18 = (unsigned int *)((char *)this + 32284);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"Desktop Size ID",
            1,
            (char *)this + 32284) )
      return 2147500037LL;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v20 = *v18;
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v21, v20);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    v22 = *v18;
    if ( *v18 > 4 )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) )
        WPP_SF_d(v19[2], 27, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v22);
      *v18 = 1;
      v22 = 1;
    }
    v23 = v22;
    v24 = 0x2000;
    v106 = 800;
    v25 = 0x2000;
    v107 = 600;
    v26 = (unsigned int)(&tscScreenResTable)[v22];
    if ( v26 < 0x2000 )
      v25 = v26;
    v27 = dword_140126334[2 * v23];
    *((_DWORD *)this + 8072) = v25;
    v28 = 0x2000;
    if ( v27 < 0x2000 )
      v28 = v27;
    *((_DWORD *)this + 8073) = v28;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"DesktopWidth",
            0,
            &v106)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"DesktopHeight",
            0,
            &v107) )
    {
      return 2147500037LL;
    }
    if ( v106 )
    {
      v29 = v107;
      if ( v107 )
      {
        if ( v106 >= 0xC8 && v107 >= 0xC8 && v106 <= 0x2000 && v107 <= 0x2000 )
        {
          v30 = 0x2000;
          if ( v106 < 0x2000 )
            v30 = v106;
          *((_DWORD *)this + 8072) = v30;
          if ( v29 < 0x2000 )
            v24 = v29;
          *((_DWORD *)this + 8073) = v24;
        }
      }
    }
    DC = GetDC(0);
    v32 = DC;
    if ( DC )
    {
      DeviceCaps = GetDeviceCaps(DC, 12);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v34 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DqD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
          v34,
          v32,
          DeviceCaps);
      }
      ReleaseDC(0, v32);
      v35 = 0;
      v96 = 0;
      if ( DeviceCaps > 0x20 )
      {
        v36 = 32;
        goto LABEL_97;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids);
      }
      v35 = 0;
      v96 = 0;
      DeviceCaps = 16;
    }
    v36 = DeviceCaps;
LABEL_97:
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, unsigned int *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"Session Bpp",
            v36,
            &v96) )
      return 2147500037LL;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v37 = v96;
      v38 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v38, v37);
      v35 = 0;
    }
    v39 = v96;
    if ( v96 >= DeviceCaps && DeviceCaps >= 8 )
    {
      v39 = DeviceCaps;
      v96 = DeviceCaps;
    }
    if ( v39 != 8 && v39 != 15 && v39 != 16 && v39 != 24 && v39 != 32 )
    {
      v39 = 16;
      v96 = 16;
    }
    *((_DWORD *)this + 11406) = v39;
    do
    {
      CUT::UT_ReadRegistryStringCb(
        L"Default",
        (&mruEntriesNames)[v35],
        &pszPassword,
        (char *)this + 512 * v35 + 32296,
        512,
        2);
      ++v35;
    }
    while ( v35 != 10 );
    memset_0(v112, 0, sizeof(v112));
    *((_DWORD *)this + 54306) = 0;
    if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const unsigned __int16 *, unsigned __int16 *, __int64))(*(_QWORD *)a2 + 96LL))(
           a2,
           L"Alternate Full Address",
           v112,
           256) )
    {
      *((_DWORD *)this + 54306) = v112[0] != 0;
    }
    if ( !*((_DWORD *)this + 54306)
      && !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const unsigned __int16 *, const WCHAR *, unsigned __int16 *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Full Address",
            &pszPassword,
            v112,
            256) )
    {
      return 2147500037LL;
    }
    CRdpConnectionString::SetFullConnectionString((CTscSettings *)((char *)this + 108), v112);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, unsigned __int16 *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"LoadBalanceInfo",
            &pszPassword,
            v116,
            257) )
      return 2147500037LL;
    CTscSettings::SetLoadBalance(this, v116);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Smart Sizing",
            0,
            (char *)this + 46160)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"DeviceScaleFactor",
            0,
            (char *)this + 37420)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"DesktopScaleFactor",
            0,
            (char *)this + 37416)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Disable Smart Sizing RemoteApp Details",
            0,
            (char *)this + 46164)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Administrative Session",
            0,
            (char *)this + 65940)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"EnableCredSspSupport",
            1,
            (char *)this + 30684)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"EnableRdsAadAuth",
            0,
            (char *)this + 30692)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"allowed security protocols",
            L"*",
            (char *)this + 30696,
            256)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"EndpointFedAuth",
            &pszPassword,
            (char *)this + 37432,
            4096)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"GatewayAccessToken",
            &pszPassword,
            (char *)this + 69628,
            0x10000) )
    {
      return 2147500037LL;
    }
    *((_DWORD *)this + 50857) = 3;
    *((_DWORD *)this + 50856) = 3;
    ServerAuthValue = CUT::UT_RegGetServerAuthValue();
    if ( ServerAuthValue < 3 )
    {
      *((_DWORD *)this + 50857) = ServerAuthValue;
    }
    else
    {
      v95 = 0;
      CredSspIsPresent();
      if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, unsigned int *))(*(_QWORD *)a2 + 144LL))(
              a2,
              L"Authentication Level",
              2,
              &v95) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 2147500037LL;
        }
        v41 = RdpWppGetCurrentThreadActivityIdPrefix();
        v42 = 31;
        goto LABEL_306;
      }
      if ( v95 >= 3 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v43);
        }
        *((_DWORD *)this + 50856) = 2;
      }
      else
      {
        *((_DWORD *)this + 50856) = v95;
      }
    }
    v44 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v45 = *((_DWORD *)this + 50856);
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v46, v45);
        v44 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 1) != 0 && *((_BYTE *)v44 + 25) >= 4u )
      {
        v47 = *((_DWORD *)this + 50857);
        v48 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v48, v47);
      }
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Prompt For Credentials",
            0,
            (char *)this + 30664)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Prompt For Credentials On Client",
            0,
            (char *)this + 30676)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Negotiate Security Layer",
            1,
            (char *)this + 30680) )
    {
      return 2147500037LL;
    }
    if ( !(unsigned int)CredSspIsPresent()
      || !*((_DWORD *)this + 7671)
      || *((_WORD *)this + 18716)
      || *((_DWORD *)this + 7673)
      || *((_WORD *)this + 15348) != 42
      || *((_WORD *)this + 15349) )
    {
      *((_DWORD *)this + 7670) = 1;
    }
    v49 = (_DWORD *)((char *)this + 46168);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"Server Port",
            3389,
            (char *)this + 46168) )
      return 2147500037LL;
    if ( *v49 > 0xFFFFu )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v50 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v50);
      }
      *v49 = 3389;
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Enable Mouse",
            1,
            (char *)this + 46172) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"High Resolution Mouse",
            0,
            (char *)this + 46176) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"IgnoreServerGeneratedMouseMoves",
            0,
            (char *)this + 215124) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"DisableTouchRemoting",
            0,
            (char *)this + 46180) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"MultipenRemotingSupported",
            0,
            (char *)this + 46184) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Disable CTRL+ALT+DEL",
            1,
            (char *)this + 46188) )
      return 2147500037LL;
    v51 = *(_QWORD *)a2;
    v97 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, unsigned int *))(v51 + 144))(
            a2,
            L"KeyboardHook",
            2,
            &v97) )
      return 2147500037LL;
    v52 = v97;
    if ( v97 > 2 )
    {
      v52 = 0;
      v97 = 0;
    }
    *((_DWORD *)this + 11407) = v52;
    v53 = *(_QWORD *)a2;
    v98 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, unsigned int *))(v53 + 144))(
            a2,
            L"AudioMode",
            0,
            &v98) )
      return 2147500037LL;
    v54 = v98;
    if ( v98 > 2 )
    {
      v54 = 0;
      v98 = 0;
    }
    *((_DWORD *)this + 11408) = v54;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"AudioCaptureMode",
            0,
            (char *)this + 45636) )
      return 2147500037LL;
    v55 = *(_QWORD *)a2;
    v99 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, unsigned int *))(v55 + 144))(
            a2,
            L"VideoPlaybackMode",
            1,
            &v99) )
      return 2147500037LL;
    v56 = v99;
    if ( v99 > 2 )
    {
      v56 = 1;
      v99 = 1;
    }
    *((_DWORD *)this + 11410) = v56;
    v57 = *(_QWORD *)a2;
    v100 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, unsigned int *))(v57 + 144))(
            a2,
            L"AudioQualityMode",
            0,
            &v100) )
      return 2147500037LL;
    v58 = v100;
    if ( v100 > 2 )
    {
      v58 = 0;
      v100 = 0;
    }
    *((_DWORD *)this + 11411) = v58;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const wchar_t *, unsigned __int16 *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"AudioPlaybackDevice",
            L"default",
            v113,
            128) )
      return 2147500037LL;
    StringCchCopyW((unsigned __int16 *)this + 22824, 0x80u, v113);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const wchar_t *, unsigned __int16 *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"AudioCaptureDevice",
            L"default",
            v114,
            128) )
      return 2147500037LL;
    StringCchCopyW((unsigned __int16 *)this + 22952, 0x80u, v114);
    RegistryInt = CUT::UT_ReadRegistryInt(&pszPassword, L"AllowMultipleAudioDevices", 0, 2);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"AllowMultipleAudioDevices",
            RegistryInt,
            (char *)this + 217184) )
      return 2147500037LL;
    *((_DWORD *)this + 54297) = CUT::UT_ReadRegistryInt(&pszPassword, L"SyncServerDefaultAudioDevice", 0, 2);
    v60 = *(_QWORD *)a2;
    v101 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, int *))(v60 + 144))(
            a2,
            L"connection type",
            7,
            &v101) )
      return 2147500037LL;
    v61 = v101;
    if ( (unsigned int)(v101 - 1) > 6 )
    {
      v61 = 7;
      v101 = 7;
    }
    *((_DWORD *)this + 16493) = v61;
    v62 = *(_QWORD *)a2;
    v108 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, int *))(v62 + 168))(
            a2,
            L"NetworkAutodetect",
            1,
            &v108) )
      return 2147500037LL;
    *((_DWORD *)this + 51533) = v108;
    v63 = *(_QWORD *)a2;
    v109 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, int *))(v63 + 168))(
            a2,
            L"BandwidthAutodetect",
            1,
            &v109) )
      return 2147500037LL;
    *((_DWORD *)this + 51534) = v109;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"DisableConnectionSharing",
            0,
            (char *)this + 60) )
      return 2147500037LL;
    memset_0((char *)this + 620, 0, 0x400u);
    memset_0((char *)this + 3692, 0, 0x400u);
    memset_0((char *)this + 29620, 0, 0x208u);
    memset_0((char *)this + 12056, 0, 0x208u);
    memset_0((char *)this + 30140, 0, 0x208u);
    memset_0((char *)this + 29096, 0, 0x208u);
    *((_DWORD *)this + 7404) = 0;
    if ( !*((_DWORD *)this + 51529)
      && !(unsigned int)CTscSettings::ReadPassword(this, a2)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v64 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v64);
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Alternate Shell",
            &pszPassword,
            (char *)this + 29620,
            260) )
      return 2147500037LL;
    if ( *((_DWORD *)this + 51002) && _wcsicmp((const wchar_t *)this + 14810, L"rdpinit.exe") )
      memset_0((char *)this + 29620, 0, 0x208u);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Shell Working Directory",
            &pszPassword,
            (char *)this + 30140,
            260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Workspace Id",
            &pszPassword,
            (char *)this + 29096,
            260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"EnableWorkspaceReconnect",
            0,
            (char *)this + 29616) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationProgram",
            &pszPassword,
            (char *)this + 12056,
            260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RemoteApplicationMode",
            0,
            (char *)this + 6260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationName",
            &pszPassword,
            (char *)this + 6280,
            256) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const char *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationIcon",
            &pszPassword,
            (char *)this + 6792,
            260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationGuid",
            &pszPassword,
            (char *)this + 7312,
            64) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationFile",
            &pszPassword,
            (char *)this + 7440,
            260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationFileExtensions",
            &pszPassword,
            (char *)this + 7960,
            2048) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RemoteApplicationExpandWorkingdir",
            0,
            (char *)this + 6264) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationCmdLine",
            &pszPassword,
            (char *)this + 12576,
            8000) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RemoteApplicationExpandCmdLine",
            1,
            (char *)this + 6268) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"DisableRemoteAppCapsCheck",
            0,
            (char *)this + 6272) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"RemoteApplicationAppID",
            &pszPassword,
            (char *)this + 28576,
            260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const unsigned __int16 *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RemoteAppMouseMoveInject",
            1,
            (char *)this + 6276) )
      return 2147500037LL;
    *((_DWORD *)this + 1563) = *((_WORD *)this + 14810) != 0;
    v65 = *(_QWORD *)a2;
    v102 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, unsigned int *))(v65 + 144))(
            a2,
            L"PrintingProgressMode",
            1,
            &v102) )
      return 2147500037LL;
    v66 = v102;
    if ( v102 > 2 )
    {
      v66 = 1;
      v102 = 1;
    }
    *((_DWORD *)this + 50858) = v66;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v67 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v67, v66);
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"SmartRawPrinters",
            &pszPassword,
            (char *)this + 215136,
            1024) )
      return 2147500037LL;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v68 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        v68,
        (__int64)this + 215136);
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Compression",
            1,
            (char *)this + 52) )
      return 2147500037LL;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v69 = *((_DWORD *)this + 13);
      v70 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v70, v69);
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"BitmapCacheSize",
            1500,
            (char *)this + 46192) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"BitmapPersistCacheSize",
            10,
            (char *)this + 46196) )
      return 2147500037LL;
    v71 = (_DWORD *)((char *)this + 46200);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"BitmapPersistCache16Size",
            20,
            (char *)this + 46200) )
      return 2147500037LL;
    v72 = (_DWORD *)((char *)this + 46204);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"BitmapPersistCache24Size",
            30,
            (char *)this + 46204)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"BitmapPersistCache32Size",
            40,
            (char *)this + 46208) )
    {
      return 2147500037LL;
    }
    v73 = CUT::UT_ReadRegistryInt(&pszPassword, L"BitmapPersistCacheSize", *((unsigned int *)this + 11549), 2);
    v74 = (unsigned int)*v71;
    *((_DWORD *)this + 11549) = v73;
    v75 = CUT::UT_ReadRegistryInt(&pszPassword, L"BitmapPersistCache16Size", v74, 2);
    v76 = (unsigned int)*v72;
    *v71 = v75;
    v77 = CUT::UT_ReadRegistryInt(&pszPassword, L"BitmapPersistCache24Size", v76, 2);
    v78 = *((unsigned int *)this + 11552);
    *v72 = v77;
    v79 = CUT::UT_ReadRegistryInt(&pszPassword, L"BitmapPersistCache32Size", v78, 2);
    *((_DWORD *)this + 11552) = v79;
    if ( *((_DWORD *)this + 11549) > 0x30u )
      *((_DWORD *)this + 11549) = 48;
    if ( *v71 > 0x30u )
      *v71 = 48;
    if ( *v72 > 0x30u )
      *v72 = 48;
    if ( v79 > 0x30 )
      *((_DWORD *)this + 11552) = 48;
    *(_OWORD *)((char *)this + 46220) = 0;
    *(_QWORD *)((char *)this + 46236) = 0;
    CUT::UT_ReadRegistryStringCb(&pszPassword, L"Keyboard Layout", L"0xffffffff", (char *)this + 46220, 24, 2);
    UserNameFromStore = StringCchCopyW(v111, 0xCu, (const unsigned __int16 *)this + 23110);
    if ( UserNameFromStore < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)UserNameFromStore;
      }
      v82 = RdpWppGetCurrentThreadActivityIdPrefix();
      v83 = 40;
      v84 = "StringCchCopy failed";
LABEL_256:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v83,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        v82,
        (__int64)v84,
        UserNameFromStore);
      return (unsigned int)UserNameFromStore;
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, unsigned __int16 *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Keyboard Layout",
            v111,
            (char *)this + 46220,
            v81) )
      return 2147500037LL;
    memset_0((char *)this + 54500, 0, 0x1450u);
    CSH::SH_GetPluginDllList(v85, L"Addins", (unsigned __int16 *)this + 27250, 0xA28u, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v86 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        v86,
        (__int64)this + 54500);
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectDrives",
            0,
            (char *)this + 46244) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectPrinters",
            1,
            (char *)this + 46248) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectLocation",
            0,
            (char *)this + 46252) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectCOMPorts",
            0,
            (char *)this + 46256) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectSmartCards",
            1,
            (char *)this + 46260) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectWebAuthn",
            1,
            (char *)this + 46288) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectTextProcessing",
            1,
            (char *)this + 46292) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectClipboard",
            1,
            (char *)this + 46264) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"ManualClipboardSync",
            0,
            (char *)this + 46268) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"RedirectPOSDevices",
            0,
            (char *)this + 46284) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"SawVmConnect",
            0,
            (char *)this + 46296) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"CamerasToRedirect",
            &pszPassword,
            (char *)this + 52444,
            1024) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Encode Redirected Video Capture",
            1,
            (char *)this + 54492) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"Redirected Video Capture Encoding Quality",
            0,
            (char *)this + 54496) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"DevicesToRedirect",
            &pszPassword,
            (char *)this + 46300,
            1024) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"UsbDevicesToRedirect",
            &pszPassword,
            (char *)this + 48348,
            1024) )
      return 2147500037LL;
    v87 = *(_QWORD *)a2;
    v103 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, unsigned int *))(v87 + 144))(
            a2,
            L"RedirectUsbDrive",
            0,
            &v103) )
      return 2147500037LL;
    v88 = v103;
    if ( v103 > 2 )
    {
      v88 = 0;
      v103 = 0;
    }
    *((_DWORD *)this + 53783) = v88;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"DrivesToRedirect",
            L"-",
            (char *)this + 50396,
            1024) )
      return 2147500037LL;
    CTscSettings::LoadRedirectedDrivesAndDevices(this);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"DisplayConnectionBar",
            1,
            (char *)this + 65944)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"AutoReconnection Enabled",
            1,
            (char *)this + 65960)
      || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"AutoReconnect Max Retries",
            5,
            (char *)this + 65964) )
    {
      return 2147500037LL;
    }
    if ( !(unsigned int)CTscSettings::ReadPerfOptions(this, a2) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147500037LL;
      }
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      v42 = 42;
      goto LABEL_306;
    }
    memset_0((char *)this + 205076, 0, 0x208u);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"ClxCommandLine",
            &pszPassword,
            (char *)this + 205076,
            260) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147500037LL;
      }
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      v42 = 43;
      goto LABEL_306;
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"HvSocketEnabled",
            0,
            (char *)this + 201340) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147500037LL;
      }
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      v42 = 44;
      goto LABEL_306;
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"HvSocketServiceId",
            &pszPassword,
            (char *)this + 201212,
            64) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147500037LL;
      }
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      v42 = 45;
LABEL_306:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids, v41);
      return 2147500037LL;
    }
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"GatewayHostname",
            &pszPassword,
            (char *)this + 65976,
            256) )
      return 2147500037LL;
    v89 = (_DWORD *)((char *)this + 66488);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"GatewayUsageMethod",
            4,
            (char *)this + 66488) )
      return 2147500037LL;
    if ( *v89 > 4u )
      *v89 = 4;
    v90 = (_DWORD *)((char *)this + 66492);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"GatewayCredentialsSource",
            4,
            (char *)this + 66492) )
      return 2147500037LL;
    if ( *v90 > 6u )
      *v90 = 4;
    v91 = (_DWORD *)((char *)this + 66496);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"GatewayProfileUsageMethod",
            0,
            (char *)this + 66496) )
      return 2147500037LL;
    if ( *v91 > 1u )
      *v91 = 4;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"Require pre-authentication",
            0,
            (char *)this + 66504) )
      return 2147500037LL;
    if ( *((_DWORD *)this + 16626) > 1u )
      *v91 = 0;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Pre-authentication server address",
            &pszPassword,
            (char *)this + 66508,
            256) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Cookie based authentication server address",
            &pszPassword,
            (char *)this + 67552,
            256) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Support URL",
            &pszPassword,
            (char *)this + 67020,
            256) )
      return 2147500037LL;
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"Login web page address",
            &pszPassword,
            (char *)this + 68080,
            256) )
      return 2147500037LL;
    v92 = (_DWORD *)((char *)this + 69624);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"GatewayBrokeringType",
            0,
            (char *)this + 69624) )
      return 2147500037LL;
    if ( *v92 > 1u )
      *v92 = 0;
    v93 = (_DWORD *)((char *)this + 66500);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 144LL))(
            a2,
            L"PromptCredentialOnce",
            0,
            (char *)this + 66500) )
      return 2147500037LL;
    if ( *v93 > 1u )
      *v93 = 1;
    (*(void (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
      a2,
      L"GatewayCertificateLogonAuthority",
      &pszPassword,
      (char *)this + 200700,
      256);
    if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
            a2,
            L"Span Monitors",
            0,
            (char *)this + 201348) )
      return 2147500037LL;
    v94 = (_DWORD *)((char *)this + 201356);
    if ( *((_DWORD *)this + 1565) )
    {
      *v94 = 1;
      memset_0((char *)this + 201364, 0, 0x800u);
    }
    else if ( !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 168LL))(
                 a2,
                 L"Use Multimon",
                 0,
                 v94)
           || !(*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
                 a2,
                 L"SelectedMonitors",
                 &pszPassword,
                 (char *)this + 201364,
                 1024) )
    {
      return 2147500037LL;
    }
    if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 168LL))(
           a2,
           L"Show RemoteEdgeBar",
           1,
           (char *)this + 206660) )
    {
      if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
             a2,
             L"EnableSuperPan",
             0,
             (char *)this + 203412) )
      {
        if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
               a2,
               L"DisableSeamlessLanguageBar",
               0,
               (char *)this + 206664) )
        {
          CTscSettings::SetEnableSuperPan(this, *((_DWORD *)this + 50853));
          if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, __int64, char *))(*(_QWORD *)a2 + 144LL))(
                 a2,
                 L"SuperPanAccelerationFactor",
                 1,
                 (char *)this + 203416) )
          {
            if ( *((_DWORD *)this + 1565) )
              CTscSettings::SetEnableSuperPan(this, 0);
            if ( *((_QWORD *)this + 4678) )
              *((_DWORD *)this + 7665) = *((_DWORD *)this + 51530) == 0;
            UserNameFromStore = CTscSettings::LoadUserNameFromStore(this, a2);
            if ( UserNameFromStore < 0 )
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                return (unsigned int)UserNameFromStore;
              }
              v82 = RdpWppGetCurrentThreadActivityIdPrefix();
              v83 = 46;
              v84 = "LoadUserNameFromStore failed";
              goto LABEL_256;
            }
            if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
                   a2,
                   L"PCB",
                   &pszPassword,
                   (char *)this + 211122,
                   2000) )
            {
              if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
                     a2,
                     L"Use Redirection Server Name",
                     0,
                     (char *)this + 203436) )
              {
                if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
                       a2,
                       L"RDGIsKDCProxy",
                       0,
                       (char *)this + 206140) )
                {
                  if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
                         a2,
                         L"KDCProxyName",
                         &pszPassword,
                         (char *)this + 206144,
                         256) )
                  {
                    *((_DWORD *)this + 51664) = CUT::UT_ReadRegistryInt(&pszPassword, L"ConnectToChildSession", 0, 2);
                    *((_DWORD *)this + 51667) = CUT::UT_ReadRegistryInt(
                                                  &pszPassword,
                                                  L"SetClientProtocolSpecMode",
                                                  0,
                                                  2);
                    if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
                           a2,
                           L"StaticCorrelationId",
                           &pszPassword,
                           (char *)this + 206672,
                           40) )
                    {
                      if ( (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
                             a2,
                             L"DiagnosticsInfo",
                             &pszPassword,
                             (char *)this + 206752,
                             100)
                        && (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, const WCHAR *, char *, int))(*(_QWORD *)a2 + 104LL))(
                             a2,
                             L"diagnosticserviceurl",
                             &pszPassword,
                             (char *)this + 206952,
                             2085)
                        && (*(unsigned int (__fastcall **)(struct ITsSettingsStore *, const wchar_t *, _QWORD, char *))(*(_QWORD *)a2 + 168LL))(
                             a2,
                             L"AllowRelativeMouseMode",
                             0,
                             (char *)this + 215128) )
                      {
                        CTscSettings::LoadSignatureSettings(this, a2);
                        return 0;
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
    return 2147500037LL;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140037188  mov     [rsp-8+arg_10], rbx
0x14003718d  push    rbp
0x14003718e  push    rsi
0x14003718f  push    rdi
0x140037190  push    r12
0x140037192  push    r13
0x140037194  push    r14
0x140037196  push    r15
0x140037198  lea     rbp, [rsp-7E0h]
0x1400371a0  sub     rsp, 8E0h
0x1400371a7  mov     rax, cs:__security_cookie
0x1400371ae  xor     rax, rsp
0x1400371b1  mov     [rbp+810h+var_40], rax
0x1400371b8  xor     ebx, ebx
0x1400371ba  mov     rdi, rdx
0x1400371bd  mov     rsi, rcx
0x1400371c0  test    rdx, rdx
0x1400371c3  jnz     short loc_140037202
0x1400371c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371cc  lea     r15, WPP_GLOBAL_Control
0x1400371d3  cmp     rcx, r15
0x1400371d6  jz      short loc_1400371FB
0x1400371d8  lea     r14d, [rdx+1]
0x1400371dc  test    [rcx+1Ch], r14b
0x1400371e0  jz      short loc_1400371FB
0x1400371e2  cmp     [rcx+19h], r14b
0x1400371e6  jb      short loc_1400371FB
0x1400371e8  mov     rcx, [rcx+10h]
0x1400371ec  lea     edx, [rdi+12h]
0x1400371ef  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x1400371f6  call    WPP_SF_
0x1400371fb  mov     eax, 80070057h
0x140037200  jmp     short loc_140037250
0x140037202  mov     rax, [rdx]
0x140037205  mov     rcx, rdi
0x140037208  mov     rax, [rax+40h]
0x14003720c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037211  test    eax, eax
0x140037213  jnz     short loc_14003727A
0x140037215  mov     rcx, cs:WPP_GLOBAL_Control
0x14003721c  lea     r15, WPP_GLOBAL_Control
0x140037223  cmp     rcx, r15
0x140037226  jz      short loc_14003724B
0x140037228  lea     r14d, [rax+1]
0x14003722c  test    [rcx+1Ch], r14b
0x140037230  jz      short loc_14003724B
0x140037232  cmp     [rcx+19h], r14b
0x140037236  jb      short loc_14003724B
0x140037238  mov     rcx, [rcx+10h]
0x14003723c  lea     edx, [rax+13h]
0x14003723f  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140037246  call    WPP_SF_
0x14003724b  mov     eax, 80004005h
0x140037250  mov     rcx, [rbp+810h+var_40]
0x140037257  xor     rcx, rsp; StackCookie
0x14003725a  call    __security_check_cookie
0x14003725f  mov     rbx, [rsp+910h+arg_10]
0x140037267  add     rsp, 8E0h
0x14003726e  pop     r15
0x140037270  pop     r14
0x140037272  pop     r13
0x140037274  pop     r12
0x140037276  pop     rdi
0x140037277  pop     rsi
0x140037278  pop     rbp
0x140037279  retn
0x14003727a  mov     r15d, 2
0x140037280  lea     r14, pszPassword
0x140037287  mov     r9d, r15d
0x14003728a  lea     rdx, aDisableprinter; "DisablePrinterRedirection"
0x140037291  mov     rcx, r14
0x140037294  xor     r8d, r8d
0x140037297  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x14003729c  mov     r9d, r15d
0x14003729f  mov     [rsi+32530h], eax
0x1400372a5  xor     r8d, r8d
0x1400372a8  lea     rdx, aDisableclipboa; "DisableClipboardRedirection"
0x1400372af  mov     rcx, r14
0x1400372b2  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x1400372b7  mov     r9d, r15d
0x1400372ba  mov     [rsi+3252Ch], eax
0x1400372c0  xor     r8d, r8d
0x1400372c3  lea     rdx, aEnablelocation; "EnableLocationSimulation"
0x1400372ca  mov     rcx, r14
0x1400372cd  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x1400372d2  mov     [rsi+101B0h], eax
0x1400372d8  lea     r9, [rsp+910h+var_8AC]
0x1400372dd  mov     rax, [rdi]
0x1400372e0  lea     rdx, aPublicMode; "Public Mode"
0x1400372e7  xor     r8d, r8d
0x1400372ea  mov     [rsp+910h+var_8AC], ebx
0x1400372ee  mov     rcx, rdi
0x1400372f1  mov     rax, [rax+0A8h]
0x1400372f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400372fd  test    eax, eax
0x1400372ff  jz      loc_14003724B
0x140037305  lea     r14d, [r15-1]
0x140037309  cmp     [rsp+910h+var_8AC], ebx
0x14003730d  jz      short loc_140037316
0x14003730f  mov     [rsi+32524h], r14d
0x140037316  mov     rax, [rdi]
0x140037319  lea     r9, [rsp+910h+var_8A8]
0x14003731e  xor     r8d, r8d
0x140037321  mov     [rsp+910h+var_8A8], ebx
0x140037325  lea     rdx, aScreenModeId; "Screen Mode ID"
0x14003732c  mov     rcx, rdi
0x14003732f  mov     rax, [rax+90h]
0x140037336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003733b  test    eax, eax
0x14003733d  jz      loc_14003724B
0x140037343  mov     ecx, [rsp+910h+var_8A8]
0x140037347  test    ecx, ecx
0x140037349  jnz     short loc_140037383
0x14003734b  mov     rax, [rdi]
0x14003734e  lea     r9, [rsp+910h+var_8D0]
0x140037353  or      r15d, 0FFFFFFFFh
0x140037357  mov     [rsp+910h+var_8D0], ebx
0x14003735b  mov     r8d, r15d
0x14003735e  lea     rdx, aDesktopSizeId; "Desktop Size ID"
0x140037365  mov     rcx, rdi
0x140037368  mov     rax, [rax+90h]
0x14003736f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037374  test    eax, eax
0x140037376  jz      loc_14003724B
0x14003737c  cmp     [rsp+910h+var_8D0], r15d
0x140037381  jmp     short loc_140037386
0x140037383  cmp     ecx, r15d
0x140037386  mov     eax, ebx
0x140037388  mov     dword ptr [rsp+910h+var_8F0], 100h
0x140037390  setz    al
0x140037393  lea     r9, [rbp+810h+Buffer]
0x14003739a  mov     rcx, rsi
0x14003739d  lea     r8, a0300800600; "0,3,0,0,800,600"
0x1400373a4  lea     rdx, aWinposstr; "WinPosStr"
0x1400373ab  mov     [rcx+31280h], eax
0x1400373b1  mov     rcx, rdi
0x1400373b4  mov     rax, [rdi]
0x1400373b7  mov     rax, [rax+68h]
0x1400373bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400373c0  test    eax, eax
0x1400373c2  jz      loc_14003724B
0x1400373c8  mov     rax, cs:WPP_GLOBAL_Control
0x1400373cf  lea     r15, WPP_GLOBAL_Control
0x1400373d6  lea     r12, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x1400373dd  cmp     rax, r15
0x1400373e0  jz      short loc_14003741A
0x1400373e2  test    [rax+1Ch], r14b
0x1400373e6  jz      short loc_14003741A
0x1400373e8  cmp     byte ptr [rax+19h], 4
0x1400373ec  jb      short loc_14003741A
0x1400373ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400373f3  lea     rcx, [rbp+810h+Buffer]
0x1400373fa  mov     edx, 14h
0x1400373ff  mov     [rsp+910h+var_8F0], rcx
0x140037404  mov     r9d, eax
0x140037407  mov     rcx, cs:WPP_GLOBAL_Control
0x14003740e  mov     r8, r12
0x140037411  mov     rcx, [rcx+10h]
0x140037415  call    WPP_SF_DS
0x14003741a  lea     rbx, [rsi+5Ch]
0x14003741e  lea     rcx, [rbx+0Ch]
0x140037422  mov     [rsp+910h+var_8D8], rcx
0x140037427  lea     rdx, [rbx+8]
0x14003742b  mov     [rsp+910h+var_8E0], rdx
0x140037430  lea     r8, [rbx+4]
0x140037434  mov     [rsp+910h+var_8E8], r8
0x140037439  lea     r13, [rsi+44h]
0x14003743d  mov     r8, r13
0x140037440  mov     [rsp+910h+var_8F0], rbx
0x140037445  lea     r9, [rsi+48h]
0x140037449  lea     rdx, aUUDDDD; "%u,%u,%d,%d,%d,%d"
0x140037450  lea     rcx, [rbp+810h+Buffer]; Buffer
0x140037457  call    cs:__imp_swscanf_s
0x14003745d  mov     [rsp+910h+var_8D0], eax
0x140037461  cmp     eax, 6
0x140037464  jz      loc_140037532
0x14003746a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037471  cmp     rcx, r15
0x140037474  jz      short loc_1400374E2
0x140037476  test    [rcx+1Ch], r14b
0x14003747a  jz      short loc_1400374A1
0x14003747c  cmp     [rcx+19h], r14b
0x140037480  jb      short loc_1400374A1
0x140037482  mov     rcx, [rcx+10h]
0x140037486  lea     r9, [rbp+810h+Buffer]
0x14003748d  mov     edx, 15h
0x140037492  mov     r8, r12
0x140037495  call    WPP_SF_S
0x14003749a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400374a1  cmp     rcx, r15
0x1400374a4  jz      short loc_1400374E2
0x1400374a6  test    [rcx+1Ch], r14b
0x1400374aa  jz      short loc_1400374E2
0x1400374ac  cmp     byte ptr [rcx+19h], 5
0x1400374b0  jb      short loc_1400374E2
0x1400374b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400374b7  mov     ecx, [rsp+910h+var_8D0]
0x1400374bb  mov     edx, 16h
0x1400374c0  mov     dword ptr [rsp+910h+var_8E8], 6
0x1400374c8  mov     r9d, eax
0x1400374cb  mov     dword ptr [rsp+910h+var_8F0], ecx
0x1400374cf  mov     r8, r12
0x1400374d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400374d9  mov     rcx, [rcx+10h]
0x1400374dd  call    WPP_SF_DLD
0x1400374e2  movups  xmm0, xmmword ptr cs:a0300800600; "0,3,0,0,800,600"
0x1400374e9  lea     rax, [rbx+0Ch]
0x1400374ed  mov     r8, r13
0x1400374f0  movups  xmm1, xmmword ptr cs:a0300800600+10h; "800,600"
0x1400374f7  mov     [rsp+910h+var_8D8], rax
0x1400374fc  lea     r9, [rsi+48h]
0x140037500  lea     rax, [rbx+8]
0x140037504  mov     [rsp+910h+var_8E0], rax
0x140037509  lea     rdx, aUUDDDD; "%u,%u,%d,%d,%d,%d"
0x140037510  lea     rax, [rbx+4]
0x140037514  mov     [rsp+910h+var_8E8], rax
0x140037519  lea     rcx, [rbp+810h+var_890]; Buffer
0x14003751d  mov     [rsp+910h+var_8F0], rbx
0x140037522  movups  xmmword ptr [rbp+810h+var_890], xmm0
0x140037526  movups  [rbp+810h+var_880], xmm1
0x14003752a  call    cs:__imp_swscanf_s
0x140037530  jmp     short loc_14003756A
0x140037532  mov     rax, cs:WPP_GLOBAL_Control
0x140037539  cmp     rax, r15
0x14003753c  jz      short loc_14003756A
0x14003753e  test    [rax+1Ch], r14b
0x140037542  jz      short loc_14003756A
0x140037544  cmp     byte ptr [rax+19h], 5
0x140037548  jb      short loc_14003756A
0x14003754a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003754f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037556  mov     edx, 17h
0x14003755b  mov     r9d, eax
0x14003755e  mov     r8, r12
0x140037561  mov     rcx, [rcx+10h]
0x140037565  call    WPP_SF_d
0x14003756a  mov     eax, [r13+0]
0x14003756e  xor     ecx, ecx
0x140037570  mov     dword ptr [rsi+40h], 2Ch ; ','
0x140037577  mov     [rsp+910h+var_8D0], eax
0x14003757b  test    eax, eax
0x14003757d  jz      short loc_1400375C5
0x14003757f  mov     rax, cs:WPP_GLOBAL_Control
0x140037586  cmp     rax, r15
0x140037589  jz      short loc_1400375C1
0x14003758b  test    [rax+1Ch], r14b
0x14003758f  jz      short loc_1400375C1
0x140037591  cmp     byte ptr [rax+19h], 5
0x140037595  jb      short loc_1400375C1
0x140037597  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003759c  mov     ecx, [rsp+910h+var_8D0]
0x1400375a0  mov     edx, 18h
0x1400375a5  mov     dword ptr [rsp+910h+var_8F0], ecx
0x1400375a9  mov     r9d, eax
0x1400375ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400375b3  mov     r8, r12
0x1400375b6  mov     rcx, [rcx+10h]
0x1400375ba  call    WPP_SF_Dd
0x1400375bf  xor     ecx, ecx
0x1400375c1  mov     [r13+0], ecx
0x1400375c5  mov     eax, [rsi+48h]
0x1400375c8  mov     [rsp+910h+var_8D0], eax
0x1400375cc  dec     eax
0x1400375ce  test    eax, 0FFFFFFFDh
0x1400375d3  jz      short loc_140037620
0x1400375d5  mov     rax, cs:WPP_GLOBAL_Control
0x1400375dc  cmp     rax, r15
0x1400375df  jz      short loc_14003761C
0x1400375e1  test    [rax+1Ch], r14b
0x1400375e5  jz      short loc_14003761C
0x1400375e7  cmp     byte ptr [rax+19h], 5
0x1400375eb  jb      short loc_14003761C
0x1400375ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400375f2  mov     ecx, [rsp+910h+var_8D0]
0x1400375f6  mov     edx, 19h
0x1400375fb  mov     dword ptr [rsp+910h+var_8E8], r14d
0x140037600  mov     r9d, eax
0x140037603  mov     dword ptr [rsp+910h+var_8F0], ecx
0x140037607  mov     r8, r12
0x14003760a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037611  mov     rcx, [rcx+10h]
0x140037615  call    WPP_SF_DLD
0x14003761a  xor     ecx, ecx
0x14003761c  mov     [rsi+48h], r14d
0x140037620  mov     eax, [rsi+64h]
0x140037623  mov     edx, 0C8h
0x140037628  sub     eax, [rbx]
0x14003762a  cmp     eax, edx
0x14003762c  jge     short loc_140037637
0x14003762e  mov     [rbx], ecx
0x140037630  mov     dword ptr [rsi+64h], 320h
0x140037637  mov     eax, [rsi+68h]
0x14003763a  sub     eax, [rsi+60h]
0x14003763d  cmp     eax, edx
0x14003763f  jge     short loc_14003764B
0x140037641  mov     [rsi+60h], ecx
0x140037644  mov     dword ptr [rsi+68h], 258h
0x14003764b  mov     rax, [rdi]
0x14003764e  lea     r13, [rsi+7E1Ch]
0x140037655  mov     r9, r13
  ... truncated ...
```
