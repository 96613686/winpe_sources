# ATL::CComContainedObject<CGameStatisticsMgr>::Release(void)

- ea: `0x180002bb0`
- end: `0x180002bc0`
- name: `?Release@?$CComContainedObject@VCGameStatisticsMgr@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameStatisticsMgr>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002bb0  mov     rcx, [rcx+8]
0x180002bb4  mov     rax, [rcx]
0x180002bb7  mov     rax, [rax+10h]
0x180002bbb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
