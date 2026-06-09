# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch$2

- ea: `0x14001d2df`
- end: `0x14001d307`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch$2`
- size: `40`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001cc6`
- `0x140004f9c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
    *(_QWORD *)(a2 + 144),
    1,
    0);
  throw;
}

```

## disassembly

```asm
0x14001d2df  mov     [rsp+arg_8], rdx
0x14001d2e4  push    rbp
0x14001d2e5  sub     rsp, 20h
0x14001d2e9  mov     rbp, rdx
0x14001d2ec  xor     r8d, r8d
0x14001d2ef  mov     dl, 1
0x14001d2f1  mov     rcx, [rbp+90h]
0x14001d2f8  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x14001d2fd  xor     edx, edx; pThrowInfo
0x14001d2ff  xor     ecx, ecx; pExceptionObject
0x14001d301  call    _CxxThrowException_0
```
