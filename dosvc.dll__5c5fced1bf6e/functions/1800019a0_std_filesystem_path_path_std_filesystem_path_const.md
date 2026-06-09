# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x1800019a0`
- end: `0x180001a61`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `193`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800097ac`
- `0x180009824`

## callees

- `0x1800019a0`
- `0x180001f30`
- `0x180003e14`
- `0x18000a6d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180001a19`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180001a19`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::path::path(
        std::filesystem::path *this,
        const struct std::filesystem::path *a2)
{
  const struct std::filesystem::path *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v6; // rcx
  void *v7; // rax
  std::filesystem::path *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = this;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  v2 = a2;
  *((_QWORD *)this + 3) = 0;
  v4 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const struct std::filesystem::path **)a2;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v4 > 7 )
  {
    v8 = (std::filesystem::path *)std::wstring::_Calculate_growth(v4, 7);
    v7 = (void *)std::wstring::_Allocate_for_capacity<0>(v6, &v8);
    *((_QWORD *)this + 3) = v8;
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
0x1800019a0  mov     [rsp+arg_8], rbx
0x1800019a5  mov     [rsp+arg_10], rsi
0x1800019aa  mov     [rsp+arg_0], rcx
0x1800019af  push    rdi
0x1800019b0  sub     rsp, 20h
0x1800019b4  xor     eax, eax
0x1800019b6  xorps   xmm0, xmm0
0x1800019b9  movups  xmmword ptr [rcx], xmm0
0x1800019bc  mov     [rcx+10h], rax
0x1800019c0  mov     rsi, rdx
0x1800019c3  mov     [rcx+18h], rax
0x1800019c7  mov     rbx, rcx
0x1800019ca  cmp     qword ptr [rdx+18h], 7
0x1800019cf  mov     rdi, [rdx+10h]
0x1800019d3  jbe     short loc_1800019D8
0x1800019d5  mov     rsi, [rdx]
0x1800019d8  mov     r8, 7FFFFFFFFFFFFFFEh
0x1800019e2  cmp     rdi, r8
0x1800019e5  ja      short loc_180001A12
0x1800019e7  cmp     rdi, 7
0x1800019eb  ja      short loc_180001A20
0x1800019ed  mov     [rcx+10h], rdi
0x1800019f1  mov     qword ptr [rcx+18h], 7
0x1800019f9  movups  xmm0, xmmword ptr [rsi]
0x1800019fc  movups  xmmword ptr [rcx], xmm0
0x1800019ff  mov     rsi, [rsp+28h+arg_10]
0x180001a04  mov     rax, rbx
0x180001a07  mov     rbx, [rsp+28h+arg_8]
0x180001a0c  add     rsp, 20h
0x180001a10  pop     rdi
0x180001a11  retn
0x180001a12  lea     rcx, aStringTooLong; "string too long"
0x180001a19  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180001a20  mov     edx, 7
0x180001a25  mov     rcx, rdi
0x180001a28  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180001a2d  lea     rdx, [rsp+28h+arg_0]
0x180001a32  mov     [rsp+28h+arg_0], rax
0x180001a37  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180001a3c  mov     rcx, [rsp+28h+arg_0]
0x180001a41  lea     r8, ds:2[rdi*2]; Size
0x180001a49  mov     [rbx+18h], rcx
0x180001a4d  mov     rdx, rsi; Src
0x180001a50  mov     rcx, rax; void *
0x180001a53  mov     [rbx], rax
0x180001a56  mov     [rbx+10h], rdi
0x180001a5a  call    memcpy_0
0x180001a5f  jmp     short loc_1800019FF
```
