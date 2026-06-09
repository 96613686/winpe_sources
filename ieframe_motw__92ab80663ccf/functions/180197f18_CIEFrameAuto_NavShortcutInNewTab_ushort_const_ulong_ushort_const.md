# CIEFrameAuto::_NavShortcutInNewTab(ushort const *,ulong,ushort const *)

- ea: `0x180197f18`
- end: `0x18019866a`
- name: `?_NavShortcutInNewTab@CIEFrameAuto@@IEAAJPEBGK0@Z`
- size: `1874`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180197a54`

## callees

- `0x180005030`
- `0x180034250`
- `0x180110868`
- `0x180197f18`
- `0x180198670`
- `0x180208b30`
- `0x180208fbc`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180198029`
- `KERNEL32!GetCurrentProcessId` at `0x180198029`
- `USER32!AllowSetForegroundWindow` at `0x1801981da`
- `USER32!AllowSetForegroundWindow` at `0x1801983a7`
- `USER32!AllowSetForegroundWindow` at `0x1801981da`
- `USER32!AllowSetForegroundWindow` at `0x1801983a7`
- `ole32!CoAllowSetForegroundWindow` at `0x180198582`
- `ole32!CoAllowSetForegroundWindow` at `0x180198582`
- `SHELL32!__imp_ILFree` at `0x180197fd7`
- `SHELL32!__imp_ILFree` at `0x1801985c4`
- `SHELL32!__imp_ILFree` at `0x180197fd7`
- `SHELL32!__imp_ILFree` at `0x1801985c4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801980c4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180198198`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801982d3`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801980c4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180198198`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801982d3`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180198055`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180198055`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18019807b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18019849e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18019807b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18019849e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180197f70`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180197f70`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180198064`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180198269`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180198439`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180198064`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180198269`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180198439`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18019803a`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18019803a`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x180197ff5`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x180197ff5`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_NavShortcutInNewTab(
        CIEFrameAuto *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  IUnknown *v8; // rcx
  int v9; // r15d
  HRESULT active; // ebx
  int v11; // eax
  int v12; // esi
  HRESULT v13; // eax
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
        DWORD2(v34) = ((unsigned __int8)a3 >> 3) & 1;
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
0x180197f18  mov     [rsp-8+arg_10], rbx
0x180197f1d  push    rbp
0x180197f1e  push    rsi
0x180197f1f  push    rdi
0x180197f20  push    r12
0x180197f22  push    r13
0x180197f24  push    r14
0x180197f26  push    r15
0x180197f28  lea     rbp, [rsp-20h]
0x180197f2d  sub     rsp, 120h
0x180197f34  mov     rax, cs:__security_cookie
0x180197f3b  xor     rax, rsp
0x180197f3e  mov     [rbp+50h+var_40], rax
0x180197f42  mov     r12, r9
0x180197f45  mov     esi, r8d
0x180197f48  mov     r14, rdx
0x180197f4b  lea     r9, [rsp+150h+ppvOut]; ppvOut
0x180197f50  mov     r13, rcx
0x180197f53  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1; riid
0x180197f5a  mov     rcx, [rcx+210h]; punk
0x180197f61  lea     rdx, SID_STabWindowManager; guidService
0x180197f68  xor     r15d, r15d
0x180197f6b  mov     [rsp+150h+ppvOut], r15
0x180197f70  call    cs:__imp_IUnknown_QueryService
0x180197f77  nop     dword ptr [rax+rax+00h]
0x180197f7c  mov     ebx, eax
0x180197f7e  test    eax, eax
0x180197f80  js      loc_180198636
0x180197f86  mov     rcx, [rsp+150h+ppvOut]
0x180197f8b  lea     rdx, [rsp+150h+var_D8]
0x180197f90  mov     [rsp+150h+var_D8], r15
0x180197f95  mov     rax, [rcx]
0x180197f98  mov     rax, [rax+38h]
0x180197f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197fa1  mov     [rsp+150h+pidl], r15
0x180197fa6  test    eax, eax
0x180197fa8  js      loc_1801985EE
0x180197fae  mov     rcx, [rsp+150h+var_D8]
0x180197fb3  lea     rdx, [rsp+150h+pidl]
0x180197fb8  mov     rax, [rcx]
0x180197fbb  mov     rax, [rax+0A0h]
0x180197fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197fc7  lea     edi, [r15+1]
0x180197fcb  test    eax, eax
0x180197fcd  js      short loc_180197FE3
0x180197fcf  mov     rcx, [rsp+150h+pidl]; pidl
0x180197fd4  mov     r15d, edi
0x180197fd7  call    cs:__imp_ILFree
0x180197fde  nop     dword ptr [rax+rax+00h]
0x180197fe3  xor     eax, eax
0x180197fe5  lea     rdx, [rsp+150h+var_E0]
0x180197fea  mov     rcx, r12
0x180197fed  mov     [rsp+150h+var_E0], eax
0x180197ff1  mov     [rsp+150h+var_DC], al
0x180197ff5  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x180197ffc  nop     dword ptr [rax+rax+00h]
0x180198001  mov     ebx, eax
0x180198003  test    eax, eax
0x180198005  jnz     loc_18019849E
0x18019800b  xorps   xmm0, xmm0
0x18019800e  xor     r15d, r15d
0x180198011  movups  xmmword ptr [rbp+50h+var_A8], xmm0
0x180198015  mov     [rbp+50h+var_D0], r15
0x180198019  movups  xmmword ptr [rbp+50h+var_A8+0Ch], xmm0
0x18019801d  mov     [rbp+50h+var_C8], r15
0x180198021  mov     [rbp+50h+var_C0], r15
0x180198025  movups  [rbp+50h+var_B8], xmm0
0x180198029  call    cs:__imp_GetCurrentProcessId
0x180198030  nop     dword ptr [rax+rax+00h]
0x180198035  mov     ecx, edi
0x180198037  mov     dword ptr [rbp+50h+var_B8], eax
0x18019803a  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180198041  nop     dword ptr [rax+rax+00h]
0x180198046  mov     ecx, 20000011h
0x18019804b  mov     dword ptr [rbp+50h+var_B8+8], r15d
0x18019804f  and     eax, 7Fh
0x180198052  mov     dword ptr [rbp+50h+var_B8+4], eax
0x180198055  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18019805c  nop     dword ptr [rax+rax+00h]
0x180198061  mov     [rbp+50h+var_A8], eax
0x180198064  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18019806b  nop     dword ptr [rax+rax+00h]
0x180198070  and     esi, 8
0x180198073  movups  xmm0, xmmword ptr [rax]
0x180198076  movdqu  xmmword ptr [rbp+50h+var_A8+0Ch], xmm0
0x18019807b  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180198082  nop     dword ptr [rax+rax+00h]
0x180198087  test    al, al
0x180198089  jz      loc_1801982C4
0x18019808f  xorps   xmm0, xmm0
0x180198092  movups  xmmword ptr [rbp+50h+var_60], xmm0
0x180198096  movups  xmmword ptr [rbp+50h+var_60+0Ch], xmm0
0x18019809a  movups  [rbp+50h+var_80], xmm0
0x18019809e  movups  [rbp+50h+var_70], xmm0
0x1801980a2  call    DualEngine__GetOpenerCookie
0x1801980a7  mov     dword ptr [rbp+50h+var_80], eax
0x1801980aa  mov     [rsp+150h+var_110], r15
0x1801980af  test    esi, esi
0x1801980b1  jz      loc_18019818A
0x1801980b7  lea     rcx, [rsp+150h+var_110]
0x1801980bc  mov     dword ptr [rbp+50h+var_80+8], edi
0x1801980bf  mov     qword ptr [rsp+150h+dwProcessId], r15
0x1801980c4  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801980cb  nop     dword ptr [rax+rax+00h]
0x1801980d0  mov     ebx, eax
0x1801980d2  test    eax, eax
0x1801980d4  js      loc_18019862C
0x1801980da  mov     rcx, [rsp+150h+var_110]
0x1801980df  lea     r9, [rsp+150h+var_108]
0x1801980e4  mov     [rsp+150h+var_108], r15
0x1801980e9  lea     r8, IID_IUnknown
0x1801980f0  lea     rdx, CLSID_CShdocvwBroker
0x1801980f7  mov     rax, [rcx]
0x1801980fa  mov     rax, [rax+30h]
0x1801980fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198103  mov     ebx, eax
0x180198105  test    eax, eax
0x180198107  js      short loc_180198138
0x180198109  mov     rcx, [rsp+150h+var_108]
0x18019810e  lea     r8, [rsp+150h+dwProcessId]
0x180198113  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x18019811a  mov     rax, [rcx]
0x18019811d  mov     rax, [rax]
0x180198120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198125  mov     rcx, [rsp+150h+var_108]
0x18019812a  mov     ebx, eax
0x18019812c  mov     rax, [rcx]
0x18019812f  mov     rax, [rax+10h]
0x180198133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198138  mov     rcx, [rsp+150h+var_110]
0x18019813d  mov     rax, [rcx]
0x180198140  mov     rax, [rax+10h]
0x180198144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198149  test    ebx, ebx
0x18019814b  js      loc_18019862C
0x180198151  mov     rcx, qword ptr [rsp+150h+dwProcessId]
0x180198156  lea     rdx, [rbp+50h+var_80]
0x18019815a  mov     [rsp+150h+var_128], rdx
0x18019815f  mov     r9d, 1000h
0x180198165  lea     rdx, [rbp+50h+var_D0]
0x180198169  mov     r8, r12
0x18019816c  mov     [rsp+150h+var_130], rdx
0x180198171  mov     rdx, r14
0x180198174  mov     rax, [rcx]
0x180198177  mov     rax, [rax+28h]
0x18019817b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198180  mov     rcx, qword ptr [rsp+150h+dwProcessId]
0x180198185  jmp     loc_18019848B
0x18019818a  lea     rcx, [rsp+150h+var_108]
0x18019818f  mov     dword ptr [rbp+50h+var_80+8], r15d
0x180198193  mov     [rsp+150h+var_108], r15
0x180198198  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18019819f  nop     dword ptr [rax+rax+00h]
0x1801981a4  mov     ebx, eax
0x1801981a6  test    eax, eax
0x1801981a8  js      loc_18019862C
0x1801981ae  mov     rcx, [rsp+150h+var_108]
0x1801981b3  lea     r9, [rsp+150h+dwProcessId]
0x1801981b8  mov     [rsp+150h+dwProcessId], r15d
0x1801981bd  xor     r8d, r8d
0x1801981c0  xor     edx, edx
0x1801981c2  mov     rax, [rcx]
0x1801981c5  mov     rax, [rax+18h]
0x1801981c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801981ce  mov     eax, [rsp+150h+dwProcessId]
0x1801981d2  or      ecx, 0FFFFFFFFh
0x1801981d5  test    eax, eax
0x1801981d7  cmovnz  ecx, eax; dwProcessId
0x1801981da  call    cs:__imp_AllowSetForegroundWindow
0x1801981e1  nop     dword ptr [rax+rax+00h]
0x1801981e6  mov     rcx, [rsp+150h+var_108]
0x1801981eb  lea     r9, [rsp+150h+pidl]
0x1801981f0  mov     [rsp+150h+pidl], r15
0x1801981f5  lea     r8, IID_IUnknown
0x1801981fc  lea     rdx, CLSID_CShdocvwBroker
0x180198203  mov     rax, [rcx]
0x180198206  mov     rax, [rax+30h]
0x18019820a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019820f  mov     ebx, eax
0x180198211  test    eax, eax
0x180198213  js      short loc_180198244
0x180198215  mov     rcx, [rsp+150h+pidl]
0x18019821a  lea     r8, [rsp+150h+var_110]
0x18019821f  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180198226  mov     rax, [rcx]
0x180198229  mov     rax, [rax]
0x18019822c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198231  mov     rcx, [rsp+150h+pidl]
0x180198236  mov     ebx, eax
0x180198238  mov     rax, [rcx]
0x18019823b  mov     rax, [rax+10h]
0x18019823f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198244  mov     rcx, [rsp+150h+var_108]
0x180198249  mov     rax, [rcx]
0x18019824c  mov     rax, [rax+10h]
0x180198250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198255  test    ebx, ebx
0x180198257  js      loc_18019862C
0x18019825d  mov     rax, [rsp+150h+var_110]
0x180198262  mov     rcx, [rax]
0x180198265  mov     rbx, [rcx+38h]
0x180198269  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180198270  nop     dword ptr [rax+rax+00h]
0x180198275  mov     rcx, [rsp+150h+var_110]
0x18019827a  lea     rdx, [rsp+150h+pidl]
0x18019827f  movups  xmm0, xmmword ptr [rax]
0x180198282  mov     rax, rbx
0x180198285  movdqu  xmmword ptr [rsp+150h+pidl], xmm0
0x18019828b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198290  mov     rcx, [rsp+150h+var_110]
0x180198295  lea     rdx, [rbp+50h+var_80]
0x180198299  mov     [rsp+150h+var_128], rdx
0x18019829e  mov     r9d, 800h
0x1801982a4  lea     rdx, [rbp+50h+var_D0]
0x1801982a8  mov     r8, r12
0x1801982ab  mov     [rsp+150h+var_130], rdx
0x1801982b0  mov     rdx, r14
0x1801982b3  mov     rax, [rcx]
0x1801982b6  mov     rax, [rax+28h]
0x1801982ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801982bf  jmp     loc_180198486
0x1801982c4  lea     rcx, [rsp+150h+var_108]
0x1801982c9  mov     [rsp+150h+var_110], r15
0x1801982ce  mov     [rsp+150h+var_108], r15
0x1801982d3  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801982da  nop     dword ptr [rax+rax+00h]
0x1801982df  mov     ebx, eax
0x1801982e1  test    esi, esi
0x1801982e3  jz      loc_180198373
0x1801982e9  test    eax, eax
0x1801982eb  js      loc_18019862C
0x1801982f1  mov     rcx, [rsp+150h+var_108]
0x1801982f6  lea     r9, [rsp+150h+pidl]
0x1801982fb  mov     [rsp+150h+pidl], r15
0x180198300  lea     r8, IID_IUnknown
0x180198307  lea     rdx, CLSID_CShdocvwBroker
0x18019830e  mov     rax, [rcx]
0x180198311  mov     rax, [rax+30h]
0x180198315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019831a  mov     ebx, eax
0x18019831c  test    eax, eax
0x18019831e  js      short loc_18019834F
0x180198320  mov     rcx, [rsp+150h+pidl]
0x180198325  lea     r8, [rsp+150h+var_110]
0x18019832a  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180198331  mov     rax, [rcx]
0x180198334  mov     rax, [rax]
0x180198337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019833c  mov     rcx, [rsp+150h+pidl]
0x180198341  mov     ebx, eax
0x180198343  mov     rax, [rcx]
0x180198346  mov     rax, [rax+10h]
0x18019834a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019834f  mov     rcx, [rsp+150h+var_108]
0x180198354  mov     rax, [rcx]
0x180198357  mov     rax, [rax+10h]
0x18019835b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198360  test    ebx, ebx
0x180198362  js      loc_18019862C
0x180198368  mov     r9d, 1000h
0x18019836e  jmp     loc_180198466
0x180198373  test    eax, eax
0x180198375  js      loc_18019862C
0x18019837b  mov     rcx, [rsp+150h+var_108]
0x180198380  lea     r9, [rsp+150h+dwProcessId]
0x180198385  mov     [rsp+150h+dwProcessId], r15d
0x18019838a  xor     r8d, r8d
0x18019838d  xor     edx, edx
0x18019838f  mov     rax, [rcx]
0x180198392  mov     rax, [rax+18h]
0x180198396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019839b  mov     eax, [rsp+150h+dwProcessId]
0x18019839f  or      ecx, 0FFFFFFFFh
0x1801983a2  test    eax, eax
0x1801983a4  cmovnz  ecx, eax; dwProcessId
0x1801983a7  call    cs:__imp_AllowSetForegroundWindow
0x1801983ae  nop     dword ptr [rax+rax+00h]
0x1801983b3  mov     rcx, [rsp+150h+var_108]
0x1801983b8  lea     r9, [rsp+150h+pidl]
0x1801983bd  mov     [rsp+150h+pidl], r15
0x1801983c2  lea     r8, IID_IUnknown
0x1801983c9  lea     rdx, CLSID_CShdocvwBroker
0x1801983d0  mov     rax, [rcx]
0x1801983d3  mov     rax, [rax+30h]
0x1801983d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801983dc  mov     ebx, eax
0x1801983de  test    eax, eax
0x1801983e0  js      short loc_180198411
0x1801983e2  mov     rcx, [rsp+150h+pidl]
0x1801983e7  lea     r8, [rsp+150h+var_110]
0x1801983ec  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1801983f3  mov     rax, [rcx]
0x1801983f6  mov     rax, [rax]
0x1801983f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801983fe  mov     rcx, [rsp+150h+pidl]
0x180198403  mov     ebx, eax
0x180198405  mov     rax, [rcx]
0x180198408  mov     rax, [rax+10h]
0x18019840c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198411  mov     rcx, [rsp+150h+var_108]
  ... truncated ...
```
