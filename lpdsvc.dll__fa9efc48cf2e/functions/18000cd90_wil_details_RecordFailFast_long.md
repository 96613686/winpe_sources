# wil::details::RecordFailFast(long)

- ea: `0x18000cd90`
- end: `0x18000cd9c`
- name: `?RecordFailFast@details@wil@@YAHJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ae18`
- `0x18000c830`

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
0x18000cd90  mov     cs:?s_hrErrorLast@?1??RecordFailFast@details@wil@@YAHJ@Z@4JC, ecx; long volatile `wil::details::RecordFailFast(long)'::`2'::s_hrErrorLast
0x18000cd96  mov     eax, 1
0x18000cd9b  retn
```
