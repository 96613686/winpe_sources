# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x18000eafc`
- end: `0x18000eb19`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000eca0`
- `0x18000ee54`

## callees

- `0x18000eafc`
- `0x18001a010`

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
0x18000eafc  sub     rsp, 28h
0x18000eb00  mov     rcx, [rcx]
0x18000eb03  test    rcx, rcx
0x18000eb06  jz      short loc_18000EB14
0x18000eb08  mov     rax, [rcx]
0x18000eb0b  mov     rax, [rax+10h]
0x18000eb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb14  add     rsp, 28h
0x18000eb18  retn
```
