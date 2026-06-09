# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x180004338`
- end: `0x1800043dc`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004460`

## callees

- `0x180001c60`
- `0x180002580`
- `0x180003280`
- `0x180004338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000434e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000434e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000436d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000439e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000436d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000439e`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  CallStackContext *v2; // rdi
  DWORD v3; // eax
  DWORD CurrentThreadId; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v2 = *(CallStackContext **)(a1 + 56);
  if ( v2 )
  {
    *(_QWORD *)(a1 + 56) = *((_QWORD *)v2 + 254);
    *((_QWORD *)v2 + 254) = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    CallStackContext::Init(v2, CurrentThreadId, 0x7Cu);
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v2 = (CallStackContext *)operator new(0x7F8u);
    v3 = GetCurrentThreadId();
    CallStackContext::CallStackContext(v2, v3, 0x7Cu);
  }
  *((_QWORD *)v2 + 254) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  return v2;
}

```

## disassembly

```asm
0x180004338  mov     [rsp+arg_0], rbx
0x18000433d  mov     [rsp+arg_8], rsi
0x180004342  push    rdi
0x180004343  sub     rsp, 20h
0x180004347  mov     rbx, rcx
0x18000434a  add     rcx, 10h; lpCriticalSection
0x18000434e  call    cs:__imp_EnterCriticalSection
0x180004354  mov     rdi, [rbx+38h]
0x180004358  test    rdi, rdi
0x18000435b  jnz     short loc_180004385
0x18000435d  inc     dword ptr [rbx+44h]
0x180004360  mov     ecx, 7F8h; Size
0x180004365  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000436a  mov     rdi, rax
0x18000436d  call    cs:__imp_GetCurrentThreadId
0x180004373  mov     r8d, 7Ch ; '|'; unsigned int
0x180004379  mov     rcx, rdi; this
0x18000437c  mov     edx, eax; unsigned int
0x18000437e  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180004383  jmp     short loc_1800043B4
0x180004385  mov     rax, [rdi+7F0h]
0x18000438c  mov     [rbx+38h], rax
0x180004390  mov     qword ptr [rdi+7F0h], 0
0x18000439b  dec     dword ptr [rbx+40h]
0x18000439e  call    cs:__imp_GetCurrentThreadId
0x1800043a4  mov     r8d, 7Ch ; '|'; unsigned int
0x1800043aa  mov     rcx, rdi; this
0x1800043ad  mov     edx, eax; unsigned int
0x1800043af  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x1800043b4  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800043b8  mov     qword ptr [rdi+7F0h], 0
0x1800043c3  call    cs:__imp_LeaveCriticalSection
0x1800043c9  mov     rbx, [rsp+28h+arg_0]
0x1800043ce  mov     rax, rdi
0x1800043d1  mov     rsi, [rsp+28h+arg_8]
0x1800043d6  add     rsp, 20h
0x1800043da  pop     rdi
0x1800043db  retn
```
