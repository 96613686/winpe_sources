# AssetElementNode::_GetFullDestination(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800277c4`
- end: `0x1800279f7`
- name: `?_GetFullDestination@AssetElementNode@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026840`

## callees

- `0x1800090e0`
- `0x180009fac`
- `0x1800277c4`
- `0x1800358a0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800278d5`
- `msvcrt!_wcsnicmp` at `0x1800278ef`
- `msvcrt!_wcsnicmp` at `0x18002791e`
- `msvcrt!_wcsnicmp` at `0x1800278d5`
- `msvcrt!_wcsnicmp` at `0x1800278ef`
- `msvcrt!_wcsnicmp` at `0x18002791e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002784a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002784a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002785b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027971`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002785b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027971`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027987`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180027829`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180027829`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180027886`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180027886`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall AssetElementNode::_GetFullDestination(__int64 a1, _QWORD *a2, __int64 a3)
{
  const WCHAR *v3; // rax
  const WCHAR *v6; // rdi
  const WCHAR *v7; // rcx
  HRESULT v8; // eax
  HRESULT v9; // eax
  const wchar_t *v10; // rbx
  const wchar_t *v11; // rcx
  _WORD *v12; // rdx
  __int64 v13; // r8
  HLOCAL hMem; // [rsp+20h] [rbp-30h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-28h] BYREF
  wchar_t String1[8]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v3 = (const WCHAR *)a3;
  hMem = 0;
  ppszPathOut = 0;
  if ( *(_QWORD *)(a3 + 24) >= 8u )
    v3 = *(const WCHAR **)a3;
  v6 = (const WCHAR *)(a1 + 136);
  if ( *(_QWORD *)(a1 + 160) < 8u )
    v7 = (const WCHAR *)(a1 + 136);
  else
    v7 = *(const WCHAR **)v6;
  v8 = PathAllocCombine(v7, v3, 1u, &ppszPathOut);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v8,
      (int)hMem);
  hMem = 0;
  v9 = PathAllocCanonicalize(ppszPathOut, 1u, (PWSTR *)&hMem);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v9,
      (int)hMem);
  v10 = (const wchar_t *)hMem;
  wcscpy(String1, L"\\\\?\\");
  if ( *((_QWORD *)v6 + 3) < 8u )
    v11 = v6;
  else
    v11 = *(const wchar_t **)v6;
  if ( _wcsnicmp(v11, (const wchar_t *)hMem, 4u) && !_wcsnicmp(String1, v10, 4u) )
    v10 += 4;
  if ( *((_QWORD *)v6 + 3) >= 8u )
    v6 = *(const WCHAR **)v6;
  if ( _wcsnicmp(v6, v10, *(_QWORD *)(a1 + 152)) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)0x86000011LL,
      (int)hMem);
  v12 = hMem;
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  if ( *v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
  }
  std::wstring::assign(a2, v12);
  if ( hMem )
    LocalFree(hMem);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return a2;
}

