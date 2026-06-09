# CWinTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180005c30`
- end: `0x180005c3c`
- name: `?Start@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `12`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Start(CWinTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  return (*(__int64 (__fastcall **)(CWinTaskHandler *, struct IUnknown *, unsigned __int16 *))(*(_QWORD *)this + 72LL))(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x180005c30  mov     rax, [rcx]
0x180005c33  mov     rax, [rax+48h]
0x180005c37  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
