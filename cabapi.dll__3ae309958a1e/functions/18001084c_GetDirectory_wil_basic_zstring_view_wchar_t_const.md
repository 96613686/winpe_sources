# GetDirectory(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x18001084c`
- end: `0x1800108bd`
- name: `?GetDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010124`

## callees

- `0x180002f70`
- `0x18001084c`
- `0x1800108c4`

## pseudocode

```c
__int64 __fastcall GetDirectory(__int64 a1, __int64 a2)
{
  const wchar_t *FileName; // rcx
  __int64 v5; // rax
  unsigned __int64 v6; // r8
  const wchar_t *v7; // rdx

  FileName = GetFileName(*(const wchar_t *const *)a2);
  v5 = -1;
  do
    ++v5;
  while ( FileName[v5] );
  v6 = *(_QWORD *)(a2 + 8);
  v7 = *(const wchar_t **)a2;
  *(_OWORD *)a1 = 0;
  if ( v6 >= v6 - v5 )
    v6 -= v5;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a1, v7, v6);
  return a1;
}

```

## disassembly

```asm
0x18001084c  mov     [rsp+arg_10], rbx
0x180010851  mov     [rsp+arg_18], rsi
0x180010856  push    rdi
0x180010857  sub     rsp, 30h
0x18001085b  mov     rbx, rcx
0x18001085e  mov     [rsp+38h+var_10], rcx
0x180010863  mov     rcx, [rdx]; FullPath
0x180010866  mov     rdi, rdx
0x180010869  xor     esi, esi
0x18001086b  call    ?GetFileName@@YAPEB_WQEB_W@Z; GetFileName(wchar_t const * const)
0x180010870  mov     rcx, rax
0x180010873  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010877  inc     rax
0x18001087a  cmp     [rcx+rax*2], si
0x18001087e  jnz     short loc_180010877
0x180010880  mov     r8, [rdi+8]
0x180010884  xorps   xmm0, xmm0
0x180010887  mov     rdx, [rdi]
0x18001088a  mov     rcx, r8
0x18001088d  sub     rcx, rax
0x180010890  cmp     r8, rcx
0x180010893  movups  xmmword ptr [rbx], xmm0
0x180010896  cmovnb  r8, rcx
0x18001089a  mov     [rbx+10h], rsi
0x18001089e  mov     rcx, rbx
0x1800108a1  mov     [rbx+18h], rsi
0x1800108a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800108aa  mov     rsi, [rsp+38h+arg_18]
0x1800108af  mov     rax, rbx
0x1800108b2  mov     rbx, [rsp+38h+arg_10]
0x1800108b7  add     rsp, 30h
0x1800108bb  pop     rdi
0x1800108bc  retn
```
