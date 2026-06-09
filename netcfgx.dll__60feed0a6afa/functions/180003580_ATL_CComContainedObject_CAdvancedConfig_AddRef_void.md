# ATL::CComContainedObject<CAdvancedConfig>::AddRef(void)

- ea: `0x180003580`
- end: `0x18000359a`
- name: `?AddRef@?$CComContainedObject@VCAdvancedConfig@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAdvancedConfig>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180003580  sub     rsp, 28h
0x180003584  mov     rcx, [rcx+8]
0x180003588  mov     rax, [rcx]
0x18000358b  mov     rax, [rax+8]
0x18000358f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003594  nop
0x180003595  add     rsp, 28h
0x180003599  retn
```
