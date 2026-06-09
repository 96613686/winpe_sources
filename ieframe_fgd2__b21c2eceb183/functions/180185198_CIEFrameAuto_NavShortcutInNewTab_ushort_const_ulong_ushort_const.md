# CIEFrameAuto::_NavShortcutInNewTab(ushort const *,ulong,ushort const *)

- ea: `0x180185198`
- end: `0x18018587d`
- name: `?_NavShortcutInNewTab@CIEFrameAuto@@IEAAJPEBGK0@Z`
- size: `1765`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180184d0c`

## callees

- `0x18000b9e0`
- `0x180030340`
- `0x180104e3c`
- `0x180185198`
- `0x180185884`
- `0x1801ef0e8`
- `0x1801ef4e0`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180185297`
- `KERNEL32!GetCurrentProcessId` at `0x180185297`
- `USER32!AllowSetForegroundWindow` at `0x18018541e`
- `USER32!AllowSetForegroundWindow` at `0x1801855d9`
- `USER32!AllowSetForegroundWindow` at `0x18018541e`
- `USER32!AllowSetForegroundWindow` at `0x1801855d9`
- `ole32!CoAllowSetForegroundWindow` at `0x1801857a2`
- `ole32!CoAllowSetForegroundWindow` at `0x1801857a2`
- `SHELL32!__imp_ILFree` at `0x180185251`
- `SHELL32!__imp_ILFree` at `0x1801857de`
- `SHELL32!__imp_ILFree` at `0x180185251`
- `SHELL32!__imp_ILFree` at `0x1801857de`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180185314`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801853e2`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18018550b`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180185314`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801853e2`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18018550b`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801852b7`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801852b7`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801852d1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801856c4`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801852d1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801856c4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801851f0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801851f0`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801852c0`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801854a7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180185665`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801852c0`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801854a7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180185665`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801852a2`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801852a2`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x180185269`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x180185269`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_NavShortcutInNewTab(
        CIEFrameAuto *this,
        const unsigned __int16 *a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4)
{
  IUnknown *v8; // rcx
  int v9; // r15d
  int active; // ebx
  int v11; // eax
  int v12; // esi
  int v13; // eax
  struct IEUserBroker *v14; // rcx
  DWORD v15; // ecx
  void (__fastcall *v16)(struct IEUserBroker *, LPITEMIDLIST *); // rbx
  int v17; // eax
  __int64 v18; // r9
  DWORD v19; // ecx
  void (__fastcall *v20)(struct IEUserBroker *, LPITEMIDLIST *); // rbx
  bool v21; // sf
  struct IEUserBroker *v23; // [rsp+40h] [rbp-C0h] BYREF
  struct IEUserBroker *v24; // [rsp+48h] [rbp-B8h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwProcessId[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *ppvOut; // [rsp+68h] [rbp-98h] BYREF
  int v28; // [rsp+70h] [rbp-90h] BYREF
  char v29; // [rsp+74h] [rbp-8Ch]
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v31[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v32; // [rsp+98h] [rbp-68h]
  _DWORD v33[10]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v34; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-20h]
  _BYTE v36[28]; // [rsp+F0h] [rbp-10h] BYREF

  v8 = (IUnknown *)*((_QWORD *)this + 66);
  v9 = 0;
  ppvOut = 0;
  active = IUnknown_QueryService(
             v8,
             (const GUID *const)&SID_STabWindowManager,
             &GUID_feefb420_9399_492d_969c_51af6dc38fb1,
             &ppvOut);
  if ( active >= 0 )
  {
    v30 = 0;
    v11 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvOut + 56LL))(ppvOut, &v30);
    pidl[0] = 0;
    if ( v11 < 0 )
    {
      active = IEParseDisplayNameWithBCW(0, a2, 0, pidl);
      if ( active >= 0 )
      {
        active = IEOpenNewFrame(pidl[0], 0, 0x80000000);
        if ( active >= 0 )
          active = 1;
      }
      goto LABEL_53;
    }
    if ( (*(int (__fastcall **)(__int64, LPITEMIDLIST *))(*(_QWORD *)v30 + 160LL))(v30, pidl) >= 0 )
    {
      v9 = 1;
      ILFree(pidl[0]);
    }
    v28 = 0;
    v29 = 0;
    active = IsRedirectToBrokerNeeded(a4, (const struct tagRedirectionPolicyFlags *)&v28);
    if ( active )
    {
      if ( IsDualEngineProcess() )
      {
        memset(v36, 0, sizeof(v36));
        v34 = 0;
        v35 = 0;
        LODWORD(v34) = DualEngine::GetOpenerCookie();
        pidl[0] = 0;
        DWORD2(v34) = (a3 >> 3) & 1;
        active = IEParseDisplayNameWithBCW(0, a2, 0, pidl);
        if ( active >= 0 )
        {
          active = SHOpenNewFrame_SendToFrameProcess(
                     pidl[0],
                     0,
                     (struct __MIDL___MIDL_itf_iebroker_0000_0021_0001 *)&v34);
          v21 = active < 0;
          goto LABEL_47;
        }
      }
      else if ( active == 1 )
      {
        if ( v9 )
        {
          pidl[0] = 0;
          active = IEParseDisplayNameWithBCW(0, a2, 0, pidl);
          if ( active >= 0 )
          {
            dwProcessId[0] = 0;
            memset_0(v31, 0, 0x48u);
            BYTE3(v31[0]) = 1;
            if ( (a3 & 8) != 0 )
            {
              BYTE1(v31[0]) = 1;
            }
            else
            {
              BYTE6(v31[0]) = 1;
              CoAllowSetForegroundWindow((IUnknown *)ppvOut, 0);
            }
            active = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, __int64, _QWORD *, _QWORD, DWORD *))(*(_QWORD *)ppvOut + 24LL))(
                       ppvOut,
                       pidl[0],
                       0x80000000LL,
                       v31,
                       0,
                       dwProcessId);
            ILFree(pidl[0]);
            goto LABEL_46;
          }
        }
        else
        {
          active = CIEFrameAuto::_NavShortcutOverActiveWindow(this, a2, a3, a4, 1);
        }
      }
