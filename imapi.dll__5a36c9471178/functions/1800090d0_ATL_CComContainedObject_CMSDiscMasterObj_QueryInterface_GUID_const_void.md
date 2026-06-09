# ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800090d0`
- end: `0x1800090e2`
- name: `?QueryInterface@?$CComContainedObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800090f0`
- `0x180009100`
- `0x180009110`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscMasterObj>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 128))(*(_QWORD *)(a1 + 128));
}

```

## disassembly

```asm
0x1800090d0  mov     rcx, [rcx+80h]
0x1800090d7  mov     rax, [rcx]
0x1800090da  mov     rax, [rax]
0x1800090dd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
