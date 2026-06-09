# Memory::RecyclerParallelThread::StartConcurrent(void)

- ea: `0x1801f0604`
- end: `0x1801f0693`
- name: `?StartConcurrent@RecyclerParallelThread@Memory@@QEAA_NXZ`
- size: `143`
- prototype: `bool __fastcall(Memory::RecyclerParallelThread *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801efdd0`
- `0x1801eff84`

## callees

- `0x180167544`
- `0x1801f0604`
- `0x1801f22a4`
- `0x18048ac1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801f067e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801f067e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f0635`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f0635`

## pseudocode

```c
bool __fastcall Memory::RecyclerParallelThread::StartConcurrent(Memory::RecyclerParallelThread *this)
{
  __int64 v2; // rdx
  HANDLE EventW; // rax

  if ( JsUtil::ThreadService::HasCallback(*(JsUtil::ThreadService **)(*((_QWORD *)this + 3) + 48LL)) )
  {
    if ( v2 || (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 5) = EventW) != 0) )
      LOBYTE(EventW) = JsUtil::ThreadService::Invoke(
                         *(JsUtil::ThreadService **)(*((_QWORD *)this + 3) + 48LL),
                         (void (*)(void *))Memory::RecyclerParallelThread::StaticBackgroundWorkCallback,
                         this);
  }
  else if ( v2 )
  {
    SetEvent(*((HANDLE *)this + 4));
    LOBYTE(EventW) = 1;
  }
  else
  {
    LOBYTE(EventW) = Memory::RecyclerParallelThread::EnableConcurrent(this, 0);
  }
  return (char)EventW;
}

```

## disassembly

```asm
0x1801f0604  mov     [rsp+arg_0], rcx
0x1801f0609  push    rbx
0x1801f060a  sub     rsp, 20h
0x1801f060e  mov     rbx, [rsp+28h+arg_0]
0x1801f0613  mov     rcx, [rbx+18h]
0x1801f0617  mov     rdx, [rbx+28h]
0x1801f061b  mov     rcx, [rcx+30h]; this
0x1801f061f  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x1801f0624  test    al, al
0x1801f0626  jz      short loc_1801F0668
0x1801f0628  test    rdx, rdx
0x1801f062b  jnz     short loc_1801F064A
0x1801f062d  xor     r9d, r9d; lpName
0x1801f0630  xor     r8d, r8d; bInitialState
0x1801f0633  xor     ecx, ecx; lpEventAttributes
0x1801f0635  call    cs:__imp_CreateEventW
0x1801f063c  nop     dword ptr [rax+rax+00h]
0x1801f0641  mov     [rbx+28h], rax
0x1801f0645  test    rax, rax
0x1801f0648  jz      short loc_1801F068C
0x1801f064a  mov     rcx, [rbx+18h]
0x1801f064e  lea     rdx, ?StaticBackgroundWorkCallback@RecyclerParallelThread@Memory@@CAXPEAX@Z; void (*)(void *)
0x1801f0655  mov     r8, rbx; void *
0x1801f0658  mov     rcx, [rcx+30h]; this
0x1801f065c  call    ?Invoke@ThreadService@JsUtil@@QEAA_NP6AXPEAX@Z0@Z; JsUtil::ThreadService::Invoke(void (*)(void *),void *)
0x1801f0661  test    al, al
0x1801f0663  setnz   al
0x1801f0666  jmp     short loc_1801F068C
0x1801f0668  test    rdx, rdx
0x1801f066b  jnz     short loc_1801F067A
0x1801f066d  mov     rcx, rbx; this
0x1801f0670  add     rsp, 20h
0x1801f0674  pop     rbx
0x1801f0675  jmp     ?EnableConcurrent@RecyclerParallelThread@Memory@@QEAA_N_N@Z; Memory::RecyclerParallelThread::EnableConcurrent(bool)
0x1801f067a  mov     rcx, [rbx+20h]; hEvent
0x1801f067e  call    cs:__imp_SetEvent
0x1801f0685  nop     dword ptr [rax+rax+00h]
0x1801f068a  mov     al, 1
0x1801f068c  add     rsp, 20h
0x1801f0690  pop     rbx
0x1801f0691  retn
```
