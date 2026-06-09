# WskOpenConnectedSocketCompletion

- ea: `0x14001ff90`
- end: `0x1400200f7`
- name: `WskOpenConnectedSocketCompletion`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004830`
- `0x14001ff90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140020005`
- `ntoskrnl!KeSetEvent` at `0x140020005`
- `ntoskrnl!IoFreeIrp` at `0x140020056`
- `ntoskrnl!IoFreeIrp` at `0x140020056`
- `ntoskrnl!IoAllocateIrp` at `0x14001ffc4`
- `ntoskrnl!IoAllocateIrp` at `0x14001ffc4`

## pseudocode

```c
__int64 __fastcall WskOpenConnectedSocketCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 Status; // r8
  char v6; // si
  void (__fastcall ***Information)(_QWORD, _QWORD, __int64, __int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD, PIRP); // r14
  PIRP Irp; // rax
  void (__fastcall *v9)(_QWORD, __int64, __int64); // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PIRP v12; // [rsp+48h] [rbp-50h]
  __int128 v13; // [rsp+60h] [rbp-38h] BYREF

  Status = (unsigned int)a2->IoStatus.Status;
  v6 = 1;
  v13 = 0;
  if ( (int)Status >= 0 )
  {
    Information = (void (__fastcall ***)(_QWORD, _QWORD, __int64, __int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD, PIRP))a2->IoStatus.Information;
    *(_QWORD *)(a3 + 384) = Information;
    Irp = IoAllocateIrp(1, 0);
    if ( Irp )
    {
      v12 = Irp;
      DWORD2(v13) = 192;
      *(_QWORD *)&v13 = &NPI_WSK_INTERFACE_ID;
      CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskConnectControlCompletion;
      CurrentStackLocation[-1].Context = (PVOID)a3;
      CurrentStackLocation[-1].Control = -32;
      (**Information)(Information, 0, 16386, 0xFFFF, 16, &v13, 0, 0, 0, v12);
      v6 = 0;
      goto LABEL_6;
    }
    Status = 3221225626LL;
  }
  v9 = *(void (__fastcall **)(_QWORD, __int64, __int64))(a3 + 40);
  if ( v9 )
    v9(*(_QWORD *)(a3 + 8), a3, Status);
LABEL_6:
  KeSetEvent((PRKEVENT)(a3 + 400), 2, 0);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 512), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a3 + 520))(a3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 512), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a3 + 520))(a3);
  }
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001ff90  push    rbx
0x14001ff92  push    rsi
0x14001ff93  push    rdi
0x14001ff94  push    r14
0x14001ff96  sub     rsp, 78h
0x14001ff9a  mov     rbx, r8
0x14001ff9d  xorps   xmm0, xmm0
0x14001ffa0  mov     r8d, [rdx+30h]
0x14001ffa4  mov     rdi, rdx
0x14001ffa7  mov     sil, 1
0x14001ffaa  movups  [rsp+98h+var_38], xmm0
0x14001ffaf  test    r8d, r8d
0x14001ffb2  js      short loc_14001FFE2
0x14001ffb4  mov     r14, [rdx+38h]
0x14001ffb8  mov     cl, sil; StackSize
0x14001ffbb  xor     edx, edx; ChargeQuota
0x14001ffbd  mov     [rbx+180h], r14
0x14001ffc4  call    cs:__imp_IoAllocateIrp
0x14001ffcb  nop     dword ptr [rax+rax+00h]
0x14001ffd0  mov     rcx, rax
0x14001ffd3  test    rax, rax
0x14001ffd6  jnz     loc_140020072
0x14001ffdc  mov     r8d, 0C000009Ah
0x14001ffe2  mov     rax, [rbx+28h]
0x14001ffe6  test    rax, rax
0x14001ffe9  jz      short loc_14001FFF7
0x14001ffeb  mov     rcx, [rbx+8]
0x14001ffef  mov     rdx, rbx
0x14001fff2  call    _guard_dispatch_icall
0x14001fff7  xor     r8d, r8d; Wait
0x14001fffa  lea     rcx, [rbx+190h]; Event
0x140020001  lea     edx, [r8+2]; Increment
0x140020005  call    cs:__imp_KeSetEvent
0x14002000c  nop     dword ptr [rax+rax+00h]
0x140020011  test    sil, sil
0x140020014  jz      short loc_140020053
0x140020016  or      esi, 0FFFFFFFFh
0x140020019  mov     eax, esi
0x14002001b  lock xadd [rbx+200h], eax
0x140020023  add     eax, esi
0x140020025  jnz     short loc_140020036
0x140020027  mov     rax, [rbx+208h]
0x14002002e  mov     rcx, rbx
0x140020031  call    _guard_dispatch_icall
0x140020036  mov     eax, esi
0x140020038  lock xadd [rbx+200h], eax
0x140020040  add     eax, esi
0x140020042  jnz     short loc_140020053
0x140020044  mov     rax, [rbx+208h]
0x14002004b  mov     rcx, rbx
0x14002004e  call    _guard_dispatch_icall
0x140020053  mov     rcx, rdi; Irp
0x140020056  call    cs:__imp_IoFreeIrp
0x14002005d  nop     dword ptr [rax+rax+00h]
0x140020062  mov     eax, 0C0000016h
0x140020067  add     rsp, 78h
0x14002006b  pop     r14
0x14002006d  pop     rdi
0x14002006e  pop     rsi
0x14002006f  pop     rbx
0x140020070  retn
0x140020072  mov     [rsp+98h+var_50], rcx
0x140020077  lea     rdx, WskConnectControlCompletion
0x14002007e  mov     dword ptr [rsp+98h+var_38+8], 0C0h
0x140020086  lea     rax, NPI_WSK_INTERFACE_ID
0x14002008d  mov     qword ptr [rsp+98h+var_38], rax
0x140020092  mov     r9d, 0FFFFh
0x140020098  mov     rax, [rcx+0B8h]
0x14002009f  mov     r8d, 4002h
0x1400200a5  mov     [rsp+98h+var_58], 0
0x1400200ae  lea     rcx, [rsp+98h+var_38]
0x1400200b3  mov     [rsp+98h+var_60], 0
0x1400200bc  mov     [rsp+98h+var_68], 0
0x1400200c5  mov     [rax-10h], rdx
0x1400200c9  xor     edx, edx
0x1400200cb  mov     [rax-8], rbx
0x1400200cf  mov     byte ptr [rax-45h], 0E0h
0x1400200d3  mov     rax, [r14]
0x1400200d6  mov     [rsp+98h+var_70], rcx
0x1400200db  mov     rcx, r14
0x1400200de  mov     [rsp+98h+var_78], 10h
0x1400200e7  mov     rax, [rax]
0x1400200ea  call    _guard_dispatch_icall
0x1400200ef  xor     sil, sil
0x1400200f2  jmp     loc_14001FFF7
```
