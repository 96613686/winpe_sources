# DllUnload

- ea: `0x18000f010`
- end: `0x18000f040`
- name: `DllUnload`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001b9c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000f020`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f020`

## pseudocode

```c
__int64 DllUnload()
{
  ExFreePoolWithTag(Globals.Buffer, 0x48545541u);
  SDT_Cleanup(P);
  return 0;
}

```

## disassembly

```asm
0x18000f010  sub     rsp, 28h
0x18000f014  mov     rcx, cs:Globals.Buffer; P
0x18000f01b  mov     edx, 48545541h; Tag
0x18000f020  call    cs:__imp_ExFreePoolWithTag
0x18000f027  nop     dword ptr [rax+rax+00h]
0x18000f02c  mov     rcx, qword ptr cs:P; P
0x18000f033  call    SDT_Cleanup
0x18000f038  xor     eax, eax
0x18000f03a  add     rsp, 28h
0x18000f03e  retn
```
