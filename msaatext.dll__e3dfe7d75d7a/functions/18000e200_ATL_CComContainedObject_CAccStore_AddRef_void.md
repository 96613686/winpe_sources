# ATL::CComContainedObject<CAccStore>::AddRef(void)

- ea: `0x18000e200`
- end: `0x18000e210`
- name: `?AddRef@?$CComContainedObject@VCAccStore@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAccStore>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000e200  mov     rcx, [rcx+8]
0x18000e204  mov     rax, [rcx]
0x18000e207  mov     rax, [rax+8]
0x18000e20b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
