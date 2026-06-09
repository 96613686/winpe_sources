# PayloadEnumerator::CreatePayloadEnumerator(void *,ushort const *)

- ea: `0x180017608`
- end: `0x180017890`
- name: `?CreatePayloadEnumerator@PayloadEnumerator@@QEAAJPEAXPEBG@Z`
- size: `648`
- prototype: `__int64 __fastcall(PayloadEnumerator *this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800157d0`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000f040`
- `0x18000fc8c`
- `0x180017608`

## string_xrefs

- `0x180017875`: `    Failed to assemble search path string`
- `0x180017754`: `    Failed to allocate _spElementPath.get()`
- `0x18001766d`: `PayloadEnumerator::CreatePayloadEnumerator`
- `0x1800176bc`: `PayloadEnumerator::CreatePayloadEnumerator`
- `0x180017741`: `PayloadEnumerator::CreatePayloadEnumerator`
- `0x180017791`: `PayloadEnumerator::CreatePayloadEnumerator`
- `0x180017811`: `PayloadEnumerator::CreatePayloadEnumerator`
- `0x180017862`: `PayloadEnumerator::CreatePayloadEnumerator`
- `0x180017680`: `    Failed to allocate _spCurrentDirectory.get()`
- `0x1800177a4`: `    Failed to assemble element path string`
- `0x180017824`: `    Failed to allocate _spFileSearchPath.get()`

## pseudocode

```c
__int64 __fastcall PayloadEnumerator::CreatePayloadEnumerator(
        PayloadEnumerator *this,
        void *a2,
        const unsigned __int16 *a3)
{
  void *v6; // rax
  const struct std::nothrow_t *v7; // rdx
  void *v8; // rcx
  _WORD *v9; // rcx
  unsigned int v10; // edi
  __int64 v12; // rax
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // kr00_8
  void *v16; // rax
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  unsigned __int16 *v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  size_t v22; // rdi
  unsigned __int64 v23; // rax
  void *v24; // rax
  const struct std::nothrow_t *v25; // rdx
  void *v26; // rcx
  WCHAR *v27; // rcx
  HRESULT v28; // eax
  ULONG v29; // [rsp+20h] [rbp-48h]
  __int64 v30; // [rsp+20h] [rbp-48h]

  v6 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v6;
  if ( v8 )
    operator delete(v8, v7);
  v9 = (_WORD *)*((_QWORD *)this + 4);
  if ( !v9 )
  {
    v10 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::CreatePayloadEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      23,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate _spCurrentDirectory.get()");
    return v10;
  }
  *v9 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::CreatePayloadEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      28,
      -2147024809);
    ProvPackageLog(3, L"    hImage: Argument cannot be NULL");
    return v10;
  }
  *((_QWORD *)this + 1) = a2;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v13 = v12 + 1;
  v15 = v12 + 1;
  v14 = 2 * (v12 + 1);
  if ( !is_mul_ok(v15, 2u) )
    v14 = -1;
  v16 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v18 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v16;
  if ( v18 )
    operator delete(v18, v17);
  v19 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( !v19 )
  {
    v10 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::CreatePayloadEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      34,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate _spElementPath.get()");
    return v10;
  }
  v20 = PathCchCanonicalizeEx(v19, v13, a3, PATHCCH_ALLOW_LONG_PATHS);
  v10 = v20;
  if ( v20 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::CreatePayloadEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      37,
      v20);
    ProvPackageLog(3, L"    Failed to assemble element path string");
    return v10;
  }
  v21 = -1;
  do
    ++v21;
  while ( a3[v21] );
  v22 = v21 + 3;
  v23 = 2 * (v21 + 3);
  if ( !is_mul_ok(v21 + 3, 2u) )
    v23 = -1;
  v24 = operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
  v26 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v24;
  if ( v26 )
    operator delete(v26, v25);
  v27 = (WCHAR *)*((_QWORD *)this + 5);
  if ( !v27 )
  {
    v10 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::CreatePayloadEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      42,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate _spFileSearchPath.get()");
    return v10;
  }
  v28 = PathCchCombineEx(v27, v22, a3, L"*", v29);
  v10 = v28;
  if ( v28 < 0 )
  {
    LODWORD(v30) = 46;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::CreatePayloadEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      v30,
      v28);
    ProvPackageLog(3, L"    Failed to assemble search path string");
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x180017608  push    rbx
0x18001760a  push    rbp
0x18001760b  push    rsi
0x18001760c  push    rdi
0x18001760d  push    r12
0x18001760f  push    r14
0x180017611  sub     rsp, 38h
0x180017615  mov     rdi, rdx
0x180017618  mov     rbx, rcx
0x18001761b  mov     r12d, 2
0x180017621  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017628  mov     ecx, r12d; unsigned __int64
0x18001762b  mov     rsi, r8
0x18001762e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017633  mov     rcx, [rbx+20h]; void *
0x180017637  xor     ebp, ebp
0x180017639  mov     [rbx+20h], rax
0x18001763d  test    rcx, rcx
0x180017640  jz      short loc_180017647
0x180017642  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017647  mov     rcx, [rbx+20h]
0x18001764b  test    rcx, rcx
0x18001764e  jnz     short loc_180017695
0x180017650  lea     ebx, [rcx+3]
0x180017653  mov     edi, 8007000Eh
0x180017658  mov     [rsp+68h+var_40], edi
0x18001765c  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017663  mov     ecx, ebx
0x180017665  mov     dword ptr [rsp+68h+var_48], 17h
0x18001766d  lea     r8, aPayloadenumera_1; "PayloadEnumerator::CreatePayloadEnumera"...
0x180017674  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001767b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017680  lea     rdx, aFailedToAlloca_40; "    Failed to allocate _spCurrentDirect"...
0x180017687  mov     ecx, ebx
0x180017689  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001768e  mov     eax, edi
0x180017690  jmp     loc_180017883
0x180017695  mov     [rcx], bp
0x180017698  test    rdi, rdi
0x18001769b  jnz     short loc_1800176D8
0x18001769d  mov     edi, 80070057h
0x1800176a2  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800176a9  mov     ebx, 3
0x1800176ae  mov     [rsp+68h+var_40], edi
0x1800176b2  mov     ecx, ebx
0x1800176b4  mov     dword ptr [rsp+68h+var_48], 1Ch
0x1800176bc  lea     r8, aPayloadenumera_1; "PayloadEnumerator::CreatePayloadEnumera"...
0x1800176c3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800176ca  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800176cf  lea     rdx, aHimageArgument; "    hImage: Argument cannot be NULL"
0x1800176d6  jmp     short loc_180017687
0x1800176d8  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800176dc  mov     [rbx+8], rdi
0x1800176e0  mov     rax, r14
0x1800176e3  inc     rax
0x1800176e6  cmp     [rsi+rax*2], bp
0x1800176ea  jnz     short loc_1800176E3
0x1800176ec  lea     rdi, [rax+1]
0x1800176f0  mov     rax, r12
0x1800176f3  mul     rdi
0x1800176f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800176fd  cmovb   rax, r14
0x180017701  mov     rcx, rax; unsigned __int64
0x180017704  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017709  mov     rcx, [rbx+18h]; void *
0x18001770d  mov     [rbx+18h], rax
0x180017711  test    rcx, rcx
0x180017714  jz      short loc_18001771B
0x180017716  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001771b  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18001771f  test    rcx, rcx
0x180017722  jnz     short loc_180017760
0x180017724  lea     ebx, [rcx+3]
0x180017727  mov     edi, 8007000Eh
0x18001772c  mov     [rsp+68h+var_40], edi
0x180017730  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017737  mov     ecx, ebx
0x180017739  mov     dword ptr [rsp+68h+var_48], 22h ; '"'
0x180017741  lea     r8, aPayloadenumera_1; "PayloadEnumerator::CreatePayloadEnumera"...
0x180017748  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001774f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017754  lea     rdx, aFailedToAlloca_37; "    Failed to allocate _spElementPath.g"...
0x18001775b  jmp     loc_180017687
0x180017760  mov     r9d, 1; enum PATHCCH_OPTIONS
0x180017766  mov     r8, rsi; unsigned __int16 *
0x180017769  mov     rdx, rdi; unsigned __int64
0x18001776c  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x180017771  mov     edi, eax
0x180017773  test    eax, eax
0x180017775  jns     short loc_1800177B0
0x180017777  mov     [rsp+68h+var_40], eax
0x18001777b  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017782  mov     ebx, 3
0x180017787  mov     dword ptr [rsp+68h+var_48], 25h ; '%'
0x18001778f  mov     ecx, ebx
0x180017791  lea     r8, aPayloadenumera_1; "PayloadEnumerator::CreatePayloadEnumera"...
0x180017798  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001779f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800177a4  lea     rdx, aFailedToAssemb_12; "    Failed to assemble element path str"...
0x1800177ab  jmp     loc_180017687
0x1800177b0  mov     rcx, r14
0x1800177b3  inc     rcx
0x1800177b6  cmp     [rsi+rcx*2], bp
0x1800177ba  jnz     short loc_1800177B3
0x1800177bc  lea     rdi, [rcx+3]
0x1800177c0  mov     rax, r12
0x1800177c3  mul     rdi
0x1800177c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800177cd  cmovb   rax, r14
0x1800177d1  mov     rcx, rax; unsigned __int64
0x1800177d4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800177d9  mov     rcx, [rbx+28h]; void *
0x1800177dd  mov     [rbx+28h], rax
0x1800177e1  test    rcx, rcx
0x1800177e4  jz      short loc_1800177EB
0x1800177e6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800177eb  mov     rcx, [rbx+28h]; pszPathOut
0x1800177ef  test    rcx, rcx
0x1800177f2  jnz     short loc_180017830
0x1800177f4  lea     ebx, [rcx+3]
0x1800177f7  mov     edi, 8007000Eh
0x1800177fc  mov     [rsp+68h+var_40], edi
0x180017800  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017807  mov     ecx, ebx
0x180017809  mov     dword ptr [rsp+68h+var_48], 2Ah ; '*'
0x180017811  lea     r8, aPayloadenumera_1; "PayloadEnumerator::CreatePayloadEnumera"...
0x180017818  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001781f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017824  lea     rdx, aFailedToAlloca_43; "    Failed to allocate _spFileSearchPat"...
0x18001782b  jmp     loc_180017687
0x180017830  lea     r9, pszMore; "*"
0x180017837  mov     r8, rsi; pszPathIn
0x18001783a  mov     rdx, rdi; cchPathOut
0x18001783d  call    PathCchCombineEx
0x180017842  mov     edi, eax
0x180017844  test    eax, eax
0x180017846  jns     short loc_180017881
0x180017848  mov     [rsp+68h+var_40], eax
0x18001784c  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017853  mov     ebx, 3
0x180017858  mov     dword ptr [rsp+68h+var_48], 2Eh ; '.'
0x180017860  mov     ecx, ebx
0x180017862  lea     r8, aPayloadenumera_1; "PayloadEnumerator::CreatePayloadEnumera"...
0x180017869  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017870  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017875  lea     rdx, aFailedToAssemb_1; "    Failed to assemble search path stri"...
0x18001787c  jmp     loc_180017687
0x180017881  xor     eax, eax
0x180017883  add     rsp, 38h
0x180017887  pop     r14
0x180017889  pop     r12
0x18001788b  pop     rdi
0x18001788c  pop     rsi
0x18001788d  pop     rbp
0x18001788e  pop     rbx
0x18001788f  retn
```
