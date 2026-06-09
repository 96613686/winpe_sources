# PmCleanup(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001f970`
- end: `0x14001f994`
- name: `?PmCleanup@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `36`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001f980`
- `ntoskrnl!IofCompleteRequest` at `0x14001f980`

## pseudocode

```c
__int64 __fastcall PmCleanup(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14001f970  sub     rsp, 28h
0x14001f974  mov     rcx, rdx; Irp
0x14001f977  mov     dword ptr [rdx+30h], 0
0x14001f97e  xor     edx, edx; PriorityBoost
0x14001f980  call    cs:__imp_IofCompleteRequest
0x14001f987  nop     dword ptr [rax+rax+00h]
0x14001f98c  xor     eax, eax
0x14001f98e  add     rsp, 28h
0x14001f992  retn
```
