# ATL::CComContainedObject<CPnpxPairingHandler>::Release(void)

- ea: `0x180008480`
- end: `0x180008490`
- name: `?Release@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800084a0`
- `0x1800084b0`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180008480  mov     rcx, [rcx+18h]
0x180008484  mov     rax, [rcx]
0x180008487  mov     rax, [rax+10h]
0x18000848b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
