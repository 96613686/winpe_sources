# FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EnqueueEvent(FingerprintCollectorStateMachine<FingerprintCollectorTimer>::Event)

- ea: `0x1800206b0`
- end: `0x1800207a9`
- name: `?EnqueueEvent@?$FingerprintCollectorStateMachine@VFingerprintCollectorTimer@@@@QEAAXW4Event@1@@Z`
- size: `249`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ffe0`
- `0x1800205b8`
- `0x180021820`

## callees

- `0x1800206b0`
- `0x1800330dc`
- `0x180033ef0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800206d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800206d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002079b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002079b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020747`

## pseudocode

```c
void __fastcall FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EnqueueEvent(
        _QWORD *a1,
        unsigned __int16 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  int v5; // eax
  bool v6; // si
  void (__fastcall *v7)(_QWORD, __int64); // rax
  __int64 v8; // rdx

  v2 = *a1;
  v3 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)(*a1 + 976LL);
  EnterCriticalSection(v4);
  v5 = *(_DWORD *)(v2 + 972);
  if ( v5 == 5 )
  {
    if ( (_WORD)v3 == *(_WORD *)(v2 + 880) )
    {
      v7 = *(void (__fastcall **)(_QWORD, __int64))(v2 + 912);
      if ( v7 )
      {
        if ( (_WORD)v3 )
          v8 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v2 + 888) + 16LL) + 4 * v3);
        else
          v8 = 0;
        v7(*(_QWORD *)(v2 + 896), v8);
      }
      *(_WORD *)(v2 + 880) = 0;
LABEL_10:
      *(_WORD *)(v2 + 966) = 0;
      *(_DWORD *)(v2 + 968) = GetCurrentThreadId();
      SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue((SmFx::StateMachineEngine::StateMachineEngineImpl *)v2);
      return;
    }
    v6 = 0;
  }
  else
  {
    v6 = v5 == 1;
  }
  if ( SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEventWithDisposition(
         (SmFx::StateMachineEngine::StateMachineEngineImpl *)v2,
         v3) )
  {
    if ( !v6 )
    {
      LeaveCriticalSection(v4);
      return;
    }
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x1800206b0  mov     rax, rsp
0x1800206b3  mov     [rax+8], rbx
0x1800206b7  mov     [rax+10h], rbp
0x1800206bb  mov     [rax+18h], rsi
0x1800206bf  mov     [rax+20h], rdi
0x1800206c3  push    r14
0x1800206c5  sub     rsp, 20h
0x1800206c9  mov     rbx, [rcx]
0x1800206cc  movzx   edi, dx
0x1800206cf  lea     rbp, [rbx+3D0h]
0x1800206d6  mov     rcx, rbp; lpCriticalSection
0x1800206d9  call    cs:__imp_EnterCriticalSection
0x1800206e0  nop     dword ptr [rax+rax+00h]
0x1800206e5  mov     eax, [rbx+3CCh]
0x1800206eb  xor     r14d, r14d
0x1800206ee  cmp     eax, 5
0x1800206f1  jnz     loc_18002077D
0x1800206f7  cmp     di, [rbx+370h]
0x1800206fe  jz      short loc_180020705
0x180020700  mov     sil, r14b
0x180020703  jmp     short loc_180020784
0x180020705  mov     rax, [rbx+390h]
0x18002070c  test    rax, rax
0x18002070f  jz      short loc_180020737
0x180020711  test    di, di
0x180020714  jnz     short loc_18002071C
0x180020716  movzx   edx, r14w
0x18002071a  jmp     short loc_18002072B
0x18002071c  mov     rcx, [rbx+378h]
0x180020723  mov     rcx, [rcx+10h]
0x180020727  movzx   edx, word ptr [rcx+rdi*4]
0x18002072b  mov     rcx, [rbx+380h]
0x180020732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020737  mov     [rbx+370h], r14w
0x18002073f  mov     [rbx+3C6h], r14w
0x180020747  call    cs:__imp_GetCurrentThreadId
0x18002074e  nop     dword ptr [rax+rax+00h]
0x180020753  mov     rcx, rbx; this
0x180020756  mov     [rbx+3C8h], eax
0x18002075c  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x180020761  mov     rbx, [rsp+28h+arg_0]
0x180020766  mov     rbp, [rsp+28h+arg_8]
0x18002076b  mov     rsi, [rsp+28h+arg_10]
0x180020770  mov     rdi, [rsp+28h+arg_18]
0x180020775  add     rsp, 20h
0x180020779  pop     r14
0x18002077b  retn
0x18002077d  cmp     eax, 1
0x180020780  setz    sil
0x180020784  movzx   edx, di; unsigned __int16
0x180020787  mov     rcx, rbx; this
0x18002078a  call    ?EnqueueEventWithDisposition@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA_NG@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEventWithDisposition(ushort)
0x18002078f  test    al, al
0x180020791  jz      short loc_180020761
0x180020793  test    sil, sil
0x180020796  jnz     short loc_18002073F
0x180020798  mov     rcx, rbp; lpCriticalSection
0x18002079b  call    cs:__imp_LeaveCriticalSection
0x1800207a2  nop     dword ptr [rax+rax+00h]
0x1800207a7  jmp     short loc_180020761
```
