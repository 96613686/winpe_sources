# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000354c`
- end: `0x180003643`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800036e4`
- `0x1800037dc`

## callees

- `0x1800012e0`
- `0x180001488`
- `0x180001fb6`
- `0x18000354c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000360a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000360a`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000354c  mov     [rsp+arg_10], r8
0x180003551  mov     [rsp+arg_8], rdx
0x180003556  mov     [rsp+arg_0], rcx
0x18000355b  push    rbx
0x18000355c  push    rsi
0x18000355d  push    rdi
0x18000355e  push    r14
0x180003560  sub     rsp, 28h
0x180003564  mov     r14, r8
0x180003567  mov     rdi, rdx
0x18000356a  mov     rbx, rcx
0x18000356d  or      rdx, 0Fh
0x180003571  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180003578  cmp     rdx, r9
0x18000357b  ja      short loc_1800035B1
0x18000357d  mov     rdi, rdx
0x180003580  mov     r8, [rcx+18h]
0x180003584  mov     rcx, r8
0x180003587  shr     rcx, 1
0x18000358a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180003594  mul     rdx
0x180003597  shr     rdx, 1
0x18000359a  cmp     rcx, rdx
0x18000359d  jbe     short loc_1800035B1
0x18000359f  mov     rax, r9
0x1800035a2  sub     rax, rcx
0x1800035a5  cmp     r8, rax
0x1800035a8  lea     rdi, [rcx+r8]
0x1800035ac  jbe     short loc_1800035B1
0x1800035ae  mov     rdi, r9
0x1800035b1  lea     rcx, [rdi+1]; Size
0x1800035b5  test    rcx, rcx
0x1800035b8  jz      short loc_1800035C9
0x1800035ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035bf  mov     rsi, rax
0x1800035c2  test    rax, rax
0x1800035c5  jz      short loc_18000363C
0x1800035c7  jmp     short loc_1800035CB
0x1800035c9  xor     esi, esi
0x1800035cb  jmp     short loc_1800035E1
0x1800035cd  mov     rbx, [rsp+48h+arg_0]
0x1800035d2  mov     r14, [rsp+48h+arg_10]
0x1800035d7  mov     rdi, [rsp+48h+arg_8]
0x1800035dc  mov     rsi, [rsp+48h+arg_18]
0x1800035e1  test    r14, r14
0x1800035e4  jz      short loc_180003600
0x1800035e6  cmp     qword ptr [rbx+18h], 10h
0x1800035eb  jb      short loc_1800035F2
0x1800035ed  mov     rdx, [rbx]
0x1800035f0  jmp     short loc_1800035F5
0x1800035f2  mov     rdx, rbx; Src
0x1800035f5  mov     r8, r14; Size
0x1800035f8  mov     rcx, rsi; void *
0x1800035fb  call    memcpy_0
0x180003600  cmp     qword ptr [rbx+18h], 10h
0x180003605  jb      short loc_180003616
0x180003607  mov     rcx, [rbx]
0x18000360a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003611  nop     dword ptr [rax+rax+00h]
0x180003616  lea     rax, [rbx+10h]
0x18000361a  mov     [rbx], rsi
0x18000361d  mov     [rbx+18h], rdi
0x180003621  cmp     rdi, 10h
0x180003625  cmovnb  rbx, rsi
0x180003629  mov     [rax], r14
0x18000362c  mov     byte ptr [rbx+r14], 0
0x180003631  add     rsp, 28h
0x180003635  pop     r14
0x180003637  pop     rdi
0x180003638  pop     rsi
0x180003639  pop     rbx
0x18000363a  retn
0x18000363c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
