# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140011650`
- end: `0x140011764`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140011ea4`
- `0x14001211c`
- `0x1400124d0`
- `0x140012c08`

## callees

- `0x14000190c`
- `0x140011650`
- `0x140014548`
- `0x140014588`
- `0x14001a83c`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v3; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rbp
  size_t v6; // rcx
  void *v7; // rax
  void *v8; // rcx
  _QWORD *v9; // rax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = (_OWORD *)a2;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v3 = *(_OWORD **)a2;
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( (v4 | 7) < 0xA )
        v5 = 10;
      if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_22;
      v6 = 2 * (v5 + 1);
      if ( !v6 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v6 = -2;
    }
    if ( v6 >= 0x1000 )
    {
      if ( v6 + 39 >= v6 )
      {
        v7 = operator new(v6 + 39);
        v8 = v7;
        if ( !v7 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v6);
LABEL_19:
    *(_QWORD *)a1 = v9;
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = v5;
    memcpy_0(v9, v3, 2 * v4 + 2);
    return a1;
  }
  *(_QWORD *)(a1 + 16) = v4;
  *(_QWORD *)(a1 + 24) = 7;
  *(_OWORD *)a1 = *v3;
  return a1;
}

```

## disassembly

```asm
0x140011650  push    rbx
0x140011652  push    rbp
0x140011653  push    rsi
0x140011654  push    rdi
0x140011655  sub     rsp, 28h
0x140011659  xorps   xmm0, xmm0
0x14001165c  mov     rbx, rcx
0x14001165f  movups  xmmword ptr [rcx], xmm0
0x140011662  mov     qword ptr [rcx+10h], 0
0x14001166a  mov     rsi, rdx
0x14001166d  mov     qword ptr [rcx+18h], 0
0x140011675  mov     ecx, 7
0x14001167a  mov     rdi, [rdx+10h]
0x14001167e  cmp     [rdx+18h], rcx
0x140011682  jbe     short loc_140011687
0x140011684  mov     rsi, [rdx]
0x140011687  mov     rbp, 7FFFFFFFFFFFFFFEh
0x140011691  cmp     rdi, rbp
0x140011694  ja      loc_140011758
0x14001169a  cmp     rdi, rcx
0x14001169d  ja      short loc_1400116B3
0x14001169f  mov     [rbx+10h], rdi
0x1400116a3  mov     [rbx+18h], rcx
0x1400116a7  movups  xmm0, xmmword ptr [rsi]
0x1400116aa  movdqu  xmmword ptr [rbx], xmm0
0x1400116ae  jmp     loc_14001174C
0x1400116b3  mov     rax, rdi
0x1400116b6  or      rax, rcx
0x1400116b9  cmp     rax, rbp
0x1400116bc  jbe     short loc_1400116F0
0x1400116be  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x1400116c5  cmp     rcx, 1000h
0x1400116cc  jb      short loc_140011729
0x1400116ce  lea     rax, [rcx+27h]
0x1400116d2  cmp     rax, rcx
0x1400116d5  jbe     loc_14001175E
0x1400116db  mov     rcx, rax; Size
0x1400116de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400116e3  mov     rcx, rax
0x1400116e6  test    rax, rax
0x1400116e9  jnz     short loc_14001171B
0x1400116eb  lea     ecx, [rax+5]
0x1400116ee  int     29h; Win8: RtlFailFast(ecx)
0x1400116f0  mov     ecx, 0Ah
0x1400116f5  mov     rbp, rax
0x1400116f8  cmp     rax, rcx
0x1400116fb  mov     rax, 7FFFFFFFFFFFFFFFh
0x140011705  cmovb   rbp, rcx
0x140011709  lea     rcx, [rbp+1]
0x14001170d  cmp     rcx, rax
0x140011710  ja      short loc_14001175E
0x140011712  add     rcx, rcx
0x140011715  jnz     short loc_1400116C5
0x140011717  xor     eax, eax
0x140011719  jmp     short loc_14001172E
0x14001171b  add     rax, 27h ; '''
0x14001171f  and     rax, 0FFFFFFFFFFFFFFE0h
0x140011723  mov     [rax-8], rcx
0x140011727  jmp     short loc_14001172E
0x140011729  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001172e  lea     r8, ds:2[rdi*2]; Size
0x140011736  mov     [rbx], rax
0x140011739  mov     rdx, rsi; Src
0x14001173c  mov     [rbx+10h], rdi
0x140011740  mov     rcx, rax; void *
0x140011743  mov     [rbx+18h], rbp
0x140011747  call    memcpy_0
0x14001174c  mov     rax, rbx
0x14001174f  add     rsp, 28h
0x140011753  pop     rdi
0x140011754  pop     rsi
0x140011755  pop     rbp
0x140011756  pop     rbx
0x140011757  retn
0x140011758  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14001175e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
