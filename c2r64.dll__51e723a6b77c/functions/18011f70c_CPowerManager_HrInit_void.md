# CPowerManager::HrInit(void)

- ea: `0x18011f70c`
- end: `0x18011fc29`
- name: `?HrInit@CPowerManager@@IEAAJXZ`
- size: `1309`
- prototype: `__int64 __fastcall(CPowerManager *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18011e670`

## callees

- `0x180013c78`
- `0x1800264b4`
- `0x18002d5c8`
- `0x180030a94`
- `0x18003e690`
- `0x1800723a8`
- `0x18009afa0`
- `0x1800aa580`
- `0x180105c44`
- `0x180117a38`
- `0x18011e0d8`
- `0x18011e6b4`
- `0x18011eb20`
- `0x18011f70c`
- `0x18011fc2c`
- `0x180121508`
- `0x180121b98`
- `0x180146090`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18011f80a`
- `KERNEL32!GetLastError` at `0x18011f96b`
- `KERNEL32!GetLastError` at `0x18011fbce`
- `KERNEL32!GetLastError` at `0x18011f80a`
- `KERNEL32!GetLastError` at `0x18011f96b`
- `KERNEL32!GetLastError` at `0x18011fbce`
- `KERNEL32!SetEvent` at `0x18011f9fd`
- `KERNEL32!SetEvent` at `0x18011f9fd`
- `KERNEL32!SetLastError` at `0x18011f94b`
- `KERNEL32!SetLastError` at `0x18011f94b`
- `KERNEL32!GetCurrentThreadId` at `0x18011f7a4`
- `KERNEL32!GetCurrentThreadId` at `0x18011f7a4`
- `KERNEL32!CreateMemoryResourceNotification` at `0x18011fa17`
- `KERNEL32!CreateMemoryResourceNotification` at `0x18011fa35`
- `KERNEL32!CreateMemoryResourceNotification` at `0x18011fa17`
- `KERNEL32!CreateMemoryResourceNotification` at `0x18011fa35`
- `USER32!SetWindowLongPtrW` at `0x18011f960`
- `USER32!SetWindowLongPtrW` at `0x18011f960`
- `USER32!RegisterRawInputDevices` at `0x18011f8e5`
- `USER32!RegisterRawInputDevices` at `0x18011f8e5`
- `USER32!SetWindowsHookExW` at `0x18011fbbc`
- `USER32!SetWindowsHookExW` at `0x18011fbbc`
- `IMM32!ImmDisableIME` at `0x18011f800`
- `IMM32!ImmDisableIME` at `0x18011f800`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPowerManager::HrInit(CPowerManager *this)
{
  unsigned int v2; // esi
  unsigned int Dw; // eax
  __int64 Window; // rax
  HWND v5; // rax
  void (*v6)(HWND, unsigned int, unsigned __int64, unsigned int); // r9
  void (*v7)(HWND, unsigned int, unsigned __int64, unsigned int); // r9
  CPowerManager *v8; // rcx
  HANDLE MemoryResourceNotification; // rbx
  _QWORD *v10; // r15
  HANDLE v11; // r14
  const struct Mso::Memory::NoThrow::MarkingLeak_t *v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // r14
  __int64 v16; // rcx
  HHOOK v17; // rax
  _QWORD v19[2]; // [rsp+68h] [rbp-69h] BYREF
  WNDCLASSEXW v20; // [rsp+78h] [rbp-59h] BYREF
  RAWINPUTDEVICE pRawInputDevices; // [rsp+C8h] [rbp-9h] BYREF
  __int64 v22; // [rsp+D8h] [rbp+7h]
  HWND v23; // [rsp+E0h] [rbp+Fh]
  int v24; // [rsp+E8h] [rbp+17h]
  int v25; // [rsp+ECh] [rbp+1Bh]
  HWND v26; // [rsp+F0h] [rbp+1Fh]

  if ( (byte_18021CCC1 & 2) != 0 )
    McTemplateU0p_EventWriteTransfer(guidProviderOfficeThreadpool_Context, PMStartup, this);
  if ( *((_QWORD *)this + 21) )
    MsoShipAssertTagProc(4014431);
  if ( *((_BYTE *)this + 403) )
    MsoShipAssertTagProc(4014432);
  *((_BYTE *)this + 403) = 0;
  if ( *((_DWORD *)this + 24) )
    MsoShipAssertTagProc(4014433);
  *((_DWORD *)this + 24) = GetCurrentThreadId();
  memset(&v20, 0, sizeof(v20));
  v20.cbSize = 80;
  v20.lpfnWndProc = (WNDPROC)CPowerManager::PowerWndProc;
  v20.lpszClassName = L"OfficePowerManagerWindow";
  if ( !(unsigned __int16)IsolationAwareRegisterClassExW(&v20) )
    goto LABEL_10;
  *((_BYTE *)this + 400) = 1;
  if ( !ImmDisableIME(0) )
    GetLastError();
  Dw = MsoDwRegGetDw((const struct _msoreg *)&vmsoridDiscardableCacheTimerInterval);
  *((_DWORD *)this + 195) = Dw;
  if ( Dw < 0x2710 )
    *((_DWORD *)this + 195) = 10000;
  *((_DWORD *)this + 194) = MsoDwRegGetDw((const struct _msoreg *)&vmsoridDiscardableCacheDefaultTimeout);
  *((_DWORD *)this + 196) = MsoDwRegGetDw((const struct _msoreg *)&vmsoridDiscardableCacheDisableCallbacks);
  *((_DWORD *)this + 197) = MsoDwRegGetDw((const struct _msoreg *)&vmsoridDiscardableCacheDontQueueCallbacks);
  Window = IsolationAwareCreateWindowExW();
  *((_QWORD *)this + 21) = Window;
  if ( !Window )
    goto LABEL_10;
  *((_QWORD *)this + 61) = MsoDwRegGetDw((const struct _msoreg *)&vmsoridAppUserIdleTimerInterval);
  *((_QWORD *)this + 60) = MsoDwRegGetDw((const struct _msoreg *)&vmsoridAppUserIdleResetInterval);
  v5 = (HWND)*((_QWORD *)this + 21);
  *(_QWORD *)&pRawInputDevices.usUsagePage = 131073;
  pRawInputDevices.hwndTarget = v5;
  v22 = 393217;
  v23 = v5;
  v24 = 13;
  v25 = 32;
  v26 = v5;
  if ( !RegisterRawInputDevices(&pRawInputDevices, 3u, 0x10u) )
    goto LABEL_10;
  if ( *((_QWORD *)this + 61) > 0xFFFFFFFF )
    __fastfail(5u);
  LODWORD(v19[0]) = *((_QWORD *)this + 61);
  HIDWORD(v19[0]) = 4095;
  if ( !MsoSetTimer(
          *((HWND *)this + 21),
          (-(__int64)(*((_BYTE *)this + 404) != 0) & 0x100) + 5,
          (const struct MsoTimeoutInterval *)v19,
          v6) )
    MsoShipAssertTagProc(4014469);
  SetLastError(0);
  if ( !SetWindowLongPtrW(*((HWND *)this + 21), -21, (LONG_PTR)this) )
  {
    if ( GetLastError() )
    {
LABEL_10:
      v2 = -2147467259;
      goto LABEL_50;
    }
  }
  v2 = 0;
  v19[0] = 0x271000001388LL;
  if ( !MsoSetTimer(
          *((HWND *)this + 21),
          (-(__int64)(*((_BYTE *)this + 404) != 0) & 0x100) + 7,
          (const struct MsoTimeoutInterval *)v19,
          v7) )
  {
    MsoShipAssertTagProc(4014471);
    CPowerManager::DoDelayedInit(this);
  }
  CPowerFlagsChangeHelper::CPowerFlagsChangeHelper(
    (CPowerFlagsChangeHelper *)&pRawInputDevices,
    *((struct ITpThreadManager **)this + 20),
    this);
  if ( CPowerManager::FHaveResumeEvents(this) )
  {
    CPowerManager::HrStartThreadManagerWaiterThread(v8, (struct CPowerFlagsChangeHelper *)&pRawInputDevices);
    SetEvent(*((HANDLE *)this + (((*(_QWORD *)&pRawInputDevices.usUsagePage >> 11) & 1LL) == 0) + 22));
  }
  *(_WORD *)((char *)this + 401) = 257;
  CPowerFlagsChangeHelper::~CPowerFlagsChangeHelper((CPowerFlagsChangeHelper *)&pRawInputDevices);
  MemoryResourceNotification = CreateMemoryResourceNotification(LowMemoryResourceNotification);
  v10 = (_QWORD *)((char *)this + 496);
  Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)this + 496);
  *((_QWORD *)this + 62) = MemoryResourceNotification;
  v11 = CreateMemoryResourceNotification(HighMemoryResourceNotification);
  Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)this + 504);
  *((_QWORD *)this + 63) = v11;
  if ( !*((_QWORD *)this + 62) || !v11 )
    MsoShipAssertTagProc(4014472);
  if ( *v10 && *((_QWORD *)this + 63) )
  {
    v13 = operator new(0x28u, v12);
    v14 = v13;
    if ( v13 )
    {
      v19[0] = this;
      v15 = *((_QWORD *)this + 20);
      *v13 = &IMsoDebugMessage::`vftable';
      *((_DWORD *)v13 + 2) = 1;
      *v13 = &CMemoryCallBack::`vftable'{for `CTpBase'};
      v13[2] = &CMemoryCallBack::`vftable'{for `ITpWaitCallback'};
      v13[3] = 0;
      v13[4] = 0;
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v16 = v14[3];
        if ( v16 )
        {
          v14[3] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v14[3] = v15;
      }
      Mso::ComUtil::HrQueryFrom<ITpPowerManagerInternal,ITpPowerManagerInternal *>(v14 + 4, v19);
    }
    else
    {
      v14 = 0;
    }
    if ( v14 )
    {
      if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD *, char *))(**((_QWORD **)this + 20) + 40LL))(
             *((_QWORD *)this + 20),
             8449,
             v14 + 2,
             (char *)this + 512) >= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 64) + 216LL))(
          *((_QWORD *)this + 64),
          *v10,
          0xFFFFFFFFLL);
