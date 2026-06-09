# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006418`
- end: `0x180006566`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `334`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006600`
- `0x1800067b4`
- `0x18000a52c`
- `0x18000a62c`

## callees

- `0x1800011c4`
- `0x180001d04`
- `0x180002f58`
- `0x180006418`
- `0x18000ab16`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006512`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006512`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // r12
  _QWORD *result; // rax
  void *v14; // rax
  unsigned __int64 v15; // rcx
  const char *v16; // rdx
  _BYTE *v17; // rdx
  _BYTE v18[32]; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v20[80]; // [rsp+38h] [rbp-50h] BYREF
  void *v24; // [rsp+A8h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
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
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, (const char *)v6);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  catch ( ... )
  {
    v16 = v18;
    try
    {
      v14 = 0;
      v15 = a2 + 1;
      if ( a2 != -1 && (v15 > 0x7FFFFFFFFFFFFFFFLL || (v14 = operator new(2 * v15)) == 0) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v20, v16);
        throw (std::bad_alloc *)v20;
      }
      v24 = v14;
    }
    catch ( ... )
    {
      v17 = v18;
      LOBYTE(v17) = 1;
      std::wstring::_Tidy(Src, v17, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v24;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    v12 = 2 * v3;
    memcpy_0(v10, v11, 2 * v3);
  }
  else
  {
    v12 = 0;
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  v5[3] = (const void *)7;
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *(_WORD *)((char *)v5 + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x180006418  mov     [rsp+arg_10], r8
0x18000641d  mov     [rsp+arg_8], rdx
0x180006422  mov     [rsp+arg_0], rcx
0x180006427  push    rbx
0x180006428  push    rsi
0x180006429  push    rdi
0x18000642a  push    r12
0x18000642c  push    r14
0x18000642e  push    r15
0x180006430  sub     rsp, 58h
0x180006434  mov     r15, r8
0x180006437  mov     rdi, rdx
0x18000643a  mov     rbx, rcx
0x18000643d  or      rdx, 7
0x180006441  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000644b  cmp     rdx, r9
0x18000644e  ja      short loc_180006484
0x180006450  mov     rdi, rdx
0x180006453  mov     r8, [rcx+18h]
0x180006457  mov     rcx, r8
0x18000645a  shr     rcx, 1
0x18000645d  mov     rax, 0AAAAAAAAAAAAAAABh
0x180006467  mul     rdx
0x18000646a  shr     rdx, 1; char *
0x18000646d  cmp     rcx, rdx
0x180006470  jbe     short loc_180006484
0x180006472  mov     rax, r9
0x180006475  sub     rax, rcx
0x180006478  cmp     r8, rax
0x18000647b  lea     rdi, [rcx+r8]
0x18000647f  jbe     short loc_180006484
0x180006481  mov     rdi, r9
0x180006484  lea     rcx, [rdi+1]
0x180006488  xor     esi, esi
0x18000648a  test    rcx, rcx
0x18000648d  jz      short loc_1800064B8
0x18000648f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180006499  cmp     rcx, rax
0x18000649c  ja      loc_180006549
0x1800064a2  add     rcx, rcx; Size
0x1800064a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064aa  mov     r14, rax
0x1800064ad  test    rax, rax
0x1800064b0  jz      loc_180006549
0x1800064b6  jmp     short loc_1800064BB
0x1800064b8  mov     r14, rsi
0x1800064bb  jmp     short loc_1800064DF
0x1800064bd  xor     esi, esi
0x1800064bf  mov     rbx, [rsp+88h+arg_0]
0x1800064c7  mov     r15, [rsp+88h+arg_10]
0x1800064cf  mov     rdi, [rsp+88h+arg_8]
0x1800064d7  mov     r14, [rsp+88h+arg_18]
0x1800064df  test    r15, r15
0x1800064e2  jz      short loc_180006504
0x1800064e4  cmp     qword ptr [rbx+18h], 8
0x1800064e9  jb      short loc_1800064F0
0x1800064eb  mov     rdx, [rbx]
0x1800064ee  jmp     short loc_1800064F3
0x1800064f0  mov     rdx, rbx; Src
0x1800064f3  lea     r12, [r15+r15]
0x1800064f7  mov     r8, r12; Size
0x1800064fa  mov     rcx, r14; void *
0x1800064fd  call    memcpy_0
0x180006502  jmp     short loc_180006508
0x180006504  lea     r12, [r15+r15]
0x180006508  cmp     qword ptr [rbx+18h], 8
0x18000650d  jb      short loc_180006518
0x18000650f  mov     rcx, [rbx]
0x180006512  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006518  mov     qword ptr [rbx+18h], 7
0x180006520  lea     rax, [rbx+10h]
0x180006524  mov     [rbx], r14
0x180006527  mov     [rbx+18h], rdi
0x18000652b  cmp     rdi, 8
0x18000652f  cmovnb  rbx, r14
0x180006533  mov     [rax], r15
0x180006536  mov     [r12+rbx], si
0x18000653b  add     rsp, 58h
0x18000653f  pop     r15
0x180006541  pop     r14
0x180006543  pop     r12
0x180006545  pop     rdi
0x180006546  pop     rsi
0x180006547  pop     rbx
0x180006548  retn
0x180006549  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000654e  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180006553  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000655a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000655f  call    _CxxThrowException_0
```
