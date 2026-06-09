# ATL::CComContainedObject<CRehydrationTaskHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800040b0`
- end: `0x1800040c9`
- name: `?QueryInterface@?$CComContainedObject@VCRehydrationTaskHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRehydrationTaskHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800040b0  sub     rsp, 28h
0x1800040b4  mov     rcx, [rcx+8]
0x1800040b8  mov     rax, [rcx]
0x1800040bb  mov     rax, [rax]
0x1800040be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c3  nop
0x1800040c4  add     rsp, 28h
0x1800040c8  retn
```
