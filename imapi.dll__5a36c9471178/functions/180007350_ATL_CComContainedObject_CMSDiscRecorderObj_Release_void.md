# ATL::CComContainedObject<CMSDiscRecorderObj>::Release(void)

- ea: `0x180007350`
- end: `0x180007360`
- name: `?Release@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007370`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscRecorderObj>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180007350  mov     rcx, [rcx+10h]
0x180007354  mov     rax, [rcx]
0x180007357  mov     rax, [rax+10h]
0x18000735b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
