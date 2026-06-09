# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180007b34`
- end: `0x180007b52`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007b28`
- `0x180007e58`
- `0x18000920c`
- `0x180009234`
- `0x18000d024`
- `0x180018bac`
- `0x18001aa90`
- `0x18001accc`
- `0x18002032c`
- `0x180020774`

## callees

- `0x180007b34`
- `0x180026010`

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
0x180007b34  sub     rsp, 28h
0x180007b38  mov     rcx, [rcx]
0x180007b3b  test    rcx, rcx
0x180007b3e  jz      short loc_180007B4D
0x180007b40  mov     rax, [rcx]
0x180007b43  mov     rax, [rax+10h]
0x180007b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b4c  nop
0x180007b4d  add     rsp, 28h
0x180007b51  retn
```
