# ATL::CComContainedObject<CPortableWorkspaceLauncher>::Release(void)

- ea: `0x18000c2f0`
- end: `0x18000c30a`
- name: `?Release@?$CComContainedObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPortableWorkspaceLauncher>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000c2f0  sub     rsp, 28h
0x18000c2f4  mov     rcx, [rcx+8]
0x18000c2f8  mov     rax, [rcx]
0x18000c2fb  mov     rax, [rax+10h]
0x18000c2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c304  nop
0x18000c305  add     rsp, 28h
0x18000c309  retn
```
