# ATL::CComContainedObject<CDpSearchProtocol>::Release(void)

- ea: `0x180005ea0`
- end: `0x180005eba`
- name: `?Release@?$CComContainedObject@VCDpSearchProtocol@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDpSearchProtocol>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005ea0  sub     rsp, 28h
0x180005ea4  mov     rcx, [rcx+8]
0x180005ea8  mov     rax, [rcx]
0x180005eab  mov     rax, [rax+10h]
0x180005eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb4  nop
0x180005eb5  add     rsp, 28h
0x180005eb9  retn
```
