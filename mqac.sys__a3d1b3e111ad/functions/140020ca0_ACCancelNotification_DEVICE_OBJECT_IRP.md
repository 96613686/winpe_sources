# ACCancelNotification(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140020ca0`
- end: `0x140020d7a`
- name: `?ACCancelNotification@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `218`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140020ca0`
- `0x140020f9c`
- `0x1400214b4`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140020ce9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140020ce9`
- `ntoskrnl!IofCompleteRequest` at `0x140020d5d`
- `ntoskrnl!IofCompleteRequest` at `0x140020d5d`

## pseudocode

```c
void __fastcall ACCancelNotification(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx
  __int64 v7; // r8

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  p_ListEntry->ListEntry.Flink = 0;
  p_ListEntry->ListEntry.Blink = 0;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qdD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      17,
      v7,
      a2,
      a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >> 3,
      a2->UserBuffer);
  }
  ACpCompleteStorageCancelled(a1);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x140020ca0  push    rbx
0x140020ca2  push    rbp
0x140020ca3  push    rsi
0x140020ca4  push    rdi
0x140020ca5  sub     rsp, 38h
0x140020ca9  lea     rax, [rdx+0A8h]
0x140020cb0  mov     rbx, rdx
0x140020cb3  mov     r8, [rax]
0x140020cb6  mov     rbp, rcx
0x140020cb9  cmp     [r8+8], rax
0x140020cbd  jnz     loc_140020D73
0x140020cc3  mov     rdx, [rax+8]
0x140020cc7  cmp     [rdx], rax
0x140020cca  jnz     loc_140020D73
0x140020cd0  mov     [rdx], r8
0x140020cd3  mov     [r8+8], rdx
0x140020cd7  mov     qword ptr [rax], 0
0x140020cde  mov     qword ptr [rax+8], 0
0x140020ce6  mov     cl, [rbx+45h]; Irql
0x140020ce9  call    cs:__imp_IoReleaseCancelSpinLock
0x140020cf0  nop     dword ptr [rax+rax+00h]
0x140020cf5  mov     rax, [rbx+0B8h]
0x140020cfc  mov     esi, [rbx+70h]
0x140020cff  mov     edi, [rax+10h]
0x140020d02  shr     edi, 3
0x140020d05  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d0c  lea     rax, WPP_GLOBAL_Control
0x140020d13  cmp     rcx, rax
0x140020d16  jz      short loc_140020D38
0x140020d18  mov     eax, [rcx+6Ch]
0x140020d1b  test    al, 4
0x140020d1d  jz      short loc_140020D38
0x140020d1f  mov     rcx, [rcx+58h]
0x140020d23  mov     edx, 11h
0x140020d28  mov     [rsp+58h+var_30], esi
0x140020d2c  mov     r9, rbx
0x140020d2f  mov     [rsp+58h+var_38], edi
0x140020d33  call    WPP_SF_qdD
0x140020d38  mov     r8, [rbx+18h]
0x140020d3c  mov     r9d, esi
0x140020d3f  mov     edx, edi
0x140020d41  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x140020d44  call    ACpCompleteStorageCancelled
0x140020d49  xor     edx, edx; PriorityBoost
0x140020d4b  mov     qword ptr [rbx+38h], 0
0x140020d53  mov     rcx, rbx; Irp
0x140020d56  mov     dword ptr [rbx+30h], 0C0000120h
0x140020d5d  call    cs:__imp_IofCompleteRequest
0x140020d64  nop     dword ptr [rax+rax+00h]
0x140020d69  add     rsp, 38h
0x140020d6d  pop     rdi
0x140020d6e  pop     rsi
0x140020d6f  pop     rbp
0x140020d70  pop     rbx
0x140020d71  retn
0x140020d73  mov     ecx, 3
0x140020d78  int     29h; Win8: RtlFailFast(ecx)
```
