# PmQueryRemoveDevice(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000bda4`
- end: `0x14000beab`
- name: `?PmQueryRemoveDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `263`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022800`

## callees

- `0x14000a014`
- `0x14000bda4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000be52`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000be52`
- `ntoskrnl!IofCallDriver` at `0x14000be77`
- `ntoskrnl!IofCallDriver` at `0x14000be77`
- `ntoskrnl!IofCompleteRequest` at `0x14000be8f`
- `ntoskrnl!IofCompleteRequest` at `0x14000be8f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000be2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000be2a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bdbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bdbe`

## string_xrefs

- `0x14000bddf`: `PmQueryRemoveDevice`

## pseudocode

```c
__int64 __fastcall PmQueryRemoveDevice(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rbp
  int Status; // edi
  struct _LIST_ENTRY *v5; // rsi
  KIRQL v6; // r15
  struct _LIST_ENTRY *v7; // rcx

  DeviceExtension = (char *)a1->DeviceExtension;
  Status = 0;
  v5 = (struct _LIST_ENTRY *)(DeviceExtension + 688);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeviceExtension + 14);
  if ( v5->Flink != v5
    || (*((_DWORD *)DeviceExtension + 129) |= 0x2000000u,
        Status = PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)DeviceExtension, "PmQueryRemoveDevice"),
        Status >= 0) )
  {
    v7 = (struct _LIST_ENTRY *)*((_QWORD *)DeviceExtension + 87);
    if ( v7->Flink != v5 )
      __fastfail(3u);
    a2->Tail.Overlay.ListEntry.Flink = v5;
    a2->Tail.Overlay.ListEntry.Blink = v7;
    v7->Flink = &a2->Tail.Overlay.ListEntry;
    *((_QWORD *)DeviceExtension + 87) = &a2->Tail.Overlay.ListEntry;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v6);
  if ( Status >= 0 )
  {
    KeWaitForSingleObject(DeviceExtension + 824, Executive, 0, 0, 0);
    Status = a2->IoStatus.Status;
    if ( Status < 0 )
    {
      a2->IoStatus.Status = Status;
      IofCompleteRequest(a2, 0);
    }
    else
    {
      ++a2->CurrentLocation;
      ++a2->Tail.Overlay.CurrentStackLocation;
      return (unsigned int)IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000bda4  push    rbx
0x14000bda6  push    rbp
0x14000bda7  push    rsi
0x14000bda8  push    rdi
0x14000bda9  push    r14
0x14000bdab  push    r15
0x14000bdad  sub     rsp, 38h
0x14000bdb1  mov     rbp, [rcx+40h]
0x14000bdb5  mov     rbx, rdx
0x14000bdb8  xor     edi, edi
0x14000bdba  lea     rcx, [rbp+70h]; SpinLock
0x14000bdbe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bdc5  nop     dword ptr [rax+rax+00h]
0x14000bdca  lea     rsi, [rbp+2B0h]
0x14000bdd1  mov     r15b, al
0x14000bdd4  cmp     [rsi], rsi
0x14000bdd7  jnz     short loc_14000BDFE
0x14000bdd9  mov     eax, [rbp+204h]
0x14000bddf  lea     rdx, aPmqueryremoved; "PmQueryRemoveDevice"
0x14000bde6  bts     eax, 19h
0x14000bdea  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14000bded  mov     [rbp+204h], eax
0x14000bdf3  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000bdf8  mov     edi, eax
0x14000bdfa  test    eax, eax
0x14000bdfc  js      short loc_14000BE23
0x14000bdfe  mov     rcx, [rsi+8]
0x14000be02  cmp     [rcx], rsi
0x14000be05  jz      short loc_14000BE0E
0x14000be07  mov     ecx, 3
0x14000be0c  int     29h; Win8: RtlFailFast(ecx)
0x14000be0e  lea     rax, [rbx+0A8h]
0x14000be15  mov     [rax], rsi
0x14000be18  mov     [rax+8], rcx
0x14000be1c  mov     [rcx], rax
0x14000be1f  mov     [rsi+8], rax
0x14000be23  mov     dl, r15b; NewIrql
0x14000be26  lea     rcx, [rbp+70h]; SpinLock
0x14000be2a  call    cs:__imp_KeReleaseSpinLock
0x14000be31  nop     dword ptr [rax+rax+00h]
0x14000be36  test    edi, edi
0x14000be38  js      short loc_14000BE9B
0x14000be3a  lea     rcx, [rbp+338h]; Object
0x14000be41  mov     [rsp+68h+Timeout], 0; Timeout
0x14000be4a  xor     r9d, r9d; Alertable
0x14000be4d  xor     r8d, r8d; WaitMode
0x14000be50  xor     edx, edx; WaitReason
0x14000be52  call    cs:__imp_KeWaitForSingleObject
0x14000be59  nop     dword ptr [rax+rax+00h]
0x14000be5e  mov     edi, [rbx+30h]
0x14000be61  test    edi, edi
0x14000be63  js      short loc_14000BE87
0x14000be65  inc     byte ptr [rbx+43h]
0x14000be68  mov     rdx, rbx; Irp
0x14000be6b  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000be73  mov     rcx, [rbp+10h]; DeviceObject
0x14000be77  call    cs:__imp_IofCallDriver
0x14000be7e  nop     dword ptr [rax+rax+00h]
0x14000be83  mov     edi, eax
0x14000be85  jmp     short loc_14000BE9B
0x14000be87  xor     edx, edx; PriorityBoost
0x14000be89  mov     [rbx+30h], edi
0x14000be8c  mov     rcx, rbx; Irp
0x14000be8f  call    cs:__imp_IofCompleteRequest
0x14000be96  nop     dword ptr [rax+rax+00h]
0x14000be9b  mov     eax, edi
0x14000be9d  add     rsp, 38h
0x14000bea1  pop     r15
0x14000bea3  pop     r14
0x14000bea5  pop     rdi
0x14000bea6  pop     rsi
0x14000bea7  pop     rbp
0x14000bea8  pop     rbx
0x14000bea9  retn
```
