# std::_Ref_count<__ExceptionPtr>::_Delete_this(void)

- ea: `0x180018390`
- end: `0x1800183af`
- name: `?_Delete_this@?$_Ref_count@V__ExceptionPtr@@@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018390`
- `0x18007d020`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<__ExceptionPtr>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180018390  sub     rsp, 28h
0x180018394  test    rcx, rcx
0x180018397  jz      short loc_1800183AA
0x180018399  mov     rax, [rcx]
0x18001839c  mov     edx, 1
0x1800183a1  mov     rax, [rax+10h]
0x1800183a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183aa  add     rsp, 28h
0x1800183ae  retn
```
