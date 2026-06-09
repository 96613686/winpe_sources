# ATL::CComContainedObject<DataStoreComServer>::Release(void)

- ea: `0x180005730`
- end: `0x18000574a`
- name: `?Release@?$CComContainedObject@VDataStoreComServer@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<DataStoreComServer>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005730  sub     rsp, 28h
0x180005734  mov     rcx, [rcx+8]
0x180005738  mov     rax, [rcx]
0x18000573b  mov     rax, [rax+10h]
0x18000573f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005744  nop
0x180005745  add     rsp, 28h
0x180005749  retn
```
