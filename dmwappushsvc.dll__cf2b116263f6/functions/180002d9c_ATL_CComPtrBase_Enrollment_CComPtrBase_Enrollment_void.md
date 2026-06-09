# ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(void)

- ea: `0x180002d9c`
- end: `0x180002dba`
- name: `??1?$CComPtrBase@VEnrollment@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d90`
- `0x180003808`
- `0x18000df4c`
- `0x18000e410`
- `0x18000e4e0`
- `0x18000e5b0`
- `0x18000e674`
- `0x18000e750`
- `0x18000e860`
- `0x18000f6d0`
- `0x18000f960`
- `0x18000faf0`
- `0x18000fe10`
- `0x180010bd0`
- `0x180011340`

## callees

- `0x180002d9c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(__int64 *a1)
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
0x180002d9c  sub     rsp, 28h
0x180002da0  mov     rcx, [rcx]
0x180002da3  test    rcx, rcx
0x180002da6  jz      short loc_180002DB5
0x180002da8  mov     rax, [rcx]
0x180002dab  mov     rax, [rax+10h]
0x180002daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db4  nop
0x180002db5  add     rsp, 28h
0x180002db9  retn
```
