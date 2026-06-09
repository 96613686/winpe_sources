# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001974`
- end: `0x180001a68`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180007830`

## callees

- `0x180001910`
- `0x180001974`
- `0x180002630`
- `0x18000265c`
- `0x180002928`
- `0x180002ad8`

## pseudocode

```c
__int64 __fastcall std::wstring::_Copy(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsi
  const void *v11; // rdx
  void *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = (const void **)a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 24);
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v16;
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = (const void **)a1;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  return std::wstring::_Eos(v5, v3);
}

```

## disassembly

```asm
0x180001974  mov     [rsp+arg_10], r8
0x180001979  mov     [rsp+arg_8], rdx
0x18000197e  mov     [rsp+arg_0], rcx
0x180001983  push    rbx
0x180001984  push    rsi
0x180001985  push    rdi
0x180001986  push    r14
0x180001988  sub     rsp, 28h
0x18000198c  mov     r14, r8
0x18000198f  mov     rdi, rdx
0x180001992  mov     rbx, rcx
0x180001995  or      rdx, 7
0x180001999  mov     r9, 7FFFFFFFFFFFFFFEh
0x1800019a3  cmp     rdx, r9
0x1800019a6  ja      short loc_1800019DC
0x1800019a8  mov     rdi, rdx
0x1800019ab  mov     r8, [rcx+18h]
0x1800019af  mov     rcx, r8
0x1800019b2  shr     rcx, 1
0x1800019b5  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800019bf  mul     rdx
0x1800019c2  shr     rdx, 1
0x1800019c5  cmp     rcx, rdx
0x1800019c8  jbe     short loc_1800019DC
0x1800019ca  mov     rax, r9
0x1800019cd  sub     rax, rcx
0x1800019d0  cmp     r8, rax
0x1800019d3  lea     rdi, [rcx+r8]
0x1800019d7  jbe     short loc_1800019DC
0x1800019d9  mov     rdi, r9
0x1800019dc  lea     rcx, [rdi+1]
0x1800019e0  test    rcx, rcx
0x1800019e3  jz      short loc_180001A09
0x1800019e5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800019ef  cmp     rcx, rax
0x1800019f2  ja      short loc_180001A04
0x1800019f4  add     rcx, rcx; Size
0x1800019f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800019fc  mov     rsi, rax
0x1800019ff  test    rax, rax
0x180001a02  jnz     short loc_180001A0B
0x180001a04  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180001a09  xor     esi, esi
0x180001a0b  jmp     short loc_180001A21
0x180001a0d  mov     rbx, [rsp+48h+arg_0]
0x180001a12  mov     r14, [rsp+48h+arg_10]
0x180001a17  mov     rdi, [rsp+48h+arg_8]
0x180001a1c  mov     rsi, [rsp+48h+arg_18]
0x180001a21  test    r14, r14
0x180001a24  jz      short loc_180001A40
0x180001a26  cmp     qword ptr [rbx+18h], 8
0x180001a2b  jb      short loc_180001A32
0x180001a2d  mov     rdx, [rbx]
0x180001a30  jmp     short loc_180001A35
0x180001a32  mov     rdx, rbx
0x180001a35  mov     r8, r14
0x180001a38  mov     rcx, rsi
0x180001a3b  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180001a40  xor     r8d, r8d
0x180001a43  mov     dl, 1
0x180001a45  mov     rcx, rbx
0x180001a48  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180001a4d  mov     [rbx], rsi
0x180001a50  mov     [rbx+18h], rdi
0x180001a54  mov     rdx, r14
0x180001a57  mov     rcx, rbx
0x180001a5a  add     rsp, 28h
0x180001a5e  pop     r14
0x180001a60  pop     rdi
0x180001a61  pop     rsi
0x180001a62  pop     rbx
0x180001a63  jmp     ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
```
