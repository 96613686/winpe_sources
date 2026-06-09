# TOKEN_ENTRY::GetFlushed(void)

- ea: `0x1800113f0`
- end: `0x1800113f7`
- name: `?GetFlushed@TOKEN_ENTRY@@UEBAHXZ`
- size: `7`
- prototype: `__int64 __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall TOKEN_ENTRY::GetFlushed(TOKEN_ENTRY *this)
{
  return *((unsigned int *)this + 63);
}

```

## disassembly

```asm
0x1800113f0  mov     eax, [rcx+0FCh]
0x1800113f6  retn
```
