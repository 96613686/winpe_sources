# CKsDevice::WaitWakeCompletion(_DEVICE_OBJECT *,_IRP *,CKsDevice *)

- ea: `0x180013630`
- end: `0x18001375a`
- name: `?WaitWakeCompletion@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z`
- size: `298`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct CKsDevice *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180013630`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180013709`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180013709`
- `ntoskrnl!KeSetEvent` at `0x1800136bd`
- `ntoskrnl!KeSetEvent` at `0x1800136bd`

## pseudocode

```c
__int64 __fastcall CKsDevice::WaitWakeCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct CKsDevice *a3)
{
  unsigned int v4; // ebx
  struct _IRP *v5; // rdi
  NTSTATUS Status; // eax
  struct _IO_REMOVE_LOCK *DeviceExtension; // rbp
  int v8; // edx
  int v9; // edx

  v4 = 0;
  v5 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    Status = a2->IoStatus.Status;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      139,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      Status);
  }
  DeviceExtension = (struct _IO_REMOVE_LOCK *)a3->m_Ext.Public.FunctionalDeviceObject->DeviceExtension;
  if ( !_InterlockedExchange64((volatile __int64 *)&a3->m_PendingWakeIrp, 0) )
    v4 = -1073741802;
  KeSetEvent(&a3->m_WakeupCompletionSignal, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      140,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  IoReleaseRemoveLockEx(DeviceExtension - 1, v5, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      141,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x180013630  push    rbx
0x180013632  push    rbp
0x180013633  push    rsi
0x180013634  push    rdi
0x180013635  push    r12
0x180013637  push    r13
0x180013639  push    r14
0x18001363b  sub     rsp, 30h
0x18001363f  xor     r14d, r14d
0x180013642  mov     rsi, r8
0x180013645  mov     ebx, r14d
0x180013648  mov     rdi, rdx
0x18001364b  lea     r13, WPP_RECORDER_INITIALIZED
0x180013652  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180013659  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180013660  jz      short loc_180013691
0x180013662  mov     rcx, cs:WPP_GLOBAL_Control
0x180013669  cmp     [rcx+48h], r14w
0x18001366e  jz      short loc_180013691
0x180013670  mov     eax, [rdx+30h]
0x180013673  lea     r8d, [r14+1]
0x180013677  mov     rcx, [rcx+40h]
0x18001367b  mov     dl, 5
0x18001367d  mov     [rsp+68h+var_40], eax
0x180013681  mov     r9d, 8Bh
0x180013687  mov     [rsp+68h+var_48], r12
0x18001368c  call    WPP_RECORDER_SF_D
0x180013691  mov     rax, [rsi+0E0h]
0x180013698  mov     ecx, 0C0000016h
0x18001369d  mov     rbp, [rax+40h]
0x1800136a1  mov     rax, r14
0x1800136a4  xchg    rax, [rsi+3C8h]
0x1800136ab  test    rax, rax
0x1800136ae  cmovz   ebx, ecx
0x1800136b1  lea     rcx, [rsi+3F8h]; Event
0x1800136b8  xor     r8d, r8d; Wait
0x1800136bb  xor     edx, edx; Increment
0x1800136bd  call    cs:__imp_KeSetEvent
0x1800136c4  nop     dword ptr [rax+rax+00h]
0x1800136c9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800136d0  jz      short loc_1800136FC
0x1800136d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136d9  cmp     [rcx+48h], r14w
0x1800136de  jz      short loc_1800136FC
0x1800136e0  mov     rcx, [rcx+40h]
0x1800136e4  mov     r9d, 8Ch
0x1800136ea  mov     r8d, 1
0x1800136f0  mov     [rsp+68h+var_48], r12
0x1800136f5  mov     dl, 5
0x1800136f7  call    WPP_RECORDER_SF_
0x1800136fc  mov     r8d, 20h ; ' '; RemlockSize
0x180013702  lea     rcx, [rbp-20h]; RemoveLock
0x180013706  mov     rdx, rdi; Tag
0x180013709  call    cs:__imp_IoReleaseRemoveLockEx
0x180013710  nop     dword ptr [rax+rax+00h]
0x180013715  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001371c  jz      short loc_180013748
0x18001371e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013725  cmp     [rcx+48h], r14w
0x18001372a  jz      short loc_180013748
0x18001372c  mov     rcx, [rcx+40h]
0x180013730  mov     r9d, 8Dh
0x180013736  mov     r8d, 1
0x18001373c  mov     [rsp+68h+var_48], r12
0x180013741  mov     dl, 5
0x180013743  call    WPP_RECORDER_SF_
0x180013748  mov     eax, ebx
0x18001374a  add     rsp, 30h
0x18001374e  pop     r14
0x180013750  pop     r13
0x180013752  pop     r12
0x180013754  pop     rdi
0x180013755  pop     rsi
0x180013756  pop     rbp
0x180013757  pop     rbx
0x180013758  retn
```
