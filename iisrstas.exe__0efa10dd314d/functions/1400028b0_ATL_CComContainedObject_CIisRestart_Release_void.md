# ATL::CComContainedObject<CIisRestart>::Release(void)

- ea: `0x1400028b0`
- end: `0x1400028c0`
- name: `?Release@?$CComContainedObject@VCIisRestart@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIisRestart>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1400028b0  mov     rcx, [rcx+8]
0x1400028b4  mov     rax, [rcx]
0x1400028b7  mov     rax, [rax+10h]
0x1400028bb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
