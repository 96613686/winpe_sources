# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Allocate_for_capacity<0>(std::allocator<char> &,unsigned __int64 &)

- ea: `0x180008c44`
- end: `0x180008c61`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CAPEADAEAV?$allocator@D@1@AEA_K@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ce4`
- `0x180008d84`
- `0x180008ecc`
- `0x1800090b0`
- `0x1800091a0`
- `0x180009340`

## callees

- `0x180003e50`

## pseudocode

```c
__int64 __fastcall std::string::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax

  result = std::_Allocate<16,std::_Default_allocate_traits>(++*a2);
  --*a2;
  return result;
}

```

## disassembly

```asm
0x180008c44  push    rbx
0x180008c46  sub     rsp, 20h
0x180008c4a  inc     qword ptr [rdx]
0x180008c4d  mov     rbx, rdx
0x180008c50  mov     rcx, [rdx]
0x180008c53  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180008c58  dec     qword ptr [rbx]
0x180008c5b  add     rsp, 20h
0x180008c5f  pop     rbx
0x180008c60  retn
```
