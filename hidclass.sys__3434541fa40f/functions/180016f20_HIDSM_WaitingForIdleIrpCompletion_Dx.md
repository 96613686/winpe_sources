# HIDSM_WaitingForIdleIrpCompletion_Dx

- ea: `0x180016f20`
- end: `0x180016f49`
- name: `HIDSM_WaitingForIdleIrpCompletion_Dx`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x180016f32`
- `ntoskrnl!IoCancelIrp` at `0x180016f32`

## pseudocode

```c
__int64 __fastcall HIDSM_WaitingForIdleIrpCompletion_Dx(__int64 a1)
{
  IoCancelIrp(*(PIRP *)(*(_QWORD *)(a1 + 960) + 432LL));
  return 1000;
}

```

## disassembly

```asm
0x180016f20  sub     rsp, 28h
0x180016f24  mov     rcx, [rcx+3C0h]
0x180016f2b  mov     rcx, [rcx+1B0h]; Irp
0x180016f32  call    cs:__imp_IoCancelIrp
0x180016f39  nop     dword ptr [rax+rax+00h]
0x180016f3e  mov     eax, 3E8h
0x180016f43  add     rsp, 28h
0x180016f47  retn
```
