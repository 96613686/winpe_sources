# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180007fd0`
- end: `0x180008097`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x180007b64`
- `0x1800080a0`
- `0x180008d80`
- `0x18000af44`
- `0x18000b84c`
- `0x18000c060`
- `0x18000e0c8`
- `0x18000e188`
- `0x18000e228`
- `0x18000e2fc`
- `0x180010124`

## callees

- `0x180002ddc`
- `0x18000678c`
- `0x180007fd0`
- `0x180013df8`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v9[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = (_OWORD *)a2;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v2 = *(_OWORD **)a2;
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
    v9[0] = v5;
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, v9);
    *(_QWORD *)(a1 + 24) = v9[0];
    *(_QWORD *)a1 = v7;
    *(_QWORD *)(a1 + 16) = v4;
    memcpy_0(v7, v2, 2 * v4 + 2);
  }
  else
  {
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = 7;
    *(_OWORD *)a1 = *v2;
  }
  return a1;
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp+arg_10], rbx
0x180007fd5  mov     [rsp+arg_18], rsi
0x180007fda  push    rdi
0x180007fdb  sub     rsp, 30h
0x180007fdf  mov     rsi, rdx
0x180007fe2  xorps   xmm0, xmm0
0x180007fe5  movups  xmmword ptr [rcx], xmm0
0x180007fe8  mov     qword ptr [rcx+10h], 0
0x180007ff0  mov     rbx, rcx
0x180007ff3  mov     qword ptr [rcx+18h], 0
0x180007ffb  mov     rdi, [rdx+10h]
0x180007fff  mov     edx, 7
0x180008004  cmp     [rsi+18h], rdx
0x180008008  jbe     short loc_18000800D
0x18000800a  mov     rsi, [rsi]
0x18000800d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008017  cmp     rdi, rax
0x18000801a  ja      short loc_180008091
0x18000801c  cmp     rdi, rdx
0x18000801f  ja      short loc_180008032
0x180008021  mov     [rcx+10h], rdi
0x180008025  mov     [rcx+18h], rdx
0x180008029  movups  xmm0, xmmword ptr [rsi]
0x18000802c  movdqu  xmmword ptr [rcx], xmm0
0x180008030  jmp     short loc_18000807E
0x180008032  mov     rcx, rdi
0x180008035  or      rcx, rdx
0x180008038  cmp     rcx, rax
0x18000803b  ja      short loc_18000804C
0x18000803d  mov     edx, 0Ah
0x180008042  mov     rax, rcx
0x180008045  cmp     rcx, rdx
0x180008048  cmovb   rax, rdx
0x18000804c  lea     rdx, [rsp+38h+var_18]
0x180008051  mov     [rsp+38h+var_18], rax
0x180008056  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x18000805b  mov     rcx, [rsp+38h+var_18]
0x180008060  lea     r8, ds:2[rdi*2]; Size
0x180008068  mov     [rbx+18h], rcx
0x18000806c  mov     rdx, rsi; Src
0x18000806f  mov     rcx, rax; void *
0x180008072  mov     [rbx], rax
0x180008075  mov     [rbx+10h], rdi
0x180008079  call    memcpy_0
0x18000807e  mov     rsi, [rsp+38h+arg_18]
0x180008083  mov     rax, rbx
0x180008086  mov     rbx, [rsp+38h+arg_10]
0x18000808b  add     rsp, 30h
0x18000808f  pop     rdi
0x180008090  retn
0x180008091  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
