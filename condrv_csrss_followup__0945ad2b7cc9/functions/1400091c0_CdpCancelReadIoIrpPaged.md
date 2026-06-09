# CdpCancelReadIoIrpPaged

- ea: `0x1400091c0`
- end: `0x140009264`
- name: `CdpCancelReadIoIrpPaged`
- size: `164`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001380`

## callees

- `0x1400091c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400091e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400091e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009227`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009227`
- `ntoskrnl!IofCompleteRequest` at `0x140009247`
- `ntoskrnl!IofCompleteRequest` at `0x140009247`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400091d9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400091d9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400091fd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400091fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009216`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009216`

## pseudocode

```c
void __fastcall CdpCancelReadIoIrpPaged(PIRP Irp)
{
  struct _LIST_ENTRY *Flink; // rdi
  char v3; // si
  struct _LIST_ENTRY *v4; // rcx

  Flink = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v3 = 0;
  if ( KeGetCurrentIrql() <= 1u )
  {
    KeEnterCriticalRegion();
    v3 = 1;
  }
  ExAcquirePushLockExclusiveEx(Flink->Flink, 0);
  v4 = Flink->Flink;
  Flink[1].Flink = 0;
  ExReleasePushLockExclusiveEx(v4, 0);
  if ( v3 )
    KeLeaveCriticalRegion();
  Irp->IoStatus.Status = -1073741536;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x1400091c0  mov     [rsp+arg_0], rbx
0x1400091c5  mov     [rsp+arg_8], rsi
0x1400091ca  push    rdi
0x1400091cb  sub     rsp, 20h
0x1400091cf  mov     rdi, [rcx+78h]
0x1400091d3  mov     rbx, rcx
0x1400091d6  xor     sil, sil
0x1400091d9  call    cs:__imp_KeGetCurrentIrql
0x1400091e0  nop     dword ptr [rax+rax+00h]
0x1400091e5  cmp     al, 1
0x1400091e7  ja      short loc_1400091F8
0x1400091e9  call    cs:__imp_KeEnterCriticalRegion
0x1400091f0  nop     dword ptr [rax+rax+00h]
0x1400091f5  mov     sil, 1
0x1400091f8  mov     rcx, [rdi]
0x1400091fb  xor     edx, edx
0x1400091fd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140009204  nop     dword ptr [rax+rax+00h]
0x140009209  mov     rcx, [rdi]
0x14000920c  xor     edx, edx
0x14000920e  mov     qword ptr [rdi+10h], 0
0x140009216  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000921d  nop     dword ptr [rax+rax+00h]
0x140009222  test    sil, sil
0x140009225  jz      short loc_140009233
0x140009227  call    cs:__imp_KeLeaveCriticalRegion
0x14000922e  nop     dword ptr [rax+rax+00h]
0x140009233  xor     edx, edx; PriorityBoost
0x140009235  mov     dword ptr [rbx+30h], 0C0000120h
0x14000923c  mov     rcx, rbx; Irp
0x14000923f  mov     qword ptr [rbx+38h], 0
0x140009247  call    cs:__imp_IofCompleteRequest
0x14000924e  nop     dword ptr [rax+rax+00h]
0x140009253  mov     rbx, [rsp+28h+arg_0]
0x140009258  mov     rsi, [rsp+28h+arg_8]
0x14000925d  add     rsp, 20h
0x140009261  pop     rdi
0x140009262  retn
```
