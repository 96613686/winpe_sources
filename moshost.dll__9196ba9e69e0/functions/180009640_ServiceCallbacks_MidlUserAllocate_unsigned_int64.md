# ServiceCallbacks::MidlUserAllocate(unsigned __int64)

- ea: `0x180009640`
- end: `0x18000964a`
- name: `?MidlUserAllocate@ServiceCallbacks@@UEAAPEAX_K@Z`
- size: `10`
- prototype: `void *__fastcall(ServiceCallbacks *this, size_t)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009643`

## pseudocode

```c
void *__fastcall ServiceCallbacks::MidlUserAllocate(ServiceCallbacks *this, size_t a2)
{
  return malloc(a2);
}

```

## disassembly

```asm
0x180009640  mov     rcx, rdx
0x180009643  jmp     cs:__imp_malloc
```
