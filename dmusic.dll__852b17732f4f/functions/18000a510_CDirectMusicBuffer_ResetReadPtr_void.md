# CDirectMusicBuffer::ResetReadPtr(void)

- ea: `0x18000a510`
- end: `0x18000a51a`
- name: `?ResetReadPtr@CDirectMusicBuffer@@UEAAJXZ`
- size: `10`
- prototype: `__int64 __fastcall(CDirectMusicBuffer *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDirectMusicBuffer::ResetReadPtr(CDirectMusicBuffer *this)
{
  *((_DWORD *)this + 12) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000a510  mov     dword ptr [rcx+30h], 0
0x18000a517  xor     eax, eax
0x18000a519  retn
```
