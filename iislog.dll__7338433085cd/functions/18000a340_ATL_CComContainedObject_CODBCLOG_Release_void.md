# ATL::CComContainedObject<CODBCLOG>::Release(void)

- ea: `0x18000a340`
- end: `0x18000a350`
- name: `?Release@?$CComContainedObject@VCODBCLOG@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a360`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CODBCLOG>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000a340  mov     rcx, [rcx+8]
0x18000a344  mov     rax, [rcx]
0x18000a347  mov     rax, [rax+10h]
0x18000a34b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
