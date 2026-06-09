# wil::details::RecordReturn(long)

- ea: `0x1800046a4`
- end: `0x1800046ba`
- name: `?RecordReturn@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002624`
- `0x180003e7c`

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
0x1800046a4  mov     cs:?s_hrErrorLast@?1??RecordReturn@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordReturn(long)'::`2'::s_hrErrorLast
0x1800046aa  mov     eax, 1
0x1800046af  lock xadd cs:?s_cErrorCount@?1??RecordReturn@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordReturn(long)'::`2'::s_cErrorCount
0x1800046b7  inc     eax
0x1800046b9  retn
```
