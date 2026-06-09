# ESIMPM::CoreFSM::Initialize(void)

- ea: `0x140024220`
- end: `0x14002444e`
- name: `?Initialize@CoreFSM@ESIMPM@@QEAAKXZ`
- size: `558`
- prototype: `unsigned int __fastcall(ESIMPM::CoreFSM *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140024d88`

## callees

- `0x140002f84`
- `0x140003244`
- `0x140014f64`
- `0x140020620`
- `0x1400238d8`
- `0x140024220`
- `0x140029bb0`
- `0x14002a14c`
- `0x1400350e4`
- `0x1400352b4`
- `0x140035420`
- `0x14003574c`

## string_xrefs

- `0x1400243a6`: `WwanCreateRwLock Failed [%d]`
- `0x1400243b0`: `ESIMPM::TimerWrapper::CreateTimer`
- `0x14002440c`: `ESIMPM::TimerWrapper::CreateTimer`
- `0x140024430`: `ESIMPM::TimerWrapper::CreateTimer`
- `0x140024426`: ` Timer Creation Completed.`
- `0x1400243e2`: `could not create timer [errCode: %d]`
- `0x1400243eb`: `ESIMPM::WwanTimerCreateTimer`
- `0x1400242a4`: `WaitSlotSwitchComplete`
- `0x14002434c`: `WaitSIMReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::CoreFSM::Initialize(ESIMPM::CoreFSM *this)
{
  _QWORD *v2; // rax
  void *v3; // rsi
  char *v4; // rsi
  wchar_t *v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int Timer; // eax
  _QWORD *v10; // [rsp+40h] [rbp+8h]

  v10 = operator new(0x10u);
  *v10 = 0;
  v10[1] = 0;
  v2 = operator new(0x30u);
  *v2 = v2;
  v2[1] = v2;
  *v10 = v2;
  v3 = (void *)*((_QWORD *)this + 39);
  *((_QWORD *)this + 39) = v10;
  if ( v3 )
  {
    std::list<std::wstring>::~list<std::wstring>(v3);
    operator delete(v3);
  }
  *((_DWORD *)this + 34) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitSlotMappingQuery");
  *((_DWORD *)this + 35) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitSlotSwitchComplete");
  *((_DWORD *)this + 36) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitScanResult");
  *((_DWORD *)this + 37) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitRegistered");
  *((_DWORD *)this + 38) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitConnected");
  *((_DWORD *)this + 39) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitReconnectedAfterSleep");
  *((_DWORD *)this + 40) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitSlotMappingQuery");
  *((_DWORD *)this + 41) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitESIMProfileList");
  *((_DWORD *)this + 42) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitESIMProfileEnabled");
  *((_DWORD *)this + 43) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitSIMReady");
  *((_DWORD *)this + 44) = ESIMPM::CoreFSM::ReadOneTimerIntervalReg(this, L"WaitEFQueryResult");
  ESIMPM::CoreFSM::SaveStartConnectionTimeAndTrigger(this, 4);
  v4 = (char *)this + 16;
  v5 = (wchar_t *)((char *)this + 184);
  *((_DWORD *)v4 + 28) = 0;
  v6 = CreateReadWriteLock((__int64)v4);
  v7 = v6;
  if ( v6 )
  {
    ESIMPM::Log::Error("ESIMPM::TimerWrapper::CreateTimer", v5, L"WwanCreateRwLock Failed [%d]", v6);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    Timer = CreateTimer(v4 + 104, g_hTimerContext, v4, v5);
    v7 = Timer;
    if ( Timer )
    {
      ESIMPM::Log::Error("ESIMPM::WwanTimerCreateTimer", 0, L"could not create timer [errCode: %d]", Timer);
      DeleteReadWriteLock(v4);
      ESIMPM::Log::Error("ESIMPM::TimerWrapper::CreateTimer", v5, L"Timer Creation Failed [%d]", v7);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      *((_DWORD *)v4 + 28) = 1;
      ESIMPM::Log::Info("ESIMPM::TimerWrapper::CreateTimer", (const struct _GUID *)v5, L" Timer Creation Completed.");
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140024220  mov     [rsp+arg_8], rbx
0x140024225  mov     [rsp+arg_10], rsi
0x14002422a  push    rdi
0x14002422b  sub     rsp, 30h
0x14002422f  mov     rdi, rcx
0x140024232  mov     ecx, 10h; Size
0x140024237  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002423c  mov     rbx, rax
0x14002423f  mov     [rsp+38h+arg_0], rax
0x140024244  mov     qword ptr [rax], 0
0x14002424b  mov     qword ptr [rax+8], 0
0x140024253  mov     ecx, 30h ; '0'; Size
0x140024258  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002425d  mov     [rax], rax
0x140024260  mov     [rax+8], rax
0x140024264  mov     [rbx], rax
0x140024267  mov     rsi, [rdi+138h]
0x14002426e  mov     [rdi+138h], rbx
0x140024275  test    rsi, rsi
0x140024278  jz      short loc_14002428F
0x14002427a  mov     rcx, rsi
0x14002427d  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x140024282  mov     edx, 10h
0x140024287  mov     rcx, rsi; Block
0x14002428a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002428f  lea     rdx, aWaitslotmappin; "WaitSlotMappingQuery"
0x140024296  mov     rcx, rdi; this
0x140024299  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x14002429e  mov     [rdi+88h], eax
0x1400242a4  lea     rdx, aWaitslotswitch; "WaitSlotSwitchComplete"
0x1400242ab  mov     rcx, rdi; this
0x1400242ae  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x1400242b3  mov     [rdi+8Ch], eax
0x1400242b9  lea     rdx, aWaitscanresult; "WaitScanResult"
0x1400242c0  mov     rcx, rdi; this
0x1400242c3  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x1400242c8  mov     [rdi+90h], eax
0x1400242ce  lea     rdx, aWaitregistered; "WaitRegistered"
0x1400242d5  mov     rcx, rdi; this
0x1400242d8  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x1400242dd  mov     [rdi+94h], eax
0x1400242e3  lea     rdx, aWaitconnected; "WaitConnected"
0x1400242ea  mov     rcx, rdi; this
0x1400242ed  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x1400242f2  mov     [rdi+98h], eax
0x1400242f8  lea     rdx, aWaitreconnecte; "WaitReconnectedAfterSleep"
0x1400242ff  mov     rcx, rdi; this
0x140024302  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x140024307  mov     [rdi+9Ch], eax
0x14002430d  lea     rdx, aWaitslotmappin; "WaitSlotMappingQuery"
0x140024314  mov     rcx, rdi; this
0x140024317  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x14002431c  mov     [rdi+0A0h], eax
0x140024322  lea     rdx, aWaitesimprofil; "WaitESIMProfileList"
0x140024329  mov     rcx, rdi; this
0x14002432c  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x140024331  mov     [rdi+0A4h], eax
0x140024337  lea     rdx, aWaitesimprofil_0; "WaitESIMProfileEnabled"
0x14002433e  mov     rcx, rdi; this
0x140024341  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x140024346  mov     [rdi+0A8h], eax
0x14002434c  lea     rdx, aWaitsimready; "WaitSIMReady"
0x140024353  mov     rcx, rdi; this
0x140024356  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x14002435b  mov     [rdi+0ACh], eax
0x140024361  lea     rdx, aWaitefqueryres; "WaitEFQueryResult"
0x140024368  mov     rcx, rdi; this
0x14002436b  call    ?ReadOneTimerIntervalReg@CoreFSM@ESIMPM@@AEAAKPEBG@Z; ESIMPM::CoreFSM::ReadOneTimerIntervalReg(ushort const *)
0x140024370  mov     [rdi+0B0h], eax
0x140024376  mov     edx, 4
0x14002437b  mov     rcx, rdi
0x14002437e  call    ?SaveStartConnectionTimeAndTrigger@CoreFSM@ESIMPM@@AEAAXW4ESIMPMCONNECTIONTRIGGER@2@@Z; ESIMPM::CoreFSM::SaveStartConnectionTimeAndTrigger(ESIMPM::ESIMPMCONNECTIONTRIGGER)
0x140024383  lea     rsi, [rdi+10h]
0x140024387  add     rdi, 0B8h
0x14002438e  mov     dword ptr [rsi+70h], 0
0x140024395  mov     rcx, rsi
0x140024398  call    CreateReadWriteLock
0x14002439d  mov     ebx, eax
0x14002439f  test    eax, eax
0x1400243a1  jz      short loc_1400243C3
0x1400243a3  mov     r9d, eax
0x1400243a6  lea     r8, aWwancreaterwlo; "WwanCreateRwLock Failed [%d]"
0x1400243ad  mov     rdx, rdi; struct _GUID *
0x1400243b0  lea     rcx, aEsimpmTimerwra_0; "ESIMPM::TimerWrapper::CreateTimer"
0x1400243b7  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400243bc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400243c1  jmp     short loc_14002443C
0x1400243c3  lea     rcx, [rsi+68h]
0x1400243c7  mov     r9, rdi
0x1400243ca  mov     r8, rsi
0x1400243cd  mov     rdx, cs:?g_hTimerContext@@3PEAXEA; void * g_hTimerContext
0x1400243d4  call    CreateTimer
0x1400243d9  mov     ebx, eax
0x1400243db  test    eax, eax
0x1400243dd  jz      short loc_14002441F
0x1400243df  mov     r9d, eax
0x1400243e2  lea     r8, aCouldNotCreate; "could not create timer [errCode: %d]"
0x1400243e9  xor     edx, edx; struct _GUID *
0x1400243eb  lea     rcx, aEsimpmWwantime_1; "ESIMPM::WwanTimerCreateTimer"
0x1400243f2  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400243f7  mov     rcx, rsi
0x1400243fa  call    DeleteReadWriteLock
0x1400243ff  mov     r9d, ebx
0x140024402  lea     r8, aTimerCreationF; "Timer Creation Failed [%d]"
0x140024409  mov     rdx, rdi; struct _GUID *
0x14002440c  lea     rcx, aEsimpmTimerwra_0; "ESIMPM::TimerWrapper::CreateTimer"
0x140024413  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140024418  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002441d  jmp     short loc_14002443C
0x14002441f  mov     dword ptr [rsi+70h], 1
0x140024426  lea     r8, aTimerCreationC; " Timer Creation Completed."
0x14002442d  mov     rdx, rdi; struct _GUID *
0x140024430  lea     rcx, aEsimpmTimerwra_0; "ESIMPM::TimerWrapper::CreateTimer"
0x140024437  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002443c  mov     eax, ebx
0x14002443e  mov     rbx, [rsp+38h+arg_8]
0x140024443  mov     rsi, [rsp+38h+arg_10]
0x140024448  add     rsp, 30h
0x14002444c  pop     rdi
0x14002444d  retn
```
