# ATL::CComContainedObject<CGameExplorer>::Release(void)

- ea: `0x1800023d0`
- end: `0x1800023e0`
- name: `?Release@?$CComContainedObject@VCGameExplorer@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800023f0`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameExplorer>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800023d0  mov     rcx, [rcx+10h]
0x1800023d4  mov     rax, [rcx]
0x1800023d7  mov     rax, [rax+10h]
0x1800023db  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
