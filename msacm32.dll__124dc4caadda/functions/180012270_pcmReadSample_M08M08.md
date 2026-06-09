# pcmReadSample_M08M08

- ea: `0x180012270`
- end: `0x180012279`
- name: `pcmReadSample_M08M08`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
_BYTE *__fastcall pcmReadSample_M08M08(_BYTE *a1, _BYTE *a2)
{
  *a2 = *a1;
  return a1 + 1;
}

```

## disassembly

```asm
0x180012270  mov     al, [rcx]
0x180012272  mov     [rdx], al
0x180012274  lea     rax, [rcx+1]
0x180012278  retn
```
