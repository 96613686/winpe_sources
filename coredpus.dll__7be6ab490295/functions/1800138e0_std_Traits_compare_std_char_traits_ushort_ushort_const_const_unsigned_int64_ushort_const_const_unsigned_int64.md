# std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)

- ea: `0x1800138e0`
- end: `0x180013927`
- name: `??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z`
- size: `71`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800107bc`
- `0x180013890`
- `0x180017aec`
- `0x18002b508`
- `0x18002b5a8`

## callees

- `0x1800138e0`
- `0x18001da30`

## pseudocode

```c
int __fastcall std::_Traits_compare<std::char_traits<unsigned short>>(
        const wchar_t *a1,
        size_t a2,
        const wchar_t *a3,
        size_t a4)
{
  size_t v5; // r8
  int result; // eax

  v5 = a4;
  if ( a4 >= a2 )
    v5 = a2;
  result = std::_WChar_traits<unsigned short>::compare(a1, a3, v5);
  if ( !result )
  {
    if ( a2 >= a4 )
      return a2 > a4;
    else
      return -1;
  }
  return result;
}

```

## disassembly

```asm
0x1800138e0  mov     [rsp+arg_0], rbx
0x1800138e5  push    rdi
0x1800138e6  sub     rsp, 20h
0x1800138ea  mov     rax, r8
0x1800138ed  cmp     r9, rdx
0x1800138f0  mov     r8, r9
0x1800138f3  mov     rdi, rdx
0x1800138f6  cmovnb  r8, rdx; N
0x1800138fa  mov     rbx, r9
0x1800138fd  mov     rdx, rax; S2
0x180013900  call    ?compare@?$_WChar_traits@G@std@@SAHQEBG0_K@Z; std::_WChar_traits<ushort>::compare(ushort const * const,ushort const * const,unsigned __int64)
0x180013905  test    eax, eax
0x180013907  jnz     short loc_18001391B
0x180013909  cmp     rdi, rbx
0x18001390c  jnb     short loc_180013913
0x18001390e  or      eax, 0FFFFFFFFh
0x180013911  jmp     short loc_18001391B
0x180013913  xor     eax, eax
0x180013915  cmp     rdi, rbx
0x180013918  setnbe  al
0x18001391b  mov     rbx, [rsp+28h+arg_0]
0x180013920  add     rsp, 20h
0x180013924  pop     rdi
0x180013925  retn
```
