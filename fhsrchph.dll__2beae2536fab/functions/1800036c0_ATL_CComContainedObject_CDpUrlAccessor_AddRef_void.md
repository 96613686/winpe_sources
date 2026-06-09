# ATL::CComContainedObject<CDpUrlAccessor>::AddRef(void)

- ea: `0x1800036c0`
- end: `0x1800036da`
- name: `?AddRef@?$CComContainedObject@VCDpUrlAccessor@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDpUrlAccessor>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800036c0  sub     rsp, 28h
0x1800036c4  mov     rcx, [rcx+8]
0x1800036c8  mov     rax, [rcx]
0x1800036cb  mov     rax, [rax+8]
0x1800036cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d4  nop
0x1800036d5  add     rsp, 28h
0x1800036d9  retn
```
