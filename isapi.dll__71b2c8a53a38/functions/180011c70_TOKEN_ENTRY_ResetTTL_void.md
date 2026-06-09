# TOKEN_ENTRY::ResetTTL(void)

- ea: `0x180011c70`
- end: `0x180011c7b`
- name: `?ResetTTL@TOKEN_ENTRY@@UEAAXXZ`
- size: `11`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall TOKEN_ENTRY::ResetTTL(TOKEN_ENTRY *this)
{
  *((_DWORD *)this + 64) = 2;
}

```

## disassembly

```asm
0x180011c70  mov     dword ptr [rcx+100h], 2
0x180011c7a  retn
```
