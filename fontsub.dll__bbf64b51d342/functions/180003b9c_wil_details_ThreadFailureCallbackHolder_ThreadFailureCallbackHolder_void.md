# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180003b9c`
- end: `0x180003bb0`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037d4`

## callees

- `0x180003b9c`
- `0x180006a54`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  if ( *((_DWORD *)this + 6) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(this);
}

```

## disassembly

```asm
0x180003b9c  sub     rsp, 28h
0x180003ba0  cmp     dword ptr [rcx+18h], 0
0x180003ba4  jz      short loc_180003BAB
0x180003ba6  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180003bab  add     rsp, 28h
0x180003baf  retn
```
