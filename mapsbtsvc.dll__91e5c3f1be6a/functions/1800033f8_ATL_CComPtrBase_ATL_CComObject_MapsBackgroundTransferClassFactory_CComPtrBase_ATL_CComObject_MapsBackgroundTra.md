# ATL::CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>(void)

- ea: `0x1800033f8`
- end: `0x180003415`
- name: `??1?$CComPtrBase@V?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800033c8`
- `0x180003650`
- `0x180003730`

## callees

- `0x1800033f8`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>::~CComPtrBase<ATL::CComObject<MapsBackgroundTransferClassFactory>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800033f8  sub     rsp, 28h
0x1800033fc  mov     rcx, [rcx]
0x1800033ff  test    rcx, rcx
0x180003402  jz      short loc_180003410
0x180003404  mov     rax, [rcx]
0x180003407  mov     rax, [rax+10h]
0x18000340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003410  add     rsp, 28h
0x180003414  retn
```
