# AssetElementNode::_GetInternalKnownFolder(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180027a00`
- end: `0x180027d63`
- name: `?_GetInternalKnownFolder@AssetElementNode@@AEAA_NPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV23@@Z`
- size: `867`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800272e4`

## callees

- `0x1800090e0`
- `0x18000918c`
- `0x180009fac`
- `0x1800123ac`
- `0x1800124ac`
- `0x1800125f4`
- `0x180027a00`
- `0x180033bfc`
- `0x180035852`
- `0x1800358a0`

## import_xrefs

- `msvcrt!towupper` at `0x180027bfb`
- `msvcrt!towupper` at `0x180027c0d`
- `msvcrt!towupper` at `0x180027bfb`
- `msvcrt!towupper` at `0x180027c0d`
- `msvcrt!_wcsicmp` at `0x180027a40`
- `msvcrt!_wcsicmp` at `0x180027a40`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027acf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027b3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027d03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027d1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027acf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027b3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027d03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027d1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027aaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027aaf`

## string_xrefs

- `0x180027a36`: `Temporary Runtime Package Command Files`
- `0x180027b48`: `\Commands`
- `0x180027c7a`: `/Command/`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall AssetElementNode::_GetInternalKnownFolder(__int64 a1, const wchar_t *a2, _QWORD *a3, __int64 a4)
{
  int PackageTempDirInternal; // eax
  HLOCAL v8; // rbx
  __int64 v9; // r8
  unsigned __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  void **v13; // rcx
  wint_t *v14; // r8
  void **v15; // rdx
  bool v16; // cf
  _QWORD *v17; // rcx
  wint_t *v18; // rax
  wint_t *v19; // r15
  __int64 v20; // r12
  __int64 v21; // r13
  wint_t *v22; // rcx
  wint_t *i; // rax
  wint_t v24; // bx
  wint_t v25; // di
  wint_t v26; // ax
  _QWORD *v27; // rcx
  char *v28; // rax
  HLOCAL hMem; // [rsp+20h] [rbp-79h] BYREF
  wint_t *v31; // [rsp+28h] [rbp-71h]
  wint_t *v32; // [rsp+30h] [rbp-69h]
  void **v33; // [rsp+38h] [rbp-61h]
  wint_t *v34; // [rsp+40h] [rbp-59h]
  void *Src[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v36; // [rsp+58h] [rbp-41h]
  unsigned __int64 v37; // [rsp+60h] [rbp-39h]
  void *v38[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v39; // [rsp+78h] [rbp-21h]
  unsigned __int64 v40; // [rsp+80h] [rbp-19h]
  void *v41[3]; // [rsp+88h] [rbp-11h] BYREF
  unsigned __int64 v42; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( _wcsicmp(a2, L"Temporary Runtime Package Command Files") )
    return 0;
  hMem = 0;
  PackageTempDirInternal = GetPackageTempDirInternal((const WCHAR *)(a1 + 72), &hMem);
  if ( PackageTempDirInternal < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)PackageTempDirInternal,
      (int)hMem);
  v8 = hMem;
  v37 = 7;
  v36 = 0;
  LOWORD(Src[0]) = 0;
  if ( *(_WORD *)hMem )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)hMem + v9) );
  }
  std::wstring::assign(Src, hMem);
  LocalFree(v8);
  if ( (void **)a4 == Src )
  {
    v12 = v37;
  }
  else
  {
    if ( *(_QWORD *)(a4 + 24) >= 8u )
      operator delete(*(void **)a4);
    *(_WORD *)a4 = 0;
    v10 = v37;
    v11 = v36;
    if ( v37 >= 8 )
    {
      *(void **)a4 = Src[0];
      Src[0] = 0;
    }
    else if ( v36 != -1 )
    {
      memcpy_0((void *)a4, Src, 2 * (v36 + 1));
    }
    *(_QWORD *)(a4 + 16) = v11;
    *(_QWORD *)(a4 + 24) = v10;
    v12 = 7;
    v37 = 7;
    v36 = 0;
    LOWORD(Src[0]) = 0;
  }
  if ( v12 >= 8 )
    operator delete(Src[0]);
  std::wstring::append((void *)a4, L"\\Commands");
  v40 = 7;
  v39 = 0;
  LOWORD(v38[0]) = 0;
  std::wstring::assign(v38, L"PrimaryContext");
  v13 = v38;
  if ( v40 >= 8 )
    v13 = (void **)v38[0];
  v14 = (wint_t *)v13 + v39;
  v32 = v14;
  v15 = v38;
  if ( v40 >= 8 )
    v15 = (void **)v38[0];
  v33 = v15;
  v16 = a3[3] < 8u;
  if ( a3[3] < 8u )
    v17 = a3;
  else
    v17 = (_QWORD *)*a3;
  v18 = (wint_t *)v17 + a3[2];
  v34 = v18;
  if ( v16 )
    v19 = (wint_t *)a3;
  else
    v19 = (wint_t *)*a3;
  v20 = v18 - v19;
  v21 = ((char *)v14 - (char *)v15) >> 1;
  if ( v21 > v20 )
  {
LABEL_34:
    v19 = v18;
  }
  else
  {
LABEL_28:
    v22 = v19;
    for ( i = (wint_t *)v15; ; i = v31 + 1 )
    {
      v31 = i;
      hMem = v22;
      if ( i == v14 )
        break;
      v24 = *v22;
      v25 = towupper(*i);
      v26 = towupper(v24);
      v14 = v32;
      if ( v26 != v25 )
      {
        ++v19;
        --v20;
        v15 = v33;
        if ( v21 <= v20 )
          goto LABEL_28;
        v18 = v34;
        goto LABEL_34;
      }
      v22 = (wint_t *)((char *)hMem + 2);
    }
  }
  if ( a3[3] < 8u )
    v27 = a3;
  else
    v27 = (_QWORD *)*a3;
  if ( v19 != (wint_t *)((char *)v27 + 2 * a3[2]) )
  {
    std::wstring::append((void *)a4, L"\\");
    std::wstring::append(v38, L"/Command/");
    v28 = a3[3] < 8u ? (char *)a3 : (char *)*a3;
    std::wstring::find(a3, 47, (((char *)v19 - v28) >> 1) + v39);
    v42 = 7;
    v41[2] = 0;
    LOWORD(v41[0]) = 0;
    std::wstring::assign(v41);
    std::wstring::append(a4, v41, 0, -1);
    if ( v42 >= 8 )
      operator delete(v41[0]);
  }
  if ( v40 >= 8 )
    operator delete(v38[0]);
  return 1;
}

