# CallStackInfo::CallStackInfo(void)

- ea: `0x180001ce0`
- end: `0x180001ce4`
- name: `??0CallStackInfo@@QEAA@XZ`
- size: `4`
- prototype: `CallStackInfo *__fastcall(CallStackInfo *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b50`
- `0x180001c60`

## pseudocode

```c
CallStackInfo *__fastcall CallStackInfo::CallStackInfo(CallStackInfo *this)
{
  return this;
}

```

## disassembly

```asm
0x180001ce0  mov     rax, rcx
0x180001ce3  retn
```
