# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::append(ushort const *,unsigned __int64)

- ea: `0x180003078`
- end: `0x1800031a7`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180002474`
- `0x180002610`
- `0x1800026d0`
- `0x180002b44`
- `0x180008930`
- `0x18000d38c`
- `0x18000dab0`
- `0x18000dba0`
- `0x18000df20`

## callees

- `0x180001f56`
- `0x180002cb0`
- `0x180002f48`
- `0x180002f78`
- `0x180003078`

## pseudocode

```c
_QWORD *__fastcall std::wstring::append(_QWORD *Src, char *a2, unsigned __int64 a3)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _BYTE *v7; // rax
  __int64 v9; // r8
  unsigned __int64 v10; // rdi
  char *v11; // rcx
  _WORD *v12; // rcx
  _WORD *v13; // rcx

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
    v9 = v5[2];
    if ( ~v9 <= a3 )
      std::wstring::_Xlen();
    if ( !a3 )
      return v5;
    v10 = v9 + a3;
    if ( v9 + a3 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v5[3] >= v10 )
    {
      if ( !v10 )
      {
        if ( v5[3] < 8u )
          v12 = v5;
        else
          v12 = (_WORD *)*v5;
        v5[2] = 0;
        *v12 = 0;
        return v5;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)v5, v9 + a3, v9);
      if ( !v10 )
        return v5;
    }
    if ( v5[3] < 8u )
      v11 = (char *)v5;
    else
      v11 = (char *)*v5;
    memcpy_0(&v11[2 * v5[2]], a2, 2 * a3);
    if ( v5[3] < 8u )
      v13 = v5;
    else
      v13 = (_WORD *)*v5;
    v5[2] = v10;
    v13[v10] = 0;
    return v5;
  }
  if ( v5[3] < 8u )
    v7 = v5;
  else
    v7 = (_BYTE *)*v5;
  return (_QWORD *)std::wstring::append(v5, v5, (a2 - v7) >> 1, a3);
}

```

## disassembly

```asm
0x180003078  push    rbx
0x18000307a  push    rsi
0x18000307b  push    rdi
0x18000307c  push    r14
0x18000307e  sub     rsp, 28h
0x180003082  mov     r14, r8
0x180003085  mov     rsi, rdx
0x180003088  mov     rbx, rcx
0x18000308b  test    rdx, rdx
0x18000308e  jz      short loc_1800030E6
0x180003090  cmp     qword ptr [rcx+18h], 8
0x180003095  jb      short loc_18000309C
0x180003097  mov     rax, [rcx]
0x18000309a  jmp     short loc_18000309F
0x18000309c  mov     rax, rbx
0x18000309f  cmp     rsi, rax
0x1800030a2  jb      short loc_1800030E6
0x1800030a4  cmp     qword ptr [rcx+18h], 8
0x1800030a9  jb      short loc_1800030AE
0x1800030ab  mov     rcx, [rcx]
0x1800030ae  mov     rax, [rbx+10h]
0x1800030b2  lea     rcx, [rcx+rax*2]
0x1800030b6  cmp     rcx, rsi
0x1800030b9  jbe     short loc_1800030E6
0x1800030bb  cmp     qword ptr [rbx+18h], 8
0x1800030c0  jb      short loc_1800030C7
0x1800030c2  mov     rax, [rbx]
0x1800030c5  jmp     short loc_1800030CA
0x1800030c7  mov     rax, rbx
0x1800030ca  sub     rsi, rax
0x1800030cd  mov     r9, r14
0x1800030d0  sar     rsi, 1
0x1800030d3  mov     rdx, rbx
0x1800030d6  mov     r8, rsi
0x1800030d9  mov     rcx, rbx
0x1800030dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800030e1  jmp     loc_180003191
0x1800030e6  mov     r8, [rbx+10h]
0x1800030ea  mov     rax, r8
0x1800030ed  not     rax
0x1800030f0  cmp     rax, r14
0x1800030f3  jbe     loc_18000319B
0x1800030f9  test    r14, r14
0x1800030fc  jz      loc_18000318E
0x180003102  lea     rdi, [r8+r14]
0x180003106  mov     rax, 7FFFFFFFFFFFFFFEh
0x180003110  cmp     rdi, rax
0x180003113  ja      loc_1800031A1
0x180003119  cmp     [rbx+18h], rdi
0x18000311d  jnb     short loc_18000313B
0x18000311f  mov     rdx, rdi
0x180003122  mov     rcx, rbx; Src
0x180003125  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000312a  test    rdi, rdi
0x18000312d  jz      short loc_18000318E
0x18000312f  cmp     qword ptr [rbx+18h], 8
0x180003134  jb      short loc_18000315E
0x180003136  mov     rcx, [rbx]
0x180003139  jmp     short loc_180003161
0x18000313b  test    rdi, rdi
0x18000313e  jnz     short loc_18000312F
0x180003140  cmp     qword ptr [rbx+18h], 8
0x180003145  jb      short loc_18000314C
0x180003147  mov     rcx, [rbx]
0x18000314a  jmp     short loc_18000314F
0x18000314c  mov     rcx, rbx
0x18000314f  xor     eax, eax
0x180003151  mov     qword ptr [rbx+10h], 0
0x180003159  mov     [rcx], ax
0x18000315c  jmp     short loc_18000318E
0x18000315e  mov     rcx, rbx
0x180003161  mov     rax, [rbx+10h]
0x180003165  lea     r8, [r14+r14]; Size
0x180003169  mov     rdx, rsi; Src
0x18000316c  lea     rcx, [rcx+rax*2]; void *
0x180003170  call    memcpy_0
0x180003175  cmp     qword ptr [rbx+18h], 8
0x18000317a  jb      short loc_180003181
0x18000317c  mov     rcx, [rbx]
0x18000317f  jmp     short loc_180003184
0x180003181  mov     rcx, rbx
0x180003184  xor     eax, eax
0x180003186  mov     [rbx+10h], rdi
0x18000318a  mov     [rcx+rdi*2], ax
0x18000318e  mov     rax, rbx
0x180003191  add     rsp, 28h
0x180003195  pop     r14
0x180003197  pop     rdi
0x180003198  pop     rsi
0x180003199  pop     rbx
0x18000319a  retn
0x18000319b  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x1800031a1  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
