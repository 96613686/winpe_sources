# ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(void)

- ea: `0x1800080a0`
- end: `0x1800080b3`
- name: `?AddRef@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800080c0`
- `0x1800080d0`
- `0x1800080e0`
- `0x1800080f0`
- `0x180008100`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscMasterObj>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 128) + 8LL))(*(_QWORD *)(a1 + 128));
}

```

## disassembly

```asm
0x1800080a0  mov     rcx, [rcx+80h]
0x1800080a7  mov     rax, [rcx]
0x1800080aa  mov     rax, [rax+8]
0x1800080ae  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
