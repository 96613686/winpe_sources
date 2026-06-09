# Element::ExportPayload(ushort const *,int)

- ea: `0x180015930`
- end: `0x18001603c`
- name: `?ExportPayload@Element@@EEAAJPEBGH@Z`
- size: `1804`
- prototype: `__int64 __fastcall(Element *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000da5c`
- `0x18000e060`
- `0x18000fc8c`
- `0x180015930`
- `0x180019010`

## string_xrefs

- `0x180015f10`: `    Failed to allocate spPayloadPath.get()`
- `0x180015e8e`: `    Failed to get next payload path`
- `0x180015fd9`: `    Failed to get next payload path`
- `0x180015d3f`: `    Failed to assemble destination path`
- `0x180015c61`: `    Failed to assemble source path`
- `0x180015e15`: `    Failed to create intermediate directories`

## pseudocode

```c
__int64 __fastcall Element::ExportPayload(Element *this, const unsigned __int16 *a2, int a3)
{
  WCHAR *v3; // rsi
  int v4; // eax
  unsigned int v5; // edi
  WCHAR *v7; // r12
  WCHAR *v8; // r14
  void *v9; // rbx
  void *v10; // rdi
  WCHAR *v11; // r15
  int v12; // eax
  const struct std::nothrow_t *v13; // rdx
  unsigned int v14; // r13d
  unsigned __int64 v15; // rax
  const struct std::nothrow_t *v16; // rdx
  void *v17; // rcx
  int v18; // eax
  unsigned int v19; // esi
  signed int IntermediateDirectories; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // r15
  unsigned __int64 v24; // rax
  const struct std::nothrow_t *v25; // rdx
  WCHAR *v26; // rcx
  HRESULT v27; // eax
  unsigned int v28; // r15d
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned __int64 v31; // rax
  const struct std::nothrow_t *v32; // rdx
  WCHAR *v33; // rcx
  HRESULT v34; // eax
  int File; // eax
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  const struct std::nothrow_t *v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  const struct std::nothrow_t *v41; // rdx
  const struct std::nothrow_t *v42; // rdx
  const struct std::nothrow_t *v43; // rdx
  void (*v44)(void); // rax
  const struct std::nothrow_t *v45; // rdx
  const struct std::nothrow_t *v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  const struct std::nothrow_t *v48; // rdx
  const struct std::nothrow_t *v49; // rdx
  const struct std::nothrow_t *v50; // rdx
  const struct std::nothrow_t *v51; // rdx
  const struct std::nothrow_t *v52; // rdx
  const struct std::nothrow_t *v53; // rdx
  const struct std::nothrow_t *v54; // rdx
  __int64 v55; // [rsp+20h] [rbp-58h]
  __int64 v56; // [rsp+20h] [rbp-58h]
  unsigned __int64 v57; // [rsp+30h] [rbp-48h] BYREF
  void *v58; // [rsp+38h] [rbp-40h]
  WCHAR *v59; // [rsp+40h] [rbp-38h]
  WCHAR *v60; // [rsp+48h] [rbp-30h]
  size_t cchPathOut; // [rsp+50h] [rbp-28h]
  __int64 *v62; // [rsp+58h] [rbp-20h]
  char v63; // [rsp+60h] [rbp-18h]
  __int64 v67; // [rsp+D8h] [rbp+60h] BYREF

  v3 = 0;
  v67 = 0;
  v62 = &v67;
  v63 = 1;
  v4 = (*(__int64 (__fastcall **)(Element *, __int64 *))(*(_QWORD *)this + 64LL))(this, &v67);
  v5 = v4;
  if ( v4 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::ExportPayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      479,
      v4);
    ProvPackageLog(3, L"    Failed to enumerate payloads");
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    return v5;
  }
  v7 = 0;
  v59 = 0;
  v8 = 0;
  v60 = 0;
  v9 = 0;
  v58 = 0;
  v57 = 0;
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    v12 = (**(__int64 (__fastcall ***)(__int64, unsigned __int64 *))v67)(v67, &v57);
    v14 = v12;
    if ( v12 < 0 )
      break;
    v15 = 2 * v57;
    if ( !is_mul_ok(v57, 2u) )
      v15 = -1;
    v10 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v9;
    v9 = v10;
    v58 = v10;
    if ( v17 )
      operator delete(v17, v16);
    if ( !v10 )
    {
      LODWORD(v55) = 489;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v55,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate spPayloadPath.get()");
      if ( v8 )
        operator delete(v8, v53);
      if ( v7 )
        operator delete(v7, v53);
      if ( v67 )
      {
        v44 = *(void (**)(void))(*(_QWORD *)v67 + 16LL);
LABEL_72:
        v44();
      }
      return 2147942414LL;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, void *, unsigned __int64))(*(_QWORD *)v67 + 8LL))(v67, v10, v57);
    v19 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v55) = 492;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v55,
        v18);
      ProvPackageLog(3, L"    Failed to get next payload path");
      operator delete(v10, v51);
      if ( v8 )
        operator delete(v8, v52);
      if ( v7 )
        operator delete(v7, v52);
      if ( v67 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      return v19;
    }
    IntermediateDirectories = CreateIntermediateDirectories(a2, (const unsigned __int16 *)v10);
    v19 = IntermediateDirectories;
    if ( IntermediateDirectories < 0 )
    {
      LODWORD(v55) = 495;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v55,
        IntermediateDirectories);
      ProvPackageLog(3, L"    Failed to create intermediate directories");
      operator delete(v10, v49);
      if ( v8 )
        operator delete(v8, v50);
      if ( v7 )
        operator delete(v7, v50);
      if ( v67 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      return v19;
    }
    v21 = -1;
    do
      ++v21;
    while ( a2[v21] );
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v10 + v22) );
    v23 = v22 + v21 + 6;
    v24 = 2 * v23;
    if ( !is_mul_ok(v23, 2u) )
      v24 = -1;
    v3 = (WCHAR *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v7;
    v7 = v3;
    v59 = v3;
    if ( v26 )
      operator delete(v26, v25);
    if ( !v3 )
    {
      LODWORD(v55) = 500;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v55,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate spDestination.get()");
      operator delete(v10, v47);
      if ( v8 )
        operator delete(v8, v48);
LABEL_42:
      if ( v67 )
      {
        v44 = *(void (**)(void))(*(_QWORD *)v67 + 16LL);
        goto LABEL_72;
      }
      return 2147942414LL;
    }
    v27 = PathCchCombineEx(v3, v23, a2, (PCWSTR)v10, v55);
    v28 = v27;
    if ( v27 < 0 )
    {
      LODWORD(v56) = 504;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v56,
        v27);
      ProvPackageLog(3, L"    Failed to assemble destination path");
      operator delete(v10, v45);
      if ( v8 )
        operator delete(v8, v46);
      operator delete(v3, v46);
      if ( v67 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      return v28;
    }
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v10 + v29) );
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(*((_QWORD *)this + 2) + 2 * v30) );
    cchPathOut = v29 + 6 + v30;
    v31 = 2 * cchPathOut;
    if ( !is_mul_ok(cchPathOut, 2u) )
      v31 = -1;
    v11 = (WCHAR *)operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
    v33 = v8;
    v8 = v11;
    v60 = v11;
    if ( v33 )
      operator delete(v33, v32);
    if ( !v11 )
    {
      LODWORD(v56) = 509;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v56,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate spSource.get()");
      operator delete(v10, v42);
      operator delete(v3, v43);
      goto LABEL_42;
    }
    v34 = PathCchCombineEx(v11, cchPathOut, *((PCWSTR *)this + 2), (PCWSTR)v10, v56);
    v14 = v34;
    if ( v34 < 0 )
    {
      LODWORD(v55) = 513;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v55,
        v34);
      ProvPackageLog(3, L"    Failed to assemble source path");
      operator delete(v10, v39);
      operator delete(v11, v40);
      operator delete(v3, v41);
      if ( v67 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      return v14;
    }
    File = ExtractFile(*(void **)(*((_QWORD *)this + 1) + 16LL), v11, v3, a3);
    v14 = File;
    if ( File < 0 )
    {
      LODWORD(v55) = 516;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::ExportPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v55,
        File);
      ProvPackageLog(3, L"    Failed to extract payload file");
      operator delete(v10, v36);
      operator delete(v11, v37);
      operator delete(v3, v38);
      if ( v67 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      return v14;
    }
  }
  if ( v12 != -2147024637 )
  {
    LODWORD(v55) = 523;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::ExportPayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v55,
      v12);
    ProvPackageLog(3, L"    Failed to get next payload path");
    if ( v10 )
      operator delete(v10, v54);
    if ( v11 )
      operator delete(v11, v54);
    if ( v3 )
      operator delete(v3, v54);
    if ( v67 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    return v14;
  }
  if ( v10 )
    operator delete(v10, v13);
  if ( v11 )
    operator delete(v11, v13);
  if ( v3 )
    operator delete(v3, v13);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  return 0;
}

```

