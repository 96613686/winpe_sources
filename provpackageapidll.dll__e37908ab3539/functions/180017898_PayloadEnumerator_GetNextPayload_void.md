# PayloadEnumerator::GetNextPayload(void)

- ea: `0x180017898`
- end: `0x180017e6e`
- name: `?GetNextPayload@PayloadEnumerator@@AEAAJXZ`
- size: `1494`
- prototype: `__int64 __fastcall(PayloadEnumerator *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017e80`
- `0x180017f50`

## callees

- `0x180001510`
- `0x180001e66`
- `0x1800020a8`
- `0x1800020ec`
- `0x180002110`
- `0x180006014`
- `0x18000e328`
- `0x18000f040`
- `0x18000fc10`
- `0x18000fc8c`
- `0x180017898`
- `0x1800180ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b5c`
- `WIMGAPI!WIMCloseHandle` at `0x180017b67`
- `WIMGAPI!WIMCloseHandle` at `0x180017b67`

## string_xrefs

- `0x180017d54`: `    Failed to assemble search path string`
- `0x180017e09`: `    Failed to allocate _spCurrentDirectory.get()`
- `0x180017d92`: `    Failed to allocate _spFileSearchPath.get()`
- `0x180017bfa`: `    Failed to allocate pszDirectory`
- `0x180017bb3`: `    Failed to assemble directory path string`
- `0x180017dcb`: `    Failed to assemble current directory string`
- `0x180017d1b`: `    Failed to assemble search path string (asterisk)`
- `0x180017c8b`: `    Failed to allocate _spPayloadPath.get()`
- `0x180017cdb`: `    Failed to assemble payload path`

## pseudocode

