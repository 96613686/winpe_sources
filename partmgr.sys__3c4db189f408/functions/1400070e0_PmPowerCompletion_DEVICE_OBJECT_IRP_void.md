# PmPowerCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400070e0`
- end: `0x1400071b1`
- name: `?PmPowerCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400070e0`
- `0x14000a014`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007195`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007195`
- `ntoskrnl!PoSetPowerState` at `0x140007136`
- `ntoskrnl!PoSetPowerState` at `0x140007136`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000717f`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000717f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007170`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007170`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007112`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007112`

## string_xrefs

- `0x14000715d`: `PmPowerCompletion`

## pseudocode

```c
__int64 __fastcall PmPowerCompletion(PDEVICE_OBJECT DeviceObject, PIRP Irp, void *a3)
{
  char *DeviceExtension; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  KIRQL v7; // al
  KIRQL v8; // r15

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( Irp->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  if ( Irp->IoStatus.Status >= 0 )
  {
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeviceExtension + 14);
    *((_DWORD *)DeviceExtension + 152) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    v8 = v7;
    if ( PoSetPowerState(DeviceObject, DevicePowerState, CurrentStackLocation->Parameters.Power.State).SystemState != *((_DWORD *)DeviceExtension + 152) )
    {
      *((_DWORD *)DeviceExtension + 129) |= 0x1000000u;
      PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)DeviceExtension, "PmPowerCompletion");
    }
    KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v8);
  }
  PoStartNextPowerIrp(Irp);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), 0, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x1400070e0  push    rbx
0x1400070e2  push    rbp
0x1400070e3  push    rsi
0x1400070e4  push    rdi
0x1400070e5  push    r14
0x1400070e7  push    r15
0x1400070e9  sub     rsp, 28h
0x1400070ed  cmp     byte ptr [rdx+41h], 0
0x1400070f1  mov     rdi, rdx
0x1400070f4  mov     rbx, [rcx+40h]
0x1400070f8  mov     rbp, rcx
0x1400070fb  mov     rsi, [rdx+0B8h]
0x140007102  jz      short loc_140007108
0x140007104  or      byte ptr [rsi+3], 1
0x140007108  cmp     dword ptr [rdx+30h], 0
0x14000710c  jl      short loc_14000717C
0x14000710e  lea     rcx, [rbx+70h]; SpinLock
0x140007112  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007119  nop     dword ptr [rax+rax+00h]
0x14000711e  mov     ecx, [rsi+18h]
0x140007121  mov     edx, 1; Type
0x140007126  mov     [rbx+260h], ecx
0x14000712c  mov     r15b, al
0x14000712f  mov     r8d, [rsi+18h]; State
0x140007133  mov     rcx, rbp; DeviceObject
0x140007136  call    cs:__imp_PoSetPowerState
0x14000713d  nop     dword ptr [rax+rax+00h]
0x140007142  cmp     eax, [rbx+260h]
0x140007148  jz      short loc_140007169
0x14000714a  mov     edx, [rbx+204h]
0x140007150  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007153  bts     edx, 18h
0x140007157  mov     [rbx+204h], edx
0x14000715d  lea     rdx, aPmpowercomplet; "PmPowerCompletion"
0x140007164  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x140007169  mov     dl, r15b; NewIrql
0x14000716c  lea     rcx, [rbx+70h]; SpinLock
0x140007170  call    cs:__imp_KeReleaseSpinLock
0x140007177  nop     dword ptr [rax+rax+00h]
0x14000717c  mov     rcx, rdi; Irp
0x14000717f  call    cs:__imp_PoStartNextPowerIrp
0x140007186  nop     dword ptr [rax+rax+00h]
0x14000718b  xor     edx, edx; Tag
0x14000718d  lea     rcx, [rbx+78h]; RemoveLock
0x140007191  lea     r8d, [rdx+20h]; RemlockSize
0x140007195  call    cs:__imp_IoReleaseRemoveLockEx
0x14000719c  nop     dword ptr [rax+rax+00h]
0x1400071a1  xor     eax, eax
0x1400071a3  add     rsp, 28h
0x1400071a7  pop     r15
0x1400071a9  pop     r14
0x1400071ab  pop     rdi
0x1400071ac  pop     rsi
0x1400071ad  pop     rbp
0x1400071ae  pop     rbx
0x1400071af  retn
```
