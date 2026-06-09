# FreeEAPConfigInputFieldArray

- ea: `0x18002e80c`
- end: `0x18002e827`
- name: `FreeEAPConfigInputFieldArray`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025e5c`

## callees

- `0x18001a4dc`
- `0x18002e830`

## pseudocode

```c
__int64 __fastcall FreeEAPConfigInputFieldArray(__int64 *a1)
{
  FreeEAPConfigInputFieldArrayFields(a1);
  return FreeOneXOrEapMemory(a1);
}

```

## disassembly

```asm
0x18002e80c  push    rbx
0x18002e80e  sub     rsp, 20h
0x18002e812  mov     rbx, rcx
0x18002e815  call    FreeEAPConfigInputFieldArrayFields
0x18002e81a  mov     rcx, rbx
0x18002e81d  add     rsp, 20h
0x18002e821  pop     rbx
0x18002e822  jmp     FreeOneXOrEapMemory
```
