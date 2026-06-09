# ATL::CComContainedObject<CIisRestart>::AddRef(void)

- ea: `0x1400019f0`
- end: `0x140001a00`
- name: `?AddRef@?$CComContainedObject@VCIisRestart@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIisRestart>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1400019f0  mov     rcx, [rcx+8]
0x1400019f4  mov     rax, [rcx]
0x1400019f7  mov     rax, [rax+8]
0x1400019fb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
