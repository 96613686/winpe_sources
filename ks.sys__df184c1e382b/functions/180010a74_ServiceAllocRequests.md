# ServiceAllocRequests

- ea: `0x180010a74`
- end: `0x180010af2`
- name: `ServiceAllocRequests`
- size: `126`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180033ac0`
- `0x180034020`

## callees

- `0x180006c40`
- `0x180007c40`
- `0x180007f30`
- `0x180010a74`
- `0x180066600`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180010acc`
- `ntoskrnl!IofCompleteRequest` at `0x180010acc`

## pseudocode

```c
void __fastcall ServiceAllocRequests(__int64 a1)
{
  KSPIN_LOCK *v1; // rdi
  struct _LIST_ENTRY *v2; // rsi
  IRP *v3; // rax
  IRP *v4; // rbx

  v1 = (KSPIN_LOCK *)(a1 + 112);
  v2 = (struct _LIST_ENTRY *)(a1 + 40);
  while ( 1 )
  {
    v3 = KsRemoveIrpFromCancelableQueue(v2, v1, KsListEntryHead, KsAcquireOnly);
    v4 = v3;
    if ( !v3 )
      break;
    if ( KsDispatchSpecificMethod(v3, iMethodAlloc) )
    {
      KsReleaseIrpOnCancelableQueue(v4, 0);
      return;
    }
    KsRemoveSpecificIrpFromCancelableQueue(v4);
    v4->IoStatus.Status = 0;
    IofCompleteRequest(v4, 0);
  }
}

```

## disassembly

```asm
0x180010a74  mov     [rsp+arg_0], rbx
0x180010a79  mov     [rsp+arg_8], rsi
0x180010a7e  push    rdi
0x180010a7f  sub     rsp, 20h
0x180010a83  lea     rdi, [rcx+70h]
0x180010a87  lea     rsi, [rcx+28h]
0x180010a8b  xor     r9d, r9d; RemovalOperation
0x180010a8e  mov     rdx, rdi; SpinLock
0x180010a91  mov     rcx, rsi; QueueHead
0x180010a94  lea     r8d, [r9+1]; ListLocation
0x180010a98  call    KsRemoveIrpFromCancelableQueue
0x180010a9d  mov     rbx, rax
0x180010aa0  test    rax, rax
0x180010aa3  jz      short loc_180010AE1
0x180010aa5  lea     rdx, iMethodAlloc; Handler
0x180010aac  mov     rcx, rax; Irp
0x180010aaf  call    KsDispatchSpecificMethod
0x180010ab4  mov     rcx, rbx; Irp
0x180010ab7  test    eax, eax
0x180010ab9  jnz     short loc_180010ADA
0x180010abb  call    KsRemoveSpecificIrpFromCancelableQueue
0x180010ac0  xor     edx, edx; PriorityBoost
0x180010ac2  mov     dword ptr [rbx+30h], 0
0x180010ac9  mov     rcx, rbx; Irp
0x180010acc  call    cs:__imp_IofCompleteRequest
0x180010ad3  nop     dword ptr [rax+rax+00h]
0x180010ad8  jmp     short loc_180010A8B
0x180010ada  xor     edx, edx; DriverCancel
0x180010adc  call    KsReleaseIrpOnCancelableQueue
0x180010ae1  mov     rbx, [rsp+28h+arg_0]
0x180010ae6  mov     rsi, [rsp+28h+arg_8]
0x180010aeb  add     rsp, 20h
0x180010aef  pop     rdi
0x180010af0  retn
```
