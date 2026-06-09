# ATL::CComContainedObject<CAdvancedConfig>::Release(void)

- ea: `0x180005a50`
- end: `0x180005a6a`
- name: `?Release@?$CComContainedObject@VCAdvancedConfig@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAdvancedConfig>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005a50  sub     rsp, 28h
0x180005a54  mov     rcx, [rcx+8]
0x180005a58  mov     rax, [rcx]
0x180005a5b  mov     rax, [rax+10h]
0x180005a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a64  nop
0x180005a65  add     rsp, 28h
0x180005a69  retn
```
