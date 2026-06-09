# SmFx::StateMachineEngine::StateMachineEngineImpl::~StateMachineEngineImpl(void)

- ea: `0x180032ed8`
- end: `0x180032fc0`
- name: `??1StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA@XZ`
- size: `232`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180033054`

## callees

- `0x180032ed8`
- `0x18003480c`
- `0x18003489c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032f1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032f1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032f8c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032f8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180032f35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180032f35`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::~StateMachineEngineImpl(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  struct _TP_WORK *v3; // rcx
  void *v4; // rbp
  HANDLE ProcessHeap; // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 976);
  **((_QWORD **)this + 131) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  *((_DWORD *)this + 243) = 0;
  LeaveCriticalSection(v1);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 128);
  if ( v3 )
  {
    CloseThreadpoolWork(v3);
    *((_QWORD *)this + 128) = 0;
    *((_QWORD *)this + 129) = 0;
    *((_QWORD *)this + 130) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 109);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_QWORD *)this + 109) = 0;
  }
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    DeleteCriticalSection(v1);
    LOBYTE(v1[1].DebugInfo) = 0;
  }
  SmFx::Worker::~Worker((SmFx::StateMachineEngine::StateMachineEngineImpl *)((char *)this + 1024));
  SmFx::SpinLock::~SpinLock((SmFx::SpinLock *)v1);
}

```

## disassembly

```asm
0x180032ed8  mov     [rsp+arg_0], rbx
0x180032edd  mov     [rsp+arg_8], rbp
0x180032ee2  mov     [rsp+arg_10], rsi
0x180032ee7  push    rdi
0x180032ee8  sub     rsp, 20h
0x180032eec  mov     rax, [rcx+418h]
0x180032ef3  lea     rbx, [rcx+3D0h]
0x180032efa  mov     rsi, rcx
0x180032efd  mov     rcx, rbx; lpCriticalSection
0x180032f00  and     qword ptr [rax], 0
0x180032f04  call    cs:__imp_EnterCriticalSection
0x180032f0b  nop     dword ptr [rax+rax+00h]
0x180032f10  and     dword ptr [rsi+3CCh], 0
0x180032f17  mov     rcx, rbx; lpCriticalSection
0x180032f1a  call    cs:__imp_LeaveCriticalSection
0x180032f21  nop     dword ptr [rax+rax+00h]
0x180032f26  lea     rdi, [rsi+400h]
0x180032f2d  mov     rcx, [rdi]; pwk
0x180032f30  test    rcx, rcx
0x180032f33  jz      short loc_180032F4F
0x180032f35  call    cs:__imp_CloseThreadpoolWork
0x180032f3c  nop     dword ptr [rax+rax+00h]
0x180032f41  and     qword ptr [rdi], 0
0x180032f45  and     qword ptr [rdi+8], 0
0x180032f4a  and     qword ptr [rdi+10h], 0
0x180032f4f  mov     rbp, [rsi+368h]
0x180032f56  test    rbp, rbp
0x180032f59  jz      short loc_180032F83
0x180032f5b  call    cs:__imp_GetProcessHeap
0x180032f62  nop     dword ptr [rax+rax+00h]
0x180032f67  mov     r8, rbp; lpMem
0x180032f6a  xor     edx, edx; dwFlags
0x180032f6c  mov     rcx, rax; hHeap
0x180032f6f  call    cs:__imp_HeapFree
0x180032f76  nop     dword ptr [rax+rax+00h]
0x180032f7b  and     qword ptr [rsi+368h], 0
0x180032f83  cmp     byte ptr [rbx+28h], 0
0x180032f87  jz      short loc_180032F9C
0x180032f89  mov     rcx, rbx; lpCriticalSection
0x180032f8c  call    cs:__imp_DeleteCriticalSection
0x180032f93  nop     dword ptr [rax+rax+00h]
0x180032f98  mov     byte ptr [rbx+28h], 0
0x180032f9c  mov     rcx, rdi; this
0x180032f9f  call    ??1Worker@SmFx@@QEAA@XZ; SmFx::Worker::~Worker(void)
0x180032fa4  mov     rcx, rbx; this
0x180032fa7  mov     rbx, [rsp+28h+arg_0]
0x180032fac  mov     rbp, [rsp+28h+arg_8]
0x180032fb1  mov     rsi, [rsp+28h+arg_10]
0x180032fb6  add     rsp, 20h
0x180032fba  pop     rdi
0x180032fbb  jmp     ??1SpinLock@SmFx@@QEAA@XZ; SmFx::SpinLock::~SpinLock(void)
```
