# _anonymous_namespace_::IsHexToken

- ea: `0x18000e710`
- end: `0x18000e789`
- name: `_anonymous_namespace_::IsHexToken`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b3e0`

## callees

- `0x180006140`
- `0x18000e710`
- `0x18001893c`

## pseudocode

```c
char __fastcall anonymous_namespace_::IsHexToken(_QWORD *a1)
{
  char v2; // di
  __int64 v3; // rdx

  v2 = 0;
  if ( !std::basic_string_view<unsigned short>::rfind(a1, L"0x")
    || !std::basic_string_view<unsigned short>::rfind(a1, L"0X") )
  {
    *a1 += 4LL;
    a1[1] -= 2LL;
  }
  v3 = a1[1];
  if ( v3
    && std::_Traits_find_first_not_of<std::char_traits<unsigned short>,1>(
         *a1,
         v3,
         0,
         (unsigned int)L"0123456789abcdefABCDEF",
         22) == -1 )
  {
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x18000e710  mov     [rsp+arg_0], rbx
0x18000e715  push    rdi
0x18000e716  sub     rsp, 30h
0x18000e71a  lea     rdx, a0x; "0x"
0x18000e721  mov     rbx, rcx
0x18000e724  call    ?rfind@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA_KQEBG_K@Z; std::basic_string_view<ushort>::rfind(ushort const * const,unsigned __int64)
0x18000e729  xor     edi, edi
0x18000e72b  test    rax, rax
0x18000e72e  jz      short loc_18000E744
0x18000e730  lea     rdx, a0x_0; "0X"
0x18000e737  mov     rcx, rbx
0x18000e73a  call    ?rfind@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA_KQEBG_K@Z; std::basic_string_view<ushort>::rfind(ushort const * const,unsigned __int64)
0x18000e73f  test    rax, rax
0x18000e742  jnz     short loc_18000E74D
0x18000e744  add     qword ptr [rbx], 4
0x18000e748  sub     qword ptr [rbx+8], 2
0x18000e74d  mov     rdx, [rbx+8]
0x18000e751  test    rdx, rdx
0x18000e754  jz      short loc_18000E77A
0x18000e756  mov     rcx, [rbx]
0x18000e759  lea     r9, a0123456789abcd; "0123456789abcdefABCDEF"
0x18000e760  xor     r8d, r8d
0x18000e763  mov     [rsp+38h+var_18], 16h
0x18000e76c  call    ??$_Traits_find_first_not_of@U?$char_traits@G@std@@$00@std@@YA_KQEBG_K101@Z; std::_Traits_find_first_not_of<std::char_traits<ushort>,1>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18000e771  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e775  jnz     short loc_18000E77A
0x18000e777  mov     dil, 1
0x18000e77a  mov     rbx, [rsp+38h+arg_0]
0x18000e77f  mov     al, dil
0x18000e782  add     rsp, 30h
0x18000e786  pop     rdi
0x18000e787  retn
```
