# ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(IBackgroundCopyFile2 * *)

- ea: `0x1800098e4`
- end: `0x180009906`
- name: `??$QueryInterface@UIBackgroundCopyFile2@@@?$CComPtrBase@UIBackgroundCopyFile@@@ATL@@QEBAJPEAPEAUIBackgroundCopyFile2@@@Z`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dd10`
- `0x180011ad0`
- `0x18001240c`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(_QWORD *a1, __int64 a2)
{
  return (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*a1)(*a1, &GUID_83e81b93_0873_474d_8a8c_f2018b1a939c, a2);
}

```

## disassembly

```asm
0x1800098e4  sub     rsp, 28h
0x1800098e8  mov     rcx, [rcx]
0x1800098eb  mov     rax, [rcx]
0x1800098ee  mov     r8, rdx
0x1800098f1  lea     rdx, _GUID_83e81b93_0873_474d_8a8c_f2018b1a939c
0x1800098f8  mov     rax, [rax]
0x1800098fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009900  nop
0x180009901  add     rsp, 28h
0x180009905  retn
```
