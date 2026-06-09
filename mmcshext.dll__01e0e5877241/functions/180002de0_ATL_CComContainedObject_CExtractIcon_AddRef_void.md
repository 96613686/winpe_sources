# ATL::CComContainedObject<CExtractIcon>::AddRef(void)

- ea: `0x180002de0`
- end: `0x180002df0`
- name: `?AddRef@?$CComContainedObject@VCExtractIcon@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002e00`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CExtractIcon>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180002de0  mov     rcx, [rcx+10h]
0x180002de4  mov     rax, [rcx]
0x180002de7  mov     rax, [rax+8]
0x180002deb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
