# CKSAutomationThunk::RouteConnectionState(_IRP *,KSIDENTIFIER *,KSSTATE *)

- ea: `0x140003650`
- end: `0x140003679`
- name: `?RouteConnectionState@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAW4KSSTATE@@@Z`
- size: `41`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1400041f0`

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
0x140003650  sub     rsp, 38h
0x140003654  mov     r10, rcx
0x140003657  mov     r9, r8
0x14000365a  mov     rcx, [rcx+80h]
0x140003661  mov     r8, rdx
0x140003664  mov     rdx, r10
0x140003667  mov     rax, [rcx]
0x14000366a  mov     rax, [rax+8]
0x14000366e  call    _guard_dispatch_icall
0x140003673  add     rsp, 38h
0x140003677  retn
```
