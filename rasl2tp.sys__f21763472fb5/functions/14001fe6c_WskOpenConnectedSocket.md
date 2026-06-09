# WskOpenConnectedSocket

- ea: `0x14001fe6c`
- end: `0x14001ff89`
- name: `WskOpenConnectedSocket`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001fb10`

## callees

- `0x140004830`
- `0x14001fe6c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001fe97`
- `ntoskrnl!KeInitializeEvent` at `0x14001fe97`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ff60`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ff60`
- `ntoskrnl!IoAllocateIrp` at `0x14001fea7`
- `ntoskrnl!IoAllocateIrp` at `0x14001fea7`

## pseudocode

```c
__int64 __fastcall WskOpenConnectedSocket(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  PIRP Irp; // rax
  PIRP v9; // r9
  int v10; // ecx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  KeInitializeEvent((PRKEVENT)(a5 + 400), NotificationEvent, 0);
  Irp = IoAllocateIrp(1, 0);
  v9 = Irp;
  if ( Irp )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a5 + 512));
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskOpenConnectedSocketCompletion;
    CurrentStackLocation[-1].Context = (PVOID)a5;
    CurrentStackLocation[-1].Control = -32;
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64, _DWORD, __int64, __int64 (__fastcall **)(int, int, int, int, __int64), _QWORD, _QWORD, _QWORD, PIRP))(a1[1] + 16LL))(
            *a1,
            1,
            6,
            a2,
            a3,
            0,
            a5,
            &g_WskClientConnDispatch,
            0,
            0,
            0,
            v9);
    if ( v10 >= 0 )
    {
      if ( *(_BYTE *)(a5 + 56) )
      {
        if ( v10 == 259 )
          return 0;
      }
      else
      {
        return (unsigned int)KeWaitForSingleObject((PVOID)(a5 + 400), Executive, 0, 0, 0);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001fe6c  push    rbx
0x14001fe6e  push    rbp
0x14001fe6f  push    rsi
0x14001fe70  push    rdi
0x14001fe71  push    r14
0x14001fe73  sub     rsp, 70h
0x14001fe77  mov     rbx, [rsp+98h+arg_20]
0x14001fe7f  mov     rbp, r8
0x14001fe82  mov     r14, rdx
0x14001fe85  mov     rsi, rcx
0x14001fe88  xor     r8d, r8d; State
0x14001fe8b  xor     edx, edx; Type
0x14001fe8d  lea     rdi, [rbx+190h]
0x14001fe94  mov     rcx, rdi; Event
0x14001fe97  call    cs:__imp_KeInitializeEvent
0x14001fe9e  nop     dword ptr [rax+rax+00h]
0x14001fea3  xor     edx, edx; ChargeQuota
0x14001fea5  mov     cl, 1; StackSize
0x14001fea7  call    cs:__imp_IoAllocateIrp
0x14001feae  nop     dword ptr [rax+rax+00h]
0x14001feb3  mov     r9, rax
0x14001feb6  test    rax, rax
0x14001feb9  jnz     short loc_14001FEC5
0x14001febb  mov     ecx, 0C000009Ah
0x14001fec0  jmp     loc_14001FF7B
0x14001fec5  lock inc dword ptr [rbx+200h]
0x14001fecc  mov     rax, [rax+0B8h]
0x14001fed3  lea     rcx, WskOpenConnectedSocketCompletion
0x14001feda  mov     [rsp+98h+var_40], r9
0x14001fedf  mov     edx, 1
0x14001fee4  mov     [rsp+98h+var_48], 0
0x14001feed  mov     r9, r14
0x14001fef0  mov     [rsp+98h+var_50], 0
0x14001fef9  mov     [rax-10h], rcx
0x14001fefd  lea     rcx, g_WskClientConnDispatch
0x14001ff04  mov     [rax-8], rbx
0x14001ff08  lea     r8d, [rdx+5]
0x14001ff0c  mov     byte ptr [rax-45h], 0E0h
0x14001ff10  mov     rax, [rsi+8]
0x14001ff14  mov     [rsp+98h+var_58], 0
0x14001ff1d  mov     [rsp+98h+var_60], rcx
0x14001ff22  mov     rcx, [rsi]
0x14001ff25  mov     rax, [rax+10h]
0x14001ff29  mov     [rsp+98h+var_68], rbx
0x14001ff2e  mov     [rsp+98h+var_70], 0
0x14001ff36  mov     [rsp+98h+Timeout], rbp
0x14001ff3b  call    _guard_dispatch_icall
0x14001ff40  mov     ecx, eax
0x14001ff42  test    eax, eax
0x14001ff44  js      short loc_14001FF7B
0x14001ff46  cmp     byte ptr [rbx+38h], 0
0x14001ff4a  jnz     short loc_14001FF70
0x14001ff4c  xor     r9d, r9d; Alertable
0x14001ff4f  mov     [rsp+98h+Timeout], 0; Timeout
0x14001ff58  xor     r8d, r8d; WaitMode
0x14001ff5b  xor     edx, edx; WaitReason
0x14001ff5d  mov     rcx, rdi; Object
0x14001ff60  call    cs:__imp_KeWaitForSingleObject
0x14001ff67  nop     dword ptr [rax+rax+00h]
0x14001ff6c  mov     ecx, eax
0x14001ff6e  jmp     short loc_14001FF7B
0x14001ff70  xor     eax, eax
0x14001ff72  cmp     ecx, 103h
0x14001ff78  cmovz   ecx, eax
0x14001ff7b  mov     eax, ecx
0x14001ff7d  add     rsp, 70h
0x14001ff81  pop     r14
0x14001ff83  pop     rdi
0x14001ff84  pop     rsi
0x14001ff85  pop     rbp
0x14001ff86  pop     rbx
0x14001ff87  retn
```
