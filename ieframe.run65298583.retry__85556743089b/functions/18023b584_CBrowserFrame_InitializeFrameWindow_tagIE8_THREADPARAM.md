# CBrowserFrame::_InitializeFrameWindow(tagIE8_THREADPARAM *)

- ea: `0x18023b584`
- end: `0x18023b95b`
- name: `?_InitializeFrameWindow@CBrowserFrame@@IEAAPEAUHWND__@@PEAUtagIE8_THREADPARAM@@@Z`
- size: `983`
- prototype: `HWND __fastcall(CBrowserFrame *__hidden this, struct tagIE8_THREADPARAM *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18023b108`

## callees

- `0x18002320c`
- `0x18008ce0c`
- `0x180093960`
- `0x1800cc420`
- `0x1801122f0`
- `0x1801988c8`
- `0x1801b549c`
- `0x180233460`
- `0x180235398`
- `0x180236048`
- `0x18023626c`
- `0x180236330`
- `0x18023b584`
- `0x18023bc88`
- `0x18023f5b4`
- `0x1802405a4`
- `0x180244c94`
- `0x180247738`
- `0x18028c858`
- `0x18053996c`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18023b759`
- `KERNEL32!CreateEventW` at `0x18023b759`
- `KERNEL32!InitOnceExecuteOnce` at `0x18023b6c1`
- `KERNEL32!InitOnceExecuteOnce` at `0x18023b6c1`
- `KERNEL32!CloseHandle` at `0x18023b785`
- `KERNEL32!CloseHandle` at `0x18023b785`
- `KERNEL32!GetCurrentThreadId` at `0x18023b66d`
- `KERNEL32!GetCurrentThreadId` at `0x18023b6f4`
- `KERNEL32!GetCurrentThreadId` at `0x18023b66d`
- `KERNEL32!GetCurrentThreadId` at `0x18023b6f4`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x18023b749`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x18023b749`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18023b80f`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18023b80f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18023b851`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18023b851`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18023b85e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18023b879`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18023b85e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18023b879`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18023b8c9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18023b8c9`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18023b60b`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18023b60b`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18023b762`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18023b762`
- `msIso!__imp_?IsoAddIdleTask@@YAJKW4IDLEMANAGER_TASKTYPE@@KKW4IDLETASK_PRIORITY@@PEAXPEAK@Z` at `0x18023b7fb`
- `msIso!__imp_?IsoAddIdleTask@@YAJKW4IDLEMANAGER_TASKTYPE@@KKW4IDLETASK_PRIORITY@@PEAXPEAK@Z` at `0x18023b7fb`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18023b705`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x18023b705`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x18023b740`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x18023b740`

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
      InitOnceExecuteOnce(&stru_180666C30, SBEUtil::InitOnceIsSingleBrowserExperienceEnabled, 0, 0);
      if ( !byte_180666C38 )
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
0x18023b584  mov     [rsp-8+arg_10], rbx
0x18023b589  push    rbp
0x18023b58a  push    rsi
0x18023b58b  push    rdi
0x18023b58c  push    r12
0x18023b58e  push    r13
0x18023b590  push    r14
0x18023b592  push    r15
0x18023b594  lea     rbp, [rsp-0FB0h]
0x18023b59c  mov     eax, 10B0h
0x18023b5a1  call    _alloca_probe
0x18023b5a6  sub     rsp, rax
0x18023b5a9  mov     rax, cs:__security_cookie
0x18023b5b0  xor     rax, rsp
0x18023b5b3  mov     [rbp+0FE0h+var_40], rax
0x18023b5ba  mov     eax, [rdx+0D0h]
0x18023b5c0  mov     rsi, rdx
0x18023b5c3  mov     [rcx+218h], eax
0x18023b5c9  mov     rdi, rcx
0x18023b5cc  call    ?_RegisterFrameClass@CBrowserFrame@@IEAAJXZ; CBrowserFrame::_RegisterFrameClass(void)
0x18023b5d1  xor     r13d, r13d
0x18023b5d4  test    eax, eax
0x18023b5d6  js      loc_18023B926
0x18023b5dc  lea     rdx, [rsp+10E0h+Buffer]; HWND *
0x18023b5e1  mov     qword ptr [rsp+10E0h+Buffer.dwLowDateTime], r13
0x18023b5e6  mov     rcx, rdi; this
0x18023b5e9  call    ?_CreateFrameWindow@CBrowserFrame@@IEAAJPEAPEAUHWND__@@@Z; CBrowserFrame::_CreateFrameWindow(HWND__ * *)
0x18023b5ee  test    eax, eax
0x18023b5f0  js      loc_18023B926
0x18023b5f6  mov     ecx, [rdi+2ACh]
0x18023b5fc  lea     r8, [rsp+10E0h+var_1098]
0x18023b601  xor     r9d, r9d
0x18023b604  mov     [rsp+10E0h+var_1098], r13
0x18023b609  mov     dl, 14h
0x18023b60b  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x18023b611  mov     rbx, qword ptr [rsp+10E0h+Buffer.dwLowDateTime]
0x18023b616  test    eax, eax
0x18023b618  js      short loc_18023B62F
0x18023b61a  mov     rax, [rsp+10E0h+var_1098]
0x18023b61f  mov     dword ptr [rax+38h], 3
0x18023b626  mov     rax, [rsp+10E0h+var_1098]
0x18023b62b  mov     [rax+28h], rbx
0x18023b62f  mov     rax, [rdi+110h]
0x18023b636  lea     r8, [rdi+70h]
0x18023b63a  mov     [rax+20h], rbx
0x18023b63e  mov     rax, rdi
0x18023b641  neg     rax
0x18023b644  sbb     rcx, rcx
0x18023b647  and     rcx, r8; punk
0x18023b64a  call    ?TLSSetThreadOwner@@YAXPEAUIUnknown@@@Z; TLSSetThreadOwner(IUnknown *)
0x18023b64f  mov     rcx, rdi; this
0x18023b652  call    ?_SetFrameIcon@CBrowserFrame@@IEAAXXZ; CBrowserFrame::_SetFrameIcon(void)
0x18023b657  mov     rdx, rbx; HWND
0x18023b65a  mov     rcx, rdi; this
0x18023b65d  call    ?_CreateClientCaption@CBrowserFrame@@IEAAXPEAUHWND__@@@Z; CBrowserFrame::_CreateClientCaption(HWND__ *)
0x18023b662  mov     rdx, rbx; HWND
0x18023b665  mov     rcx, rdi; dwNewLong
0x18023b668  call    ?_CreateGripperOverlayWindow@CBrowserFrame@@IEAAXPEAUHWND__@@@Z; CBrowserFrame::_CreateGripperOverlayWindow(HWND__ *)
0x18023b66d  call    cs:__imp_GetCurrentThreadId
0x18023b673  cmp     eax, cs:g_tidParking
0x18023b679  jnz     short loc_18023B685
0x18023b67b  mov     ecx, 1; int
0x18023b680  call    ?IsSecurityLevelSecure@@YAHH@Z; IsSecurityLevelSecure(int)
0x18023b685  mov     r9, [rdi+168h]; struct CHomePageProtector *
0x18023b68c  lea     r12, [rdi+224h]
0x18023b693  mov     rcx, [rdi+8]; HWND
0x18023b697  mov     r8, r12; int *
0x18023b69a  mov     rdx, rsi; struct tagIE8_THREADPARAM *
0x18023b69d  call    ?ResolveInitialBrowserLocation@@YAJPEAUHWND__@@PEAUtagIE8_THREADPARAM@@PEAHPEAVCHomePageProtector@@@Z; ResolveInitialBrowserLocation(HWND__ *,tagIE8_THREADPARAM *,int *,CHomePageProtector *)
0x18023b6a2  mov     rdx, rsi; struct tagIE8_THREADPARAM *
0x18023b6a5  mov     rcx, rdi; this
0x18023b6a8  call    ?_LoadFrameState@CBrowserFrame@@IEAAXPEAUtagIE8_THREADPARAM@@@Z; CBrowserFrame::_LoadFrameState(tagIE8_THREADPARAM *)
0x18023b6ad  xor     r9d, r9d; Context
0x18023b6b0  lea     rdx, SBEUtil__InitOnceIsSingleBrowserExperienceEnabled; InitFn
0x18023b6b7  xor     r8d, r8d; Parameter
0x18023b6ba  lea     rcx, stru_180666C30; InitOnce
0x18023b6c1  call    cs:__imp_InitOnceExecuteOnce
0x18023b6c7  cmp     cs:byte_180666C38, r13b
0x18023b6ce  jnz     short loc_18023B6F4
0x18023b6d0  call    ?CreateSettingSyncProcess@@YAJXZ; CreateSettingSyncProcess(void)
0x18023b6d5  mov     rax, [rdi+8]
0x18023b6d9  mov     cs:?_hwnd@CBrowserSettingChangePublisher@@0PEAUHWND__@@EA, rax; HWND__ * CBrowserSettingChangePublisher::_hwnd
0x18023b6e0  mov     cs:?_fastTimerParams@CBrowserSettingChangePublisher@@0UTimerParams@@A, 5137h; TimerParams CBrowserSettingChangePublisher::_fastTimerParams
0x18023b6ea  mov     cs:?_slowTimerParams@CBrowserSettingChangePublisher@@0UTimerParams@@A, 5138h; TimerParams CBrowserSettingChangePublisher::_slowTimerParams
0x18023b6f4  call    cs:__imp_GetCurrentThreadId
0x18023b6fa  cmp     eax, cs:g_tidParking
0x18023b700  jnz     short loc_18023B70D
0x18023b702  mov     r14b, 1
0x18023b705  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x18023b70b  jmp     short loc_18023B717
0x18023b70d  mov     r14b, r13b
0x18023b710  lea     rax, [rdi+0F4h]
0x18023b717  lea     r15, [rdi+0F8h]
0x18023b71e  mov     rdx, rax
0x18023b721  mov     r8, r15
0x18023b724  mov     cl, r14b
0x18023b727  call    IECreateThreadRef
0x18023b72c  test    eax, eax
0x18023b72e  js      loc_18023B926
0x18023b734  test    r14b, r14b
0x18023b737  jz      loc_18023B80C
0x18023b73d  mov     rcx, [r15]
0x18023b740  call    cs:__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z; ProcessSetRefCountIUnknown(IUnknown *)
0x18023b746  mov     rcx, [r15]; punk
0x18023b749  call    cs:__imp_SHSetInstanceExplorer
0x18023b74f  xor     r9d, r9d; lpName
0x18023b752  xor     r8d, r8d; bInitialState
0x18023b755  xor     edx, edx; bManualReset
0x18023b757  xor     ecx, ecx; lpEventAttributes
0x18023b759  call    cs:__imp_CreateEventW
0x18023b75f  mov     rbx, rax
0x18023b762  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x18023b768  mov     r8, rbx
0x18023b76b  mov     edx, 19h
0x18023b770  mov     rcx, rax
0x18023b773  mov     rax, [rax]
0x18023b776  mov     rax, [rax+0F8h]
0x18023b77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023b782  mov     rcx, rbx; hObject
0x18023b785  call    cs:__imp_CloseHandle
0x18023b78b  mov     ecx, [rsi+70h]; unsigned int
0x18023b78e  lea     rdx, [rsp+10E0h+Buffer]; struct _FILETIME *
0x18023b793  mov     qword ptr [rsp+10E0h+Buffer.dwLowDateTime], r13
0x18023b798  call    ?GetSessionStartTime@@YA_NKPEAU_FILETIME@@@Z; GetSessionStartTime(ulong,_FILETIME *)
0x18023b79d  test    al, al
0x18023b79f  jz      short loc_18023B7AB
0x18023b7a1  lea     rcx, [rsp+10E0h+Buffer]; lpBuffer
0x18023b7a6  call    ?LCIEUpdateSessionStartTime@@YAXPEBU_FILETIME@@@Z; LCIEUpdateSessionStartTime(_FILETIME const *)
0x18023b7ab  cmp     [rdi+208h], r13d
0x18023b7b2  jnz     short loc_18023B7BB
0x18023b7b4  xor     ecx, ecx
0x18023b7b6  call    IEOnFirstBrowserCreation
0x18023b7bb  mov     rcx, [rdi+118h]
0x18023b7c2  mov     eax, 1
0x18023b7c7  mov     r8d, eax
0x18023b7ca  mov     edx, eax
0x18023b7cc  call    ?_SetBusy@CTabWindowManager@@QEAAXW4RUN_ON_IDLE_BUSY_FLAGS@@0@Z; CTabWindowManager::_SetBusy(RUN_ON_IDLE_BUSY_FLAGS,RUN_ON_IDLE_BUSY_FLAGS)
0x18023b7d1  mov     ecx, [rdi+2ACh]
0x18023b7d7  lea     rax, [rdi+41Ch]
0x18023b7de  mov     [rsp+10E0h+var_10B0], rax
0x18023b7e3  xor     r9d, r9d
0x18023b7e6  mov     [rsp+10E0h+var_10B8], r13
0x18023b7eb  xor     r8d, r8d
0x18023b7ee  mov     edx, 3EFh
0x18023b7f3  mov     dword ptr [rsp+10E0h+lParam], 0Ah
0x18023b7fb  call    cs:__imp_?IsoAddIdleTask@@YAJKW4IDLEMANAGER_TASKTYPE@@KKW4IDLETASK_PRIORITY@@PEAXPEAK@Z; IsoAddIdleTask(ulong,IDLEMANAGER_TASKTYPE,ulong,ulong,IDLETASK_PRIORITY,void *,ulong *)
0x18023b801  test    eax, eax
0x18023b803  jns     short loc_18023B80C
0x18023b805  mov     ecx, 7
0x18023b80a  int     29h; Win8: RtlFailFast(ecx)
0x18023b80c  mov     rcx, [r15]
0x18023b80f  call    cs:__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z; IESetThreadRef(IUnknown *)
0x18023b815  test    r14b, r14b
0x18023b818  jz      loc_18023B926
0x18023b81e  cmp     [rdi+20Ch], r13d
0x18023b825  jnz     loc_18023B926
0x18023b82b  cmp     [rdi+208h], r13d
0x18023b832  jnz     loc_18023B8C6
0x18023b838  cmp     [rsi+80h], r13d
0x18023b83f  jnz     loc_18023B8C6
0x18023b845  mov     r14d, 10000009h
0x18023b84b  cmp     [r12], r13d
0x18023b84f  jnz     short loc_18023B871
0x18023b851  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18023b857  test    al, al
0x18023b859  jnz     short loc_18023B871
0x18023b85b  mov     ecx, r14d
0x18023b85e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18023b864  test    al, al
0x18023b866  jnz     short loc_18023B871
0x18023b868  cmp     [rsi+0C4h], r13d
0x18023b86f  jz      short loc_18023B8C6
0x18023b871  mov     ecx, r14d
0x18023b874  mov     ebx, 1
0x18023b879  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18023b87f  test    al, al
0x18023b881  jz      short loc_18023B88C
0x18023b883  xor     ecx, ecx; unsigned __int16 *
0x18023b885  call    ?RetrieveCookiesAndCreds@CRelaunch@@SAJPEBG@Z; CRelaunch::RetrieveCookiesAndCreds(ushort const *)
0x18023b88a  jmp     short loc_18023B8C9
0x18023b88c  cmp     [rsi+0C4h], r13d
0x18023b893  jz      short loc_18023B8C9
0x18023b895  mov     rcx, [rsi+160h]; int
0x18023b89c  lea     r9, [rsp+10E0h+var_1090]; int
0x18023b8a1  mov     [rsp+10E0h+var_10B8], r13; __int64
0x18023b8a6  xor     r8d, r8d; int
0x18023b8a9  mov     edx, 8000h; int
0x18023b8ae  mov     dword ptr [rsp+10E0h+lParam], 824h; cchBuf
0x18023b8b6  call    IEGetNameAndFlagsEx
0x18023b8bb  test    eax, eax
0x18023b8bd  js      short loc_18023B8C9
0x18023b8bf  lea     rcx, [rsp+10E0h+var_1090]
0x18023b8c4  jmp     short loc_18023B885
0x18023b8c6  mov     ebx, r13d
0x18023b8c9  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18023b8cf  test    al, al
0x18023b8d1  jz      short loc_18023B8DC
0x18023b8d3  lea     rcx, ?s_DualEngineCleanRecoveryStoresProc@CBrowserFrame@@KAKPEAX@Z; CBrowserFrame::s_DualEngineCleanRecoveryStoresProc(void *)
0x18023b8da  jmp     short loc_18023B90D
0x18023b8dc  mov     edx, ebx; int
0x18023b8de  mov     rcx, rdi; this
0x18023b8e1  call    ?_CheckForCrashedSessions@CBrowserFrame@@IEAAXH@Z; CBrowserFrame::_CheckForCrashedSessions(int)
0x18023b8e6  mov     r9d, 10000000h; unsigned int
0x18023b8ec  mov     dword ptr [rsp+10E0h+lParam], 1388h; lParam
0x18023b8f4  or      r8d, 0FFFFFFFFh; int
0x18023b8f8  lea     rcx, ?s_ClearUnpinnedSiteRecoveryDataProc@CBrowserFrame@@KAKPEAX@Z; unsigned int (*)(void *)
0x18023b8ff  xor     edx, edx; void *
0x18023b901  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x18023b906  lea     rcx, ?s_CleanActiveRecoveryStoresProc@CBrowserFrame@@KAKPEAX@Z; unsigned int (*)(void *)
0x18023b90d  mov     r9d, 10000000h; unsigned int
0x18023b913  mov     dword ptr [rsp+10E0h+lParam], 1388h; lParam
0x18023b91b  or      r8d, 0FFFFFFFFh; int
0x18023b91f  xor     edx, edx; void *
0x18023b921  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x18023b926  mov     rax, [rdi+8]
0x18023b92a  mov     byte ptr [rdi+342h], 1
0x18023b931  mov     rcx, [rbp+0FE0h+var_40]
0x18023b938  xor     rcx, rsp; StackCookie
0x18023b93b  call    __security_check_cookie
0x18023b940  mov     rbx, [rsp+10E0h+arg_10]
0x18023b948  add     rsp, 10B0h
0x18023b94f  pop     r15
0x18023b951  pop     r14
0x18023b953  pop     r13
0x18023b955  pop     r12
0x18023b957  pop     rdi
0x18023b958  pop     rsi
0x18023b959  pop     rbp
0x18023b95a  retn
```
