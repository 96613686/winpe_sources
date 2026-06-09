# CAICProxy::StaticTaskMonitorThreadProc(void *)

- ea: `0x1800bd150`
- end: `0x1800bd45b`
- name: `?StaticTaskMonitorThreadProc@CAICProxy@@CAKPEAX@Z`
- size: `779`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000f900`
- `0x18008ae98`
- `0x180094988`
- `0x1800a4324`
- `0x1800bcacc`
- `0x1800bd0b0`
- `0x1800bd150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800bd32f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800bd32f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bd36b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bd36b`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800bd20e`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800bd20e`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800bd454`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800bd454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd338`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bd323`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800bd323`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800bd266`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800bd3b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800bd266`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800bd3b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd25b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd3a8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd3d0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd25b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd3a8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd3d0`

## pseudocode

```c
void __fastcall __noreturn CAICProxy::StaticTaskMonitorThreadProc(PVOID Parameter)
{
  __int64 v2; // rcx
  const char *v3; // r9
  int v4; // r12d
  bool v5; // si
  char v6; // r14
  LARGE_INTEGER v7; // rbx
  HANDLE v8; // rax
  const unsigned __int16 *v9; // rcx
  void *v10; // r15
  LARGE_INTEGER v11; // rcx
  DWORD v12; // r13d
  DWORD v13; // eax
  bool v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[7]; // [rsp+41h] [rbp-BFh] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER v18; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  LOBYTE(v2) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SafeModeRedundantWatchdog>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SafeModeRedundantWatchdog>::GetImpl'::`2'::impl);
  if ( (unsigned __int8)wil::verify_bool<bool,0>(v2) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4CA,
      (unsigned int)"clientcore\\windows\\advcore\\ctf\\uim\\aicproxy.cpp",
      v3);
  v4 = 0;
  if ( !Parameter )
    v4 = -2147024809;
  v20 = v4;
  GetDesktopUniqueName(L"Local\\MSCTF.CtfMonitorInstMutex", Name);
  v5 = 0;
  v14 = 0;
  v6 = 0;
  v15[0] = 0;
  v18.QuadPart = 0;
  v7.QuadPart = 1;
  PerformanceCount.QuadPart = 0;
  v21 = 0;
  v17 = 0;
  while ( 1 )
  {
    v8 = OpenMutexW(0x100000u, 0, Name);
    v10 = v8;
    if ( v8 )
    {
      Handles[0] = hHandle;
      Handles[1] = v8;
      if ( v18.QuadPart )
      {
        Frequency.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        if ( QueryPerformanceFrequency(&Frequency) )
        {
          v11 = Frequency;
        }
        else
        {
          v11.QuadPart = 1;
          Frequency.QuadPart = 1;
        }
        PerformanceCount.QuadPart = 1000000 * (PerformanceCount.QuadPart - v18.QuadPart) / v11.QuadPart;
        v17 = 1000000 * v17 / v11.QuadPart;
        CtfTraceLoggingTelemetry::CiceroServerRestart<long &,bool &,bool &,long &,unsigned long &,long &,unsigned long &>(
          (unsigned int)&v20,
          (unsigned int)&v14,
          (unsigned int)v15,
          (unsigned int)&PerformanceCount.HighPart,
          (__int64)&PerformanceCount,
          (__int64)&v17 + 4,
          (__int64)&v17);
        v21 = 0;
        v18.QuadPart = 0;
        PerformanceCount.QuadPart = 0;
        v17 = 0;
      }
      else if ( !v6 )
      {
        v6 = 1;
        v15[0] = 1;
      }
      v12 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      ReleaseMutex(v10);
      CloseHandle(v10);
      v9 = (const unsigned __int16 *)(v12 - 128);
      if ( v12 == 128 || !v12 )
      {
        v5 = 1;
        v14 = 1;
      }
    }
    else if ( !v18.QuadPart )
    {
      QueryPerformanceCounter(&v18);
    }
    if ( !v5 )
    {
      CCtfmonHelper::StartCtfmonProcess(v9);
      v13 = WaitForSingleObject(hHandle, 0x1388u);
      v5 = v13 != 258;
      v14 = v13 != 258;
      if ( v13 == 258 )
        continue;
    }
    if ( v18.QuadPart )
    {
      Frequency.QuadPart = 0;
      if ( PerformanceCount.QuadPart )
        QueryPerformanceCounter(&PerformanceCount);
      if ( QueryPerformanceFrequency(&Frequency) )
        v7 = Frequency;
      else
        Frequency.QuadPart = 1;
      PerformanceCount.QuadPart = 1000000 * (PerformanceCount.QuadPart - v18.QuadPart) / v7.QuadPart;
      v17 = 1000000 * v17 / v7.QuadPart;
      CtfTraceLoggingTelemetry::CiceroServerRestart<long &,bool &,bool &,long &,unsigned long &,long &,unsigned long &>(
        (unsigned int)&v20,
        (unsigned int)&v14,
        (unsigned int)v15,
        (unsigned int)&PerformanceCount.HighPart,
        (__int64)&PerformanceCount,
        (__int64)&v17 + 4,
        (__int64)&v17);
    }
    ExitThread(v4 < 0);
  }
}

