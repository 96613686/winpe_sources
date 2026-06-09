# WskOpenConnectedSocket

- ea: `0x14001d57c`
- end: `0x14001d699`
- name: `WskOpenConnectedSocket`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001d1a0`

## callees

- `0x140007710`
- `0x14001d57c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001d5a7`
- `ntoskrnl!KeInitializeEvent` at `0x14001d5a7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d670`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d670`
- `ntoskrnl!IoAllocateIrp` at `0x14001d5b7`
- `ntoskrnl!IoAllocateIrp` at `0x14001d5b7`

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
0x14001d57c  push    rbx
0x14001d57e  push    rbp
0x14001d57f  push    rsi
0x14001d580  push    rdi
0x14001d581  push    r14
0x14001d583  sub     rsp, 70h
0x14001d587  mov     rbx, [rsp+98h+arg_20]
0x14001d58f  mov     rbp, r8
0x14001d592  mov     r14, rdx
0x14001d595  mov     rsi, rcx
0x14001d598  xor     r8d, r8d; State
0x14001d59b  xor     edx, edx; Type
0x14001d59d  lea     rdi, [rbx+190h]
0x14001d5a4  mov     rcx, rdi; Event
0x14001d5a7  call    cs:__imp_KeInitializeEvent
0x14001d5ae  nop     dword ptr [rax+rax+00h]
0x14001d5b3  xor     edx, edx; ChargeQuota
0x14001d5b5  mov     cl, 1; StackSize
0x14001d5b7  call    cs:__imp_IoAllocateIrp
0x14001d5be  nop     dword ptr [rax+rax+00h]
0x14001d5c3  mov     r9, rax
0x14001d5c6  test    rax, rax
0x14001d5c9  jnz     short loc_14001D5D5
0x14001d5cb  mov     ecx, 0C000009Ah
0x14001d5d0  jmp     loc_14001D68B
0x14001d5d5  lock inc dword ptr [rbx+200h]
0x14001d5dc  mov     rax, [rax+0B8h]
0x14001d5e3  lea     rcx, WskOpenConnectedSocketCompletion
0x14001d5ea  mov     [rsp+98h+var_40], r9
0x14001d5ef  mov     edx, 1
0x14001d5f4  mov     [rsp+98h+var_48], 0
0x14001d5fd  mov     r9, r14
0x14001d600  mov     [rsp+98h+var_50], 0
0x14001d609  mov     [rax-10h], rcx
0x14001d60d  lea     rcx, g_WskClientConnDispatch
0x14001d614  mov     [rax-8], rbx
0x14001d618  lea     r8d, [rdx+5]
0x14001d61c  mov     byte ptr [rax-45h], 0E0h
0x14001d620  mov     rax, [rsi+8]
0x14001d624  mov     [rsp+98h+var_58], 0
0x14001d62d  mov     [rsp+98h+var_60], rcx
0x14001d632  mov     rcx, [rsi]
0x14001d635  mov     rax, [rax+10h]
0x14001d639  mov     [rsp+98h+var_68], rbx
0x14001d63e  mov     [rsp+98h+var_70], 0
0x14001d646  mov     [rsp+98h+Timeout], rbp
0x14001d64b  call    _guard_dispatch_icall
0x14001d650  mov     ecx, eax
0x14001d652  test    eax, eax
0x14001d654  js      short loc_14001D68B
0x14001d656  cmp     byte ptr [rbx+38h], 0
0x14001d65a  jnz     short loc_14001D680
0x14001d65c  xor     r9d, r9d; Alertable
0x14001d65f  mov     [rsp+98h+Timeout], 0; Timeout
0x14001d668  xor     r8d, r8d; WaitMode
0x14001d66b  xor     edx, edx; WaitReason
0x14001d66d  mov     rcx, rdi; Object
0x14001d670  call    cs:__imp_KeWaitForSingleObject
0x14001d677  nop     dword ptr [rax+rax+00h]
0x14001d67c  mov     ecx, eax
0x14001d67e  jmp     short loc_14001D68B
0x14001d680  xor     eax, eax
0x14001d682  cmp     ecx, 103h
0x14001d688  cmovz   ecx, eax
0x14001d68b  mov     eax, ecx
0x14001d68d  add     rsp, 70h
0x14001d691  pop     r14
0x14001d693  pop     rdi
0x14001d694  pop     rsi
0x14001d695  pop     rbp
0x14001d696  pop     rbx
0x14001d697  retn
```
