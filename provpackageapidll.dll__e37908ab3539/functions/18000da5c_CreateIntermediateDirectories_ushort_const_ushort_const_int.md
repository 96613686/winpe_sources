# CreateIntermediateDirectories(ushort const *,ushort const *,int)

- ea: `0x18000da5c`
- end: `0x18000e057`
- name: `?CreateIntermediateDirectories@@YAJPEBG0H@Z`
- size: `1531`
- prototype: `signed int __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180015930`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180005360`
- `0x180005424`
- `0x180006014`
- `0x18000da5c`
- `0x18000f040`
- `0x18000fc8c`
- `0x180018434`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000dc44`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000dd70`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000de67`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000dc44`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000dd70`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000de67`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000dc15`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000dc15`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dd54`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000dd54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dacd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dacd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df52`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000de3b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000de3b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000da73`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000da73`

## string_xrefs

- `0x18000daa5`: `CreateIntermediateDirectories`
- `0x18000db01`: `CreateIntermediateDirectories`
- `0x18000db87`: `CreateIntermediateDirectories`
- `0x18000dbe0`: `CreateIntermediateDirectories`
- `0x18000dcae`: `CreateIntermediateDirectories`
- `0x18000dd07`: `CreateIntermediateDirectories`
- `0x18000dec4`: `CreateIntermediateDirectories`
- `0x18000df2a`: `CreateIntermediateDirectories`
- `0x18000df8f`: `CreateIntermediateDirectories`
- `0x18000dfcd`: `CreateIntermediateDirectories`
- `0x18000e00f`: `CreateIntermediateDirectories`
- `0x18000dabf`: `    Existing path is invalid`
- `0x18000db1b`: `    Existing path is not a directory`
- `0x18000db9f`: `    Failed to allocate spNewPath.get()`
- `0x18000dbfa`: `    Failed to assemble new path string`
- `0x18000dd21`: `    Failed to canonicalize intermediate path string`
- `0x18000dfa9`: `    Failed to assemble intermediate path string`
- `0x18000e029`: `    Failed to assemble intermediate path string`
- `0x18000dede`: `    Failed to copy long intermediate path string`
- `0x18000df44`: `    Failed to create directory`

## pseudocode

```c
signed int __fastcall CreateIntermediateDirectories(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  signed int result; // eax
  int v7; // ebx
  __int64 v8; // rax
  int v9; // ebx
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // kr00_8
  unsigned __int16 *v13; // rax
  wchar_t *v14; // r12
  int v15; // eax
  unsigned int v16; // esi
  const struct std::nothrow_t *v17; // rdx
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // r13
  unsigned __int64 v23; // rax
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rsi
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  int v28; // ebp
  const struct std::nothrow_t *v29; // rdx
  unsigned __int16 *v30; // rbp
  HRESULT v31; // eax
  HRESULT v32; // r14d
  __int64 v33; // rax
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // kr10_8
  const struct std::nothrow_t *v37; // rdx
  unsigned __int16 *v38; // r14
  unsigned __int16 *v39; // rcx
  int v40; // eax
  int v41; // r15d
  int v42; // eax
  const struct std::nothrow_t *v43; // rdx
  const struct std::nothrow_t *v44; // rdx
  signed int v45; // eax
  signed int v46; // eax
  const struct std::nothrow_t *v47; // rdx
  unsigned int v48; // edi
  const struct std::nothrow_t *v49; // rdx
  const struct std::nothrow_t *v50; // rdx
  __int64 v51; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v52; // [rsp+30h] [rbp-68h]
  unsigned __int16 *v53; // [rsp+38h] [rbp-60h]
  unsigned __int16 *v54; // [rsp+40h] [rbp-58h]
  wchar_t *Context; // [rsp+B8h] [rbp+20h] BYREF

  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "CreateIntermediateDirectories",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      49,
      LastError);
    ProvPackageLog(3, L"    Existing path is invalid");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v7 = -2147024809;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "CreateIntermediateDirectories",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      54,
      -2147024809);
    ProvPackageLog(3, L"    Existing path is not a directory");
    return v7;
  }
  v8 = -1;
  v9 = 0;
  do
    ++v8;
  while ( a2[v8] );
  v10 = v8 + 1;
  v12 = v8 + 1;
  v11 = 2 * (v8 + 1);
  if ( !is_mul_ok(v12, 2u) )
    v11 = -1;
  v13 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  v53 = v13;
  if ( !v13 )
  {
    v7 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "CreateIntermediateDirectories",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      60,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate spNewPath.get()");
    return v7;
  }
  v15 = PathCchCanonicalizeEx(v13, v10, a2, PATHCCH_ALLOW_LONG_PATHS);
  v16 = v15;
  if ( v15 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "CreateIntermediateDirectories",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      63,
      v15);
    ProvPackageLog(3, L"    Failed to assemble new path string");
    goto LABEL_51;
  }
  v18 = wcsrchr(v14, 0x5Cu);
  if ( v18 )
    *v18 = 0;
  else
    *v14 = 0;
  Context = 0;
  v19 = wcstok_s(v14, L"\\", &Context);
  v20 = -1;
  do
    ++v20;
  while ( a2[v20] );
  v21 = -1;
  do
    ++v21;
  while ( a1[v21] );
  v22 = v21 + v20 + 6;
  v23 = 2 * v22;
  if ( !is_mul_ok(v22, 2u) )
    v23 = -1;
  v24 = (unsigned __int16 *)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
  v25 = v24;
  v54 = v24;
  if ( v24 )
  {
    v26 = PathCchCanonicalizeEx(v24, v22, a1, PATHCCH_ALLOW_LONG_PATHS);
    v28 = v26;
    if ( v26 < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "CreateIntermediateDirectories",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
        88,
        v26);
      ProvPackageLog(3, L"    Failed to canonicalize intermediate path string");
      operator delete(v25, v29);
      v16 = v28;
      goto LABEL_51;
    }
    v30 = 0;
    v52 = 0;
    while ( 1 )
    {
      if ( !v19 )
      {
        if ( v30 )
          operator delete(v30, v27);
        goto LABEL_49;
      }
      if ( !wcschr(v19, 0x3Fu) )
      {
        v31 = PathCchCombineEx(v25, v22, v25, v19, v51);
        v32 = v31;
        if ( v31 < 0 )
        {
          LODWORD(v51) = 102;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "CreateIntermediateDirectories",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
            v51,
            v31,
            v52,
            v53,
            v54);
          ProvPackageLog(3, L"    Failed to assemble intermediate path string");
          if ( v30 )
            operator delete(v30, v50);
          operator delete(v25, v50);
          v16 = v32;
          goto LABEL_51;
        }
        v33 = -1;
        do
          ++v33;
        while ( v25[v33] );
        v34 = v33 + 5;
        v36 = v33 + 5;
        v35 = 2 * (v33 + 5);
        if ( !is_mul_ok(v36, 2u) )
          v35 = -1;
        v38 = (unsigned __int16 *)operator new[](v35, (const struct std::nothrow_t *)&std::nothrow);
        v39 = v30;
        v30 = v38;
        v52 = v38;
        if ( v39 )
          operator delete(v39, v37);
        if ( !v38 )
        {
          v9 = -2147024882;
          LODWORD(v51) = 107;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "CreateIntermediateDirectories",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
            v51,
            -2147024882,
            0,
            v53,
            v54);
          ProvPackageLog(3, L"    Failed to allocate spLongIntermediate.get()");
LABEL_49:
          operator delete(v25, v27);
          goto LABEL_50;
        }
        *v38 = 0;
        if ( wcsncmp_0(v25, L"\\\\?\\", 4u) )
        {
          v40 = StringCchCopyW(v38, v34, L"\\\\?\\");
          v41 = v40;
          if ( v40 < 0 )
          {
            LODWORD(v51) = 117;
            ProvPackageLog(
              3,
              L"%hs (%hs:%d) - 0x%08x:",
              "CreateIntermediateDirectories",
              "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
              v51,
              v40,
              v38,
              v53,
              v54);
            ProvPackageLog(3, L"    Failed to copy long intermediate path string");
LABEL_54:
            operator delete(v38, v43);
            operator delete(v25, v44);
            v16 = v41;
            goto LABEL_51;
          }
        }
        v42 = StringCchCatW(v38, v34, v25);
        v41 = v42;
        if ( v42 < 0 )
        {
          LODWORD(v51) = 121;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "CreateIntermediateDirectories",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
            v51,
            v42,
            v38,
            v53,
            v54);
          ProvPackageLog(3, L"    Failed to assemble intermediate path string");
          goto LABEL_54;
        }
        if ( !CreateDirectoryW(v38, 0) && GetLastError() != 183 )
        {
          v45 = GetLastError();
          if ( v45 > 0 )
            v45 = (unsigned __int16)v45 | 0x80070000;
          LODWORD(v51) = 127;
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "CreateIntermediateDirectories",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
            v51,
            v45,
            v38,
            v53,
            v54);
          ProvPackageLog(3, L"    Failed to create directory");
          v46 = GetLastError();
          v48 = v46;
          if ( v46 > 0 )
            v48 = (unsigned __int16)v46 | 0x80070000;
          operator delete(v38, v47);
          operator delete(v25, v49);
          v16 = v48;
          goto LABEL_51;
        }
      }
      v19 = wcstok_s(0, L"\\", &Context);
    }
  }
  v9 = -2147024882;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "CreateIntermediateDirectories",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
    85,
    -2147024882);
  ProvPackageLog(3, L"    Failed to allocate spIntermediate.get()");
