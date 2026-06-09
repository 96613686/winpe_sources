# wil::ThreadFailureCache::~ThreadFailureCache(void)

- ea: `0x1800046f8`
- end: `0x18000471e`
- name: `??1ThreadFailureCache@wil@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(wil::ThreadFailureCache *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004518`
- `0x180004600`
- `0x180004ba0`
- `0x18000de34`

## callees

- `0x180004724`
- `0x1800081f8`

## pseudocode

```c
void __fastcall wil::ThreadFailureCache::~ThreadFailureCache(wil::ThreadFailureCache *this)
{
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::ThreadFailureCache *)((char *)this + 176));
  wil::details::shared_buffer::reset((wil::ThreadFailureCache *)((char *)this + 160));
}

```

## disassembly

```asm
0x1800046f8  push    rbx
0x1800046fa  sub     rsp, 20h
0x1800046fe  mov     rbx, rcx
0x180004701  add     rcx, 0B0h; this
0x180004708  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000470d  lea     rcx, [rbx+0A0h]; this
0x180004714  add     rsp, 20h
0x180004718  pop     rbx
0x180004719  jmp     ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
```
