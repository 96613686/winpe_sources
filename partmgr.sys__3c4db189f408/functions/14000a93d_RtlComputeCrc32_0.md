# RtlComputeCrc32_0

- ea: `0x14000a93d`
- end: `0x14000a944`
- name: `RtlComputeCrc32_0`
- size: `7`
- prototype: `ULONG __stdcall(ULONG InitialCrc, PUCHAR Buffer, ULONG Length)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000f6e0`
- `0x14000ff58`
- `0x14000ffcc`
- `0x140010380`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14000a93d`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall RtlComputeCrc32_0(ULONG InitialCrc, PUCHAR Buffer, ULONG Length)
{
  return RtlComputeCrc32(InitialCrc, Buffer, Length);
}

```

## disassembly

```asm
0x14000a93d  jmp     cs:__imp_RtlComputeCrc32
```
