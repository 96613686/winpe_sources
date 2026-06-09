# ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)

- ea: `0x18000d768`
- end: `0x18000d786`
- name: `??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800188fc`
- `0x18001890e`
- `0x180018920`
- `0x180018c20`

## callees

- `0x18000d768`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(__int64 *a1)
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
0x18000d768  sub     rsp, 28h
0x18000d76c  mov     rcx, [rcx]
0x18000d76f  test    rcx, rcx
0x18000d772  jz      short loc_18000D781
0x18000d774  mov     rax, [rcx]
0x18000d777  mov     rax, [rax+10h]
0x18000d77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d780  nop
0x18000d781  add     rsp, 28h
0x18000d785  retn
```
