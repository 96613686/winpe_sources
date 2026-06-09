# CBrowserFrame::_InitializeFrameWindow(tagIE8_THREADPARAM *)

- ea: `0x180258efc`
- end: `0x180259334`
- name: `?_InitializeFrameWindow@CBrowserFrame@@IEAAPEAUHWND__@@PEAUtagIE8_THREADPARAM@@@Z`
- size: `1080`
- prototype: `HWND __fastcall(CBrowserFrame *__hidden this, struct tagIE8_THREADPARAM *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180258a4c`

## callees

- `0x180024bc4`
- `0x180093990`
- `0x18009ab38`
- `0x1800d440c`
- `0x18011e5a8`
- `0x1801accd0`
- `0x1801cae6c`
- `0x1802504f4`
- `0x180252624`
- `0x180253380`
- `0x1802535b4`
- `0x180253678`
- `0x180258efc`
- `0x18025967c`
- `0x18025d284`
- `0x18025e364`
- `0x180262e78`
- `0x180265d98`
- `0x1802aeb84`
- `0x18057c1d8`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1802590fb`
- `KERNEL32!CreateEventW` at `0x1802590fb`
- `KERNEL32!InitOnceExecuteOnce` at `0x180259045`
- `KERNEL32!InitOnceExecuteOnce` at `0x180259045`
- `KERNEL32!CloseHandle` at `0x180259133`
- `KERNEL32!CloseHandle` at `0x180259133`
- `KERNEL32!GetCurrentThreadId` at `0x180258feb`
- `KERNEL32!GetCurrentThreadId` at `0x18025907e`
- `KERNEL32!GetCurrentThreadId` at `0x180258feb`
- `KERNEL32!GetCurrentThreadId` at `0x18025907e`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x1802590e5`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x1802590e5`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x1802591c9`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x1802591c9`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180259211`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180259211`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180259224`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180259245`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180259224`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180259245`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18025929b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18025929b`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x180258f83`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x180258f83`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18025910a`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18025910a`
- `msIso!__imp_?IsoAddIdleTask@@YAJKW4IDLEMANAGER_TASKTYPE@@KKW4IDLETASK_PRIORITY@@PEAXPEAK@Z` at `0x1802591af`
- `msIso!__imp_?IsoAddIdleTask@@YAJKW4IDLEMANAGER_TASKTYPE@@KKW4IDLETASK_PRIORITY@@PEAXPEAK@Z` at `0x1802591af`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x180259095`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x180259095`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x1802590d6`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x1802590d6`

## pseudocode

