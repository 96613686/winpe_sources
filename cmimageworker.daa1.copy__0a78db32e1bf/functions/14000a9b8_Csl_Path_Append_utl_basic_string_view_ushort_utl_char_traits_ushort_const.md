# Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)

- ea: `0x14000a9b8`
- end: `0x14000aa52`
- name: `?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(Csl::Path *this)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x140006188`
- `0x14000ae14`
- `0x14000b2ec`
- `0x14000bd50`
- `0x140017868`
- `0x140017c88`
- `0x140018184`
- `0x140018320`
- `0x1400187e4`
- `0x140018d5c`
- `0x140019b98`
- `0x140019e40`
- `0x14001c440`
- `0x14001d310`
- `0x140021d08`

## callees

- `0x14000a9b8`
- `0x14000c74c`
- `0x14000cbb8`
- `0x14000cccc`

## pseudocode

```c
char __fastcall Csl::Path::Append(Csl::Path *this, _QWORD *a2)
{
  __int64 v4; // rcx
  char v5; // di

  v4 = *((_QWORD *)this + 1);
  if ( !((v4 - *(_QWORD *)this) >> 1) || !a2[1] || *(_WORD *)(v4 - 2) == 92 || *(_WORD *)*a2 == 92 )
  {
    v5 = 0;
  }
  else
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             this,
                             a2,
                             92) )
      return 0;
    v5 = 1;
  }
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          this,
                          *a2,
                          a2[1]) )
  {
    Csl::Path::TrimTrailingSeparators(this);
    return 1;
  }
  if ( v5 )
  {
    *((_QWORD *)this + 1) -= 2LL;
    **((_WORD **)this + 1) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14000a9b8  mov     [rsp+arg_0], rbx
0x14000a9bd  mov     [rsp+arg_8], rsi
0x14000a9c2  push    rdi
0x14000a9c3  sub     rsp, 20h
0x14000a9c7  mov     rbx, rcx
0x14000a9ca  mov     rsi, rdx
0x14000a9cd  mov     rcx, [rcx+8]
0x14000a9d1  mov     rax, rcx
0x14000a9d4  sub     rax, [rbx]
0x14000a9d7  sar     rax, 1
0x14000a9da  jz      short loc_14000AA0A
0x14000a9dc  cmp     qword ptr [rdx+8], 0
0x14000a9e1  jbe     short loc_14000AA0A
0x14000a9e3  mov     r8d, 5Ch ; '\'
0x14000a9e9  cmp     r8w, [rcx-2]
0x14000a9ee  jz      short loc_14000AA0A
0x14000a9f0  mov     rax, [rdx]
0x14000a9f3  cmp     r8w, [rax]
0x14000a9f7  jz      short loc_14000AA0A
0x14000a9f9  mov     rcx, rbx
0x14000a9fc  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(unsigned __int64,ushort)
0x14000aa01  test    al, al
0x14000aa03  jz      short loc_14000AA3F
0x14000aa05  mov     dil, 1
0x14000aa08  jmp     short loc_14000AA0D
0x14000aa0a  xor     dil, dil
0x14000aa0d  mov     r8, [rsi+8]
0x14000aa11  mov     rcx, rbx
0x14000aa14  mov     rdx, [rsi]
0x14000aa17  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14000aa1c  test    al, al
0x14000aa1e  jz      short loc_14000AA2C
0x14000aa20  mov     rcx, rbx; this
0x14000aa23  call    ?TrimTrailingSeparators@Path@Csl@@AEAAXXZ; Csl::Path::TrimTrailingSeparators(void)
0x14000aa28  mov     al, 1
0x14000aa2a  jmp     short loc_14000AA41
0x14000aa2c  test    dil, dil
0x14000aa2f  jz      short loc_14000AA3F
0x14000aa31  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFEh
0x14000aa36  mov     rcx, [rbx+8]
0x14000aa3a  xor     eax, eax
0x14000aa3c  mov     [rcx], ax
0x14000aa3f  xor     al, al
0x14000aa41  mov     rbx, [rsp+28h+arg_0]
0x14000aa46  mov     rsi, [rsp+28h+arg_8]
0x14000aa4b  add     rsp, 20h
0x14000aa4f  pop     rdi
0x14000aa50  retn
```
