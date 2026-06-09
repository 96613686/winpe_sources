# NatpRedirectCancelRoutine

- ea: `0x14001a0f0`
- end: `0x14001a218`
- name: `NatpRedirectCancelRoutine`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000218c`
- `0x14000e378`
- `0x140011624`
- `0x140019cec`
- `0x14001a0f0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a136`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a136`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a15f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a15f`
- `ntoskrnl!IofCompleteRequest` at `0x14001a1cf`
- `ntoskrnl!IofCompleteRequest` at `0x14001a1cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a1af`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a1af`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a18c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a18c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a149`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a149`

## pseudocode

```c
__int64 __fastcall NatpRedirectCancelRoutine(__int64 a1, IRP *a2)
{
  char *Blink; // rbx
  KIRQL v4; // si
  struct _LIST_ENTRY *Flink; // rcx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  Blink = 0;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = KeAcquireSpinLockRaiseToDpc(&MappingLock);
  KeAcquireSpinLockAtDpcLevel(&RedirectLock);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  if ( Flink )
  {
    Blink = (char *)Flink[9].Blink;
    NatpCleanupRedirect((char *)Flink, 0xC0000120);
  }
  KeReleaseSpinLockFromDpcLevel(&RedirectLock);
  if ( Blink )
    NatDeleteMapping(Blink);
  KeReleaseSpinLock(&MappingLock, v4);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  result = ReleaseComponentReference();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14001a0f0  push    rbx
0x14001a0f2  push    rbp
0x14001a0f3  push    rsi
0x14001a0f4  push    rdi
0x14001a0f5  sub     rsp, 28h
0x14001a0f9  mov     rdi, rdx
0x14001a0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a103  lea     rbp, WPP_GLOBAL_Control
0x14001a10a  cmp     rcx, rbp
0x14001a10d  jz      short loc_14001A131
0x14001a10f  mov     eax, [rcx+2Ch]
0x14001a112  test    al, 1
0x14001a114  jz      short loc_14001A131
0x14001a116  cmp     byte ptr [rcx+29h], 6
0x14001a11a  jb      short loc_14001A131
0x14001a11c  mov     rcx, [rcx+18h]
0x14001a120  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a127  mov     edx, 5Eh ; '^'
0x14001a12c  call    WPP_SF_
0x14001a131  mov     cl, [rdi+45h]; Irql
0x14001a134  xor     ebx, ebx
0x14001a136  call    cs:__imp_IoReleaseCancelSpinLock
0x14001a13d  nop     dword ptr [rax+rax+00h]
0x14001a142  lea     rcx, MappingLock; SpinLock
0x14001a149  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a150  nop     dword ptr [rax+rax+00h]
0x14001a155  lea     rcx, RedirectLock; SpinLock
0x14001a15c  mov     sil, al
0x14001a15f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001a166  nop     dword ptr [rax+rax+00h]
0x14001a16b  mov     rcx, [rdi+78h]; P
0x14001a16f  test    rcx, rcx
0x14001a172  jz      short loc_14001A185
0x14001a174  mov     rbx, [rcx+98h]
0x14001a17b  mov     edx, 0C0000120h
0x14001a180  call    NatpCleanupRedirect
0x14001a185  lea     rcx, RedirectLock; SpinLock
0x14001a18c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001a193  nop     dword ptr [rax+rax+00h]
0x14001a198  test    rbx, rbx
0x14001a19b  jz      short loc_14001A1A5
0x14001a19d  mov     rcx, rbx; Entry
0x14001a1a0  call    NatDeleteMapping
0x14001a1a5  mov     dl, sil; NewIrql
0x14001a1a8  lea     rcx, MappingLock; SpinLock
0x14001a1af  call    cs:__imp_KeReleaseSpinLock
0x14001a1b6  nop     dword ptr [rax+rax+00h]
0x14001a1bb  xor     edx, edx; PriorityBoost
0x14001a1bd  mov     dword ptr [rdi+30h], 0C0000120h
0x14001a1c4  mov     rcx, rdi; Irp
0x14001a1c7  mov     qword ptr [rdi+38h], 0
0x14001a1cf  call    cs:__imp_IofCompleteRequest
0x14001a1d6  nop     dword ptr [rax+rax+00h]
0x14001a1db  call    ReleaseComponentReference
0x14001a1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1e7  cmp     rcx, rbp
0x14001a1ea  jz      short loc_14001A20E
0x14001a1ec  mov     eax, [rcx+2Ch]
0x14001a1ef  test    al, 1
0x14001a1f1  jz      short loc_14001A20E
0x14001a1f3  cmp     byte ptr [rcx+29h], 6
0x14001a1f7  jb      short loc_14001A20E
0x14001a1f9  mov     rcx, [rcx+18h]
0x14001a1fd  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a204  mov     edx, 5Fh ; '_'
0x14001a209  call    WPP_SF_
0x14001a20e  add     rsp, 28h
0x14001a212  pop     rdi
0x14001a213  pop     rsi
0x14001a214  pop     rbp
0x14001a215  pop     rbx
0x14001a216  retn
```
