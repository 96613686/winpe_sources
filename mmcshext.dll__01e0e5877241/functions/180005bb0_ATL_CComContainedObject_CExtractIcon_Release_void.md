# ATL::CComContainedObject<CExtractIcon>::Release(void)

- ea: `0x180005bb0`
- end: `0x180005bc0`
- name: `?Release@?$CComContainedObject@VCExtractIcon@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005bd0`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CExtractIcon>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180005bb0  mov     rcx, [rcx+10h]
0x180005bb4  mov     rax, [rcx]
0x180005bb7  mov     rax, [rax+10h]
0x180005bbb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
