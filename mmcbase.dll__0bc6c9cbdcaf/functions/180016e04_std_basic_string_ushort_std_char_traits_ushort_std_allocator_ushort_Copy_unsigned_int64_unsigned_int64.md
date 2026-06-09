# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180016e04`
- end: `0x180016f0c`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180016f14`

## callees

- `0x180009928`
- `0x180016e04`
- `0x180016fc0`
- `0x180017380`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180016e8b`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x180016e8b`

## pseudocode

```c
const void **__fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  const void **result; // rax
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
  result = v5;
  if ( v4 >= 8 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180016e04  mov     [rsp+arg_10], r8
0x180016e09  mov     [rsp+arg_8], rdx
0x180016e0e  mov     [rsp+arg_0], rcx
0x180016e13  push    rbx
0x180016e14  push    rsi
0x180016e15  push    rdi
0x180016e16  push    r14
0x180016e18  push    r15
0x180016e1a  sub     rsp, 20h
0x180016e1e  mov     r15, r8
0x180016e21  mov     rbx, rdx
0x180016e24  mov     rdi, rcx
0x180016e27  or      rdx, 7
0x180016e2b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180016e35  cmp     rdx, r9
0x180016e38  ja      short loc_180016E6E
0x180016e3a  mov     rbx, rdx
0x180016e3d  mov     r8, [rcx+18h]
0x180016e41  mov     rcx, r8
0x180016e44  shr     rcx, 1
0x180016e47  mov     rax, 0AAAAAAAAAAAAAAABh
0x180016e51  mul     rdx
0x180016e54  shr     rdx, 1
0x180016e57  cmp     rcx, rdx
0x180016e5a  jbe     short loc_180016E6E
0x180016e5c  mov     rax, r9
0x180016e5f  sub     rax, rcx
0x180016e62  cmp     r8, rax
0x180016e65  lea     rbx, [rcx+r8]
0x180016e69  jbe     short loc_180016E6E
0x180016e6b  mov     rbx, r9
0x180016e6e  lea     rcx, [rbx+1]
0x180016e72  xor     esi, esi
0x180016e74  test    rcx, rcx
0x180016e77  jz      short loc_180016E9E
0x180016e79  mov     rax, 7FFFFFFFFFFFFFFFh
0x180016e83  cmp     rcx, rax
0x180016e86  ja      short loc_180016E99
0x180016e88  add     rcx, rcx
0x180016e8b  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016e91  mov     r14, rax
0x180016e94  test    rax, rax
0x180016e97  jnz     short loc_180016EA1
0x180016e99  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180016e9e  mov     r14, rsi
0x180016ea1  jmp     short loc_180016EB9
0x180016ea3  xor     esi, esi
0x180016ea5  mov     rdi, [rsp+48h+arg_0]
0x180016eaa  mov     r15, [rsp+48h+arg_10]
0x180016eaf  mov     rbx, [rsp+48h+arg_8]
0x180016eb4  mov     r14, [rsp+48h+arg_18]
0x180016eb9  test    r15, r15
0x180016ebc  jz      short loc_180016ED8
0x180016ebe  cmp     qword ptr [rdi+18h], 8
0x180016ec3  jb      short loc_180016ECA
0x180016ec5  mov     rdx, [rdi]
0x180016ec8  jmp     short loc_180016ECD
0x180016eca  mov     rdx, rdi
0x180016ecd  mov     r8, r15
0x180016ed0  mov     rcx, r14
0x180016ed3  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180016ed8  xor     r8d, r8d
0x180016edb  mov     dl, 1
0x180016edd  mov     rcx, rdi
0x180016ee0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016ee5  mov     [rdi], r14
0x180016ee8  mov     [rdi+18h], rbx
0x180016eec  mov     rax, rdi
0x180016eef  cmp     rbx, 8
0x180016ef3  cmovnb  rax, r14
0x180016ef7  mov     [rdi+10h], r15
0x180016efb  mov     [rax+r15*2], si
0x180016f00  add     rsp, 20h
0x180016f04  pop     r15
0x180016f06  pop     r14
0x180016f08  pop     rdi
0x180016f09  pop     rsi
0x180016f0a  pop     rbx
0x180016f0b  retn
```
