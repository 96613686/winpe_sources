# PStringHash(wchar_t const *,ulong)

- ea: `0x18000f42c`
- end: `0x18000f4d0`
- name: `?PStringHash@@YAKPEB_WK@Z`
- size: `164`
- prototype: `unsigned int __fastcall(const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f34c`
- `0x18000f3a0`
- `0x18001f1a4`

## callees

- `0x180005c00`
- `0x18000f42c`
- `0x18000fcd0`
- `0x180011135`
- `0x18001efe0`
- `0x180024dc0`

## string_xrefs

- `0x18000f49c`: `[UtilCommon] Integer overflow occurred while computing the size of buffer to be allocated.`
- `0x18000f4a8`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\namestr.cxx"`

## pseudocode

```c
unsigned int __fastcall PStringHash(const wchar_t *a1, unsigned int a2, __int64 a3, const wchar_t *a4)
{
  unsigned __int64 v5; // rax
  size_t v6; // r8
  unsigned __int64 v7; // rax
  void *v8; // rsp
  WCHAR SrcStr[8]; // [rsp+20h] [rbp+0h] BYREF

  v5 = 2LL * a2;
  if ( v5 > 0xFFFFFFFF )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\namestr.cxx\"",
      (const wchar_t *)0x4B,
      (__int64)L"[UtilCommon] Integer overflow occurred while computing the size of buffer to be allocated.",
      a4);
    return 0;
  }
  else
  {
    v6 = (unsigned int)v5;
    v7 = (unsigned int)v5 + 15LL;
    if ( v7 <= v6 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
    memcpy_0(SrcStr, a1, v6);
    return InternalStringHash(SrcStr, a2);
  }
}

```

## disassembly

```asm
0x18000f42c  push    rbp
0x18000f42e  sub     rsp, 30h
0x18000f432  lea     rbp, [rsp+20h]
0x18000f437  mov     [rbp+10h+arg_0], rbx
0x18000f43b  mov     [rbp+10h+arg_8], rdi
0x18000f43f  mov     rax, cs:__security_cookie
0x18000f446  xor     rax, rbp
0x18000f449  mov     qword ptr [rbp+10h+SrcStr], rax
0x18000f44d  mov     eax, edx
0x18000f44f  mov     edi, edx
0x18000f451  add     rax, rax
0x18000f454  mov     edx, 0FFFFFFFFh
0x18000f459  cmp     rax, rdx
0x18000f45c  ja      short loc_18000F49C
0x18000f45e  mov     r8d, eax
0x18000f461  lea     rax, [r8+0Fh]
0x18000f465  cmp     rax, r8
0x18000f468  ja      short loc_18000F474
0x18000f46a  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000f474  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000f478  call    _alloca_probe
0x18000f47d  sub     rsp, rax
0x18000f480  mov     rdx, rcx; Src
0x18000f483  lea     rbx, [rsp+30h+SrcStr]
0x18000f488  mov     rcx, rbx; void *
0x18000f48b  call    memcpy_0
0x18000f490  mov     edx, edi; cchSrc
0x18000f492  mov     rcx, rbx; lpSrcStr
0x18000f495  call    InternalStringHash
0x18000f49a  jmp     short loc_18000F4B6
0x18000f49c  lea     r8, aUtilcommonInte_0; "[UtilCommon] Integer overflow occurred "...
0x18000f4a3  mov     edx, 4Bh ; 'K'; wchar_t *
0x18000f4a8  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f4af  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000f4b4  xor     eax, eax
0x18000f4b6  mov     rcx, qword ptr [rbp+10h+SrcStr]
0x18000f4ba  xor     rcx, rbp; StackCookie
0x18000f4bd  call    __security_check_cookie
0x18000f4c2  mov     rbx, [rbp+10h+arg_0]
0x18000f4c6  mov     rdi, [rbp+10h+arg_8]
0x18000f4ca  lea     rsp, [rbp+10h]
0x18000f4ce  pop     rbp
0x18000f4cf  retn
```
