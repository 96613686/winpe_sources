# ATL::CComContainedObjectGlobal<CAccStore>::Release(void)

- ea: `0x180011c40`
- end: `0x180011c66`
- name: `?Release@?$CComContainedObjectGlobal@VCAccStore@@@ATL@@UEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObjectGlobal<CAccStore>::Release(__int64 a1)
{
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 16LL))(*(_QWORD *)(a1 + 80));
  return (unsigned int)_InterlockedDecrement(&dword_180024B28);
}

```

## disassembly

```asm
0x180011c40  sub     rsp, 28h
0x180011c44  mov     rcx, [rcx+50h]
0x180011c48  mov     rax, [rcx]
0x180011c4b  mov     rax, [rax+10h]
0x180011c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c54  or      eax, 0FFFFFFFFh
0x180011c57  lock xadd cs:dword_180024B28, eax
0x180011c5f  dec     eax
0x180011c61  add     rsp, 28h
0x180011c65  retn
```
