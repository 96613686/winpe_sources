# ServiceAllocRequests

- ea: `0x180010a04`
- end: `0x180010a82`
- name: `ServiceAllocRequests`
- size: `126`
- prototype: ``
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
- `0x180010a04`
- `0x180065c90`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180010a5c`
- `ntoskrnl!IofCompleteRequest` at `0x180010a5c`

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
0x180010a04  mov     [rsp+arg_0], rbx
0x180010a09  mov     [rsp+arg_8], rsi
0x180010a0e  push    rdi
0x180010a0f  sub     rsp, 20h
0x180010a13  lea     rdi, [rcx+70h]
0x180010a17  lea     rsi, [rcx+28h]
0x180010a1b  xor     r9d, r9d; RemovalOperation
0x180010a1e  mov     rdx, rdi; SpinLock
0x180010a21  mov     rcx, rsi; QueueHead
0x180010a24  lea     r8d, [r9+1]; ListLocation
0x180010a28  call    KsRemoveIrpFromCancelableQueue
0x180010a2d  mov     rbx, rax
0x180010a30  test    rax, rax
0x180010a33  jz      short loc_180010A71
0x180010a35  lea     rdx, iMethodAlloc; Handler
0x180010a3c  mov     rcx, rax; Irp
0x180010a3f  call    KsDispatchSpecificMethod
0x180010a44  mov     rcx, rbx; Irp
0x180010a47  test    eax, eax
0x180010a49  jnz     short loc_180010A6A
0x180010a4b  call    KsRemoveSpecificIrpFromCancelableQueue
0x180010a50  xor     edx, edx; PriorityBoost
0x180010a52  mov     dword ptr [rbx+30h], 0
0x180010a59  mov     rcx, rbx; Irp
0x180010a5c  call    cs:__imp_IofCompleteRequest
0x180010a63  nop     dword ptr [rax+rax+00h]
0x180010a68  jmp     short loc_180010A1B
0x180010a6a  xor     edx, edx; DriverCancel
0x180010a6c  call    KsReleaseIrpOnCancelableQueue
0x180010a71  mov     rbx, [rsp+28h+arg_0]
0x180010a76  mov     rsi, [rsp+28h+arg_8]
0x180010a7b  add     rsp, 20h
0x180010a7f  pop     rdi
0x180010a80  retn
```
