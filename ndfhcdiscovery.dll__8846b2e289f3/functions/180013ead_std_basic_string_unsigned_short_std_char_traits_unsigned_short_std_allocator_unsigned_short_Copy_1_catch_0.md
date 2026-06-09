# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x180013ead`
- end: `0x180013ed2`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f9c`
- `0x18000a3ac`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x180013ead  mov     [rsp+arg_8], rdx
0x180013eb2  push    rbp
0x180013eb3  sub     rsp, 20h
0x180013eb7  mov     rbp, rdx
0x180013eba  xor     r8d, r8d
0x180013ebd  mov     dl, 1
0x180013ebf  mov     rcx, [rbp+50h]
0x180013ec3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013ec8  xor     edx, edx; pThrowInfo
0x180013eca  xor     ecx, ecx; pExceptionObject
0x180013ecc  call    _CxxThrowException_0
```
