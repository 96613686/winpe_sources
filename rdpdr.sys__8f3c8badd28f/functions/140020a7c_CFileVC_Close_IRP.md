# CFileVC::Close(_IRP *)

- ea: `0x140020a7c`
- end: `0x140020aa8`
- name: `?Close@CFileVC@@QEAAJPEAU_IRP@@@Z`
- size: `44`
- prototype: `int(CFileVC *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400254c0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020a94`
- `ntoskrnl!IofCompleteRequest` at `0x140020a94`

## pseudocode

```c
__int64 __fastcall CFileVC::Close(CFileVC *this, struct _IRP *a2)
{
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140020a7c  sub     rsp, 28h
0x140020a80  mov     rcx, rdx; Irp
0x140020a83  mov     dword ptr [rdx+30h], 0
0x140020a8a  mov     qword ptr [rdx+38h], 0
0x140020a92  xor     edx, edx; PriorityBoost
0x140020a94  call    cs:__imp_IofCompleteRequest
0x140020a9b  nop     dword ptr [rax+rax+00h]
0x140020aa0  xor     eax, eax
0x140020aa2  add     rsp, 28h
0x140020aa6  retn
```
