# SmbWskAsynchronousConnectCompletion

- ea: `0x140021aa0`
- end: `0x140021be7`
- name: `SmbWskAsynchronousConnectCompletion`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140021aa0`
- `0x140021bf0`
- `0x140021c40`
- `0x140037b28`
- `0x140054e80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021af2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021af2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021b4e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021b4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021b14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021b14`
- `rdbss!RxDispatchToWorkerThread` at `0x140021b75`
- `rdbss!RxDispatchToWorkerThread` at `0x140021b75`

## pseudocode

```c
__int64 __fastcall SmbWskAsynchronousConnectCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 Status; // rdx
  int v6; // ecx
  KIRQL v7; // al
  KSPIN_LOCK *v8; // rcx

  Status = (unsigned int)a2->IoStatus.Status;
  *(_DWORD *)(a3 + 16) = Status;
  *(_DWORD *)(a3 + 20) = 4;
  v6 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDqq(WPP_GLOBAL_Control->AttachedDevice, Status, a3, a2, Status, a3, *(_QWORD *)(a3 + 8));
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 0x20) != 0 )
    McTemplateK0ppqq_EtwWriteTransfer(
      v6,
      (unsigned int)NetConnectCompletionV2,
      0,
      *(_QWORD *)(a3 + 216),
      *(_QWORD *)(*(_QWORD *)(a3 + 216) + 104LL),
      a2->IoStatus.Status,
      1);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a3 + 8) + 8LL));
  v8 = (KSPIN_LOCK *)(*(_QWORD *)(a3 + 8) + 8LL);
  *(_QWORD *)(a3 + 248) = 0;
  KeReleaseSpinLock(v8, v7);
  RxCeDereferenceAndFreeIrp(*(PVOID *)(a3 + 256), a2);
  if ( !*(_DWORD *)(a3 + 16)
    || KeGetCurrentIrql() < 2u
    || RxDispatchToWorkerThread(
         *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(a3 + 8) + 32LL),
         NormalWorkQueue,
         SmbWskAsynchronousConnectCompletionWorker,
         (PVOID)a3) )
  {
    SmbWskAsynchronousConnectCompletionWorker((PVOID)a3);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140021aa0  mov     [rsp+arg_0], rbx
0x140021aa5  push    rdi
0x140021aa6  sub     rsp, 40h
0x140021aaa  mov     rdi, rdx
0x140021aad  mov     rbx, r8
0x140021ab0  mov     edx, [rdx+30h]
0x140021ab3  mov     [r8+10h], edx
0x140021ab7  mov     dword ptr [r8+14h], 4
0x140021abf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140021ac6  lea     rax, WPP_GLOBAL_Control
0x140021acd  cmp     rcx, rax
0x140021ad0  jz      short loc_140021ADD
0x140021ad2  mov     eax, [rcx+2Ch]
0x140021ad5  test    al, 4
0x140021ad7  jnz     loc_140021B87
0x140021add  test    cs:Microsoft_Windows_SMBClientEnableBits, 20h
0x140021ae4  jnz     loc_140021BB4
0x140021aea  mov     rcx, [rbx+8]
0x140021aee  add     rcx, 8; SpinLock
0x140021af2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140021af9  nop     dword ptr [rax+rax+00h]
0x140021afe  mov     rcx, [rbx+8]
0x140021b02  movzx   edx, al; NewIrql
0x140021b05  add     rcx, 8; SpinLock
0x140021b09  mov     qword ptr [rbx+0F8h], 0
0x140021b14  call    cs:__imp_KeReleaseSpinLock
0x140021b1b  nop     dword ptr [rax+rax+00h]
0x140021b20  mov     rcx, [rbx+100h]; P
0x140021b27  mov     rdx, rdi; pIrp
0x140021b2a  call    RxCeDereferenceAndFreeIrp
0x140021b2f  cmp     dword ptr [rbx+10h], 0
0x140021b33  jnz     short loc_140021B4E
0x140021b35  mov     rcx, rbx; Context
0x140021b38  call    SmbWskAsynchronousConnectCompletionWorker
0x140021b3d  mov     eax, 0C0000016h
0x140021b42  mov     rbx, [rsp+48h+arg_0]
0x140021b47  add     rsp, 40h
0x140021b4b  pop     rdi
0x140021b4c  retn
0x140021b4e  call    cs:__imp_KeGetCurrentIrql
0x140021b55  nop     dword ptr [rax+rax+00h]
0x140021b5a  cmp     al, 2
0x140021b5c  jb      short loc_140021B35
0x140021b5e  mov     rcx, [rbx+8]
0x140021b62  lea     r8, SmbWskAsynchronousConnectCompletionWorker; Routine
0x140021b69  mov     r9, rbx; pContext
0x140021b6c  mov     edx, 3; WorkQueueType
0x140021b71  mov     rcx, [rcx+20h]; pMRxDeviceObject
0x140021b75  call    cs:__imp_RxDispatchToWorkerThread
0x140021b7c  nop     dword ptr [rax+rax+00h]
0x140021b81  test    eax, eax
0x140021b83  jz      short loc_140021B3D
0x140021b85  jmp     short loc_140021B35
0x140021b87  cmp     byte ptr [rcx+29h], 2
0x140021b8b  jb      loc_140021ADD
0x140021b91  mov     rax, [r8+8]
0x140021b95  mov     r9, rdi
0x140021b98  mov     rcx, [rcx+18h]
0x140021b9c  mov     [rsp+48h+var_18], rax
0x140021ba1  mov     [rsp+48h+var_20], rbx
0x140021ba6  mov     dword ptr [rsp+48h+var_28], edx
0x140021baa  call    WPP_SF_qDqq
0x140021baf  jmp     loc_140021ADD
0x140021bb4  mov     eax, [rdi+30h]
0x140021bb7  lea     rdx, NetConnectCompletionV2
0x140021bbe  mov     r9, [rbx+0D8h]
0x140021bc5  xor     r8d, r8d
0x140021bc8  mov     dword ptr [rsp+48h+var_18], 1
0x140021bd0  mov     dword ptr [rsp+48h+var_20], eax
0x140021bd4  mov     rax, [r9+68h]
0x140021bd8  mov     [rsp+48h+var_28], rax
0x140021bdd  call    McTemplateK0ppqq_EtwWriteTransfer
0x140021be2  jmp     loc_140021AEA
```
