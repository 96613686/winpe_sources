# wil::details::RecordReturn(long)

- ea: `0x140002e00`
- end: `0x140002e16`
- name: `?RecordReturn@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ed8`
- `0x140002920`

## pseudocode

```c
__int64 __fastcall wil::details::RecordReturn(wil::details *this)
{
  `wil::details::RecordReturn'::`2'::s_hrErrorLast = (int)this;
  return (unsigned int)_InterlockedIncrement(&`wil::details::RecordReturn'::`2'::s_cErrorCount);
}

```

## disassembly

```asm
0x140002e00  mov     cs:?s_hrErrorLast@?1??RecordReturn@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordReturn(long)'::`2'::s_hrErrorLast
0x140002e06  mov     eax, 1
0x140002e0b  lock xadd cs:?s_cErrorCount@?1??RecordReturn@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordReturn(long)'::`2'::s_cErrorCount
0x140002e13  inc     eax
0x140002e15  retn
```
