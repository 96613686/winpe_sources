# RdpBusDeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140001010`
- end: `0x140001036`
- name: `?RdpBusDeferIrpCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `38`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000101f`
- `ntoskrnl!KeSetEvent` at `0x14000101f`

## pseudocode

```c
__int64 __fastcall RdpBusDeferIrpCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 1, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001010  sub     rsp, 28h
0x140001014  mov     rcx, r8; Event
0x140001017  mov     edx, 1; Increment
0x14000101c  xor     r8d, r8d; Wait
0x14000101f  call    cs:__imp_KeSetEvent
0x140001026  nop     dword ptr [rax+rax+00h]
0x14000102b  mov     eax, 0C0000016h
0x140001030  add     rsp, 28h
0x140001034  retn
```
