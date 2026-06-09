# CDirectMusicUMAPort::AddRef(void)

- ea: `0x18001d9d0`
- end: `0x18001d9e0`
- name: `?AddRef@CDirectMusicUMAPort@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CDirectMusicUMAPort *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d9f0`
- `0x18001da10`
- `0x18001da30`
- `0x18001da50`
- `0x18001da70`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::AddRef(CDirectMusicUMAPort *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 104);
}

```

## disassembly

```asm
0x18001d9d0  mov     eax, 1
0x18001d9d5  lock xadd [rcx+1A0h], eax
0x18001d9dd  inc     eax
0x18001d9df  retn
```
