# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x180009fac`
- end: `0x18000a0b6`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `266`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `23`
- callee_count: `5`
- tags: ``

## callers

- `0x180009c80`
- `0x18000de00`
- `0x180011e80`
- `0x180012fcc`
- `0x18002306c`
- `0x1800230b0`
- `0x180026840`
- `0x180026dbc`
- `0x1800272e4`
- `0x1800277c4`
- `0x180027a00`
- `0x1800296fc`
- `0x18002b5c4`
- `0x18003130c`
- `0x180031afc`
- `0x1800320a8`
- `0x1800322c0`
- `0x1800338e0`
- `0x180033ad0`
- `0x180034030`
- `0x180034150`
- `0x180034a78`
- `0x180035150`

## callees

- `0x180003958`
- `0x180008f00`
- `0x18000918c`
- `0x180009fac`
- `0x180035852`

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
0x180009fac  push    rbx
0x180009fae  push    rsi
0x180009faf  push    rdi
0x180009fb0  push    r14
0x180009fb2  sub     rsp, 28h
0x180009fb6  mov     rdi, r8
0x180009fb9  mov     rsi, rdx
0x180009fbc  mov     rbx, rcx
0x180009fbf  test    rdx, rdx
0x180009fc2  jz      short loc_18000A01A
0x180009fc4  cmp     qword ptr [rcx+18h], 8
0x180009fc9  jb      short loc_180009FD0
0x180009fcb  mov     rax, [rcx]
0x180009fce  jmp     short loc_180009FD3
0x180009fd0  mov     rax, rbx
0x180009fd3  cmp     rsi, rax
0x180009fd6  jb      short loc_18000A01A
0x180009fd8  cmp     qword ptr [rcx+18h], 8
0x180009fdd  jb      short loc_180009FE2
0x180009fdf  mov     rcx, [rcx]
0x180009fe2  mov     rax, [rbx+10h]
0x180009fe6  lea     rcx, [rcx+rax*2]
0x180009fea  cmp     rcx, rsi
0x180009fed  jbe     short loc_18000A01A
0x180009fef  cmp     qword ptr [rbx+18h], 8
0x180009ff4  jb      short loc_180009FFB
0x180009ff6  mov     rax, [rbx]
0x180009ff9  jmp     short loc_180009FFE
0x180009ffb  mov     rax, rbx
0x180009ffe  sub     rsi, rax
0x18000a001  mov     r9, rdi
0x18000a004  sar     rsi, 1
0x18000a007  mov     rdx, rbx
0x18000a00a  mov     r8, rsi
0x18000a00d  mov     rcx, rbx; void *
0x18000a010  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a015  jmp     loc_18000A0A5
0x18000a01a  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a024  cmp     rdi, rax
0x18000a027  ja      loc_18000A0B0
0x18000a02d  cmp     [rbx+18h], rdi
0x18000a031  jnb     short loc_18000A053
0x18000a033  mov     r8, [rbx+10h]
0x18000a037  mov     rdx, rdi
0x18000a03a  mov     rcx, rbx; Src
0x18000a03d  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a042  test    rdi, rdi
0x18000a045  jz      short loc_18000A0A2
0x18000a047  cmp     qword ptr [rbx+18h], 8
0x18000a04c  jb      short loc_18000A076
0x18000a04e  mov     rcx, [rbx]
0x18000a051  jmp     short loc_18000A079
0x18000a053  test    rdi, rdi
0x18000a056  jnz     short loc_18000A047
0x18000a058  cmp     qword ptr [rbx+18h], 8
0x18000a05d  jb      short loc_18000A064
0x18000a05f  mov     rcx, [rbx]
0x18000a062  jmp     short loc_18000A067
0x18000a064  mov     rcx, rbx
0x18000a067  xor     eax, eax
0x18000a069  mov     qword ptr [rbx+10h], 0
0x18000a071  mov     [rcx], ax
0x18000a074  jmp     short loc_18000A0A2
0x18000a076  mov     rcx, rbx; void *
0x18000a079  lea     r14, [rdi+rdi]
0x18000a07d  mov     rdx, rsi; Src
0x18000a080  mov     r8, r14; Size
0x18000a083  call    memcpy_0
0x18000a088  cmp     qword ptr [rbx+18h], 8
0x18000a08d  jb      short loc_18000A094
0x18000a08f  mov     rcx, [rbx]
0x18000a092  jmp     short loc_18000A097
0x18000a094  mov     rcx, rbx
0x18000a097  xor     eax, eax
0x18000a099  mov     [rbx+10h], rdi
0x18000a09d  mov     [r14+rcx], ax
0x18000a0a2  mov     rax, rbx
0x18000a0a5  add     rsp, 28h
0x18000a0a9  pop     r14
0x18000a0ab  pop     rdi
0x18000a0ac  pop     rsi
0x18000a0ad  pop     rbx
0x18000a0ae  retn
0x18000a0b0  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
