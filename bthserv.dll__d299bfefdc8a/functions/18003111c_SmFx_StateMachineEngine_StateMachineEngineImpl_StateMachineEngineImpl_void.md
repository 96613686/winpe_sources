# SmFx::StateMachineEngine::StateMachineEngineImpl::~StateMachineEngineImpl(void)

- ea: `0x18003111c`
- end: `0x1800311e7`
- name: `??1StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA@XZ`
- size: `203`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001db80`
- `0x180031278`

## callees

- `0x18003111c`
- `0x1800329c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031140`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031140`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031153`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031153`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800311b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800311d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800311b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800311d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031191`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031191`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003119f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003119f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180031168`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180031168`

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
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    DeleteCriticalSection(v1);
    LOBYTE(v1[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18003111c  push    rbx
0x18003111e  push    rbp
0x18003111f  push    rsi
0x180031120  push    rdi
0x180031121  sub     rsp, 28h
0x180031125  mov     rax, [rcx+418h]
0x18003112c  lea     rbx, [rcx+3D0h]
0x180031133  mov     rsi, rcx
0x180031136  mov     rcx, rbx; lpCriticalSection
0x180031139  mov     qword ptr [rax], 0
0x180031140  call    cs:__imp_EnterCriticalSection
0x180031146  mov     rcx, rbx; lpCriticalSection
0x180031149  mov     dword ptr [rsi+3CCh], 0
0x180031153  call    cs:__imp_LeaveCriticalSection
0x180031159  lea     rdi, [rsi+400h]
0x180031160  mov     rcx, [rdi]; pwk
0x180031163  test    rcx, rcx
0x180031166  jz      short loc_180031185
0x180031168  call    cs:__imp_CloseThreadpoolWork
0x18003116e  mov     qword ptr [rdi], 0
0x180031175  mov     qword ptr [rdi+8], 0
0x18003117d  mov     qword ptr [rdi+10h], 0
0x180031185  mov     rbp, [rsi+368h]
0x18003118c  test    rbp, rbp
0x18003118f  jz      short loc_1800311B0
0x180031191  call    cs:__imp_GetProcessHeap
0x180031197  mov     r8, rbp; lpMem
0x18003119a  xor     edx, edx; dwFlags
0x18003119c  mov     rcx, rax; hHeap
0x18003119f  call    cs:__imp_HeapFree
0x1800311a5  mov     qword ptr [rsi+368h], 0
0x1800311b0  cmp     byte ptr [rbx+28h], 0
0x1800311b4  jz      short loc_1800311C3
0x1800311b6  mov     rcx, rbx; lpCriticalSection
0x1800311b9  call    cs:__imp_DeleteCriticalSection
0x1800311bf  mov     byte ptr [rbx+28h], 0
0x1800311c3  mov     rcx, rdi; this
0x1800311c6  call    ??1Worker@SmFx@@QEAA@XZ; SmFx::Worker::~Worker(void)
0x1800311cb  cmp     byte ptr [rbx+28h], 0
0x1800311cf  jz      short loc_1800311DE
0x1800311d1  mov     rcx, rbx; lpCriticalSection
0x1800311d4  call    cs:__imp_DeleteCriticalSection
0x1800311da  mov     byte ptr [rbx+28h], 0
0x1800311de  add     rsp, 28h
0x1800311e2  pop     rdi
0x1800311e3  pop     rsi
0x1800311e4  pop     rbp
0x1800311e5  pop     rbx
0x1800311e6  retn
```
