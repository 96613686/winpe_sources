# ATL::CComPtrBase<IBackgroundCopyJob>::QueryInterface<IBackgroundCopyJob5>(IBackgroundCopyJob5 * *)

- ea: `0x1800039d8`
- end: `0x1800039fa`
- name: `??$QueryInterface@UIBackgroundCopyJob5@@@?$CComPtrBase@UIBackgroundCopyJob@@@ATL@@QEBAJPEAPEAUIBackgroundCopyJob5@@@Z`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004940`
- `0x18000cfec`
- `0x18000eb80`
- `0x18000ecb8`
- `0x18000f9cc`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IBackgroundCopyJob>::QueryInterface<IBackgroundCopyJob5>(_QWORD *a1, __int64 a2)
{
  return (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*a1)(*a1, &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe, a2);
}

```

## disassembly

```asm
0x1800039d8  sub     rsp, 28h
0x1800039dc  mov     rcx, [rcx]
0x1800039df  mov     rax, [rcx]
0x1800039e2  mov     r8, rdx
0x1800039e5  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x1800039ec  mov     rax, [rax]
0x1800039ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f4  nop
0x1800039f5  add     rsp, 28h
0x1800039f9  retn
```
