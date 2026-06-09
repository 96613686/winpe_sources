# ClfsTelemetryFinalize

- ea: `0x14004fa98`
- end: `0x14004fc12`
- name: `ClfsTelemetryFinalize`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140035660`

## callees

- `0x140017294`
- `0x14001770c`
- `0x14001784c`
- `0x14004fa98`
- `0x1400503fc`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14004fabd`
- `ntoskrnl!KeCancelTimer` at `0x14004fabd`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14004fad0`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14004fad0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14004faf3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14004faf3`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14004fb8b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14004fb8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fbc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fbe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fbc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fbe0`

## pseudocode

```c
void ClfsTelemetryFinalize()
{
  __int64 v0; // rcx
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rax

  if ( byte_140029768 )
  {
    byte_140029768 = 0;
    KeCancelTimer(Timer);
    KeRemoveQueueDpc(Dpc);
    _InterlockedExchange(&dword_140029748, 1);
    RequestTelemetryWork();
    KeAcquireGuardedMutex(P);
    if ( (__int64 *)qword_140029610 != &qword_140029610 )
      ClfsProcessTelemetryEvents();
    while ( 1 )
    {
      v0 = qword_140029600;
      if ( (__int64 *)qword_140029600 == &qword_140029600 )
        break;
      if ( *(__int64 **)(qword_140029600 + 8) != &qword_140029600
        || (v1 = *(_QWORD *)qword_140029600, *(_QWORD *)(*(_QWORD *)qword_140029600 + 8LL) != qword_140029600) )
      {
LABEL_12:
        __fastfail(3u);
      }
      qword_140029600 = *(_QWORD *)qword_140029600;
      *(_QWORD *)(v1 + 8) = &qword_140029600;
      FreeOpenEvent((PVOID)(v0 - 96));
    }
    while ( 1 )
    {
      v2 = qword_140029610;
      if ( (__int64 *)qword_140029610 == &qword_140029610 )
        break;
      if ( *(__int64 **)(qword_140029610 + 8) != &qword_140029610 )
        goto LABEL_12;
      v3 = *(_QWORD *)qword_140029610;
      if ( *(_QWORD *)(*(_QWORD *)qword_140029610 + 8LL) != qword_140029610 )
        goto LABEL_12;
      qword_140029610 = *(_QWORD *)qword_140029610;
      *(_QWORD *)(v3 + 8) = &qword_140029610;
      FreeOpenEvent((PVOID)(v2 - 96));
    }
    KeReleaseGuardedMutex(P);
    ExFreePoolWithTag(Timer, 0);
    Timer = 0;
    ExFreePoolWithTag(Dpc, 0);
    Dpc = 0;
    ExFreePoolWithTag(P, 0);
    P = 0;
    dword_14002974C = 0;
    TraceLoggingUnregister_EtwUnregister();
  }
}

```

## disassembly

```asm
0x14004fa98  mov     [rsp+arg_0], rsi
0x14004fa9d  push    rdi
0x14004fa9e  sub     rsp, 20h
0x14004faa2  cmp     cs:byte_140029768, 0
0x14004faa9  jz      loc_14004FC06
0x14004faaf  mov     rcx, cs:Timer; PKTIMER
0x14004fab6  mov     cs:byte_140029768, 0
0x14004fabd  call    cs:__imp_KeCancelTimer
0x14004fac4  nop     dword ptr [rax+rax+00h]
0x14004fac9  mov     rcx, cs:Dpc; Dpc
0x14004fad0  call    cs:__imp_KeRemoveQueueDpc
0x14004fad7  nop     dword ptr [rax+rax+00h]
0x14004fadc  mov     eax, 1
0x14004fae1  xchg    eax, cs:dword_140029748
0x14004fae7  call    RequestTelemetryWork
0x14004faec  mov     rcx, cs:P; Mutex
0x14004faf3  call    cs:__imp_KeAcquireGuardedMutex
0x14004fafa  nop     dword ptr [rax+rax+00h]
0x14004faff  lea     rdi, qword_140029610
0x14004fb06  cmp     cs:qword_140029610, rdi
0x14004fb0d  jz      short loc_14004FB14
0x14004fb0f  call    ?ClfsProcessTelemetryEvents@@YAXXZ; ClfsProcessTelemetryEvents(void)
0x14004fb14  lea     rsi, qword_140029600
0x14004fb1b  mov     rcx, cs:qword_140029600
0x14004fb22  cmp     rcx, rsi
0x14004fb25  jz      short loc_14004FB4C
0x14004fb27  cmp     [rcx+8], rsi
0x14004fb2b  jnz     short loc_14004FB7D
0x14004fb2d  mov     rax, [rcx]
0x14004fb30  cmp     [rax+8], rcx
0x14004fb34  jnz     short loc_14004FB7D
0x14004fb36  mov     cs:qword_140029600, rax
0x14004fb3d  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14004fb41  mov     [rax+8], rsi
0x14004fb45  call    FreeOpenEvent
0x14004fb4a  jmp     short loc_14004FB1B
0x14004fb4c  mov     rcx, cs:qword_140029610
0x14004fb53  cmp     rcx, rdi
0x14004fb56  jz      short loc_14004FB84
0x14004fb58  cmp     [rcx+8], rdi
0x14004fb5c  jnz     short loc_14004FB7D
0x14004fb5e  mov     rax, [rcx]
0x14004fb61  cmp     [rax+8], rcx
0x14004fb65  jnz     short loc_14004FB7D
0x14004fb67  mov     cs:qword_140029610, rax
0x14004fb6e  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14004fb72  mov     [rax+8], rdi
0x14004fb76  call    FreeOpenEvent
0x14004fb7b  jmp     short loc_14004FB4C
0x14004fb7d  mov     ecx, 3
0x14004fb82  int     29h; Win8: RtlFailFast(ecx)
0x14004fb84  mov     rcx, cs:P; Mutex
0x14004fb8b  call    cs:__imp_KeReleaseGuardedMutex
0x14004fb92  nop     dword ptr [rax+rax+00h]
0x14004fb97  mov     rcx, cs:Timer; P
0x14004fb9e  xor     edx, edx; Tag
0x14004fba0  call    cs:__imp_ExFreePoolWithTag
0x14004fba7  nop     dword ptr [rax+rax+00h]
0x14004fbac  mov     rcx, cs:Dpc; P
0x14004fbb3  xor     edx, edx; Tag
0x14004fbb5  mov     cs:Timer, 0
0x14004fbc0  call    cs:__imp_ExFreePoolWithTag
0x14004fbc7  nop     dword ptr [rax+rax+00h]
0x14004fbcc  mov     rcx, cs:P; P
0x14004fbd3  xor     edx, edx; Tag
0x14004fbd5  mov     cs:Dpc, 0
0x14004fbe0  call    cs:__imp_ExFreePoolWithTag
0x14004fbe7  nop     dword ptr [rax+rax+00h]
0x14004fbec  mov     cs:P, 0
0x14004fbf7  mov     cs:dword_14002974C, 0
0x14004fc01  call    TraceLoggingUnregister_EtwUnregister
0x14004fc06  mov     rsi, [rsp+28h+arg_0]
0x14004fc0b  add     rsp, 20h
0x14004fc0f  pop     rdi
0x14004fc10  retn
```
