# wil::details::registry_watcher_state::`scalar deleting destructor'(uint)

- ea: `0x180008464`
- end: `0x180008488`
- name: `??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z`
- size: `36`
- prototype: `wil::details::registry_watcher_state *__fastcall(wil::details::registry_watcher_state *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000828c`
- `0x180008740`
- `0x180008afc`
- `0x180008c58`

## callees

- `0x1800024d0`
- `0x18000832c`

## pseudocode

```c
wil::details::registry_watcher_state *__fastcall wil::details::registry_watcher_state::`scalar deleting destructor'(
        wil::details::registry_watcher_state *this)
{
  wil::details::registry_watcher_state::~registry_watcher_state(this);
  operator delete(this, (const struct std::nothrow_t *)0xA0);
  return this;
}

```

## disassembly

```asm
0x180008464  push    rbx
0x180008466  sub     rsp, 20h
0x18000846a  mov     rbx, rcx
0x18000846d  call    ??1registry_watcher_state@details@wil@@QEAA@XZ; wil::details::registry_watcher_state::~registry_watcher_state(void)
0x180008472  mov     edx, 0A0h; struct std::nothrow_t *
0x180008477  mov     rcx, rbx; void *
0x18000847a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000847f  mov     rax, rbx
0x180008482  add     rsp, 20h
0x180008486  pop     rbx
0x180008487  retn
```
