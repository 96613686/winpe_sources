# ServiceCallbacks::MidlUserFree(void *)

- ea: `0x180009650`
- end: `0x18000965a`
- name: `?MidlUserFree@ServiceCallbacks@@UEAAXPEAX@Z`
- size: `10`
- prototype: `void __fastcall(ServiceCallbacks *__hidden this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009653`

## pseudocode

```c
void __fastcall ServiceCallbacks::MidlUserFree(ServiceCallbacks *this, void *a2)
{
  free(a2);
}

```

## disassembly

```asm
0x180009650  mov     rcx, rdx
0x180009653  jmp     cs:__imp_free
```
