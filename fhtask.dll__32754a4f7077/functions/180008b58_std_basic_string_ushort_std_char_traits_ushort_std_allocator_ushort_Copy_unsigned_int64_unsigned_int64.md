# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180008b58`
- end: `0x180008ca6`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `334`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006a10`
- `0x180006b24`
- `0x180008e44`
- `0x180008f44`

## callees

- `0x1800011d8`
- `0x180001d18`
- `0x180006950`
- `0x180008b58`
- `0x1800099b6`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008c52`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008c52`

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
0x180008b58  mov     [rsp+arg_10], r8
0x180008b5d  mov     [rsp+arg_8], rdx
0x180008b62  mov     [rsp+arg_0], rcx
0x180008b67  push    rbx
0x180008b68  push    rsi
0x180008b69  push    rdi
0x180008b6a  push    r12
0x180008b6c  push    r14
0x180008b6e  push    r15
0x180008b70  sub     rsp, 58h
0x180008b74  mov     r15, r8
0x180008b77  mov     rdi, rdx
0x180008b7a  mov     rbx, rcx
0x180008b7d  or      rdx, 7
0x180008b81  mov     r9, 7FFFFFFFFFFFFFFEh
0x180008b8b  cmp     rdx, r9
0x180008b8e  ja      short loc_180008BC4
0x180008b90  mov     rdi, rdx
0x180008b93  mov     r8, [rcx+18h]
0x180008b97  mov     rcx, r8
0x180008b9a  shr     rcx, 1
0x180008b9d  mov     rax, 0AAAAAAAAAAAAAAABh
0x180008ba7  mul     rdx
0x180008baa  shr     rdx, 1; char *
0x180008bad  cmp     rcx, rdx
0x180008bb0  jbe     short loc_180008BC4
0x180008bb2  mov     rax, r9
0x180008bb5  sub     rax, rcx
0x180008bb8  cmp     r8, rax
0x180008bbb  lea     rdi, [rcx+r8]
0x180008bbf  jbe     short loc_180008BC4
0x180008bc1  mov     rdi, r9
0x180008bc4  lea     rcx, [rdi+1]
0x180008bc8  xor     esi, esi
0x180008bca  test    rcx, rcx
0x180008bcd  jz      short loc_180008BF8
0x180008bcf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008bd9  cmp     rcx, rax
0x180008bdc  ja      loc_180008C89
0x180008be2  add     rcx, rcx; Size
0x180008be5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008bea  mov     r14, rax
0x180008bed  test    rax, rax
0x180008bf0  jz      loc_180008C89
0x180008bf6  jmp     short loc_180008BFB
0x180008bf8  mov     r14, rsi
0x180008bfb  jmp     short loc_180008C1F
0x180008bfd  xor     esi, esi
0x180008bff  mov     rbx, [rsp+88h+arg_0]
0x180008c07  mov     r15, [rsp+88h+arg_10]
0x180008c0f  mov     rdi, [rsp+88h+arg_8]
0x180008c17  mov     r14, [rsp+88h+arg_18]
0x180008c1f  test    r15, r15
0x180008c22  jz      short loc_180008C44
0x180008c24  cmp     qword ptr [rbx+18h], 8
0x180008c29  jb      short loc_180008C30
0x180008c2b  mov     rdx, [rbx]
0x180008c2e  jmp     short loc_180008C33
0x180008c30  mov     rdx, rbx; Src
0x180008c33  lea     r12, [r15+r15]
0x180008c37  mov     r8, r12; Size
0x180008c3a  mov     rcx, r14; void *
0x180008c3d  call    memcpy_0
0x180008c42  jmp     short loc_180008C48
0x180008c44  lea     r12, [r15+r15]
0x180008c48  cmp     qword ptr [rbx+18h], 8
0x180008c4d  jb      short loc_180008C58
0x180008c4f  mov     rcx, [rbx]
0x180008c52  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008c58  mov     qword ptr [rbx+18h], 7
0x180008c60  lea     rax, [rbx+10h]
0x180008c64  mov     [rbx], r14
0x180008c67  mov     [rbx+18h], rdi
0x180008c6b  cmp     rdi, 8
0x180008c6f  cmovnb  rbx, r14
0x180008c73  mov     [rax], r15
0x180008c76  mov     [r12+rbx], si
0x180008c7b  add     rsp, 58h
0x180008c7f  pop     r15
0x180008c81  pop     r14
0x180008c83  pop     r12
0x180008c85  pop     rdi
0x180008c86  pop     rsi
0x180008c87  pop     rbx
0x180008c88  retn
0x180008c89  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180008c8e  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180008c93  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180008c9a  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180008c9f  call    _CxxThrowException_0
```