```

## disassembly

```asm
0x180027a00  push    rbp
0x180027a02  push    rbx
0x180027a03  push    rsi
0x180027a04  push    rdi
0x180027a05  push    r12
0x180027a07  push    r13
0x180027a09  push    r14
0x180027a0b  push    r15
0x180027a0d  lea     rbp, [rsp-1Fh]
0x180027a12  sub     rsp, 0B8h
0x180027a19  mov     rax, cs:__security_cookie
0x180027a20  xor     rax, rsp
0x180027a23  mov     [rbp+57h+var_48], rax
0x180027a27  mov     r14, r9
0x180027a2a  mov     rsi, r8
0x180027a2d  mov     rax, rdx
0x180027a30  mov     rbx, rcx
0x180027a33  xor     r15d, r15d
0x180027a36  lea     rdx, aTemporaryRunti; "Temporary Runtime Package Command Files"
0x180027a3d  mov     rcx, rax; String1
0x180027a40  call    cs:__imp__wcsicmp
0x180027a47  nop     dword ptr [rax+rax+00h]
0x180027a4c  test    eax, eax
0x180027a4e  jnz     loc_180027D2B
0x180027a54  mov     [rbp+57h+hMem], r15
0x180027a58  lea     rcx, [rbx+48h]; pszMore
0x180027a5c  lea     rdx, [rbp+57h+hMem]
0x180027a60  call    ?GetPackageTempDirInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetPackageTempDirInternal(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180027a65  mov     rcx, [rbp+5Fh]; this
0x180027a69  test    eax, eax
0x180027a6b  js      loc_180027D4E
0x180027a71  mov     rbx, [rbp+57h+hMem]
0x180027a75  mov     [rbp+57h+var_90], 7
0x180027a7d  mov     [rbp+57h+var_98], r15
0x180027a81  mov     word ptr [rbp+57h+Src], r15w
0x180027a86  cmp     [rbx], r15w
0x180027a8a  jnz     short loc_180027A91
0x180027a8c  mov     r8d, r15d
0x180027a8f  jmp     short loc_180027A9F
0x180027a91  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027a95  inc     r8
0x180027a98  cmp     [rbx+r8*2], r15w
0x180027a9d  jnz     short loc_180027A95
0x180027a9f  mov     rdx, rbx; Src
0x180027aa2  lea     rcx, [rbp+57h+Src]; void *
0x180027aa6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027aab  nop
0x180027aac  mov     rcx, rbx; hMem
0x180027aaf  call    cs:__imp_LocalFree
0x180027ab6  nop     dword ptr [rax+rax+00h]
0x180027abb  nop
0x180027abc  lea     rax, [rbp+57h+Src]
0x180027ac0  cmp     r14, rax
0x180027ac3  jz      short loc_180027B2E
0x180027ac5  cmp     qword ptr [r14+18h], 8
0x180027aca  jb      short loc_180027ADB
0x180027acc  mov     rcx, [r14]
0x180027acf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027ad6  nop     dword ptr [rax+rax+00h]
0x180027adb  mov     [r14], r15w
0x180027adf  mov     rdi, [rbp+57h+var_90]
0x180027ae3  mov     rbx, [rbp+57h+var_98]
0x180027ae7  cmp     rdi, 8
0x180027aeb  jnb     short loc_180027B07
0x180027aed  lea     r8, [rbx+1]
0x180027af1  test    r8, r8
0x180027af4  jz      short loc_180027B12
0x180027af6  add     r8, r8; Size
0x180027af9  lea     rdx, [rbp+57h+Src]; Src
0x180027afd  mov     rcx, r14; void *
0x180027b00  call    memcpy_0
0x180027b05  jmp     short loc_180027B12
0x180027b07  mov     rax, [rbp+57h+Src]
0x180027b0b  mov     [r14], rax
0x180027b0e  mov     [rbp+57h+Src], r15
0x180027b12  mov     [r14+10h], rbx
0x180027b16  mov     [r14+18h], rdi
0x180027b1a  mov     ecx, 7
0x180027b1f  mov     [rbp+57h+var_90], rcx
0x180027b23  mov     [rbp+57h+var_98], r15
0x180027b27  mov     word ptr [rbp+57h+Src], r15w
0x180027b2c  jmp     short loc_180027B32
0x180027b2e  mov     rcx, [rbp+57h+var_90]
0x180027b32  cmp     rcx, 8
0x180027b36  jb      short loc_180027B48
0x180027b38  mov     rcx, [rbp+57h+Src]
0x180027b3c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027b43  nop     dword ptr [rax+rax+00h]
0x180027b48  lea     rdx, aCommands; "\\Commands"
0x180027b4f  mov     rcx, r14; Src
0x180027b52  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180027b57  mov     [rbp+57h+var_70], 7
0x180027b5f  mov     [rbp+57h+var_78], r15
0x180027b63  mov     word ptr [rbp+57h+var_88], r15w
0x180027b68  mov     r8d, 0Eh
0x180027b6e  lea     rdx, aPrimarycontext; "PrimaryContext"
0x180027b75  lea     rcx, [rbp+57h+var_88]; void *
0x180027b79  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027b7e  nop
0x180027b7f  lea     rcx, [rbp+57h+var_88]
0x180027b83  cmp     [rbp+57h+var_70], 8
0x180027b88  cmovnb  rcx, [rbp+57h+var_88]
0x180027b8d  mov     rax, [rbp+57h+var_78]
0x180027b91  lea     r8, [rcx+rax*2]
0x180027b95  mov     [rbp+57h+var_C0], r8
0x180027b99  lea     rdx, [rbp+57h+var_88]
0x180027b9d  cmovnb  rdx, [rbp+57h+var_88]
0x180027ba2  mov     [rbp+57h+var_B8], rdx
0x180027ba6  cmp     qword ptr [rsi+18h], 8
0x180027bab  jb      short loc_180027BB2
0x180027bad  mov     rcx, [rsi]
0x180027bb0  jmp     short loc_180027BB5
0x180027bb2  mov     rcx, rsi
0x180027bb5  mov     rax, [rsi+10h]
0x180027bb9  lea     rax, [rcx+rax*2]
0x180027bbd  mov     [rbp+57h+var_B0], rax
0x180027bc1  jb      short loc_180027BC8
0x180027bc3  mov     r15, [rsi]
0x180027bc6  jmp     short loc_180027BCB
0x180027bc8  mov     r15, rsi
0x180027bcb  mov     r12, rax
0x180027bce  sub     r12, r15
0x180027bd1  sar     r12, 1
0x180027bd4  mov     r13, r8
0x180027bd7  sub     r13, rdx
0x180027bda  sar     r13, 1
0x180027bdd  cmp     r13, r12
0x180027be0  jg      short loc_180027C48
0x180027be2  mov     rcx, r15
0x180027be5  mov     rax, rdx
0x180027be8  mov     [rbp+57h+var_C8], rax
0x180027bec  mov     [rbp+57h+hMem], rcx
0x180027bf0  cmp     rax, r8
0x180027bf3  jz      short loc_180027C4B
0x180027bf5  movzx   ebx, word ptr [rcx]
0x180027bf8  movzx   ecx, word ptr [rax]; C
0x180027bfb  call    cs:__imp_towupper
0x180027c02  nop     dword ptr [rax+rax+00h]
0x180027c07  movzx   edi, ax
0x180027c0a  movzx   ecx, bx; C
0x180027c0d  call    cs:__imp_towupper
0x180027c14  nop     dword ptr [rax+rax+00h]
0x180027c19  mov     r8, [rbp+57h+var_C0]
0x180027c1d  cmp     ax, di
0x180027c20  jnz     short loc_180027C34
0x180027c22  mov     rcx, [rbp+57h+hMem]
0x180027c26  add     rcx, 2
0x180027c2a  mov     rax, [rbp+57h+var_C8]
0x180027c2e  add     rax, 2
0x180027c32  jmp     short loc_180027BE8
0x180027c34  add     r15, 2
0x180027c38  dec     r12
0x180027c3b  cmp     r13, r12
0x180027c3e  mov     rdx, [rbp+57h+var_B8]
0x180027c42  jle     short loc_180027BE2
0x180027c44  mov     rax, [rbp+57h+var_B0]
0x180027c48  mov     r15, rax
0x180027c4b  cmp     qword ptr [rsi+18h], 8
0x180027c50  jb      short loc_180027C57
0x180027c52  mov     rcx, [rsi]
0x180027c55  jmp     short loc_180027C5A
0x180027c57  mov     rcx, rsi
0x180027c5a  mov     rax, [rsi+10h]
0x180027c5e  lea     rcx, [rcx+rax*2]
0x180027c62  cmp     r15, rcx
0x180027c65  jz      loc_180027D10
0x180027c6b  lea     rdx, asc_18003C970; "\\"
0x180027c72  mov     rcx, r14; Src
0x180027c75  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180027c7a  lea     rdx, aCommand; "/Command/"
0x180027c81  lea     rcx, [rbp+57h+var_88]; Src
0x180027c85  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180027c8a  cmp     qword ptr [rsi+18h], 8
0x180027c8f  jb      short loc_180027C96
0x180027c91  mov     rax, [rsi]
0x180027c94  jmp     short loc_180027C99
0x180027c96  mov     rax, rsi
0x180027c99  sub     r15, rax
0x180027c9c  sar     r15, 1
0x180027c9f  mov     rbx, [rbp+57h+var_78]
0x180027ca3  add     rbx, r15
0x180027ca6  mov     edx, 2Fh ; '/'
0x180027cab  mov     r8, rbx
0x180027cae  mov     rcx, rsi
0x180027cb1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x180027cb6  mov     [rbp+57h+var_50], 7
0x180027cbe  mov     [rbp+57h+var_58], 0
0x180027cc6  xor     r10d, r10d
0x180027cc9  mov     word ptr [rbp+57h+var_68], r10w
0x180027cce  sub     rax, rbx
0x180027cd1  mov     r9, rax
0x180027cd4  mov     r8, rbx
0x180027cd7  mov     rdx, rsi
0x180027cda  lea     rcx, [rbp+57h+var_68]; void *
0x180027cde  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180027ce3  nop
0x180027ce4  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027ce8  xor     r8d, r8d
0x180027ceb  lea     rdx, [rbp+57h+var_68]
0x180027cef  mov     rcx, r14
0x180027cf2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180027cf7  nop
0x180027cf8  cmp     [rbp+57h+var_50], 8
0x180027cfd  jb      short loc_180027D10
0x180027cff  mov     rcx, [rbp+57h+var_68]
0x180027d03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027d0a  nop     dword ptr [rax+rax+00h]
0x180027d0f  nop
0x180027d10  cmp     [rbp+57h+var_70], 8
0x180027d15  jb      short loc_180027D27
0x180027d17  mov     rcx, [rbp+57h+var_88]
0x180027d1b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027d22  nop     dword ptr [rax+rax+00h]
0x180027d27  mov     al, 1
0x180027d29  jmp     short loc_180027D2D
0x180027d2b  xor     al, al
0x180027d2d  mov     rcx, [rbp+57h+var_48]
0x180027d31  xor     rcx, rsp; StackCookie
0x180027d34  call    __security_check_cookie
0x180027d39  add     rsp, 0B8h
0x180027d40  pop     r15
0x180027d42  pop     r14
0x180027d44  pop     r13
0x180027d46  pop     r12
0x180027d48  pop     rdi
0x180027d49  pop     rsi
0x180027d4a  pop     rbx
0x180027d4b  pop     rbp
0x180027d4c  retn
0x180027d4e  mov     r9d, eax; char *
0x180027d51  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180027d58  mov     edx, 29h ; ')'; void *
0x180027d5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
