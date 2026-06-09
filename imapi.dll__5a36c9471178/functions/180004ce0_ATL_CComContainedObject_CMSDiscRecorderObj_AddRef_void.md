# ATL::CComContainedObject<CMSDiscRecorderObj>::AddRef(void)

- ea: `0x180004ce0`
- end: `0x180004cf0`
- name: `?AddRef@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004d00`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscRecorderObj>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180004ce0  mov     rcx, [rcx+10h]
0x180004ce4  mov     rax, [rcx]
0x180004ce7  mov     rax, [rax+8]
0x180004ceb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
