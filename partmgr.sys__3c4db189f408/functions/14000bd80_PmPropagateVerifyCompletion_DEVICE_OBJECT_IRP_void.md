# PmPropagateVerifyCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14000bd80`
- end: `0x14000bd9e`
- name: `?PmPropagateVerifyCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `30`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000bd87`
- `ntoskrnl!IoFreeIrp` at `0x14000bd87`

## pseudocode

```c
__int64 __fastcall PmPropagateVerifyCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000bd80  sub     rsp, 28h
0x14000bd84  mov     rcx, rdx; Irp
0x14000bd87  call    cs:__imp_IoFreeIrp
0x14000bd8e  nop     dword ptr [rax+rax+00h]
0x14000bd93  mov     eax, 0C0000016h
0x14000bd98  add     rsp, 28h
0x14000bd9c  retn
```
