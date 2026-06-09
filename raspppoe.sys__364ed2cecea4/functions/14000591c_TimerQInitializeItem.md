# TimerQInitializeItem

- ea: `0x14000591c`
- end: `0x140005924`
- name: `TimerQInitializeItem`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140016310`
- `0x140016534`
- `0x140017740`
- `0x140017a00`

## pseudocode

```c
void __fastcall TimerQInitializeItem(_QWORD *a1)
{
  a1[1] = a1;
  *a1 = a1;
}

```

## disassembly

```asm
0x14000591c  mov     [rcx+8], rcx
0x140005920  mov     [rcx], rcx
0x140005923  retn
```
