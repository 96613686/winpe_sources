# CKSAutomationThunk::RouteConnectionState(_IRP *,KSIDENTIFIER *,KSSTATE *)

- ea: `0x140002cf0`
- end: `0x140002d19`
- name: `?RouteConnectionState@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAW4KSSTATE@@@Z`
- size: `41`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003770`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::RouteConnectionState(struct _IRP *a1, struct KSIDENTIFIER *a2, enum KSSTATE *a3)
{
  return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *))a1->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink->Flink->Blink)(
           a1->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink,
           a1,
           a2,
           a3);
}

```

## disassembly

```asm
0x140002cf0  sub     rsp, 38h
0x140002cf4  mov     r10, rcx
0x140002cf7  mov     r9, r8
0x140002cfa  mov     rcx, [rcx+80h]
0x140002d01  mov     r8, rdx
0x140002d04  mov     rdx, r10
0x140002d07  mov     rax, [rcx]
0x140002d0a  mov     rax, [rax+8]
0x140002d0e  call    _guard_dispatch_icall
0x140002d13  add     rsp, 38h
0x140002d17  retn
```