## disassembly

```asm
0x180015930  mov     [rsp-40h+arg_10], r8d
0x180015935  mov     [rsp-40h+pszPathIn], rdx
0x18001593a  mov     [rsp-40h+arg_0], rcx
0x18001593f  push    rbp
0x180015940  push    rbx
0x180015941  push    rsi
0x180015942  push    rdi
0x180015943  push    r12
0x180015945  push    r13
0x180015947  push    r14
0x180015949  push    r15
0x18001594b  mov     rbp, rsp
0x18001594e  sub     rsp, 78h
0x180015952  xor     esi, esi
0x180015954  mov     [rbp+arg_18], rsi
0x180015958  lea     rax, [rbp+arg_18]
0x18001595c  mov     [rbp+var_20], rax
0x180015960  mov     [rbp+var_18], 1
0x180015964  mov     rax, [rcx]
0x180015967  lea     rdx, [rbp+arg_18]
0x18001596b  mov     rax, [rax+40h]
0x18001596f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015974  mov     edi, eax
0x180015976  test    eax, eax
0x180015978  jns     short loc_1800159D1
0x18001597a  mov     [rsp+78h+var_50], eax
0x18001597e  mov     dword ptr [rsp+78h+var_58], 1DFh
0x180015986  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001598d  lea     r8, aElementExportp; "Element::ExportPayload"
0x180015994  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001599b  lea     ebx, [rsi+3]
0x18001599e  mov     ecx, ebx
0x1800159a0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800159a5  lea     rdx, aFailedToEnumer; "    Failed to enumerate payloads"
0x1800159ac  mov     ecx, ebx
0x1800159ae  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800159b3  nop
0x1800159b4  mov     rcx, [rbp+arg_18]
0x1800159b8  test    rcx, rcx
0x1800159bb  jz      short loc_1800159CA
0x1800159bd  mov     rax, [rcx]
0x1800159c0  mov     rax, [rax+10h]
0x1800159c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c9  nop
0x1800159ca  mov     eax, edi
0x1800159cc  jmp     loc_18001602B
0x1800159d1  mov     r12, rsi
0x1800159d4  mov     [rbp+var_38], rsi
0x1800159d8  mov     r14, rsi
0x1800159db  mov     [rbp+var_30], rsi
0x1800159df  mov     rbx, rsi
0x1800159e2  mov     [rbp+var_40], rbx
0x1800159e6  mov     [rbp+var_48], rsi
0x1800159ea  mov     rdi, rsi
0x1800159ed  mov     r15, rsi
0x1800159f0  mov     rcx, [rbp+arg_18]
0x1800159f4  mov     rax, [rcx]
0x1800159f7  lea     rdx, [rbp+var_48]
0x1800159fb  mov     rax, [rax]
0x1800159fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a03  mov     r13d, eax
0x180015a06  test    eax, eax
0x180015a08  js      loc_180015F5B
0x180015a0e  mov     eax, 2
0x180015a13  mul     [rbp+var_48]
0x180015a17  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015a1e  cmovb   rax, rcx
0x180015a22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015a29  mov     rcx, rax; unsigned __int64
0x180015a2c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015a31  mov     rdi, rax
0x180015a34  mov     rcx, rbx; void *
0x180015a37  mov     rbx, rax
0x180015a3a  mov     [rbp+var_40], rax
0x180015a3e  xor     r15d, r15d
0x180015a41  test    rcx, rcx
0x180015a44  jz      short loc_180015A4B
0x180015a46  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015a4b  test    rdi, rdi
0x180015a4e  jz      loc_180015EDF
0x180015a54  mov     rcx, [rbp+arg_18]
0x180015a58  mov     rax, [rcx]
0x180015a5b  mov     r8, [rbp+var_48]
0x180015a5f  mov     rdx, rdi
0x180015a62  mov     rax, [rax+8]
0x180015a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a6b  mov     esi, eax
0x180015a6d  test    eax, eax
0x180015a6f  js      loc_180015E61
0x180015a75  mov     rdx, rdi; unsigned __int16 *
0x180015a78  mov     r13, [rbp+pszPathIn]
0x180015a7c  mov     rcx, r13; unsigned __int16 *
0x180015a7f  call    ?CreateIntermediateDirectories@@YAJPEBG0H@Z; CreateIntermediateDirectories(ushort const *,ushort const *,int)
0x180015a84  mov     esi, eax
0x180015a86  test    eax, eax
0x180015a88  js      loc_180015DE8
0x180015a8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015a92  mov     rcx, r8
0x180015a95  inc     rcx
0x180015a98  cmp     [r13+rcx*2+0], r15w
0x180015a9e  jnz     short loc_180015A95
0x180015aa0  mov     rax, r8
0x180015aa3  inc     rax
0x180015aa6  cmp     [rdi+rax*2], r15w
0x180015aab  jnz     short loc_180015AA3
0x180015aad  lea     r15, [rcx+6]
0x180015ab1  add     r15, rax
0x180015ab4  mov     eax, 2
0x180015ab9  mul     r15
0x180015abc  cmovb   rax, r8
0x180015ac0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015ac7  mov     rcx, rax; unsigned __int64
0x180015aca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015acf  mov     rsi, rax
0x180015ad2  mov     rcx, r12; void *
0x180015ad5  mov     r12, rax
0x180015ad8  mov     [rbp+var_38], rax
0x180015adc  test    rcx, rcx
0x180015adf  jz      short loc_180015AE6
0x180015ae1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015ae6  test    rsi, rsi
0x180015ae9  jz      loc_180015D8C
0x180015aef  mov     r9, rdi; pszMore
0x180015af2  mov     r8, r13; pszPathIn
0x180015af5  mov     rdx, r15; cchPathOut
0x180015af8  mov     rcx, rsi; pszPathOut
0x180015afb  call    PathCchCombineEx
0x180015b00  mov     r15d, eax
0x180015b03  xor     r13d, r13d
0x180015b06  test    eax, eax
0x180015b08  js      loc_180015D11
0x180015b0e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180015b12  mov     rax, r9
0x180015b15  inc     rax
0x180015b18  cmp     [rdi+rax*2], r13w
0x180015b1d  jnz     short loc_180015B15
0x180015b1f  mov     r13, [rbp+arg_0]
0x180015b23  mov     rdx, [r13+10h]
0x180015b27  mov     rcx, r9
0x180015b2a  xor     r8d, r8d
0x180015b2d  inc     rcx
0x180015b30  cmp     [rdx+rcx*2], r8w
0x180015b35  jnz     short loc_180015B2D
0x180015b37  add     rax, 6
0x180015b3b  add     rcx, rax
0x180015b3e  mov     [rbp+cchPathOut], rcx
0x180015b42  mov     eax, 2
0x180015b47  mul     rcx
0x180015b4a  cmovb   rax, r9
0x180015b4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015b55  mov     rcx, rax; unsigned __int64
0x180015b58  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015b5d  mov     r15, rax
0x180015b60  mov     rcx, r14; void *
0x180015b63  mov     r14, rax
0x180015b66  mov     [rbp+var_30], rax
0x180015b6a  test    rcx, rcx
0x180015b6d  jz      short loc_180015B74
0x180015b6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015b74  test    r15, r15
0x180015b77  jz      loc_180015CA6
0x180015b7d  mov     r9, rdi; pszMore
0x180015b80  mov     r8, [r13+10h]; pszPathIn
0x180015b84  mov     rdx, [rbp+cchPathOut]; cchPathOut
0x180015b88  mov     rcx, r15; pszPathOut
0x180015b8b  call    PathCchCombineEx
0x180015b90  mov     r13d, eax
0x180015b93  test    eax, eax
0x180015b95  js      loc_180015C33
0x180015b9b  mov     rcx, [rbp+arg_0]
0x180015b9f  mov     rcx, [rcx+8]
0x180015ba3  mov     r9d, [rbp+arg_10]; int
0x180015ba7  mov     r8, rsi; unsigned __int16 *
0x180015baa  mov     rdx, r15; unsigned __int16 *
0x180015bad  mov     rcx, [rcx+10h]; void *
0x180015bb1  call    ?ExtractFile@@YAJPEAXPEBG1H@Z; ExtractFile(void *,ushort const *,ushort const *,int)
0x180015bb6  mov     r13d, eax
0x180015bb9  test    eax, eax
0x180015bbb  jns     loc_1800159F0
0x180015bc1  mov     [rsp+78h+var_50], eax
0x180015bc5  mov     dword ptr [rsp+78h+var_58], 204h
0x180015bcd  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015bd4  lea     r8, aElementExportp; "Element::ExportPayload"
0x180015bdb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015be2  mov     ebx, 3
0x180015be7  mov     ecx, ebx
0x180015be9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015bee  lea     rdx, aFailedToExtrac_0; "    Failed to extract payload file"
0x180015bf5  mov     ecx, ebx
0x180015bf7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015bfc  nop
0x180015bfd  mov     rcx, rdi; void *
0x180015c00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c05  nop
0x180015c06  mov     rcx, r15; void *
0x180015c09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c0e  nop
0x180015c0f  mov     rcx, rsi; void *
0x180015c12  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c17  nop
0x180015c18  mov     rcx, [rbp+arg_18]
0x180015c1c  test    rcx, rcx
0x180015c1f  jz      short loc_180015C2E
0x180015c21  mov     rax, [rcx]
0x180015c24  mov     rax, [rax+10h]
0x180015c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c2d  nop
0x180015c2e  jmp     loc_180016028
0x180015c33  mov     [rsp+78h+var_50], r13d
0x180015c38  mov     dword ptr [rsp+78h+var_58], 201h
0x180015c40  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015c47  lea     r8, aElementExportp; "Element::ExportPayload"
0x180015c4e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015c55  mov     ebx, 3
0x180015c5a  mov     ecx, ebx
0x180015c5c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015c61  lea     rdx, aFailedToAssemb_10; "    Failed to assemble source path"
0x180015c68  mov     ecx, ebx
0x180015c6a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015c6f  nop
0x180015c70  mov     rcx, rdi; void *
0x180015c73  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c78  nop
0x180015c79  mov     rcx, r15; void *
0x180015c7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c81  nop
0x180015c82  mov     rcx, rsi; void *
0x180015c85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c8a  nop
0x180015c8b  mov     rcx, [rbp+arg_18]
0x180015c8f  test    rcx, rcx
0x180015c92  jz      short loc_180015CA1
0x180015c94  mov     rax, [rcx]
0x180015c97  mov     rax, [rax+10h]
0x180015c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca0  nop
0x180015ca1  jmp     loc_180016028
0x180015ca6  mov     [rsp+78h+var_50], 8007000Eh
0x180015cae  mov     dword ptr [rsp+78h+var_58], 1FDh
0x180015cb6  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015cbd  lea     r8, aElementExportp; "Element::ExportPayload"
0x180015cc4  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015ccb  mov     ebx, 3
0x180015cd0  mov     ecx, ebx
0x180015cd2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015cd7  lea     rdx, aFailedToAlloca_6; "    Failed to allocate spSource.get()"
0x180015cde  mov     ecx, ebx
0x180015ce0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015ce5  nop
0x180015ce6  mov     rcx, rdi; void *
0x180015ce9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015cee  nop
0x180015cef  mov     rcx, rsi; void *
0x180015cf2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015cf7  nop
0x180015cf8  mov     rcx, [rbp+arg_18]
0x180015cfc  test    rcx, rcx
0x180015cff  jz      loc_180015F51
0x180015d05  mov     rax, [rcx]
0x180015d08  mov     rax, [rax+10h]
0x180015d0c  jmp     loc_180015F4B
0x180015d11  mov     [rsp+78h+var_50], r15d
0x180015d16  mov     dword ptr [rsp+78h+var_58], 1F8h
0x180015d1e  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015d25  lea     r8, aElementExportp; "Element::ExportPayload"
0x180015d2c  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015d33  mov     ebx, 3
0x180015d38  mov     ecx, ebx
0x180015d3a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015d3f  lea     rdx, aFailedToAssemb_18; "    Failed to assemble destination path"
0x180015d46  mov     ecx, ebx
0x180015d48  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015d4d  nop
0x180015d4e  mov     rcx, rdi; void *
0x180015d51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015d56  nop
0x180015d57  test    r14, r14
0x180015d5a  jz      short loc_180015D65
0x180015d5c  mov     rcx, r14; void *
0x180015d5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015d64  nop
0x180015d65  mov     rcx, rsi; void *
0x180015d68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015d6d  nop
0x180015d6e  mov     rcx, [rbp+arg_18]
0x180015d72  test    rcx, rcx
0x180015d75  jz      short loc_180015D84
0x180015d77  mov     rax, [rcx]
0x180015d7a  mov     rax, [rax+10h]
0x180015d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d83  nop
0x180015d84  mov     eax, r15d
0x180015d87  jmp     loc_18001602B
0x180015d8c  mov     [rsp+78h+var_50], 8007000Eh
0x180015d94  mov     dword ptr [rsp+78h+var_58], 1F4h
0x180015d9c  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015da3  lea     r8, aElementExportp; "Element::ExportPayload"
0x180015daa  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015db1  mov     ebx, 3
0x180015db6  mov     ecx, ebx
  ... truncated ...
```
