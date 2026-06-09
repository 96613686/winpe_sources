# std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)

- ea: `0x1800097bc`
- end: `0x180009802`
- name: `??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z`
- size: `70`
- prototype: `int __fastcall(const wchar_t *, size_t, const wchar_t *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c750`
- `0x18000fd90`

## callees

- `0x1800097bc`
- `0x18000c744`

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
0x1800097bc  mov     [rsp+arg_0], rbx
0x1800097c1  push    rdi
0x1800097c2  sub     rsp, 20h
0x1800097c6  mov     rax, r8
0x1800097c9  cmp     r9, rdx
0x1800097cc  mov     r8, r9
0x1800097cf  mov     rdi, rdx
0x1800097d2  cmovnb  r8, rdx; N
0x1800097d6  mov     rbx, r9
0x1800097d9  mov     rdx, rax; S2
0x1800097dc  call    ?compare@?$_WChar_traits@G@std@@SAHQEBG0_K@Z; std::_WChar_traits<ushort>::compare(ushort const * const,ushort const * const,unsigned __int64)
0x1800097e1  test    eax, eax
0x1800097e3  jnz     short loc_1800097F7
0x1800097e5  cmp     rdi, rbx
0x1800097e8  jnb     short loc_1800097EF
0x1800097ea  or      eax, 0FFFFFFFFh
0x1800097ed  jmp     short loc_1800097F7
0x1800097ef  xor     eax, eax
0x1800097f1  cmp     rdi, rbx
0x1800097f4  setnbe  al
0x1800097f7  mov     rbx, [rsp+28h+arg_0]
0x1800097fc  add     rsp, 20h
0x180009800  pop     rdi
0x180009801  retn
```
