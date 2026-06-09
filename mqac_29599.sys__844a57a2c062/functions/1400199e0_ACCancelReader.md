# ACCancelReader

- ea: `0x1400199e0`
- end: `0x140019b59`
- name: `ACCancelReader`
- size: `377`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x1400199e0`
- `0x14001a50c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140019a70`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140019a70`
- `ntoskrnl!IofCompleteRequest` at `0x140019b35`
- `ntoskrnl!IofCompleteRequest` at `0x140019b35`
- `ntoskrnl!KeDelayExecutionThread` at `0x140019af2`
- `ntoskrnl!KeDelayExecutionThread` at `0x140019af2`
- `ntoskrnl!IoQueueWorkItem` at `0x140019b1c`
- `ntoskrnl!IoQueueWorkItem` at `0x140019b1c`

## pseudocode

```c
void __fastcall ACCancelReader(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  int v3; // edi
  struct _LIST_ENTRY *Flink; // rdx
  char v6; // di
  struct _LIST_ENTRY *Blink; // rcx
  union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *p_Tail; // rax
  struct _LIST_ENTRY *v10; // rdx
  struct _LIST_ENTRY *v11; // rcx
  PVOID v12; // rdi
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp+10h] BYREF

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  v3 = *((_DWORD *)&a2->Tail.CompletionKey + 6) >> 3;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  v6 = v3 & 1;
  if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Flink->Blink != p_ListEntry )
    goto LABEL_17;
  Blink = p_ListEntry->ListEntry.Blink;
  if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry
    || (Blink->Flink = Flink,
        Flink->Blink = Blink,
        p_ListEntry->ListEntry.Flink = 0,
        p_ListEntry->ListEntry.Blink = 0,
        p_Tail = &a2->Tail,
        v10 = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink,
        (union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *)v10->Blink != &a2->Tail)
    || (v11 = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink,
        (union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *)v11->Flink != p_Tail) )
  {
LABEL_17:
    __fastfail(3u);
  }
  v11->Flink = v10;
  v10->Blink = v11;
  p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = 0;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      10,
      &WPP_1a882a3fc31b35c4a82a1c9fc158b1b4_Traceguids,
      a2,
      a2->IoStatus.Status);
  }
  if ( v6 )
    SafeSchedCancel(a1, a2);
  if ( (*(_BYTE *)(&a2->Tail.CompletionKey + 3) & 7) != 3 )
  {
    v12 = a2->Tail.Overlay.DriverContext[2];
    if ( v12 )
    {
      while ( _InterlockedExchange((volatile __int32 *)v12 + 22, 1) )
      {
        Interval.QuadPart = -10000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      IoQueueWorkItem(*((PIO_WORKITEM *)v12 + 10), ReleaseCursorRoutine, DelayedWorkQueue, v12);
    }
  }
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x1400199e0  mov     [rsp+arg_0], rbx
0x1400199e5  mov     [rsp+arg_10], rsi
0x1400199ea  push    rdi
0x1400199eb  sub     rsp, 30h
0x1400199ef  mov     edi, [rdx+90h]
0x1400199f5  lea     rax, [rdx+0A8h]
0x1400199fc  shr     edi, 3
0x1400199ff  mov     rbx, rdx
0x140019a02  mov     rdx, [rax]
0x140019a05  and     dil, 1
0x140019a09  mov     rsi, rcx
0x140019a0c  cmp     [rdx+8], rax
0x140019a10  jnz     loc_140019B52
0x140019a16  mov     rcx, [rax+8]
0x140019a1a  cmp     [rcx], rax
0x140019a1d  jnz     loc_140019B52
0x140019a23  mov     [rcx], rdx
0x140019a26  mov     [rdx+8], rcx
0x140019a2a  mov     qword ptr [rax], 0
0x140019a31  mov     qword ptr [rax+8], 0
0x140019a39  lea     rax, [rbx+78h]
0x140019a3d  mov     rdx, [rax]
0x140019a40  cmp     [rdx+8], rax
0x140019a44  jnz     loc_140019B52
0x140019a4a  mov     rcx, [rax+8]
0x140019a4e  cmp     [rcx], rax
0x140019a51  jnz     loc_140019B52
0x140019a57  mov     [rcx], rdx
0x140019a5a  mov     [rdx+8], rcx
0x140019a5e  mov     qword ptr [rax], 0
0x140019a65  mov     qword ptr [rax+8], 0
0x140019a6d  mov     cl, [rbx+45h]; Irql
0x140019a70  call    cs:__imp_IoReleaseCancelSpinLock
0x140019a77  nop     dword ptr [rax+rax+00h]
0x140019a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a83  lea     rax, WPP_GLOBAL_Control
0x140019a8a  cmp     rcx, rax
0x140019a8d  jz      short loc_140019AB5
0x140019a8f  mov     eax, [rcx+6Ch]
0x140019a92  test    al, 4
0x140019a94  jz      short loc_140019AB5
0x140019a96  mov     eax, [rbx+30h]
0x140019a99  lea     r8, WPP_1a882a3fc31b35c4a82a1c9fc158b1b4_Traceguids
0x140019aa0  mov     rcx, [rcx+58h]
0x140019aa4  mov     edx, 0Ah
0x140019aa9  mov     r9, rbx
0x140019aac  mov     [rsp+38h+var_18], eax
0x140019ab0  call    WPP_SF_qD
0x140019ab5  test    dil, dil
0x140019ab8  jz      short loc_140019AC5
0x140019aba  mov     rdx, rbx
0x140019abd  mov     rcx, rsi
0x140019ac0  call    SafeSchedCancel
0x140019ac5  mov     eax, [rbx+90h]
0x140019acb  and     eax, 7
0x140019ace  cmp     al, 3
0x140019ad0  jz      short loc_140019B28
0x140019ad2  mov     rdi, [rbx+88h]
0x140019ad9  test    rdi, rdi
0x140019adc  jz      short loc_140019B28
0x140019ade  jmp     short loc_140019AFE
0x140019ae0  lea     r8, [rsp+38h+Interval]; Interval
0x140019ae5  mov     qword ptr [rsp+38h+Interval], 0FFFFFFFFFFFFD8F0h
0x140019aee  xor     edx, edx; Alertable
0x140019af0  xor     ecx, ecx; WaitMode
0x140019af2  call    cs:__imp_KeDelayExecutionThread
0x140019af9  nop     dword ptr [rax+rax+00h]
0x140019afe  mov     eax, 1
0x140019b03  xchg    eax, [rdi+58h]
0x140019b06  test    eax, eax
0x140019b08  jnz     short loc_140019AE0
0x140019b0a  mov     rcx, [rdi+50h]; IoWorkItem
0x140019b0e  lea     r8d, [rax+1]; QueueType
0x140019b12  mov     r9, rdi; Context
0x140019b15  lea     rdx, ReleaseCursorRoutine; WorkerRoutine
0x140019b1c  call    cs:__imp_IoQueueWorkItem
0x140019b23  nop     dword ptr [rax+rax+00h]
0x140019b28  xor     edx, edx; PriorityBoost
0x140019b2a  mov     qword ptr [rbx+38h], 0
0x140019b32  mov     rcx, rbx; Irp
0x140019b35  call    cs:__imp_IofCompleteRequest
0x140019b3c  nop     dword ptr [rax+rax+00h]
0x140019b41  mov     rbx, [rsp+38h+arg_0]
0x140019b46  mov     rsi, [rsp+38h+arg_10]
0x140019b4b  add     rsp, 30h
0x140019b4f  pop     rdi
0x140019b50  retn
0x140019b52  mov     ecx, 3
0x140019b57  int     29h; Win8: RtlFailFast(ecx)
```
