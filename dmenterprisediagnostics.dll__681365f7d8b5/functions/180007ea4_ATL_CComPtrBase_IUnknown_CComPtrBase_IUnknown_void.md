# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180007ea4`
- end: `0x180007ec3`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e98`
- `0x1800081e4`
- `0x18000969c`
- `0x1800096c4`
- `0x18000d67c`
- `0x1800195c0`
- `0x18001b544`
- `0x18001b77c`
- `0x18002101c`
- `0x180021484`

## callees

- `0x180007ea4`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x180007ea4  sub     rsp, 28h
0x180007ea8  mov     rcx, [rcx]
0x180007eab  test    rcx, rcx
0x180007eae  jz      short loc_180007EBD
0x180007eb0  mov     rax, [rcx]
0x180007eb3  mov     rax, [rax+10h]
0x180007eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ebc  nop
0x180007ebd  add     rsp, 28h
0x180007ec1  retn
```
