# ATL::CComContainedObject<CMSDiscRecorderObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007260`
- end: `0x18000726f`
- name: `?QueryInterface@?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007280`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSDiscRecorderObj>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180007260  mov     rcx, [rcx+10h]
0x180007264  mov     rax, [rcx]
0x180007267  mov     rax, [rax]
0x18000726a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
