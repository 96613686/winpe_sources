# ATL::CComContainedObject<DataStoreComServer>::AddRef(void)

- ea: `0x180002810`
- end: `0x18000282a`
- name: `?AddRef@?$CComContainedObject@VDataStoreComServer@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<DataStoreComServer>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002810  sub     rsp, 28h
0x180002814  mov     rcx, [rcx+8]
0x180002818  mov     rax, [rcx]
0x18000281b  mov     rax, [rax+8]
0x18000281f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002824  nop
0x180002825  add     rsp, 28h
0x180002829  retn
```
