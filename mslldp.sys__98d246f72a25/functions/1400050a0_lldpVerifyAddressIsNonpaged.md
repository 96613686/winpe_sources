# lldpVerifyAddressIsNonpaged

- ea: `0x1400050a0`
- end: `0x1400050c4`
- name: `lldpVerifyAddressIsNonpaged`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000edc0`
- `0x14000ef10`
- `0x14000f230`
- `0x14000f360`

## callees

- `0x1400050a0`

## import_xrefs

- `ntoskrnl!MmIsNonPagedSystemAddressValid` at `0x1400050ae`
- `ntoskrnl!MmIsNonPagedSystemAddressValid` at `0x1400050ae`

## pseudocode

```c
BOOLEAN __fastcall lldpVerifyAddressIsNonpaged(__int64 a1, void *a2)
{
  if ( (*(_DWORD *)(a1 + 4) & 1) != 0 )
    return MmIsNonPagedSystemAddressValid(a2);
  else
    return 1;
}

```

## disassembly

```asm
0x1400050a0  sub     rsp, 28h
0x1400050a4  mov     eax, [rcx+4]
0x1400050a7  test    al, 1
0x1400050a9  jz      short loc_1400050BC
0x1400050ab  mov     rcx, rdx; VirtualAddress
0x1400050ae  call    cs:__imp_MmIsNonPagedSystemAddressValid
0x1400050b5  nop     dword ptr [rax+rax+00h]
0x1400050ba  jmp     short loc_1400050BE
0x1400050bc  mov     al, 1
0x1400050be  add     rsp, 28h
0x1400050c2  retn
```
