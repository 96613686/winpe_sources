# web::json::object::find_by_key(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140007740`
- end: `0x14000786c`
- name: `?find_by_key@object@json@web@@AEBA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007e20`

## callees

- `0x140004270`
- `0x1400042d0`
- `0x140007740`
- `0x140022f0c`

## pseudocode

```c
_QWORD *__fastcall web::json::object::find_by_key(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  const wchar_t *v8; // rdx
  const wchar_t *v9; // rcx
  size_t v10; // r8
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rdi

  v4 = *a1;
  v6 = a1[1];
  if ( *((_BYTE *)a1 + 24) )
  {
    for ( ; v4 != v6; v4 += 40 )
    {
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v8 = (const wchar_t *)a3;
      else
        v8 = *(const wchar_t **)a3;
      if ( *(_QWORD *)(v4 + 24) <= 7u )
        v9 = (const wchar_t *)v4;
      else
        v9 = *(const wchar_t **)v4;
      v10 = *(_QWORD *)(v4 + 16);
      if ( v10 == *(_QWORD *)(a3 + 16) && (!v10 || !wmemcmp(v9, v8, v10)) )
        break;
    }
  }
  else
  {
    v12 = (__int64)((unsigned __int128)((v6 - v4) * (__int128)0x6666666666666667LL) >> 64) >> 4;
    v13 = (v12 >> 63) + v12;
    while ( (__int64)v13 > 0 )
    {
      if ( (unsigned __int8)std::operator<<unsigned short>(v4 + 40 * (v13 >> 1), a3) )
      {
        v4 += 40 * (v13 >> 1) + 40;
        v13 += -1LL - (v13 >> 1);
      }
      else
      {
        v13 >>= 1;
      }
    }
    if ( v4 != a1[1] && (unsigned __int8)std::operator!=<unsigned short>(a3, v4) )
    {
      *a2 = a1[1];
      return a2;
    }
  }
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x140007740  mov     [rsp+arg_10], rbx
0x140007745  mov     [rsp+arg_18], rdi
0x14000774a  push    r12
0x14000774c  push    r14
0x14000774e  push    r15
0x140007750  sub     rsp, 20h
0x140007754  cmp     byte ptr [rcx+18h], 0
0x140007758  mov     r14, r8
0x14000775b  mov     rbx, [rcx]
0x14000775e  mov     r12, rdx
0x140007761  mov     rdi, [rcx+8]
0x140007765  mov     r15, rcx
0x140007768  jz      short loc_1400077CB
0x14000776a  cmp     rbx, rdi
0x14000776d  jz      short loc_1400077AF
0x14000776f  nop
0x140007770  cmp     qword ptr [r14+18h], 7
0x140007775  jbe     short loc_14000777C
0x140007777  mov     rdx, [r14]
0x14000777a  jmp     short loc_14000777F
0x14000777c  mov     rdx, r14; S2
0x14000777f  cmp     qword ptr [rbx+18h], 7
0x140007784  jbe     short loc_14000778B
0x140007786  mov     rcx, [rbx]
0x140007789  jmp     short loc_14000778E
0x14000778b  mov     rcx, rbx; S1
0x14000778e  mov     r8, [rbx+10h]; N
0x140007792  cmp     r8, [r14+10h]
0x140007796  jnz     short loc_1400077A6
0x140007798  test    r8, r8
0x14000779b  jz      short loc_1400077AF
0x14000779d  call    wmemcmp
0x1400077a2  test    eax, eax
0x1400077a4  jz      short loc_1400077AF
0x1400077a6  add     rbx, 28h ; '('
0x1400077aa  cmp     rbx, rdi
0x1400077ad  jnz     short loc_140007770
0x1400077af  mov     [r12], rbx
0x1400077b3  mov     rbx, [rsp+38h+arg_10]
0x1400077b8  mov     rax, r12
0x1400077bb  mov     rdi, [rsp+38h+arg_18]
0x1400077c0  add     rsp, 20h
0x1400077c4  pop     r15
0x1400077c6  pop     r14
0x1400077c8  pop     r12
0x1400077ca  retn
0x1400077cb  sub     rdi, rbx
0x1400077ce  mov     rax, 6666666666666667h
0x1400077d8  imul    rdi
0x1400077db  mov     rdi, rdx
0x1400077de  sar     rdi, 4
0x1400077e2  mov     rax, rdi
0x1400077e5  shr     rax, 3Fh
0x1400077e9  add     rdi, rax
0x1400077ec  test    rdi, rdi
0x1400077ef  jle     short loc_140007842
0x1400077f1  mov     [rsp+38h+arg_0], rbp
0x1400077f6  mov     [rsp+38h+arg_8], rsi
0x1400077fb  nop     dword ptr [rax+rax+00h]
0x140007800  mov     rsi, rdi
0x140007803  mov     rdx, r14
0x140007806  shr     rsi, 1
0x140007809  lea     rax, [rsi+rsi*4]
0x14000780d  lea     rbp, [rbx+rax*8]
0x140007811  mov     rcx, rbp
0x140007814  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x140007819  test    al, al
0x14000781b  jz      short loc_140007830
0x14000781d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140007824  lea     rbx, [rbp+28h]
0x140007828  sub     rax, rsi
0x14000782b  add     rdi, rax
0x14000782e  jmp     short loc_140007833
0x140007830  mov     rdi, rsi
0x140007833  test    rdi, rdi
0x140007836  jg      short loc_140007800
0x140007838  mov     rsi, [rsp+38h+arg_8]
0x14000783d  mov     rbp, [rsp+38h+arg_0]
0x140007842  cmp     rbx, [r15+8]
0x140007846  jz      loc_1400077AF
0x14000784c  mov     rdx, rbx
0x14000784f  mov     rcx, r14
0x140007852  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x140007857  test    al, al
0x140007859  jz      loc_1400077AF
0x14000785f  mov     rax, [r15+8]
0x140007863  mov     [r12], rax
0x140007867  jmp     loc_1400077B3
```
