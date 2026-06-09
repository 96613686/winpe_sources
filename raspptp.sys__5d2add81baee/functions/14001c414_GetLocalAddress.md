# GetLocalAddress

- ea: `0x14001c414`
- end: `0x14001c4dc`
- name: `GetLocalAddress`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400122b0`
- `0x140013954`

## callees

- `0x140007710`
- `0x140014c30`
- `0x14001c414`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001c460`
- `ntoskrnl!ExAllocatePool2` at `0x14001c460`
- `ntoskrnl!IoFreeIrp` at `0x14001c47c`
- `ntoskrnl!IoFreeIrp` at `0x14001c47c`
- `ntoskrnl!IoAllocateIrp` at `0x14001c42e`
- `ntoskrnl!IoAllocateIrp` at `0x14001c42e`

## pseudocode

```c
__int64 __fastcall GetLocalAddress(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  PIRP Irp; // rsi
  unsigned int v6; // ebx
  _QWORD *Pool2; // rax
  _QWORD *v8; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  v2 = *(_QWORD *)(a1 + 384);
  Irp = IoAllocateIrp(1, 0);
  if ( Irp )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 16, 1819173239);
    v8 = Pool2;
    if ( Pool2 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
      Pool2[1] = a1;
      *Pool2 = CtlpQueryAddrInfoCallback;
      CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)WskGetLocalAddrIrpCompletion;
      CurrentStackLocation[-1].Context = v8;
      CurrentStackLocation[-1].Control = -32;
      return (*(unsigned int (__fastcall **)(__int64, __int64, PIRP))(*(_QWORD *)v2 + 32LL))(v2, a2, Irp);
    }
    v6 = -1073741670;
    IoFreeIrp(Irp);
  }
  else
  {
    v6 = -1073741670;
  }
  CtlpQueryAddrInfoCallback(*(_QWORD *)(a1 + 8));
  return v6;
}

```

## disassembly

```asm
0x14001c414  push    rbx
0x14001c416  push    rbp
0x14001c417  push    rsi
0x14001c418  push    rdi
0x14001c419  sub     rsp, 28h
0x14001c41d  mov     rbx, [rcx+180h]
0x14001c424  mov     rbp, rdx
0x14001c427  mov     rdi, rcx
0x14001c42a  xor     edx, edx; ChargeQuota
0x14001c42c  mov     cl, 1; StackSize
0x14001c42e  call    cs:__imp_IoAllocateIrp
0x14001c435  nop     dword ptr [rax+rax+00h]
0x14001c43a  mov     rsi, rax
0x14001c43d  test    rax, rax
0x14001c440  jnz     short loc_14001C452
0x14001c442  mov     ebx, 0C000009Ah
0x14001c447  mov     rcx, [rdi+8]
0x14001c44b  call    CtlpQueryAddrInfoCallback
0x14001c450  jmp     short loc_14001C4D0
0x14001c452  mov     edx, 10h
0x14001c457  mov     r8d, 6C6E6177h
0x14001c45d  lea     ecx, [rdx+30h]
0x14001c460  call    cs:__imp_ExAllocatePool2
0x14001c467  nop     dword ptr [rax+rax+00h]
0x14001c46c  mov     rcx, rax
0x14001c46f  test    rax, rax
0x14001c472  jnz     short loc_14001C48A
0x14001c474  mov     rcx, rsi; Irp
0x14001c477  mov     ebx, 0C000009Ah
0x14001c47c  call    cs:__imp_IoFreeIrp
0x14001c483  nop     dword ptr [rax+rax+00h]
0x14001c488  jmp     short loc_14001C447
0x14001c48a  lock inc dword ptr [rdi+200h]
0x14001c491  mov     [rax+8], rdi
0x14001c495  lea     rdx, WskGetLocalAddrIrpCompletion
0x14001c49c  lea     rax, CtlpQueryAddrInfoCallback
0x14001c4a3  mov     r8, rsi
0x14001c4a6  mov     [rcx], rax
0x14001c4a9  mov     rax, [rsi+0B8h]
0x14001c4b0  mov     [rax-10h], rdx
0x14001c4b4  mov     rdx, rbp
0x14001c4b7  mov     [rax-8], rcx
0x14001c4bb  mov     rcx, rbx
0x14001c4be  mov     byte ptr [rax-45h], 0E0h
0x14001c4c2  mov     rax, [rbx]
0x14001c4c5  mov     rax, [rax+20h]
0x14001c4c9  call    _guard_dispatch_icall
0x14001c4ce  mov     ebx, eax
0x14001c4d0  mov     eax, ebx
0x14001c4d2  add     rsp, 28h
0x14001c4d6  pop     rdi
0x14001c4d7  pop     rsi
0x14001c4d8  pop     rbp
0x14001c4d9  pop     rbx
0x14001c4da  retn
```