```

## disassembly

```asm
0x1800277c4  push    rbp
0x1800277c6  push    rbx
0x1800277c7  push    rsi
0x1800277c8  push    rdi
0x1800277c9  push    r12
0x1800277cb  push    r14
0x1800277cd  push    r15
0x1800277cf  mov     rbp, rsp
0x1800277d2  sub     rsp, 50h
0x1800277d6  mov     rax, cs:__security_cookie
0x1800277dd  xor     rax, rsp
0x1800277e0  mov     [rbp+var_8], rax
0x1800277e4  mov     rax, r8
0x1800277e7  mov     rsi, rdx
0x1800277ea  mov     r15, rcx
0x1800277ed  mov     [rbp+ppszPathOut], rdx
0x1800277f1  xor     r12d, r12d
0x1800277f4  mov     [rbp+hMem], r12
0x1800277f8  mov     [rbp+ppszPathOut], r12
0x1800277fc  cmp     qword ptr [r8+18h], 8
0x180027801  jb      short loc_180027806
0x180027803  mov     rax, [r8]
0x180027806  lea     rdi, [rcx+88h]
0x18002780d  cmp     qword ptr [rdi+18h], 8
0x180027812  jb      short loc_180027819
0x180027814  mov     rcx, [rdi]
0x180027817  jmp     short loc_18002781C
0x180027819  mov     rcx, rdi; pszPathIn
0x18002781c  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180027820  mov     r8d, 1; dwFlags
0x180027826  mov     rdx, rax; pszMore
0x180027829  call    cs:__imp_PathAllocCombine
0x180027830  nop     dword ptr [rax+rax+00h]
0x180027835  mov     rcx, [rbp+38h]; this
0x180027839  test    eax, eax
0x18002783b  js      loc_1800279CD
0x180027841  mov     r14, [rbp+hMem]
0x180027845  test    r14, r14
0x180027848  jz      short loc_180027875
0x18002784a  call    cs:__imp_GetLastError
0x180027851  nop     dword ptr [rax+rax+00h]
0x180027856  mov     ebx, eax
0x180027858  mov     rcx, r14; hMem
0x18002785b  call    cs:__imp_LocalFree
0x180027862  nop     dword ptr [rax+rax+00h]
0x180027867  mov     ecx, ebx; dwErrCode
0x180027869  call    cs:__imp_SetLastError
0x180027870  nop     dword ptr [rax+rax+00h]
0x180027875  mov     [rbp+hMem], r12
0x180027879  lea     r8, [rbp+hMem]; ppszPathOut
0x18002787d  mov     edx, 1; dwFlags
0x180027882  mov     rcx, [rbp+ppszPathOut]; pszPathIn
0x180027886  call    cs:__imp_PathAllocCanonicalize
0x18002788d  nop     dword ptr [rax+rax+00h]
0x180027892  mov     rcx, [rbp+38h]; this
0x180027896  test    eax, eax
0x180027898  js      loc_1800279E2
0x18002789e  mov     rbx, [rbp+hMem]
0x1800278a2  movsd   xmm0, qword ptr cs:asc_18003D610; "\\\\?\\"
0x1800278aa  movsd   qword ptr [rbp+String1], xmm0
0x1800278af  movzx   eax, word ptr cs:asc_18003D610+8; ""
0x1800278b6  mov     [rbp+var_10], ax
0x1800278ba  cmp     qword ptr [rdi+18h], 8
0x1800278bf  jb      short loc_1800278C6
0x1800278c1  mov     rcx, [rdi]
0x1800278c4  jmp     short loc_1800278C9
0x1800278c6  mov     rcx, rdi; String1
0x1800278c9  mov     r14d, 4
0x1800278cf  mov     r8d, r14d; MaxCount
0x1800278d2  mov     rdx, rbx; String2
0x1800278d5  call    cs:__imp__wcsnicmp
0x1800278dc  nop     dword ptr [rax+rax+00h]
0x1800278e1  test    eax, eax
0x1800278e3  jz      short loc_180027903
0x1800278e5  mov     r8d, r14d; MaxCount
0x1800278e8  mov     rdx, rbx; String2
0x1800278eb  lea     rcx, [rbp+String1]; String1
0x1800278ef  call    cs:__imp__wcsnicmp
0x1800278f6  nop     dword ptr [rax+rax+00h]
0x1800278fb  test    eax, eax
0x1800278fd  jnz     short loc_180027903
0x1800278ff  add     rbx, 8
0x180027903  cmp     qword ptr [rdi+18h], 8
0x180027908  jb      short loc_18002790D
0x18002790a  mov     rdi, [rdi]
0x18002790d  mov     r14, [rbp+38h]
0x180027911  mov     r8, [r15+98h]; MaxCount
0x180027918  mov     rdx, rbx; String2
0x18002791b  mov     rcx, rdi; String1
0x18002791e  call    cs:__imp__wcsnicmp
0x180027925  nop     dword ptr [rax+rax+00h]
0x18002792a  test    eax, eax
0x18002792c  jnz     loc_1800279B2
0x180027932  mov     rdx, [rbp+hMem]; Src
0x180027936  mov     qword ptr [rsi+18h], 7
0x18002793e  mov     [rsi+10h], r12
0x180027942  mov     [rsi], r12w
0x180027946  cmp     [rdx], r12w
0x18002794a  jnz     short loc_180027951
0x18002794c  mov     r8, r12
0x18002794f  jmp     short loc_18002795F
0x180027951  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027955  inc     r8
0x180027958  cmp     [rdx+r8*2], r12w
0x18002795d  jnz     short loc_180027955
0x18002795f  mov     rcx, rsi; void *
0x180027962  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027967  nop
0x180027968  mov     rcx, [rbp+hMem]; hMem
0x18002796c  test    rcx, rcx
0x18002796f  jz      short loc_18002797E
0x180027971  call    cs:__imp_LocalFree
0x180027978  nop     dword ptr [rax+rax+00h]
0x18002797d  nop
0x18002797e  mov     rcx, [rbp+ppszPathOut]; hMem
0x180027982  test    rcx, rcx
0x180027985  jz      short loc_180027993
0x180027987  call    cs:__imp_LocalFree
0x18002798e  nop     dword ptr [rax+rax+00h]
0x180027993  mov     rax, rsi
0x180027996  mov     rcx, [rbp+var_8]
0x18002799a  xor     rcx, rsp; StackCookie
0x18002799d  call    __security_check_cookie
0x1800279a2  add     rsp, 50h
0x1800279a6  pop     r15
0x1800279a8  pop     r14
0x1800279aa  pop     r12
0x1800279ac  pop     rdi
0x1800279ad  pop     rsi
0x1800279ae  pop     rbx
0x1800279af  pop     rbp
0x1800279b0  retn
0x1800279b2  mov     r9d, 86000011h; char *
0x1800279b8  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800279bf  mov     edx, 13Fh; void *
0x1800279c4  mov     rcx, r14; this
0x1800279c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800279cd  mov     r9d, eax; char *
0x1800279d0  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800279d7  mov     edx, 13Ah; void *
0x1800279dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800279e2  mov     r9d, eax; char *
0x1800279e5  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800279ec  mov     edx, 13Bh; void *
0x1800279f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
