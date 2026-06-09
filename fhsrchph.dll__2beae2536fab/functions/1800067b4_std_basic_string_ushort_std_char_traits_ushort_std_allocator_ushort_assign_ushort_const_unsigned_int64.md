# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x1800067b4`
- end: `0x1800068bd`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `265`
- prototype: `_QWORD *__fastcall(_QWORD *Src, char *, unsigned __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180004020`
- `0x180006dc0`
- `0x1800091fc`
- `0x1800093b4`
- `0x1800099e4`

## callees

- `0x180006418`
- `0x1800065d0`
- `0x180006600`
- `0x1800067b4`
- `0x18000ab16`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *Src, char *a2, unsigned __int64 a3)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _BYTE *v7; // rax
  void *v9; // rcx
  _WORD *v10; // rcx
  _WORD *v11; // rcx

  v5 = Src;
  if ( !a2 )
    goto LABEL_13;
  v6 = Src[3] < 8u ? (char *)Src : (char *)*Src;
  if ( a2 < v6 )
    goto LABEL_13;
  if ( Src[3] >= 8u )
    Src = (_QWORD *)*Src;
  if ( (char *)Src + 2 * v5[2] <= a2 )
  {
LABEL_13:
    if ( a3 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v5[3] >= a3 )
    {
      if ( !a3 )
      {
        if ( v5[3] < 8u )
          v10 = v5;
        else
          v10 = (_WORD *)*v5;
        v5[2] = 0;
        *v10 = 0;
        return v5;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)v5, a3, v5[2]);
      if ( !a3 )
        return v5;
    }
    if ( v5[3] < 8u )
      v9 = v5;
    else
      v9 = (void *)*v5;
    memcpy_0(v9, a2, 2 * a3);
    if ( v5[3] < 8u )
      v11 = v5;
    else
      v11 = (_WORD *)*v5;
    v5[2] = a3;
    v11[a3] = 0;
    return v5;
  }
  if ( v5[3] < 8u )
    v7 = v5;
  else
    v7 = (_BYTE *)*v5;
  return std::wstring::assign(v5, v5, (a2 - v7) >> 1, a3);
}

```

## disassembly

```asm
0x1800067b4  push    rbx
0x1800067b6  push    rsi
0x1800067b7  push    rdi
0x1800067b8  push    r14
0x1800067ba  sub     rsp, 28h
0x1800067be  mov     rdi, r8
0x1800067c1  mov     rsi, rdx
0x1800067c4  mov     rbx, rcx
0x1800067c7  test    rdx, rdx
0x1800067ca  jz      short loc_180006822
0x1800067cc  cmp     qword ptr [rcx+18h], 8
0x1800067d1  jb      short loc_1800067D8
0x1800067d3  mov     rax, [rcx]
0x1800067d6  jmp     short loc_1800067DB
0x1800067d8  mov     rax, rbx
0x1800067db  cmp     rsi, rax
0x1800067de  jb      short loc_180006822
0x1800067e0  cmp     qword ptr [rcx+18h], 8
0x1800067e5  jb      short loc_1800067EA
0x1800067e7  mov     rcx, [rcx]
0x1800067ea  mov     rax, [rbx+10h]
0x1800067ee  lea     rcx, [rcx+rax*2]
0x1800067f2  cmp     rcx, rsi
0x1800067f5  jbe     short loc_180006822
0x1800067f7  cmp     qword ptr [rbx+18h], 8
0x1800067fc  jb      short loc_180006803
0x1800067fe  mov     rax, [rbx]
0x180006801  jmp     short loc_180006806
0x180006803  mov     rax, rbx
0x180006806  sub     rsi, rax
0x180006809  mov     r9, rdi
0x18000680c  sar     rsi, 1
0x18000680f  mov     rdx, rbx
0x180006812  mov     r8, rsi
0x180006815  mov     rcx, rbx; Src
0x180006818  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000681d  jmp     loc_1800068AD
0x180006822  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000682c  cmp     rdi, rax
0x18000682f  ja      loc_1800068B7
0x180006835  cmp     [rbx+18h], rdi
0x180006839  jnb     short loc_18000685B
0x18000683b  mov     r8, [rbx+10h]
0x18000683f  mov     rdx, rdi
0x180006842  mov     rcx, rbx; Src
0x180006845  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000684a  test    rdi, rdi
0x18000684d  jz      short loc_1800068AA
0x18000684f  cmp     qword ptr [rbx+18h], 8
0x180006854  jb      short loc_18000687E
0x180006856  mov     rcx, [rbx]
0x180006859  jmp     short loc_180006881
0x18000685b  test    rdi, rdi
0x18000685e  jnz     short loc_18000684F
0x180006860  cmp     qword ptr [rbx+18h], 8
0x180006865  jb      short loc_18000686C
0x180006867  mov     rcx, [rbx]
0x18000686a  jmp     short loc_18000686F
0x18000686c  mov     rcx, rbx
0x18000686f  xor     eax, eax
0x180006871  mov     qword ptr [rbx+10h], 0
0x180006879  mov     [rcx], ax
0x18000687c  jmp     short loc_1800068AA
0x18000687e  mov     rcx, rbx; void *
0x180006881  lea     r14, [rdi+rdi]
0x180006885  mov     rdx, rsi; Src
0x180006888  mov     r8, r14; Size
0x18000688b  call    memcpy_0
0x180006890  cmp     qword ptr [rbx+18h], 8
0x180006895  jb      short loc_18000689C
0x180006897  mov     rcx, [rbx]
0x18000689a  jmp     short loc_18000689F
0x18000689c  mov     rcx, rbx
0x18000689f  xor     eax, eax
0x1800068a1  mov     [rbx+10h], rdi
0x1800068a5  mov     [r14+rcx], ax
0x1800068aa  mov     rax, rbx
0x1800068ad  add     rsp, 28h
0x1800068b1  pop     r14
0x1800068b3  pop     rdi
0x1800068b4  pop     rsi
0x1800068b5  pop     rbx
0x1800068b6  retn
0x1800068b7  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