LABEL_42:
        if ( v14 )
          (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
        goto LABEL_47;
      }
    }
    else
    {
      MsoShipAssertTagProc(4014473);
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 88LL))(*((_QWORD *)this + 20)) )
      MsoShipAssertTagProc(4014474);
    goto LABEL_42;
  }
  Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)this + 496);
  Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)this + 504);
LABEL_47:
  v17 = SetWindowsHookExW(5, PowerManagerWindowHook, 0, Mso::Threadpool::details::vdwTidMain);
  *((_QWORD *)this + 99) = v17;
  if ( !v17 && !GetLastError() )
    MsoShipAssertTagProc(4014475);
LABEL_50:
  if ( !*((_BYTE *)this + 402) )
    CPowerManager::UnInit(this);
  return v2;
}

```

## disassembly

```asm
0x18011f70c  mov     rax, rsp
0x18011f70f  mov     [rax+10h], rbx
0x18011f713  mov     [rax+18h], rsi
0x18011f717  mov     [rax+20h], rdi
0x18011f71b  push    rbp
0x18011f71c  push    r12
0x18011f71e  push    r13
0x18011f720  push    r14
0x18011f722  push    r15
0x18011f724  lea     rbp, [rax-5Fh]
0x18011f728  sub     rsp, 100h
0x18011f72f  mov     rax, cs:__security_cookie
0x18011f736  xor     rax, rsp
0x18011f739  mov     [rbp+57h+var_30], rax
0x18011f73d  mov     rdi, rcx
0x18011f740  mov     esi, 2
0x18011f745  test    cs:byte_18021CCC1, sil
0x18011f74c  jz      short loc_18011F764
0x18011f74e  mov     r8, rcx
0x18011f751  lea     rdx, PMStartup
0x18011f758  lea     rcx, guidProviderOfficeThreadpool_Context
0x18011f75f  call    McTemplateU0p_EventWriteTransfer
0x18011f764  xor     r13d, r13d
0x18011f767  cmp     [rdi+0A8h], r13
0x18011f76e  jz      short loc_18011F77A
0x18011f770  mov     ecx, 3D415Fh
0x18011f775  call    MsoShipAssertTagProc
0x18011f77a  cmp     [rdi+193h], r13b
0x18011f781  jz      short loc_18011F78D
0x18011f783  mov     ecx, 3D4160h
0x18011f788  call    MsoShipAssertTagProc
0x18011f78d  mov     [rdi+193h], r13b
0x18011f794  cmp     [rdi+60h], r13d
0x18011f798  jz      short loc_18011F7A4
0x18011f79a  mov     ecx, 3D4161h
0x18011f79f  call    MsoShipAssertTagProc
0x18011f7a4  call    cs:__imp_GetCurrentThreadId
0x18011f7aa  mov     [rdi+60h], eax
0x18011f7ad  mov     ebx, 50h ; 'P'
0x18011f7b2  mov     r8d, ebx; Size
0x18011f7b5  xor     edx, edx; Val
0x18011f7b7  lea     rcx, [rbp+57h+var_B0]; void *
0x18011f7bb  call    memset
0x18011f7c0  mov     [rbp+57h+var_B0.cbSize], ebx
0x18011f7c3  lea     rax, ?PowerWndProc@CPowerManager@@KA_JPEAUHWND__@@I_K_J@Z; CPowerManager::PowerWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18011f7ca  mov     [rbp+57h+var_B0.lpfnWndProc], rax
0x18011f7ce  lea     rax, ?c_szPowerManagerWindowClassName@@3QB_WB; "OfficePowerManagerWindow"
0x18011f7d5  mov     [rbp+57h+var_B0.lpszClassName], rax
0x18011f7d9  lea     rcx, [rbp+57h+var_B0]; WNDCLASSEXW *
0x18011f7dd  call    IsolationAwareRegisterClassExW
0x18011f7e2  test    ax, ax
0x18011f7e5  jnz     short loc_18011F7F1
0x18011f7e7  mov     esi, 80004005h
0x18011f7ec  jmp     loc_18011FBE2
0x18011f7f1  mov     r12d, 1
0x18011f7f7  mov     [rdi+190h], r12b
0x18011f7fe  xor     ecx, ecx; DWORD
0x18011f800  call    cs:__imp_ImmDisableIME
0x18011f806  test    eax, eax
0x18011f808  jnz     short loc_18011F811
0x18011f80a  call    cs:__imp_GetLastError
0x18011f810  nop
0x18011f811  lea     rcx, ?vmsoridDiscardableCacheTimerInterval@@3U_msoreg@@B; struct _msoreg *
0x18011f818  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18011f81d  mov     [rdi+30Ch], eax
0x18011f823  mov     ebx, 2710h
0x18011f828  cmp     eax, ebx
0x18011f82a  jnb     short loc_18011F832
0x18011f82c  mov     [rdi+30Ch], ebx
0x18011f832  lea     rcx, ?vmsoridDiscardableCacheDefaultTimeout@@3U_msoreg@@B; struct _msoreg *
0x18011f839  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18011f83e  mov     [rdi+308h], eax
0x18011f844  lea     rcx, ?vmsoridDiscardableCacheDisableCallbacks@@3U_msoreg@@B; struct _msoreg *
0x18011f84b  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18011f850  mov     [rdi+310h], eax
0x18011f856  lea     rcx, ?vmsoridDiscardableCacheDontQueueCallbacks@@3U_msoreg@@B; struct _msoreg *
0x18011f85d  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18011f862  mov     [rdi+314h], eax
0x18011f868  call    IsolationAwareCreateWindowExW
0x18011f86d  mov     [rdi+0A8h], rax
0x18011f874  test    rax, rax
0x18011f877  jz      loc_18011F7E7
0x18011f87d  lea     rcx, ?vmsoridAppUserIdleTimerInterval@@3U_msoreg@@B; struct _msoreg *
0x18011f884  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18011f889  mov     eax, eax
0x18011f88b  mov     [rdi+1E8h], rax
0x18011f892  lea     rcx, ?vmsoridAppUserIdleResetInterval@@3U_msoreg@@B; struct _msoreg *
0x18011f899  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x18011f89e  mov     eax, eax
0x18011f8a0  mov     [rdi+1E0h], rax
0x18011f8a7  mov     rax, [rdi+0A8h]
0x18011f8ae  mov     qword ptr [rbp+57h+pRawInputDevices.usUsagePage], 20001h
0x18011f8b6  mov     [rbp+57h+pRawInputDevices.hwndTarget], rax
0x18011f8ba  mov     [rbp+57h+var_50], 60001h
0x18011f8c2  mov     [rbp+57h+var_48], rax
0x18011f8c6  mov     [rbp+57h+var_40], 0Dh
0x18011f8cd  mov     [rbp+57h+var_3C], 20h ; ' '
0x18011f8d4  mov     [rbp+57h+var_38], rax
0x18011f8d8  mov     edx, 3; uiNumDevices
0x18011f8dd  lea     r8d, [rdx+0Dh]; cbSize
0x18011f8e1  lea     rcx, [rbp+57h+pRawInputDevices]; pRawInputDevices
0x18011f8e5  call    cs:__imp_RegisterRawInputDevices
0x18011f8eb  test    eax, eax
0x18011f8ed  jz      loc_18011F7E7
0x18011f8f3  mov     rax, [rdi+1E8h]
0x18011f8fa  mov     ecx, 0FFFFFFFFh
0x18011f8ff  cmp     rax, rcx
0x18011f902  ja      loc_18011FC22
0x18011f908  mov     dword ptr [rbp+57h+var_C0], eax
0x18011f90b  mov     dword ptr [rbp+57h+var_C0+4], 0FFFh
0x18011f912  mov     al, [rdi+194h]
0x18011f918  neg     al
0x18011f91a  sbb     rdx, rdx
0x18011f91d  mov     r14d, 100h
0x18011f923  and     rdx, r14
0x18011f926  add     rdx, 5; unsigned __int64
0x18011f92a  lea     r8, [rbp+57h+var_C0]; struct MsoTimeoutInterval *
0x18011f92e  mov     rcx, [rdi+0A8h]; HWND
0x18011f935  call    ?MsoSetTimer@@YA_KPEAUHWND__@@_KAEBUMsoTimeoutInterval@@P6AX0I1K@Z@Z; MsoSetTimer(HWND__ *,unsigned __int64,MsoTimeoutInterval const &,void (*)(HWND__ *,uint,unsigned __int64,ulong))
0x18011f93a  test    rax, rax
0x18011f93d  jnz     short loc_18011F949
0x18011f93f  mov     ecx, 3D4185h
0x18011f944  call    MsoShipAssertTagProc
0x18011f949  xor     ecx, ecx; dwErrCode
0x18011f94b  call    cs:__imp_SetLastError
0x18011f951  mov     r8, rdi; dwNewLong
0x18011f954  mov     edx, 0FFFFFFEBh; nIndex
0x18011f959  mov     rcx, [rdi+0A8h]; hWnd
0x18011f960  call    cs:__imp_SetWindowLongPtrW
0x18011f966  test    rax, rax
0x18011f969  jnz     short loc_18011F979
0x18011f96b  call    cs:__imp_GetLastError
0x18011f971  test    eax, eax
0x18011f973  jnz     loc_18011F7E7
0x18011f979  mov     esi, r13d
0x18011f97c  mov     dword ptr [rbp+57h+var_C0], 1388h
0x18011f983  mov     dword ptr [rbp+57h+var_C0+4], ebx
0x18011f986  mov     al, [rdi+194h]
0x18011f98c  neg     al
0x18011f98e  sbb     rdx, rdx
0x18011f991  and     rdx, r14
0x18011f994  add     rdx, 7; unsigned __int64
0x18011f998  lea     r8, [rbp+57h+var_C0]; struct MsoTimeoutInterval *
0x18011f99c  mov     rcx, [rdi+0A8h]; HWND
0x18011f9a3  call    ?MsoSetTimer@@YA_KPEAUHWND__@@_KAEBUMsoTimeoutInterval@@P6AX0I1K@Z@Z; MsoSetTimer(HWND__ *,unsigned __int64,MsoTimeoutInterval const &,void (*)(HWND__ *,uint,unsigned __int64,ulong))
0x18011f9a8  test    rax, rax
0x18011f9ab  jnz     short loc_18011F9BF
0x18011f9ad  mov     ecx, 3D4187h
0x18011f9b2  call    MsoShipAssertTagProc
0x18011f9b7  mov     rcx, rdi; this
0x18011f9ba  call    ?DoDelayedInit@CPowerManager@@IEAAXXZ; CPowerManager::DoDelayedInit(void)
0x18011f9bf  mov     r8, rdi; struct ITpPowerManagerInternal *
0x18011f9c2  mov     rdx, [rdi+0A0h]; struct ITpThreadManager *
0x18011f9c9  lea     rcx, [rbp+57h+pRawInputDevices]; this
0x18011f9cd  call    ??0CPowerFlagsChangeHelper@@QEAA@PEAUITpThreadManager@@PEAUITpPowerManagerInternal@@@Z; CPowerFlagsChangeHelper::CPowerFlagsChangeHelper(ITpThreadManager *,ITpPowerManagerInternal *)
0x18011f9d2  mov     rcx, rdi; this
0x18011f9d5  call    ?FHaveResumeEvents@CPowerManager@@IEBA_NXZ; CPowerManager::FHaveResumeEvents(void)
0x18011f9da  test    al, al
0x18011f9dc  jz      short loc_18011FA03
0x18011f9de  lea     rdx, [rbp+57h+pRawInputDevices]; struct CPowerFlagsChangeHelper *
0x18011f9e2  call    ?HrStartThreadManagerWaiterThread@CPowerManager@@IEAAJPEAVCPowerFlagsChangeHelper@@@Z; CPowerManager::HrStartThreadManagerWaiterThread(CPowerFlagsChangeHelper *)
0x18011f9e7  mov     rcx, qword ptr [rbp+57h+pRawInputDevices.usUsagePage]
0x18011f9eb  shr     rcx, 0Bh
0x18011f9ef  not     rcx
0x18011f9f2  and     rcx, r12
0x18011f9f5  mov     rcx, [rdi+rcx*8+0B0h]; hEvent
0x18011f9fd  call    cs:__imp_SetEvent
0x18011fa03  mov     word ptr [rdi+191h], 101h
0x18011fa0c  lea     rcx, [rbp+57h+pRawInputDevices]; this
0x18011fa10  call    ??1CPowerFlagsChangeHelper@@QEAA@XZ; CPowerFlagsChangeHelper::~CPowerFlagsChangeHelper(void)
0x18011fa15  xor     ecx, ecx; NotificationType
0x18011fa17  call    cs:__imp_CreateMemoryResourceNotification
0x18011fa1d  mov     rbx, rax
0x18011fa20  lea     r15, [rdi+1F0h]
0x18011fa27  mov     rcx, r15
0x18011fa2a  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x18011fa2f  mov     [r15], rbx
0x18011fa32  mov     ecx, r12d; NotificationType
0x18011fa35  call    cs:__imp_CreateMemoryResourceNotification
0x18011fa3b  mov     r14, rax
0x18011fa3e  lea     rbx, [rdi+1F8h]
0x18011fa45  mov     rcx, rbx
0x18011fa48  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x18011fa4d  mov     [rbx], r14
0x18011fa50  cmp     [r15], r13
0x18011fa53  jz      short loc_18011FA5A
0x18011fa55  test    r14, r14
0x18011fa58  jnz     short loc_18011FA64
0x18011fa5a  mov     ecx, 3D4188h
0x18011fa5f  call    MsoShipAssertTagProc
0x18011fa64  cmp     [r15], r13
0x18011fa67  jz      loc_18011FB97
0x18011fa6d  cmp     [rbx], r13
0x18011fa70  jz      loc_18011FB97
0x18011fa76  mov     ecx, 28h ; '('; unsigned __int64
0x18011fa7b  call    ??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new(unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x18011fa80  mov     rbx, rax
0x18011fa83  test    rax, rax
0x18011fa86  jz      short loc_18011FB00
0x18011fa88  mov     [rbp+57h+var_C0], rdi
0x18011fa8c  mov     r14, [rdi+0A0h]
0x18011fa93  lea     rax, ??_7IMsoDebugMessage@@6B@; const IMsoDebugMessage::`vftable'
0x18011fa9a  mov     [rbx], rax
0x18011fa9d  mov     [rbx+8], r12d
0x18011faa1  lea     rax, ??_7CMemoryCallBack@@6BCTpBase@@@; const CMemoryCallBack::`vftable'{for `CTpBase'}
0x18011faa8  mov     [rbx], rax
0x18011faab  lea     rax, ??_7CMemoryCallBack@@6BITpWaitCallback@@@; const CMemoryCallBack::`vftable'{for `ITpWaitCallback'}
0x18011fab2  mov     [rbx+10h], rax
0x18011fab6  mov     [rbx+18h], r13
0x18011faba  mov     [rbx+20h], r13
0x18011fabe  test    r14, r14
0x18011fac1  jz      short loc_18011FAF1
0x18011fac3  mov     rax, [r14]
0x18011fac6  mov     rcx, r14
0x18011fac9  mov     rax, [rax+8]
0x18011facd  call    cs:__guard_dispatch_icall_fptr
0x18011fad3  mov     rcx, [rbx+18h]
0x18011fad7  test    rcx, rcx
0x18011fada  jz      short loc_18011FAED
0x18011fadc  mov     [rbx+18h], r13
0x18011fae0  mov     rax, [rcx]
0x18011fae3  mov     rax, [rax+10h]
0x18011fae7  call    cs:__guard_dispatch_icall_fptr
0x18011faed  mov     [rbx+18h], r14
0x18011faf1  lea     rdx, [rbp+57h+var_C0]
0x18011faf5  lea     rcx, [rbx+20h]
0x18011faf9  call    ??$HrQueryFrom@UITpPowerManagerInternal@@PEAU1@@ComUtil@Mso@@YAJAEAV?$TCntPtr@UITpPowerManagerInternal@@@1@AEBQEAUITpPowerManagerInternal@@AEBU_GUID@@@Z; Mso::ComUtil::HrQueryFrom<ITpPowerManagerInternal,ITpPowerManagerInternal *>(Mso::TCntPtr<ITpPowerManagerInternal> &,ITpPowerManagerInternal * const &,_GUID const &)
0x18011fafe  jmp     short loc_18011FB03
0x18011fb00  mov     rbx, r13
0x18011fb03  test    rbx, rbx
0x18011fb06  jnz     short loc_18011FB4B
0x18011fb08  mov     ecx, 3D4189h
0x18011fb0d  call    MsoShipAssertTagProc
0x18011fb12  mov     rcx, [rdi+0A0h]
0x18011fb19  mov     rax, [rcx]
0x18011fb1c  mov     rax, [rax+58h]
0x18011fb20  call    cs:__guard_dispatch_icall_fptr
0x18011fb26  test    eax, eax
0x18011fb28  jnz     short loc_18011FB34
0x18011fb2a  mov     ecx, 3D418Ah
0x18011fb2f  call    MsoShipAssertTagProc
0x18011fb34  test    rbx, rbx
0x18011fb37  jz      short loc_18011FBA7
0x18011fb39  mov     rax, [rbx]
0x18011fb3c  mov     rcx, rbx
0x18011fb3f  mov     rax, [rax+10h]
0x18011fb43  call    cs:__guard_dispatch_icall_fptr
0x18011fb49  jmp     short loc_18011FBA7
0x18011fb4b  mov     rcx, [rdi+0A0h]
0x18011fb52  mov     rax, [rcx]
0x18011fb55  lea     r8, [rbx+10h]
0x18011fb59  lea     r14, [rdi+200h]
0x18011fb60  mov     r9, r14
0x18011fb63  mov     edx, 2101h
0x18011fb68  mov     rax, [rax+28h]
0x18011fb6c  call    cs:__guard_dispatch_icall_fptr
0x18011fb72  test    eax, eax
0x18011fb74  js      short loc_18011FB12
0x18011fb76  lfence
0x18011fb79  mov     rcx, [r14]
0x18011fb7c  mov     rax, [rcx]
0x18011fb7f  mov     r8d, 0FFFFFFFFh
0x18011fb85  mov     rdx, [r15]
0x18011fb88  mov     rax, [rax+0D8h]
0x18011fb8f  call    cs:__guard_dispatch_icall_fptr
0x18011fb95  jmp     short loc_18011FB34
0x18011fb97  mov     rcx, r15
0x18011fb9a  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x18011fb9f  mov     rcx, rbx
0x18011fba2  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x18011fba7  mov     r9d, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; dwThreadId
0x18011fbae  xor     r8d, r8d; hmod
0x18011fbb1  lea     rdx, ?PowerManagerWindowHook@@YA_JH_K_J@Z; lpfn
0x18011fbb8  lea     ecx, [r8+5]; idHook
0x18011fbbc  call    cs:__imp_SetWindowsHookExW
0x18011fbc2  mov     [rdi+318h], rax
0x18011fbc9  test    rax, rax
0x18011fbcc  jnz     short loc_18011FBE2
0x18011fbce  call    cs:__imp_GetLastError
0x18011fbd4  test    eax, eax
0x18011fbd6  jnz     short loc_18011FBE2
0x18011fbd8  mov     ecx, 3D418Bh
0x18011fbdd  call    MsoShipAssertTagProc
0x18011fbe2  cmp     [rdi+192h], r13b
0x18011fbe9  jnz     short loc_18011FBF3
0x18011fbeb  mov     rcx, rdi; this
0x18011fbee  call    ?UnInit@CPowerManager@@IEAAXXZ; CPowerManager::UnInit(void)
0x18011fbf3  mov     eax, esi
0x18011fbf5  mov     rcx, [rbp+57h+var_30]
0x18011fbf9  xor     rcx, rsp; StackCookie
0x18011fbfc  call    __security_check_cookie
0x18011fc01  lea     r11, [rsp+120h+var_20]
0x18011fc09  mov     rbx, [r11+38h]
0x18011fc0d  mov     rsi, [r11+40h]
0x18011fc11  mov     rdi, [r11+48h]
0x18011fc15  mov     rsp, r11
0x18011fc18  pop     r15
0x18011fc1a  pop     r14
0x18011fc1c  pop     r13
0x18011fc1e  pop     r12
  ... truncated ...
```