LABEL_53:
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v30);
      goto LABEL_54;
    }
    memset(v33, 0, 28);
    memset(v31, 0, sizeof(v31));
    v32 = 0;
    LODWORD(v32) = GetCurrentProcessId();
    *(_QWORD *)((char *)&v32 + 4) = IsoGetIntegrity(1) & 0x7F;
    v33[0] = IEConfiguration_GetDWORD(536870929);
    v12 = a3 & 8;
    *(_OWORD *)&v33[3] = *(_OWORD *)GlobalThreadState();
    if ( IsDualEngineProcess() )
    {
      memset(v36, 0, sizeof(v36));
      v34 = 0;
      v35 = 0;
      LODWORD(v34) = DualEngine::GetOpenerCookie();
      v23 = 0;
      if ( v12 )
      {
        DWORD2(v34) = 1;
        *(_QWORD *)dwProcessId = 0;
        active = CoCreateUserBroker(&v23);
        if ( active < 0 )
          goto LABEL_53;
        v24 = 0;
        active = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, struct IEUserBroker **))(*(_QWORD *)v23 + 48LL))(
                   v23,
                   &CLSID_CShdocvwBroker,
                   &IID_IUnknown,
                   &v24);
        if ( active >= 0 )
        {
          active = (**(__int64 (__fastcall ***)(struct IEUserBroker *, GUID *, DWORD *))v24)(
                     v24,
                     &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                     dwProcessId);
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v24 + 16LL))(v24);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v23 + 16LL))(v23);
        if ( active < 0 )
          goto LABEL_53;
        v13 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD *, __int128 *))(**(_QWORD **)dwProcessId + 40LL))(
                *(_QWORD *)dwProcessId,
                a2,
                a4,
                4096,
                v31,
                &v34);
        v14 = *(struct IEUserBroker **)dwProcessId;
        goto LABEL_35;
      }
      DWORD2(v34) = 0;
      v24 = 0;
      active = CoCreateUserBroker(&v24);
      if ( active < 0 )
        goto LABEL_53;
      dwProcessId[0] = 0;
      (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v24 + 24LL))(
        v24,
        0,
        0,
        dwProcessId);
      v15 = -1;
      if ( dwProcessId[0] )
        v15 = dwProcessId[0];
      AllowSetForegroundWindow(v15);
      pidl[0] = 0;
      active = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, LPITEMIDLIST *))(*(_QWORD *)v24 + 48LL))(
                 v24,
                 &CLSID_CShdocvwBroker,
                 &IID_IUnknown,
                 pidl);
      if ( active >= 0 )
      {
        active = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, struct IEUserBroker **))pidl[0])(
                   pidl[0],
                   &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                   &v23);
        (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)pidl[0] + 16LL))(pidl[0]);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v24 + 16LL))(v24);
      if ( active < 0 )
        goto LABEL_53;
      v16 = *(void (__fastcall **)(struct IEUserBroker *, LPITEMIDLIST *))(*(_QWORD *)v23 + 56LL);
      *(_OWORD *)pidl = *(_OWORD *)GlobalThreadState();
      v16(v23, pidl);
      v13 = (*(__int64 (__fastcall **)(struct IEUserBroker *, const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD *, __int128 *))(*(_QWORD *)v23 + 40LL))(
              v23,
              a2,
              a4,
              2048,
              v31,
              &v34);
    }
    else
    {
      v23 = 0;
      v24 = 0;
      v17 = CoCreateUserBroker(&v24);
      active = v17;
      if ( v12 )
      {
        if ( v17 < 0 )
          goto LABEL_53;
        pidl[0] = 0;
        active = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, LPITEMIDLIST *))(*(_QWORD *)v24 + 48LL))(
                   v24,
                   &CLSID_CShdocvwBroker,
                   &IID_IUnknown,
                   pidl);
        if ( active >= 0 )
        {
          active = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, struct IEUserBroker **))pidl[0])(
                     pidl[0],
                     &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                     &v23);
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)pidl[0] + 16LL))(pidl[0]);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( active < 0 )
          goto LABEL_53;
        v18 = 4096;
      }
      else
      {
        if ( v17 < 0 )
          goto LABEL_53;
        dwProcessId[0] = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v24 + 24LL))(
          v24,
          0,
          0,
          dwProcessId);
        v19 = -1;
        if ( dwProcessId[0] )
          v19 = dwProcessId[0];
        AllowSetForegroundWindow(v19);
        pidl[0] = 0;
        active = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, LPITEMIDLIST *))(*(_QWORD *)v24 + 48LL))(
                   v24,
                   &CLSID_CShdocvwBroker,
                   &IID_IUnknown,
                   pidl);
        if ( active >= 0 )
        {
          active = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, struct IEUserBroker **))pidl[0])(
                     pidl[0],
                     &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                     &v23);
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)pidl[0] + 16LL))(pidl[0]);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( active < 0 )
          goto LABEL_53;
        v20 = *(void (__fastcall **)(struct IEUserBroker *, LPITEMIDLIST *))(*(_QWORD *)v23 + 1256LL);
        *(_OWORD *)pidl = *(_OWORD *)GlobalThreadState();
        v20(v23, pidl);
        v18 = 2048;
      }
      v13 = (*(__int64 (__fastcall **)(struct IEUserBroker *, const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD *))(*(_QWORD *)v23 + 32LL))(
              v23,
              a2,
              a4,
              v18,
              v31);
    }
    v14 = v23;
