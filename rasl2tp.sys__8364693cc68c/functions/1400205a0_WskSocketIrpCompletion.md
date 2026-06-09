# WskSocketIrpCompletion

- ea: `0x1400205a0`
- end: `0x1400205be`
- name: `WskSocketIrpCompletion`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400205a7`
- `ntoskrnl!IoFreeIrp` at `0x1400205a7`

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
0x1400205a0  sub     rsp, 28h
0x1400205a4  mov     rcx, rdx; Irp
0x1400205a7  call    cs:__imp_IoFreeIrp
0x1400205ae  nop     dword ptr [rax+rax+00h]
0x1400205b3  mov     eax, 0C0000016h
0x1400205b8  add     rsp, 28h
0x1400205bc  retn
```
