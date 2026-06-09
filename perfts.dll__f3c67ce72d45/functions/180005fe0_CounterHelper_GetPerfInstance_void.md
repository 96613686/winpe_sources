# CounterHelper::GetPerfInstance(void)

- ea: `0x180005fe0`
- end: `0x180006061`
- name: `?GetPerfInstance@CounterHelper@@QEAAPEAU_USER_INPUT_DELAY_INSTANCE@@XZ`
- size: `129`
- prototype: `struct _USER_INPUT_DELAY_INSTANCE *__fastcall(CounterHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006f98`

## callees

- `0x180005fe0`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180006000`
- `KERNEL32!CreateMutexW` at `0x180006000`
- `KERNEL32!WaitForSingleObject` at `0x180006013`
- `KERNEL32!WaitForSingleObject` at `0x180006013`
- `KERNEL32!ReleaseMutex` at `0x18000604c`
- `KERNEL32!ReleaseMutex` at `0x18000604c`

## pseudocode

```c
struct _USER_INPUT_DELAY_INSTANCE *__fastcall CounterHelper::GetPerfInstance(CounterHelper *this)
{
  HANDLE MutexW; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  HANDLE v5; // rcx

  MutexW = CounterHelper::LagCounterMajorEvent;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  v3 = *(_QWORD *)this;
  v4 = *((_QWORD *)this + 3);
  ++*((_DWORD *)this + 4);
  *((_QWORD *)this + 3) = v4 + v3;
  *((_DWORD *)this + 55) = *((_DWORD *)this + 4);
  *((_QWORD *)this + 28) = *((_QWORD *)this + 3);
  v5 = CounterHelper::LagCounterMajorEvent;
  *(_QWORD *)this = 0;
  ReleaseMutex(v5);
  return (CounterHelper *)((char *)this + 48);
}

```

## disassembly

```asm
0x180005fe0  mov     [rsp+arg_0], rbx
0x180005fe5  push    rdi
0x180005fe6  sub     rsp, 20h
0x180005fea  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180005ff1  mov     rdi, rcx
0x180005ff4  test    rax, rax
0x180005ff7  jnz     short loc_18000600D
0x180005ff9  xor     r8d, r8d; lpName
0x180005ffc  xor     edx, edx; bInitialOwner
0x180005ffe  xor     ecx, ecx; lpMutexAttributes
0x180006000  call    cs:__imp_CreateMutexW
0x180006006  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x18000600d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006010  mov     rcx, rax; hHandle
0x180006013  call    cs:__imp_WaitForSingleObject
0x180006019  mov     rcx, [rdi]
0x18000601c  mov     rax, [rdi+18h]
0x180006020  inc     dword ptr [rdi+10h]
0x180006023  add     rcx, rax
0x180006026  mov     [rdi+18h], rcx
0x18000602a  mov     ecx, [rdi+10h]
0x18000602d  mov     [rdi+0DCh], ecx
0x180006033  mov     rcx, [rdi+18h]
0x180006037  mov     [rdi+0E0h], rcx
0x18000603e  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; hMutex
0x180006045  mov     qword ptr [rdi], 0
0x18000604c  call    cs:__imp_ReleaseMutex
0x180006052  mov     rbx, [rsp+28h+arg_0]
0x180006057  lea     rax, [rdi+30h]
0x18000605b  add     rsp, 20h
0x18000605f  pop     rdi
0x180006060  retn
```
