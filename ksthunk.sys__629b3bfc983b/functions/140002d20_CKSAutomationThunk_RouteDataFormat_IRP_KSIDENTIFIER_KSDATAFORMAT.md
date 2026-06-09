# CKSAutomationThunk::RouteDataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x140002d20`
- end: `0x140002d48`
- name: `?RouteDataFormat@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003770`

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
0x140002d20  sub     rsp, 38h
0x140002d24  mov     r10, rcx
0x140002d27  mov     r9, r8
0x140002d2a  mov     rcx, [rcx+80h]
0x140002d31  mov     r8, rdx
0x140002d34  mov     rdx, r10
0x140002d37  mov     rax, [rcx]
0x140002d3a  mov     rax, [rax]
0x140002d3d  call    _guard_dispatch_icall
0x140002d42  add     rsp, 38h
0x140002d46  retn
```
