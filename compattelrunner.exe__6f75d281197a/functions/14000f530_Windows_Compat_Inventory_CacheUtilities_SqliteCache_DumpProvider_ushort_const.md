# Windows::Compat::Inventory::CacheUtilities::SqliteCache::DumpProvider(ushort const *)

- ea: `0x14000f530`
- end: `0x14000fc72`
- name: `?DumpProvider@SqliteCache@CacheUtilities@Inventory@Compat@Windows@@UEAAXPEBG@Z`
- size: `1858`
- prototype: `void __fastcall(Windows::Compat::Inventory::CacheUtilities::SqliteCache *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x140001ba0`
- `0x1400026cc`
- `0x1400026d8`
- `0x140002780`
- `0x14000e0d8`
- `0x14000e204`
- `0x14000e4b0`
- `0x14000e730`
- `0x14000e814`
- `0x14000e9e0`
- `0x14000ea3c`
- `0x14000eacc`
- `0x14000ec78`
- `0x14000f530`
- `0x140010280`
- `0x140010eb0`
- `0x1400247e8`
- `0x14005086c`
- `0x14006a0dc`
- `0x140088090`
- `0x1400880d0`
- `0x1400882f0`
- `0x140088330`
- `0x14008a240`
- `0x14008a290`
- `0x14008abd0`
- `0x14008bab0`
- `0x14008cfa0`

## import_xrefs

- `CRYPT32!CryptBinaryToStringW` at `0x14000fa5f`
- `CRYPT32!CryptBinaryToStringW` at `0x14000faec`
- `CRYPT32!CryptBinaryToStringW` at `0x14000fa5f`
- `CRYPT32!CryptBinaryToStringW` at `0x14000faec`

## string_xrefs

