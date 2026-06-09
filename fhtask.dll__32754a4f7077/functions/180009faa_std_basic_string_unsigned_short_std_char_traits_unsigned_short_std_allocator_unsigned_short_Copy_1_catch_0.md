# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x180009faa`
- end: `0x180009fd2`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `40`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d18`
- `0x180008db0`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 144), a2, 0);
  throw;
}

```

## disassembly

```asm
0x180009faa  mov     [rsp+arg_8], rdx
0x180009faf  push    rbp
0x180009fb0  sub     rsp, 20h
0x180009fb4  mov     rbp, rdx
0x180009fb7  xor     r8d, r8d
0x180009fba  mov     dl, 1
0x180009fbc  mov     rcx, [rbp+90h]
0x180009fc3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009fc8  xor     edx, edx; pThrowInfo
0x180009fca  xor     ecx, ecx; pExceptionObject
0x180009fcc  call    _CxxThrowException_0
```
