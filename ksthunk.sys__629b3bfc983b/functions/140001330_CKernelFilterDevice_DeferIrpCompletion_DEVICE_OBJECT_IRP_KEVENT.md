# CKernelFilterDevice::DeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,_KEVENT *)

- ea: `0x140001330`
- end: `0x14000135c`
- name: `?DeferIrpCompletion@CKernelFilterDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAU_KEVENT@@@Z`
- size: `44`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, struct _KEVENT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001330`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001345`
- `ntoskrnl!KeSetEvent` at `0x140001345`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::DeferIrpCompletion(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        struct _KEVENT *a3)
{
  if ( a2->PendingReturned )
    KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001330  sub     rsp, 28h
0x140001334  cmp     byte ptr [rdx+41h], 0
0x140001338  mov     rax, r8
0x14000133b  jz      short loc_140001351
0x14000133d  xor     r8d, r8d; Wait
0x140001340  xor     edx, edx; Increment
0x140001342  mov     rcx, rax; Event
0x140001345  call    cs:__imp_KeSetEvent
0x14000134c  nop     dword ptr [rax+rax+00h]
0x140001351  mov     eax, 0C0000016h
0x140001356  add     rsp, 28h
0x14000135a  retn
```
