# ATL::CComContainedObjectGlobal<CAccStore>::AddRef(void)

- ea: `0x18000e220`
- end: `0x18000e248`
- name: `?AddRef@?$CComContainedObjectGlobal@VCAccStore@@@ATL@@UEAAKXZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObjectGlobal<CAccStore>::AddRef(__int64 a1)
{
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 8LL))(*(_QWORD *)(a1 + 80));
  return (unsigned int)_InterlockedIncrement(&dword_180024B28);
}

```

## disassembly

```asm
0x18000e220  sub     rsp, 28h
0x18000e224  mov     rcx, [rcx+50h]
0x18000e228  mov     rax, [rcx]
0x18000e22b  mov     rax, [rax+8]
0x18000e22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e234  mov     eax, 1
0x18000e239  lock xadd cs:dword_180024B28, eax
0x18000e241  inc     eax
0x18000e243  add     rsp, 28h
0x18000e247  retn
```
