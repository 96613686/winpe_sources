# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140006190`
- end: `0x1400061a5`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005884`

## callees

- `0x140006190`
- `0x14000cb58`

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
0x140006190  sub     rsp, 28h
0x140006194  cmp     dword ptr [rcx+18h], 0
0x140006198  jz      short loc_1400061A0
0x14000619a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14000619f  nop
0x1400061a0  add     rsp, 28h
0x1400061a4  retn
```
