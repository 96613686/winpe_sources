# ATL::CComContainedObject<CPortableWorkspaceLauncher>::AddRef(void)

- ea: `0x18000bb10`
- end: `0x18000bb2a`
- name: `?AddRef@?$CComContainedObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPortableWorkspaceLauncher>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000bb10  sub     rsp, 28h
0x18000bb14  mov     rcx, [rcx+8]
0x18000bb18  mov     rax, [rcx]
0x18000bb1b  mov     rax, [rax+8]
0x18000bb1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb24  nop
0x18000bb25  add     rsp, 28h
0x18000bb29  retn
```