- `0x14000f640`: `Failed to open database with error [%d]: %hs\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Windows::Compat::Inventory::CacheUtilities::SqliteCache::DumpProvider(
        Windows::Compat::Inventory::CacheUtilities::SqliteCache *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  const unsigned __int16 *v3; // rsi
  _QWORD *v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned int v11; // eax
  _QWORD *v12; // r12
  _QWORD *v13; // rbx
  __m128i si128; // xmm6
  _QWORD *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rsi
  int i; // r14d
  __int64 v22; // rax
  const wchar_t *v23; // r8
  __int64 v24; // r8
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // r14
  int v30; // r13d
  unsigned int v31; // esi
  __int64 v32; // rax
  __m128i *v33; // rdx
  unsigned int v34; // esi
  __int64 v35; // r8
  _QWORD *v36; // r8
  const BYTE *v37; // r12
  DWORD v38; // eax
  DWORD v39; // r15d
  unsigned __int64 v40; // rdx
  LPWSTR *v41; // rcx
  __int64 v42; // r8
  WCHAR *v43; // r9
  __int128 *v44; // r8
  const wchar_t *v45; // r8
  DWORD pcchString; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v49; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v50; // [rsp+60h] [rbp-A0h]
  _QWORD *v51; // [rsp+68h] [rbp-98h]
  __int128 v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+88h] [rbp-78h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h]
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR pszString[2]; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v58; // [rsp+C8h] [rbp-38h]
  __int128 v59; // [rsp+D8h] [rbp-28h] BYREF
  __m128i v60; // [rsp+E8h] [rbp-18h]
  _QWORD v61[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD Src[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v63[4]; // [rsp+138h] [rbp+38h] BYREF

  v3 = a2;
  v50 = a2;
  v47 = 0;
  v5 = (_QWORD *)((char *)this + 72);
  v6 = *((_QWORD *)this + 11);
  if ( v6 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring(v63, a2, a3, v5, v6, L"\\", 1);
  v7 = std::operator+<unsigned short>(Src, v63, v3);
  std::operator+<unsigned short>(v61, v7, L".db");
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v63);
  v54 = 0;
  v55 = 0;
  v8 = v61;
  if ( v61[3] > 7u )
    v8 = (_QWORD *)v61[0];
  if ( !(unsigned int)sqlite3_open16(v8, &v47) )
  {
    if ( (int)Windows::Compat::Inventory::CacheUtilities::SqliteCache::GetTableVersions(v9, v47, v3, &v54) < 0 )
    {
      fprintf(*((FILE *const *)this + 8), "Failed to query provider versions");
      goto LABEL_8;
    }
    v12 = (_QWORD *)*((_QWORD *)&v54 + 1);
    v49 = (_QWORD *)*((_QWORD *)&v54 + 1);
    v13 = (_QWORD *)v54;
    v51 = (_QWORD *)v54;
    if ( (_QWORD)v54 == *((_QWORD *)&v54 + 1) )
    {
      fprintf(*((FILE *const *)this + 8), "Failed to find any tables");
      goto LABEL_8;
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( v13[3] <= 7u )
        v15 = v13;
      else
        v15 = (_QWORD *)*v13;
      fwprintf(*((FILE *const *)this + 8), L"Provider name: %ls%ls\n", v3, v15);
      v48 = 0;
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v13[2]) < 0x16 )
        std::_Xlen_string();
      if ( v13[3] <= 7u )
        v18 = v13;
      else
        v18 = (_QWORD *)*v13;
      std::wstring::wstring(&v59, v16, v17, L"SELECT * FROM Metadata", 22, v18, v13[2]);
      std::operator+<unsigned short>(v63, &v59, L";");
      std::wstring::~wstring(&v59);
      v19 = v63;
      if ( v63[3] > 7u )
        LODWORD(v19) = v63[0];
      if ( !(unsigned int)sqlite3Prepare16(v47, (_DWORD)v19, -1, 128, (__int64)&v48, 0) )
      {
        v20 = v48;
        if ( (unsigned int)sqlite3_step(v48) == 100 )
        {
          do
          {
            for ( i = 0; i < 2; ++i )
            {
              v22 = sqlite3_column_text16(v20, (unsigned int)i);
              v23 = L"NULL";
              if ( v22 )
                v23 = (const wchar_t *)v22;
              fwprintf(*((FILE *const *)this + 8), L"\t%-20ls", v23);
            }
            fwprintf(*((FILE *const *)this + 8), L"\n");
          }
          while ( (unsigned int)sqlite3_step(v20) == 100 );
          v13 = v51;
          v49 = v12;
        }
        sqlite3_finalize(v20);
        v3 = v50;
      }
      std::wstring::wstring(Src, L"SELECT * FROM ");
      v25 = -1;
      do
        ++v25;
      while ( v3[v25] );
      v26 = v13[2];
      if ( 0x7FFFFFFFFFFFFFFELL - v26 < v25 )
        std::_Xlen_string();
      if ( v13[3] <= 7u )
        v27 = v13;
      else
        v27 = (_QWORD *)*v13;
      std::wstring::wstring(&v59, v26, v24, v3, v25, v27, v13[2]);
      std::operator+<unsigned short>(pszString, &v59, L";");
      std::wstring::operator+=(Src);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(&v59);
      v48 = 0;
      v28 = Src;
      if ( Src[3] > 7u )
        LODWORD(v28) = Src[0];
      if ( (unsigned int)sqlite3Prepare16(v47, (_DWORD)v28, -1, 128, (__int64)&v48, 0) )
        goto LABEL_80;
      v29 = v48;
      v30 = 0;
      if ( v48 )
        v30 = *(unsigned __int16 *)(v48 + 192);
      v52 = 0;
      v53 = 0;
      v31 = 0;
      if ( v30 )
      {
        do
        {
          v32 = columnName(v29, v31, 1);
          std::wstring::wstring(pszString, v32);
          v33 = (__m128i *)*((_QWORD *)&v52 + 1);
          if ( *((_QWORD *)&v52 + 1) == v53 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v52, *((_QWORD *)&v52 + 1), pszString);
          }
          else
          {
            **((_OWORD **)&v52 + 1) = *(_OWORD *)pszString;
            v33[1] = v58;
            v58 = si128;
            LOWORD(pszString[0]) = 0;
            *((_QWORD *)&v52 + 1) += 32LL;
          }
          std::wstring::~wstring(pszString);
          ++v31;
        }
        while ( (int)v31 < v30 );
      }
      while ( (unsigned int)sqlite3_step(v29) == 100 )
      {
        v34 = 0;
        if ( v30 )
        {
          while ( 1 )
          {
            fwprintf(*((FILE *const *)this + 8), L"\n\t");
            if ( v34 )
              break;
            v35 = sqlite3_column_text16(v29, 0);
            fwprintf(*((FILE *const *)this + 8), L"%-20ls", v35);
LABEL_76:
            if ( (int)++v34 >= v30 )
              goto LABEL_77;
          }
          v36 = (_QWORD *)(v52 + 32LL * v34);
          if ( v36[3] > 7u )
            v36 = (_QWORD *)*v36;
          fwprintf(*((FILE *const *)this + 8), L"\t%-20ls", v36);
          if ( (unsigned int)sqlite3_column_type(v29, v34) != 4 )
          {
            v45 = (const wchar_t *)sqlite3_column_text16(v29, v34);
            if ( !v45 )
              v45 = L"NULL";
            fwprintf(*((FILE *const *)this + 8), L"\t%-20ls", v45);
            goto LABEL_76;
          }
          v37 = (const BYTE *)sqlite3_column_blob(v29, v34);
          v38 = sqlite3_column_bytes(v29, v34);
          v39 = v38;
          if ( v37 && v38 )
          {
            pcchString = 0;
            if ( !CryptBinaryToStringW(v37, v38, 0x40000001u, 0, &pcchString) )
            {
              std::runtime_error::runtime_error(
                (std::runtime_error *)pExceptionObject,
                "CryptBinaryToStringW (size) failed");
              throw (std::runtime_error *)pExceptionObject;
            }
            *(_OWORD *)pszString = 0;
            v58.m128i_i64[0] = 0;
            v58.m128i_i64[1] = 7;
            LOWORD(pszString[0]) = 0;
            v40 = pcchString - 1;
            if ( pcchString == 1 )
            {
              v58.m128i_i64[0] = 0;
              goto LABEL_63;
            }
            v41 = pszString;
            if ( v40 > 7 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(pszString);
            }
            else
            {
              v58.m128i_i64[0] = pcchString - 1;
              v42 = v58.m128i_i64[0];
              do
              {
                *(_WORD *)v41 = 0;
                v41 = (LPWSTR *)((char *)v41 + 2);
                --v42;
              }
              while ( v42 );
LABEL_63:
              *((_WORD *)pszString + v40) = 0;
            }
            v43 = (WCHAR *)pszString;
            if ( v58.m128i_i64[1] > 7uLL )
              v43 = pszString[0];
            if ( !CryptBinaryToStringW(v37, v39, 0x40000001u, v43, &pcchString) )
            {
              std::runtime_error::runtime_error(
                (std::runtime_error *)pExceptionObject,
                "CryptBinaryToStringW (encode) failed");
              throw (std::runtime_error *)pExceptionObject;
            }
            v59 = *(_OWORD *)pszString;
            v60 = v58;
            v58.m128i_i64[0] = 0;
            v58.m128i_i64[1] = 7;
            LOWORD(pszString[0]) = 0;
            std::wstring::~wstring(pszString);
          }
          else
          {
            std::wstring::wstring(&v59, &word_1400ADB90);
          }
          v44 = &v59;
          if ( v60.m128i_i64[1] > 7uLL )
            v44 = (__int128 *)v59;
          fwprintf(*((FILE *const *)this + 8), L"\t%-20ls", v44);
          std::wstring::~wstring(&v59);
          goto LABEL_76;
        }
LABEL_77:
        fwprintf(*((FILE *const *)this + 8), L"\n");
      }
      fwprintf(*((FILE *const *)this + 8), L"\n");
      sqlite3_finalize(v29);
      std::vector<std::wstring>::~vector<std::wstring>(&v52);
      v12 = v49;
      v3 = v50;
LABEL_80:
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v63);
      v13 += 4;
      v51 = v13;
      if ( v13 == v12 )
      {
        sqlite3Close(v47, 0);
        goto LABEL_8;
      }
    }
  }
  v10 = sqlite3_errmsg(v47);
  v11 = sqlite3_errcode(v47);
  fwprintf(*((FILE *const *)this + 8), L"Failed to open database with error [%d]: %hs\n", v11, v10);
LABEL_8:
  std::vector<std::wstring>::~vector<std::wstring>(&v54);
  std::wstring::~wstring(v61);
}

```