LABEL_35:
    active = v13;
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_46:
    v21 = active < 0;
LABEL_47:
    if ( !v21 )
      active = 1;
    goto LABEL_53;
  }
LABEL_54:
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppvOut);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x180185198  mov     [rsp-8+arg_10], rbx
0x18018519d  push    rbp
0x18018519e  push    rsi
0x18018519f  push    rdi
0x1801851a0  push    r12
0x1801851a2  push    r13
0x1801851a4  push    r14
0x1801851a6  push    r15
0x1801851a8  lea     rbp, [rsp-20h]
0x1801851ad  sub     rsp, 120h
0x1801851b4  mov     rax, cs:__security_cookie
0x1801851bb  xor     rax, rsp
0x1801851be  mov     [rbp+50h+var_40], rax
0x1801851c2  mov     r12, r9
0x1801851c5  mov     esi, r8d
0x1801851c8  mov     r14, rdx
0x1801851cb  lea     r9, [rsp+150h+ppvOut]; ppvOut
0x1801851d0  mov     r13, rcx
0x1801851d3  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1; riid
0x1801851da  mov     rcx, [rcx+210h]; punk
0x1801851e1  lea     rdx, SID_STabWindowManager; guidService
0x1801851e8  xor     r15d, r15d
0x1801851eb  mov     [rsp+150h+ppvOut], r15
0x1801851f0  call    cs:__imp_IUnknown_QueryService
0x1801851f6  mov     ebx, eax
0x1801851f8  test    eax, eax
0x1801851fa  js      loc_18018584A
0x180185200  mov     rcx, [rsp+150h+ppvOut]
0x180185205  lea     rdx, [rsp+150h+var_D8]
0x18018520a  mov     [rsp+150h+var_D8], r15
0x18018520f  mov     rax, [rcx]
0x180185212  mov     rax, [rax+38h]
0x180185216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018521b  mov     [rsp+150h+pidl], r15
0x180185220  test    eax, eax
0x180185222  js      loc_180185802
0x180185228  mov     rcx, [rsp+150h+var_D8]
0x18018522d  lea     rdx, [rsp+150h+pidl]
0x180185232  mov     rax, [rcx]
0x180185235  mov     rax, [rax+0A0h]
0x18018523c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185241  lea     edi, [r15+1]
0x180185245  test    eax, eax
0x180185247  js      short loc_180185257
0x180185249  mov     rcx, [rsp+150h+pidl]; pidl
0x18018524e  mov     r15d, edi
0x180185251  call    cs:__imp_ILFree
0x180185257  xor     eax, eax
0x180185259  lea     rdx, [rsp+150h+var_E0]
0x18018525e  mov     rcx, r12
0x180185261  mov     [rsp+150h+var_E0], eax
0x180185265  mov     [rsp+150h+var_DC], al
0x180185269  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x18018526f  mov     ebx, eax
0x180185271  test    eax, eax
0x180185273  jnz     loc_1801856C4
0x180185279  xorps   xmm0, xmm0
0x18018527c  xor     r15d, r15d
0x18018527f  movups  xmmword ptr [rbp+50h+var_A8], xmm0
0x180185283  mov     [rbp+50h+var_D0], r15
0x180185287  movups  xmmword ptr [rbp+50h+var_A8+0Ch], xmm0
0x18018528b  mov     [rbp+50h+var_C8], r15
0x18018528f  mov     [rbp+50h+var_C0], r15
0x180185293  movups  [rbp+50h+var_B8], xmm0
0x180185297  call    cs:__imp_GetCurrentProcessId
0x18018529d  mov     ecx, edi
0x18018529f  mov     dword ptr [rbp+50h+var_B8], eax
0x1801852a2  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1801852a8  mov     ecx, 20000011h
0x1801852ad  mov     dword ptr [rbp+50h+var_B8+8], r15d
0x1801852b1  and     eax, 7Fh
0x1801852b4  mov     dword ptr [rbp+50h+var_B8+4], eax
0x1801852b7  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801852bd  mov     [rbp+50h+var_A8], eax
0x1801852c0  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801852c6  and     esi, 8
0x1801852c9  movups  xmm0, xmmword ptr [rax]
0x1801852cc  movdqu  xmmword ptr [rbp+50h+var_A8+0Ch], xmm0
0x1801852d1  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801852d7  test    al, al
0x1801852d9  jz      loc_1801854FC
0x1801852df  xorps   xmm0, xmm0
0x1801852e2  movups  xmmword ptr [rbp+50h+var_60], xmm0
0x1801852e6  movups  xmmword ptr [rbp+50h+var_60+0Ch], xmm0
0x1801852ea  movups  [rbp+50h+var_80], xmm0
0x1801852ee  movups  [rbp+50h+var_70], xmm0
0x1801852f2  call    DualEngine__GetOpenerCookie
0x1801852f7  mov     dword ptr [rbp+50h+var_80], eax
0x1801852fa  mov     [rsp+150h+var_110], r15
0x1801852ff  test    esi, esi
0x180185301  jz      loc_1801853D4
0x180185307  lea     rcx, [rsp+150h+var_110]
0x18018530c  mov     dword ptr [rbp+50h+var_80+8], edi
0x18018530f  mov     qword ptr [rsp+150h+dwProcessId], r15
0x180185314  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18018531a  mov     ebx, eax
0x18018531c  test    eax, eax
0x18018531e  js      loc_180185840
0x180185324  mov     rcx, [rsp+150h+var_110]
0x180185329  lea     r9, [rsp+150h+var_108]
0x18018532e  mov     [rsp+150h+var_108], r15
0x180185333  lea     r8, IID_IUnknown
0x18018533a  lea     rdx, CLSID_CShdocvwBroker
0x180185341  mov     rax, [rcx]
0x180185344  mov     rax, [rax+30h]
0x180185348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018534d  mov     ebx, eax
0x18018534f  test    eax, eax
0x180185351  js      short loc_180185382
0x180185353  mov     rcx, [rsp+150h+var_108]
0x180185358  lea     r8, [rsp+150h+dwProcessId]
0x18018535d  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180185364  mov     rax, [rcx]
0x180185367  mov     rax, [rax]
0x18018536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018536f  mov     rcx, [rsp+150h+var_108]
0x180185374  mov     ebx, eax
0x180185376  mov     rax, [rcx]
0x180185379  mov     rax, [rax+10h]
0x18018537d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185382  mov     rcx, [rsp+150h+var_110]
0x180185387  mov     rax, [rcx]
0x18018538a  mov     rax, [rax+10h]
0x18018538e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185393  test    ebx, ebx
0x180185395  js      loc_180185840
0x18018539b  mov     rcx, qword ptr [rsp+150h+dwProcessId]
0x1801853a0  lea     rdx, [rbp+50h+var_80]
0x1801853a4  mov     [rsp+150h+var_128], rdx
0x1801853a9  mov     r9d, 1000h
0x1801853af  lea     rdx, [rbp+50h+var_D0]
0x1801853b3  mov     r8, r12
0x1801853b6  mov     [rsp+150h+var_130], rdx
0x1801853bb  mov     rdx, r14
0x1801853be  mov     rax, [rcx]
0x1801853c1  mov     rax, [rax+28h]
0x1801853c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801853ca  mov     rcx, qword ptr [rsp+150h+dwProcessId]
0x1801853cf  jmp     loc_1801856B1
0x1801853d4  lea     rcx, [rsp+150h+var_108]
0x1801853d9  mov     dword ptr [rbp+50h+var_80+8], r15d
0x1801853dd  mov     [rsp+150h+var_108], r15
0x1801853e2  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801853e8  mov     ebx, eax
0x1801853ea  test    eax, eax
0x1801853ec  js      loc_180185840
0x1801853f2  mov     rcx, [rsp+150h+var_108]
0x1801853f7  lea     r9, [rsp+150h+dwProcessId]
0x1801853fc  mov     [rsp+150h+dwProcessId], r15d
0x180185401  xor     r8d, r8d
0x180185404  xor     edx, edx
0x180185406  mov     rax, [rcx]
0x180185409  mov     rax, [rax+18h]
0x18018540d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185412  mov     eax, [rsp+150h+dwProcessId]
0x180185416  or      ecx, 0FFFFFFFFh
0x180185419  test    eax, eax
0x18018541b  cmovnz  ecx, eax; dwProcessId
0x18018541e  call    cs:__imp_AllowSetForegroundWindow
0x180185424  mov     rcx, [rsp+150h+var_108]
0x180185429  lea     r9, [rsp+150h+pidl]
0x18018542e  mov     [rsp+150h+pidl], r15
0x180185433  lea     r8, IID_IUnknown
0x18018543a  lea     rdx, CLSID_CShdocvwBroker
0x180185441  mov     rax, [rcx]
0x180185444  mov     rax, [rax+30h]
0x180185448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018544d  mov     ebx, eax
0x18018544f  test    eax, eax
0x180185451  js      short loc_180185482
0x180185453  mov     rcx, [rsp+150h+pidl]
0x180185458  lea     r8, [rsp+150h+var_110]
0x18018545d  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180185464  mov     rax, [rcx]
0x180185467  mov     rax, [rax]
0x18018546a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018546f  mov     rcx, [rsp+150h+pidl]
0x180185474  mov     ebx, eax
0x180185476  mov     rax, [rcx]
0x180185479  mov     rax, [rax+10h]
0x18018547d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185482  mov     rcx, [rsp+150h+var_108]
0x180185487  mov     rax, [rcx]
0x18018548a  mov     rax, [rax+10h]
0x18018548e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185493  test    ebx, ebx
0x180185495  js      loc_180185840
0x18018549b  mov     rax, [rsp+150h+var_110]
0x1801854a0  mov     rcx, [rax]
0x1801854a3  mov     rbx, [rcx+38h]
0x1801854a7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801854ad  mov     rcx, [rsp+150h+var_110]
0x1801854b2  lea     rdx, [rsp+150h+pidl]
0x1801854b7  movups  xmm0, xmmword ptr [rax]
0x1801854ba  mov     rax, rbx
0x1801854bd  movdqu  xmmword ptr [rsp+150h+pidl], xmm0
0x1801854c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801854c8  mov     rcx, [rsp+150h+var_110]
0x1801854cd  lea     rdx, [rbp+50h+var_80]
0x1801854d1  mov     [rsp+150h+var_128], rdx
0x1801854d6  mov     r9d, 800h
0x1801854dc  lea     rdx, [rbp+50h+var_D0]
0x1801854e0  mov     r8, r12
0x1801854e3  mov     [rsp+150h+var_130], rdx
0x1801854e8  mov     rdx, r14
0x1801854eb  mov     rax, [rcx]
0x1801854ee  mov     rax, [rax+28h]
0x1801854f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801854f7  jmp     loc_1801856AC
0x1801854fc  lea     rcx, [rsp+150h+var_108]
0x180185501  mov     [rsp+150h+var_110], r15
0x180185506  mov     [rsp+150h+var_108], r15
0x18018550b  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180185511  mov     ebx, eax
0x180185513  test    esi, esi
0x180185515  jz      loc_1801855A5
0x18018551b  test    eax, eax
0x18018551d  js      loc_180185840
0x180185523  mov     rcx, [rsp+150h+var_108]
0x180185528  lea     r9, [rsp+150h+pidl]
0x18018552d  mov     [rsp+150h+pidl], r15
0x180185532  lea     r8, IID_IUnknown
0x180185539  lea     rdx, CLSID_CShdocvwBroker
0x180185540  mov     rax, [rcx]
0x180185543  mov     rax, [rax+30h]
0x180185547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018554c  mov     ebx, eax
0x18018554e  test    eax, eax
0x180185550  js      short loc_180185581
0x180185552  mov     rcx, [rsp+150h+pidl]
0x180185557  lea     r8, [rsp+150h+var_110]
0x18018555c  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180185563  mov     rax, [rcx]
0x180185566  mov     rax, [rax]
0x180185569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018556e  mov     rcx, [rsp+150h+pidl]
0x180185573  mov     ebx, eax
0x180185575  mov     rax, [rcx]
0x180185578  mov     rax, [rax+10h]
0x18018557c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185581  mov     rcx, [rsp+150h+var_108]
0x180185586  mov     rax, [rcx]
0x180185589  mov     rax, [rax+10h]
0x18018558d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185592  test    ebx, ebx
0x180185594  js      loc_180185840
0x18018559a  mov     r9d, 1000h
0x1801855a0  jmp     loc_18018568C
0x1801855a5  test    eax, eax
0x1801855a7  js      loc_180185840
0x1801855ad  mov     rcx, [rsp+150h+var_108]
0x1801855b2  lea     r9, [rsp+150h+dwProcessId]
0x1801855b7  mov     [rsp+150h+dwProcessId], r15d
0x1801855bc  xor     r8d, r8d
0x1801855bf  xor     edx, edx
0x1801855c1  mov     rax, [rcx]
0x1801855c4  mov     rax, [rax+18h]
0x1801855c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801855cd  mov     eax, [rsp+150h+dwProcessId]
0x1801855d1  or      ecx, 0FFFFFFFFh
0x1801855d4  test    eax, eax
0x1801855d6  cmovnz  ecx, eax; dwProcessId
0x1801855d9  call    cs:__imp_AllowSetForegroundWindow
0x1801855df  mov     rcx, [rsp+150h+var_108]
0x1801855e4  lea     r9, [rsp+150h+pidl]
0x1801855e9  mov     [rsp+150h+pidl], r15
0x1801855ee  lea     r8, IID_IUnknown
0x1801855f5  lea     rdx, CLSID_CShdocvwBroker
0x1801855fc  mov     rax, [rcx]
0x1801855ff  mov     rax, [rax+30h]
0x180185603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185608  mov     ebx, eax
0x18018560a  test    eax, eax
0x18018560c  js      short loc_18018563D
0x18018560e  mov     rcx, [rsp+150h+pidl]
0x180185613  lea     r8, [rsp+150h+var_110]
0x180185618  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18018561f  mov     rax, [rcx]
0x180185622  mov     rax, [rax]
0x180185625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018562a  mov     rcx, [rsp+150h+pidl]
0x18018562f  mov     ebx, eax
0x180185631  mov     rax, [rcx]
0x180185634  mov     rax, [rax+10h]
0x180185638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018563d  mov     rcx, [rsp+150h+var_108]
0x180185642  mov     rax, [rcx]
0x180185645  mov     rax, [rax+10h]
0x180185649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018564e  test    ebx, ebx
0x180185650  js      loc_180185840
0x180185656  mov     rax, [rsp+150h+var_110]
0x18018565b  mov     rcx, [rax]
0x18018565e  mov     rbx, [rcx+4E8h]
0x180185665  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18018566b  mov     rcx, [rsp+150h+var_110]
0x180185670  lea     rdx, [rsp+150h+pidl]
0x180185675  movups  xmm0, xmmword ptr [rax]
0x180185678  mov     rax, rbx
0x18018567b  movdqu  xmmword ptr [rsp+150h+pidl], xmm0
  ... truncated ...
```
