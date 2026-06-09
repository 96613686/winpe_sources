# Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)

- ea: `0x180042ed4`
- end: `0x18004392b`
- name: `?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `2647`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800427e0`
- `0x180046f38`

## callees

- `0x180008900`
- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x180019324`
- `0x1800220b4`
- `0x18002b470`
- `0x180042ed4`
- `0x180043934`
- `0x1800dfd24`
- `0x18012a90c`
- `0x180148b20`
- `0x18014aac0`
- `0x18014b400`
- `0x18014d7d0`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004357b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004357b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043770`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800430f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800432c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004364c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180043850`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800430f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800432c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004364c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180043850`

## string_xrefs

- `0x180042f36`: `CreateTableString failed [%#x]`
- `0x180043505`: `CREATE TABLE `
- `0x180043713`: `CREATE TABLE IF NOT EXISTS `
- `0x180042f43`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x180042fe6`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x18004308f`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x1800430fd`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::CreateTable(
        Windows::Compat::Inventory::SqliteInvCache *this)
{
  int v2; // eax
  signed int v3; // ebx
  __int128 *v5; // rdx
  const char *v6; // rax
  __int64 v7; // rcx
  const wchar_t *v8; // rsi
  const wchar_t *v9; // r8
  __int64 v10; // r12
  const char *v11; // rax
  int i; // ebx
  int v13; // r13d
  DWORD LastError; // ebx
  __int128 *v15; // rdx
  const char *v16; // rax
  int v17; // r8d
  __int64 v18; // rsi
  const char *v19; // rax
  int j; // r12d
  const char *v21; // rax
  _WORD *v22; // rax
  unsigned __int64 v23; // r8
  __int128 *v24; // r8
  __int128 *v25; // r12
  char *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int128 *v30; // rax
  __int64 v31; // rax
  DWORD v32; // ebx
  __int128 *v33; // rdx
  const char *v34; // rax
  int k; // r12d
  const char *v36; // rax
  __int64 v37; // r8
  _QWORD *v38; // rax
  unsigned __int64 v39; // rdx
  __int64 v40; // rax
  DWORD v41; // ebx
  __int128 *v42; // rdx
  const char *v43; // rax
  int m; // r12d
  const char *v45; // rax
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v47; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v48; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v49; // [rsp+60h] [rbp-A0h]
  __int128 v50; // [rsp+68h] [rbp-98h] BYREF
  __int128 v51; // [rsp+78h] [rbp-88h]
  __int128 v52; // [rsp+88h] [rbp-78h] BYREF
  __int128 v53; // [rsp+98h] [rbp-68h]
  __int128 v54; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v55; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v56; // [rsp+C0h] [rbp-40h]
  __int128 v57; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v58; // [rsp+D8h] [rbp-28h]
  char *Src[4]; // [rsp+E8h] [rbp-18h] BYREF

  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 7;
  LOWORD(v47) = 0;
  v2 = Windows::Compat::Inventory::SqliteInvCache::CreateTableString(this, &v47);
  v3 = v2;
  if ( v2 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1438,
      "CreateTableString failed [%#x]",
      v2);
    std::wstring::~wstring((char **)&v47);
    return (unsigned int)v3;
  }
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&v52,
    L"SELECT 1 FROM sqlite_master WHERE type='table' AND name=?;",
    0x3Au);
  v46 = 0;
  v5 = &v52;
  if ( *((_QWORD *)&v53 + 1) > 7u )
    LODWORD(v5) = v52;
  v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v5, -1, 128, (__int64)&v46, 0);
  if ( v3 )
  {
    v6 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1446,
      "sqlite3_prepare16_v2 failed: [%d] %hs",
      v3,
      v6);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    v7 = v46;
    if ( !v46 )
      return (unsigned int)v3;
    goto LABEL_97;
  }
  v8 = (const wchar_t *)((char *)this + 72);
  if ( *((_QWORD *)this + 12) <= 7u )
    LODWORD(v9) = (_DWORD)this + 72;
  else
    v9 = *(const wchar_t **)v8;
  v10 = v46;
  v3 = bindText(v46, 1, (_DWORD)v9, -2, 0, 2);
  if ( v3 )
  {
    v11 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1452,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v3,
      v11);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    if ( v10 )
      sqlite3_finalize(v10);
    return (unsigned int)v3;
  }
  for ( i = 0; i < 100; ++i )
  {
    v13 = sqlite3_step(v10);
    if ( (unsigned int)(v13 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v13 == 100 )
  {
    v50 = 0;
    v51 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v50,
      L"SELECT sql FROM sqlite_master WHERE type='table' AND name=?;",
      0x3Cu);
    if ( v10 )
    {
      LastError = GetLastError();
      sqlite3_finalize(v10);
      SetLastError(LastError);
    }
    v46 = 0;
    v15 = &v50;
    if ( *((_QWORD *)&v51 + 1) > 7u )
      LODWORD(v15) = v50;
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v15, -1, 128, (__int64)&v46, 0);
    if ( v3 )
    {
      v16 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1463,
        "sqlite3_prepare16_v2 failed: [%d] %hs",
        v3,
        v16);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      v7 = v46;
      if ( !v46 )
        return (unsigned int)v3;
      goto LABEL_97;
    }
    if ( *((_QWORD *)this + 12) > 7u )
      v8 = *(const wchar_t **)v8;
    v17 = (int)v8;
    v18 = v46;
    v3 = bindText(v46, 1, v17, -2, 0, 2);
    if ( v3 )
    {
      v19 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1469,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v3,
        v19);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( !v18 )
        return (unsigned int)v3;
      goto LABEL_105;
    }
    for ( j = 0; j < 100; ++j )
    {
      v3 = sqlite3_step(v18);
      if ( (unsigned int)(v3 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v3 != 100 )
    {
      v21 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1475,
        "sqlite3_step failed: [%d] %hs",
        v3,
        v21);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( !v18 )
        return (unsigned int)v3;
      goto LABEL_105;
    }
    v22 = (_WORD *)sqlite3_column_text16(v18, 0);
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v54, v22, v23);
    if ( !v55 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1482,
        "sqlite3_column_text16 returned a null schema [%#x]",
        -2147467259);
      std::wstring::~wstring((char **)&v54);
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( v18 )
        goto LABEL_62;
      return 2147500037LL;
    }
    v24 = &v47;
    if ( v49 > 7 )
      v24 = (__int128 *)v47;
    v25 = &v54;
    if ( v56 > 7 )
      v25 = (__int128 *)v54;
    if ( v48 > v55
      || v48
      && ((v26 = (char *)v25 + 2 * v55, v27 = _std_search_2(v25, v26, v24, v48), (char *)v27 == v26)
       || (v27 - (__int64)v25) >> 1 == -1) )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1488,
        "Schema mismatch [%#x]",
        -2147467259);
      std::wstring::~wstring((char **)&v54);
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( v18 )
LABEL_62:
        sqlite3_finalize(v18);
      return 2147500037LL;
    }
    std::wstring::~wstring((char **)&v54);
  }
  else
  {
    if ( *((_QWORD *)this + 12) > 7u )
      v8 = *(const wchar_t **)v8;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1494,
      "Table %ls doesn't exist. Creating new table.",
      v8);
    if ( 0x7FFFFFFFFFFFFFFELL - v48 < 0xD )
      std::_Xlen_string();
    v30 = &v47;
    if ( v49 > 7 )
      v30 = (__int128 *)v47;
    std::wstring::wstring(Src, v28, v29, L"CREATE TABLE ", 13, v30, v48);
    v31 = std::wstring::append(Src, L";");
    v50 = 0;
    v51 = 0;
    v50 = *(_OWORD *)v31;
    v51 = *(_OWORD *)(v31 + 16);
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    *(_WORD *)v31 = 0;
    std::wstring::~wstring(Src);
    if ( v10 )
    {
      v32 = GetLastError();
      sqlite3_finalize(v10);
      SetLastError(v32);
    }
    v46 = 0;
    v33 = &v50;
    if ( *((_QWORD *)&v51 + 1) > 7u )
      LODWORD(v33) = v50;
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v33, -1, 128, (__int64)&v46, 0);
    if ( v3 )
    {
      v34 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1501,
        "sqlite3_prepare16_v2 failed: [%d] %hs",
        v3,
        v34);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      v7 = v46;
      if ( !v46 )
        return (unsigned int)v3;
LABEL_97:
      sqlite3_finalize(v7);
      return (unsigned int)v3;
    }
    v18 = v46;
    for ( k = 0; k < 100; ++k )
    {
      v3 = sqlite3_step(v18);
      if ( (unsigned int)(v3 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v3 != 101 )
    {
      v36 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1507,
        "sqlite3_step failed: [%d] %hs",
        v3,
        v36);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( !v18 )
        return (unsigned int)v3;
LABEL_105:
      sqlite3_finalize(v18);
      return (unsigned int)v3;
    }
  }
  std::wstring::~wstring((char **)&v50);
  v38 = (_QWORD *)((char *)this + 104);
  v39 = 0x7FFFFFFFFFFFFFFELL - *((_QWORD *)this + 15);
  if ( v39 < 0x1B )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 16) > 7u )
    v38 = (_QWORD *)*v38;
  std::wstring::wstring(Src, v39, v37, L"CREATE TABLE IF NOT EXISTS ", 27, v38, *((_QWORD *)this + 15));
  v40 = std::wstring::append(Src, L" (Name TEXT PRIMARY KEY, Value TEXT);");
  v57 = 0;
  v58 = 0;
  v57 = *(_OWORD *)v40;
  v58 = *(_OWORD *)(v40 + 16);
  *(_QWORD *)(v40 + 16) = 0;
  *(_QWORD *)(v40 + 24) = 7;
  *(_WORD *)v40 = 0;
  std::wstring::~wstring(Src);
  if ( v18 )
  {
    v41 = GetLastError();
    sqlite3_finalize(v18);
    SetLastError(v41);
  }
  v46 = 0;
  v42 = &v57;
  if ( *((_QWORD *)&v58 + 1) > 7u )
    LODWORD(v42) = v57;
  v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v42, -1, 128, (__int64)&v46, 0);
  if ( v3 )
  {
    v43 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1517,
      "sqlite3_prepare16_v2 failed: [%d] %hs",
      v3,
      v43);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v57);
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    v7 = v46;
    if ( !v46 )
      return (unsigned int)v3;
    goto LABEL_97;
  }
  v18 = v46;
  for ( m = 0; m < 100; ++m )
  {
    v3 = sqlite3_step(v18);
    if ( (unsigned int)(v3 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v3 != 101 )
  {
    v45 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1523,
      "sqlite3_step failed: [%d] %hs",
      v3,
      v45);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v57);
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    if ( !v18 )
      return (unsigned int)v3;
    goto LABEL_105;
  }
  std::wstring::~wstring((char **)&v57);
  std::wstring::~wstring((char **)&v52);
  std::wstring::~wstring((char **)&v47);
  if ( v18 )
    sqlite3_finalize(v18);
  return 0;
}

```

