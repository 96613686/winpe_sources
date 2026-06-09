# ATL::CComContainedObject<CPortableWorkspaceLauncher>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c210`
- end: `0x18000c229`
- name: `?QueryInterface@?$CComContainedObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPortableWorkspaceLauncher>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000c210  sub     rsp, 28h
0x18000c214  mov     rcx, [rcx+8]
0x18000c218  mov     rax, [rcx]
0x18000c21b  mov     rax, [rax]
0x18000c21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c223  nop
0x18000c224  add     rsp, 28h
0x18000c228  retn
```