LABEL_50:
  v16 = v9;
LABEL_51:
  operator delete(v14, v17);
  return v16;
}

```

## disassembly

```asm
0x18000da5c  push    rbx
0x18000da5e  push    rbp
0x18000da5f  push    rsi
0x18000da60  push    rdi
0x18000da61  push    r12
0x18000da63  push    r13
0x18000da65  push    r14
0x18000da67  push    r15
0x18000da69  sub     rsp, 58h
0x18000da6d  mov     rbp, rdx
0x18000da70  mov     r14, rcx
0x18000da73  call    cs:__imp_GetFileAttributesW
0x18000da79  cmp     eax, 0FFFFFFFFh
0x18000da7c  jnz     short loc_18000DAE5
0x18000da7e  call    cs:__imp_GetLastError
0x18000da84  mov     ebp, 80070000h
0x18000da89  test    eax, eax
0x18000da8b  jle     short loc_18000DA92
0x18000da8d  movzx   eax, ax
0x18000da90  or      eax, ebp
0x18000da92  mov     [rsp+98h+var_70], eax
0x18000da96  mov     dword ptr [rsp+98h+var_78], 31h ; '1'
0x18000da9e  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000daa5  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000daac  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000dab3  mov     edi, 3
0x18000dab8  mov     ecx, edi
0x18000daba  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dabf  lea     rdx, aExistingPathIs; "    Existing path is invalid"
0x18000dac6  mov     ecx, edi
0x18000dac8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dacd  call    cs:__imp_GetLastError
0x18000dad3  test    eax, eax
0x18000dad5  jle     loc_18000DE9F
0x18000dadb  movzx   eax, ax
0x18000dade  or      eax, ebp
0x18000dae0  jmp     loc_18000DE9F
0x18000dae5  test    al, 10h
0x18000dae7  jnz     short loc_18000DB30
0x18000dae9  mov     ebx, 80070057h
0x18000daee  mov     [rsp+98h+var_70], ebx
0x18000daf2  mov     dword ptr [rsp+98h+var_78], 36h ; '6'
0x18000dafa  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000db01  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000db08  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000db0f  mov     edi, 3
0x18000db14  mov     ecx, edi
0x18000db16  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000db1b  lea     rdx, aExistingPathIs_0; "    Existing path is not a directory"
0x18000db22  mov     ecx, edi
0x18000db24  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000db29  mov     eax, ebx
0x18000db2b  jmp     loc_18000DE9F
0x18000db30  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000db34  mov     rax, r15
0x18000db37  xor     ebx, ebx
0x18000db39  inc     rax
0x18000db3c  cmp     [rbp+rax*2+0], bx
0x18000db41  jnz     short loc_18000DB39
0x18000db43  lea     rdi, [rax+1]
0x18000db47  mov     eax, 2
0x18000db4c  mul     rdi
0x18000db4f  cmovb   rax, r15
0x18000db53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000db5a  mov     rcx, rax; unsigned __int64
0x18000db5d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000db62  mov     r12, rax
0x18000db65  mov     [rsp+98h+var_60], rax
0x18000db6a  test    rax, rax
0x18000db6d  jnz     short loc_18000DBB3
0x18000db6f  mov     ebx, 8007000Eh
0x18000db74  mov     [rsp+98h+var_70], ebx
0x18000db78  mov     dword ptr [rsp+98h+var_78], 3Ch ; '<'
0x18000db80  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000db87  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000db8e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000db95  lea     edi, [rax+3]
0x18000db98  mov     ecx, edi
0x18000db9a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000db9f  lea     rdx, aFailedToAlloca_19; "    Failed to allocate spNewPath.get()"
0x18000dba6  mov     ecx, edi
0x18000dba8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dbad  nop
0x18000dbae  jmp     loc_18000DB29
0x18000dbb3  mov     r9d, 1; enum PATHCCH_OPTIONS
0x18000dbb9  mov     r8, rbp; unsigned __int16 *
0x18000dbbc  mov     rdx, rdi; unsigned __int64
0x18000dbbf  mov     rcx, r12; unsigned __int16 *
0x18000dbc2  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18000dbc7  mov     esi, eax
0x18000dbc9  test    eax, eax
0x18000dbcb  jns     short loc_18000DC0D
0x18000dbcd  mov     [rsp+98h+var_70], eax
0x18000dbd1  mov     dword ptr [rsp+98h+var_78], 3Fh ; '?'
0x18000dbd9  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000dbe0  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000dbe7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000dbee  mov     edi, 3
0x18000dbf3  mov     ecx, edi
0x18000dbf5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dbfa  lea     rdx, aFailedToAssemb_7; "    Failed to assemble new path string"
0x18000dc01  mov     ecx, edi
0x18000dc03  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dc08  jmp     loc_18000DE95
0x18000dc0d  mov     edx, 5Ch ; '\'; Ch
0x18000dc12  mov     rcx, r12; Str
0x18000dc15  call    cs:__imp_wcsrchr
0x18000dc1b  test    rax, rax
0x18000dc1e  jnz     short loc_18000DC27
0x18000dc20  mov     [r12], bx
0x18000dc25  jmp     short loc_18000DC2A
0x18000dc27  mov     [rax], bx
0x18000dc2a  mov     [rsp+98h+Context], rbx
0x18000dc32  lea     r8, [rsp+98h+Context]; Context
0x18000dc3a  lea     rdx, Delimiter; "\\"
0x18000dc41  mov     rcx, r12; String
0x18000dc44  call    cs:__imp_wcstok_s
0x18000dc4a  mov     rdi, rax
0x18000dc4d  mov     rcx, r15
0x18000dc50  inc     rcx
0x18000dc53  cmp     [rbp+rcx*2+0], bx
0x18000dc58  jnz     short loc_18000DC50
0x18000dc5a  mov     rax, r15
0x18000dc5d  inc     rax
0x18000dc60  cmp     [r14+rax*2], bx
0x18000dc65  jnz     short loc_18000DC5D
0x18000dc67  lea     r13, [rcx+6]
0x18000dc6b  add     r13, rax
0x18000dc6e  mov     eax, 2
0x18000dc73  mul     r13
0x18000dc76  cmovb   rax, r15
0x18000dc7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dc81  mov     rcx, rax; unsigned __int64
0x18000dc84  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000dc89  mov     rsi, rax
0x18000dc8c  mov     [rsp+98h+var_58], rax
0x18000dc91  test    rax, rax
0x18000dc94  jnz     short loc_18000DCDA
0x18000dc96  mov     ebx, 8007000Eh
0x18000dc9b  mov     [rsp+98h+var_70], ebx
0x18000dc9f  mov     dword ptr [rsp+98h+var_78], 55h ; 'U'
0x18000dca7  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000dcae  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000dcb5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000dcbc  lea     edi, [rax+3]
0x18000dcbf  mov     ecx, edi
0x18000dcc1  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dcc6  lea     rdx, aFailedToAlloca_9; "    Failed to allocate spIntermediate.g"...
0x18000dccd  mov     ecx, edi
0x18000dccf  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dcd4  nop
0x18000dcd5  jmp     loc_18000DE93
0x18000dcda  mov     r9d, 1; enum PATHCCH_OPTIONS
0x18000dce0  mov     r8, r14; unsigned __int16 *
0x18000dce3  mov     rdx, r13; unsigned __int64
0x18000dce6  mov     rcx, rsi; unsigned __int16 *
0x18000dce9  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18000dcee  mov     ebp, eax
0x18000dcf0  test    eax, eax
0x18000dcf2  jns     short loc_18000DD3F
0x18000dcf4  mov     [rsp+98h+var_70], eax
0x18000dcf8  mov     dword ptr [rsp+98h+var_78], 58h ; 'X'
0x18000dd00  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000dd07  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000dd0e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000dd15  mov     edi, 3
0x18000dd1a  mov     ecx, edi
0x18000dd1c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dd21  lea     rdx, aFailedToCanoni; "    Failed to canonicalize intermediate"...
0x18000dd28  mov     ecx, edi
0x18000dd2a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dd2f  nop
0x18000dd30  mov     rcx, rsi; void *
0x18000dd33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000dd38  mov     esi, ebp
0x18000dd3a  jmp     loc_18000DE95
0x18000dd3f  mov     rbp, rbx
0x18000dd42  mov     [rsp+98h+var_68], rbx
0x18000dd47  jmp     loc_18000DE74
0x18000dd4c  mov     edx, 3Fh ; '?'; Ch
0x18000dd51  mov     rcx, rdi; Str
0x18000dd54  call    cs:__imp_wcschr
0x18000dd5a  test    rax, rax
0x18000dd5d  jz      short loc_18000DD7B
0x18000dd5f  lea     r8, [rsp+98h+Context]; Context
0x18000dd67  lea     rdx, Delimiter; "\\"
0x18000dd6e  xor     ecx, ecx; String
0x18000dd70  call    cs:__imp_wcstok_s
0x18000dd76  jmp     loc_18000DE71
0x18000dd7b  mov     r9, rdi; pszMore
0x18000dd7e  mov     r8, rsi; pszPathIn
0x18000dd81  mov     rdx, r13; cchPathOut
0x18000dd84  mov     rcx, rsi; pszPathOut
0x18000dd87  call    PathCchCombineEx
0x18000dd8c  mov     r14d, eax
0x18000dd8f  test    eax, eax
0x18000dd91  js      loc_18000DFFB
0x18000dd97  mov     rax, r15
0x18000dd9a  inc     rax
0x18000dd9d  cmp     [rsi+rax*2], bx
0x18000dda1  jnz     short loc_18000DD9A
0x18000dda3  lea     rdi, [rax+5]
0x18000dda7  mov     eax, 2
0x18000ddac  mul     rdi
0x18000ddaf  cmovb   rax, r15
0x18000ddb3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ddba  mov     rcx, rax; unsigned __int64
0x18000ddbd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ddc2  mov     r14, rax
0x18000ddc5  mov     rcx, rbp; void *
0x18000ddc8  mov     rbp, rax
0x18000ddcb  mov     [rsp+98h+var_68], rax
0x18000ddd0  test    rcx, rcx
0x18000ddd3  jz      short loc_18000DDDA
0x18000ddd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ddda  test    r14, r14
0x18000dddd  jz      loc_18000DFB5
0x18000dde3  mov     [r14], bx
0x18000dde7  mov     r8d, 4; MaxCount
0x18000dded  lea     rdx, String2; "\\\\?\\"
0x18000ddf4  mov     rcx, rsi; String1
0x18000ddf7  call    wcsncmp_0
0x18000ddfc  test    eax, eax
0x18000ddfe  jz      short loc_18000DE1D
0x18000de00  lea     r8, String2; "\\\\?\\"
0x18000de07  mov     rdx, rdi; unsigned __int64
0x18000de0a  mov     rcx, r14; unsigned __int16 *
0x18000de0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000de12  mov     r15d, eax
0x18000de15  test    eax, eax
0x18000de17  js      loc_18000DEB0
0x18000de1d  mov     r8, rsi; unsigned __int16 *
0x18000de20  mov     rdx, rdi; unsigned __int64
0x18000de23  mov     rcx, r14; unsigned __int16 *
0x18000de26  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000de2b  mov     r15d, eax
0x18000de2e  test    eax, eax
0x18000de30  js      loc_18000DF7B
0x18000de36  xor     edx, edx; lpSecurityAttributes
0x18000de38  mov     rcx, r14; lpPathName
0x18000de3b  call    cs:__imp_CreateDirectoryW
0x18000de41  test    eax, eax
0x18000de43  jnz     short loc_18000DE56
0x18000de45  call    cs:__imp_GetLastError
0x18000de4b  cmp     eax, 0B7h
0x18000de50  jnz     loc_18000DF03
0x18000de56  lea     r8, [rsp+98h+Context]; Context
0x18000de5e  lea     rdx, Delimiter; "\\"
0x18000de65  xor     ecx, ecx; String
0x18000de67  call    cs:__imp_wcstok_s
0x18000de6d  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000de71  mov     rdi, rax
0x18000de74  test    rdi, rdi
0x18000de77  jnz     loc_18000DD4C
0x18000de7d  test    rbp, rbp
0x18000de80  jz      short loc_18000DE8B
0x18000de82  mov     rcx, rbp; void *
0x18000de85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000de8a  nop
0x18000de8b  mov     rcx, rsi; void *
0x18000de8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000de93  mov     esi, ebx
0x18000de95  mov     rcx, r12; void *
0x18000de98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000de9d  mov     eax, esi
0x18000de9f  add     rsp, 58h
0x18000dea3  pop     r15
0x18000dea5  pop     r14
0x18000dea7  pop     r13
0x18000dea9  pop     r12
0x18000deab  pop     rdi
0x18000deac  pop     rsi
0x18000dead  pop     rbp
0x18000deae  pop     rbx
0x18000deaf  retn
0x18000deb0  mov     [rsp+98h+var_70], r15d
0x18000deb5  mov     dword ptr [rsp+98h+var_78], 75h ; 'u'
0x18000debd  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000dec4  lea     r8, aCreateintermed; "CreateIntermediateDirectories"
0x18000decb  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000ded2  mov     edi, 3
0x18000ded7  mov     ecx, edi
0x18000ded9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000dede  lea     rdx, aFailedToCopyLo; "    Failed to copy long intermediate pa"...
0x18000dee5  mov     ecx, edi
0x18000dee7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000deec  nop
0x18000deed  mov     rcx, r14; void *
0x18000def0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000def5  nop
0x18000def6  mov     rcx, rsi; void *
0x18000def9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000defe  mov     esi, r15d
0x18000df01  jmp     short loc_18000DE95
0x18000df03  call    cs:__imp_GetLastError
0x18000df09  mov     ebp, 80070000h
0x18000df0e  test    eax, eax
0x18000df10  jle     short loc_18000DF17
0x18000df12  movzx   eax, ax
0x18000df15  or      eax, ebp
  ... truncated ...
```
