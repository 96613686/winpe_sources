# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x140008cd8`
- end: `0x140008e47`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `367`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x140008e50`
- `0x14000a8dc`
- `0x14000ad18`
- `0x14000b454`
- `0x14000c0e0`
- `0x14000c5d0`
- `0x14000c610`
- `0x14000c7b0`

## callees

- `0x1400086e0`
- `0x140008c90`
- `0x140008cc0`
- `0x140008cd8`
- `0x14000de86`
- `0x14000de92`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  _QWORD *v6; // r14
  _QWORD *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r14
  _WORD *v11; // rax
  char *v12; // rcx
  unsigned __int64 v13; // r14
  _QWORD *v14; // rax
  unsigned __int64 v15; // rax
  void *v16; // rcx
  _QWORD *v17; // rax

  v4 = a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = v8 + a3;
    if ( a1[2] < v8 + a3 )
      std::wstring::_Xran();
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + v9) = 0;
    v10 = v7[2];
    if ( v10 <= a3 )
    {
      if ( v7[3] < 8u )
        v11 = v7;
      else
        v11 = (_WORD *)*v7;
      v7[2] = 0;
LABEL_13:
      *v11 = 0;
      return v7;
    }
    if ( a3 )
    {
      if ( v7[3] < 8u )
        v12 = (char *)v7;
      else
        v12 = (char *)*v7;
      v13 = v10 - a3;
      if ( v13 )
        memmove_0(v12, &v12[2 * a3], 2 * v13);
      if ( v7[3] < 8u )
        v14 = v7;
      else
        v14 = (_QWORD *)*v7;
      v7[2] = v13;
      *((_WORD *)v14 + v13) = 0;
    }
  }
  else
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    v15 = a1[3];
    if ( v15 >= v8 )
    {
      if ( !v8 )
      {
        if ( v15 < 8 )
          v11 = a1;
        else
          v11 = (_WORD *)*a1;
        a1[2] = 0;
        goto LABEL_13;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)a1, v8, a1[2]);
      if ( !v8 )
        return v7;
    }
    if ( v6[3] >= 8u )
      v6 = (_QWORD *)*v6;
    if ( v7[3] < 8u )
      v16 = v7;
    else
      v16 = (void *)*v7;
    memcpy_0(v16, (char *)v6 + 2 * a3, 2 * v8);
    if ( v7[3] < 8u )
      v17 = v7;
    else
      v17 = (_QWORD *)*v7;
    v7[2] = v8;
    *((_WORD *)v17 + v8) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140008cd8  push    rbx
0x140008cda  push    rbp
0x140008cdb  push    rsi
0x140008cdc  push    rdi
0x140008cdd  push    r14
0x140008cdf  push    r15
0x140008ce1  sub     rsp, 28h
0x140008ce5  mov     rdi, [rdx+10h]
0x140008ce9  mov     rbp, r8
0x140008cec  mov     r14, rdx
0x140008cef  mov     rbx, rcx
0x140008cf2  cmp     rdi, r8
0x140008cf5  jb      loc_140008E35
0x140008cfb  sub     rdi, r8
0x140008cfe  cmp     r9, rdi
0x140008d01  cmovb   rdi, r9
0x140008d05  cmp     rcx, rdx
0x140008d08  jnz     loc_140008D9D
0x140008d0e  lea     rax, [rdi+r8]
0x140008d12  cmp     [rcx+10h], rax
0x140008d16  jb      loc_140008E3B
0x140008d1c  cmp     qword ptr [rcx+18h], 8
0x140008d21  jb      short loc_140008D26
0x140008d23  mov     rcx, [rcx]
0x140008d26  xor     esi, esi
0x140008d28  mov     [rbx+10h], rax
0x140008d2c  mov     [rcx+rax*2], si
0x140008d30  mov     r14, [rbx+10h]
0x140008d34  cmp     r14, rbp
0x140008d37  ja      short loc_140008D54
0x140008d39  cmp     qword ptr [rbx+18h], 8
0x140008d3e  jb      short loc_140008D45
0x140008d40  mov     rax, [rbx]
0x140008d43  jmp     short loc_140008D48
0x140008d45  mov     rax, rbx
0x140008d48  mov     [rbx+10h], rsi
0x140008d4c  mov     [rax], si
0x140008d4f  jmp     loc_140008E25
0x140008d54  test    rbp, rbp
0x140008d57  jz      loc_140008E25
0x140008d5d  cmp     qword ptr [rbx+18h], 8
0x140008d62  jb      short loc_140008D69
0x140008d64  mov     rcx, [rbx]
0x140008d67  jmp     short loc_140008D6C
0x140008d69  mov     rcx, rbx; void *
0x140008d6c  sub     r14, rbp
0x140008d6f  lea     rdi, [r14+r14]
0x140008d73  jz      short loc_140008D81
0x140008d75  lea     rdx, [rcx+r8*2]; Src
0x140008d79  mov     r8, rdi; Size
0x140008d7c  call    memmove_0
0x140008d81  cmp     qword ptr [rbx+18h], 8
0x140008d86  jb      short loc_140008D8D
0x140008d88  mov     rax, [rbx]
0x140008d8b  jmp     short loc_140008D90
0x140008d8d  mov     rax, rbx
0x140008d90  mov     [rbx+10h], r14
0x140008d94  mov     [rdi+rax], si
0x140008d98  jmp     loc_140008E25
0x140008d9d  mov     rax, 7FFFFFFFFFFFFFFEh
0x140008da7  cmp     rdi, rax
0x140008daa  ja      loc_140008E41
0x140008db0  mov     rax, [rcx+18h]
0x140008db4  xor     esi, esi
0x140008db6  cmp     rax, rdi
0x140008db9  jnb     short loc_140008DE2
0x140008dbb  mov     r8, [rcx+10h]
0x140008dbf  mov     rdx, rdi
0x140008dc2  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x140008dc7  test    rdi, rdi
0x140008dca  jz      short loc_140008E25
0x140008dcc  cmp     qword ptr [r14+18h], 8
0x140008dd1  jb      short loc_140008DD6
0x140008dd3  mov     r14, [r14]
0x140008dd6  cmp     qword ptr [rbx+18h], 8
0x140008ddb  jb      short loc_140008DFE
0x140008ddd  mov     rcx, [rbx]
0x140008de0  jmp     short loc_140008E01
0x140008de2  test    rdi, rdi
0x140008de5  jnz     short loc_140008DCC
0x140008de7  cmp     rax, 8
0x140008deb  jb      short loc_140008DF2
0x140008ded  mov     rax, [rcx]
0x140008df0  jmp     short loc_140008DF5
0x140008df2  mov     rax, rbx
0x140008df5  mov     [rcx+10h], rsi
0x140008df9  jmp     loc_140008D4C
0x140008dfe  mov     rcx, rbx; void *
0x140008e01  lea     r8, [rdi+rdi]; Size
0x140008e05  lea     rdx, [r14+rbp*2]; Src
0x140008e09  call    memcpy_0
0x140008e0e  cmp     qword ptr [rbx+18h], 8
0x140008e13  jb      short loc_140008E1A
0x140008e15  mov     rax, [rbx]
0x140008e18  jmp     short loc_140008E1D
0x140008e1a  mov     rax, rbx
0x140008e1d  mov     [rbx+10h], rdi
0x140008e21  mov     [rax+rdi*2], si
0x140008e25  mov     rax, rbx
0x140008e28  add     rsp, 28h
0x140008e2c  pop     r15
0x140008e2e  pop     r14
0x140008e30  pop     rdi
0x140008e31  pop     rsi
0x140008e32  pop     rbp
0x140008e33  pop     rbx
0x140008e34  retn
0x140008e35  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x140008e3b  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x140008e41  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
