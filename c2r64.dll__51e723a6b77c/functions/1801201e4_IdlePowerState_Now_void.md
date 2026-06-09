# IdlePowerState::Now(void)

- ea: `0x1801201e4`
- end: `0x180120333`
- name: `?Now@IdlePowerState@@SA?AU1@XZ`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180121008`

## callees

- `0x1800264b4`
- `0x180028310`
- `0x18003aa1c`
- `0x1801201e4`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180120240`
- `KERNEL32!GetCurrentProcess` at `0x180120293`
- `KERNEL32!GetCurrentProcess` at `0x180120240`
- `KERNEL32!GetCurrentProcess` at `0x180120293`
- `KERNEL32!GetTickCount64` at `0x1801202e1`
- `KERNEL32!GetTickCount64` at `0x1801202e1`
- `KERNEL32!GetProcessTimes` at `0x18012025e`
- `KERNEL32!GetProcessTimes` at `0x18012025e`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1801202b6`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1801202b6`
- `KERNEL32!QueryProcessCycleTime` at `0x1801202a0`
- `KERNEL32!QueryProcessCycleTime` at `0x1801202a0`
- `KERNEL32!OpenThread` at `0x1801202fd`
- `KERNEL32!OpenThread` at `0x1801202fd`
- `KERNEL32!QueryThreadCycleTime` at `0x180120318`
- `KERNEL32!QueryThreadCycleTime` at `0x180120318`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall IdlePowerState::Now(_QWORD *a1)
{
  HANDLE CurrentProcess; // rax
  HANDLE v3; // rax
  ULONGLONG TickCount64; // rax
  char *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  struct _FILETIME CreationTime; // [rsp+30h] [rbp-18h] BYREF
  struct _FILETIME KernelTime; // [rsp+70h] [rbp+28h] BYREF
  struct _FILETIME UserTime; // [rsp+78h] [rbp+30h] BYREF
  ULONGLONG UnbiasedTime; // [rsp+80h] [rbp+38h] BYREF
  struct _FILETIME ExitTime; // [rsp+88h] [rbp+40h] BYREF

  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0x8000000000000000uLL;
  a1[3] = 0;
  a1[4] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
  {
    a1[1] = *(_QWORD *)((__int64 (__fastcall *)(_QWORD, _QWORD))Mso::Chrono::filetime_clock::from_FILETIME)(
                         &UnbiasedTime,
                         KernelTime);
    *a1 = *(_QWORD *)((__int64 (__fastcall *)(_QWORD, _QWORD))Mso::Chrono::filetime_clock::from_FILETIME)(
                       &UnbiasedTime,
                       UserTime);
    v3 = GetCurrentProcess();
    if ( QueryProcessCycleTime(v3, a1 + 3) )
    {
      UnbiasedTime = 0;
      if ( QueryUnbiasedInterruptTime(&UnbiasedTime) )
      {
        TickCount64 = UnbiasedTime / 0x2710;
      }
      else
      {
        MsoShipAssertTagProc(4014811);
        TickCount64 = GetTickCount64();
      }
      a1[2] = TickCount64;
      if ( Mso::Threadpool::details::vdwTidMain )
      {
        v5 = (char *)OpenThread(0x40u, 0, Mso::Threadpool::details::vdwTidMain);
        UnbiasedTime = (ULONGLONG)v5;
        if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          QueryThreadCycleTime(v5, a1 + 4);
        std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(
          &UnbiasedTime,
          v6,
          v7);
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1801201e4  push    rbp
0x1801201e6  push    rbx
0x1801201e7  push    rsi
0x1801201e8  push    rdi
0x1801201e9  mov     rbp, rsp
0x1801201ec  sub     rsp, 48h
0x1801201f0  mov     rbx, rcx
0x1801201f3  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x1801201fb  mov     qword ptr [rbp+ExitTime.dwLowDateTime], 0
0x180120203  mov     qword ptr [rbp+KernelTime.dwLowDateTime], 0
0x18012020b  mov     qword ptr [rbp+UserTime.dwLowDateTime], 0
0x180120213  mov     qword ptr [rcx], 0
0x18012021a  mov     qword ptr [rcx+8], 0
0x180120222  mov     rax, 8000000000000000h
0x18012022c  mov     [rcx+10h], rax
0x180120230  mov     qword ptr [rcx+18h], 0
0x180120238  mov     qword ptr [rcx+20h], 0
0x180120240  call    cs:__imp_GetCurrentProcess
0x180120246  mov     rcx, rax; hProcess
0x180120249  lea     rax, [rbp+UserTime]
0x18012024d  mov     [rsp+48h+lpUserTime], rax; lpUserTime
0x180120252  lea     r9, [rbp+KernelTime]; lpKernelTime
0x180120256  lea     r8, [rbp+ExitTime]; lpExitTime
0x18012025a  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x18012025e  call    cs:__imp_GetProcessTimes
0x180120264  test    eax, eax
0x180120266  jz      loc_180120327
0x18012026c  mov     rdx, qword ptr [rbp+KernelTime.dwLowDateTime]
0x180120270  lea     rcx, [rbp+UnbiasedTime]
0x180120274  call    ?from_FILETIME@filetime_clock@Chrono@Mso@@SA?AV?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@U_FILETIME@@@Z; Mso::Chrono::filetime_clock::from_FILETIME(_FILETIME)
0x180120279  mov     rcx, [rax]
0x18012027c  mov     [rbx+8], rcx
0x180120280  mov     rdx, qword ptr [rbp+UserTime.dwLowDateTime]
0x180120284  lea     rcx, [rbp+UnbiasedTime]
0x180120288  call    ?from_FILETIME@filetime_clock@Chrono@Mso@@SA?AV?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@U_FILETIME@@@Z; Mso::Chrono::filetime_clock::from_FILETIME(_FILETIME)
0x18012028d  mov     rcx, [rax]
0x180120290  mov     [rbx], rcx
0x180120293  call    cs:__imp_GetCurrentProcess
0x180120299  mov     rcx, rax; ProcessHandle
0x18012029c  lea     rdx, [rbx+18h]; CycleTime
0x1801202a0  call    cs:__imp_QueryProcessCycleTime
0x1801202a6  test    eax, eax
0x1801202a8  jz      short loc_180120327
0x1801202aa  mov     [rbp+UnbiasedTime], 0
0x1801202b2  lea     rcx, [rbp+UnbiasedTime]; UnbiasedTime
0x1801202b6  call    cs:__imp_QueryUnbiasedInterruptTime
0x1801202bc  test    eax, eax
0x1801202be  jz      short loc_1801202D7
0x1801202c0  mov     rax, 346DC5D63886594Bh
0x1801202ca  mul     [rbp+UnbiasedTime]
0x1801202ce  mov     rax, rdx
0x1801202d1  shr     rax, 0Bh
0x1801202d5  jmp     short loc_1801202E8
0x1801202d7  mov     ecx, 3D42DBh
0x1801202dc  call    MsoShipAssertTagProc
0x1801202e1  call    cs:__imp_GetTickCount64
0x1801202e7  nop
0x1801202e8  mov     [rbx+10h], rax
0x1801202ec  mov     r8d, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; dwThreadId
0x1801202f3  test    r8d, r8d
0x1801202f6  jz      short loc_180120327
0x1801202f8  xor     edx, edx; bInheritHandle
0x1801202fa  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1801202fd  call    cs:__imp_OpenThread
0x180120303  mov     [rbp+UnbiasedTime], rax
0x180120307  lea     rcx, [rax-1]
0x18012030b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18012030f  ja      short loc_18012031E
0x180120311  lea     rdx, [rbx+20h]; CycleTime
0x180120315  mov     rcx, rax; ThreadHandle
0x180120318  call    cs:__imp_QueryThreadCycleTime
0x18012031e  lea     rcx, [rbp+UnbiasedTime]
0x180120322  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x180120327  mov     rax, rbx
0x18012032a  add     rsp, 48h
0x18012032e  pop     rdi
0x18012032f  pop     rsi
0x180120330  pop     rbx
0x180120331  pop     rbp
0x180120332  retn
```
