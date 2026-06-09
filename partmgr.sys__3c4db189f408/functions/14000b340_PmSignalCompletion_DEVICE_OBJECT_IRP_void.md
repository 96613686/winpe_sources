# PmSignalCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14000b340`
- end: `0x14000b363`
- name: `?PmSignalCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `35`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000b34c`
- `ntoskrnl!KeSetEvent` at `0x14000b34c`

## pseudocode

```c
__int64 __fastcall PmSignalCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000b340  sub     rsp, 28h
0x14000b344  mov     rcx, r8; Event
0x14000b347  xor     edx, edx; Increment
0x14000b349  xor     r8d, r8d; Wait
0x14000b34c  call    cs:__imp_KeSetEvent
0x14000b353  nop     dword ptr [rax+rax+00h]
0x14000b358  mov     eax, 0C0000016h
0x14000b35d  add     rsp, 28h
0x14000b361  retn
```