## disassembly

```asm
0x180042ed4  push    rbp
0x180042ed6  push    rbx
0x180042ed7  push    rsi
0x180042ed8  push    rdi
0x180042ed9  push    r12
0x180042edb  push    r13
0x180042edd  push    r14
0x180042edf  push    r15
0x180042ee1  lea     rbp, [rsp-18h]
0x180042ee6  sub     rsp, 118h
0x180042eed  mov     rax, cs:__security_cookie
0x180042ef4  xor     rax, rsp
0x180042ef7  mov     [rbp+50h+var_48], rax
0x180042efb  mov     r15, rcx
0x180042efe  xor     r13d, r13d
0x180042f01  mov     [rsp+150h+var_110], r13
0x180042f06  xorps   xmm0, xmm0
0x180042f09  movups  [rsp+150h+var_108], xmm0
0x180042f0e  mov     [rsp+150h+var_F8], r13
0x180042f13  mov     [rsp+150h+var_F0], 7
0x180042f1c  mov     word ptr [rsp+150h+var_108], r13w
0x180042f22  lea     rdx, [rsp+150h+var_108]
0x180042f27  call    ?CreateTableString@SqliteInvCache@Inventory@Compat@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateTableString(std::wstring &)
0x180042f2c  mov     ebx, eax
0x180042f2e  test    eax, eax
0x180042f30  jns     short loc_180042F66
0x180042f32  mov     dword ptr [rsp+150h+var_130], eax
0x180042f36  lea     r9, aCreatetablestr; "CreateTableString failed [%#x]"
0x180042f3d  mov     r8d, 59Eh
0x180042f43  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::SqliteInvCa"...
0x180042f4a  lea     ecx, [r13+1]
0x180042f4e  call    AslLogCallPrintf
0x180042f53  nop
0x180042f54  lea     rcx, [rsp+150h+var_108]
0x180042f59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042f5e  nop
0x180042f5f  mov     eax, ebx
0x180042f61  jmp     loc_1800438FF
0x180042f66  xorps   xmm0, xmm0
0x180042f69  movups  [rbp+50h+var_C8], xmm0
0x180042f6d  xorps   xmm1, xmm1
0x180042f70  movdqu  [rbp+50h+var_B8], xmm1
0x180042f75  mov     r8d, 3Ah ; ':'
0x180042f7b  lea     rdx, aSelect1FromSql; "SELECT 1 FROM sqlite_master WHERE type="...
0x180042f82  lea     rcx, [rbp+50h+var_C8]
0x180042f86  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180042f8b  nop
0x180042f8c  mov     [rsp+150h+var_110], r13
0x180042f91  lea     rdx, [rbp+50h+var_C8]
0x180042f95  cmp     qword ptr [rbp+50h+var_B8+8], 7
0x180042f9a  cmova   rdx, qword ptr [rbp+50h+var_C8]
0x180042f9f  mov     [rsp+150h+var_128], r13
0x180042fa4  lea     rax, [rsp+150h+var_110]
0x180042fa9  mov     [rsp+150h+var_130], rax
0x180042fae  mov     r9d, 80h
0x180042fb4  or      r8d, 0FFFFFFFFh
0x180042fb8  mov     rcx, [r15+8]
0x180042fbc  call    sqlite3Prepare16
0x180042fc1  mov     ebx, eax
0x180042fc3  test    eax, eax
0x180042fc5  jz      short loc_180043032
0x180042fc7  mov     rcx, [r15+8]
0x180042fcb  call    sqlite3_errmsg
0x180042fd0  mov     [rsp+150h+var_128], rax
0x180042fd5  mov     dword ptr [rsp+150h+var_130], ebx
0x180042fd9  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x180042fe0  mov     r8d, 5A6h
0x180042fe6  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::SqliteInvCa"...
0x180042fed  mov     ecx, 1
0x180042ff2  call    AslLogCallPrintf
0x180042ff7  test    ebx, ebx
0x180042ff9  jle     short loc_180043004
0x180042ffb  movzx   ebx, bx
0x180042ffe  or      ebx, 80070000h
0x180043004  lea     rcx, [rbp+50h+var_C8]
0x180043008  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004300d  nop
0x18004300e  lea     rcx, [rsp+150h+var_108]
0x180043013  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043018  nop
0x180043019  mov     rcx, [rsp+150h+var_110]
0x18004301e  test    rcx, rcx
0x180043021  jz      loc_180042F5F
0x180043027  call    sqlite3_finalize
0x18004302c  nop
0x18004302d  jmp     loc_180042F5F
0x180043032  lea     rsi, [r15+48h]
0x180043036  cmp     qword ptr [rsi+18h], 7
0x18004303b  jbe     short loc_180043042
0x18004303d  mov     r8, [rsi]
0x180043040  jmp     short loc_180043045
0x180043042  mov     r8, rsi
0x180043045  mov     byte ptr [rsp+150h+var_128], 2
0x18004304a  mov     [rsp+150h+var_130], r13
0x18004304f  mov     edi, 1
0x180043054  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18004305b  mov     edx, edi
0x18004305d  mov     r12, [rsp+150h+var_110]
0x180043062  mov     rcx, r12
0x180043065  call    bindText
0x18004306a  mov     ebx, eax
0x18004306c  test    eax, eax
0x18004306e  jz      short loc_1800430D6
0x180043070  mov     rcx, [r15+8]
0x180043074  call    sqlite3_errmsg
0x180043079  mov     [rsp+150h+var_128], rax
0x18004307e  mov     dword ptr [rsp+150h+var_130], ebx
0x180043082  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180043089  mov     r8d, 5ACh
0x18004308f  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::SqliteInvCa"...
0x180043096  mov     ecx, edi
0x180043098  call    AslLogCallPrintf
0x18004309d  test    ebx, ebx
0x18004309f  jle     short loc_1800430AA
0x1800430a1  movzx   ebx, bx
0x1800430a4  or      ebx, 80070000h
0x1800430aa  lea     rcx, [rbp+50h+var_C8]
0x1800430ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800430b3  nop
0x1800430b4  lea     rcx, [rsp+150h+var_108]
0x1800430b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800430be  nop
0x1800430bf  test    r12, r12
0x1800430c2  jz      loc_180042F5F
0x1800430c8  mov     rcx, r12
0x1800430cb  call    sqlite3_finalize
0x1800430d0  nop
0x1800430d1  jmp     loc_180042F5F
0x1800430d6  mov     ebx, r13d
0x1800430d9  mov     rcx, r12
0x1800430dc  call    sqlite3_step
0x1800430e1  mov     r13d, eax
0x1800430e4  lea     ecx, [rax-5]
0x1800430e7  cmp     ecx, edi
0x1800430e9  ja      short loc_1800430FD
0x1800430eb  mov     ecx, 5; dwMilliseconds
0x1800430f0  call    cs:__imp_Sleep
0x1800430f6  add     ebx, edi
0x1800430f8  cmp     ebx, 64h ; 'd'
0x1800430fb  jl      short loc_1800430D9
0x1800430fd  lea     r14, aWindowsCompatI_8; "Windows::Compat::Inventory::SqliteInvCa"...
0x180043104  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18004310e  cmp     r13d, 64h ; 'd'
0x180043112  jnz     loc_1800434A3
0x180043118  xorps   xmm0, xmm0
0x18004311b  movups  [rsp+150h+var_E8], xmm0
0x180043120  xorps   xmm1, xmm1
0x180043123  movdqu  [rsp+150h+var_D8], xmm1
0x180043129  lea     r8d, [r13-28h]
0x18004312d  lea     rdx, aSelectSqlFromS; "SELECT sql FROM sqlite_master WHERE typ"...
0x180043134  lea     rcx, [rsp+150h+var_E8]
0x180043139  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004313e  nop
0x18004313f  xor     r13d, r13d
0x180043142  test    r12, r12
0x180043145  jz      short loc_180043160
0x180043147  call    cs:__imp_GetLastError
0x18004314d  mov     ebx, eax
0x18004314f  mov     rcx, r12
0x180043152  call    sqlite3_finalize
0x180043157  mov     ecx, ebx; dwErrCode
0x180043159  call    cs:__imp_SetLastError
0x18004315f  nop
0x180043160  mov     [rsp+150h+var_110], r13
0x180043165  lea     rdx, [rsp+150h+var_E8]
0x18004316a  cmp     qword ptr [rbp+50h+var_D8+8], 7
0x18004316f  cmova   rdx, qword ptr [rsp+150h+var_E8]
0x180043175  mov     [rsp+150h+var_128], r13
0x18004317a  lea     rax, [rsp+150h+var_110]
0x18004317f  mov     [rsp+150h+var_130], rax
0x180043184  mov     r9d, 80h
0x18004318a  or      r8d, 0FFFFFFFFh
0x18004318e  mov     rcx, [r15+8]
0x180043192  call    sqlite3Prepare16
0x180043197  mov     ebx, eax
0x180043199  test    eax, eax
0x18004319b  jz      short loc_18004320C
0x18004319d  mov     rcx, [r15+8]
0x1800431a1  call    sqlite3_errmsg
0x1800431a6  mov     [rsp+150h+var_128], rax
0x1800431ab  mov     dword ptr [rsp+150h+var_130], ebx
0x1800431af  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x1800431b6  mov     r8d, 5B7h
0x1800431bc  mov     rdx, r14
0x1800431bf  mov     ecx, edi
0x1800431c1  call    AslLogCallPrintf
0x1800431c6  test    ebx, ebx
0x1800431c8  jle     short loc_1800431D3
0x1800431ca  movzx   ebx, bx
0x1800431cd  or      ebx, 80070000h
0x1800431d3  lea     rcx, [rsp+150h+var_E8]
0x1800431d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800431dd  nop
0x1800431de  lea     rcx, [rbp+50h+var_C8]
0x1800431e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800431e7  nop
0x1800431e8  lea     rcx, [rsp+150h+var_108]
0x1800431ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800431f2  nop
0x1800431f3  mov     rcx, [rsp+150h+var_110]
0x1800431f8  test    rcx, rcx
0x1800431fb  jz      loc_180042F5F
0x180043201  call    sqlite3_finalize
0x180043206  nop
0x180043207  jmp     loc_180042F5F
0x18004320c  cmp     qword ptr [rsi+18h], 7
0x180043211  jbe     short loc_180043216
0x180043213  mov     rsi, [rsi]
0x180043216  mov     byte ptr [rsp+150h+var_128], 2
0x18004321b  mov     [rsp+150h+var_130], r13
0x180043220  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180043227  mov     r8, rsi
0x18004322a  mov     edx, edi
0x18004322c  mov     rsi, [rsp+150h+var_110]
0x180043231  mov     rcx, rsi
0x180043234  call    bindText
0x180043239  mov     ebx, eax
0x18004323b  test    eax, eax
0x18004323d  jz      short loc_1800432AC
0x18004323f  mov     rcx, [r15+8]
0x180043243  call    sqlite3_errmsg
0x180043248  mov     [rsp+150h+var_128], rax
0x18004324d  mov     dword ptr [rsp+150h+var_130], ebx
0x180043251  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180043258  mov     r8d, 5BDh
0x18004325e  mov     rdx, r14
0x180043261  mov     ecx, edi
0x180043263  call    AslLogCallPrintf
0x180043268  test    ebx, ebx
0x18004326a  jle     short loc_180043275
0x18004326c  movzx   ebx, bx
0x18004326f  or      ebx, 80070000h
0x180043275  lea     rcx, [rsp+150h+var_E8]
0x18004327a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004327f  nop
0x180043280  lea     rcx, [rbp+50h+var_C8]
0x180043284  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043289  nop
0x18004328a  lea     rcx, [rsp+150h+var_108]
0x18004328f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043294  nop
0x180043295  test    rsi, rsi
0x180043298  jz      loc_180042F5F
0x18004329e  mov     rcx, rsi
0x1800432a1  call    sqlite3_finalize
0x1800432a6  nop
0x1800432a7  jmp     loc_180042F5F
0x1800432ac  mov     r12d, r13d
0x1800432af  mov     rcx, rsi
0x1800432b2  call    sqlite3_step
0x1800432b7  mov     ebx, eax
0x1800432b9  add     eax, 0FFFFFFFBh
0x1800432bc  cmp     eax, edi
0x1800432be  ja      short loc_1800432D4
0x1800432c0  mov     ecx, 5; dwMilliseconds
0x1800432c5  call    cs:__imp_Sleep
0x1800432cb  add     r12d, edi
0x1800432ce  cmp     r12d, 64h ; 'd'
0x1800432d2  jl      short loc_1800432AF
0x1800432d4  cmp     ebx, 64h ; 'd'
0x1800432d7  jz      short loc_180043346
0x1800432d9  mov     rcx, [r15+8]
0x1800432dd  call    sqlite3_errmsg
0x1800432e2  mov     [rsp+150h+var_128], rax
0x1800432e7  mov     dword ptr [rsp+150h+var_130], ebx
0x1800432eb  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800432f2  mov     r8d, 5C3h
0x1800432f8  mov     rdx, r14
0x1800432fb  mov     ecx, edi
0x1800432fd  call    AslLogCallPrintf
0x180043302  test    ebx, ebx
0x180043304  jle     short loc_18004330F
0x180043306  movzx   ebx, bx
0x180043309  or      ebx, 80070000h
0x18004330f  lea     rcx, [rsp+150h+var_E8]
0x180043314  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043319  nop
0x18004331a  lea     rcx, [rbp+50h+var_C8]
0x18004331e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043323  nop
0x180043324  lea     rcx, [rsp+150h+var_108]
0x180043329  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004332e  nop
0x18004332f  test    rsi, rsi
0x180043332  jz      loc_180042F5F
0x180043338  mov     rcx, rsi
0x18004333b  call    sqlite3_finalize
0x180043340  nop
0x180043341  jmp     loc_180042F5F
0x180043346  xor     edx, edx
0x180043348  mov     rcx, rsi
0x18004334b  call    sqlite3_column_text16
0x180043350  xorps   xmm0, xmm0
0x180043353  movups  [rbp+50h+var_A8], xmm0
0x180043357  mov     [rbp+50h+var_98], r13
0x18004335b  mov     [rbp+50h+var_90], r13
0x18004335f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180043363  inc     r8
0x180043366  cmp     [rax+r8*2], r13w
0x18004336b  jnz     short loc_180043363
  ... truncated ...
```
