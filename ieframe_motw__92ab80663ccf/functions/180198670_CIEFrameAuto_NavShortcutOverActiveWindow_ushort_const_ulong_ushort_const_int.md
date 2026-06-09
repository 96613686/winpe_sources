# CIEFrameAuto::_NavShortcutOverActiveWindow(ushort const *,ulong,ushort const *,int)

- ea: `0x180198670`
- end: `0x180198a85`
- name: `?_NavShortcutOverActiveWindow@CIEFrameAuto@@IEAAJPEBGK0H@Z`
- size: `1045`
- prototype: `__int64 __usercall@<rax>(CIEFrameAuto *__hidden this@<rcx>, PCWSTR pszSrch@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180197a54`
- `0x180197f18`

## callees

- `0x180005030`
- `0x180034250`
- `0x1801149b8`
- `0x180196510`
- `0x180198670`
- `0x1802648c8`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180198a18`
- `KERNEL32!LocalFree` at `0x180198a18`
- `KERNEL32!GetCurrentProcessId` at `0x18019877c`
- `KERNEL32!GetCurrentProcessId` at `0x18019877c`
- `KERNEL32!GetCurrentThreadId` at `0x1801987cc`
- `KERNEL32!GetCurrentThreadId` at `0x1801987cc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180198a27`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180198a27`
- `USER32!AllowSetForegroundWindow` at `0x18019883f`
- `USER32!AllowSetForegroundWindow` at `0x18019883f`
- `SHELL32!__imp_ILFree` at `0x180198a4f`
- `SHELL32!__imp_ILFree` at `0x180198a4f`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801987fe`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801987fe`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801987a9`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801987a9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180198968`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180198968`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1801987e6`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1801987e6`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801986be`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801986be`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801987b8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801988c5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801987b8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801988c5`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18019878e`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18019878e`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x1801986d9`
- `urlmon!__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z` at `0x1801986d9`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_NavShortcutOverActiveWindow(
        CIEFrameAuto *this,
        PCWSTR pszSrch,
        char a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v9; // eax
  HRESULT UserBroker; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, LPITEMIDLIST *); // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  DWORD v14; // edi
  DWORD CurrentThreadId; // eax
  DWORD v16; // ecx
  void (__fastcall *v17)(__int64, __int128 *); // rbx
  IUnknown *v18; // rcx
  void *v19; // rcx
  PWSTR v20; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v21; // rdx
  DWORD dwProcessId; // [rsp+30h] [rbp-81h] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-79h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-71h] BYREF
  __int64 v26; // [rsp+48h] [rbp-69h] BYREF
  __int128 v27; // [rsp+50h] [rbp-61h] BYREF
  int v28; // [rsp+60h] [rbp-51h] BYREF
  char v29; // [rsp+64h] [rbp-4Dh]
  unsigned int v30[2]; // [rsp+70h] [rbp-41h] BYREF
  __int64 v31; // [rsp+78h] [rbp-39h]
  __int64 v32; // [rsp+80h] [rbp-31h]
  __int128 v33; // [rsp+88h] [rbp-29h]
  _DWORD v34[10]; // [rsp+98h] [rbp-19h] BYREF

  if ( !(unsigned int)LCIE_IsOnValidBrowserTabThread() )
    LCIE2ChangeComponentSharedFlagBit_FromComponentThread(1, 8u);
  v28 = 0;
  v29 = 0;
  v9 = IsRedirectToBrokerNeeded(a4, (const struct tagRedirectionPolicyFlags *)&v28);
  UserBroker = v9;
  if ( v9 )
  {
    if ( v9 >= 0 )
    {
      if ( !a5 || (a3 & 4) != 0 )
      {
        pidl = 0;
        UserBroker = IEParseDisplayNameWithBCW(0, a4, 0, &pidl);
        if ( UserBroker >= 0 )
        {
          v19 = (void *)*((_QWORD *)this + 75);
          if ( v19 )
            LocalFree(v19);
          v20 = StrDupW(pszSrch);
          v21 = (const struct _ITEMIDLIST_ABSOLUTE *)pidl;
          *((_QWORD *)this + 75) = v20;
          UserBroker = CIEFrameAuto::_BrowseObject(this, v21, 1u);
          ILFree(pidl);
        }
      }
      else
      {
        v18 = (IUnknown *)*((_QWORD *)this + 66);
        ppvOut = 0;
        UserBroker = IUnknown_QueryService(
                       v18,
                       (const GUID *const)&SID_STabWindowManager,
                       &GUID_feefb420_9399_492d_969c_51af6dc38fb1,
                       &ppvOut);
        if ( UserBroker >= 0 )
        {
          *(_QWORD *)&v27 = 0;
          UserBroker = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppvOut + 56LL))(ppvOut, &v27);
          if ( UserBroker >= 0 )
          {
            pidl = 0;
            UserBroker = (**(__int64 (__fastcall ***)(_QWORD, GUID *, LPITEMIDLIST *))v27)(
                           v27,
                           &GUID_1e1760ce_126f_46ca_9734_91a6cbf8b6f3,
                           &pidl);
            if ( UserBroker >= 0 )
              UserBroker = (*(__int64 (__fastcall **)(LPITEMIDLIST, PCWSTR, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 72LL))(
                             pidl,
                             pszSrch,
                             0);
            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
          }
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v27);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppvOut);
      }
    }
  }
  else
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPITEMIDLIST *))*((_QWORD *)this + 66);
    pidl = 0;
    UserBroker = (**v11)(v11, &GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c, &pidl);
    if ( UserBroker >= 0 )
    {
      UserBroker = (*(__int64 (__fastcall **)(LPITEMIDLIST, _QWORD, _QWORD))(*(_QWORD *)&pidl->mkid.cb + 56LL))(
                     pidl,
                     0,
                     0);
      if ( UserBroker >= 0 )
      {
        v13 = *((_QWORD *)this + 71);
        dwProcessId = 0x4000;
        LODWORD(v26) = 0;
        HandleBFCache(v13, v12, &dwProcessId, &v26);
        v14 = dwProcessId;
        memset(v34, 0, 28);
        v30[0] = 0;
        v30[1] = dwProcessId;
        v31 = 0;
        v32 = 0;
        v33 = 0;
        LODWORD(v33) = GetCurrentProcessId();
        *(_QWORD *)((char *)&v33 + 4) = IsoGetIntegrity(1) & 0x7F;
        v34[0] = IEConfiguration_GetDWORD(536870929);
        *(_OWORD *)&v34[3] = *(_OWORD *)GlobalThreadState();
        CurrentThreadId = GetCurrentThreadId();
        LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, v30, 0);
        v26 = 0;
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
          v16 = -1;
          if ( dwProcessId )
            v16 = dwProcessId;
          AllowSetForegroundWindow(v16);
          *(_QWORD *)&v27 = 0;
          UserBroker = (*(__int64 (__fastcall **)(void *, GUID *, GUID *, __int128 *))(*(_QWORD *)ppvOut + 48LL))(
                         ppvOut,
                         &CLSID_CShdocvwBroker,
                         &IID_IUnknown,
                         &v27);
          if ( UserBroker >= 0 )
          {
            UserBroker = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v27)(
                           v27,
                           &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                           &v26);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27 + 16LL))(v27);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          if ( UserBroker >= 0 )
          {
            v17 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v26 + 1256LL);
            v27 = *(_OWORD *)GlobalThreadState();
            v17(v26, &v27);
            UserBroker = (*(__int64 (__fastcall **)(__int64, PCWSTR, const unsigned __int16 *, _QWORD, unsigned int *))(*(_QWORD *)v26 + 32LL))(
                           v26,
                           pszSrch,
                           a4,
                           v14,
                           v30);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
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
0x180198670  mov     [rsp-8+arg_10], rbx
0x180198675  push    rbp
0x180198676  push    rsi
0x180198677  push    rdi
0x180198678  push    r12
0x18019867a  push    r13
0x18019867c  push    r14
0x18019867e  push    r15
0x180198680  lea     rbp, [rsp-1Fh]
0x180198685  sub     rsp, 0D0h
0x18019868c  mov     rax, cs:__security_cookie
0x180198693  xor     rax, rsp
0x180198696  mov     [rbp+4Fh+var_40], rax
0x18019869a  mov     rsi, r9
0x18019869d  mov     r15d, r8d
0x1801986a0  mov     r14, rdx
0x1801986a3  mov     rdi, rcx
0x1801986a6  call    ?LCIE_IsOnValidBrowserTabThread@@YAJXZ; LCIE_IsOnValidBrowserTabThread(void)
0x1801986ab  xor     r12d, r12d
0x1801986ae  mov     r13d, 1
0x1801986b4  test    eax, eax
0x1801986b6  jnz     short loc_1801986CA
0x1801986b8  lea     edx, [rax+8]
0x1801986bb  mov     cl, r13b
0x1801986be  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z; LCIE2ChangeComponentSharedFlagBit_FromComponentThread(bool,ulong)
0x1801986c5  nop     dword ptr [rax+rax+00h]
0x1801986ca  xor     eax, eax
0x1801986cc  lea     rdx, [rbp+4Fh+var_A0]
0x1801986d0  mov     rcx, rsi
0x1801986d3  mov     [rbp+4Fh+var_A0], eax
0x1801986d6  mov     [rbp+4Fh+var_9C], al
0x1801986d9  call    cs:__imp_?IsRedirectToBrokerNeeded@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z; IsRedirectToBrokerNeeded(ushort const *,tagRedirectionPolicyFlags const *)
0x1801986e0  nop     dword ptr [rax+rax+00h]
0x1801986e5  mov     ebx, eax
0x1801986e7  test    eax, eax
0x1801986e9  jnz     loc_180198931
0x1801986ef  mov     rcx, [rdi+210h]
0x1801986f6  lea     r8, [rbp+4Fh+pidl]
0x1801986fa  mov     [rbp+4Fh+pidl], r12
0x1801986fe  lea     rdx, _GUID_acabe16f_8a7f_4b32_82cb_313c3288e78c
0x180198705  mov     rax, [rcx]
0x180198708  mov     rax, [rax]
0x18019870b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198710  mov     ebx, eax
0x180198712  test    eax, eax
0x180198714  js      loc_180198923
0x18019871a  mov     rcx, [rbp+4Fh+pidl]
0x18019871e  xor     r8d, r8d
0x180198721  xor     edx, edx
0x180198723  mov     rax, [rcx]
0x180198726  mov     rax, [rax+38h]
0x18019872a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019872f  mov     ebx, eax
0x180198731  test    eax, eax
0x180198733  js      loc_180198923
0x180198739  mov     rcx, [rdi+238h]
0x180198740  lea     r9, [rbp+4Fh+var_B8]
0x180198744  lea     r8, [rsp+100h+dwProcessId]
0x180198749  mov     [rsp+100h+dwProcessId], 4000h
0x180198751  mov     dword ptr [rbp+4Fh+var_B8], r12d
0x180198755  call    ?HandleBFCache@@YAXPEAUIOleCommandTarget@@W4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@PEAKPEAW42@@Z; HandleBFCache(IOleCommandTarget *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS,ulong *,tagBFCACHE_CANDIDACY_FAILURE_FLAGS *)
0x18019875a  mov     edi, [rsp+100h+dwProcessId]
0x18019875e  xorps   xmm0, xmm0
0x180198761  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x180198765  mov     [rbp+4Fh+var_90], r12d
0x180198769  movups  xmmword ptr [rbp+4Fh+var_68+0Ch], xmm0
0x18019876d  mov     [rbp+4Fh+var_8C], edi
0x180198770  mov     [rbp+4Fh+var_88], r12
0x180198774  mov     [rbp+4Fh+var_80], r12
0x180198778  movups  [rbp+4Fh+var_78], xmm0
0x18019877c  call    cs:__imp_GetCurrentProcessId
0x180198783  nop     dword ptr [rax+rax+00h]
0x180198788  mov     ecx, r13d
0x18019878b  mov     dword ptr [rbp+4Fh+var_78], eax
0x18019878e  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180198795  nop     dword ptr [rax+rax+00h]
0x18019879a  mov     ecx, 20000011h
0x18019879f  mov     dword ptr [rbp+4Fh+var_78+8], r12d
0x1801987a3  and     eax, 7Fh
0x1801987a6  mov     dword ptr [rbp+4Fh+var_78+4], eax
0x1801987a9  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801987b0  nop     dword ptr [rax+rax+00h]
0x1801987b5  mov     [rbp+4Fh+var_68], eax
0x1801987b8  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801987bf  nop     dword ptr [rax+rax+00h]
0x1801987c4  movups  xmm0, xmmword ptr [rax]
0x1801987c7  movdqu  xmmword ptr [rbp+4Fh+var_68+0Ch], xmm0
0x1801987cc  call    cs:__imp_GetCurrentThreadId
0x1801987d3  nop     dword ptr [rax+rax+00h]
0x1801987d8  xor     r9d, r9d
0x1801987db  lea     r8, [rbp+4Fh+var_90]
0x1801987df  mov     edx, eax
0x1801987e1  mov     ecx, 203h
0x1801987e6  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1801987ed  nop     dword ptr [rax+rax+00h]
0x1801987f2  lea     rcx, [rbp+4Fh+ppvOut]
0x1801987f6  mov     [rbp+4Fh+var_B8], r12
0x1801987fa  mov     [rbp+4Fh+ppvOut], r12
0x1801987fe  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180198805  nop     dword ptr [rax+rax+00h]
0x18019880a  mov     ebx, eax
0x18019880c  test    eax, eax
0x18019880e  js      loc_180198923
0x180198814  mov     rcx, [rbp+4Fh+ppvOut]
0x180198818  lea     r9, [rsp+100h+dwProcessId]
0x18019881d  mov     [rsp+100h+dwProcessId], r12d
0x180198822  xor     r8d, r8d
0x180198825  xor     edx, edx
0x180198827  mov     rax, [rcx]
0x18019882a  mov     rax, [rax+18h]
0x18019882e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198833  mov     eax, [rsp+100h+dwProcessId]
0x180198837  or      ecx, 0FFFFFFFFh
0x18019883a  test    eax, eax
0x18019883c  cmovnz  ecx, eax; dwProcessId
0x18019883f  call    cs:__imp_AllowSetForegroundWindow
0x180198846  nop     dword ptr [rax+rax+00h]
0x18019884b  mov     rcx, [rbp+4Fh+ppvOut]
0x18019884f  lea     r9, [rbp+4Fh+var_B0]
0x180198853  mov     qword ptr [rbp+4Fh+var_B0], r12
0x180198857  lea     r8, IID_IUnknown
0x18019885e  lea     rdx, CLSID_CShdocvwBroker
0x180198865  mov     rax, [rcx]
0x180198868  mov     rax, [rax+30h]
0x18019886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198871  mov     ebx, eax
0x180198873  test    eax, eax
0x180198875  js      short loc_1801988A3
0x180198877  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x18019887b  lea     r8, [rbp+4Fh+var_B8]
0x18019887f  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180198886  mov     rax, [rcx]
0x180198889  mov     rax, [rax]
0x18019888c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198891  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x180198895  mov     ebx, eax
0x180198897  mov     rax, [rcx]
0x18019889a  mov     rax, [rax+10h]
0x18019889e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801988a3  mov     rcx, [rbp+4Fh+ppvOut]
0x1801988a7  mov     rax, [rcx]
0x1801988aa  mov     rax, [rax+10h]
0x1801988ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801988b3  test    ebx, ebx
0x1801988b5  js      short loc_180198923
0x1801988b7  mov     rax, [rbp+4Fh+var_B8]
0x1801988bb  mov     rcx, [rax]
0x1801988be  mov     rbx, [rcx+4E8h]
0x1801988c5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801988cc  nop     dword ptr [rax+rax+00h]
0x1801988d1  mov     rcx, [rbp+4Fh+var_B8]
0x1801988d5  lea     rdx, [rbp+4Fh+var_B0]
0x1801988d9  movups  xmm0, xmmword ptr [rax]
0x1801988dc  mov     rax, rbx
0x1801988df  movdqu  [rbp+4Fh+var_B0], xmm0
0x1801988e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801988e9  mov     rcx, [rbp+4Fh+var_B8]
0x1801988ed  lea     rdx, [rbp+4Fh+var_90]
0x1801988f1  mov     [rsp+100h+var_E0], rdx
0x1801988f6  mov     r9d, edi
0x1801988f9  mov     r8, rsi
0x1801988fc  mov     rdx, r14
0x1801988ff  mov     rax, [rcx]
0x180198902  mov     rax, [rax+20h]
0x180198906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019890b  mov     rcx, [rbp+4Fh+var_B8]
0x18019890f  mov     ebx, eax
0x180198911  mov     rax, [rcx]
0x180198914  mov     rax, [rax+10h]
0x180198918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019891d  test    ebx, ebx
0x18019891f  cmovns  ebx, r13d
0x180198923  lea     rcx, [rbp+4Fh+pidl]; void *
0x180198927  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18019892c  jmp     loc_180198A5B
0x180198931  js      loc_180198A5B
0x180198937  cmp     [rbp+4Fh+arg_20], r12d
0x18019893b  jz      loc_1801989F1
0x180198941  test    r15b, 4
0x180198945  jnz     loc_1801989F1
0x18019894b  mov     rcx, [rdi+210h]; punk
0x180198952  lea     r9, [rbp+4Fh+ppvOut]; ppvOut
0x180198956  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1; riid
0x18019895d  mov     [rbp+4Fh+ppvOut], r12
0x180198961  lea     rdx, SID_STabWindowManager; guidService
0x180198968  call    cs:__imp_IUnknown_QueryService
0x18019896f  nop     dword ptr [rax+rax+00h]
0x180198974  mov     ebx, eax
0x180198976  test    eax, eax
0x180198978  js      short loc_1801989E6
0x18019897a  mov     rcx, [rbp+4Fh+ppvOut]
0x18019897e  lea     rdx, [rbp+4Fh+var_B0]
0x180198982  mov     qword ptr [rbp+4Fh+var_B0], r12
0x180198986  mov     rax, [rcx]
0x180198989  mov     rax, [rax+38h]
0x18019898d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198992  mov     ebx, eax
0x180198994  test    eax, eax
0x180198996  js      short loc_1801989DD
0x180198998  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x18019899c  lea     r8, [rbp+4Fh+pidl]
0x1801989a0  mov     [rbp+4Fh+pidl], r12
0x1801989a4  lea     rdx, _GUID_1e1760ce_126f_46ca_9734_91a6cbf8b6f3
0x1801989ab  mov     rax, [rcx]
0x1801989ae  mov     rax, [rax]
0x1801989b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801989b6  mov     ebx, eax
0x1801989b8  test    eax, eax
0x1801989ba  js      short loc_1801989D4
0x1801989bc  mov     rcx, [rbp+4Fh+pidl]
0x1801989c0  xor     r8d, r8d
0x1801989c3  mov     rdx, r14
0x1801989c6  mov     rax, [rcx]
0x1801989c9  mov     rax, [rax+48h]
0x1801989cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801989d2  mov     ebx, eax
0x1801989d4  lea     rcx, [rbp+4Fh+pidl]; void *
0x1801989d8  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801989dd  lea     rcx, [rbp+4Fh+var_B0]; void *
0x1801989e1  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801989e6  lea     rcx, [rbp+4Fh+ppvOut]; void *
0x1801989ea  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801989ef  jmp     short loc_180198A5B
0x1801989f1  lea     r9, [rbp+4Fh+pidl]
0x1801989f5  mov     [rbp+4Fh+pidl], r12
0x1801989f9  xor     r8d, r8d
0x1801989fc  mov     rdx, rsi
0x1801989ff  xor     ecx, ecx
0x180198a01  call    IEParseDisplayNameWithBCW
0x180198a06  mov     ebx, eax
0x180198a08  test    eax, eax
0x180198a0a  js      short loc_180198A5B
0x180198a0c  mov     rcx, [rdi+258h]; hMem
0x180198a13  test    rcx, rcx
0x180198a16  jz      short loc_180198A24
0x180198a18  call    cs:__imp_LocalFree
0x180198a1f  nop     dword ptr [rax+rax+00h]
0x180198a24  mov     rcx, r14; pszSrch
0x180198a27  call    cs:__imp_StrDupW
0x180198a2e  nop     dword ptr [rax+rax+00h]
0x180198a33  mov     rdx, [rbp+4Fh+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180198a37  mov     r8d, r13d; unsigned int
0x180198a3a  mov     rcx, rdi; this
0x180198a3d  mov     [rdi+258h], rax
0x180198a44  call    ?_BrowseObject@CIEFrameAuto@@IEAAJPEBU_ITEMIDLIST_ABSOLUTE@@I@Z; CIEFrameAuto::_BrowseObject(_ITEMIDLIST_ABSOLUTE const *,uint)
0x180198a49  mov     rcx, [rbp+4Fh+pidl]; pidl
0x180198a4d  mov     ebx, eax
0x180198a4f  call    cs:__imp_ILFree
0x180198a56  nop     dword ptr [rax+rax+00h]
0x180198a5b  mov     eax, ebx
0x180198a5d  mov     rcx, [rbp+4Fh+var_40]
0x180198a61  xor     rcx, rsp; StackCookie
0x180198a64  call    __security_check_cookie
0x180198a69  mov     rbx, [rsp+100h+arg_10]
0x180198a71  add     rsp, 0D0h
0x180198a78  pop     r15
0x180198a7a  pop     r14
0x180198a7c  pop     r13
0x180198a7e  pop     r12
0x180198a80  pop     rdi
0x180198a81  pop     rsi
0x180198a82  pop     rbp
0x180198a83  retn
```
