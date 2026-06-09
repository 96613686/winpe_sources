# Microsoft::Bluetooth::Foundation::StateMachineTimer::TimerCallback(void)

- ea: `0x180021b74`
- end: `0x180021d68`
- name: `?TimerCallback@StateMachineTimer@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `500`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::StateMachineTimer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ff40`

## callees

- `0x1800017a0`
- `0x180001d20`
- `0x180001d88`
- `0x18000b330`
- `0x180021b74`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021c76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021cc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021c76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021cc1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021bac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021bac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180021c61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180021c61`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021bda`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021cac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021bda`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021cac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180021d3f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180021d3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Bluetooth::Foundation::StateMachineTimer::TimerCallback(
        Microsoft::Bluetooth::Foundation::StateMachineTimer *this)
{
  RTL_SRWLOCK *v2; // rdi
  LARGE_INTEGER v3; // rsi
  LONGLONG v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  char v9; // al
  LARGE_INTEGER PerformanceCount; // [rsp+28h] [rbp-49h] BYREF
  LARGE_INTEGER Frequency; // [rsp+30h] [rbp-41h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v13[112]; // [rsp+40h] [rbp-31h] BYREF
  __int64 v14; // [rsp+B0h] [rbp+3Fh]

  v14 = 0;
  v2 = (RTL_SRWLOCK *)((char *)this + 32);
  AcquireSRWLockExclusive((PSRWLOCK)this + 4);
  pftDueTime = (struct _FILETIME)v2;
  if ( *((_BYTE *)this + 41) )
    goto LABEL_10;
  PerformanceCount.QuadPart = 0;
  if ( *((_BYTE *)this + 168) )
  {
    QueryPerformanceCounter(&PerformanceCount);
    v3 = PerformanceCount;
  }
  else
  {
    v3 = *(LARGE_INTEGER *)((char *)this + 184);
    PerformanceCount = v3;
  }
  v4 = v3.QuadPart - *((_QWORD *)this + 22);
  if ( __TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA);
    if ( __TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA == -1 )
    {
      Frequency.QuadPart = 0;
      QueryPerformanceFrequency(&Frequency);
      `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>'::`2'::ticksPerSecond = Frequency.QuadPart;
      Init_thread_footer(&__TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA);
    }
  }
  v5 = 1000
     * v4
     / `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>'::`2'::ticksPerSecond;
  v6 = *((_QWORD *)this + 24);
  if ( v5 >= v6 )
  {
LABEL_10:
    wistd::function<void (void)>::operator=(v13, (char *)this + 48);
    *((_BYTE *)this + 40) = 0;
    v9 = *((_BYTE *)this + 168);
    *((_BYTE *)this + 168) = 0;
    if ( v9 )
      QueryPerformanceCounter((LARGE_INTEGER *)this + 23);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    v8 = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
      v8 = v14;
    }
  }
  else
  {
    v7 = *((_QWORD *)this + 3);
    pftDueTime = (struct _FILETIME)(-10000 * (v6 - v5));
    SetThreadpoolTimerEx(*(PTP_TIMER *)(v7 + 80), &pftDueTime, 0, 0);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    v8 = v14;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
}

