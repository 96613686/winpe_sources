# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x140008e50`
- end: `0x140008f59`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `265`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x140004ce0`
- `0x14000ad18`
- `0x14000b250`
- `0x14000b454`
- `0x14000be30`
- `0x14000c610`
- `0x14000c7f0`
- `0x14000c920`
- `0x14000ca40`
- `0x14000d760`

## callees

- `0x1400086e0`
- `0x140008c90`
- `0x140008cd8`
- `0x140008e50`
- `0x14000de86`

## pseudocode

```c
__int64 *__fastcall std::wstring::assign(__int64 *a1, char *Src, unsigned __int64 a3)
{
  __int64 *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _WORD *v9; // rcx
  __int64 v10; // rcx

  v5 = a1;
  if ( Src )
  {
    v6 = (unsigned __int64)a1[3] < 8 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( (unsigned __int64)a1[3] >= 8 )
        a1 = (__int64 *)*a1;
      if ( (char *)a1 + 2 * v5[2] > Src )
        return (__int64 *)std::wstring::assign(v5);
    }
  }
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( v5[3] >= a3 )
  {
    if ( !a3 )
    {
      if ( (unsigned __int64)v5[3] < 8 )
        v9 = v5;
      else
        v9 = (_WORD *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::wstring::_Copy((const void **)v5, a3, v5[2]);
  if ( a3 )
  {
LABEL_13:
    if ( (unsigned __int64)v5[3] < 8 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, 2 * a3);
    if ( (unsigned __int64)v5[3] < 8 )
      v10 = (__int64)v5;
    else
      v10 = *v5;
    v5[2] = a3;
    *(_WORD *)(2 * a3 + v10) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140008e50  push    rbx
0x140008e52  push    rsi
0x140008e53  push    rdi
0x140008e54  push    r14
0x140008e56  sub     rsp, 28h
0x140008e5a  mov     rdi, r8
0x140008e5d  mov     rsi, rdx
0x140008e60  mov     rbx, rcx
0x140008e63  test    rdx, rdx
0x140008e66  jz      short loc_140008EBE
0x140008e68  cmp     qword ptr [rcx+18h], 8
0x140008e6d  jb      short loc_140008E74
0x140008e6f  mov     rax, [rcx]
0x140008e72  jmp     short loc_140008E77
0x140008e74  mov     rax, rbx
0x140008e77  cmp     rsi, rax
0x140008e7a  jb      short loc_140008EBE
0x140008e7c  cmp     qword ptr [rcx+18h], 8
0x140008e81  jb      short loc_140008E86
0x140008e83  mov     rcx, [rcx]
0x140008e86  mov     rax, [rbx+10h]
0x140008e8a  lea     rcx, [rcx+rax*2]
0x140008e8e  cmp     rcx, rsi
0x140008e91  jbe     short loc_140008EBE
0x140008e93  cmp     qword ptr [rbx+18h], 8
0x140008e98  jb      short loc_140008E9F
0x140008e9a  mov     rax, [rbx]
0x140008e9d  jmp     short loc_140008EA2
0x140008e9f  mov     rax, rbx
0x140008ea2  sub     rsi, rax
0x140008ea5  mov     r9, rdi
0x140008ea8  sar     rsi, 1
0x140008eab  mov     rdx, rbx
0x140008eae  mov     r8, rsi
0x140008eb1  mov     rcx, rbx; void *
0x140008eb4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x140008eb9  jmp     loc_140008F49
0x140008ebe  mov     rax, 7FFFFFFFFFFFFFFEh
0x140008ec8  cmp     rdi, rax
0x140008ecb  ja      loc_140008F53
0x140008ed1  cmp     [rbx+18h], rdi
0x140008ed5  jnb     short loc_140008EF7
0x140008ed7  mov     r8, [rbx+10h]
0x140008edb  mov     rdx, rdi
0x140008ede  mov     rcx, rbx; Src
0x140008ee1  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x140008ee6  test    rdi, rdi
0x140008ee9  jz      short loc_140008F46
0x140008eeb  cmp     qword ptr [rbx+18h], 8
0x140008ef0  jb      short loc_140008F1A
0x140008ef2  mov     rcx, [rbx]
0x140008ef5  jmp     short loc_140008F1D
0x140008ef7  test    rdi, rdi
0x140008efa  jnz     short loc_140008EEB
0x140008efc  cmp     qword ptr [rbx+18h], 8
0x140008f01  jb      short loc_140008F08
0x140008f03  mov     rcx, [rbx]
0x140008f06  jmp     short loc_140008F0B
0x140008f08  mov     rcx, rbx
0x140008f0b  xor     eax, eax
0x140008f0d  mov     qword ptr [rbx+10h], 0
0x140008f15  mov     [rcx], ax
0x140008f18  jmp     short loc_140008F46
0x140008f1a  mov     rcx, rbx; void *
0x140008f1d  lea     r14, [rdi+rdi]
0x140008f21  mov     rdx, rsi; Src
0x140008f24  mov     r8, r14; Size
0x140008f27  call    memcpy_0
0x140008f2c  cmp     qword ptr [rbx+18h], 8
0x140008f31  jb      short loc_140008F38
0x140008f33  mov     rcx, [rbx]
0x140008f36  jmp     short loc_140008F3B
0x140008f38  mov     rcx, rbx
0x140008f3b  xor     eax, eax
0x140008f3d  mov     [rbx+10h], rdi
0x140008f41  mov     [r14+rcx], ax
0x140008f46  mov     rax, rbx
0x140008f49  add     rsp, 28h
0x140008f4d  pop     r14
0x140008f4f  pop     rdi
0x140008f50  pop     rsi
0x140008f51  pop     rbx
0x140008f52  retn
0x140008f53  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
