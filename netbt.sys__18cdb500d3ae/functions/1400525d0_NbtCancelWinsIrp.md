# NbtCancelWinsIrp

- ea: `0x1400525d0`
- end: `0x140052699`
- name: `NbtCancelWinsIrp`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140040294`
- `0x1400525d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005266a`
- `ntoskrnl!IofCompleteRequest` at `0x14005266a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005260e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005260e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052621`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052621`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052652`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052681`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052652`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052681`

## pseudocode

```c
void __fastcall NbtCancelWinsIrp(__int64 a1, IRP *a2)
{
  _QWORD *FsContext; // rdi
  KIRQL v4; // al

  if ( (BYTE2(xmmword_140038420) & 1) != 0 )
    WPP_SF_(1040, 21, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids);
  FsContext = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( FsContext && *((_DWORD *)FsContext + 4) == 1936615767 && (IRP *)FsContext[8] == a2 )
  {
    FsContext[8] = 0;
    KeReleaseSpinLock(&SpinLock, v4);
    a2->IoStatus.Status = -1073741536;
    IofCompleteRequest(a2, 2);
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v4);
  }
}

```

## disassembly

```asm
0x1400525d0  mov     [rsp+arg_0], rbx
0x1400525d5  push    rdi
0x1400525d6  sub     rsp, 20h
0x1400525da  mov     rbx, rdx
0x1400525dd  test    byte ptr cs:xmmword_140038420+2, 1
0x1400525e4  jz      short loc_1400525FC
0x1400525e6  mov     edx, 15h
0x1400525eb  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x1400525f2  mov     ecx, 410h
0x1400525f7  call    WPP_SF_
0x1400525fc  mov     rax, [rbx+0B8h]
0x140052603  mov     rcx, [rax+30h]
0x140052607  mov     rdi, [rcx+18h]
0x14005260b  mov     cl, [rbx+45h]; Irql
0x14005260e  call    cs:__imp_IoReleaseCancelSpinLock
0x140052615  nop     dword ptr [rax+rax+00h]
0x14005261a  lea     rcx, SpinLock; SpinLock
0x140052621  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140052628  nop     dword ptr [rax+rax+00h]
0x14005262d  test    rdi, rdi
0x140052630  jz      short loc_140052678
0x140052632  cmp     dword ptr [rdi+10h], 736E6957h
0x140052639  jnz     short loc_140052678
0x14005263b  cmp     [rdi+40h], rbx
0x14005263f  jnz     short loc_140052678
0x140052641  mov     dl, al; NewIrql
0x140052643  mov     qword ptr [rdi+40h], 0
0x14005264b  lea     rcx, SpinLock; SpinLock
0x140052652  call    cs:__imp_KeReleaseSpinLock
0x140052659  nop     dword ptr [rax+rax+00h]
0x14005265e  mov     dl, 2; PriorityBoost
0x140052660  mov     dword ptr [rbx+30h], 0C0000120h
0x140052667  mov     rcx, rbx; Irp
0x14005266a  call    cs:__imp_IofCompleteRequest
0x140052671  nop     dword ptr [rax+rax+00h]
0x140052676  jmp     short loc_14005268D
0x140052678  mov     dl, al; NewIrql
0x14005267a  lea     rcx, SpinLock; SpinLock
0x140052681  call    cs:__imp_KeReleaseSpinLock
0x140052688  nop     dword ptr [rax+rax+00h]
0x14005268d  mov     rbx, [rsp+28h+arg_0]
0x140052692  add     rsp, 20h
0x140052696  pop     rdi
0x140052697  retn
```
