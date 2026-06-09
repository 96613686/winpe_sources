# CommandLineHandler(ushort const *,uchar *)

- ea: `0x140004ce0`
- end: `0x140004d51`
- name: `?CommandLineHandler@@YAJPEBGPEAE@Z`
- size: `113`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004ce0`
- `0x140008b0c`
- `0x140008e50`

## pseudocode

```c
__int64 __fastcall CommandLineHandler(unsigned __int16 *Src, unsigned __int8 *a2)
{
  unsigned __int8 *v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // r8
  const char *v6; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    v3 = a2 + 96;
    if ( *((_QWORD *)a2 + 13) == *((_QWORD *)a2 + 14) )
      std::vector<std::wstring>::_Reserve(a2 + 96);
    v4 = (_QWORD *)*((_QWORD *)v3 + 1);
    v4[3] = 7;
    v4[2] = 0;
    *(_WORD *)v4 = 0;
    if ( *Src )
    {
      v5 = -1;
      do
        ++v5;
      while ( Src[v5] );
    }
    std::wstring::assign(v4, Src);
    *((_QWORD *)v3 + 1) += 32LL;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x49,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140004ce0  mov     [rsp+arg_0], rbx
0x140004ce5  push    rdi
0x140004ce6  sub     rsp, 20h
0x140004cea  mov     rdi, rcx
0x140004ced  lea     rbx, [rdx+60h]
0x140004cf1  mov     rax, [rbx+10h]
0x140004cf5  cmp     [rbx+8], rax
0x140004cf9  jnz     short loc_140004D03
0x140004cfb  mov     rcx, rbx
0x140004cfe  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x140004d03  mov     rcx, [rbx+8]; void *
0x140004d07  mov     qword ptr [rcx+18h], 7
0x140004d0f  xor     edx, edx
0x140004d11  mov     [rcx+10h], rdx
0x140004d15  mov     [rcx], dx
0x140004d18  cmp     [rdi], dx
0x140004d1b  jnz     short loc_140004D22
0x140004d1d  mov     r8d, edx
0x140004d20  jmp     short loc_140004D30
0x140004d22  or      r8, 0FFFFFFFFFFFFFFFFh
0x140004d26  inc     r8
0x140004d29  cmp     [rdi+r8*2], dx
0x140004d2e  jnz     short loc_140004D26
0x140004d30  mov     rdx, rdi; Src
0x140004d33  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140004d38  add     qword ptr [rbx+8], 20h ; ' '
0x140004d3d  xor     eax, eax
0x140004d3f  jmp     short loc_140004D45
0x140004d41  mov     eax, [rsp+28h+arg_8]
0x140004d45  mov     rbx, [rsp+28h+arg_0]
0x140004d4a  add     rsp, 20h
0x140004d4e  pop     rdi
0x140004d4f  retn
```
