# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator+=(ushort const *)

- ea: `0x180007818`
- end: `0x180007959`
- name: `??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z`
- size: `321`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _WORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008c30`
- `0x180009160`

## callees

- `0x180001e16`
- `0x180004b70`
- `0x180005e70`
- `0x180007818`
- `0x1800092b8`

## pseudocode

```c
_QWORD *__fastcall std::wstring::operator+=(_QWORD *Src, _WORD *a2)
{
  _QWORD *v3; // rbx
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rax
  _WORD *v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  _QWORD *v10; // rcx
  _WORD *v11; // rcx
  _QWORD *v12; // rcx

  v3 = Src;
  if ( *a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = Src[3];
  if ( v5 < 8 )
    v6 = Src;
  else
    v6 = (_QWORD *)*Src;
  if ( a2 >= (_WORD *)v6 )
  {
    if ( v5 >= 8 )
      Src = (_QWORD *)*Src;
    if ( (_WORD *)((char *)Src + 2 * v3[2]) > a2 )
    {
      if ( v5 < 8 )
        v7 = v3;
      else
        v7 = (_WORD *)*v3;
      return (_QWORD *)std::wstring::append(v3, v3, a2 - v7, v4);
    }
  }
  v8 = v3[2];
  if ( ~v8 <= v4 )
    std::wstring::_Xlen();
  if ( v4 )
  {
    v9 = v8 + v4;
    if ( v8 + v4 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v5 < v9 )
    {
      std::wstring::_Copy(v3);
      if ( !v9 )
        return v3;
      goto LABEL_21;
    }
    if ( v9 )
    {
LABEL_21:
      if ( v3[3] < 8u )
        v10 = v3;
      else
        v10 = (_QWORD *)*v3;
      memcpy_0((char *)v10 + 2 * v3[2], a2, 2 * v4);
      if ( v3[3] < 8u )
        v12 = v3;
      else
        v12 = (_QWORD *)*v3;
      v3[2] = v9;
      *((_WORD *)v12 + v9) = 0;
      return v3;
    }
    if ( v5 < 8 )
      v11 = v3;
    else
      v11 = (_WORD *)*v3;
    v3[2] = 0;
    *v11 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180007818  push    rbx
0x18000781a  push    rbp
0x18000781b  push    rsi
0x18000781c  push    rdi
0x18000781d  push    r14
0x18000781f  sub     rsp, 20h
0x180007823  xor     r14d, r14d
0x180007826  mov     rbp, rdx
0x180007829  mov     rbx, rcx
0x18000782c  cmp     [rdx], r14w
0x180007830  jnz     short loc_180007837
0x180007832  mov     esi, r14d
0x180007835  jmp     short loc_180007845
0x180007837  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000783b  inc     rsi
0x18000783e  cmp     [rdx+rsi*2], r14w
0x180007843  jnz     short loc_18000783B
0x180007845  mov     rdx, [rcx+18h]
0x180007849  cmp     rdx, 8
0x18000784d  jb      short loc_180007854
0x18000784f  mov     rax, [rcx]
0x180007852  jmp     short loc_180007857
0x180007854  mov     rax, rbx
0x180007857  cmp     rbp, rax
0x18000785a  jb      short loc_18000789F
0x18000785c  cmp     rdx, 8
0x180007860  jb      short loc_180007865
0x180007862  mov     rcx, [rcx]
0x180007865  mov     rax, [rbx+10h]
0x180007869  lea     rcx, [rcx+rax*2]
0x18000786d  cmp     rcx, rbp
0x180007870  jbe     short loc_18000789F
0x180007872  cmp     rdx, 8
0x180007876  jb      short loc_18000787D
0x180007878  mov     rax, [rbx]
0x18000787b  jmp     short loc_180007880
0x18000787d  mov     rax, rbx
0x180007880  sub     rbp, rax
0x180007883  mov     r9, rsi
0x180007886  sar     rbp, 1
0x180007889  mov     rdx, rbx
0x18000788c  mov     r8, rbp
0x18000788f  mov     rcx, rbx
0x180007892  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007897  mov     rbx, rax
0x18000789a  jmp     loc_18000793F
0x18000789f  mov     r8, [rbx+10h]
0x1800078a3  mov     rax, r8
0x1800078a6  not     rax
0x1800078a9  cmp     rax, rsi
0x1800078ac  jbe     loc_18000794D
0x1800078b2  test    rsi, rsi
0x1800078b5  jz      loc_18000793F
0x1800078bb  lea     rdi, [r8+rsi]
0x1800078bf  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800078c9  cmp     rdi, rax
0x1800078cc  ja      loc_180007953
0x1800078d2  cmp     rdx, rdi
0x1800078d5  jnb     short loc_1800078F3
0x1800078d7  mov     rdx, rdi
0x1800078da  mov     rcx, rbx; Src
0x1800078dd  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800078e2  test    rdi, rdi
0x1800078e5  jz      short loc_18000793F
0x1800078e7  cmp     qword ptr [rbx+18h], 8
0x1800078ec  jb      short loc_180007910
0x1800078ee  mov     rcx, [rbx]
0x1800078f1  jmp     short loc_180007913
0x1800078f3  test    rdi, rdi
0x1800078f6  jnz     short loc_1800078E7
0x1800078f8  cmp     rdx, 8
0x1800078fc  jb      short loc_180007903
0x1800078fe  mov     rcx, [rbx]
0x180007901  jmp     short loc_180007906
0x180007903  mov     rcx, rbx
0x180007906  mov     [rbx+10h], r14
0x18000790a  mov     [rcx], r14w
0x18000790e  jmp     short loc_18000793F
0x180007910  mov     rcx, rbx
0x180007913  mov     rax, [rbx+10h]
0x180007917  lea     r8, [rsi+rsi]; Size
0x18000791b  mov     rdx, rbp; Src
0x18000791e  lea     rcx, [rcx+rax*2]; void *
0x180007922  call    memcpy_0
0x180007927  cmp     qword ptr [rbx+18h], 8
0x18000792c  jb      short loc_180007933
0x18000792e  mov     rcx, [rbx]
0x180007931  jmp     short loc_180007936
0x180007933  mov     rcx, rbx
0x180007936  mov     [rbx+10h], rdi
0x18000793a  mov     [rcx+rdi*2], r14w
0x18000793f  mov     rax, rbx
0x180007942  add     rsp, 20h
0x180007946  pop     r14
0x180007948  pop     rdi
0x180007949  pop     rsi
0x18000794a  pop     rbp
0x18000794b  pop     rbx
0x18000794c  retn
0x18000794d  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x180007953  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
