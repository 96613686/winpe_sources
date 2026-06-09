# ATL::CComContainedObject<CMSMQRuleHandler>::Release(void)

- ea: `0x18000f860`
- end: `0x18000f870`
- name: `?Release@?$CComContainedObject@VCMSMQRuleHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f880`

## callees

- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSMQRuleHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x18000f860  mov     rcx, [rcx+10h]
0x18000f864  mov     rax, [rcx]
0x18000f867  mov     rax, [rax+10h]
0x18000f86b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
