# CdpDisplayClose

- ea: `0x140008c80`
- end: `0x140008cc0`
- name: `CdpDisplayClose`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008c8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008c8b`
- `ntoskrnl!IofCompleteRequest` at `0x140008cab`
- `ntoskrnl!IofCompleteRequest` at `0x140008cab`

## pseudocode

```c
__int64 __fastcall CdpDisplayClose(void *a1, IRP *a2)
{
  ExFreePoolWithTag(a1, 0);
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x140008c80  push    rbx
0x140008c82  sub     rsp, 20h
0x140008c86  mov     rbx, rdx
0x140008c89  xor     edx, edx; Tag
0x140008c8b  call    cs:__imp_ExFreePoolWithTag
0x140008c92  nop     dword ptr [rax+rax+00h]
0x140008c97  xor     edx, edx; PriorityBoost
0x140008c99  mov     dword ptr [rbx+30h], 0
0x140008ca0  mov     rcx, rbx; Irp
0x140008ca3  mov     qword ptr [rbx+38h], 0
0x140008cab  call    cs:__imp_IofCompleteRequest
0x140008cb2  nop     dword ptr [rax+rax+00h]
0x140008cb7  xor     eax, eax
0x140008cb9  add     rsp, 20h
0x140008cbd  pop     rbx
0x140008cbe  retn
```
