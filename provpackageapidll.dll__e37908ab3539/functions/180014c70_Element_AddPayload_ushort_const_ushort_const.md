# Element::AddPayload(ushort const *,ushort const *)

- ea: `0x180014c70`
- end: `0x180014f83`
- name: `?AddPayload@Element@@EEAAJPEBG0@Z`
- size: `787`
- prototype: `__int64 __fastcall(Element *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180005424`
- `0x180006014`
- `0x18000fc8c`
- `0x180014c70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180014e18`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180014e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f0a`
- `WIMGAPI!WIMAddImagePath` at `0x180014e38`
- `WIMGAPI!WIMAddImagePath` at `0x180014eed`
- `WIMGAPI!WIMAddImagePath` at `0x180014e38`
- `WIMGAPI!WIMAddImagePath` at `0x180014eed`

## string_xrefs

- `0x180014d13`: `    Failed to allocate spDestinationPath.get()`
- `0x180014d6e`: `    Failed to assemble destination path`
- `0x180014eab`: `    Failed to create destination folder`

## pseudocode

```c
__int64 __fastcall Element::AddPayload(Element *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rbp
  unsigned int v13; // edi
  HRESULT v15; // eax
  const struct std::nothrow_t *v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int16 *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  const struct std::nothrow_t *v21; // rdx
  __int64 v22; // rbx
  signed int LastError; // eax
  bool v24; // sf
  signed int v25; // eax
  signed int v26; // eax
  unsigned int v27; // ebx
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  ULONG v31; // [rsp+20h] [rbp-38h]
  __int64 v32; // [rsp+20h] [rbp-38h]

  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = *((_QWORD *)this + 2);
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v7 + 2 * v8) );
  v9 = v8 + v6 + 2;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddPayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      325,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate spDestinationPath.get()");
    return v13;
  }
  v15 = PathCchCombineEx(v11, v9, *((PCWSTR *)this + 2), a2, v31);
  v13 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v32) = 329;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddPayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v32,
      v15);
    ProvPackageLog(3, L"    Failed to assemble destination path");
    operator delete(v12, v16);
    return v13;
  }
  v17 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v17 = -1;
  v18 = (unsigned __int16 *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
  v19 = StringCchCopyW(v18, v9, v12);
  v20 = v19;
  if ( v19 >= 0 )
  {
    *wcsrchr(v18, 0x5Cu) = 0;
    v22 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
    if ( (unsigned int)WIMAddImagePath(v22, 0, v18, 33554434) || GetLastError() == 183 )
      goto LABEL_33;
    LastError = GetLastError();
    v24 = LastError < 0;
    if ( LastError > 0 )
      v24 = 1;
    if ( !v24 )
    {
LABEL_33:
      if ( (unsigned int)WIMAddImagePath(v22, a3, v12, 2) )
        goto LABEL_37;
      v28 = GetLastError();
      v29 = v28 < 0;
      if ( v28 > 0 )
        v29 = 1;
      if ( !v29 )
      {
LABEL_37:
        if ( v18 )
          operator delete(v18, v21);
        v20 = 0;
        goto LABEL_40;
      }
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      LODWORD(v32) = 349;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::AddPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v32,
        v30);
      ProvPackageLog(3, L"    Failed to add payload");
    }
    else
    {
      v25 = GetLastError();
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      LODWORD(v32) = 344;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::AddPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v32,
        v25);
      ProvPackageLog(3, L"    Failed to create destination folder");
    }
    v26 = GetLastError();
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( v18 )
      operator delete(v18, v21);
    v20 = v27;
  }
  else
  {
    LODWORD(v32) = 334;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::AddPayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v32,
      v19);
    ProvPackageLog(3, L"    Failed to assemble destination folder");
    if ( v18 )
      operator delete(v18, v21);
  }
LABEL_40:
  operator delete(v12, v21);
  return v20;
}

