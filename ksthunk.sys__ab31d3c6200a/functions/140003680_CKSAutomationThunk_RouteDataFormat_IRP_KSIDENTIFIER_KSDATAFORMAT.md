# CKSAutomationThunk::RouteDataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x140003680`
- end: `0x1400036a8`
- name: `?RouteDataFormat@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1400041f0`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::RouteDataFormat(
        struct _IRP *a1,
        struct KSIDENTIFIER *a2,
        union KSDATAFORMAT *a3)
{
  return ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *))a1->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink->Flink->Flink)(
           a1->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink,
           a1,
           a2,
           a3);
}

```

## disassembly

```asm
0x140003680  sub     rsp, 38h
0x140003684  mov     r10, rcx
0x140003687  mov     r9, r8
0x14000368a  mov     rcx, [rcx+80h]
0x140003691  mov     r8, rdx
0x140003694  mov     rdx, r10
0x140003697  mov     rax, [rcx]
0x14000369a  mov     rax, [rax]
0x14000369d  call    _guard_dispatch_icall
0x1400036a2  add     rsp, 38h
0x1400036a6  retn
```
