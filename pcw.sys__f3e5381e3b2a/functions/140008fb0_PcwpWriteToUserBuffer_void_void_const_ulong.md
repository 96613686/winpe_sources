# PcwpWriteToUserBuffer(void *,void const *,ulong)

- ea: `0x140008fb0`
- end: `0x140008fc7`
- name: `?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z`
- size: `23`
- prototype: `int(void *, const void *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140008224`
- `0x1400082ec`
- `0x1400083e4`
- `0x14000868c`
- `0x140008840`
- `0x140008c48`

## callees

- `0x140008008`
- `0x140008fb0`

## pseudocode

```c
__int64 __fastcall PcwpWriteToUserBuffer(void *a1, void *a2, unsigned int a3)
{
  RtlCopyToUser(a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x140008fb0  sub     rsp, 28h
0x140008fb4  mov     r8d, r8d; Size
0x140008fb7  call    RtlCopyToUser
0x140008fbc  nop
0x140008fbd  xor     eax, eax
0x140008fbf  jmp     short $+2
0x140008fc1  add     rsp, 28h
0x140008fc5  retn
```
