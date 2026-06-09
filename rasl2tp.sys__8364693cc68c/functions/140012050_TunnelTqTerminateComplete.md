# TunnelTqTerminateComplete

- ea: `0x140012050`
- end: `0x140012072`
- name: `TunnelTqTerminateComplete`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012060`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012060`

## pseudocode

```c
void __fastcall TunnelTqTerminateComplete(__int64 a1, __int64 a2)
{
  --*(_DWORD *)(a2 + 400);
  ExFreePoolWithTag((PVOID)(a1 - 16), 0);
}

```

## disassembly

```asm
0x140012050  sub     rsp, 28h
0x140012054  dec     dword ptr [rdx+190h]
0x14001205a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001205e  xor     edx, edx; Tag
0x140012060  call    cs:__imp_ExFreePoolWithTag
0x140012067  nop     dword ptr [rax+rax+00h]
0x14001206c  add     rsp, 28h
0x140012070  retn
```
