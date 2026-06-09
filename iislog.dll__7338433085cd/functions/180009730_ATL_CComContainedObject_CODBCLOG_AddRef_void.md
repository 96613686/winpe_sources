# ATL::CComContainedObject<CODBCLOG>::AddRef(void)

- ea: `0x180009730`
- end: `0x180009740`
- name: `?AddRef@?$CComContainedObject@VCODBCLOG@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009750`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CODBCLOG>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180009730  mov     rcx, [rcx+8]
0x180009734  mov     rax, [rcx]
0x180009737  mov     rax, [rax+8]
0x18000973b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
