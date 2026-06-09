# pcmReadSample_S16S16

- ea: `0x180006e80`
- end: `0x180006e89`
- name: `pcmReadSample_S16S16`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
_DWORD *__fastcall pcmReadSample_S16S16(_DWORD *a1, _DWORD *a2)
{
  *a2 = *a1;
  return a1 + 1;
}

```

## disassembly

```asm
0x180006e80  mov     eax, [rcx]
0x180006e82  mov     [rdx], eax
0x180006e84  lea     rax, [rcx+4]
0x180006e88  retn
```
