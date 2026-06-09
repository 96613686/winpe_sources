# ATL::CComContainedObject<CGameExplorer>::AddRef(void)

- ea: `0x180001da0`
- end: `0x180001db0`
- name: `?AddRef@?$CComContainedObject@VCGameExplorer@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001dc0`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameExplorer>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180001da0  mov     rcx, [rcx+10h]
0x180001da4  mov     rax, [rcx]
0x180001da7  mov     rax, [rax+8]
0x180001dab  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
