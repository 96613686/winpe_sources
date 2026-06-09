# CallStackInfo::CallStackInfo(void)

- ea: `0x180007db0`
- end: `0x180007db4`
- name: `??0CallStackInfo@@QEAA@XZ`
- size: `4`
- prototype: `CallStackInfo *__fastcall(CallStackInfo *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180007ef0`
- `0x18000854c`

## pseudocode

```c
CallStackInfo *__fastcall CallStackInfo::CallStackInfo(CallStackInfo *this)
{
  return this;
}

```

## disassembly

```asm
0x180007db0  mov     rax, rcx
0x180007db3  retn
```
