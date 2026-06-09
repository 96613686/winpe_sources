# wil::details::RecordFailFast(long)

- ea: `0x180005550`
- end: `0x18000555c`
- name: `?RecordFailFast@details@wil@@YAHJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800024e0`
- `0x180004d90`

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
0x180005550  mov     cs:?s_hrErrorLast@?1??RecordFailFast@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordFailFast(long)'::`2'::s_hrErrorLast
0x180005556  mov     eax, 1
0x18000555b  retn
```
