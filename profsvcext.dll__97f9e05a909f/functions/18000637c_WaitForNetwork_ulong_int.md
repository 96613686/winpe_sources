# WaitForNetwork(ulong,int)

- ea: `0x18000637c`
- end: `0x1800066f0`
- name: `?WaitForNetwork@@YAJKH@Z`
- size: `884`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f610`

## callees

- `0x180005960`
- `0x18000637c`
- `0x1800066f8`
- `0x18000671c`
- `0x180006a9c`
- `0x180006b18`
- `0x180006b3c`
- `0x18000a520`
- `0x18000d160`
- `0x18000ed38`
- `0x18001026c`
- `0x18001038c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800063b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800063b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006422`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800064b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006563`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800064b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006563`
- `USER32!MsgWaitForMultipleObjects` at `0x1800064da`
- `USER32!MsgWaitForMultipleObjects` at `0x1800064da`
- `USER32!DispatchMessageW` at `0x18000650f`
- `USER32!DispatchMessageW` at `0x18000650f`
- `USER32!TranslateMessage` at `0x180006505`
- `USER32!TranslateMessage` at `0x180006505`
- `USER32!PeekMessageW` at `0x180006525`
- `USER32!PeekMessageW` at `0x180006525`

## string_xrefs

- `0x1800063d5`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x180006470`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x1800066a1`: `clientcore\ds\security\gina\profile\roaming\network.cpp`

## pseudocode

```c
__int64 __fastcall WaitForNetwork(DWORD dwMilliseconds, int a2)
{
  void *v4; // rbx
  wil::details *v5; // rcx
  HANDLE Event; // rdi
  int LastErrorFailHr; // eax
  unsigned int v8; // edi
  int HaveConnectivity; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // edi
  DWORD v14; // r14d
  int TickCount64; // eax
  int v16; // r15d
  __int64 v17; // rcx
  DWORD v18; // edi
  int v19; // ecx
  int v20; // r8d
  char *v21; // rax
  DWORD v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  int dwWakeMask; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  void *v28; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-C0h] BYREF
  void *v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+5Ch] [rbp-A4h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  MSG Msg; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v39[16]; // [rsp+E0h] [rbp-20h] BYREF
  char v40; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = 0;
  v28 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v28,
      Event);
    v4 = v28;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    v8 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x391,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        dwWakeMask);
      goto LABEL_50;
    }
  }
  v30 = v4;
  v31 = 0;
  v32 = a2;
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v27 = 0;
  HaveConnectivity = CConnectivityWatcher::RegisterForConnectivityNotification((CConnectivityWatcher *)&v30, &v27);
  v8 = HaveConnectivity;
  if ( HaveConnectivity < 0 )
  {
    v11 = 917;
LABEL_7:
    v12 = (unsigned int)HaveConnectivity;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)v12,
      dwWakeMask);
    goto LABEL_9;
  }
  v13 = v27;
  if ( !v27 && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v10, EVENT_ROAMING_PROFILE_WAIT_START, dwMilliseconds);
  v14 = dwMilliseconds;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v13 )
      {
        CConnectivityWatcher::~CConnectivityWatcher((CConnectivityWatcher *)&v30);
        v8 = 0;
        goto LABEL_50;
      }
      TickCount64 = GetTickCount64();
      pHandles = v4;
      v16 = TickCount64;
      v18 = MsgWaitForMultipleObjects(1u, &pHandles, 0, v14, 0x1CBFu);
      if ( v18 != 1 )
        break;
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 0xF80001u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      HaveConnectivity = CConnectivityWatcher::HaveConnectivity((CConnectivityWatcher *)&v30, &v27);
      v8 = HaveConnectivity;
      if ( HaveConnectivity < 0 )
      {
        v11 = 946;
        goto LABEL_7;
      }
      v13 = v27;
      if ( v27 )
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
        {
          v21 = &v40;
          goto LABEL_30;
        }
      }
      else
      {
        v22 = GetTickCount64() - v16;
        if ( v22 >= v14 )
        {
          if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
            McTemplateU0q_EtwEventWriteTransfer(v23, EVENT_ROAMING_PROFILE_WAIT_TIMEOUT, dwMilliseconds);
          v8 = -2147023436;
          v11 = 962;
          v12 = 2147943860LL;
          goto LABEL_8;
        }
        v14 -= v22;
      }
    }
    if ( v18 )
      break;
    HaveConnectivity = CConnectivityWatcher::HaveConnectivity((CConnectivityWatcher *)&v30, &v27);
    v8 = HaveConnectivity;
    if ( HaveConnectivity < 0 )
    {
      v11 = 968;
      goto LABEL_7;
    }
    v13 = v27;
    if ( !v27 )
    {
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v19, (unsigned int)"I", v20, 1, (__int64)v39);
      v8 = -2147467259;
      v11 = 973;
      v12 = 2147500037LL;
      goto LABEL_8;
    }
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    {
      v21 = v39;
LABEL_30:
      McGenEventWrite_EtwEventWriteTransfer(
        v19,
        (unsigned int)EVENT_ROAMING_PROFILE_WAIT_COMPLETE,
        v20,
        1,
        (__int64)v21);
    }
  }
  if ( v18 != 258 )
  {
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x20) != 0 )
    {
      if ( (int)v18 > 0 )
        v24 = (unsigned __int16)v18 | 0x80070000;
      else
        v24 = v18;
      McTemplateU0q_EtwEventWriteTransfer(v17, "H", v24);
    }
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3DE,
           (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
           (const char *)v18,
           dwWakeMask);
