# BrbSendConnectDeny

- ea: `0x14000dc00`
- end: `0x14000dd21`
- name: `BrbSendConnectDeny`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d4b0`

## callees

- `0x14000dc00`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000dd07`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000dd07`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000dc3a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000dc3a`
- `ntoskrnl!IofCallDriver` at `0x14000dcdd`
- `ntoskrnl!IofCallDriver` at `0x14000dcdd`
- `ntoskrnl!IoFreeIrp` at `0x14000dcee`
- `ntoskrnl!IoFreeIrp` at `0x14000dcee`
- `ntoskrnl!IoAllocateIrp` at `0x14000dc57`
- `ntoskrnl!IoAllocateIrp` at `0x14000dc57`

## string_xrefs

- `0x14000dc26`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
void __fastcall BrbSendConnectDeny(__int64 a1, _QWORD *a2, __int16 a3)
{
  PIRP Irp; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  _IO_STACK_LOCATION *v10; // rax

  if ( IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(a1 + 40),
         &BrbDenyConnectComplete,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c",
         0x2Eu,
         0x20u) >= 0 )
  {
    Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 88) + 76LL), 0);
    if ( Irp )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 312))(531, 1111647826);
      v8 = v7;
      if ( v7 )
      {
        *(_QWORD *)(v7 + 128) = a2[1];
        *(_QWORD *)(v7 + 112) = *a2;
        *(_WORD *)(v7 + 122) = 0;
        *(_WORD *)(v7 + 120) = a3;
        *(_QWORD *)(v7 + 72) = a1;
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].Parameters.WMI.ProviderId = v7;
        CurrentStackLocation[-1].MajorFunction = 15;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
        v10 = Irp->Tail.Overlay.CurrentStackLocation;
        v10[-1].Context = (void *)v8;
        v10[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&BrbDenyConnectComplete;
        v10[-1].Control = -32;
        IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 88), Irp);
        return;
      }
      IoFreeIrp(Irp);
    }
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), &BrbDenyConnectComplete, 0x20u);
  }
}

```

## disassembly

```asm
0x14000dc00  push    rbx
0x14000dc02  push    rbp
0x14000dc03  push    rsi
0x14000dc04  push    rdi
0x14000dc05  push    r14
0x14000dc07  push    r15
0x14000dc09  sub     rsp, 38h
0x14000dc0d  movzx   ebp, r8w
0x14000dc11  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14000dc19  mov     r14, rdx
0x14000dc1c  lea     r15, BrbDenyConnectComplete
0x14000dc23  mov     rdi, rcx
0x14000dc26  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000dc2d  mov     rdx, r15; Tag
0x14000dc30  mov     r9d, 2Eh ; '.'; Line
0x14000dc36  add     rcx, 28h ; '('; RemoveLock
0x14000dc3a  call    cs:__imp_IoAcquireRemoveLockEx
0x14000dc41  nop     dword ptr [rax+rax+00h]
0x14000dc46  test    eax, eax
0x14000dc48  js      loc_14000DD13
0x14000dc4e  mov     rcx, [rdi+58h]
0x14000dc52  xor     edx, edx; ChargeQuota
0x14000dc54  mov     cl, [rcx+4Ch]; StackSize
0x14000dc57  call    cs:__imp_IoAllocateIrp
0x14000dc5e  nop     dword ptr [rax+rax+00h]
0x14000dc63  mov     rbx, rax
0x14000dc66  test    rax, rax
0x14000dc69  jz      loc_14000DCFA
0x14000dc6f  mov     rax, [rdi+138h]
0x14000dc76  mov     edx, 42426652h
0x14000dc7b  mov     ecx, 213h
0x14000dc80  call    _guard_dispatch_icall
0x14000dc85  mov     rdx, rax
0x14000dc88  test    rax, rax
0x14000dc8b  jz      short loc_14000DCEB
0x14000dc8d  mov     rcx, [r14+8]
0x14000dc91  mov     [rax+80h], rcx
0x14000dc98  mov     rcx, [r14]
0x14000dc9b  mov     [rax+70h], rcx
0x14000dc9f  xor     ecx, ecx
0x14000dca1  mov     [rax+7Ah], cx
0x14000dca5  mov     [rax+78h], bp
0x14000dca9  mov     [rax+48h], rdi
0x14000dcad  mov     rcx, [rbx+0B8h]
0x14000dcb4  mov     [rcx-40h], rax
0x14000dcb8  mov     byte ptr [rcx-48h], 0Fh
0x14000dcbc  mov     dword ptr [rcx-30h], 410003h
0x14000dcc3  mov     rax, [rbx+0B8h]
0x14000dcca  mov     [rax-8], rdx
0x14000dcce  mov     rdx, rbx; Irp
0x14000dcd1  mov     [rax-10h], r15
0x14000dcd5  mov     byte ptr [rax-45h], 0E0h
0x14000dcd9  mov     rcx, [rdi+58h]; DeviceObject
0x14000dcdd  call    cs:__imp_IofCallDriver
0x14000dce4  nop     dword ptr [rax+rax+00h]
0x14000dce9  jmp     short loc_14000DD13
0x14000dceb  mov     rcx, rbx; Irp
0x14000dcee  call    cs:__imp_IoFreeIrp
0x14000dcf5  nop     dword ptr [rax+rax+00h]
0x14000dcfa  mov     r8d, 20h ; ' '; RemlockSize
0x14000dd00  lea     rcx, [rdi+28h]; RemoveLock
0x14000dd04  mov     rdx, r15; Tag
0x14000dd07  call    cs:__imp_IoReleaseRemoveLockEx
0x14000dd0e  nop     dword ptr [rax+rax+00h]
0x14000dd13  add     rsp, 38h
0x14000dd17  pop     r15
0x14000dd19  pop     r14
0x14000dd1b  pop     rdi
0x14000dd1c  pop     rsi
0x14000dd1d  pop     rbp
0x14000dd1e  pop     rbx
0x14000dd1f  retn
```
