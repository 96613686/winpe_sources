# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::~basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>(void)

- ea: `0x140003bf4`
- end: `0x140003c08`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d013`
- `0x14001d39a`
- `0x14001d3ac`
- `0x14001e85c`
- `0x14001e872`
- `0x14001e888`
- `0x14001e89e`
- `0x14001ebab`
- `0x14001ebbd`
- `0x14001ec4f`

## callees

- `0x140004f2c`

## pseudocode

```c
__int64 __fastcall std::string::~string(__int64 a1, __int64 a2)
{
  LOBYTE(a2) = 1;
  return std::string::_Tidy(a1, a2, 0);
}

```

## disassembly

```asm
0x140003bf4  sub     rsp, 28h
0x140003bf8  xor     r8d, r8d
0x140003bfb  mov     dl, 1
0x140003bfd  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140003c02  nop
0x140003c03  add     rsp, 28h
0x140003c07  retn
```
