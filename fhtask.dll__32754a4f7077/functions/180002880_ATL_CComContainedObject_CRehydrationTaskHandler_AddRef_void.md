# ATL::CComContainedObject<CRehydrationTaskHandler>::AddRef(void)

- ea: `0x180002880`
- end: `0x18000289a`
- name: `?AddRef@?$CComContainedObject@VCRehydrationTaskHandler@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRehydrationTaskHandler>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180002880  sub     rsp, 28h
0x180002884  mov     rcx, [rcx+8]
0x180002888  mov     rax, [rcx]
0x18000288b  mov     rax, [rax+8]
0x18000288f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002894  nop
0x180002895  add     rsp, 28h
0x180002899  retn
```
