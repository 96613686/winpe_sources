# ATL::CComContainedObject<CHHCollectionWrapper>::AddRef(void)

- ea: `0x180002e10`
- end: `0x180002e20`
- name: `?AddRef@?$CComContainedObject@VCHHCollectionWrapper@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CHHCollectionWrapper>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002e10  mov     rcx, [rcx+8]
0x180002e14  mov     rax, [rcx]
0x180002e17  mov     rax, [rax+8]
0x180002e1b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
