# CIEFrameAuto::_NavShortcutOverActiveWindow(ushort const *,ulong,ushort const *,int)

- ea: `0x180185884`
- end: `0x180185c94`
- name: `?_NavShortcutOverActiveWindow@CIEFrameAuto@@IEAAJPEBGK0H@Z`
- size: `1040`
- prototype: `__int64 __usercall@<rax>(CIEFrameAuto *__hidden this@<rcx>, PCWSTR pszSrch@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180184d0c`
- `0x180185198`

## callees

- `0x18000b9e0`
- `0x180030340`
- `0x180108cf0`
- `0x180185884`
- `0x1802464fc`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180185902`
- `KERNEL32!TlsGetValue` at `0x180185902`
- `KERNEL32!LocalFree` at `0x180185c3a`
- `KERNEL32!LocalFree` at `0x180185c3a`
- `KERNEL32!GetCurrentProcessId` at `0x1801859da`
- `KERNEL32!GetCurrentProcessId` at `0x1801859da`
- `KERNEL32!GetCurrentThreadId` at `0x180185a12`
- `KERNEL32!GetCurrentThreadId` at `0x180185a12`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180185c43`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180185c43`
- `USER32!AllowSetForegroundWindow` at `0x180185a73`
- `USER32!AllowSetForegroundWindow` at `0x180185a73`
- `SHELL32!__imp_ILFree` at `0x180185c65`
- `SHELL32!__imp_ILFree` at `0x180185c65`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180185a38`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180185a38`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801858bf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801858bf`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801859fb`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801859fb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180185b90`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180185b90`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180185a26`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180185a26`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801858d7`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801858e2`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801858d7`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801858e2`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x180185928`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x180185928`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180185a04`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180185af3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180185a04`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180185af3`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801859e6`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801859e6`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18018593d`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x18018593d`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_NavShortcutOverActiveWindow(
        CIEFrameAuto *this,
        PCWSTR pszSrch,
        char a3,
        const unsigned __int16 *a4,
        int a5)
{
  struct IsoScope *DefaultScope; // rax
  DWORD v10; // eax
  _DWORD *Value; // rax
  int v12; // eax
  HRESULT UserBroker; // ebx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, LPITEMIDLIST *); // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  DWORD v17; // edi
  DWORD CurrentThreadId; // eax
  DWORD v19; // ecx
  void (__fastcall *v20)(__int64, __int128 *); // rbx
  IUnknown *v21; // rcx
  void *v22; // rcx
  PWSTR v23; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v24; // rdx
  DWORD dwProcessId; // [rsp+30h] [rbp-81h] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-79h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-71h] BYREF
  __int64 v29; // [rsp+48h] [rbp-69h] BYREF
  __int128 v30; // [rsp+50h] [rbp-61h] BYREF
  int v31; // [rsp+60h] [rbp-51h] BYREF
  char v32; // [rsp+64h] [rbp-4Dh]
  unsigned int v33[2]; // [rsp+70h] [rbp-41h] BYREF
  __int64 v34; // [rsp+78h] [rbp-39h]
  __int64 v35; // [rsp+80h] [rbp-31h]
  __int128 v36; // [rsp+88h] [rbp-29h]
  _DWORD v37[10]; // [rsp+98h] [rbp-19h] BYREF

  if ( (unsigned __int8)IEConfiguration_GetBool(268435482) )
  {
    if ( IsoGetDefaultScope() )
    {
      DefaultScope = IsoGetDefaultScope();
      v10 = (*(__int64 (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 680LL))(DefaultScope, 1);
      Value = TlsGetValue(v10);
      if ( Value )
      {
        if ( Value[1] && *(_BYTE *)Value == 20 && *((_WORD *)Value + 1) == 515 )
          LCIE2ChangeComponentSharedFlagBit_FromComponentThread(1, 8u);
      }
    }
  }
  v31 = 0;
  v32 = 0;
  v12 = IsRedirectToBrokerNeeded(a4, (const struct tagRedirectionPolicyFlags *)&v31);
  UserBroker = v12;
  if ( v12 )
  {
    if ( v12 >= 0 )
    {
      if ( !a5 || (a3 & 4) != 0 )
      {
        pidl = 0;
        UserBroker = IEParseDisplayNameWithBCW(0, a4, 0, &pidl);
        if ( UserBroker >= 0 )
        {
          v22 = (void *)*((_QWORD *)this + 75);
          if ( v22 )
            LocalFree(v22);
          v23 = StrDupW(pszSrch);
          v24 = (const struct _ITEMIDLIST_ABSOLUTE *)pidl;
          *((_QWORD *)this + 75) = v23;
          UserBroker = CIEFrameAuto::_BrowseObject(this, v24, 1u);
          ILFree(pidl);
        }
      }
      else
      {
        v21 = (IUnknown *)*((_QWORD *)this + 66);
        ppvOut = 0;
        UserBroker = IUnknown_QueryService(
                       v21,
                       (const GUID *const)&SID_STabWindowManager,
                       &GUID_feefb420_9399_492d_969c_51af6dc38fb1,
                       &ppvOut);
        if ( UserBroker >= 0 )
        {
          *(_QWORD *)&v30 = 0;
          UserBroker = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppvOut + 56LL))(ppvOut, &v30);
          if ( UserBroker >= 0 )
          {
            pidl = 0;
            UserBroker = (**(__int64 (__fastcall ***)(_QWORD, GUID *, LPITEMIDLIST *))v30)(
                           v30,
                           &GUID_1e1760ce_126f_46ca_9734_91a6cbf8b6f3,
                           &pidl);
            if ( UserBroker >= 0 )
              UserBroker = (*(__int64 (__fastcall **)(LPITEMIDLIST, PCWSTR, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 72LL))(
                             pidl,
                             pszSrch,
                             0);
            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
          }
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v30);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppvOut);
      }
    }
  }
  else
  {
    v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPITEMIDLIST *))*((_QWORD *)this + 66);
    pidl = 0;
    UserBroker = (**v14)(v14, &GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c, &pidl);
    if ( UserBroker >= 0 )
    {
      UserBroker = (*(__int64 (__fastcall **)(LPITEMIDLIST, _QWORD, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 56LL))(
                     pidl,
                     0,
                     0);
      if ( UserBroker >= 0 )
      {
        v16 = *((_QWORD *)this + 71);
        dwProcessId = 0x4000;
        LODWORD(v29) = 0;
        HandleBFCache(v16, v15, &dwProcessId, &v29);
        v17 = dwProcessId;
        memset(v37, 0, 28);
        v33[0] = 0;
        v33[1] = dwProcessId;
        v34 = 0;
        v35 = 0;
        v36 = 0;
        LODWORD(v36) = GetCurrentProcessId();
        *(_QWORD *)((char *)&v36 + 4) = IsoGetIntegrity(1) & 0x7F;
        v37[0] = IEConfiguration_GetDWORD(536870929);
        *(_OWORD *)&v37[3] = *(_OWORD *)GlobalThreadState();
        CurrentThreadId = GetCurrentThreadId();
        LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, v33, 0);
        v29 = 0;
        ppvOut = 0;
        UserBroker = CoCreateUserBroker((struct IEUserBroker **)&ppvOut);
        if ( UserBroker >= 0 )
        {
          dwProcessId = 0;
          (*(void (__fastcall **)(void *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)ppvOut + 24LL))(
            ppvOut,
            0,
            0,
            &dwProcessId);
          v19 = -1;
          if ( dwProcessId )
            v19 = dwProcessId;
          AllowSetForegroundWindow(v19);
          *(_QWORD *)&v30 = 0;
          UserBroker = (*(__int64 (__fastcall **)(void *, GUID *, GUID *, __int128 *))(*(_QWORD *)ppvOut + 48LL))(
                         ppvOut,
                         &CLSID_CShdocvwBroker,
                         &IID_IUnknown,
                         &v30);
          if ( UserBroker >= 0 )
          {
            UserBroker = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v30)(
                           v30,
                           &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                           &v29);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 16LL))(v30);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          if ( UserBroker >= 0 )
          {
            v20 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v29 + 1256LL);
            v30 = *(_OWORD *)GlobalThreadState();
            v20(v29, &v30);
            UserBroker = (*(__int64 (__fastcall **)(__int64, PCWSTR, const unsigned __int16 *, _QWORD, unsigned int *))(*(_QWORD *)v29 + 32LL))(
                           v29,
                           pszSrch,
                           a4,
                           v17,
                           v33);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            if ( UserBroker >= 0 )
              UserBroker = 1;
          }
        }
      }
    }
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
  }
  return (unsigned int)UserBroker;
}