```c
__int64 __fastcall PayloadEnumerator::GetNextPayload(PayloadEnumerator *this)
{
  __int64 *i; // r12
  int NextFile; // eax
  __int64 v4; // rdx
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rbp
  const struct std::nothrow_t *v10; // rdx
  unsigned int v11; // esi
  __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  __int64 v14; // r14
  unsigned __int64 v15; // r9
  const unsigned __int16 *v16; // rbx
  unsigned __int64 v17; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // kr00_8
  void *v23; // rax
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  unsigned __int16 *v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // rax
  void *v32; // rax
  const struct std::nothrow_t *v33; // rdx
  void *v34; // rcx
  WCHAR *v35; // rcx
  HRESULT v36; // eax
  ULONG v37; // r9d
  HRESULT v38; // eax
  __int64 v39; // rsi
  DWORD LastError; // ebx
  unsigned int v42; // edi
  __int64 v43; // rcx
  unsigned __int64 v44; // rbx
  unsigned __int64 v45; // rax
  void *v46; // rax
  const struct std::nothrow_t *v47; // rdx
  void *v48; // rcx
  WCHAR *v49; // rcx
  HRESULT v50; // eax
  __int64 v51; // [rsp+20h] [rbp-318h]
  __int64 v52; // [rsp+20h] [rbp-318h]
  _BYTE v53[44]; // [rsp+40h] [rbp-2F8h] BYREF
  WCHAR pszMore[314]; // [rsp+6Ch] [rbp-2CCh] BYREF

  memset_0(v53, 0, 0x2A0u);
  for ( i = (__int64 *)((char *)this + 16); ; *i = 0 )
  {
    while ( 1 )
    {
      NextFile = GetNextFile(*((_QWORD *)this + 1), (__int64 *)this + 2, *((_QWORD *)this + 5), (__int64)v53);
      if ( NextFile < 0 )
        break;
      v4 = -1;
      do
        ++v4;
      while ( pszMore[v4] );
      if ( (v53[0] & 0x10) == 0 )
      {
        v43 = -1;
        do
          ++v43;
        while ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * v43) );
        v44 = v43 + v4 + 6;
        v45 = 2 * v44;
        if ( !is_mul_ok(v44, 2u) )
          v45 = -1;
        v46 = operator new[](v45, (const struct std::nothrow_t *)&std::nothrow);
        v48 = (void *)*((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = v46;
        if ( v48 )
          operator delete(v48, v47);
        v49 = (WCHAR *)*((_QWORD *)this + 6);
        if ( !v49 )
        {
          v42 = -2147024882;
          LODWORD(v51) = 120;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "PayloadEnumerator::GetNextPayload",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
            v51,
            -2147024882);
          ProvPackageLog(3, L"    Failed to allocate _spPayloadPath.get()");
          return v42;
        }
        v50 = PathCchCombineEx(v49, v44, *((PCWSTR *)this + 4), pszMore, v51);
        v42 = v50;
        if ( v50 < 0 )
        {
          LODWORD(v52) = 124;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "PayloadEnumerator::GetNextPayload",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
            v52,
            v50);
          ProvPackageLog(3, L"    Failed to assemble payload path");
          return v42;
        }
        return 0;
      }
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * v5) );
      v6 = v5 + v4 + 2;
      v7 = 2 * v6;
      if ( !is_mul_ok(v6, 2u) )
        v7 = -1;
      v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( !v8 )
      {
        v42 = -2147024882;
        LODWORD(v51) = 64;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PayloadEnumerator::GetNextPayload",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
          v51,
          -2147024882);
        ProvPackageLog(3, L"    Failed to allocate pszDirectory");
        return v42;
      }
      v11 = PathCchCombineEx(v8, v6, *((PCWSTR *)this + 4), pszMore, v51);
      if ( (v11 & 0x80000000) != 0 )
      {
        operator delete(v9, v10);
        LODWORD(v51) = 70;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "PayloadEnumerator::GetNextPayload",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
          v51,
          v11);
        ProvPackageLog(3, L"    Failed to assemble directory path string");
        return v11;
      }
      if ( ((*((_BYTE *)this + 80) + (unsigned __int8)*((_QWORD *)this + 11)) & 1) == 0
        && *((_QWORD *)this + 9) <= (unsigned __int64)(*((_QWORD *)this + 11) + 2LL) >> 1 )
      {
        std::deque<unsigned short *>::_Growmap((char *)this + 56);
      }
      v12 = *((_QWORD *)this + 9);
      *((_QWORD *)this + 10) &= 2 * v12 - 1;
      v13 = *((_QWORD *)this + 11) + *((_QWORD *)this + 10);
      v14 = (v13 >> 1) & (v12 - 1);
      if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 8 * v14) )
        *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v14) = operator new(0x10u);
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 8 * ((v13 >> 1) & (*((_QWORD *)this + 9) - 1LL))) + 8 * (v13 & 1)) = v9;
      ++*((_QWORD *)this + 11);
    }
    if ( NextFile != -2147024637 || !*((_QWORD *)this + 11) )
    {
      LODWORD(v51) = 82;
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "PayloadEnumerator::GetNextPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        v51,
        L"No more payloads to enumerate");
      return 2147942659LL;
    }
    v15 = *((_QWORD *)this + 10);
    v16 = *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 8)
                                                 + 8 * ((*((_QWORD *)this + 9) - 1LL) & (v15 >> 1)))
                                     + 8 * (v15 & 1));
    v17 = 0;
    if ( (*((_QWORD *)this + 11))-- != 1 )
      v17 = v15 + 1;
    *((_QWORD *)this + 10) = v17;
    v19 = -1;
    do
      ++v19;
    while ( v16[v19] );
    v20 = v19 + 1;
    v22 = v19 + 1;
    v21 = 2 * (v19 + 1);
    if ( !is_mul_ok(v22, 2u) )
      v21 = -1;
    v23 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
    v25 = (void *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v23;
    if ( v25 )
      operator delete(v25, v24);
    v26 = (unsigned __int16 *)*((_QWORD *)this + 4);
    if ( !v26 )
      break;
    v27 = PathCchCanonicalizeEx(v26, v20, v16, PATHCCH_ALLOW_LONG_PATHS);
    v11 = v27;
    if ( v27 < 0 )
    {
      LODWORD(v51) = 96;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PayloadEnumerator::GetNextPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        v51,
        v27);
      ProvPackageLog(3, L"    Failed to assemble current directory string");
      return v11;
    }
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v28) );
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * v29) );
    v30 = v28 + v29 + 8;
    v31 = 2 * v30;
    if ( !is_mul_ok(v30, 2u) )
      v31 = -1;
    v32 = operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
    v34 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v32;
    if ( v34 )
      operator delete(v34, v33);
    v35 = (WCHAR *)*((_QWORD *)this + 5);
    if ( !v35 )
    {
      v42 = -2147024882;
      LODWORD(v51) = 102;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PayloadEnumerator::GetNextPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        v51,
        -2147024882);
      ProvPackageLog(3, L"    Failed to allocate _spFileSearchPath.get()");
      return v42;
    }
    v36 = PathCchCombineEx(v35, v30, *((PCWSTR *)this + 3), *((PCWSTR *)this + 4), v51);
    v11 = v36;
    if ( v36 < 0 )
    {
      LODWORD(v51) = 106;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PayloadEnumerator::GetNextPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        v51,
        v36);
      ProvPackageLog(3, L"    Failed to assemble search path string");
      return v11;
    }
    v38 = PathCchAppendEx(*((PWSTR *)this + 5), v30, L"*", v37);
    v11 = v38;
    if ( v38 < 0 )
    {
      LODWORD(v51) = 109;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PayloadEnumerator::GetNextPayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        v51,
        v38);
      ProvPackageLog(3, L"    Failed to assemble search path string (asterisk)");
      return v11;
    }
    v39 = *i;
    if ( (unsigned __int64)(*i - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      WIMCloseHandle(v39);
      SetLastError(LastError);
    }
  }
  v42 = -2147024882;
  LODWORD(v51) = 92;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "PayloadEnumerator::GetNextPayload",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
    v51,
    -2147024882);
  ProvPackageLog(3, L"    Failed to allocate _spCurrentDirectory.get()");
  return v42;
}

```

