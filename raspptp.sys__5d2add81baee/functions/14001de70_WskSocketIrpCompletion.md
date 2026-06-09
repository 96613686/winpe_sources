# WskSocketIrpCompletion

- ea: `0x14001de70`
- end: `0x14001de8e`
- name: `WskSocketIrpCompletion`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001de77`
- `ntoskrnl!IoFreeIrp` at `0x14001de77`

## pseudocode

```c
__int64 __fastcall WskSocketIrpCompletion(__int64 a1, IRP *a2)
{
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001de70  sub     rsp, 28h
0x14001de74  mov     rcx, rdx; Irp
0x14001de77  call    cs:__imp_IoFreeIrp
0x14001de7e  nop     dword ptr [rax+rax+00h]
0x14001de83  mov     eax, 0C0000016h
0x14001de88  add     rsp, 28h
0x14001de8c  retn
```
