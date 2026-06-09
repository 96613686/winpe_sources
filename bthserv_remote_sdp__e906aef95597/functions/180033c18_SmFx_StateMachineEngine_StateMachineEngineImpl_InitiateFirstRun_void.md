# SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(void)

- ea: `0x180033c18`
- end: `0x180033ce8`
- name: `?InitiateFirstRun@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ`
- size: `208`
- prototype: `void __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180033ac4`

## callees

- `0x1800331c4`
- `0x180033408`
- `0x180033c18`
- `0x180033ef0`
- `0x180034240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033c34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033cb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033c34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033cb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033c4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033c4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033c62`

## pseudocode

```c
void __fastcall SmFx::StateMachineEngine::StateMachineEngineImpl::InitiateFirstRun(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // edi
  _QWORD v4[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 976);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  *((_DWORD *)this + 243) = 2;
  LeaveCriticalSection(v1);
  *((_WORD *)this + 483) = 0;
  v4[0] = 6;
  *((_DWORD *)this + 242) = GetCurrentThreadId();
  v4[1] = *(_QWORD *)(*((_QWORD *)this + 111) + 8LL) + 2LL * **((unsigned __int8 **)this + 111);
  v3 = SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(this, v4);
  if ( v3 == 2 )
    v3 = SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(this);
  EnterCriticalSection(v1);
  if ( v3 == 1 )
    SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(this);
  else
    SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState((__int64)this, v3);
}

```

## disassembly

```asm
0x180033c18  mov     [rsp+arg_0], rbx
0x180033c1d  mov     [rsp+arg_8], rsi
0x180033c22  push    rdi
0x180033c23  sub     rsp, 30h
0x180033c27  lea     rsi, [rcx+3D0h]
0x180033c2e  mov     rbx, rcx
0x180033c31  mov     rcx, rsi; lpCriticalSection
0x180033c34  call    cs:__imp_EnterCriticalSection
0x180033c3b  nop     dword ptr [rax+rax+00h]
0x180033c40  mov     rcx, rsi; lpCriticalSection
0x180033c43  mov     dword ptr [rbx+3CCh], 2
0x180033c4d  call    cs:__imp_LeaveCriticalSection
0x180033c54  nop     dword ptr [rax+rax+00h]
0x180033c59  xor     edi, edi
0x180033c5b  mov     [rbx+3C6h], di
0x180033c62  call    cs:__imp_GetCurrentThreadId
0x180033c69  nop     dword ptr [rax+rax+00h]
0x180033c6e  mov     rcx, rbx
0x180033c71  mov     [rsp+38h+var_18], 6
0x180033c7a  mov     [rbx+3C8h], eax
0x180033c80  mov     rax, [rbx+378h]
0x180033c87  movzx   edx, byte ptr [rax]
0x180033c8a  mov     rax, [rax+8]
0x180033c8e  lea     rdx, [rax+rdx*2]
0x180033c92  mov     [rsp+38h+var_10], rdx
0x180033c97  lea     rdx, [rsp+38h+var_18]
0x180033c9c  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x180033ca1  mov     edi, eax
0x180033ca3  cmp     eax, 2
0x180033ca6  jnz     short loc_180033CB2
0x180033ca8  mov     rcx, rbx
0x180033cab  call    ?ExecuteCurrentState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(void)
0x180033cb0  mov     edi, eax
0x180033cb2  mov     rcx, rsi; lpCriticalSection
0x180033cb5  call    cs:__imp_EnterCriticalSection
0x180033cbc  nop     dword ptr [rax+rax+00h]
0x180033cc1  mov     rcx, rbx; this
0x180033cc4  cmp     edi, 1
0x180033cc7  jnz     short loc_180033CD0
0x180033cc9  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x180033cce  jmp     short loc_180033CD7
0x180033cd0  mov     edx, edi
0x180033cd2  call    ?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)
0x180033cd7  mov     rbx, [rsp+38h+arg_0]
0x180033cdc  mov     rsi, [rsp+38h+arg_8]
0x180033ce1  add     rsp, 30h
0x180033ce5  pop     rdi
0x180033ce6  retn
```
