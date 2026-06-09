# ElementEnumerator::GetNextElementType(void)

- ea: `0x18000d708`
- end: `0x18000da26`
- name: `?GetNextElementType@ElementEnumerator@@AEAAJXZ`
- size: `798`
- prototype: `__int64 __fastcall(ElementEnumerator *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d010`
- `0x18000d350`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180005424`
- `0x180006014`
- `0x18000d708`
- `0x18000e17c`
- `0x18000e328`
- `0x18000fc8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d97e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d96b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d96b`
- `WIMGAPI!WIMCloseHandle` at `0x18000d976`
- `WIMGAPI!WIMCloseHandle` at `0x18000d976`

## string_xrefs

- `0x18000d954`: `    Failed to assemble element search path`
- `0x18000d87b`: `    Failed to copy element type string`
- `0x18000d902`: `    Failed to allocate _spElementSearchPath.get()`

## pseudocode

```c
__int64 __fastcall ElementEnumerator::GetNextElementType(ElementEnumerator *this)
{
  int NextFile; // eax
  unsigned int v3; // esi
  __int64 v4; // rax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // kr00_8
  void *v8; // rax
  const struct std::nothrow_t *v9; // rdx
  void *v10; // rcx
  unsigned __int16 *v11; // rcx
  int v13; // eax
  __int64 v14; // rcx
  size_t v15; // rbx
  unsigned __int64 v16; // rax
  void *v17; // rax
  const struct std::nothrow_t *v18; // rdx
  void *v19; // rcx
  WCHAR *v20; // rcx
  HRESULT v21; // eax
  __int64 v22; // rsi
  DWORD LastError; // ebx
  ULONG v24; // [rsp+20h] [rbp-2D8h]
  int v25; // [rsp+20h] [rbp-2D8h]
  int v26; // [rsp+20h] [rbp-2D8h]
  int v27; // [rsp+20h] [rbp-2D8h]
  __int64 v28; // [rsp+20h] [rbp-2D8h]
  int v29; // [rsp+20h] [rbp-2D8h]
  int v30; // [rsp+20h] [rbp-2D8h]
  int v31; // [rsp+28h] [rbp-2D0h]
  int v32; // [rsp+28h] [rbp-2D0h]
  int v33; // [rsp+28h] [rbp-2D0h]
  HRESULT v34; // [rsp+28h] [rbp-2D0h]
  int v35; // [rsp+28h] [rbp-2D0h]
  _BYTE v36[44]; // [rsp+30h] [rbp-2C8h] BYREF
  unsigned __int16 v37[314]; // [rsp+5Ch] [rbp-29Ch] BYREF

  memset_0(v36, 0, 0x2A0u);
  do
  {
    NextFile = GetNextFile(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL), (char *)this + 16, L"*", v36);
    v3 = NextFile;
    if ( NextFile == -2147024878 || NextFile == -2147024893 || NextFile == -2147024637 )
    {
      v30 = 88;
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "ElementEnumerator::GetNextElementType",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
        v30,
        L"No more element types to enumerate");
      return 2147942659LL;
    }
    if ( NextFile < 0 )
    {
      v35 = NextFile;
      v29 = 91;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ElementEnumerator::GetNextElementType",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
        v29,
        v35);
      ProvPackageLog(3, L"    Failed to get next element type");
      return v3;
    }
  }
  while ( (v36[0] & 0x10) == 0 || !(unsigned int)GetElementTypeEnum(v37) );
  v4 = -1;
  do
    ++v4;
  while ( v37[v4] );
  v5 = v4 + 1;
  v7 = v4 + 1;
  v6 = 2 * (v4 + 1);
  if ( !is_mul_ok(v7, 2u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v10 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v8;
  if ( v10 )
    operator delete(v10, v9);
  v11 = (unsigned __int16 *)*((_QWORD *)this + 5);
  if ( !v11 )
  {
    v31 = -2147024882;
    v25 = 98;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElementType",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v25,
      v31);
    ProvPackageLog(3, L"    Failed to allocate _spElementType.get()");
    return 2147942414LL;
  }
  v13 = StringCchCopyW(v11, v5, v37);
  v3 = v13;
  if ( v13 < 0 )
  {
    v32 = v13;
    v26 = 101;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElementType",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v26,
      v32);
    ProvPackageLog(3, L"    Failed to copy element type string");
    return v3;
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(*((_QWORD *)this + 5) + 2 * v14) );
  v15 = v14 + 3;
  v16 = 2 * (v14 + 3);
  if ( !is_mul_ok(v14 + 3, 2u) )
    v16 = -1;
  v17 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  v19 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v17;
  if ( v19 )
    operator delete(v19, v18);
  v20 = (WCHAR *)*((_QWORD *)this + 7);
  if ( !v20 )
  {
    v33 = -2147024882;
    v27 = 106;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElementType",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v27,
      v33);
    ProvPackageLog(3, L"    Failed to allocate _spElementSearchPath.get()");
    return 2147942414LL;
  }
  v21 = PathCchCombineEx(v20, v15, *((PCWSTR *)this + 5), L"*", v24);
  v3 = v21;
  if ( v21 < 0 )
  {
    v34 = v21;
    LODWORD(v28) = 110;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::GetNextElementType",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v28,
      v34);
    ProvPackageLog(3, L"    Failed to assemble element search path");
    return v3;
  }
  v22 = *((_QWORD *)this + 3);
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    WIMCloseHandle(v22);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 3) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000d708  mov     [rsp+arg_8], rbx
0x18000d70d  mov     [rsp+arg_10], rbp
0x18000d712  push    rsi
0x18000d713  push    rdi
0x18000d714  push    r14
0x18000d716  sub     rsp, 2E0h
0x18000d71d  mov     rax, cs:__security_cookie
0x18000d724  xor     rax, rsp
0x18000d727  mov     [rsp+2F8h+var_28], rax
0x18000d72f  mov     rdi, rcx
0x18000d732  xor     edx, edx; Val
0x18000d734  lea     rcx, [rsp+2F8h+var_2C8]; void *
0x18000d739  mov     r8d, 2A0h; Size
0x18000d73f  call    memset_0
0x18000d744  xor     ebp, ebp
0x18000d746  mov     r14d, 80070103h
0x18000d74c  mov     rcx, [rdi+8]
0x18000d750  lea     r9, [rsp+2F8h+var_2C8]
0x18000d755  lea     r8, pszMore; "*"
0x18000d75c  lea     rdx, [rdi+10h]
0x18000d760  mov     rcx, [rcx+10h]
0x18000d764  call    ?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z; GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)
0x18000d769  mov     esi, eax
0x18000d76b  cmp     eax, 80070012h
0x18000d770  jz      loc_18000D9CB
0x18000d776  cmp     eax, 80070003h
0x18000d77b  jz      loc_18000D9CB
0x18000d781  cmp     eax, r14d
0x18000d784  jz      loc_18000D9CB
0x18000d78a  test    eax, eax
0x18000d78c  js      loc_18000D98C
0x18000d792  test    [rsp+2F8h+var_2C8], 10h
0x18000d797  jz      short loc_18000D74C
0x18000d799  lea     rcx, [rsp+2F8h+var_29C]
0x18000d79e  call    ?GetElementTypeEnum@@YA?AW4_PROVISIONINGELEMENTTYPE@@PEBG@Z; GetElementTypeEnum(ushort const *)
0x18000d7a3  test    eax, eax
0x18000d7a5  jz      short loc_18000D74C
0x18000d7a7  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000d7ab  lea     rcx, [rsp+2F8h+var_29C]
0x18000d7b0  mov     rax, r14
0x18000d7b3  inc     rax
0x18000d7b6  cmp     [rcx+rax*2], bp
0x18000d7ba  jnz     short loc_18000D7B3
0x18000d7bc  lea     rbx, [rax+1]
0x18000d7c0  mov     eax, 2
0x18000d7c5  mul     rbx
0x18000d7c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d7cf  cmovb   rax, r14
0x18000d7d3  mov     rcx, rax; unsigned __int64
0x18000d7d6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d7db  mov     rcx, [rdi+28h]; void *
0x18000d7df  mov     [rdi+28h], rax
0x18000d7e3  test    rcx, rcx
0x18000d7e6  jz      short loc_18000D7ED
0x18000d7e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d7ed  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18000d7f1  test    rcx, rcx
0x18000d7f4  jnz     short loc_18000D83B
0x18000d7f6  lea     ebx, [rcx+3]
0x18000d7f9  mov     edi, 8007000Eh
0x18000d7fe  mov     dword ptr [rsp+2F8h+var_2D0], edi
0x18000d802  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d809  mov     ecx, ebx
0x18000d80b  mov     dword ptr [rsp+2F8h+var_2D8], 62h ; 'b'
0x18000d813  lea     r8, aElementenumera; "ElementEnumerator::GetNextElementType"
0x18000d81a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d821  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d826  lea     rdx, aFailedToAlloca_41; "    Failed to allocate _spElementType.g"...
0x18000d82d  mov     ecx, ebx
0x18000d82f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d834  mov     eax, edi
0x18000d836  jmp     loc_18000D9FE
0x18000d83b  lea     r8, [rsp+2F8h+var_29C]; unsigned __int16 *
0x18000d840  mov     rdx, rbx; unsigned __int64
0x18000d843  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d848  mov     esi, eax
0x18000d84a  test    eax, eax
0x18000d84c  jns     short loc_18000D887
0x18000d84e  mov     dword ptr [rsp+2F8h+var_2D0], eax
0x18000d852  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d859  mov     ebx, 3
0x18000d85e  mov     dword ptr [rsp+2F8h+var_2D8], 65h ; 'e'
0x18000d866  mov     ecx, ebx
0x18000d868  lea     r8, aElementenumera; "ElementEnumerator::GetNextElementType"
0x18000d86f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d876  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d87b  lea     rdx, aFailedToCopyEl; "    Failed to copy element type string"
0x18000d882  jmp     loc_18000D9C0
0x18000d887  mov     r8, [rdi+28h]
0x18000d88b  mov     rcx, r14
0x18000d88e  inc     rcx
0x18000d891  cmp     [r8+rcx*2], bp
0x18000d896  jnz     short loc_18000D88E
0x18000d898  lea     rbx, [rcx+3]
0x18000d89c  mov     eax, 2
0x18000d8a1  mul     rbx
0x18000d8a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d8ab  cmovb   rax, r14
0x18000d8af  mov     rcx, rax; unsigned __int64
0x18000d8b2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d8b7  mov     rcx, [rdi+38h]; void *
0x18000d8bb  mov     [rdi+38h], rax
0x18000d8bf  test    rcx, rcx
0x18000d8c2  jz      short loc_18000D8C9
0x18000d8c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d8c9  mov     rcx, [rdi+38h]; pszPathOut
0x18000d8cd  test    rcx, rcx
0x18000d8d0  jnz     short loc_18000D90E
0x18000d8d2  lea     ebx, [rcx+3]
0x18000d8d5  mov     edi, 8007000Eh
0x18000d8da  mov     dword ptr [rsp+2F8h+var_2D0], edi
0x18000d8de  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d8e5  mov     ecx, ebx
0x18000d8e7  mov     dword ptr [rsp+2F8h+var_2D8], 6Ah ; 'j'
0x18000d8ef  lea     r8, aElementenumera; "ElementEnumerator::GetNextElementType"
0x18000d8f6  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d8fd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d902  lea     rdx, aFailedToAlloca_36; "    Failed to allocate _spElementSearch"...
0x18000d909  jmp     loc_18000D82D
0x18000d90e  mov     r8, [rdi+28h]; pszPathIn
0x18000d912  lea     r9, pszMore; "*"
0x18000d919  mov     rdx, rbx; cchPathOut
0x18000d91c  call    PathCchCombineEx
0x18000d921  mov     esi, eax
0x18000d923  test    eax, eax
0x18000d925  jns     short loc_18000D95D
0x18000d927  mov     dword ptr [rsp+2F8h+var_2D0], eax
0x18000d92b  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d932  mov     ebx, 3
0x18000d937  mov     dword ptr [rsp+2F8h+var_2D8], 6Eh ; 'n'
0x18000d93f  mov     ecx, ebx
0x18000d941  lea     r8, aElementenumera; "ElementEnumerator::GetNextElementType"
0x18000d948  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d94f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d954  lea     rdx, aFailedToAssemb_5; "    Failed to assemble element search p"...
0x18000d95b  jmp     short loc_18000D9C0
0x18000d95d  mov     rsi, [rdi+18h]
0x18000d961  lea     rax, [rsi-1]
0x18000d965  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d969  ja      short loc_18000D984
0x18000d96b  call    cs:__imp_GetLastError
0x18000d971  mov     rcx, rsi
0x18000d974  mov     ebx, eax
0x18000d976  call    cs:__imp_WIMCloseHandle
0x18000d97c  mov     ecx, ebx; dwErrCode
0x18000d97e  call    cs:__imp_SetLastError
0x18000d984  mov     [rdi+18h], rbp
0x18000d988  xor     eax, eax
0x18000d98a  jmp     short loc_18000D9FE
0x18000d98c  mov     ebx, 3
0x18000d991  mov     dword ptr [rsp+2F8h+var_2D0], esi
0x18000d995  mov     ecx, ebx
0x18000d997  mov     dword ptr [rsp+2F8h+var_2D8], 5Bh ; '['
0x18000d99f  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d9a6  lea     r8, aElementenumera; "ElementEnumerator::GetNextElementType"
0x18000d9ad  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d9b4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d9b9  lea     rdx, aFailedToGetNex_4; "    Failed to get next element type"
0x18000d9c0  mov     ecx, ebx
0x18000d9c2  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d9c7  mov     eax, esi
0x18000d9c9  jmp     short loc_18000D9FE
0x18000d9cb  lea     rcx, aNoMoreElementT; "No more element types to enumerate"
0x18000d9d2  mov     [rsp+2F8h+var_2D0], rcx
0x18000d9d7  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d9de  xor     ecx, ecx
0x18000d9e0  mov     dword ptr [rsp+2F8h+var_2D8], 58h ; 'X'
0x18000d9e8  lea     r8, aElementenumera; "ElementEnumerator::GetNextElementType"
0x18000d9ef  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x18000d9f6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d9fb  mov     eax, r14d
0x18000d9fe  mov     rcx, [rsp+2F8h+var_28]
0x18000da06  xor     rcx, rsp; StackCookie
0x18000da09  call    __security_check_cookie
0x18000da0e  lea     r11, [rsp+2F8h+var_18]
0x18000da16  mov     rbx, [r11+28h]
0x18000da1a  mov     rbp, [r11+30h]
0x18000da1e  mov     rsp, r11
0x18000da21  pop     r14
0x18000da23  pop     rdi
0x18000da24  pop     rsi
0x18000da25  retn
```
