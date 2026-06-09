# ServiceCallbacks::GetProxyResolver(IClientProxyResolver * *)

- ea: `0x180009500`
- end: `0x180009516`
- name: `?GetProxyResolver@ServiceCallbacks@@UEAAJPEAPEAUIClientProxyResolver@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(ServiceCallbacks *__hidden this, struct IClientProxyResolver **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::GetProxyResolver(ServiceCallbacks *this, struct IClientProxyResolver **a2)
{
  return (*(__int64 (__fastcall **)(__int64, struct IClientProxyResolver **))(*(_QWORD *)qword_1800185D0 + 240LL))(
           qword_1800185D0,
           a2);
}

```

## disassembly

```asm
0x180009500  mov     rcx, cs:qword_1800185D0
0x180009507  mov     rax, [rcx]
0x18000950a  mov     rax, [rax+0F0h]
0x180009511  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
