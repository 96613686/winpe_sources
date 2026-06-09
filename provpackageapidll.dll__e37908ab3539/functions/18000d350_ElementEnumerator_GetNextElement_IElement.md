# ElementEnumerator::GetNextElement(IElement * *)

- ea: `0x18000d350`
- end: `0x18000d700`
- name: `?GetNextElement@ElementEnumerator@@EEAAJPEAPEAUIElement@@@Z`
- size: `944`
- prototype: `__int64 __fastcall(ElementEnumerator *__hidden this, struct IElement **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x180001510`
- `0x180001e66`
- `0x180002084`
- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000d350`
- `0x18000d708`
- `0x18000e328`
- `0x18000fc8c`
- `0x180016c50`
- `0x180019010`

## string_xrefs

- `0x18000d4c8`: `    Failed to allocate spElementPath.get()`
- `0x18000d53e`: `    Failed to assemble element path`
- `0x18000d5f0`: `    Failed to open element`

## pseudocode

```c
__int64 __fastcall ElementEnumerator::GetNextElement(ElementEnumerator *this, struct IElement **a2)
{
  __int64 v4; // r8
  int NextFile; // eax
  unsigned int v6; // esi
  int NextElementType; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // rbp
  int v15; // edi
  HRESULT v16; // eax
  const struct std::nothrow_t *v17; // rdx
  Element *v18; // rbx
  const struct std::nothrow_t *v19; // rdx
  ULONG v20; // [rsp+20h] [rbp-2F8h]
  __int64 v21; // [rsp+20h] [rbp-2F8h]
  WCHAR *v22; // [rsp+30h] [rbp-2E8h]
  _BYTE v23[44]; // [rsp+40h] [rbp-2D8h] BYREF
  WCHAR pszMore[314]; // [rsp+6Ch] [rbp-2ACh] BYREF

  *a2 = 0;
  memset_0(v23, 0, 0x2A0u);
  do
  {
    v4 = *((_QWORD *)this + 7);
    if ( !v4 )
    {
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "ElementEnumerator::GetNextElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
        128,
        L"No more element types to enumerate");
      return 2147942659LL;
    }
    NextFile = GetNextFile(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL), (char *)this + 24, v4, v23);
    v6 = NextFile;
    if ( !*((_BYTE *)this + 64) || NextFile >= 0 )
    {
      if ( ((NextFile + 2147024893) & 0xFFFFFEFF) != 0 )
      {
        if ( NextFile < 0 )
        {
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "ElementEnumerator::GetNextElement",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
            155,
            NextFile);
          ProvPackageLog(3, L"    Failed to get next element");
          return v6;
        }
        continue;
      }
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "ElementEnumerator::GetNextElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
        151,
        L"No more elements to enumerate");
      return 2147942659LL;
    }
    NextElementType = ElementEnumerator::GetNextElementType(this);
    v6 = NextElementType;
    if ( NextElementType == -2147024637 )
    {
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "ElementEnumerator::GetNextElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
        140,
        L"No more element types to enumerate");
      return 2147942659LL;
    }
    if ( NextElementType < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ElementEnumerator::GetNextElement",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
        143,
        NextElementType);
      ProvPackageLog(3, L"    Failed to get next element type");
      return v6;
    }
  }
  while ( (v23[0] & 0x10) == 0 );
  v9 = -1;
  do
    ++v9;
  while ( pszMore[v9] );
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(*((_QWORD *)this + 5) + 2 * v10) );
  v11 = v9 + v10 + 2;
  v12 = 2 * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  v22 = v13;
  if ( !v13 )
  {
    v15 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      161,
      -2147024882,
      0);
    ProvPackageLog(3, L"    Failed to allocate spElementPath.get()");
    return (unsigned int)v15;
  }
  v16 = PathCchCombineEx(v13, v11, *((PCWSTR *)this + 5), pszMore, v20);
  v6 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v21) = 165;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v21,
      v16,
      v22);
    ProvPackageLog(3, L"    Failed to assemble element path");
    goto LABEL_30;
  }
  v18 = (Element *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v18 )
  {
    v15 = -2147024882;
    LODWORD(v21) = 169;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v21,
      -2147024882,
      v22,
      0);
    ProvPackageLog(3, L"    Failed to allocate ptr");
    goto LABEL_29;
  }
  *(_QWORD *)v18 = &Element::`vftable';
  *((_QWORD *)v18 + 1) = 0;
  *((_QWORD *)v18 + 2) = 0;
  *((_QWORD *)v18 + 3) = 0;
  *((_QWORD *)v18 + 4) = 0;
  *((_QWORD *)v18 + 5) = 0;
  v15 = Element::OpenElement(
          v18,
          *((struct ProvisioningPackage **)this + 1),
          *((const unsigned __int16 **)this + 5),
          pszMore);
  if ( v15 < 0 )
  {
    (*(void (__fastcall **)(Element *))(*(_QWORD *)v18 + 80LL))(v18);
    *a2 = 0;
    LODWORD(v21) = 180;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElement",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v21,
      v15,
      v22,
      v18);
    ProvPackageLog(3, L"    Failed to open element");
LABEL_29:
    v6 = v15;
LABEL_30:
    operator delete(v14, v17);
    return v6;
  }
  *a2 = v18;
  operator delete(v14, v19);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000d350  mov     [rsp+arg_10], rbx
0x18000d355  push    rbp
0x18000d356  push    rsi
0x18000d357  push    rdi
0x18000d358  push    r14
0x18000d35a  push    r15
0x18000d35c  sub     rsp, 2F0h
0x18000d363  mov     rax, cs:__security_cookie
0x18000d36a  xor     rax, rsp
0x18000d36d  mov     [rsp+318h+var_38], rax
0x18000d375  mov     r14, rdx
0x18000d378  mov     rdi, rcx
0x18000d37b  xor     r15d, r15d
0x18000d37e  mov     [rdx], r15
0x18000d381  xor     edx, edx; Val
0x18000d383  mov     r8d, 2A0h; Size
0x18000d389  lea     rcx, [rsp+318h+var_2D8]; void *
0x18000d38e  call    memset_0
0x18000d393  mov     ebx, 80070103h
0x18000d398  mov     r8, [rdi+38h]
0x18000d39c  test    r8, r8
0x18000d39f  jz      loc_18000D6A7
0x18000d3a5  lea     rdx, [rdi+18h]
0x18000d3a9  mov     rcx, [rdi+8]
0x18000d3ad  lea     r9, [rsp+318h+var_2D8]
0x18000d3b2  mov     rcx, [rcx+10h]
0x18000d3b6  call    ?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z; GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)
0x18000d3bb  mov     esi, eax
0x18000d3bd  cmp     [rdi+40h], r15b
0x18000d3c1  jz      short loc_18000D41F
0x18000d3c3  test    eax, eax
0x18000d3c5  jns     short loc_18000D41F
0x18000d3c7  mov     rcx, rdi; this
0x18000d3ca  call    ?GetNextElementType@ElementEnumerator@@AEAAJXZ; ElementEnumerator::GetNextElementType(void)
0x18000d3cf  mov     esi, eax
0x18000d3d1  cmp     eax, ebx
0x18000d3d3  jz      loc_18000D4DE
0x18000d3d9  test    eax, eax
0x18000d3db  jns     short loc_18000D437
0x18000d3dd  mov     dword ptr [rsp+318h+var_2F0], eax
0x18000d3e1  mov     dword ptr [rsp+318h+var_2F8], 8Fh
0x18000d3e9  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d3f0  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d3f7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d3fe  mov     ebx, 3
0x18000d403  mov     ecx, ebx
0x18000d405  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d40a  lea     rdx, aFailedToGetNex_4; "    Failed to get next element type"
0x18000d411  mov     ecx, ebx
0x18000d413  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d418  mov     eax, esi
0x18000d41a  jmp     loc_18000D6D9
0x18000d41f  add     eax, 7FF8FFFDh
0x18000d424  test    eax, 0FFFFFEFFh
0x18000d429  jz      loc_18000D691
0x18000d42f  test    esi, esi
0x18000d431  js      loc_18000D658
0x18000d437  test    [rsp+318h+var_2D8], 10h
0x18000d43c  jz      loc_18000D398
0x18000d442  lea     rcx, [rsp+318h+pszMore]
0x18000d447  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d44b  mov     rax, r8
0x18000d44e  inc     rax
0x18000d451  cmp     [rcx+rax*2], r15w
0x18000d456  jnz     short loc_18000D44E
0x18000d458  mov     rdx, [rdi+28h]
0x18000d45c  mov     rcx, r8
0x18000d45f  inc     rcx
0x18000d462  cmp     [rdx+rcx*2], r15w
0x18000d467  jnz     short loc_18000D45F
0x18000d469  lea     rbx, [rcx+2]
0x18000d46d  add     rbx, rax
0x18000d470  mov     eax, 2
0x18000d475  mul     rbx
0x18000d478  cmovb   rax, r8
0x18000d47c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d483  mov     rcx, rax; unsigned __int64
0x18000d486  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d48b  mov     rbp, rax
0x18000d48e  mov     [rsp+318h+var_2E8], rax
0x18000d493  test    rax, rax
0x18000d496  jnz     short loc_18000D4F7
0x18000d498  mov     edi, 8007000Eh
0x18000d49d  mov     dword ptr [rsp+318h+var_2F0], edi
0x18000d4a1  mov     dword ptr [rsp+318h+var_2F8], 0A1h
0x18000d4a9  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d4b0  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d4b7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d4be  lea     ebx, [rax+3]
0x18000d4c1  mov     ecx, ebx
0x18000d4c3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d4c8  lea     rdx, aFailedToAlloca_2; "    Failed to allocate spElementPath.ge"...
0x18000d4cf  mov     ecx, ebx
0x18000d4d1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d4d6  nop
0x18000d4d7  mov     eax, edi
0x18000d4d9  jmp     loc_18000D6D9
0x18000d4de  lea     rcx, aNoMoreElementT; "No more element types to enumerate"
0x18000d4e5  mov     [rsp+318h+var_2F0], rcx
0x18000d4ea  mov     dword ptr [rsp+318h+var_2F8], 8Ch
0x18000d4f2  jmp     loc_18000D6BB
0x18000d4f7  lea     r9, [rsp+318h+pszMore]; pszMore
0x18000d4fc  mov     r8, [rdi+28h]; pszPathIn
0x18000d500  mov     rdx, rbx; cchPathOut
0x18000d503  mov     rcx, rbp; pszPathOut
0x18000d506  call    PathCchCombineEx
0x18000d50b  mov     esi, eax
0x18000d50d  test    eax, eax
0x18000d50f  jns     short loc_18000D551
0x18000d511  mov     dword ptr [rsp+318h+var_2F0], eax
0x18000d515  mov     dword ptr [rsp+318h+var_2F8], 0A5h
0x18000d51d  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d524  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d52b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d532  mov     ebx, 3
0x18000d537  mov     ecx, ebx
0x18000d539  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d53e  lea     rdx, aFailedToAssemb; "    Failed to assemble element path"
0x18000d545  mov     ecx, ebx
0x18000d547  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d54c  jmp     loc_18000D64B
0x18000d551  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d558  mov     ecx, 30h ; '0'; unsigned __int64
0x18000d55d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d562  mov     rbx, rax
0x18000d565  mov     [rsp+318h+var_2E0], rax
0x18000d56a  test    rax, rax
0x18000d56d  jz      loc_18000D609
0x18000d573  lea     rax, ??_7Element@@6B@; const Element::`vftable'
0x18000d57a  mov     [rbx], rax
0x18000d57d  mov     [rbx+8], r15
0x18000d581  mov     [rbx+10h], r15
0x18000d585  mov     [rbx+18h], r15
0x18000d589  mov     [rbx+20h], r15
0x18000d58d  mov     [rbx+28h], r15
0x18000d591  test    rbx, rbx
0x18000d594  jz      short loc_18000D609
0x18000d596  lea     r9, [rsp+318h+pszMore]; unsigned __int16 *
0x18000d59b  mov     r8, [rdi+28h]; unsigned __int16 *
0x18000d59f  mov     rdx, [rdi+8]; struct ProvisioningPackage *
0x18000d5a3  mov     rcx, rbx; this
0x18000d5a6  call    ?OpenElement@Element@@QEAAJPEAVProvisioningPackage@@PEBG1@Z; Element::OpenElement(ProvisioningPackage *,ushort const *,ushort const *)
0x18000d5ab  mov     edi, eax
0x18000d5ad  test    eax, eax
0x18000d5af  jns     short loc_18000D5F9
0x18000d5b1  mov     rdx, [rbx]
0x18000d5b4  mov     rcx, rbx
0x18000d5b7  mov     rax, [rdx+50h]
0x18000d5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c0  mov     [r14], r15
0x18000d5c3  mov     dword ptr [rsp+318h+var_2F0], edi
0x18000d5c7  mov     dword ptr [rsp+318h+var_2F8], 0B4h
0x18000d5cf  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d5d6  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d5dd  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d5e4  mov     ebx, 3
0x18000d5e9  mov     ecx, ebx
0x18000d5eb  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d5f0  lea     rdx, aFailedToOpenEl; "    Failed to open element"
0x18000d5f7  jmp     short loc_18000D642
0x18000d5f9  mov     [r14], rbx
0x18000d5fc  mov     rcx, rbp; void *
0x18000d5ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d604  jmp     loc_18000D4D7
0x18000d609  mov     edi, 8007000Eh
0x18000d60e  mov     dword ptr [rsp+318h+var_2F0], edi
0x18000d612  mov     dword ptr [rsp+318h+var_2F8], 0A9h
0x18000d61a  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d621  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d628  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d62f  mov     ebx, 3
0x18000d634  mov     ecx, ebx
0x18000d636  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d63b  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x18000d642  mov     ecx, ebx
0x18000d644  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d649  mov     esi, edi
0x18000d64b  mov     rcx, rbp; void *
0x18000d64e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d653  jmp     loc_18000D418
0x18000d658  mov     dword ptr [rsp+318h+var_2F0], esi
0x18000d65c  mov     dword ptr [rsp+318h+var_2F8], 9Bh
0x18000d664  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d66b  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d672  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d679  mov     ebx, 3
0x18000d67e  mov     ecx, ebx
0x18000d680  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d685  lea     rdx, aFailedToGetNex; "    Failed to get next element"
0x18000d68c  jmp     loc_18000D411
0x18000d691  lea     rax, aNoMoreElements; "No more elements to enumerate"
0x18000d698  mov     [rsp+318h+var_2F0], rax
0x18000d69d  mov     dword ptr [rsp+318h+var_2F8], 97h
0x18000d6a5  jmp     short loc_18000D6BB
0x18000d6a7  lea     rcx, aNoMoreElementT; "No more element types to enumerate"
0x18000d6ae  mov     [rsp+318h+var_2F0], rcx
0x18000d6b3  mov     dword ptr [rsp+318h+var_2F8], 80h
0x18000d6bb  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d6c2  lea     r8, aElementenumera_0; "ElementEnumerator::GetNextElement"
0x18000d6c9  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x18000d6d0  xor     ecx, ecx
0x18000d6d2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d6d7  mov     eax, ebx
0x18000d6d9  mov     rcx, [rsp+318h+var_38]
0x18000d6e1  xor     rcx, rsp; StackCookie
0x18000d6e4  call    __security_check_cookie
0x18000d6e9  mov     rbx, [rsp+318h+arg_10]
0x18000d6f1  add     rsp, 2F0h
0x18000d6f8  pop     r15
0x18000d6fa  pop     r14
0x18000d6fc  pop     rdi
0x18000d6fd  pop     rsi
0x18000d6fe  pop     rbp
0x18000d6ff  retn
```
