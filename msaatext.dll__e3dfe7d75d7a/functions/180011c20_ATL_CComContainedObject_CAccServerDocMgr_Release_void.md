# ATL::CComContainedObject<CAccServerDocMgr>::Release(void)

- ea: `0x180011c20`
- end: `0x180011c30`
- name: `?Release@?$CComContainedObject@VCAccServerDocMgr@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAccServerDocMgr>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180011c20  mov     rcx, [rcx+8]
0x180011c24  mov     rax, [rcx]
0x180011c27  mov     rax, [rax+10h]
0x180011c2b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
