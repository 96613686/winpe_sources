# VmbusTlCreateConnection

- ea: `0x1400193ec`
- end: `0x140019543`
- name: `VmbusTlCreateConnection`
- size: `343`
- prototype: `__int64 __fastcall(__int64, struct _KPROCESS *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14001c2d0`
- `0x140020b80`

## callees

- `0x14000a2c8`
- `0x1400193ec`
- `0x140019b70`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001947c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001949d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400194be`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001947c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001949d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400194be`
- `ntoskrnl!KeInitializeEvent` at `0x14001951f`
- `ntoskrnl!KeInitializeEvent` at `0x14001951f`
- `ntoskrnl!KeInitializeDpc` at `0x1400194f8`
- `ntoskrnl!KeInitializeDpc` at `0x1400194f8`
- `ntoskrnl!KeInitializeTimer` at `0x1400194db`
- `ntoskrnl!KeInitializeTimer` at `0x1400194db`
- `ntoskrnl!PsGetProcessId` at `0x14001943a`
- `ntoskrnl!PsGetProcessId` at `0x14001943a`

## string_xrefs

- `0x140019449`: `VmbusTlCreateConnection`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateConnection(__int64 a1, struct _KPROCESS *a2, _QWORD *a3)
{
  int v5; // ebx
  unsigned int ProcessId; // eax
  char *v7; // rbx
  _QWORD *v8; // rax
  KSPIN_LOCK *v9; // rcx
  PVOID DeferredContext; // [rsp+48h] [rbp+20h] BYREF

  DeferredContext = 0;
  v5 = VmbusTlCreateEndpoint(a1, a2, 2, &DeferredContext);
  if ( v5 >= 0 )
  {
    v7 = (char *)DeferredContext;
    v8 = (char *)DeferredContext + 800;
    v9 = (KSPIN_LOCK *)((char *)DeferredContext + 816);
    *((_QWORD *)DeferredContext + 101) = (char *)DeferredContext + 800;
    *v8 = v8;
    KeInitializeSpinLock(v9);
    *((_QWORD *)v7 + 105) = v7 + 832;
    *((_QWORD *)v7 + 104) = v7 + 832;
    KeInitializeSpinLock((PKSPIN_LOCK)v7 + 106);
    *((_QWORD *)v7 + 95) = v7 + 752;
    *((_QWORD *)v7 + 94) = v7 + 752;
    KeInitializeSpinLock((PKSPIN_LOCK)v7 + 93);
    *((_DWORD *)v7 + 193) = 1;
    KeInitializeTimer((PKTIMER)(v7 + 336));
    KeInitializeDpc((PRKDPC)(v7 + 400), VmbusTlConnectTimeoutDpc, v7);
    *((GUID *)v7 + 56) = HV_GUID_ZERO;
    KeInitializeEvent((PRKEVENT)(v7 + 712), NotificationEvent, 1u);
    *a3 = v7;
    return 0;
  }
  else if ( (unsigned int)dword_140013058 > 2 )
  {
    if ( a2 )
      ProcessId = (unsigned int)PsGetProcessId(a2);
    else
      ProcessId = 0;
    HvsocketTraceULongError("VmbusTlCreateConnection", 78, (unsigned int)v5, ProcessId);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400193ec  mov     rax, rsp
0x1400193ef  mov     [rax+8], rbx
0x1400193f3  mov     [rax+10h], rsi
0x1400193f7  push    rdi
0x1400193f8  sub     rsp, 20h
0x1400193fc  mov     rsi, r8
0x1400193ff  mov     qword ptr [rax+20h], 0
0x140019407  mov     r8d, 2
0x14001940d  lea     r9, [rax+20h]
0x140019411  mov     rdi, rdx
0x140019414  call    VmbusTlCreateEndpoint
0x140019419  mov     ebx, eax
0x14001941b  test    eax, eax
0x14001941d  jns     short loc_140019462
0x14001941f  mov     ecx, cs:dword_140013058
0x140019425  cmp     ecx, 2
0x140019428  jbe     loc_140019530
0x14001942e  test    rdi, rdi
0x140019431  jnz     short loc_140019437
0x140019433  xor     eax, eax
0x140019435  jmp     short loc_140019446
0x140019437  mov     rcx, rdi; Process
0x14001943a  call    cs:__imp_PsGetProcessId
0x140019441  nop     dword ptr [rax+rax+00h]
0x140019446  mov     r9d, eax
0x140019449  lea     rcx, aVmbustlcreatec; "VmbusTlCreateConnection"
0x140019450  mov     r8d, ebx
0x140019453  mov     edx, 4Eh ; 'N'
0x140019458  call    HvsocketTraceULongError
0x14001945d  jmp     loc_140019530
0x140019462  mov     rbx, [rsp+28h+DeferredContext]
0x140019467  lea     rax, [rbx+320h]
0x14001946e  lea     rcx, [rbx+330h]; SpinLock
0x140019475  mov     [rax+8], rax
0x140019479  mov     [rax], rax
0x14001947c  call    cs:__imp_KeInitializeSpinLock
0x140019483  nop     dword ptr [rax+rax+00h]
0x140019488  lea     rax, [rbx+340h]
0x14001948f  lea     rcx, [rbx+350h]; SpinLock
0x140019496  mov     [rax+8], rax
0x14001949a  mov     [rax], rax
0x14001949d  call    cs:__imp_KeInitializeSpinLock
0x1400194a4  nop     dword ptr [rax+rax+00h]
0x1400194a9  lea     rax, [rbx+2F0h]
0x1400194b0  lea     rcx, [rbx+2E8h]; SpinLock
0x1400194b7  mov     [rax+8], rax
0x1400194bb  mov     [rax], rax
0x1400194be  call    cs:__imp_KeInitializeSpinLock
0x1400194c5  nop     dword ptr [rax+rax+00h]
0x1400194ca  lea     rcx, [rbx+150h]; Timer
0x1400194d1  mov     dword ptr [rbx+304h], 1
0x1400194db  call    cs:__imp_KeInitializeTimer
0x1400194e2  nop     dword ptr [rax+rax+00h]
0x1400194e7  lea     rcx, [rbx+190h]; Dpc
0x1400194ee  mov     r8, rbx; DeferredContext
0x1400194f1  lea     rdx, VmbusTlConnectTimeoutDpc; DeferredRoutine
0x1400194f8  call    cs:__imp_KeInitializeDpc
0x1400194ff  nop     dword ptr [rax+rax+00h]
0x140019504  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x14001950b  lea     rcx, [rbx+2C8h]; Event
0x140019512  mov     r8b, 1; State
0x140019515  xor     edx, edx; Type
0x140019517  movdqu  xmmword ptr [rbx+380h], xmm0
0x14001951f  call    cs:__imp_KeInitializeEvent
0x140019526  nop     dword ptr [rax+rax+00h]
0x14001952b  mov     [rsi], rbx
0x14001952e  xor     ebx, ebx
0x140019530  mov     rsi, [rsp+28h+arg_8]
0x140019535  mov     eax, ebx
0x140019537  mov     rbx, [rsp+28h+arg_0]
0x14001953c  add     rsp, 20h
0x140019540  pop     rdi
0x140019541  retn
```
