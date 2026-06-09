# KsFilterCreateNode_wrapper

- ea: `0x18006fe80`
- end: `0x18006feed`
- name: `KsFilterCreateNode_wrapper`
- size: `109`
- prototype: `NTSTATUS __fastcall(PKSFILTER Filter, KSNODE_DESCRIPTOR *NodeDescriptor, PULONG NodeID)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019cb0`
- `0x18003d270`
- `0x18006fe80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006fea2`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006fea2`

## string_xrefs

- `0x18006feb9`: `KsFilterCreateNode should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
NTSTATUS __fastcall KsFilterCreateNode_wrapper(PKSFILTER Filter, KSNODE_DESCRIPTOR *NodeDescriptor, PULONG NodeID)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsFilterCreateNode should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsFilterCreateNode(Filter, NodeDescriptor, NodeID);
}

```

## disassembly

```asm
0x18006fe80  mov     [rsp+arg_0], rbx
0x18006fe85  mov     [rsp+arg_8], rsi
0x18006fe8a  push    rdi
0x18006fe8b  sub     rsp, 20h
0x18006fe8f  mov     eax, cs:KsXdvExtLevel
0x18006fe95  mov     rbx, r8
0x18006fe98  mov     rdi, rdx
0x18006fe9b  mov     rsi, rcx
0x18006fe9e  test    al, 8
0x18006fea0  jz      short loc_18006FECE
0x18006fea2  call    cs:__imp_KeGetCurrentIrql
0x18006fea9  nop     dword ptr [rax+rax+00h]
0x18006feae  test    al, al
0x18006feb0  jz      short loc_18006FECE
0x18006feb2  mov     rax, cs:KsVerifierUtilTable
0x18006feb9  lea     rcx, aKsfiltercreate; "KsFilterCreateNode should only be calle"...
0x18006fec0  mov     edx, 81009h
0x18006fec5  mov     rax, [rax+60h]
0x18006fec9  call    _guard_dispatch_icall
0x18006fece  mov     r8, rbx; NodeID
0x18006fed1  mov     rdx, rdi; NodeDescriptor
0x18006fed4  mov     rcx, rsi; Filter
0x18006fed7  call    KsFilterCreateNode
0x18006fedc  mov     rbx, [rsp+28h+arg_0]
0x18006fee1  mov     rsi, [rsp+28h+arg_8]
0x18006fee6  add     rsp, 20h
0x18006feea  pop     rdi
0x18006feeb  retn
```