```c
HWND __fastcall CBrowserFrame::_InitializeFrameWindow(CBrowserFrame *this, struct tagIE8_THREADPARAM *a2)
{
  unsigned int v4; // ecx
  int ArtifactAddress; // eax
  HWND v6; // rbx
  __int64 v7; // rcx
  char v8; // r14
  int *RefCountAddress; // rax
  struct IUnknown **v10; // r15
  HANDLE EventW; // rbx
  struct IsoScope *DefaultScope; // rax
  unsigned int v13; // ecx
  int v14; // ebx
  int *v15; // rcx
  unsigned int (*v16)(void *); // rcx
  HWND result; // rax
  LPARAM lParam; // [rsp+20h] [rbp-E0h]
  struct _FILETIME Buffer; // [rsp+40h] [rbp-C0h] BYREF
  struct _IsoArtifact *v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21[1044]; // [rsp+50h] [rbp-B0h] BYREF

  *((_DWORD *)this + 134) = *((_DWORD *)a2 + 52);
  if ( (int)CBrowserFrame::_RegisterFrameClass(this) >= 0 )
  {
    Buffer = 0;
    if ( (int)CBrowserFrame::_CreateFrameWindow(this, (HWND *)&Buffer) >= 0 )
    {
      v4 = *((_DWORD *)this + 171);
      v20 = 0;
      ArtifactAddress = IsoGetArtifactAddress(v4, 0x14u, &v20, 0);
      v6 = (HWND)Buffer;
      if ( ArtifactAddress >= 0 )
      {
        *((_DWORD *)v20 + 14) = 3;
        *((_QWORD *)v20 + 5) = v6;
      }
      *(_QWORD *)(*((_QWORD *)this + 34) + 32LL) = v6;
      TLSSetThreadOwner((IUnknown *)(((unsigned __int64)this + 112) & -(__int64)(this != 0)));
      CBrowserFrame::_SetFrameIcon(this);
      CBrowserFrame::_CreateClientCaption(this, v6);
      CBrowserFrame::_CreateGripperOverlayWindow((LONG_PTR)this, v6);
      if ( GetCurrentThreadId() == g_tidParking )
        IsSecurityLevelSecure(1);
      ResolveInitialBrowserLocation(
        *((HWND *)this + 1),
        a2,
        (int *)this + 137,
        *((struct CHomePageProtector **)this + 45));
      CBrowserFrame::_LoadFrameState(this, a2);
      InitOnceExecuteOnce(&stru_1806AAC60, SBEUtil::InitOnceIsSingleBrowserExperienceEnabled, 0, 0);
      if ( !byte_1806AAC58 )
      {
        CreateSettingSyncProcess();
        CBrowserSettingChangePublisher::_hwnd = (HWND)*((_QWORD *)this + 1);
        LODWORD(CBrowserSettingChangePublisher::_fastTimerParams) = 20791;
        LODWORD(CBrowserSettingChangePublisher::_slowTimerParams) = 20792;
      }
      if ( GetCurrentThreadId() == g_tidParking )
      {
        v8 = 1;
        RefCountAddress = ProcessGetRefCountAddress();
      }
      else
      {
        v8 = 0;
        RefCountAddress = (int *)((char *)this + 244);
      }
      v10 = (struct IUnknown **)((char *)this + 248);
      LOBYTE(v7) = v8;
      if ( (int)IECreateThreadRef(v7, RefCountAddress, (char *)this + 248) >= 0 )
      {
        if ( v8 )
        {
          ProcessSetRefCountIUnknown(*v10);
          SHSetInstanceExplorer(*v10);
          EventW = CreateEventW(0, 0, 0, 0);
          DefaultScope = IsoGetDefaultScope();
          (*(void (__fastcall **)(struct IsoScope *, __int64, HANDLE))(*(_QWORD *)DefaultScope + 248LL))(
            DefaultScope,
            25,
            EventW);
          CloseHandle(EventW);
          v13 = *((_DWORD *)a2 + 28);
          Buffer = 0;
          if ( GetSessionStartTime(v13, &Buffer) )
            LCIEUpdateSessionStartTime(&Buffer);
          if ( !*((_DWORD *)this + 130) )
            IEOnFirstBrowserCreation(0);
          CTabWindowManager::_SetBusy(*((_QWORD *)this + 35), 1, 1);
          if ( (int)IsoAddIdleTask(*((unsigned int *)this + 171), 1007, 0, 0, 10, 0, (char *)this + 1052) < 0 )
            __fastfail(7u);
        }
        IESetThreadRef(*v10);
        if ( v8 )
        {
          if ( !*((_DWORD *)this + 131) )
          {
            if ( *((_DWORD *)this + 130)
              || *((_DWORD *)a2 + 32)
              || !*((_DWORD *)this + 137)
              && !LCIEIsCurrentProcessInPrivate()
              && !(unsigned __int8)IEConfiguration_GetBool(268435465)
              && !*((_DWORD *)a2 + 49) )
            {
              v14 = 0;
              goto LABEL_35;
            }
            v14 = 1;
            if ( (unsigned __int8)IEConfiguration_GetBool(268435465) )
            {
              v15 = 0;
            }
            else
            {
              if ( !*((_DWORD *)a2 + 49)
                || (int)IEGetNameAndFlagsEx(*((_QWORD *)a2 + 44), 0x8000, 0, (int)v21, 0x824u, 0) < 0 )
              {
LABEL_35:
                if ( IsDualEngineProcess() )
                {
                  v16 = (unsigned int (*)(void *))CBrowserFrame::s_DualEngineCleanRecoveryStoresProc;
                }
                else
                {
                  CBrowserFrame::_CheckForCrashedSessions(this, v14);
                  LODWORD(lParam) = 5000;
                  CWorkItemQueue::ScheduleWorkItem(
                    (unsigned int (*)(void *))CBrowserFrame::s_ClearUnpinnedSiteRecoveryDataProc,
                    0,
                    -1,
                    0x10000000u,
                    lParam);
                  v16 = (unsigned int (*)(void *))CBrowserFrame::s_CleanActiveRecoveryStoresProc;
                }
                LODWORD(lParam) = 5000;
                CWorkItemQueue::ScheduleWorkItem(v16, 0, -1, 0x10000000u, lParam);
                goto LABEL_39;
              }
              v15 = v21;
            }
            CRelaunch::RetrieveCookiesAndCreds((const unsigned __int16 *)v15);
            goto LABEL_35;
          }
        }
      }
    }
  }
LABEL_39:
  result = (HWND)*((_QWORD *)this + 1);
  *((_BYTE *)this + 834) = 1;
  return result;
}

```

