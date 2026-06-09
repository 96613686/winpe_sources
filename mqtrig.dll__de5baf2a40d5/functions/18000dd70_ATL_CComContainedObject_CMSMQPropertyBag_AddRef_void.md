# ATL::CComContainedObject<CMSMQPropertyBag>::AddRef(void)

- ea: `0x18000dd70`
- end: `0x18000dd80`
- name: `?AddRef@?$CComContainedObject@VCMSMQPropertyBag@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dd90`

## callees

- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSMQPropertyBag>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x18000dd70  mov     rcx, [rcx+10h]
0x18000dd74  mov     rax, [rcx]
0x18000dd77  mov     rax, [rax+8]
0x18000dd7b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
