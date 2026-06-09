# TOKEN_ENTRY::SetFlushed(void)

- ea: `0x180011c90`
- end: `0x180011c9b`
- name: `?SetFlushed@TOKEN_ENTRY@@UEAAXXZ`
- size: `11`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall TOKEN_ENTRY::SetFlushed(TOKEN_ENTRY *this)
{
  *((_DWORD *)this + 63) = 1;
}

```

## disassembly

```asm
0x180011c90  mov     dword ptr [rcx+0FCh], 1
0x180011c9a  retn
```
