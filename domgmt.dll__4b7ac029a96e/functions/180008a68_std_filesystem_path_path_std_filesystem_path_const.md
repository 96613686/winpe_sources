# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x180008a68`
- end: `0x180008b34`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800088f8`
- `0x180008988`
- `0x180008f94`
- `0x18000993c`

## callees

- `0x18000739c`
- `0x180008a68`
- `0x18000aa3c`
- `0x18000d5b4`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::path::path(
        std::filesystem::path *this,
        const struct std::filesystem::path *a2)
{
  const struct std::filesystem::path *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
  std::filesystem::path *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = this;
  v2 = a2;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v4 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const struct std::filesystem::path **)a2;
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    v6 = v4 | 7;
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( v6 < 0xA )
        v5 = 10;
    }
    v9 = (std::filesystem::path *)v5;
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, &v9);
    *((_QWORD *)this + 3) = v9;
    *(_QWORD *)this = v7;
    *((_QWORD *)this + 2) = v4;
    memcpy_0(v7, v2, 2 * v4 + 2);
  }
  else
  {
    *((_QWORD *)this + 2) = v4;
    *((_QWORD *)this + 3) = 7;
    *(_OWORD *)this = *(_OWORD *)v2;
  }
  return this;
}

```

## disassembly

```asm
0x180008a68  mov     [rsp+arg_8], rbx
0x180008a6d  mov     [rsp+arg_10], rsi
0x180008a72  mov     [rsp+arg_0], rcx
0x180008a77  push    rdi
0x180008a78  sub     rsp, 20h
0x180008a7c  mov     rsi, rdx
0x180008a7f  xorps   xmm0, xmm0
0x180008a82  movups  xmmword ptr [rcx], xmm0
0x180008a85  mov     qword ptr [rcx+10h], 0
0x180008a8d  mov     rbx, rcx
0x180008a90  mov     qword ptr [rcx+18h], 0
0x180008a98  mov     rdi, [rdx+10h]
0x180008a9c  mov     edx, 7
0x180008aa1  cmp     [rsi+18h], rdx
0x180008aa5  jbe     short loc_180008AAA
0x180008aa7  mov     rsi, [rsi]
0x180008aaa  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008ab4  cmp     rdi, rax
0x180008ab7  ja      short loc_180008B2E
0x180008ab9  cmp     rdi, rdx
0x180008abc  ja      short loc_180008ACF
0x180008abe  mov     [rcx+10h], rdi
0x180008ac2  mov     [rcx+18h], rdx
0x180008ac6  movups  xmm0, xmmword ptr [rsi]
0x180008ac9  movdqu  xmmword ptr [rcx], xmm0
0x180008acd  jmp     short loc_180008B1B
0x180008acf  mov     rcx, rdi
0x180008ad2  or      rcx, rdx
0x180008ad5  cmp     rcx, rax
0x180008ad8  ja      short loc_180008AE9
0x180008ada  mov     edx, 0Ah
0x180008adf  mov     rax, rcx
0x180008ae2  cmp     rcx, rdx
0x180008ae5  cmovb   rax, rdx
0x180008ae9  lea     rdx, [rsp+28h+arg_0]
0x180008aee  mov     [rsp+28h+arg_0], rax
0x180008af3  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180008af8  mov     rcx, [rsp+28h+arg_0]
0x180008afd  lea     r8, ds:2[rdi*2]; Size
0x180008b05  mov     [rbx+18h], rcx
0x180008b09  mov     rdx, rsi; Src
0x180008b0c  mov     rcx, rax; void *
0x180008b0f  mov     [rbx], rax
0x180008b12  mov     [rbx+10h], rdi
0x180008b16  call    memcpy_0
0x180008b1b  mov     rsi, [rsp+28h+arg_10]
0x180008b20  mov     rax, rbx
0x180008b23  mov     rbx, [rsp+28h+arg_8]
0x180008b28  add     rsp, 20h
0x180008b2c  pop     rdi
0x180008b2d  retn
0x180008b2e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
