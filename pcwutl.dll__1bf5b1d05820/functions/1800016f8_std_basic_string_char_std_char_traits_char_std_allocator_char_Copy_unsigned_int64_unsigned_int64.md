# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800016f8`
- end: `0x1800017ef`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001908`
- `0x180001a00`

## callees

- `0x180001524`
- `0x1800016f8`
- `0x180001858`
- `0x180002670`
- `0x1800027d6`

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
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
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
      v13 = v14;
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
0x1800016f8  mov     rax, rsp
0x1800016fb  mov     [rax+18h], r8
0x1800016ff  mov     [rax+10h], rdx
0x180001703  mov     [rax+8], rcx
0x180001707  push    rbx
0x180001708  push    rsi
0x180001709  push    rdi
0x18000170a  push    r14
0x18000170c  sub     rsp, 38h
0x180001710  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001718  mov     r14, r8
0x18000171b  mov     rdi, rdx
0x18000171e  mov     rbx, rcx
0x180001721  or      rdx, 0Fh
0x180001725  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000172c  cmp     rdx, r9
0x18000172f  ja      short loc_180001765
0x180001731  mov     rdi, rdx
0x180001734  mov     r8, [rcx+18h]
0x180001738  mov     rcx, r8
0x18000173b  shr     rcx, 1
0x18000173e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001748  mul     rdx
0x18000174b  shr     rdx, 1
0x18000174e  cmp     rcx, rdx
0x180001751  jbe     short loc_180001765
0x180001753  mov     rax, r9
0x180001756  sub     rax, rcx
0x180001759  cmp     r8, rax
0x18000175c  lea     rdi, [rcx+r8]
0x180001760  jbe     short loc_180001765
0x180001762  mov     rdi, r9
0x180001765  lea     rcx, [rdi+1]; Size
0x180001769  test    rcx, rcx
0x18000176c  jz      short loc_18000177D
0x18000176e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001773  mov     rsi, rax
0x180001776  test    rax, rax
0x180001779  jz      short loc_1800017E8
0x18000177b  jmp     short loc_18000177F
0x18000177d  xor     esi, esi
0x18000177f  jmp     short loc_180001795
0x180001781  mov     rbx, [rsp+58h+arg_0]
0x180001786  mov     r14, [rsp+58h+arg_10]
0x18000178b  mov     rdi, [rsp+58h+arg_8]
0x180001790  mov     rsi, [rsp+58h+arg_18]
0x180001795  test    r14, r14
0x180001798  jz      short loc_1800017B4
0x18000179a  cmp     qword ptr [rbx+18h], 10h
0x18000179f  jb      short loc_1800017A6
0x1800017a1  mov     rdx, [rbx]
0x1800017a4  jmp     short loc_1800017A9
0x1800017a6  mov     rdx, rbx; Src
0x1800017a9  mov     r8, r14; Size
0x1800017ac  mov     rcx, rsi; void *
0x1800017af  call    memcpy_0
0x1800017b4  cmp     qword ptr [rbx+18h], 10h
0x1800017b9  jb      short loc_1800017C3
0x1800017bb  mov     rcx, [rbx]; void *
0x1800017be  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800017c3  lea     rax, [rbx+10h]
0x1800017c7  mov     [rbx], rsi
0x1800017ca  mov     [rbx+18h], rdi
0x1800017ce  cmp     rdi, 10h
0x1800017d2  cmovnb  rbx, rsi
0x1800017d6  mov     [rax], r14
0x1800017d9  mov     byte ptr [rbx+r14], 0
0x1800017de  add     rsp, 38h
0x1800017e2  pop     r14
0x1800017e4  pop     rdi
0x1800017e5  pop     rsi
0x1800017e6  pop     rbx
0x1800017e7  retn
0x1800017e8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