```

## disassembly

```asm
0x1800bd150  push    rbp
0x1800bd152  push    rbx
0x1800bd153  push    rsi
0x1800bd154  push    rdi
0x1800bd155  push    r12
0x1800bd157  push    r13
0x1800bd159  push    r14
0x1800bd15b  push    r15
0x1800bd15d  lea     rbp, [rsp-1B8h]
0x1800bd165  sub     rsp, 2B8h
0x1800bd16c  mov     rax, cs:__security_cookie
0x1800bd173  xor     rax, rsp
0x1800bd176  mov     [rbp+1F0h+var_50], rax
0x1800bd17d  mov     rbx, rcx
0x1800bd180  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SafeModeRedundantWatchdog@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SafeModeRedundantWatchdog@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SafeModeRedundantWatchdog> `wil::Feature<__WilFeatureTraits_Feature_SafeModeRedundantWatchdog>::GetImpl(void)'::`2'::impl
0x1800bd187  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SafeModeRedundantWatchdog@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SafeModeRedundantWatchdog>::__private_IsEnabled(void)
0x1800bd18c  mov     cl, al
0x1800bd18e  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x1800bd193  xor     r13d, r13d
0x1800bd196  test    al, al
0x1800bd198  jz      short loc_1800BD1B3
0x1800bd19a  mov     rcx, [rbp+1F8h]; this
0x1800bd1a1  lea     r8, aClientcoreWind_3; "clientcore\\windows\\advcore\\ctf\\uim"...
0x1800bd1a8  mov     edx, 4CAh; void *
0x1800bd1ad  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800bd1b3  test    rbx, rbx
0x1800bd1b6  lea     rdx, [rbp+1F0h+Name]; unsigned __int16 *
0x1800bd1ba  mov     eax, 80070057h
0x1800bd1bf  lea     rcx, aLocalMsctfCtfm_0; "Local\\MSCTF.CtfMonitorInstMutex"
0x1800bd1c6  mov     r12d, r13d
0x1800bd1c9  cmovz   r12d, eax
0x1800bd1cd  mov     [rsp+2F0h+var_288], r12d
0x1800bd1d2  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x1800bd1d7  mov     sil, r13b
0x1800bd1da  mov     [rsp+2F0h+var_2B0], r13b
0x1800bd1df  mov     r14b, r13b
0x1800bd1e2  mov     [rsp+2F0h+var_2AF], r13b
0x1800bd1e7  mov     qword ptr [rsp+2F0h+var_298], r13
0x1800bd1ec  mov     ebx, 1
0x1800bd1f1  mov     qword ptr [rsp+2F0h+PerformanceCount], r13
0x1800bd1f6  mov     rdi, r13
0x1800bd1f9  mov     [rsp+2F0h+var_280], r13
0x1800bd1fe  mov     [rsp+2F0h+var_2A0], r13
0x1800bd203  lea     r8, [rbp+1F0h+Name]; lpName
0x1800bd207  xor     edx, edx; bInheritHandle
0x1800bd209  mov     ecx, 100000h; dwDesiredAccess
0x1800bd20e  call    cs:__imp_OpenMutexW
0x1800bd214  mov     r15, rax
0x1800bd217  test    rax, rax
0x1800bd21a  jz      loc_1800BD3C4
0x1800bd220  mov     rcx, cs:hHandle
0x1800bd227  mov     [rsp+2F0h+Handles], rcx
0x1800bd22c  mov     [rbp+1F0h+var_270], rax
0x1800bd230  cmp     qword ptr [rsp+2F0h+var_298], r13
0x1800bd235  jnz     short loc_1800BD251
0x1800bd237  test    rdi, rdi
0x1800bd23a  jnz     short loc_1800BD251
0x1800bd23c  test    r14b, r14b
0x1800bd23f  jnz     loc_1800BD313
0x1800bd245  mov     r14b, bl
0x1800bd248  mov     [rsp+2F0h+var_2AF], bl
0x1800bd24c  jmp     loc_1800BD313
0x1800bd251  lea     rcx, [rsp+2F0h+PerformanceCount]; lpPerformanceCount
0x1800bd256  mov     qword ptr [rsp+2F0h+Frequency], r13
0x1800bd25b  call    cs:__imp_QueryPerformanceCounter
0x1800bd261  lea     rcx, [rsp+2F0h+Frequency]; lpFrequency
0x1800bd266  call    cs:__imp_QueryPerformanceFrequency
0x1800bd26c  test    eax, eax
0x1800bd26e  jnz     short loc_1800BD27A
0x1800bd270  mov     rcx, rbx
0x1800bd273  mov     qword ptr [rsp+2F0h+Frequency], rbx
0x1800bd278  jmp     short loc_1800BD27F
0x1800bd27a  mov     rcx, qword ptr [rsp+2F0h+Frequency]
0x1800bd27f  mov     rax, qword ptr [rsp+2F0h+PerformanceCount]
0x1800bd284  lea     r9, [rsp+2F0h+PerformanceCount+4]
0x1800bd289  sub     rax, qword ptr [rsp+2F0h+var_298]
0x1800bd28e  lea     r8, [rsp+2F0h+var_2AF]
0x1800bd293  imul    rax, 0F4240h
0x1800bd29a  cqo
0x1800bd29c  idiv    rcx
0x1800bd29f  mov     qword ptr [rsp+2F0h+PerformanceCount], rax
0x1800bd2a4  mov     rax, [rsp+2F0h+var_2A0]
0x1800bd2a9  sub     rax, rdi
0x1800bd2ac  imul    rax, 0F4240h
0x1800bd2b3  cqo
0x1800bd2b5  idiv    rcx
0x1800bd2b8  lea     rdx, [rsp+2F0h+var_2B0]
0x1800bd2bd  mov     [rsp+2F0h+var_2A0], rax
0x1800bd2c2  lea     rcx, [rsp+2F0h+var_288]
0x1800bd2c7  lea     rax, [rsp+2F0h+var_2A0]
0x1800bd2cc  mov     [rsp+2F0h+var_2C0], rax
0x1800bd2d1  lea     rax, [rsp+2F0h+var_2A0+4]
0x1800bd2d6  mov     [rsp+2F0h+var_2C8], rax
0x1800bd2db  lea     rax, [rsp+2F0h+PerformanceCount]
0x1800bd2e0  mov     [rsp+2F0h+var_2D0], rax
0x1800bd2e5  call    ??$CiceroServerRestart@AEAJAEA_NAEA_NAEAJAEAKAEAJAEAK@CtfTraceLoggingTelemetry@@SAXAEAJAEA_N10AEAK02@Z; CtfTraceLoggingTelemetry::CiceroServerRestart<long &,bool &,bool &,long &,ulong &,long &,ulong &>(long &,bool &,bool &,long &,ulong &,long &,ulong &)
0x1800bd2ea  mov     [rsp+2F0h+var_280], 0
0x1800bd2f3  mov     rdi, [rsp+2F0h+var_280]
0x1800bd2f8  mov     qword ptr [rsp+2F0h+var_298], 0
0x1800bd301  mov     qword ptr [rsp+2F0h+PerformanceCount], 0
0x1800bd30a  mov     [rsp+2F0h+var_2A0], 0
0x1800bd313  xor     r8d, r8d; bWaitAll
0x1800bd316  lea     rdx, [rsp+2F0h+Handles]; lpHandles
0x1800bd31b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800bd31f  lea     ecx, [r8+2]; nCount
0x1800bd323  call    cs:__imp_WaitForMultipleObjects
0x1800bd329  mov     rcx, r15; hMutex
0x1800bd32c  mov     r13d, eax
0x1800bd32f  call    cs:__imp_ReleaseMutex
0x1800bd335  mov     rcx, r15; hObject
0x1800bd338  call    cs:__imp_CloseHandle
0x1800bd33e  lea     ecx, [r13-80h]
0x1800bd342  test    ecx, ecx
0x1800bd344  jz      short loc_1800BD34B
0x1800bd346  test    r13d, r13d
0x1800bd349  jnz     short loc_1800BD352
0x1800bd34b  mov     sil, bl
0x1800bd34e  mov     [rsp+2F0h+var_2B0], bl
0x1800bd352  xor     r13d, r13d
0x1800bd355  test    sil, sil
0x1800bd358  jnz     short loc_1800BD387
0x1800bd35a  call    ?StartCtfmonProcess@CCtfmonHelper@@SA_NXZ; CCtfmonHelper::StartCtfmonProcess(void)
0x1800bd35f  mov     rcx, cs:hHandle; hHandle
0x1800bd366  mov     edx, 1388h; dwMilliseconds
0x1800bd36b  call    cs:__imp_WaitForSingleObject
0x1800bd371  mov     ecx, 102h
0x1800bd376  cmp     eax, ecx
0x1800bd378  setnz   sil
0x1800bd37c  mov     [rsp+2F0h+var_2B0], sil
0x1800bd381  jz      loc_1800BD203
0x1800bd387  cmp     qword ptr [rsp+2F0h+var_298], r13
0x1800bd38c  jnz     short loc_1800BD397
0x1800bd38e  test    rdi, rdi
0x1800bd391  jz      loc_1800BD44B
0x1800bd397  mov     qword ptr [rsp+2F0h+Frequency], r13
0x1800bd39c  cmp     qword ptr [rsp+2F0h+PerformanceCount], r13
0x1800bd3a1  jz      short loc_1800BD3AE
0x1800bd3a3  lea     rcx, [rsp+2F0h+PerformanceCount]; lpPerformanceCount
0x1800bd3a8  call    cs:__imp_QueryPerformanceCounter
0x1800bd3ae  lea     rcx, [rsp+2F0h+Frequency]; lpFrequency
0x1800bd3b3  call    cs:__imp_QueryPerformanceFrequency
0x1800bd3b9  test    eax, eax
0x1800bd3bb  jnz     short loc_1800BD3DB
0x1800bd3bd  mov     qword ptr [rsp+2F0h+Frequency], rbx
0x1800bd3c2  jmp     short loc_1800BD3E0
0x1800bd3c4  cmp     qword ptr [rsp+2F0h+var_298], r13
0x1800bd3c9  jnz     short loc_1800BD355
0x1800bd3cb  lea     rcx, [rsp+2F0h+var_298]; lpPerformanceCount
0x1800bd3d0  call    cs:__imp_QueryPerformanceCounter
0x1800bd3d6  jmp     loc_1800BD355
0x1800bd3db  mov     rbx, qword ptr [rsp+2F0h+Frequency]
0x1800bd3e0  mov     rax, qword ptr [rsp+2F0h+PerformanceCount]
0x1800bd3e5  lea     r9, [rsp+2F0h+PerformanceCount+4]
0x1800bd3ea  sub     rax, qword ptr [rsp+2F0h+var_298]
0x1800bd3ef  lea     r8, [rsp+2F0h+var_2AF]
0x1800bd3f4  imul    rax, 0F4240h
0x1800bd3fb  lea     rcx, [rsp+2F0h+var_288]
0x1800bd400  cqo
0x1800bd402  idiv    rbx
0x1800bd405  mov     qword ptr [rsp+2F0h+PerformanceCount], rax
0x1800bd40a  mov     rax, [rsp+2F0h+var_2A0]
0x1800bd40f  sub     rax, rdi
0x1800bd412  imul    rax, 0F4240h
0x1800bd419  cqo
0x1800bd41b  idiv    rbx
0x1800bd41e  lea     rdx, [rsp+2F0h+var_2B0]
0x1800bd423  mov     [rsp+2F0h+var_2A0], rax
0x1800bd428  lea     rax, [rsp+2F0h+var_2A0]
0x1800bd42d  mov     [rsp+2F0h+var_2C0], rax
0x1800bd432  lea     rax, [rsp+2F0h+var_2A0+4]
0x1800bd437  mov     [rsp+2F0h+var_2C8], rax
0x1800bd43c  lea     rax, [rsp+2F0h+PerformanceCount]
0x1800bd441  mov     [rsp+2F0h+var_2D0], rax
0x1800bd446  call    ??$CiceroServerRestart@AEAJAEA_NAEA_NAEAJAEAKAEAJAEAK@CtfTraceLoggingTelemetry@@SAXAEAJAEA_N10AEAK02@Z; CtfTraceLoggingTelemetry::CiceroServerRestart<long &,bool &,bool &,long &,ulong &,long &,ulong &>(long &,bool &,bool &,long &,ulong &,long &,ulong &)
0x1800bd44b  test    r12d, r12d
0x1800bd44e  mov     ecx, r13d
0x1800bd451  sets    cl; dwExitCode
0x1800bd454  call    cs:__imp_ExitThread
```
