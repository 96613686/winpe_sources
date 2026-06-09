# pcmReadSample_M08M16

- ea: `0x180012280`
- end: `0x18001228c`
- name: `pcmReadSample_M08M16`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
__int64 __fastcall pcmReadSample_M08M16(__int64 a1, _BYTE *a2)
{
  *a2 = *(_BYTE *)(a1 + 1) ^ 0x80;
  return a1 + 2;
}

```

## disassembly

```asm
0x180012280  mov     al, [rcx+1]
0x180012283  xor     al, 80h
0x180012285  mov     [rdx], al
0x180012287  lea     rax, [rcx+2]
0x18001228b  retn
```
