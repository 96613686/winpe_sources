# std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)

- ea: `0x180001590`
- end: `0x1800015cb`
- name: `??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z`
- size: `59`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012a0`

## callees

- `0x180001590`
- `0x1800015e0`

## pseudocode

```c
__int64 __fastcall std::filesystem::path::path(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rax
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(*a2 + 2 * v3) );
  v5[0] = *a2;
  v5[1] = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, v5);
  return a1;
}

```

## disassembly

```asm
0x180001590  push    rbx
0x180001592  sub     rsp, 30h
0x180001596  mov     r8, [rdx]
0x180001599  mov     rbx, rcx
0x18000159c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800015a3  inc     rax
0x1800015a6  cmp     word ptr [r8+rax*2], 0
0x1800015ac  jnz     short loc_1800015A3
0x1800015ae  lea     rdx, [rsp+38h+var_18]
0x1800015b3  mov     [rsp+38h+var_18], r8
0x1800015b8  mov     [rsp+38h+var_10], rax
0x1800015bd  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1800015c2  mov     rax, rbx
0x1800015c5  add     rsp, 30h
0x1800015c9  pop     rbx
0x1800015ca  retn
```
