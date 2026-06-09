# SCHEDULER::CreateScheduler(void)

- ea: `0x1800210f8`
- end: `0x1800211b1`
- name: `?CreateScheduler@SCHEDULER@@SAPEAV1@XZ`
- size: `185`
- prototype: `struct SCHEDULER *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021470`

## callees

- `0x180019230`
- `0x1800210d0`
- `0x1800210f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002117d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002117d`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueue` at `0x180021157`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueue` at `0x180021157`

## pseudocode

```c
struct SCHEDULER *SCHEDULER::CreateScheduler(void)
{
  SCHEDULER *v0; // rax
  SCHEDULER *v1; // rbx
  HANDLE TimerQueue; // rax
  unsigned int v3; // edx
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  phModule = 0;
  v0 = (SCHEDULER *)operator new(0x30u);
  v1 = v0;
  if ( v0 )
  {
    *(_DWORD *)v0 = 1145389907;
    *((_QWORD *)v0 + 1) = 0;
    *((_QWORD *)v0 + 2) = 0;
    *((_DWORD *)v0 + 6) = 0;
    *((_DWORD *)v0 + 7) = _InterlockedIncrement(&SCHEDULER::sm_nID);
    *((_QWORD *)v0 + 5) = (char *)v0 + 32;
    *((_QWORD *)v0 + 4) = (char *)v0 + 32;
    TimerQueue = CreateTimerQueue();
    *((_QWORD *)v1 + 1) = TimerQueue;
    if ( TimerQueue && GetModuleHandleExW(4u, (LPCWSTR)TIMER::TimerCallback, &phModule) && phModule )
    {
      *((_QWORD *)v1 + 2) = phModule;
      return v1;
    }
    SCHEDULER::`scalar deleting destructor'(v1, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800210f8  push    rbx
0x1800210fa  sub     rsp, 20h
0x1800210fe  mov     ecx, 30h ; '0'; Size
0x180021103  mov     [rsp+28h+phModule], 0
0x18002110c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021111  mov     rbx, rax
0x180021114  test    rax, rax
0x180021117  jz      loc_1800211A8
0x18002111d  mov     dword ptr [rax], 44454353h
0x180021123  mov     ecx, 1
0x180021128  mov     qword ptr [rax+8], 0
0x180021130  mov     qword ptr [rax+10h], 0
0x180021138  mov     dword ptr [rax+18h], 0
0x18002113f  lock xadd cs:?sm_nID@SCHEDULER@@0JA, ecx; long SCHEDULER::sm_nID
0x180021147  inc     ecx
0x180021149  mov     [rax+1Ch], ecx
0x18002114c  lea     rcx, [rax+20h]
0x180021150  mov     [rcx+8], rcx
0x180021154  mov     [rcx], rcx
0x180021157  call    cs:__imp_CreateTimerQueue
0x18002115e  nop     dword ptr [rax+rax+00h]
0x180021163  mov     [rbx+8], rax
0x180021167  test    rax, rax
0x18002116a  jz      short loc_1800211A0
0x18002116c  lea     r8, [rsp+28h+phModule]; phModule
0x180021171  mov     ecx, 4; dwFlags
0x180021176  lea     rdx, ?TimerCallback@TIMER@@SAXPEAXE@Z; lpModuleName
0x18002117d  call    cs:__imp_GetModuleHandleExW
0x180021184  nop     dword ptr [rax+rax+00h]
0x180021189  test    eax, eax
0x18002118b  jz      short loc_1800211A0
0x18002118d  mov     rax, [rsp+28h+phModule]
0x180021192  test    rax, rax
0x180021195  jz      short loc_1800211A0
0x180021197  mov     [rbx+10h], rax
0x18002119b  mov     rax, rbx
0x18002119e  jmp     short loc_1800211AA
0x1800211a0  mov     rcx, rbx; this
0x1800211a3  call    ??_GSCHEDULER@@AEAAPEAXI@Z; SCHEDULER::`scalar deleting destructor'(uint)
0x1800211a8  xor     eax, eax
0x1800211aa  add     rsp, 20h
0x1800211ae  pop     rbx
0x1800211af  retn
```
