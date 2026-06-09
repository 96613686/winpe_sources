# CDpUrlAccessor::Init(ushort const *,ushort const *)

- ea: `0x180006dc0`
- end: `0x1800070bc`
- name: `?Init@CDpUrlAccessor@@QEAAJPEBG0@Z`
- size: `764`
- prototype: `__int64 __fastcall(CDpUrlAccessor *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004020`

## callees

- `0x180006600`
- `0x1800067b4`
- `0x180006dc0`
- `0x180007178`
- `0x18000739c`
- `0x18000743c`
- `0x18000ab60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006e7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006eb1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000702f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007058`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007084`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006e7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006eb1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000702f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007058`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007084`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::Init(CDpUrlAccessor *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v6; // r8
  __int64 v7; // r8
  void *v8; // rax
  __int64 v9; // r8
  void **v10; // rax
  void **v11; // rcx
  unsigned __int64 v12; // r8
  __int64 v13; // r9
  void **v14; // rax
  void **v15; // rbx
  void **v16; // rdx
  void **v17; // rax
  _QWORD *v18; // rbx
  _QWORD *v19; // rdi
  __int64 result; // rax
  void *v21[2]; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-E8h]
  unsigned __int64 v23; // [rsp+48h] [rbp-E0h]
  void *v24; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-C0h]
  unsigned __int64 v26; // [rsp+70h] [rbp-B8h]
  void *v27; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+90h] [rbp-98h]
  unsigned __int64 v29; // [rsp+98h] [rbp-90h]
  void *Src[3]; // [rsp+A8h] [rbp-80h] BYREF
  unsigned __int64 v31; // [rsp+C0h] [rbp-68h]
  void *v32[3]; // [rsp+D0h] [rbp-58h] BYREF
  unsigned __int64 v33; // [rsp+E8h] [rbp-40h]

  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  try
  {
    std::wstring::assign((char *)this + 64, a2);
    v31 = 7;
    Src[2] = 0;
    LOWORD(Src[0]) = 0;
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    std::wstring::assign(Src, a2);
    v8 = (void *)UrlToFilename(v32);
    std::wstring::assign((char *)this + 104, v8);
    if ( v33 >= 8 )
      operator delete(v32[0]);
    v33 = 7;
    v32[2] = 0;
    LOWORD(v32[0]) = 0;
    if ( v31 >= 8 )
      operator delete(Src[0]);
    v23 = 7;
    v22 = 0;
    LOWORD(v21[0]) = 0;
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    std::wstring::assign(v21, a3);
    v10 = v21;
    v11 = (void **)v21[0];
    v12 = v23;
    if ( v23 >= 8 )
      v10 = (void **)v21[0];
    v13 = v22;
    v14 = (void **)((char *)v10 + 2 * v22);
    v15 = v21;
    if ( v23 >= 8 )
      v15 = (void **)v21[0];
    while ( v15 != v14 && *(_WORD *)v15 != 124 )
      v15 = (void **)((char *)v15 + 2);
    v16 = v21;
    if ( v23 >= 8 )
      v16 = (void **)v21[0];
    v29 = 7;
    v28 = 0;
    LOWORD(v27) = 0;
    if ( v16 != v15 )
    {
      std::wstring::assign(&v27, v16);
      v12 = v23;
      v13 = v22;
      v11 = (void **)v21[0];
    }
    v17 = v21;
    if ( v12 >= 8 )
      v17 = v11;
    v26 = 7;
    v25 = 0;
    LOWORD(v24) = 0;
    if ( (char *)v15 + 2 != (char *)v17 + 2 * v13 )
      std::wstring::assign(&v24, (char *)v15 + 2);
    v18 = (_QWORD *)((char *)this + 144);
    std::wstring::assign((char *)this + 144);
    v19 = (_QWORD *)((char *)this + 184);
    std::wstring::assign(v19);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      if ( v19[3] >= 8u )
        v19 = (_QWORD *)*v19;
      if ( v18[3] >= 8u )
        v18 = (_QWORD *)*v18;
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v18, (__int64)v19);
    }
    if ( v26 >= 8 )
      operator delete(v24);
    v26 = 7;
    v25 = 0;
    LOWORD(v24) = 0;
    if ( v29 >= 8 )
      operator delete(v27);
    v29 = 7;
    v28 = 0;
    LOWORD(v27) = 0;
    if ( v23 >= 8 )
      operator delete(v21[0]);
    result = 0;
  }
  catch ( exception )
  {
    return 2147500037LL;
  }
  std::wstring::assign((char *)this + 64, a2);
}

```

