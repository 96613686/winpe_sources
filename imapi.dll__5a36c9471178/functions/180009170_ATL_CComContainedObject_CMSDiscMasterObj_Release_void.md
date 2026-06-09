# ATL::CComContainedObject<CMSDiscMasterObj>::Release(void)

- ea: `0x180009170`
- end: `0x180009183`
- name: `?Release@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009190`
- `0x1800091a0`
- `0x1800091b0`
- `0x1800091c0`
- `0x1800091d0`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscMasterObj>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 128) + 16LL))(*(_QWORD *)(a1 + 128));
}

```

## disassembly

```asm
0x180009170  mov     rcx, [rcx+80h]
0x180009177  mov     rax, [rcx]
0x18000917a  mov     rax, [rax+10h]
0x18000917e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
