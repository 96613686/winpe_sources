# wil::details::ThreadFailureCallbackHolder::IsWatching(void)

- ea: `0x180004c9c`
- end: `0x180004ca4`
- name: `?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ`
- size: `8`
- prototype: `bool __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004004`
- `0x180004c64`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::IsWatching(wil::details::ThreadFailureCallbackHolder *this)
{
  return *((_DWORD *)this + 6) != 0;
}

```

## disassembly

```asm
0x180004c9c  cmp     dword ptr [rcx+18h], 0
0x180004ca0  setnz   al
0x180004ca3  retn
```