## disassembly

```asm
0x14000f530  mov     rax, rsp
0x14000f533  mov     [rax+18h], rbx
0x14000f537  push    rbp
0x14000f538  push    rsi
0x14000f539  push    rdi
0x14000f53a  push    r12
0x14000f53c  push    r13
0x14000f53e  push    r14
0x14000f540  push    r15
0x14000f542  lea     rbp, [rsp-70h]
0x14000f547  sub     rsp, 170h
0x14000f54e  movaps  xmmword ptr [rax-48h], xmm6
0x14000f552  mov     rax, cs:__security_cookie
0x14000f559  xor     rax, rsp
0x14000f55c  mov     [rbp+0A0h+var_48], rax
0x14000f560  mov     rsi, rdx
0x14000f563  mov     [rsp+1A0h+var_140], rdx
0x14000f568  mov     rdi, rcx
0x14000f56b  xor     r15d, r15d
0x14000f56e  mov     [rsp+1A0h+var_158], r15
0x14000f573  lea     r9, [rcx+48h]
0x14000f577  mov     rcx, [r9+10h]
0x14000f57b  mov     r14, 7FFFFFFFFFFFFFFEh
0x14000f585  mov     rax, r14
0x14000f588  sub     rax, rcx
0x14000f58b  cmp     rax, 1
0x14000f58f  jb      loc_14000FC2A
0x14000f595  cmp     qword ptr [r9+18h], 7
0x14000f59a  jbe     short loc_14000F59F
0x14000f59c  mov     r9, [r9]
0x14000f59f  mov     [rsp+1A0h+var_170], 1
0x14000f5a8  lea     rax, Source; "\\"
0x14000f5af  mov     [rsp+1A0h+var_178], rax
0x14000f5b4  mov     [rsp+1A0h+pcchString], rcx
0x14000f5b9  lea     rcx, [rbp+0A0h+var_68]
0x14000f5bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14000f5c2  nop
0x14000f5c3  mov     r8, rsi
0x14000f5c6  lea     rdx, [rbp+0A0h+var_68]
0x14000f5ca  lea     rcx, [rbp+0A0h+Src]
0x14000f5ce  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f5d3  nop
0x14000f5d4  lea     r8, aDb; ".db"
0x14000f5db  mov     rdx, rax
0x14000f5de  lea     rcx, [rbp+0A0h+var_A8]
0x14000f5e2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f5e7  nop
0x14000f5e8  lea     rcx, [rbp+0A0h+Src]
0x14000f5ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f5f1  nop
0x14000f5f2  lea     rcx, [rbp+0A0h+var_68]
0x14000f5f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f5fb  xorps   xmm0, xmm0
0x14000f5fe  movdqu  [rbp+0A0h+var_118], xmm0
0x14000f603  mov     [rbp+0A0h+var_108], r15
0x14000f607  lea     rcx, [rbp+0A0h+var_A8]
0x14000f60b  cmp     [rbp+0A0h+var_90], 7
0x14000f610  cmova   rcx, [rbp+0A0h+var_A8]
0x14000f615  lea     rdx, [rsp+1A0h+var_158]
0x14000f61a  call    sqlite3_open16
0x14000f61f  test    eax, eax
0x14000f621  jz      short loc_14000F690
0x14000f623  mov     rcx, [rsp+1A0h+var_158]
0x14000f628  call    sqlite3_errmsg
0x14000f62d  mov     rbx, rax
0x14000f630  mov     rcx, [rsp+1A0h+var_158]
0x14000f635  call    sqlite3_errcode
0x14000f63a  mov     r9, rbx
0x14000f63d  mov     r8d, eax
0x14000f640  lea     rdx, aFailedToOpenDa; "Failed to open database with error [%d]"...
0x14000f647  mov     rcx, [rdi+40h]; Stream
0x14000f64b  call    fwprintf
0x14000f650  nop
0x14000f651  lea     rcx, [rbp+0A0h+var_118]
0x14000f655  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000f65a  nop
0x14000f65b  lea     rcx, [rbp+0A0h+var_A8]
0x14000f65f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f664  mov     rcx, [rbp+0A0h+var_48]
0x14000f668  xor     rcx, rsp; StackCookie
0x14000f66b  call    __security_check_cookie
0x14000f670  lea     r11, [rsp+1A0h+var_30]
0x14000f678  mov     rbx, [r11+50h]
0x14000f67c  movaps  xmm6, xmmword ptr [r11-10h]
0x14000f681  mov     rsp, r11
0x14000f684  pop     r15
0x14000f686  pop     r14
0x14000f688  pop     r13
0x14000f68a  pop     r12
0x14000f68c  pop     rdi
0x14000f68d  pop     rsi
0x14000f68e  pop     rbp
0x14000f68f  retn
0x14000f690  lea     r9, [rbp+0A0h+var_118]
0x14000f694  mov     r8, rsi
0x14000f697  mov     rdx, [rsp+1A0h+var_158]
0x14000f69c  call    ?GetTableVersions@SqliteCache@CacheUtilities@Inventory@Compat@Windows@@AEAAJPEAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Windows::Compat::Inventory::CacheUtilities::SqliteCache::GetTableVersions(void *,ushort const *,std::vector<std::wstring> &)
0x14000f6a1  test    eax, eax
0x14000f6a3  jns     short loc_14000F6B7
0x14000f6a5  lea     rdx, aFailedToQueryP; "Failed to query provider versions"
0x14000f6ac  mov     rcx, [rdi+40h]; Stream
0x14000f6b0  call    fprintf
0x14000f6b5  jmp     short loc_14000F651
0x14000f6b7  mov     r12, qword ptr [rbp+0A0h+var_118+8]
0x14000f6bb  mov     [rsp+1A0h+var_148], r12
0x14000f6c0  mov     rbx, qword ptr [rbp+0A0h+var_118]
0x14000f6c4  mov     [rsp+1A0h+var_138], rbx
0x14000f6c9  cmp     rbx, r12
0x14000f6cc  jnz     short loc_14000F6D7
0x14000f6ce  lea     rdx, aFailedToFindAn; "Failed to find any tables"
0x14000f6d5  jmp     short loc_14000F6AC
0x14000f6d7  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14000f6df  cmp     qword ptr [rbx+18h], 7
0x14000f6e4  jbe     short loc_14000F6EB
0x14000f6e6  mov     r9, [rbx]
0x14000f6e9  jmp     short loc_14000F6EE
0x14000f6eb  mov     r9, rbx
0x14000f6ee  mov     r8, rsi
0x14000f6f1  lea     rdx, aProviderNameLs_0; "Provider name: %ls%ls\n"
0x14000f6f8  mov     rcx, [rdi+40h]; Stream
0x14000f6fc  call    fwprintf
0x14000f701  mov     [rsp+1A0h+var_150], r15
0x14000f706  mov     rcx, [rbx+10h]
0x14000f70a  mov     rax, r14
0x14000f70d  sub     rax, rcx
0x14000f710  cmp     rax, 16h
0x14000f714  jb      loc_14000FC24
0x14000f71a  cmp     qword ptr [rbx+18h], 7
0x14000f71f  jbe     short loc_14000F726
0x14000f721  mov     rax, [rbx]
0x14000f724  jmp     short loc_14000F729
0x14000f726  mov     rax, rbx
0x14000f729  mov     [rsp+1A0h+var_170], rcx
0x14000f72e  mov     [rsp+1A0h+var_178], rax
0x14000f733  mov     [rsp+1A0h+pcchString], 16h
0x14000f73c  lea     r9, aSelectFromMeta; "SELECT * FROM Metadata"
0x14000f743  lea     rcx, [rbp+0A0h+var_C8]
0x14000f747  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14000f74c  nop
0x14000f74d  lea     r8, asc_1400AEF5C; ";"
0x14000f754  lea     rdx, [rbp+0A0h+var_C8]
0x14000f758  lea     rcx, [rbp+0A0h+var_68]
0x14000f75c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f761  nop
0x14000f762  lea     rcx, [rbp+0A0h+var_C8]
0x14000f766  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f76b  lea     rdx, [rbp+0A0h+var_68]
0x14000f76f  cmp     [rbp+0A0h+var_50], 7
0x14000f774  cmova   rdx, [rbp+0A0h+var_68]
0x14000f779  mov     [rsp+1A0h+var_178], r15
0x14000f77e  lea     rax, [rsp+1A0h+var_150]
0x14000f783  mov     [rsp+1A0h+pcchString], rax
0x14000f788  mov     r9d, 80h
0x14000f78e  or      r8d, 0FFFFFFFFh
0x14000f792  mov     rcx, [rsp+1A0h+var_158]
0x14000f797  call    sqlite3Prepare16
0x14000f79c  test    eax, eax
0x14000f79e  jnz     loc_14000F82E
0x14000f7a4  mov     rsi, [rsp+1A0h+var_150]
0x14000f7a9  mov     rcx, rsi
0x14000f7ac  call    sqlite3_step
0x14000f7b1  cmp     eax, 64h ; 'd'
0x14000f7b4  jnz     short loc_14000F821
0x14000f7b6  xor     ebx, ebx
0x14000f7b8  mov     r14d, ebx
0x14000f7bb  mov     edx, r14d
0x14000f7be  mov     rcx, rsi
0x14000f7c1  call    sqlite3_column_text16
0x14000f7c6  lea     r8, aNull_2; "NULL"
0x14000f7cd  test    rax, rax
0x14000f7d0  cmovnz  r8, rax
0x14000f7d4  lea     rdx, a20ls; "\t%-20ls"
0x14000f7db  mov     rcx, [rdi+40h]; Stream
0x14000f7df  call    fwprintf
0x14000f7e4  inc     r14d
0x14000f7e7  cmp     r14d, 2
0x14000f7eb  jl      short loc_14000F7BB
0x14000f7ed  lea     rdx, asc_1400ACFA0; "\n"
0x14000f7f4  mov     rcx, [rdi+40h]; Stream
0x14000f7f8  call    fwprintf
0x14000f7fd  mov     rcx, rsi
0x14000f800  call    sqlite3_step
0x14000f805  cmp     eax, 64h ; 'd'
0x14000f808  jz      short loc_14000F7B8
0x14000f80a  mov     rbx, [rsp+1A0h+var_138]
0x14000f80f  mov     [rsp+1A0h+var_148], r12
0x14000f814  xor     r15d, r15d
0x14000f817  mov     r14, 7FFFFFFFFFFFFFFEh
0x14000f821  mov     rcx, rsi
0x14000f824  call    sqlite3_finalize
0x14000f829  mov     rsi, [rsp+1A0h+var_140]
0x14000f82e  lea     rdx, aSelectFrom; "SELECT * FROM "
0x14000f835  lea     rcx, [rbp+0A0h+Src]
0x14000f839  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000f83e  nop
0x14000f83f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f843  inc     rcx
0x14000f846  cmp     [rsi+rcx*2], r15w
0x14000f84b  jnz     short loc_14000F843
0x14000f84d  mov     rdx, [rbx+10h]
0x14000f851  mov     rax, r14
0x14000f854  sub     rax, rdx
0x14000f857  cmp     rax, rcx
0x14000f85a  jb      loc_14000FC1E
0x14000f860  cmp     qword ptr [rbx+18h], 7
0x14000f865  jbe     short loc_14000F86C
0x14000f867  mov     rax, [rbx]
0x14000f86a  jmp     short loc_14000F86F
0x14000f86c  mov     rax, rbx
0x14000f86f  mov     [rsp+1A0h+var_170], rdx
0x14000f874  mov     [rsp+1A0h+var_178], rax
0x14000f879  mov     [rsp+1A0h+pcchString], rcx
0x14000f87e  mov     r9, rsi
0x14000f881  lea     rcx, [rbp+0A0h+var_C8]
0x14000f885  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14000f88a  nop
0x14000f88b  lea     r8, asc_1400AEF5C; ";"
0x14000f892  lea     rdx, [rbp+0A0h+var_C8]
0x14000f896  lea     rcx, [rbp+0A0h+pszString]
0x14000f89a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x14000f89f  nop
0x14000f8a0  mov     rdx, rax
0x14000f8a3  lea     rcx, [rbp+0A0h+Src]; Src
0x14000f8a7  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14000f8ac  nop
0x14000f8ad  lea     rcx, [rbp+0A0h+pszString]
0x14000f8b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f8b6  nop
0x14000f8b7  lea     rcx, [rbp+0A0h+var_C8]
0x14000f8bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f8c0  mov     [rsp+1A0h+var_150], r15
0x14000f8c5  lea     rdx, [rbp+0A0h+Src]
0x14000f8c9  cmp     [rbp+0A0h+var_70], 7
0x14000f8ce  cmova   rdx, [rbp+0A0h+Src]
0x14000f8d3  mov     [rsp+1A0h+var_178], r15
0x14000f8d8  lea     rax, [rsp+1A0h+var_150]
0x14000f8dd  mov     [rsp+1A0h+pcchString], rax
0x14000f8e2  mov     r9d, 80h
0x14000f8e8  or      r8d, 0FFFFFFFFh
0x14000f8ec  mov     rcx, [rsp+1A0h+var_158]
0x14000f8f1  call    sqlite3Prepare16
0x14000f8f6  test    eax, eax
0x14000f8f8  jnz     loc_14000FBE8
0x14000f8fe  mov     r14, [rsp+1A0h+var_150]
0x14000f903  test    r14, r14
0x14000f906  mov     r13d, r15d
0x14000f909  jz      short loc_14000F913
0x14000f90b  movzx   r13d, word ptr [r14+0C0h]
0x14000f913  xorps   xmm0, xmm0
0x14000f916  movdqu  [rsp+1A0h+var_130], xmm0
0x14000f91c  mov     [rbp+0A0h+var_120], r15
0x14000f920  mov     esi, r15d
0x14000f923  test    r13d, r13d
0x14000f926  jz      loc_14000FBA0
0x14000f92c  xor     r9d, r9d
0x14000f92f  lea     r8d, [r9+1]
0x14000f933  mov     edx, esi
0x14000f935  mov     rcx, r14
0x14000f938  call    columnName
0x14000f93d  mov     rdx, rax
0x14000f940  lea     rcx, [rbp+0A0h+pszString]
0x14000f944  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000f949  nop
0x14000f94a  mov     rdx, qword ptr [rsp+1A0h+var_130+8]
0x14000f94f  cmp     rdx, [rbp+0A0h+var_120]
0x14000f953  jz      short loc_14000F976
0x14000f955  movups  xmm0, xmmword ptr [rbp+0A0h+pszString]
0x14000f959  movups  xmmword ptr [rdx], xmm0
0x14000f95c  movups  xmm1, [rbp+0A0h+var_D8]
0x14000f960  movups  xmmword ptr [rdx+10h], xmm1
0x14000f964  movdqu  [rbp+0A0h+var_D8], xmm6
0x14000f969  mov     word ptr [rbp+0A0h+pszString], r15w
0x14000f96e  add     qword ptr [rsp+1A0h+var_130+8], 20h ; ' '
0x14000f974  jmp     short loc_14000F985
0x14000f976  lea     r8, [rbp+0A0h+pszString]
0x14000f97a  lea     rcx, [rsp+1A0h+var_130]
0x14000f97f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14000f984  nop
0x14000f985  lea     rcx, [rbp+0A0h+pszString]
0x14000f989  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f98e  inc     esi
0x14000f990  cmp     esi, r13d
0x14000f993  jl      short loc_14000F92C
0x14000f995  jmp     loc_14000FBA0
0x14000f99a  mov     esi, r15d
0x14000f99d  test    r13d, r13d
0x14000f9a0  jz      loc_14000FB90
0x14000f9a6  lea     rdx, asc_1400AF060; "\n\t"
0x14000f9ad  mov     rcx, [rdi+40h]; Stream
0x14000f9b1  call    fwprintf
0x14000f9b6  test    esi, esi
0x14000f9b8  jnz     short loc_14000F9D7
0x14000f9ba  xor     edx, edx
0x14000f9bc  mov     rcx, r14
0x14000f9bf  call    sqlite3_column_text16
0x14000f9c4  mov     r8, rax
0x14000f9c7  lea     rdx, a20ls_1; "%-20ls"
0x14000f9ce  mov     rcx, [rdi+40h]
0x14000f9d2  jmp     loc_14000FB80
0x14000f9d7  mov     r8d, esi
  ... truncated ...
```
