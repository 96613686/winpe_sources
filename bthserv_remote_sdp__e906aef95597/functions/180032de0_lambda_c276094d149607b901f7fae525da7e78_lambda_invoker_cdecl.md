# _lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_

- ea: `0x180032de0`
- end: `0x180032ed2`
- name: `_lambda_c276094d149607b901f7fae525da7e78_::_lambda_invoker_cdecl_`
- size: `242`
- prototype: `__int64 __fastcall(SmFx::StateMachineEngine::StateMachineEngineImpl *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180032de0`
- `0x1800331c4`
- `0x180033408`
- `0x180033ef0`
- `0x180034240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032e9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032e1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032e30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032e30`

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
0x180032de0  mov     [rsp+arg_0], rbx
0x180032de5  mov     [rsp+arg_8], rsi
0x180032dea  push    rdi
0x180032deb  sub     rsp, 20h
0x180032def  lea     rsi, [rcx+3D0h]
0x180032df6  mov     rdi, rcx
0x180032df9  mov     rcx, rsi; lpCriticalSection
0x180032dfc  call    cs:__imp_EnterCriticalSection
0x180032e03  nop     dword ptr [rax+rax+00h]
0x180032e08  mov     ebx, [rdi+3CCh]
0x180032e0e  mov     rcx, rsi; lpCriticalSection
0x180032e11  mov     dword ptr [rdi+3CCh], 2
0x180032e1b  call    cs:__imp_LeaveCriticalSection
0x180032e22  nop     dword ptr [rax+rax+00h]
0x180032e27  mov     word ptr [rdi+3C6h], 1
0x180032e30  call    cs:__imp_GetCurrentThreadId
0x180032e37  nop     dword ptr [rax+rax+00h]
0x180032e3c  mov     [rdi+3C8h], eax
0x180032e42  sub     ebx, 3
0x180032e45  jz      short loc_180032E79
0x180032e47  cmp     ebx, 1
0x180032e4a  jnz     short loc_180032EC1
0x180032e4c  lea     rbx, [rdi+3B0h]
0x180032e53  mov     rcx, rdi
0x180032e56  mov     rdx, rbx
0x180032e59  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x180032e5e  xorps   xmm0, xmm0
0x180032e61  mov     rcx, rsi; lpCriticalSection
0x180032e64  movdqu  xmmword ptr [rbx], xmm0
0x180032e68  call    cs:__imp_EnterCriticalSection
0x180032e6f  nop     dword ptr [rax+rax+00h]
0x180032e74  mov     rcx, rdi
0x180032e77  jmp     short loc_180032EB3
0x180032e79  lea     rbx, [rdi+3B0h]
0x180032e80  mov     rcx, rdi
0x180032e83  mov     rdx, rbx
0x180032e86  call    ?ExecuteEventAction@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@AEBUEVENT_ACTION@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteEventAction(SmFx::StateMachineEngine::StateMachineEngineImpl::EVENT_ACTION const &)
0x180032e8b  xorps   xmm0, xmm0
0x180032e8e  mov     rcx, rdi
0x180032e91  movdqu  xmmword ptr [rbx], xmm0
0x180032e95  call    ?ExecuteCurrentState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA?AW4EngineState@123@XZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ExecuteCurrentState(void)
0x180032e9a  mov     rcx, rsi; lpCriticalSection
0x180032e9d  mov     ebx, eax
0x180032e9f  call    cs:__imp_EnterCriticalSection
0x180032ea6  nop     dword ptr [rax+rax+00h]
0x180032eab  mov     rcx, rdi; this
0x180032eae  cmp     ebx, 1
0x180032eb1  jnz     short loc_180032EBA
0x180032eb3  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x180032eb8  jmp     short loc_180032EC1
0x180032eba  mov     edx, ebx
0x180032ebc  call    ?UpdateEngineState@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXW4EngineState@123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::UpdateEngineState(SmFx::StateMachineEngine::StateMachineEngineImpl::EngineState)
0x180032ec1  mov     rbx, [rsp+28h+arg_0]
0x180032ec6  mov     rsi, [rsp+28h+arg_8]
0x180032ecb  add     rsp, 20h
0x180032ecf  pop     rdi
0x180032ed0  retn
```
