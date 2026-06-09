# WskOpenConnectedSocketCompletion

- ea: `0x14001d6a0`
- end: `0x14001d807`
- name: `WskOpenConnectedSocketCompletion`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007710`
- `0x14001d6a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001d715`
- `ntoskrnl!KeSetEvent` at `0x14001d715`
- `ntoskrnl!IoFreeIrp` at `0x14001d766`
- `ntoskrnl!IoFreeIrp` at `0x14001d766`
- `ntoskrnl!IoAllocateIrp` at `0x14001d6d4`
- `ntoskrnl!IoAllocateIrp` at `0x14001d6d4`

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
0x14001d6a0  push    rbx
0x14001d6a2  push    rsi
0x14001d6a3  push    rdi
0x14001d6a4  push    r14
0x14001d6a6  sub     rsp, 78h
0x14001d6aa  mov     rbx, r8
0x14001d6ad  xorps   xmm0, xmm0
0x14001d6b0  mov     r8d, [rdx+30h]
0x14001d6b4  mov     rdi, rdx
0x14001d6b7  mov     sil, 1
0x14001d6ba  movups  [rsp+98h+var_38], xmm0
0x14001d6bf  test    r8d, r8d
0x14001d6c2  js      short loc_14001D6F2
0x14001d6c4  mov     r14, [rdx+38h]
0x14001d6c8  mov     cl, sil; StackSize
0x14001d6cb  xor     edx, edx; ChargeQuota
0x14001d6cd  mov     [rbx+180h], r14
0x14001d6d4  call    cs:__imp_IoAllocateIrp
0x14001d6db  nop     dword ptr [rax+rax+00h]
0x14001d6e0  mov     rcx, rax
0x14001d6e3  test    rax, rax
0x14001d6e6  jnz     loc_14001D782
0x14001d6ec  mov     r8d, 0C000009Ah
0x14001d6f2  mov     rax, [rbx+28h]
0x14001d6f6  test    rax, rax
0x14001d6f9  jz      short loc_14001D707
0x14001d6fb  mov     rcx, [rbx+8]
0x14001d6ff  mov     rdx, rbx
0x14001d702  call    _guard_dispatch_icall
0x14001d707  xor     r8d, r8d; Wait
0x14001d70a  lea     rcx, [rbx+190h]; Event
0x14001d711  lea     edx, [r8+2]; Increment
0x14001d715  call    cs:__imp_KeSetEvent
0x14001d71c  nop     dword ptr [rax+rax+00h]
0x14001d721  test    sil, sil
0x14001d724  jz      short loc_14001D763
0x14001d726  or      esi, 0FFFFFFFFh
0x14001d729  mov     eax, esi
0x14001d72b  lock xadd [rbx+200h], eax
0x14001d733  add     eax, esi
0x14001d735  jnz     short loc_14001D746
0x14001d737  mov     rax, [rbx+208h]
0x14001d73e  mov     rcx, rbx
0x14001d741  call    _guard_dispatch_icall
0x14001d746  mov     eax, esi
0x14001d748  lock xadd [rbx+200h], eax
0x14001d750  add     eax, esi
0x14001d752  jnz     short loc_14001D763
0x14001d754  mov     rax, [rbx+208h]
0x14001d75b  mov     rcx, rbx
0x14001d75e  call    _guard_dispatch_icall
0x14001d763  mov     rcx, rdi; Irp
0x14001d766  call    cs:__imp_IoFreeIrp
0x14001d76d  nop     dword ptr [rax+rax+00h]
0x14001d772  mov     eax, 0C0000016h
0x14001d777  add     rsp, 78h
0x14001d77b  pop     r14
0x14001d77d  pop     rdi
0x14001d77e  pop     rsi
0x14001d77f  pop     rbx
0x14001d780  retn
0x14001d782  mov     [rsp+98h+var_50], rcx
0x14001d787  lea     rdx, WskConnectControlCompletion
0x14001d78e  mov     dword ptr [rsp+98h+var_38+8], 0C0h
0x14001d796  lea     rax, NPI_WSK_INTERFACE_ID
0x14001d79d  mov     qword ptr [rsp+98h+var_38], rax
0x14001d7a2  mov     r9d, 0FFFFh
0x14001d7a8  mov     rax, [rcx+0B8h]
0x14001d7af  mov     r8d, 4002h
0x14001d7b5  mov     [rsp+98h+var_58], 0
0x14001d7be  lea     rcx, [rsp+98h+var_38]
0x14001d7c3  mov     [rsp+98h+var_60], 0
0x14001d7cc  mov     [rsp+98h+var_68], 0
0x14001d7d5  mov     [rax-10h], rdx
0x14001d7d9  xor     edx, edx
0x14001d7db  mov     [rax-8], rbx
0x14001d7df  mov     byte ptr [rax-45h], 0E0h
0x14001d7e3  mov     rax, [r14]
0x14001d7e6  mov     [rsp+98h+var_70], rcx
0x14001d7eb  mov     rcx, r14
0x14001d7ee  mov     [rsp+98h+var_78], 10h
0x14001d7f7  mov     rax, [rax]
0x14001d7fa  call    _guard_dispatch_icall
0x14001d7ff  xor     sil, sil
0x14001d802  jmp     loc_14001D707
```
