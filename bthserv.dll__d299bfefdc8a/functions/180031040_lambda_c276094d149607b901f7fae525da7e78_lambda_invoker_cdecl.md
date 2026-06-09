# _lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_

- ea: `0x180031040`
- end: `0x180031113`
- name: `_lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_`
- size: `211`
- prototype: `__int64 __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180031040`
- `0x1800313bc`
- `0x1800315f0`
- `0x180032048`
- `0x1800322e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003105c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003105c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031075`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031084`

## pseudocode

```c
void __fastcall lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_(
        SmFx::StateMachineEngine::StateMachineEngineImpl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // ebx
  int v4; // ebx
  SmFx::StateMachineEngine::StateMachineEngineImpl *v5; // rcx
  int v6; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 976);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 976));
  v3 = *((_DWORD *)this + 243);
  *((_DWORD *)this + 243) = 2;
  LeaveCriticalSection(v1);
  *((_WORD *)this + 483) = 1;
  *((_DWORD *)this + 242) = GetCurrentThreadId();
  v4 = v3 - 3;
  if ( v4 )
  {
    if ( v4 != 1 )
      return;
    SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(this, (char *)this + 944);
    *((_OWORD *)this + 59) = 0;
    EnterCriticalSection(v1);
    v5 = this;
    goto LABEL_5;
  }
  SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(this, (char *)this + 944);
  *((_OWORD *)this + 59) = 0;
  v6 = SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(this);
  EnterCriticalSection(v1);
  v5 = this;
  if ( v6 == 1 )
  {
LABEL_5:
    SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(v5);
    return;
  }
  SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState((__int64)this, v6);
}

```

## disassembly

```asm
0x180031040  mov     [rsp+arg_0], rbx
0x180031045  mov     [rsp+arg_8], rsi
0x18003104a  push    rdi
0x18003104b  sub     rsp, 20h
0x18003104f  lea     rsi, [rcx+3D0h]
0x180031056  mov     rdi, rcx
0x180031059  mov     rcx, rsi; lpCriticalSection
0x18003105c  call    cs:__imp_EnterCriticalSection
0x180031062  mov     ebx, [rdi+3CCh]
0x180031068  mov     rcx, rsi; lpCriticalSection
0x18003106b  mov     dword ptr [rdi+3CCh], 2
0x180031075  call    cs:__imp_LeaveCriticalSection
0x18003107b  mov     word ptr [rdi+3C6h], 1
0x180031084  call    cs:__imp_GetCurrentThreadId
0x18003108a  mov     [rdi+3C8h], eax
0x180031090  sub     ebx, 3
0x180031093  jz      short loc_1800310C1
0x180031095  cmp     ebx, 1
0x180031098  jnz     short loc_180031103
0x18003109a  lea     rbx, [rdi+3B0h]
0x1800310a1  mov     rcx, rdi
0x1800310a4  mov     rdx, rbx
0x1800310a7  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x1800310ac  xorps   xmm0, xmm0
0x1800310af  mov     rcx, rsi; lpCriticalSection
0x1800310b2  movdqu  xmmword ptr [rbx], xmm0
0x1800310b6  call    cs:__imp_EnterCriticalSection
0x1800310bc  mov     rcx, rdi
0x1800310bf  jmp     short loc_1800310F5
0x1800310c1  lea     rbx, [rdi+3B0h]
0x1800310c8  mov     rcx, rdi
0x1800310cb  mov     rdx, rbx
0x1800310ce  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x1800310d3  xorps   xmm0, xmm0
0x1800310d6  mov     rcx, rdi
0x1800310d9  movdqu  xmmword ptr [rbx], xmm0
0x1800310dd  call    ?ExecuteCurrentState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(void)
0x1800310e2  mov     rcx, rsi; lpCriticalSection
0x1800310e5  mov     ebx, eax
0x1800310e7  call    cs:__imp_EnterCriticalSection
0x1800310ed  mov     rcx, rdi; this
0x1800310f0  cmp     ebx, 1
0x1800310f3  jnz     short loc_1800310FC
0x1800310f5  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x1800310fa  jmp     short loc_180031103
0x1800310fc  mov     edx, ebx
0x1800310fe  call    ?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)
0x180031103  mov     rbx, [rsp+28h+arg_0]
0x180031108  mov     rsi, [rsp+28h+arg_8]
0x18003110d  add     rsp, 20h
0x180031111  pop     rdi
0x180031112  retn
```
