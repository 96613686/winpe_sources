# std::_Ref_count<MapsBackgroundTransferJob>::_Delete_this(void)

- ea: `0x18000fe20`
- end: `0x18000fe3f`
- name: `?_Delete_this@?$_Ref_count@VMapsBackgroundTransferJob@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000fe20`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<MapsBackgroundTransferJob>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000fe20  sub     rsp, 28h
0x18000fe24  test    rcx, rcx
0x18000fe27  jz      short loc_18000FE3A
0x18000fe29  mov     rax, [rcx]
0x18000fe2c  mov     edx, 1
0x18000fe31  mov     rax, [rax+10h]
0x18000fe35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe3a  add     rsp, 28h
0x18000fe3e  retn
```