LABEL_9:
    CConnectivityWatcher::~CConnectivityWatcher((CConnectivityWatcher *)&v30);
    goto LABEL_50;
  }
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v17, EVENT_ROAMING_PROFILE_WAIT_TIMEOUT, dwMilliseconds);
  CConnectivityWatcher::~CConnectivityWatcher((CConnectivityWatcher *)&v30);
  v8 = -2147024638;
LABEL_50:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
  return v8;
}

```

## disassembly

```asm
0x18000637c  push    rbp
0x18000637e  push    rbx
0x18000637f  push    rsi
0x180006380  push    rdi
0x180006381  push    r14
0x180006383  push    r15
0x180006385  lea     rbp, [rsp-18h]
0x18000638a  sub     rsp, 118h
0x180006391  mov     rax, cs:__security_cookie
0x180006398  xor     rax, rsp
0x18000639b  mov     [rbp+40h+var_40], rax
0x18000639f  mov     r14d, edx
0x1800063a2  mov     esi, ecx
0x1800063a4  xor     ebx, ebx
0x1800063a6  xor     edx, edx; lpName
0x1800063a8  xor     ecx, ecx; lpEventAttributes
0x1800063aa  mov     [rsp+140h+var_108], rbx
0x1800063af  mov     r9d, 1F0003h; dwDesiredAccess
0x1800063b5  xor     r8d, r8d; dwFlags
0x1800063b8  call    cs:__imp_CreateEventExW
0x1800063be  mov     rdi, rax
0x1800063c1  test    rax, rax
0x1800063c4  jnz     short loc_1800063EE
0x1800063c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800063cb  mov     edi, eax
0x1800063cd  test    eax, eax
0x1800063cf  jns     short loc_180006406
0x1800063d1  mov     rcx, [rbp+48h]; this
0x1800063d5  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x1800063dc  mov     r9d, eax; char *
0x1800063df  mov     edx, 391h; void *
0x1800063e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063e9  jmp     loc_1800066C8
0x1800063ee  call    cs:__imp_GetLastError
0x1800063f4  mov     rdx, rdi
0x1800063f7  lea     rcx, [rsp+140h+var_108]
0x1800063fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006401  mov     rbx, [rsp+140h+var_108]
0x180006406  xor     r8d, r8d; Flags
0x180006409  mov     [rsp+140h+var_F0], rbx
0x18000640e  xor     edx, edx; dwSpinCount
0x180006410  mov     [rsp+140h+var_E8], 0
0x180006418  lea     rcx, [rsp+140h+CriticalSection]; lpCriticalSection
0x18000641d  mov     [rsp+140h+var_E4], r14d
0x180006422  call    cs:__imp_InitializeCriticalSectionEx
0x180006428  lea     rdx, [rsp+140h+var_110]; int *
0x18000642d  mov     [rbp+40h+var_B8], 0
0x180006435  lea     rcx, [rsp+140h+var_F0]; this
0x18000643a  mov     [rbp+40h+var_B0], 0
0x180006441  mov     [rbp+40h+var_A8], 0
0x180006449  mov     [rbp+40h+var_A0], 0
0x180006451  mov     [rsp+140h+var_110], 0
0x180006459  call    ?RegisterForConnectivityNotification@CConnectivityWatcher@@QEAAJPEAH@Z; CConnectivityWatcher::RegisterForConnectivityNotification(int *)
0x18000645e  mov     edi, eax
0x180006460  test    eax, eax
0x180006462  jns     short loc_18000648B
0x180006464  mov     edx, 395h; void *
0x180006469  mov     r9d, eax; char *
0x18000646c  mov     rcx, [rbp+48h]; this
0x180006470  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x180006477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000647c  lea     rcx, [rsp+140h+var_F0]; this
0x180006481  call    ??1CConnectivityWatcher@@QEAA@XZ; CConnectivityWatcher::~CConnectivityWatcher(void)
0x180006486  jmp     loc_1800066C8
0x18000648b  mov     edi, [rsp+140h+var_110]
0x18000648f  test    edi, edi
0x180006491  jnz     short loc_1800064AB
0x180006493  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x18000649a  jz      short loc_1800064AB
0x18000649c  mov     r8d, esi
0x18000649f  lea     rdx, EVENT_ROAMING_PROFILE_WAIT_START
0x1800064a6  call    McTemplateU0q_EtwEventWriteTransfer
0x1800064ab  mov     r14d, esi
0x1800064ae  test    edi, edi
0x1800064b0  jnz     loc_1800066BC
0x1800064b6  call    cs:__imp_GetTickCount64
0x1800064bc  mov     r9d, r14d; dwMilliseconds
0x1800064bf  mov     [rsp+140h+pHandles], rbx
0x1800064c4  xor     r8d, r8d; fWaitAll
0x1800064c7  mov     [rsp+140h+dwWakeMask], 1CBFh; unsigned int
0x1800064cf  lea     rdx, [rsp+140h+pHandles]; pHandles
0x1800064d4  mov     r15, rax
0x1800064d7  lea     ecx, [rdi+1]; nCount
0x1800064da  call    cs:__imp_MsgWaitForMultipleObjects
0x1800064e0  mov     edi, eax
0x1800064e2  cmp     eax, 1
0x1800064e5  jnz     loc_180006579
0x1800064eb  xorps   xmm0, xmm0
0x1800064ee  mov     edi, 0F80001h
0x1800064f3  movups  xmmword ptr [rbp+40h+Msg.hwnd], xmm0
0x1800064f7  movups  xmmword ptr [rbp+40h+Msg.wParam], xmm0
0x1800064fb  movups  xmmword ptr [rbp+40h+Msg.time], xmm0
0x1800064ff  jmp     short loc_180006515
0x180006501  lea     rcx, [rbp+40h+Msg]; lpMsg
0x180006505  call    cs:__imp_TranslateMessage
0x18000650b  lea     rcx, [rbp+40h+Msg]; lpMsg
0x18000650f  call    cs:__imp_DispatchMessageW
0x180006515  xor     r9d, r9d; wMsgFilterMax
0x180006518  mov     [rsp+140h+dwWakeMask], edi; wRemoveMsg
0x18000651c  xor     r8d, r8d; wMsgFilterMin
0x18000651f  lea     rcx, [rbp+40h+Msg]; lpMsg
0x180006523  xor     edx, edx; hWnd
0x180006525  call    cs:__imp_PeekMessageW
0x18000652b  test    eax, eax
0x18000652d  jnz     short loc_180006501
0x18000652f  lea     rdx, [rsp+140h+var_110]; int *
0x180006534  lea     rcx, [rsp+140h+var_F0]; this
0x180006539  call    ?HaveConnectivity@CConnectivityWatcher@@QEAAJPEAH@Z; CConnectivityWatcher::HaveConnectivity(int *)
0x18000653e  mov     edi, eax
0x180006540  test    eax, eax
0x180006542  js      loc_1800065F9
0x180006548  mov     edi, [rsp+140h+var_110]
0x18000654c  test    edi, edi
0x18000654e  jz      short loc_180006563
0x180006550  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180006557  jz      loc_1800064AE
0x18000655d  lea     rax, [rbp+40h+var_50]
0x180006561  jmp     short loc_1800065B3
0x180006563  call    cs:__imp_GetTickCount64
0x180006569  sub     eax, r15d
0x18000656c  cmp     eax, r14d
0x18000656f  jnb     short loc_1800065CF
0x180006571  sub     r14d, eax
0x180006574  jmp     loc_1800064AE
0x180006579  test    edi, edi
0x18000657b  jnz     loc_180006643
0x180006581  lea     rdx, [rsp+140h+var_110]; int *
0x180006586  lea     rcx, [rsp+140h+var_F0]; this
0x18000658b  call    ?HaveConnectivity@CConnectivityWatcher@@QEAAJPEAH@Z; CConnectivityWatcher::HaveConnectivity(int *)
0x180006590  mov     edi, eax
0x180006592  test    eax, eax
0x180006594  js      loc_180006639
0x18000659a  mov     edi, [rsp+140h+var_110]
0x18000659e  test    edi, edi
0x1800065a0  jz      short loc_180006603
0x1800065a2  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800065a9  jz      loc_1800064AE
0x1800065af  lea     rax, [rbp+40h+var_60]
0x1800065b3  mov     r9d, 1
0x1800065b9  mov     qword ptr [rsp+140h+dwWakeMask], rax
0x1800065be  lea     rdx, EVENT_ROAMING_PROFILE_WAIT_COMPLETE
0x1800065c5  call    McGenEventWrite_EtwEventWriteTransfer
0x1800065ca  jmp     loc_1800064AE
0x1800065cf  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800065d6  jz      short loc_1800065E7
0x1800065d8  mov     r8d, esi
0x1800065db  lea     rdx, EVENT_ROAMING_PROFILE_WAIT_TIMEOUT
0x1800065e2  call    McTemplateU0q_EtwEventWriteTransfer
0x1800065e7  mov     edi, 800705B4h
0x1800065ec  mov     edx, 3C2h
0x1800065f1  mov     r9d, edi
0x1800065f4  jmp     loc_18000646C
0x1800065f9  mov     edx, 3B2h
0x1800065fe  jmp     loc_180006469
0x180006603  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x18000660a  jz      short loc_180006627
0x18000660c  lea     rax, [rbp+40h+var_60]
0x180006610  mov     r9d, 1
0x180006616  lea     rdx, EVENT_ROAMING_PROFILE_WAIT_NOT_READY; "I"
0x18000661d  mov     qword ptr [rsp+140h+dwWakeMask], rax
0x180006622  call    McGenEventWrite_EtwEventWriteTransfer
0x180006627  mov     edi, 80004005h
0x18000662c  mov     edx, 3CDh
0x180006631  mov     r9d, edi
0x180006634  jmp     loc_18000646C
0x180006639  mov     edx, 3C8h
0x18000663e  jmp     loc_180006469
0x180006643  cmp     edi, 102h
0x180006649  jnz     short loc_180006674
0x18000664b  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x180006652  jz      short loc_180006663
0x180006654  mov     r8d, esi
0x180006657  lea     rdx, EVENT_ROAMING_PROFILE_WAIT_TIMEOUT
0x18000665e  call    McTemplateU0q_EtwEventWriteTransfer
0x180006663  lea     rcx, [rsp+140h+var_F0]; this
0x180006668  call    ??1CConnectivityWatcher@@QEAA@XZ; CConnectivityWatcher::~CConnectivityWatcher(void)
0x18000666d  mov     edi, 80070102h
0x180006672  jmp     short loc_1800066C8
0x180006674  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 20h
0x18000667b  jz      short loc_18000669D
0x18000667d  test    edi, edi
0x18000667f  jg      short loc_180006686
0x180006681  mov     r8d, edi
0x180006684  jmp     short loc_180006691
0x180006686  movzx   r8d, di
0x18000668a  or      r8d, 80070000h
0x180006691  lea     rdx, EVENT_ROAMING_PROFILE_WAIT_FAILURE; "H"
0x180006698  call    McTemplateU0q_EtwEventWriteTransfer
0x18000669d  mov     rcx, [rbp+48h]; this
0x1800066a1  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x1800066a8  mov     r9d, edi; char *
0x1800066ab  mov     edx, 3DEh; void *
0x1800066b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800066b5  mov     edi, eax
0x1800066b7  jmp     loc_18000647C
0x1800066bc  lea     rcx, [rsp+140h+var_F0]; this
0x1800066c1  call    ??1CConnectivityWatcher@@QEAA@XZ; CConnectivityWatcher::~CConnectivityWatcher(void)
0x1800066c6  xor     edi, edi
0x1800066c8  lea     rcx, [rsp+140h+var_108]
0x1800066cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066d2  mov     eax, edi
0x1800066d4  mov     rcx, [rbp+40h+var_40]
0x1800066d8  xor     rcx, rsp; StackCookie
0x1800066db  call    __security_check_cookie
0x1800066e0  add     rsp, 118h
0x1800066e7  pop     r15
0x1800066e9  pop     r14
0x1800066eb  pop     rdi
0x1800066ec  pop     rsi
0x1800066ed  pop     rbx
0x1800066ee  pop     rbp
0x1800066ef  retn
```
