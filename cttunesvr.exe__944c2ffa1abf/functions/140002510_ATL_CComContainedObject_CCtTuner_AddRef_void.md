# ATL::CComContainedObject<CCtTuner>::AddRef(void)

- ea: `0x140002510`
- end: `0x140002520`
- name: `?AddRef@?$CComContainedObject@VCCtTuner@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CCtTuner>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x140002510  mov     rcx, [rcx+8]
0x140002514  mov     rax, [rcx]
0x140002517  mov     rax, [rax+8]
0x14000251b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