```

## disassembly

```asm
0x180185884  mov     [rsp-8+arg_10], rbx
0x180185889  push    rbp
0x18018588a  push    rsi
0x18018588b  push    rdi
0x18018588c  push    r12
0x18018588e  push    r13
0x180185890  push    r14
0x180185892  push    r15
0x180185894  lea     rbp, [rsp-1Fh]
0x180185899  sub     rsp, 0D0h
0x1801858a0  mov     rax, cs:__security_cookie
0x1801858a7  xor     rax, rsp
0x1801858aa  mov     [rbp+4Fh+var_40], rax
0x1801858ae  mov     rdi, rcx
0x1801858b1  mov     rsi, r9
0x1801858b4  mov     ecx, 1000001Ah
0x1801858b9  mov     r15d, r8d
0x1801858bc  mov     r14, rdx
0x1801858bf  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801858c5  xor     r12d, r12d
0x1801858c8  mov     ebx, 203h
0x1801858cd  mov     r13d, 1
0x1801858d3  test    al, al
0x1801858d5  jz      short loc_18018592E
0x1801858d7  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801858dd  test    rax, rax
0x1801858e0  jz      short loc_18018592E
0x1801858e2  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801858e8  mov     r8, rax
0x1801858eb  mov     edx, r13d
0x1801858ee  mov     rcx, [rax]
0x1801858f1  mov     rax, [rcx+2A8h]
0x1801858f8  mov     rcx, r8
0x1801858fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185900  mov     ecx, eax; dwTlsIndex
0x180185902  call    cs:__imp_TlsGetValue
0x180185908  test    rax, rax
0x18018590b  jz      short loc_18018592E
0x18018590d  mov     ecx, [rax+4]
0x180185910  test    ecx, ecx
0x180185912  jz      short loc_18018592E
0x180185914  mov     cl, [rax]
0x180185916  cmp     cl, 14h
0x180185919  jnz     short loc_18018592E
0x18018591b  cmp     [rax+2], bx
0x18018591f  jnz     short loc_18018592E
0x180185921  lea     edx, [r13+7]
0x180185925  mov     cl, r13b
0x180185928  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z; LCIE2ChangeComponentSharedFlagBit_FromComponentThread(bool,ulong)
0x18018592e  xor     eax, eax
0x180185930  lea     rdx, [rbp+4Fh+var_A0]
0x180185934  mov     rcx, rsi
0x180185937  mov     [rbp+4Fh+var_A0], eax
0x18018593a  mov     [rbp+4Fh+var_9C], al
0x18018593d  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x180185943  mov     ebx, eax
0x180185945  test    eax, eax
0x180185947  jnz     loc_180185B59
0x18018594d  mov     rcx, [rdi+210h]
0x180185954  lea     r8, [rbp+4Fh+pidl]
0x180185958  mov     [rbp+4Fh+pidl], r12
0x18018595c  lea     rdx, _GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c
0x180185963  mov     rax, [rcx]
0x180185966  mov     rax, [rax]
0x180185969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018596e  mov     ebx, eax
0x180185970  test    eax, eax
0x180185972  js      loc_180185B4B
0x180185978  mov     rcx, [rbp+4Fh+pidl]
0x18018597c  xor     r8d, r8d
0x18018597f  xor     edx, edx
0x180185981  mov     rax, [rcx]
0x180185984  mov     rax, [rax+38h]
0x180185988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018598d  mov     ebx, eax
0x18018598f  test    eax, eax
0x180185991  js      loc_180185B4B
0x180185997  mov     rcx, [rdi+238h]
0x18018599e  lea     r9, [rbp+4Fh+var_B8]
0x1801859a2  lea     r8, [rsp+100h+dwProcessId]
0x1801859a7  mov     [rsp+100h+dwProcessId], 4000h
0x1801859af  mov     dword ptr [rbp+4Fh+var_B8], r12d
0x1801859b3  call    ?HandleBFCache@@YAXPEAUIOleCommandTarget@@W4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@PEAKPEAW42@@Z; HandleBFCache(IOleCommandTarget *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS,ulong *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS *)
0x1801859b8  mov     edi, [rsp+100h+dwProcessId]
0x1801859bc  xorps   xmm0, xmm0
0x1801859bf  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1801859c3  mov     [rbp+4Fh+var_90], r12d
0x1801859c7  movups  xmmword ptr [rbp+4Fh+var_68+0Ch], xmm0
0x1801859cb  mov     [rbp+4Fh+var_8C], edi
0x1801859ce  mov     [rbp+4Fh+var_88], r12
0x1801859d2  mov     [rbp+4Fh+var_80], r12
0x1801859d6  movups  [rbp+4Fh+var_78], xmm0
0x1801859da  call    cs:__imp_GetCurrentProcessId
0x1801859e0  mov     ecx, r13d
0x1801859e3  mov     dword ptr [rbp+4Fh+var_78], eax
0x1801859e6  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1801859ec  mov     ecx, 20000011h
0x1801859f1  mov     dword ptr [rbp+4Fh+var_78+8], r12d
0x1801859f5  and     eax, 7Fh
0x1801859f8  mov     dword ptr [rbp+4Fh+var_78+4], eax
0x1801859fb  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180185a01  mov     [rbp+4Fh+var_68], eax
0x180185a04  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180185a0a  movups  xmm0, xmmword ptr [rax]
0x180185a0d  movdqu  xmmword ptr [rbp+4Fh+var_68+0Ch], xmm0
0x180185a12  call    cs:__imp_GetCurrentThreadId
0x180185a18  xor     r9d, r9d
0x180185a1b  lea     r8, [rbp+4Fh+var_90]
0x180185a1f  mov     edx, eax
0x180185a21  mov     ecx, 203h
0x180185a26  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x180185a2c  lea     rcx, [rbp+4Fh+ppvOut]
0x180185a30  mov     [rbp+4Fh+var_B8], r12
0x180185a34  mov     [rbp+4Fh+ppvOut], r12
0x180185a38  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180185a3e  mov     ebx, eax
0x180185a40  test    eax, eax
0x180185a42  js      loc_180185B4B
0x180185a48  mov     rcx, [rbp+4Fh+ppvOut]
0x180185a4c  lea     r9, [rsp+100h+dwProcessId]
0x180185a51  mov     [rsp+100h+dwProcessId], r12d
0x180185a56  xor     r8d, r8d
0x180185a59  xor     edx, edx
0x180185a5b  mov     rax, [rcx]
0x180185a5e  mov     rax, [rax+18h]
0x180185a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185a67  mov     eax, [rsp+100h+dwProcessId]
0x180185a6b  or      ecx, 0FFFFFFFFh
0x180185a6e  test    eax, eax
0x180185a70  cmovnz  ecx, eax; dwProcessId
0x180185a73  call    cs:__imp_AllowSetForegroundWindow
0x180185a79  mov     rcx, [rbp+4Fh+ppvOut]
0x180185a7d  lea     r9, [rbp+4Fh+var_B0]
0x180185a81  mov     qword ptr [rbp+4Fh+var_B0], r12
0x180185a85  lea     r8, IID_IUnknown
0x180185a8c  lea     rdx, CLSID_CShdocvwBroker
0x180185a93  mov     rax, [rcx]
0x180185a96  mov     rax, [rax+30h]
0x180185a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185a9f  mov     ebx, eax
0x180185aa1  test    eax, eax
0x180185aa3  js      short loc_180185AD1
0x180185aa5  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x180185aa9  lea     r8, [rbp+4Fh+var_B8]
0x180185aad  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180185ab4  mov     rax, [rcx]
0x180185ab7  mov     rax, [rax]
0x180185aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185abf  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x180185ac3  mov     ebx, eax
0x180185ac5  mov     rax, [rcx]
0x180185ac8  mov     rax, [rax+10h]
0x180185acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185ad1  mov     rcx, [rbp+4Fh+ppvOut]
0x180185ad5  mov     rax, [rcx]
0x180185ad8  mov     rax, [rax+10h]
0x180185adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185ae1  test    ebx, ebx
0x180185ae3  js      short loc_180185B4B
0x180185ae5  mov     rax, [rbp+4Fh+var_B8]
0x180185ae9  mov     rcx, [rax]
0x180185aec  mov     rbx, [rcx+4E8h]
0x180185af3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180185af9  mov     rcx, [rbp+4Fh+var_B8]
0x180185afd  lea     rdx, [rbp+4Fh+var_B0]
0x180185b01  movups  xmm0, xmmword ptr [rax]
0x180185b04  mov     rax, rbx
0x180185b07  movdqu  [rbp+4Fh+var_B0], xmm0
0x180185b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185b11  mov     rcx, [rbp+4Fh+var_B8]
0x180185b15  lea     rdx, [rbp+4Fh+var_90]
0x180185b19  mov     [rsp+100h+var_E0], rdx
0x180185b1e  mov     r9d, edi
0x180185b21  mov     r8, rsi
0x180185b24  mov     rdx, r14
0x180185b27  mov     rax, [rcx]
0x180185b2a  mov     rax, [rax+20h]
0x180185b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185b33  mov     rcx, [rbp+4Fh+var_B8]
0x180185b37  mov     ebx, eax
0x180185b39  mov     rax, [rcx]
0x180185b3c  mov     rax, [rax+10h]
0x180185b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185b45  test    ebx, ebx
0x180185b47  cmovns  ebx, r13d
0x180185b4b  lea     rcx, [rbp+4Fh+pidl]; void *
0x180185b4f  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180185b54  jmp     loc_180185C6B
0x180185b59  js      loc_180185C6B
0x180185b5f  cmp     [rbp+4Fh+arg_20], r12d
0x180185b63  jz      loc_180185C13
0x180185b69  test    r15b, 4
0x180185b6d  jnz     loc_180185C13
0x180185b73  mov     rcx, [rdi+210h]; punk
0x180185b7a  lea     r9, [rbp+4Fh+ppvOut]; ppvOut
0x180185b7e  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1; riid
0x180185b85  mov     [rbp+4Fh+ppvOut], r12
0x180185b89  lea     rdx, SID_STabWindowManager; guidService
0x180185b90  call    cs:__imp_IUnknown_QueryService
0x180185b96  mov     ebx, eax
0x180185b98  test    eax, eax
0x180185b9a  js      short loc_180185C08
0x180185b9c  mov     rcx, [rbp+4Fh+ppvOut]
0x180185ba0  lea     rdx, [rbp+4Fh+var_B0]
0x180185ba4  mov     qword ptr [rbp+4Fh+var_B0], r12
0x180185ba8  mov     rax, [rcx]
0x180185bab  mov     rax, [rax+38h]
0x180185baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185bb4  mov     ebx, eax
0x180185bb6  test    eax, eax
0x180185bb8  js      short loc_180185BFF
0x180185bba  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x180185bbe  lea     r8, [rbp+4Fh+pidl]
0x180185bc2  mov     [rbp+4Fh+pidl], r12
0x180185bc6  lea     rdx, _GUID_1e1760ce_126f_46ca_9734_91a6cbf8b6f3
0x180185bcd  mov     rax, [rcx]
0x180185bd0  mov     rax, [rax]
0x180185bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185bd8  mov     ebx, eax
0x180185bda  test    eax, eax
0x180185bdc  js      short loc_180185BF6
0x180185bde  mov     rcx, [rbp+4Fh+pidl]
0x180185be2  xor     r8d, r8d
0x180185be5  mov     rdx, r14
0x180185be8  mov     rax, [rcx]
0x180185beb  mov     rax, [rax+48h]
0x180185bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185bf4  mov     ebx, eax
0x180185bf6  lea     rcx, [rbp+4Fh+pidl]; void *
0x180185bfa  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180185bff  lea     rcx, [rbp+4Fh+var_B0]; void *
0x180185c03  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180185c08  lea     rcx, [rbp+4Fh+ppvOut]; void *
0x180185c0c  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180185c11  jmp     short loc_180185C6B
0x180185c13  lea     r9, [rbp+4Fh+pidl]
0x180185c17  mov     [rbp+4Fh+pidl], r12
0x180185c1b  xor     r8d, r8d
0x180185c1e  mov     rdx, rsi
0x180185c21  xor     ecx, ecx
0x180185c23  call    IEParseDisplayNameWithBCW
0x180185c28  mov     ebx, eax
0x180185c2a  test    eax, eax
0x180185c2c  js      short loc_180185C6B
0x180185c2e  mov     rcx, [rdi+258h]; hMem
0x180185c35  test    rcx, rcx
0x180185c38  jz      short loc_180185C40
0x180185c3a  call    cs:__imp_LocalFree
0x180185c40  mov     rcx, r14; pszSrch
0x180185c43  call    cs:__imp_StrDupW
0x180185c49  mov     rdx, [rbp+4Fh+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180185c4d  mov     r8d, r13d; unsigned int
0x180185c50  mov     rcx, rdi; this
0x180185c53  mov     [rdi+258h], rax
0x180185c5a  call    ?_BrowseObject@CIEFrameAuto@@IEAAJPEBU_ITEMIDLIST_ABSOLUTE@@I@Z; CIEFrameAuto::_BrowseObject(_ITEMIDLIST_ABSOLUTE const *,uint)
0x180185c5f  mov     rcx, [rbp+4Fh+pidl]; pidl
0x180185c63  mov     ebx, eax
0x180185c65  call    cs:__imp_ILFree
0x180185c6b  mov     eax, ebx
0x180185c6d  mov     rcx, [rbp+4Fh+var_40]
0x180185c71  xor     rcx, rsp; StackCookie
0x180185c74  call    __security_check_cookie
0x180185c79  mov     rbx, [rsp+100h+arg_10]
0x180185c81  add     rsp, 0D0h
0x180185c88  pop     r15
0x180185c8a  pop     r14
0x180185c8c  pop     r13
0x180185c8e  pop     r12
0x180185c90  pop     rdi
0x180185c91  pop     rsi
0x180185c92  pop     rbp
0x180185c93  retn
```
