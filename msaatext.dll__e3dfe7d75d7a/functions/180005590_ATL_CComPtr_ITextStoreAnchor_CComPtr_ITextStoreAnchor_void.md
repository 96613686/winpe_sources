# ATL::CComPtr<ITextStoreAnchor>::~CComPtr<ITextStoreAnchor>(void)

- ea: `0x180005590`
- end: `0x1800055ae`
- name: `??1?$CComPtr@UITextStoreAnchor@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800131b6`
- `0x1800131c8`
- `0x1800131da`
- `0x180013218`
- `0x1800136a4`
- `0x18001373a`
- `0x18001387a`
- `0x1800139ab`

## callees

- `0x180005590`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITextStoreAnchor>::~CComPtr<ITextStoreAnchor>(__int64 *a1)
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
0x180005590  sub     rsp, 28h
0x180005594  mov     rcx, [rcx]
0x180005597  test    rcx, rcx
0x18000559a  jz      short loc_1800055A9
0x18000559c  mov     rax, [rcx]
0x18000559f  mov     rax, [rax+10h]
0x1800055a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a8  nop
0x1800055a9  add     rsp, 28h
0x1800055ad  retn
```