## disassembly

```asm
0x180258efc  mov     [rsp-8+arg_10], rbx
0x180258f01  push    rbp
0x180258f02  push    rsi
0x180258f03  push    rdi
0x180258f04  push    r12
0x180258f06  push    r13
0x180258f08  push    r14
0x180258f0a  push    r15
0x180258f0c  lea     rbp, [rsp-0FB0h]
0x180258f14  mov     eax, 10B0h
0x180258f19  call    _alloca_probe
0x180258f1e  sub     rsp, rax
0x180258f21  mov     rax, cs:__security_cookie
0x180258f28  xor     rax, rsp
0x180258f2b  mov     [rbp+0FE0h+var_40], rax
0x180258f32  mov     eax, [rdx+0D0h]
0x180258f38  mov     rsi, rdx
0x180258f3b  mov     [rcx+218h], eax
0x180258f41  mov     rdi, rcx
0x180258f44  call    ?_RegisterFrameClass@CBrowserFrame@@IEAAJXZ; CBrowserFrame::_RegisterFrameClass(void)
0x180258f49  xor     r13d, r13d
0x180258f4c  test    eax, eax
0x180258f4e  js      loc_1802592FE
0x180258f54  lea     rdx, [rsp+10E0h+Buffer]; HWND *
0x180258f59  mov     qword ptr [rsp+10E0h+Buffer.dwLowDateTime], r13
0x180258f5e  mov     rcx, rdi; this
0x180258f61  call    ?_CreateFrameWindow@CBrowserFrame@@IEAAJPEAPEAUHWND__@@@Z; CBrowserFrame::_CreateFrameWindow(HWND__ * *)
0x180258f66  test    eax, eax
0x180258f68  js      loc_1802592FE
0x180258f6e  mov     ecx, [rdi+2ACh]
0x180258f74  lea     r8, [rsp+10E0h+var_1098]
0x180258f79  xor     r9d, r9d
0x180258f7c  mov     [rsp+10E0h+var_1098], r13
0x180258f81  mov     dl, 14h
0x180258f83  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x180258f8a  nop     dword ptr [rax+rax+00h]
0x180258f8f  mov     rbx, qword ptr [rsp+10E0h+Buffer.dwLowDateTime]
0x180258f94  test    eax, eax
0x180258f96  js      short loc_180258FAD
0x180258f98  mov     rax, [rsp+10E0h+var_1098]
0x180258f9d  mov     dword ptr [rax+38h], 3
0x180258fa4  mov     rax, [rsp+10E0h+var_1098]
0x180258fa9  mov     [rax+28h], rbx
0x180258fad  mov     rax, [rdi+110h]
0x180258fb4  lea     r8, [rdi+70h]
0x180258fb8  mov     [rax+20h], rbx
0x180258fbc  mov     rax, rdi
0x180258fbf  neg     rax
0x180258fc2  sbb     rcx, rcx
0x180258fc5  and     rcx, r8; punk
0x180258fc8  call    ?TLSSetThreadOwner@@YAXPEAUIUnknown@@@Z; TLSSetThreadOwner(IUnknown *)
0x180258fcd  mov     rcx, rdi; this
0x180258fd0  call    ?_SetFrameIcon@CBrowserFrame@@IEAAXXZ; CBrowserFrame::_SetFrameIcon(void)
0x180258fd5  mov     rdx, rbx; HWND
0x180258fd8  mov     rcx, rdi; this
0x180258fdb  call    ?_CreateClientCaption@CBrowserFrame@@IEAAXPEAUHWND__@@@Z; CBrowserFrame::_CreateClientCaption(HWND__ *)
0x180258fe0  mov     rdx, rbx; HWND
0x180258fe3  mov     rcx, rdi; dwNewLong
0x180258fe6  call    ?_CreateGripperOverlayWindow@CBrowserFrame@@IEAAXPEAUHWND__@@@Z; CBrowserFrame::_CreateGripperOverlayWindow(HWND__ *)
0x180258feb  call    cs:__imp_GetCurrentThreadId
0x180258ff2  nop     dword ptr [rax+rax+00h]
0x180258ff7  cmp     eax, cs:g_tidParking
0x180258ffd  jnz     short loc_180259009
0x180258fff  mov     ecx, 1; int
0x180259004  call    ?IsSecurityLevelSecure@@YAHH@Z; IsSecurityLevelSecure(int)
0x180259009  mov     r9, [rdi+168h]; struct CHomePageProtector *
0x180259010  lea     r12, [rdi+224h]
0x180259017  mov     rcx, [rdi+8]; HWND
0x18025901b  mov     r8, r12; int *
0x18025901e  mov     rdx, rsi; struct tagIE8_THREADPARAM *
0x180259021  call    ?ResolveInitialBrowserLocation@@YAJPEAUHWND__@@PEAUtagIE8_THREADPARAM@@PEAHPEAVCHomePageProtector@@@Z; ResolveInitialBrowserLocation(HWND__ *,tagIE8_THREADPARAM *,int *,CHomePageProtector *)
0x180259026  mov     rdx, rsi; struct tagIE8_THREADPARAM *
0x180259029  mov     rcx, rdi; this
0x18025902c  call    ?_LoadFrameState@CBrowserFrame@@IEAAXPEAUtagIE8_THREADPARAM@@@Z; CBrowserFrame::_LoadFrameState(tagIE8_THREADPARAM *)
0x180259031  xor     r9d, r9d; Context
0x180259034  lea     rdx, SBEUtil__InitOnceIsSingleBrowserExperienceEnabled; InitFn
0x18025903b  xor     r8d, r8d; Parameter
0x18025903e  lea     rcx, stru_1806AAC60; InitOnce
0x180259045  call    cs:__imp_InitOnceExecuteOnce
0x18025904c  nop     dword ptr [rax+rax+00h]
0x180259051  cmp     cs:byte_1806AAC58, r13b
0x180259058  jnz     short loc_18025907E
0x18025905a  call    ?CreateSettingSyncProcess@@YAJXZ; CreateSettingSyncProcess(void)
0x18025905f  mov     rax, [rdi+8]
0x180259063  mov     cs:?_hwnd@CBrowserSettingChangePublisher@@0PEAUHWND__@@EA, rax; HWND__ * CBrowserSettingChangePublisher::_hwnd
0x18025906a  mov     cs:?_fastTimerParams@CBrowserSettingChangePublisher@@0UTimerParams@@A, 5137h; TimerParams CBrowserSettingChangePublisher::_fastTimerParams
0x180259074  mov     cs:?_slowTimerParams@CBrowserSettingChangePublisher@@0UTimerParams@@A, 5138h; TimerParams CBrowserSettingChangePublisher::_slowTimerParams
0x18025907e  call    cs:__imp_GetCurrentThreadId
0x180259085  nop     dword ptr [rax+rax+00h]
0x18025908a  cmp     eax, cs:g_tidParking
0x180259090  jnz     short loc_1802590A3
0x180259092  mov     r14b, 1
0x180259095  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x18025909c  nop     dword ptr [rax+rax+00h]
0x1802590a1  jmp     short loc_1802590AD
0x1802590a3  mov     r14b, r13b
0x1802590a6  lea     rax, [rdi+0F4h]
0x1802590ad  lea     r15, [rdi+0F8h]
0x1802590b4  mov     rdx, rax
0x1802590b7  mov     r8, r15
0x1802590ba  mov     cl, r14b
0x1802590bd  call    IECreateThreadRef
0x1802590c2  test    eax, eax
0x1802590c4  js      loc_1802592FE
0x1802590ca  test    r14b, r14b
0x1802590cd  jz      loc_1802591C6
0x1802590d3  mov     rcx, [r15]
0x1802590d6  call    cs:__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z; ProcessSetRefCountIUnknown(IUnknown *)
0x1802590dd  nop     dword ptr [rax+rax+00h]
0x1802590e2  mov     rcx, [r15]; punk
0x1802590e5  call    cs:__imp_SHSetInstanceExplorer
0x1802590ec  nop     dword ptr [rax+rax+00h]
0x1802590f1  xor     r9d, r9d; lpName
0x1802590f4  xor     r8d, r8d; bInitialState
0x1802590f7  xor     edx, edx; bManualReset
0x1802590f9  xor     ecx, ecx; lpEventAttributes
0x1802590fb  call    cs:__imp_CreateEventW
0x180259102  nop     dword ptr [rax+rax+00h]
0x180259107  mov     rbx, rax
0x18025910a  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x180259111  nop     dword ptr [rax+rax+00h]
0x180259116  mov     r8, rbx
0x180259119  mov     edx, 19h
0x18025911e  mov     rcx, rax
0x180259121  mov     rax, [rax]
0x180259124  mov     rax, [rax+0F8h]
0x18025912b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259130  mov     rcx, rbx; hObject
0x180259133  call    cs:__imp_CloseHandle
0x18025913a  nop     dword ptr [rax+rax+00h]
0x18025913f  mov     ecx, [rsi+70h]; unsigned int
0x180259142  lea     rdx, [rsp+10E0h+Buffer]; struct _FILETIME *
0x180259147  mov     qword ptr [rsp+10E0h+Buffer.dwLowDateTime], r13
0x18025914c  call    ?GetSessionStartTime@@YA_NKPEAU_FILETIME@@@Z; GetSessionStartTime(ulong,_FILETIME *)
0x180259151  test    al, al
0x180259153  jz      short loc_18025915F
0x180259155  lea     rcx, [rsp+10E0h+Buffer]; lpBuffer
0x18025915a  call    ?LCIEUpdateSessionStartTime@@YAXPEBU_FILETIME@@@Z; LCIEUpdateSessionStartTime(_FILETIME const *)
0x18025915f  cmp     [rdi+208h], r13d
0x180259166  jnz     short loc_18025916F
0x180259168  xor     ecx, ecx
0x18025916a  call    IEOnFirstBrowserCreation
0x18025916f  mov     rcx, [rdi+118h]
0x180259176  mov     eax, 1
0x18025917b  mov     r8d, eax
0x18025917e  mov     edx, eax
0x180259180  call    ?_SetBusy@CTabWindowManager@@QEAAXW4RUN_ON_IDLE_BUSY_FLAGS@@0@Z; CTabWindowManager::_SetBusy(RUN_ON_IDLE_BUSY_FLAGS,RUN_ON_IDLE_BUSY_FLAGS)
0x180259185  mov     ecx, [rdi+2ACh]
0x18025918b  lea     rax, [rdi+41Ch]
0x180259192  mov     [rsp+10E0h+var_10B0], rax
0x180259197  xor     r9d, r9d
0x18025919a  mov     [rsp+10E0h+var_10B8], r13
0x18025919f  xor     r8d, r8d
0x1802591a2  mov     edx, 3EFh
0x1802591a7  mov     dword ptr [rsp+10E0h+lParam], 0Ah
0x1802591af  call    cs:__imp_?IsoAddIdleTask@@YAJKW4IDLEMANAGER_TASKTYPE@@KKW4IDLETASK_PRIORITY@@PEAXPEAK@Z; IsoAddIdleTask(ulong,IDLEMANAGER_TASKTYPE,ulong,ulong,IDLETASK_PRIORITY,void *,ulong *)
0x1802591b6  nop     dword ptr [rax+rax+00h]
0x1802591bb  test    eax, eax
0x1802591bd  jns     short loc_1802591C6
0x1802591bf  mov     ecx, 7
0x1802591c4  int     29h; Win8: RtlFailFast(ecx)
0x1802591c6  mov     rcx, [r15]
0x1802591c9  call    cs:__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z; IESetThreadRef(IUnknown *)
0x1802591d0  nop     dword ptr [rax+rax+00h]
0x1802591d5  test    r14b, r14b
0x1802591d8  jz      loc_1802592FE
0x1802591de  cmp     [rdi+20Ch], r13d
0x1802591e5  jnz     loc_1802592FE
0x1802591eb  cmp     [rdi+208h], r13d
0x1802591f2  jnz     loc_180259298
0x1802591f8  cmp     [rsi+80h], r13d
0x1802591ff  jnz     loc_180259298
0x180259205  mov     r14d, 10000009h
0x18025920b  cmp     [r12], r13d
0x18025920f  jnz     short loc_18025923D
0x180259211  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180259218  nop     dword ptr [rax+rax+00h]
0x18025921d  test    al, al
0x18025921f  jnz     short loc_18025923D
0x180259221  mov     ecx, r14d
0x180259224  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18025922b  nop     dword ptr [rax+rax+00h]
0x180259230  test    al, al
0x180259232  jnz     short loc_18025923D
0x180259234  cmp     [rsi+0C4h], r13d
0x18025923b  jz      short loc_180259298
0x18025923d  mov     ecx, r14d
0x180259240  mov     ebx, 1
0x180259245  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18025924c  nop     dword ptr [rax+rax+00h]
0x180259251  test    al, al
0x180259253  jz      short loc_18025925E
0x180259255  xor     ecx, ecx; unsigned __int16 *
0x180259257  call    ?RetrieveCookiesAndCreds@CRelaunch@@SAJPEBG@Z; CRelaunch::RetrieveCookiesAndCreds(ushort const *)
0x18025925c  jmp     short loc_18025929B
0x18025925e  cmp     [rsi+0C4h], r13d
0x180259265  jz      short loc_18025929B
0x180259267  mov     rcx, [rsi+160h]; int
0x18025926e  lea     r9, [rsp+10E0h+var_1090]; int
0x180259273  mov     [rsp+10E0h+var_10B8], r13; __int64
0x180259278  xor     r8d, r8d; int
0x18025927b  mov     edx, 8000h; int
0x180259280  mov     dword ptr [rsp+10E0h+lParam], 824h; cchBuf
0x180259288  call    IEGetNameAndFlagsEx
0x18025928d  test    eax, eax
0x18025928f  js      short loc_18025929B
0x180259291  lea     rcx, [rsp+10E0h+var_1090]
0x180259296  jmp     short loc_180259257
0x180259298  mov     ebx, r13d
0x18025929b  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1802592a2  nop     dword ptr [rax+rax+00h]
0x1802592a7  test    al, al
0x1802592a9  jz      short loc_1802592B4
0x1802592ab  lea     rcx, ?s_DualEngineCleanRecoveryStoresProc@CBrowserFrame@@KAKPEAX@Z; CBrowserFrame::s_DualEngineCleanRecoveryStoresProc(void *)
0x1802592b2  jmp     short loc_1802592E5
0x1802592b4  mov     edx, ebx; int
0x1802592b6  mov     rcx, rdi; this
0x1802592b9  call    ?_CheckForCrashedSessions@CBrowserFrame@@IEAAXH@Z; CBrowserFrame::_CheckForCrashedSessions(int)
0x1802592be  mov     r9d, 10000000h; unsigned int
0x1802592c4  mov     dword ptr [rsp+10E0h+lParam], 1388h; lParam
0x1802592cc  or      r8d, 0FFFFFFFFh; int
0x1802592d0  lea     rcx, ?s_ClearUnpinnedSiteRecoveryDataProc@CBrowserFrame@@KAKPEAX@Z; unsigned int (*)(void *)
0x1802592d7  xor     edx, edx; void *
0x1802592d9  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x1802592de  lea     rcx, ?s_CleanActiveRecoveryStoresProc@CBrowserFrame@@KAKPEAX@Z; unsigned int (*)(void *)
0x1802592e5  mov     r9d, 10000000h; unsigned int
0x1802592eb  mov     dword ptr [rsp+10E0h+lParam], 1388h; lParam
0x1802592f3  or      r8d, 0FFFFFFFFh; int
0x1802592f7  xor     edx, edx; void *
0x1802592f9  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x1802592fe  mov     rax, [rdi+8]
0x180259302  mov     byte ptr [rdi+342h], 1
0x180259309  mov     rcx, [rbp+0FE0h+var_40]
0x180259310  xor     rcx, rsp; StackCookie
0x180259313  call    __security_check_cookie
0x180259318  mov     rbx, [rsp+10E0h+arg_10]
0x180259320  add     rsp, 10B0h
0x180259327  pop     r15
0x180259329  pop     r14
0x18025932b  pop     r13
0x18025932d  pop     r12
0x18025932f  pop     rdi
0x180259330  pop     rsi
0x180259331  pop     rbp
0x180259332  retn
```
