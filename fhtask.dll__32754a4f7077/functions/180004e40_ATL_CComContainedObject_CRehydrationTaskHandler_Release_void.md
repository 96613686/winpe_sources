# ATL::CComContainedObject<CRehydrationTaskHandler>::Release(void)

- ea: `0x180004e40`
- end: `0x180004e5a`
- name: `?Release@?$CComContainedObject@VCRehydrationTaskHandler@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRehydrationTaskHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180004e40  sub     rsp, 28h
0x180004e44  mov     rcx, [rcx+8]
0x180004e48  mov     rax, [rcx]
0x180004e4b  mov     rax, [rax+10h]
0x180004e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e54  nop
0x180004e55  add     rsp, 28h
0x180004e59  retn
```
