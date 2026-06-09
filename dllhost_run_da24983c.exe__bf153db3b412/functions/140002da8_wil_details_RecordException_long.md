# wil::details::RecordException(long)

- ea: `0x140002da8`
- end: `0x140002dbe`
- name: `?RecordException@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140002920`

## pseudocode

```c
__int64 __fastcall wil::details::RecordException(wil::details *this)
{
  `wil::details::RecordException'::`2'::s_hrErrorLast = (int)this;
  return (unsigned int)_InterlockedIncrement(&`wil::details::RecordException'::`2'::s_cErrorCount);
}

```

## disassembly

```asm
0x140002da8  mov     cs:?s_hrErrorLast@?1??RecordException@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordException(long)'::`2'::s_hrErrorLast
0x140002dae  mov     eax, 1
0x140002db3  lock xadd cs:?s_cErrorCount@?1??RecordException@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordException(long)'::`2'::s_cErrorCount
0x140002dbb  inc     eax
0x140002dbd  retn
```