## disassembly

```asm
0x180006dc0  mov     [rsp+arg_18], rbx
0x180006dc5  push    rsi
0x180006dc6  push    rdi
0x180006dc7  push    r12
0x180006dc9  push    r13
0x180006dcb  push    r14
0x180006dcd  sub     rsp, 100h
0x180006dd4  mov     rax, cs:__security_cookie
0x180006ddb  xor     rax, rsp
0x180006dde  mov     [rsp+128h+var_30], rax
0x180006de6  mov     rbx, r8
0x180006de9  mov     rsi, rdx
0x180006dec  mov     rdi, rcx
0x180006def  or      r13, 0FFFFFFFFFFFFFFFFh
0x180006df3  mov     r8, r13
0x180006df6  xor     r14d, r14d
0x180006df9  inc     r8
0x180006dfc  cmp     [rdx+r8*2], r14w
0x180006e01  jnz     short loc_180006DF9
0x180006e03  add     rcx, 40h ; '@'; Src
0x180006e07  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180006e0c  mov     r12d, 7
0x180006e12  mov     [rsp+128h+var_68], r12
0x180006e1a  mov     [rsp+128h+var_70], r14
0x180006e22  mov     word ptr [rsp+128h+Src], r14w
0x180006e2b  mov     r8, r13
0x180006e2e  inc     r8
0x180006e31  cmp     [rsi+r8*2], r14w
0x180006e36  jnz     short loc_180006E2E
0x180006e38  mov     rdx, rsi; void *
0x180006e3b  lea     rcx, [rsp+128h+Src]; Src
0x180006e43  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180006e48  nop
0x180006e49  lea     rdx, [rsp+128h+Src]
0x180006e51  lea     rcx, [rsp+128h+var_58]; void *
0x180006e59  call    ?UrlToFilename@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; UrlToFilename(std::wstring const &)
0x180006e5e  nop
0x180006e5f  lea     rcx, [rdi+68h]; void *
0x180006e63  mov     rdx, rax; Src
0x180006e66  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x180006e6b  nop
0x180006e6c  cmp     [rsp+128h+var_40], 8
0x180006e75  jb      short loc_180006E85
0x180006e77  mov     rcx, [rsp+128h+var_58]
0x180006e7f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006e85  mov     [rsp+128h+var_40], r12
0x180006e8d  mov     [rsp+128h+var_48], r14
0x180006e95  mov     word ptr [rsp+128h+var_58], r14w
0x180006e9e  cmp     [rsp+128h+var_68], 8
0x180006ea7  jb      short loc_180006EB7
0x180006ea9  mov     rcx, [rsp+128h+Src]
0x180006eb1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006eb7  mov     [rsp+128h+var_E0], r12
0x180006ebc  mov     [rsp+128h+var_E8], r14
0x180006ec1  mov     word ptr [rsp+128h+var_F8], r14w
0x180006ec7  mov     r8, r13
0x180006eca  inc     r8
0x180006ecd  cmp     [rbx+r8*2], r14w
0x180006ed2  jnz     short loc_180006ECA
0x180006ed4  mov     rdx, rbx; void *
0x180006ed7  lea     rcx, [rsp+128h+var_F8]; Src
0x180006edc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180006ee1  nop
0x180006ee2  lea     rax, [rsp+128h+var_F8]
0x180006ee7  mov     rcx, [rsp+128h+var_F8]
0x180006eec  mov     r8, [rsp+128h+var_E0]
0x180006ef1  cmp     r8, 8
0x180006ef5  cmovnb  rax, rcx
0x180006ef9  mov     r9, [rsp+128h+var_E8]
0x180006efe  lea     rax, [rax+r9*2]
0x180006f02  lea     rbx, [rsp+128h+var_F8]
0x180006f07  cmovnb  rbx, rcx
0x180006f0b  jmp     short loc_180006F17
0x180006f0d  cmp     word ptr [rbx], 7Ch ; '|'
0x180006f11  jz      short loc_180006F1C
0x180006f13  add     rbx, 2
0x180006f17  cmp     rbx, rax
0x180006f1a  jnz     short loc_180006F0D
0x180006f1c  lea     rdx, [rsp+128h+var_F8]
0x180006f21  cmp     r8, 8
0x180006f25  cmovnb  rdx, rcx; void *
0x180006f29  mov     [rsp+128h+var_90], r12
0x180006f31  mov     [rsp+128h+var_98], r14
0x180006f39  mov     word ptr [rsp+128h+var_A8], r14w
0x180006f42  cmp     rdx, rbx
0x180006f45  jz      short loc_180006F6C
0x180006f47  mov     r8, rbx
0x180006f4a  sub     r8, rdx
0x180006f4d  sar     r8, 1
0x180006f50  lea     rcx, [rsp+128h+var_A8]; Src
0x180006f58  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180006f5d  mov     r8, [rsp+128h+var_E0]
0x180006f62  mov     r9, [rsp+128h+var_E8]
0x180006f67  mov     rcx, [rsp+128h+var_F8]
0x180006f6c  lea     rax, [rsp+128h+var_F8]
0x180006f71  cmp     r8, 8
0x180006f75  cmovnb  rax, rcx
0x180006f79  lea     r8, [rax+r9*2]
0x180006f7d  lea     rdx, [rbx+2]; void *
0x180006f81  mov     [rsp+128h+var_B8], r12
0x180006f86  mov     [rsp+128h+var_C0], r14
0x180006f8b  mov     word ptr [rsp+128h+var_D0], r14w
0x180006f91  cmp     rdx, r8
0x180006f94  jz      short loc_180006FA7
0x180006f96  sub     r8, rdx
0x180006f99  sar     r8, 1
0x180006f9c  lea     rcx, [rsp+128h+var_D0]; Src
0x180006fa1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180006fa6  nop
0x180006fa7  lea     rbx, [rdi+90h]
0x180006fae  mov     r9, r13
0x180006fb1  xor     r8d, r8d
0x180006fb4  lea     rdx, [rsp+128h+var_A8]
0x180006fbc  mov     rcx, rbx; Src
0x180006fbf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006fc4  add     rdi, 0B8h
0x180006fcb  mov     r9, r13
0x180006fce  xor     r8d, r8d
0x180006fd1  lea     rdx, [rsp+128h+var_D0]
0x180006fd6  mov     rcx, rdi; Src
0x180006fd9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006fde  lea     rax, WPP_GLOBAL_Control
0x180006fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fec  cmp     rcx, rax
0x180006fef  jz      short loc_180007022
0x180006ff1  test    byte ptr [rcx+1Ch], 8
0x180006ff5  jz      short loc_180007022
0x180006ff7  cmp     qword ptr [rdi+18h], 8
0x180006ffc  jb      short loc_180007001
0x180006ffe  mov     rdi, [rdi]
0x180007001  cmp     qword ptr [rbx+18h], 8
0x180007006  jb      short loc_18000700B
0x180007008  mov     rbx, [rbx]
0x18000700b  mov     [rsp+128h+var_100], rdi; __int64
0x180007010  mov     [rsp+128h+var_108], rbx; __int64
0x180007015  mov     r9, rsi
0x180007018  mov     rcx, [rcx+10h]; LoggerHandle
0x18000701c  call    WPP_SF_SSS
0x180007021  nop
0x180007022  cmp     [rsp+128h+var_B8], 8
0x180007028  jb      short loc_180007035
0x18000702a  mov     rcx, [rsp+128h+var_D0]
0x18000702f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007035  mov     [rsp+128h+var_B8], r12
0x18000703a  mov     [rsp+128h+var_C0], r14
0x18000703f  mov     word ptr [rsp+128h+var_D0], r14w
0x180007045  cmp     [rsp+128h+var_90], 8
0x18000704e  jb      short loc_18000705E
0x180007050  mov     rcx, [rsp+128h+var_A8]
0x180007058  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000705e  mov     [rsp+128h+var_90], r12
0x180007066  mov     [rsp+128h+var_98], r14
0x18000706e  mov     word ptr [rsp+128h+var_A8], r14w
0x180007077  cmp     [rsp+128h+var_E0], 8
0x18000707d  jb      short loc_18000708B
0x18000707f  mov     rcx, [rsp+128h+var_F8]
0x180007084  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000708a  nop
0x18000708b  xor     eax, eax
0x18000708d  jmp     short loc_180007094
0x18000708f  mov     eax, 80004005h
0x180007094  mov     rcx, [rsp+128h+var_30]
0x18000709c  xor     rcx, rsp; StackCookie
0x18000709f  call    __security_check_cookie
0x1800070a4  mov     rbx, [rsp+128h+arg_18]
0x1800070ac  add     rsp, 100h
0x1800070b3  pop     r14
0x1800070b5  pop     r13
0x1800070b7  pop     r12
0x1800070b9  pop     rdi
0x1800070ba  pop     rsi
0x1800070bb  retn
```
