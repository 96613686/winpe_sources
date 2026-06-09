# Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)

- ea: `0x180028824`
- end: `0x18002927b`
- name: `?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `2647`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180027e90`
- `0x18002cf28`

## callees

- `0x1800059a0`
- `0x180005e40`
- `0x18000fa50`
- `0x180013f20`
- `0x180016440`
- `0x180017600`
- `0x180026308`
- `0x180028824`
- `0x180029284`
- `0x180066c10`
- `0x18007ee44`
- `0x1800c9a2c`
- `0x1800e7c40`
- `0x1800e9be0`
- `0x1800ea520`
- `0x1800ec8f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028aa9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800290d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028aa9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800290d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290c0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028a40`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028c15`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028f9c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800291a0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028a40`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028c15`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028f9c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800291a0`

## string_xrefs

- `0x180028886`: `CreateTableString failed [%#x]`
- `0x180028e55`: `CREATE TABLE `
- `0x180029063`: `CREATE TABLE IF NOT EXISTS `
- `0x180028893`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x180028936`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x1800289df`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x180028a4d`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`

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
  __int64 v22; // rax
  __int64 v23; // r8
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
  _BYTE Src[32]; // [rsp+E8h] [rbp-18h] BYREF

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
    std::wstring::~wstring(&v47);
    return (unsigned int)v3;
  }
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v52,
    L"SELECT 1 FROM sqlite_master WHERE type='table' AND name=?;",
    58);
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
    std::wstring::~wstring(&v52);
    std::wstring::~wstring(&v47);
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
    std::wstring::~wstring(&v52);
    std::wstring::~wstring(&v47);
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
      &v50,
      L"SELECT sql FROM sqlite_master WHERE type='table' AND name=?;",
      60);
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
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
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
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
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
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
      if ( !v18 )
        return (unsigned int)v3;
      goto LABEL_105;
    }
    v22 = sqlite3_column_text16(v18, 0);
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v22 + 2 * v23) );
    std::wstring::_Construct<1,unsigned short const *>(&v54, v22, v23);
    if ( !v55 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1482,
        "sqlite3_column_text16 returned a null schema [%#x]",
        -2147467259);
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
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
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
      if ( v18 )
LABEL_62:
        sqlite3_finalize(v18);
      return 2147500037LL;
    }
    std::wstring::~wstring(&v54);
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
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
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
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v47);
      if ( !v18 )
        return (unsigned int)v3;
LABEL_105:
      sqlite3_finalize(v18);
      return (unsigned int)v3;
    }
  }
  std::wstring::~wstring(&v50);
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
    std::wstring::~wstring(&v57);
    std::wstring::~wstring(&v52);
    std::wstring::~wstring(&v47);
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
    std::wstring::~wstring(&v57);
    std::wstring::~wstring(&v52);
    std::wstring::~wstring(&v47);
    if ( !v18 )
      return (unsigned int)v3;
    goto LABEL_105;
  }
  std::wstring::~wstring(&v57);
  std::wstring::~wstring(&v52);
  std::wstring::~wstring(&v47);
  if ( v18 )
    sqlite3_finalize(v18);
  return 0;
}

