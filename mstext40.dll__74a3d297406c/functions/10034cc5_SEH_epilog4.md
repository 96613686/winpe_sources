# __SEH_epilog4

- ea: `0x10034cc5`
- end: `0x10034cd9`
- name: `__SEH_epilog4`
- size: `20`
- prototype: ``
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x1002e1ef`
- `0x1002e384`
- `0x1002e746`
- `0x1002eac8`
- `0x1002eb6e`
- `0x1002ef30`
- `0x1002f122`
- `0x10032330`
- `0x10033cf7`
- `0x100344f8`
- `0x10034efc`
- `0x10035fac`
- `0x100373d2`
- `0x10037d26`
- `0x1003a190`
- `0x1003a31c`
- `0x1003b7cd`
- `0x1003b9aa`
- `0x1003bafa`
- `0x1003bbde`
- `0x1003c2b7`
- `0x1003cbc8`
- `0x1003cc3f`
- `0x1003cd5e`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void _SEH_epilog4()
{
  __asm { retn }
}

```

## disassembly

```asm
0x10034cc5  mov     ecx, [ebp-10h]
0x10034cc8  mov     large fs:0, ecx
0x10034ccf  pop     ecx
0x10034cd0  pop     edi
0x10034cd1  pop     edi
0x10034cd2  pop     esi
0x10034cd3  pop     ebx
0x10034cd4  mov     esp, ebp
0x10034cd6  pop     ebp
0x10034cd7  push    ecx
0x10034cd8  retn
```
