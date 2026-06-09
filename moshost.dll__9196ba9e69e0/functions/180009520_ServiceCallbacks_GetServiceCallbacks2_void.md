# ServiceCallbacks::GetServiceCallbacks2(void)

- ea: `0x180009520`
- end: `0x18000952e`
- name: `?GetServiceCallbacks2@ServiceCallbacks@@UEAAPEAUIServiceCallbacks2@@XZ`
- size: `14`
- prototype: `struct IServiceCallbacks2 *__fastcall(ServiceCallbacks *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
struct IServiceCallbacks2 *__fastcall ServiceCallbacks::GetServiceCallbacks2(ServiceCallbacks *this)
{
  return (struct IServiceCallbacks2 *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
}

```

## disassembly

```asm
0x180009520  lea     rdx, [rcx+8]
0x180009524  neg     rcx
0x180009527  sbb     rax, rax
0x18000952a  and     rax, rdx
0x18000952d  retn
```
