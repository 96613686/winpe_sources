# DevMgmtEventRequestIRPCancel(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140004500`
- end: `0x1400045fb`
- name: `?DevMgmtEventRequestIRPCancel@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `251`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x1400042fc`
- `0x140004500`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000457d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000457d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000459e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000459e`
- `ntoskrnl!IofCompleteRequest` at `0x1400045be`
- `ntoskrnl!IofCompleteRequest` at `0x1400045be`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004565`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140004565`

## pseudocode

```c
void __fastcall DevMgmtEventRequestIRPCancel(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PFILE_OBJECT FileObject; // rax
  unsigned int *FsContext; // rax
  unsigned int v5; // esi
  KIRQL v6; // bl
  __int64 v7; // rcx

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject )
  {
    FsContext = (unsigned int *)FileObject->FsContext;
    if ( FsContext )
    {
      v5 = *FsContext;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids, v5);
      _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, 0);
      IoReleaseCancelSpinLock(a2->CancelIrql);
      if ( WPP_MAIN_CB.DeviceQueue.Lock )
      {
        v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
        RDPEVNTLIST_DequeueSpecificRequest(v7, v5, a2);
        KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v6);
      }
    }
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
}

```

## disassembly

```asm
0x140004500  push    rbx
0x140004502  push    rbp
0x140004503  push    rsi
0x140004504  push    rdi
0x140004505  sub     rsp, 28h
0x140004509  mov     rax, [rdx+0B8h]
0x140004510  lea     rbp, WPP_GLOBAL_Control
0x140004517  mov     rdi, rdx
0x14000451a  mov     rax, [rax+30h]
0x14000451e  test    rax, rax
0x140004521  jz      loc_1400045AA
0x140004527  mov     rax, [rax+18h]
0x14000452b  test    rax, rax
0x14000452e  jz      short loc_1400045AA
0x140004530  mov     esi, [rax]
0x140004532  mov     rcx, cs:WPP_GLOBAL_Control
0x140004539  cmp     rcx, rbp
0x14000453c  jz      short loc_14000455C
0x14000453e  cmp     byte ptr [rcx+29h], 4
0x140004542  jb      short loc_14000455C
0x140004544  mov     rcx, [rcx+18h]
0x140004548  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14000454f  mov     edx, 17h
0x140004554  mov     r9d, esi
0x140004557  call    WPP_SF_d
0x14000455c  xor     eax, eax
0x14000455e  xchg    rax, [rdi+68h]
0x140004562  mov     cl, [rdi+45h]; Irql
0x140004565  call    cs:__imp_IoReleaseCancelSpinLock
0x14000456c  nop     dword ptr [rax+rax+00h]
0x140004571  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140004578  test    rcx, rcx
0x14000457b  jz      short loc_1400045AA
0x14000457d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004584  nop     dword ptr [rax+rax+00h]
0x140004589  mov     r8, rdi
0x14000458c  mov     edx, esi
0x14000458e  mov     bl, al
0x140004590  call    RDPEVNTLIST_DequeueSpecificRequest
0x140004595  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x14000459c  mov     dl, bl; NewIrql
0x14000459e  call    cs:__imp_KeReleaseSpinLock
0x1400045a5  nop     dword ptr [rax+rax+00h]
0x1400045aa  xor     edx, edx; PriorityBoost
0x1400045ac  mov     qword ptr [rdi+38h], 0
0x1400045b4  mov     rcx, rdi; Irp
0x1400045b7  mov     dword ptr [rdi+30h], 0C0000120h
0x1400045be  call    cs:__imp_IofCompleteRequest
0x1400045c5  nop     dword ptr [rax+rax+00h]
0x1400045ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045d1  cmp     rcx, rbp
0x1400045d4  jz      short loc_1400045F1
0x1400045d6  cmp     byte ptr [rcx+29h], 4
0x1400045da  jb      short loc_1400045F1
0x1400045dc  mov     rcx, [rcx+18h]
0x1400045e0  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x1400045e7  mov     edx, 18h
0x1400045ec  call    WPP_SF_
0x1400045f1  add     rsp, 28h
0x1400045f5  pop     rdi
0x1400045f6  pop     rsi
0x1400045f7  pop     rbp
0x1400045f8  pop     rbx
0x1400045f9  retn
```
