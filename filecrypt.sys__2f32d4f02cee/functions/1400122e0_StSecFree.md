# StSecFree

- ea: `0x1400122e0`
- end: `0x140012300`
- name: `StSecFree`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d4c8`
- `0x14000d7a8`
- `0x14000dd14`
- `0x14000dff8`
- `0x14000e104`
- `0x14000e340`
- `0x14000e5e0`
- `0x14000e6cc`
- `0x14000e840`
- `0x14000eb20`

## callees

- `0x1400122e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400122ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400122ee`

## pseudocode

```c
void __fastcall StSecFree(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0x70537453u);
}

```

## disassembly

```asm
0x1400122e0  sub     rsp, 28h
0x1400122e4  test    rcx, rcx
0x1400122e7  jz      short loc_1400122FA
0x1400122e9  mov     edx, 70537453h; Tag
0x1400122ee  call    cs:__imp_ExFreePoolWithTag
0x1400122f5  nop     dword ptr [rax+rax+00h]
0x1400122fa  add     rsp, 28h
0x1400122fe  retn
```
