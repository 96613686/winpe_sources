# PmFail(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000bad0`
- end: `0x14000baf7`
- name: `?PmFail@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `39`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000bae0`
- `ntoskrnl!IofCompleteRequest` at `0x14000bae0`

## pseudocode

```c
__int64 __fastcall PmFail(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  a2->IoStatus.Status = -1073741808;
  IofCompleteRequest(a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x14000bad0  sub     rsp, 28h
0x14000bad4  mov     rcx, rdx; Irp
0x14000bad7  mov     dword ptr [rdx+30h], 0C0000010h
0x14000bade  xor     edx, edx; PriorityBoost
0x14000bae0  call    cs:__imp_IofCompleteRequest
0x14000bae7  nop     dword ptr [rax+rax+00h]
0x14000baec  mov     eax, 0C0000010h
0x14000baf1  add     rsp, 28h
0x14000baf5  retn
```
