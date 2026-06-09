# std::_Ref_count<ProviderContext>::_Delete_this(void)

- ea: `0x140013d40`
- end: `0x140013d5f`
- name: `?_Delete_this@?$_Ref_count@VProviderContext@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140013d40`
- `0x14001c010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<ProviderContext>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x140013d40  sub     rsp, 28h
0x140013d44  test    rcx, rcx
0x140013d47  jz      short loc_140013D5A
0x140013d49  mov     rax, [rcx]
0x140013d4c  mov     edx, 1
0x140013d51  mov     rax, [rax+10h]
0x140013d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d5a  add     rsp, 28h
0x140013d5e  retn
```
