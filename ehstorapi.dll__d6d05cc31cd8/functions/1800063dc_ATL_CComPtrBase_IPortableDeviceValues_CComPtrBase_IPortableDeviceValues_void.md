# ATL::CComPtrBase<IPortableDeviceValues>::~CComPtrBase<IPortableDeviceValues>(void)

- ea: `0x1800063dc`
- end: `0x1800063fa`
- name: `??1?$CComPtrBase@UIPortableDeviceValues@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007290`

## callees

- `0x1800063dc`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IPortableDeviceValues>::~CComPtrBase<IPortableDeviceValues>(__int64 *a1)
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
0x1800063dc  sub     rsp, 28h
0x1800063e0  mov     rcx, [rcx]
0x1800063e3  test    rcx, rcx
0x1800063e6  jz      short loc_1800063F5
0x1800063e8  mov     rax, [rcx]
0x1800063eb  mov     rax, [rax+10h]
0x1800063ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f4  nop
0x1800063f5  add     rsp, 28h
0x1800063f9  retn
```
