# SpFreeContextBuffer

- ea: `0x1800024c0`
- end: `0x1800024c7`
- name: `SpFreeContextBuffer`
- size: `7`
- prototype: `SECURITY_STATUS __stdcall(PVOID pvContextBuffer)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x1800024c0`

## pseudocode

```c
// attributes: thunk
SECURITY_STATUS __stdcall SpFreeContextBuffer(PVOID pvContextBuffer)
{
  return FreeContextBuffer(pvContextBuffer);
}

```

## disassembly

```asm
0x1800024c0  jmp     cs:__imp_FreeContextBuffer
```
