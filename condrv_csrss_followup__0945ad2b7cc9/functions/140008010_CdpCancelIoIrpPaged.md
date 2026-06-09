# CdpCancelIoIrpPaged

- ea: `0x140008010`
- end: `0x1400080bd`
- name: `CdpCancelIoIrpPaged`
- size: `173`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010e0`

## callees

- `0x140008010`
- `0x14000c3d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140008040`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008040`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008080`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008080`
- `ntoskrnl!IofCompleteRequest` at `0x1400080a0`
- `ntoskrnl!IofCompleteRequest` at `0x1400080a0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008030`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008030`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008054`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140008054`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000806f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000806f`

## pseudocode

```c
void __fastcall CdpCancelIoIrpPaged(PIRP Irp)
{
  char v2; // si
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  __int64 v4; // rdx

  v2 = 0;
  SecurityContext = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( KeGetCurrentIrql() <= 1u )
  {
    KeEnterCriticalRegion();
    v2 = 1;
  }
  ExAcquirePushLockExclusiveEx(SecurityContext->SecurityQos, 0);
  LOBYTE(v4) = 1;
  CdpPrepareIoCompletion(Irp, v4);
  ExReleasePushLockExclusiveEx(SecurityContext->SecurityQos, 0);
  if ( v2 )
    KeLeaveCriticalRegion();
  Irp->IoStatus.Status = -1073741536;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x140008010  mov     [rsp+arg_0], rbx
0x140008015  mov     [rsp+arg_8], rsi
0x14000801a  push    rdi
0x14000801b  sub     rsp, 20h
0x14000801f  mov     rax, [rcx+0B8h]
0x140008026  mov     rbx, rcx
0x140008029  xor     sil, sil
0x14000802c  mov     rdi, [rax+8]
0x140008030  call    cs:__imp_KeGetCurrentIrql
0x140008037  nop     dword ptr [rax+rax+00h]
0x14000803c  cmp     al, 1
0x14000803e  ja      short loc_14000804F
0x140008040  call    cs:__imp_KeEnterCriticalRegion
0x140008047  nop     dword ptr [rax+rax+00h]
0x14000804c  mov     sil, 1
0x14000804f  mov     rcx, [rdi]
0x140008052  xor     edx, edx
0x140008054  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000805b  nop     dword ptr [rax+rax+00h]
0x140008060  mov     dl, 1
0x140008062  mov     rcx, rbx
0x140008065  call    CdpPrepareIoCompletion
0x14000806a  mov     rcx, [rdi]
0x14000806d  xor     edx, edx
0x14000806f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140008076  nop     dword ptr [rax+rax+00h]
0x14000807b  test    sil, sil
0x14000807e  jz      short loc_14000808C
0x140008080  call    cs:__imp_KeLeaveCriticalRegion
0x140008087  nop     dword ptr [rax+rax+00h]
0x14000808c  xor     edx, edx; PriorityBoost
0x14000808e  mov     dword ptr [rbx+30h], 0C0000120h
0x140008095  mov     rcx, rbx; Irp
0x140008098  mov     qword ptr [rbx+38h], 0
0x1400080a0  call    cs:__imp_IofCompleteRequest
0x1400080a7  nop     dword ptr [rax+rax+00h]
0x1400080ac  mov     rbx, [rsp+28h+arg_0]
0x1400080b1  mov     rsi, [rsp+28h+arg_8]
0x1400080b6  add     rsp, 20h
0x1400080ba  pop     rdi
0x1400080bb  retn
```