```

## disassembly

```asm
0x180021b74  mov     rax, rsp
0x180021b77  mov     [rax+10h], rbx
0x180021b7b  mov     [rax+18h], rsi
0x180021b7f  mov     [rax+20h], rdi
0x180021b83  push    rbp
0x180021b84  lea     rbp, [rax-5Fh]
0x180021b88  sub     rsp, 0C0h
0x180021b8f  mov     rax, cs:__security_cookie
0x180021b96  xor     rax, rsp
0x180021b99  mov     [rbp+57h+var_10], rax
0x180021b9d  mov     rbx, rcx
0x180021ba0  and     [rbp+57h+var_18], 0
0x180021ba5  lea     rdi, [rcx+20h]
0x180021ba9  mov     rcx, rdi; SRWLock
0x180021bac  call    cs:__imp_AcquireSRWLockExclusive
0x180021bb3  nop     dword ptr [rax+rax+00h]
0x180021bb8  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rdi
0x180021bbc  cmp     byte ptr [rbx+29h], 0
0x180021bc0  jnz     loc_180021C89
0x180021bc6  and     qword ptr [rbp+57h+PerformanceCount], 0
0x180021bcb  mov     al, [rbx+0A8h]
0x180021bd1  nop
0x180021bd2  test    al, al
0x180021bd4  jz      short loc_180021BEC
0x180021bd6  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180021bda  call    cs:__imp_QueryPerformanceCounter
0x180021be1  nop     dword ptr [rax+rax+00h]
0x180021be6  mov     rsi, qword ptr [rbp+57h+PerformanceCount]
0x180021bea  jmp     short loc_180021BF7
0x180021bec  mov     rsi, [rbx+0B8h]
0x180021bf3  mov     qword ptr [rbp+57h+PerformanceCount], rsi
0x180021bf7  sub     rsi, [rbx+0B0h]
0x180021bfe  mov     ecx, cs:_tls_index
0x180021c04  mov     rax, gs:58h
0x180021c0d  mov     edx, 4
0x180021c12  mov     rax, [rax+rcx*8]
0x180021c16  mov     ecx, [rdx+rax]
0x180021c19  cmp     cs:?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA, ecx
0x180021c1f  jg      loc_180021D1D
0x180021c25  imul    rax, rsi, 3E8h
0x180021c2c  cqo
0x180021c2e  idiv    cs:?ticksPerSecond@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4_JB; __int64 const `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>(__int64)'::`2'::ticksPerSecond
0x180021c35  mov     rdx, [rbx+0C0h]
0x180021c3c  cmp     rax, rdx
0x180021c3f  jge     short loc_180021C89
0x180021c41  sub     rdx, rax
0x180021c44  mov     rcx, [rbx+18h]
0x180021c48  imul    rax, rdx, 0FFFFFFFFFFFFD8F0h
0x180021c4f  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180021c53  xor     r9d, r9d; msWindowLength
0x180021c56  xor     r8d, r8d; msPeriod
0x180021c59  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x180021c5d  mov     rcx, [rcx+50h]; pti
0x180021c61  call    cs:__imp_SetThreadpoolTimerEx
0x180021c68  nop     dword ptr [rax+rax+00h]
0x180021c6d  nop
0x180021c6e  test    rdi, rdi
0x180021c71  jz      short loc_180021C83
0x180021c73  mov     rcx, rdi; SRWLock
0x180021c76  call    cs:__imp_ReleaseSRWLockExclusive
0x180021c7d  nop     dword ptr [rax+rax+00h]
0x180021c82  nop
0x180021c83  mov     rcx, [rbp+57h+var_18]
0x180021c87  jmp     short loc_180021CE6
0x180021c89  lea     rdx, [rbx+30h]
0x180021c8d  lea     rcx, [rbp+57h+var_88]
0x180021c91  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::function<void (void)>::operator=(wistd::function<void (void)> &&)
0x180021c96  xor     eax, eax
0x180021c98  mov     [rbx+28h], al
0x180021c9b  xchg    al, [rbx+0A8h]
0x180021ca1  test    al, al
0x180021ca3  jz      short loc_180021CB9
0x180021ca5  lea     rcx, [rbx+0B8h]; lpPerformanceCount
0x180021cac  call    cs:__imp_QueryPerformanceCounter
0x180021cb3  nop     dword ptr [rax+rax+00h]
0x180021cb8  nop
0x180021cb9  test    rdi, rdi
0x180021cbc  jz      short loc_180021CCD
0x180021cbe  mov     rcx, rdi; SRWLock
0x180021cc1  call    cs:__imp_ReleaseSRWLockExclusive
0x180021cc8  nop     dword ptr [rax+rax+00h]
0x180021ccd  mov     rcx, [rbp+57h+var_18]
0x180021cd1  test    rcx, rcx
0x180021cd4  jz      short loc_180021CE6
0x180021cd6  mov     rax, [rcx]
0x180021cd9  mov     rax, [rax+20h]
0x180021cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ce2  mov     rcx, [rbp+57h+var_18]
0x180021ce6  test    rcx, rcx
0x180021ce9  jz      short loc_180021CF7
0x180021ceb  mov     rax, [rcx]
0x180021cee  mov     rax, [rax+18h]
0x180021cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cf7  mov     rcx, [rbp+57h+var_10]
0x180021cfb  xor     rcx, rsp; StackCookie
0x180021cfe  call    __security_check_cookie
0x180021d03  lea     r11, [rsp+0C0h+var_s0]
0x180021d0b  mov     rbx, [r11+18h]
0x180021d0f  mov     rsi, [r11+20h]
0x180021d13  mov     rdi, [r11+28h]
0x180021d17  mov     rsp, r11
0x180021d1a  pop     rbp
0x180021d1b  retn
0x180021d1d  lea     rcx, ?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA
0x180021d24  call    _Init_thread_header
0x180021d29  cmp     cs:?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA, 0FFFFFFFFh
0x180021d30  jnz     loc_180021C25
0x180021d36  and     qword ptr [rbp+57h+Frequency], 0
0x180021d3b  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x180021d3f  call    cs:__imp_QueryPerformanceFrequency
0x180021d46  nop     dword ptr [rax+rax+00h]
0x180021d4b  mov     rax, qword ptr [rbp+57h+Frequency]
0x180021d4f  mov     cs:?ticksPerSecond@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4_JB, rax; __int64 const `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>(__int64)'::`2'::ticksPerSecond
0x180021d56  lea     rcx, ?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA
0x180021d5d  call    _Init_thread_footer
0x180021d62  jmp     loc_180021C25
```