```

## disassembly

```asm
0x180028824  push    rbp
0x180028826  push    rbx
0x180028827  push    rsi
0x180028828  push    rdi
0x180028829  push    r12
0x18002882b  push    r13
0x18002882d  push    r14
0x18002882f  push    r15
0x180028831  lea     rbp, [rsp-18h]
0x180028836  sub     rsp, 118h
0x18002883d  mov     rax, cs:__security_cookie
0x180028844  xor     rax, rsp
0x180028847  mov     [rbp+50h+var_48], rax
0x18002884b  mov     r15, rcx
0x18002884e  xor     r13d, r13d
0x180028851  mov     [rsp+150h+var_110], r13
0x180028856  xorps   xmm0, xmm0
0x180028859  movups  [rsp+150h+var_108], xmm0
0x18002885e  mov     [rsp+150h+var_F8], r13
0x180028863  mov     [rsp+150h+var_F0], 7
0x18002886c  mov     word ptr [rsp+150h+var_108], r13w
0x180028872  lea     rdx, [rsp+150h+var_108]
0x180028877  call    ?CreateTableString@SqliteInvCache@Inventory@Compat@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateTableString(std::wstring &)
0x18002887c  mov     ebx, eax
0x18002887e  test    eax, eax
0x180028880  jns     short loc_1800288B6
0x180028882  mov     dword ptr [rsp+150h+var_130], eax
0x180028886  lea     r9, aCreatetablestr; "CreateTableString failed [%#x]"
0x18002888d  mov     r8d, 59Eh
0x180028893  lea     rdx, aWindowsCompatI_10; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002889a  lea     ecx, [r13+1]
0x18002889e  call    AslLogCallPrintf
0x1800288a3  nop
0x1800288a4  lea     rcx, [rsp+150h+var_108]; void *
0x1800288a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800288ae  nop
0x1800288af  mov     eax, ebx
0x1800288b1  jmp     loc_18002924F
0x1800288b6  xorps   xmm0, xmm0
0x1800288b9  movups  [rbp+50h+var_C8], xmm0
0x1800288bd  xorps   xmm1, xmm1
0x1800288c0  movdqu  [rbp+50h+var_B8], xmm1
0x1800288c5  mov     r8d, 3Ah ; ':'
0x1800288cb  lea     rdx, aSelect1FromSql; "SELECT 1 FROM sqlite_master WHERE type="...
0x1800288d2  lea     rcx, [rbp+50h+var_C8]
0x1800288d6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800288db  nop
0x1800288dc  mov     [rsp+150h+var_110], r13
0x1800288e1  lea     rdx, [rbp+50h+var_C8]
0x1800288e5  cmp     qword ptr [rbp+50h+var_B8+8], 7
0x1800288ea  cmova   rdx, qword ptr [rbp+50h+var_C8]
0x1800288ef  mov     [rsp+150h+var_128], r13
0x1800288f4  lea     rax, [rsp+150h+var_110]
0x1800288f9  mov     [rsp+150h+var_130], rax
0x1800288fe  mov     r9d, 80h
0x180028904  or      r8d, 0FFFFFFFFh
0x180028908  mov     rcx, [r15+8]
0x18002890c  call    sqlite3Prepare16
0x180028911  mov     ebx, eax
0x180028913  test    eax, eax
0x180028915  jz      short loc_180028982
0x180028917  mov     rcx, [r15+8]
0x18002891b  call    sqlite3_errmsg
0x180028920  mov     [rsp+150h+var_128], rax
0x180028925  mov     dword ptr [rsp+150h+var_130], ebx
0x180028929  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x180028930  mov     r8d, 5A6h
0x180028936  lea     rdx, aWindowsCompatI_10; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002893d  mov     ecx, 1
0x180028942  call    AslLogCallPrintf
0x180028947  test    ebx, ebx
0x180028949  jle     short loc_180028954
0x18002894b  movzx   ebx, bx
0x18002894e  or      ebx, 80070000h
0x180028954  lea     rcx, [rbp+50h+var_C8]; void *
0x180028958  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002895d  nop
0x18002895e  lea     rcx, [rsp+150h+var_108]; void *
0x180028963  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028968  nop
0x180028969  mov     rcx, [rsp+150h+var_110]
0x18002896e  test    rcx, rcx
0x180028971  jz      loc_1800288AF
0x180028977  call    sqlite3_finalize
0x18002897c  nop
0x18002897d  jmp     loc_1800288AF
0x180028982  lea     rsi, [r15+48h]
0x180028986  cmp     qword ptr [rsi+18h], 7
0x18002898b  jbe     short loc_180028992
0x18002898d  mov     r8, [rsi]
0x180028990  jmp     short loc_180028995
0x180028992  mov     r8, rsi
0x180028995  mov     byte ptr [rsp+150h+var_128], 2
0x18002899a  mov     [rsp+150h+var_130], r13
0x18002899f  mov     edi, 1
0x1800289a4  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800289ab  mov     edx, edi
0x1800289ad  mov     r12, [rsp+150h+var_110]
0x1800289b2  mov     rcx, r12
0x1800289b5  call    bindText
0x1800289ba  mov     ebx, eax
0x1800289bc  test    eax, eax
0x1800289be  jz      short loc_180028A26
0x1800289c0  mov     rcx, [r15+8]
0x1800289c4  call    sqlite3_errmsg
0x1800289c9  mov     [rsp+150h+var_128], rax
0x1800289ce  mov     dword ptr [rsp+150h+var_130], ebx
0x1800289d2  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x1800289d9  mov     r8d, 5ACh
0x1800289df  lea     rdx, aWindowsCompatI_10; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800289e6  mov     ecx, edi
0x1800289e8  call    AslLogCallPrintf
0x1800289ed  test    ebx, ebx
0x1800289ef  jle     short loc_1800289FA
0x1800289f1  movzx   ebx, bx
0x1800289f4  or      ebx, 80070000h
0x1800289fa  lea     rcx, [rbp+50h+var_C8]; void *
0x1800289fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028a03  nop
0x180028a04  lea     rcx, [rsp+150h+var_108]; void *
0x180028a09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028a0e  nop
0x180028a0f  test    r12, r12
0x180028a12  jz      loc_1800288AF
0x180028a18  mov     rcx, r12
0x180028a1b  call    sqlite3_finalize
0x180028a20  nop
0x180028a21  jmp     loc_1800288AF
0x180028a26  mov     ebx, r13d
0x180028a29  mov     rcx, r12
0x180028a2c  call    sqlite3_step
0x180028a31  mov     r13d, eax
0x180028a34  lea     ecx, [rax-5]
0x180028a37  cmp     ecx, edi
0x180028a39  ja      short loc_180028A4D
0x180028a3b  mov     ecx, 5; dwMilliseconds
0x180028a40  call    cs:__imp_Sleep
0x180028a46  add     ebx, edi
0x180028a48  cmp     ebx, 64h ; 'd'
0x180028a4b  jl      short loc_180028A29
0x180028a4d  lea     r14, aWindowsCompatI_10; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028a54  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180028a5e  cmp     r13d, 64h ; 'd'
0x180028a62  jnz     loc_180028DF3
0x180028a68  xorps   xmm0, xmm0
0x180028a6b  movups  [rsp+150h+var_E8], xmm0
0x180028a70  xorps   xmm1, xmm1
0x180028a73  movdqu  [rsp+150h+var_D8], xmm1
0x180028a79  lea     r8d, [r13-28h]
0x180028a7d  lea     rdx, aSelectSqlFromS; "SELECT sql FROM sqlite_master WHERE typ"...
0x180028a84  lea     rcx, [rsp+150h+var_E8]
0x180028a89  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028a8e  nop
0x180028a8f  xor     r13d, r13d
0x180028a92  test    r12, r12
0x180028a95  jz      short loc_180028AB0
0x180028a97  call    cs:__imp_GetLastError
0x180028a9d  mov     ebx, eax
0x180028a9f  mov     rcx, r12
0x180028aa2  call    sqlite3_finalize
0x180028aa7  mov     ecx, ebx; dwErrCode
0x180028aa9  call    cs:__imp_SetLastError
0x180028aaf  nop
0x180028ab0  mov     [rsp+150h+var_110], r13
0x180028ab5  lea     rdx, [rsp+150h+var_E8]
0x180028aba  cmp     qword ptr [rbp+50h+var_D8+8], 7
0x180028abf  cmova   rdx, qword ptr [rsp+150h+var_E8]
0x180028ac5  mov     [rsp+150h+var_128], r13
0x180028aca  lea     rax, [rsp+150h+var_110]
0x180028acf  mov     [rsp+150h+var_130], rax
0x180028ad4  mov     r9d, 80h
0x180028ada  or      r8d, 0FFFFFFFFh
0x180028ade  mov     rcx, [r15+8]
0x180028ae2  call    sqlite3Prepare16
0x180028ae7  mov     ebx, eax
0x180028ae9  test    eax, eax
0x180028aeb  jz      short loc_180028B5C
0x180028aed  mov     rcx, [r15+8]
0x180028af1  call    sqlite3_errmsg
0x180028af6  mov     [rsp+150h+var_128], rax
0x180028afb  mov     dword ptr [rsp+150h+var_130], ebx
0x180028aff  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x180028b06  mov     r8d, 5B7h
0x180028b0c  mov     rdx, r14
0x180028b0f  mov     ecx, edi
0x180028b11  call    AslLogCallPrintf
0x180028b16  test    ebx, ebx
0x180028b18  jle     short loc_180028B23
0x180028b1a  movzx   ebx, bx
0x180028b1d  or      ebx, 80070000h
0x180028b23  lea     rcx, [rsp+150h+var_E8]; void *
0x180028b28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028b2d  nop
0x180028b2e  lea     rcx, [rbp+50h+var_C8]; void *
0x180028b32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028b37  nop
0x180028b38  lea     rcx, [rsp+150h+var_108]; void *
0x180028b3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028b42  nop
0x180028b43  mov     rcx, [rsp+150h+var_110]
0x180028b48  test    rcx, rcx
0x180028b4b  jz      loc_1800288AF
0x180028b51  call    sqlite3_finalize
0x180028b56  nop
0x180028b57  jmp     loc_1800288AF
0x180028b5c  cmp     qword ptr [rsi+18h], 7
0x180028b61  jbe     short loc_180028B66
0x180028b63  mov     rsi, [rsi]
0x180028b66  mov     byte ptr [rsp+150h+var_128], 2
0x180028b6b  mov     [rsp+150h+var_130], r13
0x180028b70  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180028b77  mov     r8, rsi
0x180028b7a  mov     edx, edi
0x180028b7c  mov     rsi, [rsp+150h+var_110]
0x180028b81  mov     rcx, rsi
0x180028b84  call    bindText
0x180028b89  mov     ebx, eax
0x180028b8b  test    eax, eax
0x180028b8d  jz      short loc_180028BFC
0x180028b8f  mov     rcx, [r15+8]
0x180028b93  call    sqlite3_errmsg
0x180028b98  mov     [rsp+150h+var_128], rax
0x180028b9d  mov     dword ptr [rsp+150h+var_130], ebx
0x180028ba1  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180028ba8  mov     r8d, 5BDh
0x180028bae  mov     rdx, r14
0x180028bb1  mov     ecx, edi
0x180028bb3  call    AslLogCallPrintf
0x180028bb8  test    ebx, ebx
0x180028bba  jle     short loc_180028BC5
0x180028bbc  movzx   ebx, bx
0x180028bbf  or      ebx, 80070000h
0x180028bc5  lea     rcx, [rsp+150h+var_E8]; void *
0x180028bca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028bcf  nop
0x180028bd0  lea     rcx, [rbp+50h+var_C8]; void *
0x180028bd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028bd9  nop
0x180028bda  lea     rcx, [rsp+150h+var_108]; void *
0x180028bdf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028be4  nop
0x180028be5  test    rsi, rsi
0x180028be8  jz      loc_1800288AF
0x180028bee  mov     rcx, rsi
0x180028bf1  call    sqlite3_finalize
0x180028bf6  nop
0x180028bf7  jmp     loc_1800288AF
0x180028bfc  mov     r12d, r13d
0x180028bff  mov     rcx, rsi
0x180028c02  call    sqlite3_step
0x180028c07  mov     ebx, eax
0x180028c09  add     eax, 0FFFFFFFBh
0x180028c0c  cmp     eax, edi
0x180028c0e  ja      short loc_180028C24
0x180028c10  mov     ecx, 5; dwMilliseconds
0x180028c15  call    cs:__imp_Sleep
0x180028c1b  add     r12d, edi
0x180028c1e  cmp     r12d, 64h ; 'd'
0x180028c22  jl      short loc_180028BFF
0x180028c24  cmp     ebx, 64h ; 'd'
0x180028c27  jz      short loc_180028C96
0x180028c29  mov     rcx, [r15+8]
0x180028c2d  call    sqlite3_errmsg
0x180028c32  mov     [rsp+150h+var_128], rax
0x180028c37  mov     dword ptr [rsp+150h+var_130], ebx
0x180028c3b  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180028c42  mov     r8d, 5C3h
0x180028c48  mov     rdx, r14
0x180028c4b  mov     ecx, edi
0x180028c4d  call    AslLogCallPrintf
0x180028c52  test    ebx, ebx
0x180028c54  jle     short loc_180028C5F
0x180028c56  movzx   ebx, bx
0x180028c59  or      ebx, 80070000h
0x180028c5f  lea     rcx, [rsp+150h+var_E8]; void *
0x180028c64  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028c69  nop
0x180028c6a  lea     rcx, [rbp+50h+var_C8]; void *
0x180028c6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028c73  nop
0x180028c74  lea     rcx, [rsp+150h+var_108]; void *
0x180028c79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028c7e  nop
0x180028c7f  test    rsi, rsi
0x180028c82  jz      loc_1800288AF
0x180028c88  mov     rcx, rsi
0x180028c8b  call    sqlite3_finalize
0x180028c90  nop
0x180028c91  jmp     loc_1800288AF
0x180028c96  xor     edx, edx
0x180028c98  mov     rcx, rsi
0x180028c9b  call    sqlite3_column_text16
0x180028ca0  xorps   xmm0, xmm0
0x180028ca3  movups  [rbp+50h+var_A8], xmm0
0x180028ca7  mov     [rbp+50h+var_98], r13
0x180028cab  mov     [rbp+50h+var_90], r13
0x180028caf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028cb3  inc     r8
0x180028cb6  cmp     [rax+r8*2], r13w
0x180028cbb  jnz     short loc_180028CB3
  ... truncated ...
```
