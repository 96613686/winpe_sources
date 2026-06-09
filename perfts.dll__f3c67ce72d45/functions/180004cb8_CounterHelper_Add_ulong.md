# CounterHelper::Add(ulong)

- ea: `0x180004cb8`
- end: `0x180004d54`
- name: `?Add@CounterHelper@@QEAAXK@Z`
- size: `156`
- prototype: `void __fastcall(CounterHelper *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cb8`
- `0x180007b10`

## callees

- `0x180004cb8`
- `0x180006214`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180004cda`
- `KERNEL32!CreateMutexW` at `0x180004cda`
- `KERNEL32!WaitForSingleObject` at `0x180004ced`
- `KERNEL32!WaitForSingleObject` at `0x180004ced`
- `KERNEL32!ReleaseMutex` at `0x180004d4d`

## pseudocode

```c
void __fastcall CounterHelper::Add(CounterHelper *this, unsigned int a2)
{
  HANDLE MutexW; // rax
  unsigned __int64 v4; // rdi
  int v5; // eax
  struct CounterHelper *SessionCounterHelper; // rax
  CounterHelper *v7; // rcx

  MutexW = CounterHelper::LagCounterMajorEvent;
  v4 = a2;
  if ( !CounterHelper::LagCounterMajorEvent )
  {
    MutexW = CreateMutexW(0, 0, 0);
    CounterHelper::LagCounterMajorEvent = MutexW;
  }
  WaitForSingleObject(MutexW, 0xFFFFFFFF);
  if ( *(_QWORD *)this < v4 )
    *(_QWORD *)this = v4;
  *((_QWORD *)this + 5) += v4;
  ++*((_DWORD *)this + 8);
  v5 = *((_DWORD *)this + 104);
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      v7 = CounterHelper::MachineCounter;
      if ( CounterHelper::MachineCounter )
        goto LABEL_10;
    }
  }
  else
  {
    SessionCounterHelper = CounterHelper::GetSessionCounterHelper(this, this);
    if ( SessionCounterHelper )
    {
      v7 = SessionCounterHelper;
LABEL_10:
      CounterHelper::Add(v7, v4);
    }
  }
  ReleaseMutex(CounterHelper::LagCounterMajorEvent);
}

```

## disassembly

```asm
0x180004cb8  mov     [rsp+arg_0], rbx
0x180004cbd  push    rdi
0x180004cbe  sub     rsp, 20h
0x180004cc2  mov     rax, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180004cc9  mov     rbx, rcx
0x180004ccc  mov     edi, edx
0x180004cce  test    rax, rax
0x180004cd1  jnz     short loc_180004CE7
0x180004cd3  xor     r8d, r8d; lpName
0x180004cd6  xor     edx, edx; bInitialOwner
0x180004cd8  xor     ecx, ecx; lpMutexAttributes
0x180004cda  call    cs:__imp_CreateMutexW
0x180004ce0  mov     cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA, rax; void * CounterHelper::LagCounterMajorEvent
0x180004ce7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004cea  mov     rcx, rax; hHandle
0x180004ced  call    cs:__imp_WaitForSingleObject
0x180004cf3  mov     rax, [rbx]
0x180004cf6  cmp     rax, rdi
0x180004cf9  jnb     short loc_180004CFE
0x180004cfb  mov     [rbx], rdi
0x180004cfe  add     [rbx+28h], rdi
0x180004d02  inc     dword ptr [rbx+20h]
0x180004d05  mov     eax, [rbx+1A0h]
0x180004d0b  test    eax, eax
0x180004d0d  jnz     short loc_180004D24
0x180004d0f  mov     rdx, rbx; struct CounterHelper *
0x180004d12  mov     rcx, rbx; this
0x180004d15  call    ?GetSessionCounterHelper@CounterHelper@@QEAAPEAV1@PEAV1@@Z; CounterHelper::GetSessionCounterHelper(CounterHelper *)
0x180004d1a  test    rax, rax
0x180004d1d  jz      short loc_180004D3C
0x180004d1f  mov     rcx, rax
0x180004d22  jmp     short loc_180004D35
0x180004d24  cmp     eax, 1
0x180004d27  jnz     short loc_180004D3C
0x180004d29  mov     rcx, cs:?MachineCounter@CounterHelper@@2PEAV1@EA; this
0x180004d30  test    rcx, rcx
0x180004d33  jz      short loc_180004D3C
0x180004d35  mov     edx, edi; unsigned int
0x180004d37  call    ?Add@CounterHelper@@QEAAXK@Z; CounterHelper::Add(ulong)
0x180004d3c  mov     rcx, cs:?LagCounterMajorEvent@CounterHelper@@2PEAXEA; void * CounterHelper::LagCounterMajorEvent
0x180004d43  mov     rbx, [rsp+28h+arg_0]
0x180004d48  add     rsp, 20h
0x180004d4c  pop     rdi
0x180004d4d  jmp     cs:__imp_ReleaseMutex
```
