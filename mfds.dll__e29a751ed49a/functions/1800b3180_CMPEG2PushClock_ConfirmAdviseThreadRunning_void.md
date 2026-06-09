# CMPEG2PushClock::ConfirmAdviseThreadRunning_(void)

- ea: `0x1800b3180`
- end: `0x1800b326c`
- name: `?ConfirmAdviseThreadRunning_@CMPEG2PushClock@@AEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(CMPEG2PushClock *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b29b0`
- `0x1800b2e94`

## callees

- `0x1800b3180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b321b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b321b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b3203`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b3203`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b3257`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b3257`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x1800b31d7`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x1800b31d7`
- `api-ms-win-mm-time-l1-1-0!timeGetDevCaps` at `0x1800b31b2`
- `api-ms-win-mm-time-l1-1-0!timeGetDevCaps` at `0x1800b31b2`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x1800b3231`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x1800b3231`

## pseudocode

```c
__int64 __fastcall CMPEG2PushClock::ConfirmAdviseThreadRunning_(CMPEG2PushClock *this)
{
  bool v1; // zf
  MMRESULT DevCaps; // eax
  UINT wPeriodMin; // ecx
  HANDLE v5; // rax
  DWORD LastError; // eax
  UINT v7; // ecx
  __int64 result; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  timecaps_tag ptc; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 37) == 0;
  ThreadId = 0;
  ptc = 0;
  if ( !v1 )
    return 0;
  DevCaps = timeGetDevCaps(&ptc, 8u);
  wPeriodMin = 10;
  if ( !DevCaps && ptc.wPeriodMin >= 0xA )
    wPeriodMin = ptc.wPeriodMin;
  *((_DWORD *)this + 114) = wPeriodMin;
  timeBeginPeriod(wPeriodMin);
  v5 = CreateThread(0, 0, CMPEG2PushClock::ThreadEntry, this, 0, &ThreadId);
  *((_QWORD *)this + 37) = v5;
  if ( v5 )
  {
    SetThreadPriority(v5, 15);
    return 0;
  }
  LastError = GetLastError();
  v7 = *((_DWORD *)this + 114);
  ThreadId = LastError;
  timeEndPeriod(v7);
  result = ThreadId;
  if ( (int)ThreadId > 0 )
    return (unsigned __int16)ThreadId | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800b3180  push    rbx
0x1800b3182  sub     rsp, 30h
0x1800b3186  cmp     qword ptr [rcx+128h], 0
0x1800b318e  mov     rbx, rcx
0x1800b3191  mov     [rsp+38h+ThreadId], 0
0x1800b3199  mov     qword ptr [rsp+38h+ptc.wPeriodMin], 0
0x1800b31a2  jnz     loc_1800B3263
0x1800b31a8  mov     edx, 8; cbtc
0x1800b31ad  lea     rcx, [rsp+38h+ptc]; ptc
0x1800b31b2  call    cs:__imp_timeGetDevCaps
0x1800b31b9  nop     dword ptr [rax+rax+00h]
0x1800b31be  mov     ecx, 0Ah
0x1800b31c3  test    eax, eax
0x1800b31c5  jnz     short loc_1800B31D1
0x1800b31c7  cmp     [rsp+38h+ptc.wPeriodMin], ecx
0x1800b31cb  jb      short loc_1800B31D1
0x1800b31cd  mov     ecx, [rsp+38h+ptc.wPeriodMin]; uPeriod
0x1800b31d1  mov     [rbx+1C8h], ecx
0x1800b31d7  call    cs:__imp_timeBeginPeriod
0x1800b31de  nop     dword ptr [rax+rax+00h]
0x1800b31e3  lea     rax, [rsp+38h+ThreadId]
0x1800b31e8  mov     r9, rbx; lpParameter
0x1800b31eb  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800b31f0  lea     r8, ?ThreadEntry@CMPEG2PushClock@@SAKPEAX@Z; lpStartAddress
0x1800b31f7  xor     edx, edx; dwStackSize
0x1800b31f9  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800b3201  xor     ecx, ecx; lpThreadAttributes
0x1800b3203  call    cs:__imp_CreateThread
0x1800b320a  nop     dword ptr [rax+rax+00h]
0x1800b320f  mov     [rbx+128h], rax
0x1800b3216  test    rax, rax
0x1800b3219  jnz     short loc_1800B324F
0x1800b321b  call    cs:__imp_GetLastError
0x1800b3222  nop     dword ptr [rax+rax+00h]
0x1800b3227  mov     ecx, [rbx+1C8h]; uPeriod
0x1800b322d  mov     [rsp+38h+ThreadId], eax
0x1800b3231  call    cs:__imp_timeEndPeriod
0x1800b3238  nop     dword ptr [rax+rax+00h]
0x1800b323d  mov     eax, [rsp+38h+ThreadId]
0x1800b3241  test    eax, eax
0x1800b3243  jle     short loc_1800B3265
0x1800b3245  movzx   eax, ax
0x1800b3248  or      eax, 80070000h
0x1800b324d  jmp     short loc_1800B3265
0x1800b324f  mov     edx, 0Fh; nPriority
0x1800b3254  mov     rcx, rax; hThread
0x1800b3257  call    cs:__imp_SetThreadPriority
0x1800b325e  nop     dword ptr [rax+rax+00h]
0x1800b3263  xor     eax, eax
0x1800b3265  add     rsp, 30h
0x1800b3269  pop     rbx
0x1800b326a  retn
```
