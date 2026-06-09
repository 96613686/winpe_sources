# wil::details::RecordFailFast(long)

- ea: `0x140002dd0`
- end: `0x140002ddc`
- name: `?RecordFailFast@details@wil@@YAHJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140002920`

## pseudocode

```c
__int64 __fastcall wil::details::RecordFailFast(wil::details *this)
{
  `wil::details::RecordFailFast'::`2'::s_hrErrorLast = (int)this;
  return 1;
}

```

## disassembly

```asm
0x140002dd0  mov     cs:?s_hrErrorLast@?1??RecordFailFast@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordFailFast(long)'::`2'::s_hrErrorLast
0x140002dd6  mov     eax, 1
0x140002ddb  retn
```
