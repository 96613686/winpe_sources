# ATL::CComContainedObject<CDpSearchProtocol>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005110`
- end: `0x180005129`
- name: `?QueryInterface@?$CComContainedObject@VCDpSearchProtocol@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDpSearchProtocol>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005110  sub     rsp, 28h
0x180005114  mov     rcx, [rcx+8]
0x180005118  mov     rax, [rcx]
0x18000511b  mov     rax, [rax]
0x18000511e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005123  nop
0x180005124  add     rsp, 28h
0x180005128  retn
```