```

## disassembly

```asm
0x180014c70  mov     [rsp+arg_8], rbx
0x180014c75  mov     [rsp+arg_10], rbp
0x180014c7a  push    rsi
0x180014c7b  push    rdi
0x180014c7c  push    r12
0x180014c7e  push    r14
0x180014c80  push    r15
0x180014c82  sub     rsp, 30h
0x180014c86  mov     r14, r8
0x180014c89  mov     rdi, rdx
0x180014c8c  mov     rbx, rcx
0x180014c8f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180014c93  mov     rax, r12
0x180014c96  xor     r15d, r15d
0x180014c99  inc     rax
0x180014c9c  cmp     [rdx+rax*2], r15w
0x180014ca1  jnz     short loc_180014C99
0x180014ca3  mov     rdx, [rcx+10h]
0x180014ca7  mov     rcx, r12
0x180014caa  inc     rcx
0x180014cad  cmp     [rdx+rcx*2], r15w
0x180014cb2  jnz     short loc_180014CAA
0x180014cb4  lea     rsi, [rax+2]
0x180014cb8  add     rsi, rcx
0x180014cbb  mov     eax, 2
0x180014cc0  mul     rsi
0x180014cc3  cmovb   rax, r12
0x180014cc7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014cce  mov     rcx, rax; unsigned __int64
0x180014cd1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014cd6  mov     rbp, rax
0x180014cd9  mov     [rsp+58h+arg_0], rax
0x180014cde  test    rax, rax
0x180014ce1  jnz     short loc_180014D29
0x180014ce3  mov     edi, 8007000Eh
0x180014ce8  mov     [rsp+58h+var_30], edi
0x180014cec  mov     dword ptr [rsp+58h+var_38], 145h
0x180014cf4  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014cfb  lea     r8, aElementAddpayl; "Element::AddPayload"
0x180014d02  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014d09  lea     ebx, [rax+3]
0x180014d0c  mov     ecx, ebx
0x180014d0e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014d13  lea     rdx, aFailedToAlloca_12; "    Failed to allocate spDestinationPat"...
0x180014d1a  mov     ecx, ebx
0x180014d1c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014d21  nop
0x180014d22  mov     eax, edi
0x180014d24  jmp     loc_180014F6C
0x180014d29  mov     r9, rdi; pszMore
0x180014d2c  mov     r8, [rbx+10h]; pszPathIn
0x180014d30  mov     rdx, rsi; cchPathOut
0x180014d33  mov     rcx, rbp; pszPathOut
0x180014d36  call    PathCchCombineEx
0x180014d3b  mov     edi, eax
0x180014d3d  test    eax, eax
0x180014d3f  jns     short loc_180014D87
0x180014d41  mov     [rsp+58h+var_30], eax
0x180014d45  mov     dword ptr [rsp+58h+var_38], 149h
0x180014d4d  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014d54  lea     r8, aElementAddpayl; "Element::AddPayload"
0x180014d5b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014d62  mov     ebx, 3
0x180014d67  mov     ecx, ebx
0x180014d69  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014d6e  lea     rdx, aFailedToAssemb_18; "    Failed to assemble destination path"
0x180014d75  mov     ecx, ebx
0x180014d77  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014d7c  nop
0x180014d7d  mov     rcx, rbp; void *
0x180014d80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014d85  jmp     short loc_180014D22
0x180014d87  mov     eax, 2
0x180014d8c  mul     rsi
0x180014d8f  cmovb   rax, r12
0x180014d93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d9a  mov     rcx, rax; unsigned __int64
0x180014d9d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014da2  mov     rdi, rax
0x180014da5  mov     [rsp+58h+arg_18], rax
0x180014daa  mov     r8, rbp; unsigned __int16 *
0x180014dad  mov     rdx, rsi; unsigned __int64
0x180014db0  mov     rcx, rax; unsigned __int16 *
0x180014db3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014db8  mov     esi, eax
0x180014dba  test    eax, eax
0x180014dbc  jns     short loc_180014E10
0x180014dbe  mov     [rsp+58h+var_30], eax
0x180014dc2  mov     dword ptr [rsp+58h+var_38], 14Eh
0x180014dca  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014dd1  lea     r8, aElementAddpayl; "Element::AddPayload"
0x180014dd8  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014ddf  mov     ebx, 3
0x180014de4  mov     ecx, ebx
0x180014de6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014deb  lea     rdx, aFailedToAssemb_2; "    Failed to assemble destination fold"...
0x180014df2  mov     ecx, ebx
0x180014df4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014df9  nop
0x180014dfa  test    rdi, rdi
0x180014dfd  jz      loc_180014F62
0x180014e03  mov     rcx, rdi; void *
0x180014e06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014e0b  jmp     loc_180014F62
0x180014e10  mov     edx, 5Ch ; '\'; Ch
0x180014e15  mov     rcx, rdi; Str
0x180014e18  call    cs:__imp_wcsrchr
0x180014e1e  mov     [rax], r15w
0x180014e22  mov     rax, [rbx+8]
0x180014e26  mov     rbx, [rax+10h]
0x180014e2a  mov     r9d, 2000002h
0x180014e30  mov     r8, rdi
0x180014e33  xor     edx, edx
0x180014e35  mov     rcx, rbx
0x180014e38  call    cs:__imp_WIMAddImagePath
0x180014e3e  mov     esi, 80070000h
0x180014e43  test    eax, eax
0x180014e45  jnz     loc_180014EDE
0x180014e4b  call    cs:__imp_GetLastError
0x180014e51  cmp     eax, 0B7h
0x180014e56  jz      loc_180014EDE
0x180014e5c  call    cs:__imp_GetLastError
0x180014e62  test    eax, eax
0x180014e64  jle     short loc_180014E6D
0x180014e66  movzx   eax, ax
0x180014e69  or      eax, esi
0x180014e6b  test    eax, eax
0x180014e6d  jns     short loc_180014EDE
0x180014e6f  call    cs:__imp_GetLastError
0x180014e75  test    eax, eax
0x180014e77  jle     short loc_180014E7E
0x180014e79  movzx   eax, ax
0x180014e7c  or      eax, esi
0x180014e7e  mov     [rsp+58h+var_30], eax
0x180014e82  mov     dword ptr [rsp+58h+var_38], 158h
0x180014e8a  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014e91  lea     r8, aElementAddpayl; "Element::AddPayload"
0x180014e98  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014e9f  mov     ebx, 3
0x180014ea4  mov     ecx, ebx
0x180014ea6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014eab  lea     rdx, aFailedToCreate_14; "    Failed to create destination folder"
0x180014eb2  mov     ecx, ebx
0x180014eb4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014eb9  call    cs:__imp_GetLastError
0x180014ebf  test    eax, eax
0x180014ec1  mov     ebx, eax
0x180014ec3  jle     short loc_180014ECA
0x180014ec5  movzx   ebx, ax
0x180014ec8  or      ebx, esi
0x180014eca  test    rdi, rdi
0x180014ecd  jz      short loc_180014ED7
0x180014ecf  mov     rcx, rdi; void *
0x180014ed2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014ed7  mov     esi, ebx
0x180014ed9  jmp     loc_180014F62
0x180014ede  mov     r9d, 2
0x180014ee4  mov     r8, rbp
0x180014ee7  mov     rdx, r14
0x180014eea  mov     rcx, rbx
0x180014eed  call    cs:__imp_WIMAddImagePath
0x180014ef3  test    eax, eax
0x180014ef5  jnz     short loc_180014F52
0x180014ef7  call    cs:__imp_GetLastError
0x180014efd  test    eax, eax
0x180014eff  jle     short loc_180014F08
0x180014f01  movzx   eax, ax
0x180014f04  or      eax, esi
0x180014f06  test    eax, eax
0x180014f08  jns     short loc_180014F52
0x180014f0a  call    cs:__imp_GetLastError
0x180014f10  test    eax, eax
0x180014f12  jle     short loc_180014F19
0x180014f14  movzx   eax, ax
0x180014f17  or      eax, esi
0x180014f19  mov     [rsp+58h+var_30], eax
0x180014f1d  mov     dword ptr [rsp+58h+var_38], 15Dh
0x180014f25  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014f2c  lea     r8, aElementAddpayl; "Element::AddPayload"
0x180014f33  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014f3a  mov     ebx, 3
0x180014f3f  mov     ecx, ebx
0x180014f41  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014f46  lea     rdx, aFailedToAddPay; "    Failed to add payload"
0x180014f4d  jmp     loc_180014EB2
0x180014f52  test    rdi, rdi
0x180014f55  jz      short loc_180014F5F
0x180014f57  mov     rcx, rdi; void *
0x180014f5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014f5f  mov     esi, r15d
0x180014f62  mov     rcx, rbp; void *
0x180014f65  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014f6a  mov     eax, esi
0x180014f6c  mov     rbx, [rsp+58h+arg_8]
0x180014f71  mov     rbp, [rsp+58h+arg_10]
0x180014f76  add     rsp, 30h
0x180014f7a  pop     r15
0x180014f7c  pop     r14
0x180014f7e  pop     r12
0x180014f80  pop     rdi
0x180014f81  pop     rsi
0x180014f82  retn
```
