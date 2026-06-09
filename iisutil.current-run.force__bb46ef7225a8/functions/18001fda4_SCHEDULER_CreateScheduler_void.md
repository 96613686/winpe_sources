# SCHEDULER::CreateScheduler(void)

- ea: `0x18001fda4`
- end: `0x18001fe4c`
- name: `?CreateScheduler@SCHEDULER@@SAPEAV1@XZ`
- size: `168`
- prototype: `struct SCHEDULER *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800200e0`

## callees

- `0x1800183f8`
- `0x18001fd7c`
- `0x18001fda4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001fe1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001fe1f`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueue` at `0x18001fdff`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueue` at `0x18001fdff`

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
0x18001fda4  push    rbx
0x18001fda6  sub     rsp, 20h
0x18001fdaa  mov     ecx, 30h ; '0'; Size
0x18001fdaf  mov     [rsp+28h+phModule], 0
0x18001fdb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fdbd  mov     rbx, rax
0x18001fdc0  test    rax, rax
0x18001fdc3  jz      short loc_18001FE44
0x18001fdc5  mov     dword ptr [rax], 44454353h
0x18001fdcb  mov     ecx, 1
0x18001fdd0  mov     qword ptr [rax+8], 0
0x18001fdd8  mov     qword ptr [rax+10h], 0
0x18001fde0  mov     dword ptr [rax+18h], 0
0x18001fde7  lock xadd cs:?sm_nID@SCHEDULER@@0JA, ecx; long SCHEDULER::sm_nID
0x18001fdef  inc     ecx
0x18001fdf1  mov     [rax+1Ch], ecx
0x18001fdf4  lea     rcx, [rax+20h]
0x18001fdf8  mov     [rcx+8], rcx
0x18001fdfc  mov     [rcx], rcx
0x18001fdff  call    cs:__imp_CreateTimerQueue
0x18001fe05  mov     [rbx+8], rax
0x18001fe09  test    rax, rax
0x18001fe0c  jz      short loc_18001FE3C
0x18001fe0e  lea     r8, [rsp+28h+phModule]; phModule
0x18001fe13  mov     ecx, 4; dwFlags
0x18001fe18  lea     rdx, ?TimerCallback@TIMER@@SAXPEAXE@Z; lpModuleName
0x18001fe1f  call    cs:__imp_GetModuleHandleExW
0x18001fe25  test    eax, eax
0x18001fe27  jz      short loc_18001FE3C
0x18001fe29  mov     rax, [rsp+28h+phModule]
0x18001fe2e  test    rax, rax
0x18001fe31  jz      short loc_18001FE3C
0x18001fe33  mov     [rbx+10h], rax
0x18001fe37  mov     rax, rbx
0x18001fe3a  jmp     short loc_18001FE46
0x18001fe3c  mov     rcx, rbx; this
0x18001fe3f  call    ??_GSCHEDULER@@AEAAPEAXI@Z; SCHEDULER::`scalar deleting destructor'(uint)
0x18001fe44  xor     eax, eax
0x18001fe46  add     rsp, 20h
0x18001fe4a  pop     rbx
0x18001fe4b  retn
```
