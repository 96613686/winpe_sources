# wil::details::RecordLog(long)

- ea: `0x140002de4`
- end: `0x140002dfa`
- name: `?RecordLog@details@wil@@YAHJ@Z`
- size: `22`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140002920`

## pseudocode

```c
__int64 __fastcall wil::details::RecordLog(wil::details *this)
{
  `wil::details::RecordLog'::`2'::s_hrErrorLast = (int)this;
  return (unsigned int)_InterlockedIncrement(&`wil::details::RecordLog'::`2'::s_cErrorCount);
}

```

## disassembly

```asm
0x140002de4  mov     cs:?s_hrErrorLast@?1??RecordLog@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordLog(long)'::`2'::s_hrErrorLast
0x140002dea  mov     eax, 1
0x140002def  lock xadd cs:?s_cErrorCount@?1??RecordLog@details@wil@@YAHJ@Z@4JC, eax; long volatile `wil::details::RecordLog(long)'::`2'::s_cErrorCount
0x140002df7  inc     eax
0x140002df9  retn
```
