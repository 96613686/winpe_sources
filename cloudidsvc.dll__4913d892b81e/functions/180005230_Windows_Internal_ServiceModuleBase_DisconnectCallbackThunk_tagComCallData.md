# Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)

- ea: `0x180005230`
- end: `0x18000523c`
- name: `?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z`
- size: `12`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(struct tagComCallData *a1)
{
  return (*(__int64 (__fastcall **)(struct tagComCallData *))(*(_QWORD *)&a1->dwDispid + 8LL))(a1);
}

```

## disassembly

```asm
0x180005230  mov     rax, [rcx]
0x180005233  mov     rax, [rax+8]
0x180005237  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