## disassembly

```asm
0x180017898  push    rbx
0x18001789a  push    rbp
0x18001789b  push    rsi
0x18001789c  push    rdi
0x18001789d  push    r12
0x18001789f  push    r13
0x1800178a1  push    r14
0x1800178a3  push    r15
0x1800178a5  sub     rsp, 2F8h
0x1800178ac  mov     rax, cs:__security_cookie
0x1800178b3  xor     rax, rsp
0x1800178b6  mov     [rsp+338h+var_58], rax
0x1800178be  mov     rdi, rcx
0x1800178c1  xor     edx, edx; Val
0x1800178c3  lea     rcx, [rsp+338h+var_2F8]; void *
0x1800178c8  mov     r8d, 2A0h; Size
0x1800178ce  call    memset_0
0x1800178d3  xor     r13d, r13d
0x1800178d6  lea     r12, [rdi+10h]
0x1800178da  mov     r14d, 2
0x1800178e0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800178e4  mov     r8, [rdi+28h]
0x1800178e8  lea     r9, [rsp+338h+var_2F8]
0x1800178ed  mov     rcx, [rdi+8]
0x1800178f1  mov     rdx, r12
0x1800178f4  call    ?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z; GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)
0x1800178f9  test    eax, eax
0x1800178fb  js      loc_180017A06
0x180017901  mov     eax, dword ptr [rsp+338h+var_2F8]
0x180017905  lea     rcx, [rsp+338h+pszMore]
0x18001790a  and     eax, 10h
0x18001790d  mov     rdx, rbp
0x180017910  inc     rdx
0x180017913  cmp     [rcx+rdx*2], r13w
0x180017918  jnz     short loc_180017910
0x18001791a  test    eax, eax
0x18001791c  jz      loc_180017C0F
0x180017922  mov     rcx, [rdi+20h]
0x180017926  mov     rax, rbp
0x180017929  inc     rax
0x18001792c  cmp     [rcx+rax*2], r13w
0x180017931  jnz     short loc_180017929
0x180017933  lea     rbx, [rdx+2]
0x180017937  add     rbx, rax
0x18001793a  mov     rax, r14
0x18001793d  mul     rbx
0x180017940  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017947  cmovb   rax, rbp
0x18001794b  mov     rcx, rax; unsigned __int64
0x18001794e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017953  mov     rbp, rax
0x180017956  test    rax, rax
0x180017959  jz      loc_180017BC8
0x18001795f  mov     r8, [rdi+20h]; pszPathIn
0x180017963  lea     r9, [rsp+338h+pszMore]; pszMore
0x180017968  mov     rdx, rbx; cchPathOut
0x18001796b  mov     rcx, rax; pszPathOut
0x18001796e  call    PathCchCombineEx
0x180017973  mov     esi, eax
0x180017975  test    eax, eax
0x180017977  js      loc_180017B7E
0x18001797d  mov     rcx, [rdi+58h]
0x180017981  mov     al, cl
0x180017983  add     al, [rdi+50h]
0x180017986  test    al, 1
0x180017988  jnz     short loc_1800179A0
0x18001798a  lea     rax, [rcx+2]
0x18001798e  shr     rax, 1
0x180017991  cmp     [rdi+48h], rax
0x180017995  ja      short loc_1800179A0
0x180017997  lea     rcx, [rdi+38h]
0x18001799b  call    ?_Growmap@?$deque@PEAGV?$allocator@PEAG@std@@@std@@AEAAX_K@Z; std::deque<ushort *>::_Growmap(unsigned __int64)
0x1800179a0  mov     rdx, [rdi+48h]
0x1800179a4  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x1800179ac  and     [rdi+50h], rax
0x1800179b0  lea     r14, [rdx-1]
0x1800179b4  mov     rsi, [rdi+50h]
0x1800179b8  add     rsi, [rdi+58h]
0x1800179bc  mov     rax, [rdi+40h]
0x1800179c0  mov     r15, rsi
0x1800179c3  shr     r15, 1
0x1800179c6  and     r14, r15
0x1800179c9  cmp     [rax+r14*8], r13
0x1800179cd  jnz     short loc_1800179E4
0x1800179cf  mov     ecx, 10h; Size
0x1800179d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800179d9  mov     rcx, rax
0x1800179dc  mov     rax, [rdi+40h]
0x1800179e0  mov     [rax+r14*8], rcx
0x1800179e4  mov     rcx, [rdi+48h]
0x1800179e8  and     esi, 1
0x1800179eb  mov     rax, [rdi+40h]
0x1800179ef  dec     rcx
0x1800179f2  and     rcx, r15
0x1800179f5  mov     rax, [rax+rcx*8]
0x1800179f9  mov     [rax+rsi*8], rbp
0x1800179fd  inc     qword ptr [rdi+58h]
0x180017a01  jmp     loc_1800178DA
0x180017a06  cmp     eax, 80070103h
0x180017a0b  jnz     loc_180017E15
0x180017a11  cmp     [rdi+58h], r13
0x180017a15  jz      loc_180017E15
0x180017a1b  mov     r9, [rdi+50h]
0x180017a1f  mov     rax, [rdi+48h]
0x180017a23  mov     rcx, r9
0x180017a26  dec     rax
0x180017a29  and     ecx, 1
0x180017a2c  mov     rdx, r9
0x180017a2f  shr     rdx, 1
0x180017a32  and     rdx, rax
0x180017a35  mov     rax, [rdi+40h]
0x180017a39  mov     rax, [rax+rdx*8]
0x180017a3d  mov     rbx, [rax+rcx*8]
0x180017a41  mov     rax, r13
0x180017a44  add     [rdi+58h], rbp
0x180017a48  jz      short loc_180017A4E
0x180017a4a  lea     rax, [r9+1]
0x180017a4e  mov     [rdi+50h], rax
0x180017a52  mov     rax, rbp
0x180017a55  inc     rax
0x180017a58  cmp     [rbx+rax*2], r13w
0x180017a5d  jnz     short loc_180017A55
0x180017a5f  lea     rsi, [rax+1]
0x180017a63  mov     rax, r14
0x180017a66  mul     rsi
0x180017a69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017a70  cmovb   rax, rbp
0x180017a74  mov     rcx, rax; unsigned __int64
0x180017a77  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017a7c  mov     rcx, [rdi+20h]; void *
0x180017a80  mov     [rdi+20h], rax
0x180017a84  test    rcx, rcx
0x180017a87  jz      short loc_180017A8E
0x180017a89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017a8e  mov     rcx, [rdi+20h]; unsigned __int16 *
0x180017a92  test    rcx, rcx
0x180017a95  jz      loc_180017DD7
0x180017a9b  mov     r9d, 1; enum PATHCCH_OPTIONS
0x180017aa1  mov     r8, rbx; unsigned __int16 *
0x180017aa4  mov     rdx, rsi; unsigned __int64
0x180017aa7  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x180017aac  mov     esi, eax
0x180017aae  test    eax, eax
0x180017ab0  js      loc_180017D9E
0x180017ab6  mov     rax, [rdi+18h]
0x180017aba  mov     rcx, rbp
0x180017abd  inc     rcx
0x180017ac0  cmp     [rax+rcx*2], r13w
0x180017ac5  jnz     short loc_180017ABD
0x180017ac7  mov     rdx, [rdi+20h]
0x180017acb  mov     rax, rbp
0x180017ace  inc     rax
0x180017ad1  cmp     [rdx+rax*2], r13w
0x180017ad6  jnz     short loc_180017ACE
0x180017ad8  lea     rbx, [rax+8]
0x180017adc  mov     rax, r14
0x180017adf  add     rbx, rcx
0x180017ae2  mul     rbx
0x180017ae5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017aec  cmovb   rax, rbp
0x180017af0  mov     rcx, rax; unsigned __int64
0x180017af3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017af8  mov     rcx, [rdi+28h]; void *
0x180017afc  mov     [rdi+28h], rax
0x180017b00  test    rcx, rcx
0x180017b03  jz      short loc_180017B0A
0x180017b05  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017b0a  mov     rcx, [rdi+28h]; pszPathOut
0x180017b0e  test    rcx, rcx
0x180017b11  jz      loc_180017D60
0x180017b17  mov     r9, [rdi+20h]; pszMore
0x180017b1b  mov     rdx, rbx; cchPathOut
0x180017b1e  mov     r8, [rdi+18h]; pszPathIn
0x180017b22  call    PathCchCombineEx
0x180017b27  mov     esi, eax
0x180017b29  test    eax, eax
0x180017b2b  js      loc_180017D27
0x180017b31  mov     rcx, [rdi+28h]; pszPath
0x180017b35  lea     r8, pszMore; "*"
0x180017b3c  mov     rdx, rbx; cchPath
0x180017b3f  call    PathCchAppendEx
0x180017b44  mov     esi, eax
0x180017b46  test    eax, eax
0x180017b48  js      loc_180017CEE
0x180017b4e  mov     rsi, [r12]
0x180017b52  lea     rax, [rsi-1]
0x180017b56  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017b5a  ja      short loc_180017B75
0x180017b5c  call    cs:__imp_GetLastError
0x180017b62  mov     rcx, rsi
0x180017b65  mov     ebx, eax
0x180017b67  call    cs:__imp_WIMCloseHandle
0x180017b6d  mov     ecx, ebx; dwErrCode
0x180017b6f  call    cs:__imp_SetLastError
0x180017b75  mov     [r12], r13
0x180017b79  jmp     loc_1800178E4
0x180017b7e  mov     rcx, rbp; void *
0x180017b81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017b86  mov     ebx, 3
0x180017b8b  mov     dword ptr [rsp+338h+var_310], esi
0x180017b8f  mov     ecx, ebx
0x180017b91  mov     dword ptr [rsp+338h+var_318], 46h ; 'F'
0x180017b99  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017ba0  lea     r8, aPayloadenumera; "PayloadEnumerator::GetNextPayload"
0x180017ba7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017bae  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017bb3  lea     rdx, aFailedToAssemb_17; "    Failed to assemble directory path s"...
0x180017bba  mov     ecx, ebx
0x180017bbc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017bc1  mov     eax, esi
0x180017bc3  jmp     loc_180017E4A
0x180017bc8  mov     edi, 8007000Eh
0x180017bcd  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017bd4  mov     ebx, 3
0x180017bd9  mov     dword ptr [rsp+338h+var_310], edi
0x180017bdd  mov     ecx, ebx
0x180017bdf  mov     dword ptr [rsp+338h+var_318], 40h ; '@'
0x180017be7  lea     r8, aPayloadenumera; "PayloadEnumerator::GetNextPayload"
0x180017bee  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017bf5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017bfa  lea     rdx, aFailedToAlloca_32; "    Failed to allocate pszDirectory"
0x180017c01  mov     ecx, ebx
0x180017c03  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017c08  mov     eax, edi
0x180017c0a  jmp     loc_180017E4A
0x180017c0f  mov     r8, [rdi+20h]
0x180017c13  mov     rcx, rbp
0x180017c16  inc     rcx
0x180017c19  cmp     [r8+rcx*2], r13w
0x180017c1e  jnz     short loc_180017C16
0x180017c20  lea     rbx, [rdx+6]
0x180017c24  mov     rax, r14
0x180017c27  add     rbx, rcx
0x180017c2a  mul     rbx
0x180017c2d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017c34  cmovb   rax, rbp
0x180017c38  mov     rcx, rax; unsigned __int64
0x180017c3b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017c40  mov     rcx, [rdi+30h]; void *
0x180017c44  mov     [rdi+30h], rax
0x180017c48  test    rcx, rcx
0x180017c4b  jz      short loc_180017C52
0x180017c4d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017c52  mov     rcx, [rdi+30h]; pszPathOut
0x180017c56  test    rcx, rcx
0x180017c59  jnz     short loc_180017C97
0x180017c5b  lea     ebx, [rcx+3]
0x180017c5e  mov     edi, 8007000Eh
0x180017c63  mov     dword ptr [rsp+338h+var_310], edi
0x180017c67  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017c6e  mov     ecx, ebx
0x180017c70  mov     dword ptr [rsp+338h+var_318], 78h ; 'x'
0x180017c78  lea     r8, aPayloadenumera; "PayloadEnumerator::GetNextPayload"
0x180017c7f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017c86  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017c8b  lea     rdx, aFailedToAlloca_24; "    Failed to allocate _spPayloadPath.g"...
0x180017c92  jmp     loc_180017C01
0x180017c97  mov     r8, [rdi+20h]; pszPathIn
0x180017c9b  lea     r9, [rsp+338h+pszMore]; pszMore
0x180017ca0  mov     rdx, rbx; cchPathOut
0x180017ca3  call    PathCchCombineEx
0x180017ca8  mov     edi, eax
0x180017caa  test    eax, eax
0x180017cac  jns     short loc_180017CE7
0x180017cae  mov     dword ptr [rsp+338h+var_310], eax
0x180017cb2  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017cb9  mov     ebx, 3
0x180017cbe  mov     dword ptr [rsp+338h+var_318], 7Ch ; '|'
0x180017cc6  mov     ecx, ebx
0x180017cc8  lea     r8, aPayloadenumera; "PayloadEnumerator::GetNextPayload"
0x180017ccf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017cd6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017cdb  lea     rdx, aFailedToAssemb_8; "    Failed to assemble payload path"
0x180017ce2  jmp     loc_180017C01
0x180017ce7  xor     eax, eax
0x180017ce9  jmp     loc_180017E4A
0x180017cee  mov     ebx, 3
0x180017cf3  mov     dword ptr [rsp+338h+var_310], esi
0x180017cf7  mov     ecx, ebx
0x180017cf9  mov     dword ptr [rsp+338h+var_318], 6Dh ; 'm'
0x180017d01  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017d08  lea     r8, aPayloadenumera; "PayloadEnumerator::GetNextPayload"
0x180017d0f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017d16  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017d1b  lea     rdx, aFailedToAssemb_19; "    Failed to assemble search path stri"...
0x180017d22  jmp     loc_180017BBA
0x180017d27  mov     ebx, 3
0x180017d2c  mov     dword ptr [rsp+338h+var_310], esi
0x180017d30  mov     ecx, ebx
0x180017d32  mov     dword ptr [rsp+338h+var_318], 6Ah ; 'j'
0x180017d3a  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017d41  lea     r8, aPayloadenumera; "PayloadEnumerator::GetNextPayload"
0x180017d48  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017d4f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017d54  lea     rdx, aFailedToAssemb_1; "    Failed to assemble search path stri"...
0x180017d5b  jmp     loc_180017BBA
0x180017d60  mov     edi, 8007000Eh
0x180017d65  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017d6c  mov     ebx, 3
0x180017d71  mov     dword ptr [rsp+338h+var_310], edi
  ... truncated ...
```
