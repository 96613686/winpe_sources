# Csl::ExecuteCommandLine(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ulong &,utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &,ulong)

- ea: `0x14000d1d4`
- end: `0x14000d2b1`
- name: `?ExecuteCommandLine@Csl@@YAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAKAEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@3@K@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140017868`
- `0x140018d5c`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000d1d4`
- `0x14000d2b8`
- `0x14000de24`

## pseudocode

```c
__int64 __fastcall Csl::ExecuteCommandLine(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  void *v7; // rbx
  void *v8[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v8[2] = (void *)-1LL;
  *(__m128i *)v8 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v4 = Csl::ExecuteCommandLine(a1, a2, v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = v8[0];
    if ( (unsigned __int8)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(
                            a3,
                            v8[0],
                            (char *)v8[1] - (char *)v8[0]) )
    {
      if ( v7 != (void *)-1LL )
        operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D9,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
        (const char *)0x8007000ELL,
        (int)v8[0]);
      if ( v7 != (void *)-1LL )
        operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)(unsigned int)v4,
      (int)v8[0]);
    if ( v8[0] != (void *)-1LL )
      operator delete(v8[0], (const struct std::nothrow_t *)&std::nothrow);
    return v5;
  }
}

```

## disassembly

```asm
0x14000d1d4  mov     rax, rsp
0x14000d1d7  mov     [rax+8], rbx
0x14000d1db  push    rdi
0x14000d1dc  sub     rsp, 40h
0x14000d1e0  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000d1e8  mov     rdi, r8
0x14000d1eb  lea     r8, [rax-28h]
0x14000d1ef  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFFh
0x14000d1f7  movdqu  xmmword ptr [rax-28h], xmm0
0x14000d1fc  call    ?ExecuteCommandLine@Csl@@YAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAKPEAV?$vector@EV?$allocator@E@utl@@@3@K@Z; Csl::ExecuteCommandLine(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ulong &,utl::vector<uchar,utl::allocator<uchar>> *,ulong)
0x14000d201  mov     ebx, eax
0x14000d203  test    eax, eax
0x14000d205  jns     short loc_14000D23B
0x14000d207  mov     rcx, [rsp+48h]; this
0x14000d20c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d213  mov     r9d, eax; char *
0x14000d216  mov     edx, 5D6h; void *
0x14000d21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d220  mov     rcx, [rsp+48h+var_28]; void *
0x14000d225  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d229  jz      short loc_14000D237
0x14000d22b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d232  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d237  mov     eax, ebx
0x14000d239  jmp     short loc_14000D2A5
0x14000d23b  mov     rbx, [rsp+48h+var_28]
0x14000d240  mov     rcx, rdi
0x14000d243  mov     r8, [rsp+48h+var_20]
0x14000d248  mov     rdx, rbx
0x14000d24b  sub     r8, rbx
0x14000d24e  call    ?assign@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEAA_NPEBD_K@Z; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(char const *,unsigned __int64)
0x14000d253  test    al, al
0x14000d255  jnz     short loc_14000D28E
0x14000d257  mov     rcx, [rsp+48h]; this
0x14000d25c  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000d263  mov     edi, 8007000Eh
0x14000d268  mov     edx, 5D9h; void *
0x14000d26d  mov     r9d, edi; char *
0x14000d270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d275  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000d279  jz      short loc_14000D28A
0x14000d27b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d282  mov     rcx, rbx; void *
0x14000d285  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d28a  mov     eax, edi
0x14000d28c  jmp     short loc_14000D2A5
0x14000d28e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000d292  jz      short loc_14000D2A3
0x14000d294  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000d29b  mov     rcx, rbx; void *
0x14000d29e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d2a3  xor     eax, eax
0x14000d2a5  mov     rbx, [rsp+48h+arg_0]
0x14000d2aa  add     rsp, 40h
0x14000d2ae  pop     rdi
0x14000d2af  retn
```
