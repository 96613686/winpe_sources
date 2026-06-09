# CdCompleteMdl

- ea: `0x14000b62c`
- end: `0x14000b67b`
- name: `CdCompleteMdl`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001240`

## callees

- `0x140001160`

## import_xrefs

- `ntoskrnl!CcMdlReadComplete` at `0x14000b64b`
- `ntoskrnl!CcMdlReadComplete` at `0x14000b64b`

## pseudocode

```c
__int64 __fastcall CdCompleteMdl(void *a1, IRP *a2)
{
  CcMdlReadComplete(a2->Tail.Overlay.CurrentStackLocation->FileObject, a2->MdlAddress);
  a2->MdlAddress = 0;
  CdCompleteRequest(a1, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000b62c  mov     [rsp+arg_0], rbx
0x14000b631  push    rdi
0x14000b632  sub     rsp, 20h
0x14000b636  mov     rdi, rcx
0x14000b639  mov     rbx, rdx
0x14000b63c  mov     rcx, [rdx+0B8h]
0x14000b643  mov     rdx, [rdx+8]; MdlChain
0x14000b647  mov     rcx, [rcx+30h]; FileObject
0x14000b64b  call    cs:__imp_CcMdlReadComplete
0x14000b652  nop     dword ptr [rax+rax+00h]
0x14000b657  xor     r8d, r8d
0x14000b65a  mov     qword ptr [rbx+8], 0
0x14000b662  mov     rdx, rbx
0x14000b665  mov     rcx, rdi
0x14000b668  call    CdCompleteRequest
0x14000b66d  mov     rbx, [rsp+28h+arg_0]
0x14000b672  xor     eax, eax
0x14000b674  add     rsp, 20h
0x14000b678  pop     rdi
0x14000b679  retn
```
