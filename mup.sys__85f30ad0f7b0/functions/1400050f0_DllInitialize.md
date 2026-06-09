# DllInitialize

- ea: `0x1400050f0`
- end: `0x140005102`
- name: `DllInitialize`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllInitialize()
{
  return MupiInitSuccessful == 0 ? 0xC0000010 : 0;
}

```

## disassembly

```asm
0x1400050f0  mov     al, cs:MupiInitSuccessful
0x1400050f6  neg     al
0x1400050f8  sbb     eax, eax
0x1400050fa  not     eax
0x1400050fc  and     eax, 0C0000010h
0x140005101  retn
```
