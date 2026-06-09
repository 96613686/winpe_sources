# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x180003e14`
- end: `0x180003e49`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800015e0`
- `0x1800016c0`
- `0x1800019a0`
- `0x180003700`
- `0x180008e20`
- `0x180008fb8`
- `0x18000926c`
- `0x1800093fc`

## callees

- `0x180003e14`
- `0x180003e50`
- `0x18000a0cc`

## pseudocode

```c
__int64 __fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax

  if ( ++*a2 > 0x7FFFFFFFFFFFFFFFuLL )
    std::_Throw_bad_array_new_length();
  result = std::_Allocate<16,std::_Default_allocate_traits>(2LL * *a2);
  --*a2;
  return result;
}

```

## disassembly

```asm
0x180003e14  push    rbx
0x180003e16  sub     rsp, 20h
0x180003e1a  inc     qword ptr [rdx]
0x180003e1d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180003e27  mov     rcx, [rdx]
0x180003e2a  mov     rbx, rdx
0x180003e2d  cmp     rcx, rax
0x180003e30  jbe     short loc_180003E38
0x180003e32  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180003e38  add     rcx, rcx
0x180003e3b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180003e40  dec     qword ptr [rbx]
0x180003e43  add     rsp, 20h
0x180003e47  pop     rbx
0x180003e48  retn
```
