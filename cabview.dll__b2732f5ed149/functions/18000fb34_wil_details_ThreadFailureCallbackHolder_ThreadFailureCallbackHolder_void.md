# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000fb34`
- end: `0x18000fb48`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f968`

## callees

- `0x18000fb34`
- `0x180011a3c`

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
0x18000fb34  sub     rsp, 28h
0x18000fb38  cmp     dword ptr [rcx+18h], 0
0x18000fb3c  jz      short loc_18000FB43
0x18000fb3e  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000fb43  add     rsp, 28h
0x18000fb47  retn
```
