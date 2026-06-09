# CdCompleteRoutineFreeIrp

- ea: `0x14000e210`
- end: `0x14000e22e`
- name: `CdCompleteRoutineFreeIrp`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000e217`
- `ntoskrnl!IoFreeIrp` at `0x14000e217`

## pseudocode

```c
__int64 __fastcall CdCompleteRoutineFreeIrp(__int64 a1, IRP *a2)
{
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000e210  sub     rsp, 28h
0x14000e214  mov     rcx, rdx; Irp
0x14000e217  call    cs:__imp_IoFreeIrp
0x14000e21e  nop     dword ptr [rax+rax+00h]
0x14000e223  mov     eax, 0C0000016h
0x14000e228  add     rsp, 28h
0x14000e22c  retn
```
