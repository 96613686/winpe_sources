# DfscSystemControl

- ea: `0x140012ba0`
- end: `0x140012bc7`
- name: `DfscSystemControl`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140012bb0`
- `ntoskrnl!IofCompleteRequest` at `0x140012bb0`

## pseudocode

```c
__int64 __fastcall DfscSystemControl(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = -1073741637;
  IofCompleteRequest(a2, 0);
  return 3221225659LL;
}

```

## disassembly

```asm
0x140012ba0  sub     rsp, 28h
0x140012ba4  mov     rcx, rdx; Irp
0x140012ba7  mov     dword ptr [rdx+30h], 0C00000BBh
0x140012bae  xor     edx, edx; PriorityBoost
0x140012bb0  call    cs:__imp_IofCompleteRequest
0x140012bb7  nop     dword ptr [rax+rax+00h]
0x140012bbc  mov     eax, 0C00000BBh
0x140012bc1  add     rsp, 28h
0x140012bc5  retn
```
