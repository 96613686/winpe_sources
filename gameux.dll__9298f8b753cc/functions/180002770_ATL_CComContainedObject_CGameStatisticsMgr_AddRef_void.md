# ATL::CComContainedObject<CGameStatisticsMgr>::AddRef(void)

- ea: `0x180002770`
- end: `0x180002780`
- name: `?AddRef@?$CComContainedObject@VCGameStatisticsMgr@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CGameStatisticsMgr>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002770  mov     rcx, [rcx+8]
0x180002774  mov     rax, [rcx]
0x180002777  mov     rax, [rax+8]
0x18000277b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
