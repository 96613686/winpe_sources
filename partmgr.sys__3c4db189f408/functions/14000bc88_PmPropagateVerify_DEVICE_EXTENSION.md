# PmPropagateVerify(_DEVICE_EXTENSION *)

- ea: `0x14000bc88`
- end: `0x14000bd71`
- name: `?PmPropagateVerify@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `233`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400021c0`

## callees

- `0x14000ae88`
- `0x14000ae94`
- `0x14000bc88`
- `0x14000cb34`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000bd59`
- `ntoskrnl!IofCallDriver` at `0x14000bd59`
- `ntoskrnl!IoAllocateIrp` at `0x14000bd02`
- `ntoskrnl!IoAllocateIrp` at `0x14000bd02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bced`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bced`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bc9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bc9e`

## pseudocode

```c
void __fastcall PmPropagateVerify(struct _DEVICE_EXTENSION *a1)
{
  KIRQL v2; // al
  char *v3; // r9
  KIRQL v4; // r10
  char *i; // r8
  int NoFence; // eax
  __int64 v7; // r8
  char **v8; // r8
  PIRP Irp; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v11; // rcx

  PmInvalidatePartitionTableCache((KSPIN_LOCK *)a1);
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  v3 = (char *)a1 + 896;
  v4 = v2;
  for ( i = (char *)*((_QWORD *)a1 + 112); i != v3; i = *v8 )
  {
    NoFence = ScReadNoFence((unsigned int *)(*((_QWORD *)i - 17) + 48LL));
    ScWriteNoFence((unsigned int *)(*(_QWORD *)(v7 - 136) + 48LL), NoFence | 2);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v4);
  Irp = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)a1 + 2) + 76LL), 0);
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].Parameters.Read.Length = 0;
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 459783;
    v11 = Irp->Tail.Overlay.CurrentStackLocation;
    Irp->RequestorMode = 0;
    Irp->AssociatedIrp.MasterIrp = 0;
    v11[-1].CompletionRoutine = PmPropagateVerifyCompletion;
    v11[-1].Context = 0;
    v11[-1].Control = -32;
    IofCallDriver(*((PDEVICE_OBJECT *)a1 + 2), Irp);
  }
}

```

## disassembly

```asm
0x14000bc88  mov     [rsp+arg_0], rbx
0x14000bc8d  push    rdi
0x14000bc8e  sub     rsp, 20h
0x14000bc92  mov     rbx, rcx
0x14000bc95  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14000bc9a  lea     rcx, [rbx+70h]; SpinLock
0x14000bc9e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bca5  nop     dword ptr [rax+rax+00h]
0x14000bcaa  lea     r9, [rbx+380h]
0x14000bcb1  mov     r10b, al
0x14000bcb4  mov     r8, [r9]
0x14000bcb7  jmp     short loc_14000BCE1
0x14000bcb9  mov     rcx, [r8-88h]
0x14000bcc0  add     rcx, 30h ; '0'; unsigned int *
0x14000bcc4  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14000bcc9  mov     rcx, [r8-88h]
0x14000bcd0  or      eax, 2
0x14000bcd3  mov     edx, eax; unsigned int
0x14000bcd5  add     rcx, 30h ; '0'; unsigned int *
0x14000bcd9  call    ?ScWriteNoFence@@YAXPEAKK@Z; ScWriteNoFence(ulong *,ulong)
0x14000bcde  mov     r8, [r8]
0x14000bce1  cmp     r8, r9
0x14000bce4  jnz     short loc_14000BCB9
0x14000bce6  mov     dl, r10b; NewIrql
0x14000bce9  lea     rcx, [rbx+70h]; SpinLock
0x14000bced  call    cs:__imp_KeReleaseSpinLock
0x14000bcf4  nop     dword ptr [rax+rax+00h]
0x14000bcf9  mov     rcx, [rbx+10h]
0x14000bcfd  xor     edx, edx; ChargeQuota
0x14000bcff  mov     cl, [rcx+4Ch]; StackSize
0x14000bd02  call    cs:__imp_IoAllocateIrp
0x14000bd09  nop     dword ptr [rax+rax+00h]
0x14000bd0e  xor     r8d, r8d
0x14000bd11  test    rax, rax
0x14000bd14  jz      short loc_14000BD65
0x14000bd16  mov     rcx, [rax+0B8h]
0x14000bd1d  lea     rdx, ?PmPropagateVerifyCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PmPropagateVerifyCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14000bd24  mov     byte ptr [rcx-48h], 0Eh
0x14000bd28  mov     [rcx-40h], r8d
0x14000bd2c  mov     [rcx-38h], r8d
0x14000bd30  mov     dword ptr [rcx-30h], 70407h
0x14000bd37  mov     rcx, [rax+0B8h]
0x14000bd3e  mov     [rax+40h], r8b
0x14000bd42  mov     [rax+18h], r8
0x14000bd46  mov     [rcx-10h], rdx
0x14000bd4a  mov     rdx, rax; Irp
0x14000bd4d  mov     [rcx-8], r8
0x14000bd51  mov     byte ptr [rcx-45h], 0E0h
0x14000bd55  mov     rcx, [rbx+10h]; DeviceObject
0x14000bd59  call    cs:__imp_IofCallDriver
0x14000bd60  nop     dword ptr [rax+rax+00h]
0x14000bd65  mov     rbx, [rsp+28h+arg_0]
0x14000bd6a  add     rsp, 20h
0x14000bd6e  pop     rdi
0x14000bd6f  retn
```
