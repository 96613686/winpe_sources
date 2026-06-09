# ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(void)

- ea: `0x180002988`
- end: `0x1800029a6`
- name: `??1?$CComPtrBase@UID3D12CoreModule@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000290c`
- `0x180002978`
- `0x180002a9c`
- `0x180005e54`
- `0x180006004`
- `0x180006228`
- `0x180007b8c`
- `0x18000eb4c`

## callees

- `0x180002988`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ID3D12CoreModule>::~CComPtrBase<ID3D12CoreModule>(__int64 *a1)
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
0x180002988  sub     rsp, 28h
0x18000298c  mov     rcx, [rcx]
0x18000298f  test    rcx, rcx
0x180002992  jz      short loc_1800029A1
0x180002994  mov     rax, [rcx]
0x180002997  mov     rax, [rax+10h]
0x18000299b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a0  nop
0x1800029a1  add     rsp, 28h
0x1800029a5  retn
```
