# TOKEN_CACHE::GetCachedToken(ushort *,ushort *,ushort *,ulong,TOKEN_CACHE_ENTRY * *,ulong *)

- ea: `0x180059230`
- end: `0x18005978c`
- name: `?GetCachedToken@TOKEN_CACHE@@QEAAJPEAG00KPEAPEAVTOKEN_CACHE_ENTRY@@PEAK@Z`
- size: `1372`
- prototype: `int(TOKEN_CACHE *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, struct TOKEN_CACHE_ENTRY **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004461c`
- `0x1800562fc`

## callees

- `0x18001c250`
- `0x18001e610`
- `0x180058e98`
- `0x180058f60`
- `0x180058ff8`
- `0x180059230`
- `0x1800599f0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcschr` at `0x18005935d`
- `msvcrt!wcschr` at `0x18005947c`
- `msvcrt!wcschr` at `0x18005935d`
- `msvcrt!wcschr` at `0x18005947c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800594e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005954c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800595a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800594e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005954c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800595a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059701`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x1800595be`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x1800595be`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x1800595f8`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x1800595f8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180059626`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180059626`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005970b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059716`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059720`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005972a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059738`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059743`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005974d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059757`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005970b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059716`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059720`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005972a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059738`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059743`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005974d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180059757`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800593c9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800593d7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005946e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005948f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005949f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005950a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180059554`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180059562`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180059645`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800593c9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800593d7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005946e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005948f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005949f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18005950a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180059554`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180059562`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180059645`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180059294`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800592c3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800592ed`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180059312`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005960c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180059294`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800592c3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800592ed`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180059312`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005960c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005939e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800593b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180059652`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005939e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800593b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180059652`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180059418`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180059418`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800596b5`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800596b5`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18005937b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18005937b`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x1800594d7`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180059542`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180059598`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x1800594d7`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180059542`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180059598`

## pseudocode

```c
__int64 __fastcall TOKEN_CACHE::GetCachedToken(
        TOKEN_CACHE *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        DWORD dwLogonType,
        struct TOKEN_CACHE_ENTRY **a6,
        unsigned int *a7)
{
  wchar_t *v10; // rax
  wchar_t *v11; // r14
  const unsigned __int16 *v12; // rdx
  int CacheKey; // ebx
  STRU *v14; // rcx
  const unsigned __int16 *Str; // rbx
  const unsigned __int16 *v16; // rax
  TOKEN_CACHE *v17; // rcx
  int Key; // eax
  TOKEN_CACHE_ENTRY *v19; // rcx
  const wchar_t *v20; // rax
  const WCHAR *v21; // rax
  DWORD LastError; // eax
  const WCHAR *v23; // rax
  const WCHAR *v24; // rbx
  const WCHAR *v25; // rax
  DWORD v26; // eax
  char *v27; // rdi
  const unsigned __int16 *v28; // rax
  __int64 v29; // rcx
  int v30; // edx
  int v31; // ecx
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpszDomain; // [rsp+60h] [rbp-A0h] BYREF
  TOKEN_CACHE *v36; // [rsp+68h] [rbp-98h]
  _BYTE v37[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v39[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v40[56]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v41[68]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 v42[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v43[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v44[64]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v36 = g_pTokenCache;
  STRU::STRU((STRU *)v40, v41, 0x40u);
  hObject = 0;
  memset_0(v42, 0, sizeof(v42));
  STRU::STRU((STRU *)v39, v42, 0x20u);
  memset_0(v43, 0, sizeof(v43));
  STRU::STRU((STRU *)v37, v43, 0x40u);
  memset_0(v44, 0, sizeof(v44));
  STRU::STRU((STRU *)v38, v44, 0x40u);
  v34 = 0;
  if ( a2 && a3 && a4 && a6 && a7 )
  {
    *a6 = 0;
    *a7 = 0;
    if ( *a3 )
    {
      CacheKey = STRU::Copy((STRU *)v37, a2);
      if ( CacheKey < 0 )
        goto LABEL_46;
      v12 = a3;
      v14 = (STRU *)v38;
    }
    else
    {
      v10 = wcschr(a2, 0x5Cu);
      v11 = v10;
      v12 = a2;
      if ( v10 )
      {
        CacheKey = STRU::Copy((STRU *)v38, a2, v10 - a2);
        if ( CacheKey < 0 )
          goto LABEL_46;
        v12 = v11 + 1;
      }
      v14 = (STRU *)v37;
    }
    CacheKey = STRU::Copy(v14, v12);
    if ( CacheKey < 0 )
      goto LABEL_46;
    Str = STRU::QueryStr((STRU *)v38);
    v16 = STRU::QueryStr((STRU *)v37);
    CacheKey = TOKEN_CACHE_KEY::CreateCacheKey((TOKEN_CACHE_KEY *)v40, v16, Str, dwLogonType);
    if ( CacheKey < 0 )
      goto LABEL_46;
    v17 = v36;
    *a6 = 0;
    lpszDomain = 0;
    Key = CLKRHashTable::FindKey(v17, v40, &lpszDomain);
    v19 = (TOKEN_CACHE_ENTRY *)lpszDomain;
    *a6 = (struct TOKEN_CACHE_ENTRY *)lpszDomain;
    if ( !Key )
    {
      CacheKey = TOKEN_CACHE_ENTRY::EqualPasswordHash(v19, a4, &v34);
      if ( CacheKey < 0 )
      {
        TOKEN_CACHE_ENTRY::DereferenceCacheEntry(*a6);
        *a6 = 0;
LABEL_46:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_48;
      }
      if ( v34 )
      {
LABEL_48:
        STRU::~STRU((STRU *)v38);
        STRU::~STRU((STRU *)v37);
        STRU::~STRU((STRU *)v39);
        STRU::~STRU((STRU *)v40);
        return (unsigned int)CacheKey;
      }
      TOKEN_CACHE_ENTRY::DereferenceCacheEntry(*a6);
      *a6 = 0;
    }
    v20 = STRU::QueryStr((STRU *)v37);
    if ( wcschr(v20, 0x40u) )
    {
      lpszDomain = STRU::QueryStr((STRU *)v38);
      v21 = STRU::QueryStr((STRU *)v37);
      if ( !LogonUserExW(v21, &szDomain, a4, dwLogonType, 0, &hObject, 0, 0, 0, 0) )
      {
        LastError = GetLastError();
        *a7 = LastError;
        if ( LastError == 1909 )
        {
LABEL_28:
          CLKRHashTable::DeleteKey(v36, v40);
          goto LABEL_29;
        }
        if ( LastError != 1326 )
        {
LABEL_29:
          CacheKey = 0;
          goto LABEL_48;
        }
        v23 = STRU::QueryStr((STRU *)v37);
        if ( !LogonUserExW(v23, lpszDomain, a4, dwLogonType, 0, &hObject, 0, 0, 0, 0) )
        {
LABEL_27:
          v26 = GetLastError();
          *a7 = v26;
          if ( v26 == 1909 )
            goto LABEL_28;
          goto LABEL_29;
        }
      }
    }
    else
    {
      v24 = STRU::QueryStr((STRU *)v38);
      v25 = STRU::QueryStr((STRU *)v37);
      if ( !LogonUserExW(v25, v24, a4, dwLogonType, 0, &hObject, 0, 0, 0, 0) )
        goto LABEL_27;
    }
    v27 = (char *)operator new(0x170u);
    if ( v27 )
    {
      *((_DWORD *)v27 + 7) = 1;
      *(_QWORD *)v27 = &TOKEN_CACHE_ENTRY::`vftable';
      CSmallSpinLock::CSmallSpinLock((CSmallSpinLock *)(v27 + 32));
      STRU::STRU((STRU *)(v27 + 40), (unsigned __int16 *)v27 + 48, 0x40u);
      STRA::STRA((STRA *)(v27 + 296), v27 + 224, 0x41u);
      *((_QWORD *)v27 + 44) = 0;
      *((_QWORD *)v27 + 45) = 0;
      *((_DWORD *)v27 + 6) = 1413690199;
      v28 = STRU::QueryStr((STRU *)v40);
      CacheKey = STRU::Copy((STRU *)(v27 + 40), v28);
      if ( CacheKey >= 0 )
      {
        if ( dwLogonType == 3 || (v29 = 0, dwLogonType == 8) )
          v29 = 1;
        if ( hObject )
        {
          if ( (_DWORD)v29 )
            *((_QWORD *)v27 + 44) = hObject;
          else
            *((_QWORD *)v27 + 45) = hObject;
          CacheKey = TOKEN_CACHE_ENTRY::GenPasswordHash((TOKEN_CACHE_ENTRY *)v29, a4, (struct STRA *)(v27 + 296));
          if ( CacheKey >= 0 )
          {
            CLKRHashTable::InsertRecord(v36, v27, 0);
            if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
              McTemplateU0zzzp_EtwEventWriteTransfer(v31, v30, (_DWORD)a3, (_DWORD)a2, (__int64)a4, (char)hObject);
            *a6 = (struct TOKEN_CACHE_ENTRY *)v27;
            goto LABEL_48;
          }
        }
        else
        {
          CacheKey = -2147024809;
        }
      }
      TOKEN_CACHE_ENTRY::DereferenceCacheEntry((TOKEN_CACHE_ENTRY *)v27);
    }
    else
    {
      CacheKey = -2147024888;
    }
    goto LABEL_46;
  }
  STRU::~STRU((STRU *)v38);
  STRU::~STRU((STRU *)v37);
  STRU::~STRU((STRU *)v39);
  STRU::~STRU((STRU *)v40);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180059230  mov     [rsp-8+arg_0], rbx
0x180059235  push    rbp
0x180059236  push    rsi
0x180059237  push    rdi
0x180059238  push    r12
0x18005923a  push    r13
0x18005923c  push    r14
0x18005923e  push    r15
0x180059240  lea     rbp, [rsp-230h]
0x180059248  sub     rsp, 330h
0x18005924f  mov     rax, cs:__security_cookie
0x180059256  xor     rax, rsp
0x180059259  mov     [rbp+260h+var_40], rax
0x180059260  mov     rax, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x180059267  lea     rcx, [rbp+260h+var_240]
0x18005926b  mov     rsi, [rbp+260h+arg_28]
0x180059272  mov     r13, r8
0x180059275  mov     rdi, [rbp+260h+arg_30]
0x18005927c  mov     r12, rdx
0x18005927f  mov     r14d, 40h ; '@'
0x180059285  mov     [rsp+360h+var_2F8], rax
0x18005928a  mov     r8d, r14d
0x18005928d  lea     rdx, [rbp+260h+var_208]
0x180059291  mov     r15, r9
0x180059294  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005929a  mov     r8d, r14d; Size
0x18005929d  mov     [rsp+360h+hObject], 0
0x1800592a6  xor     edx, edx; Val
0x1800592a8  lea     rcx, [rbp+260h+var_180]; void *
0x1800592af  call    memset_0
0x1800592b4  lea     r8d, [r14-20h]
0x1800592b8  lea     rdx, [rbp+260h+var_180]
0x1800592bf  lea     rcx, [rbp+260h+var_280]
0x1800592c3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800592c9  lea     ebx, [r14+40h]
0x1800592cd  xor     edx, edx; Val
0x1800592cf  mov     r8d, ebx; Size
0x1800592d2  lea     rcx, [rbp+260h+var_140]; void *
0x1800592d9  call    memset_0
0x1800592de  mov     r8d, r14d
0x1800592e1  lea     rdx, [rbp+260h+var_140]
0x1800592e8  lea     rcx, [rsp+360h+var_2F0]
0x1800592ed  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800592f3  mov     r8d, ebx; Size
0x1800592f6  lea     rcx, [rbp+260h+var_C0]; void *
0x1800592fd  xor     edx, edx; Val
0x1800592ff  call    memset_0
0x180059304  mov     r8d, r14d
0x180059307  lea     rdx, [rbp+260h+var_C0]
0x18005930e  lea     rcx, [rbp+260h+var_2B8]
0x180059312  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180059318  xor     ebx, ebx
0x18005931a  mov     [rsp+360h+var_308], ebx
0x18005931e  test    r12, r12
0x180059321  jz      loc_180059734
0x180059327  test    r13, r13
0x18005932a  jz      loc_180059734
0x180059330  test    r15, r15
0x180059333  jz      loc_180059734
0x180059339  test    rsi, rsi
0x18005933c  jz      loc_180059734
0x180059342  test    rdi, rdi
0x180059345  jz      loc_180059734
0x18005934b  mov     [rsi], rbx
0x18005934e  mov     [rdi], ebx
0x180059350  cmp     [r13+0], bx
0x180059355  jnz     short loc_180059396
0x180059357  lea     edx, [rbx+5Ch]; Ch
0x18005935a  mov     rcx, r12; Str
0x18005935d  call    cs:__imp_wcschr
0x180059363  mov     r14, rax
0x180059366  mov     rdx, r12
0x180059369  test    rax, rax
0x18005936c  jz      short loc_18005938F
0x18005936e  mov     r8, rax
0x180059371  lea     rcx, [rbp+260h+var_2B8]
0x180059375  sub     r8, r12
0x180059378  sar     r8, 1
0x18005937b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180059381  mov     ebx, eax
0x180059383  test    eax, eax
0x180059385  js      loc_1800596F7
0x18005938b  lea     rdx, [r14+2]
0x18005938f  lea     rcx, [rsp+360h+var_2F0]
0x180059394  jmp     short loc_1800593B5
0x180059396  mov     rdx, r12
0x180059399  lea     rcx, [rsp+360h+var_2F0]
0x18005939e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800593a4  mov     ebx, eax
0x1800593a6  test    eax, eax
0x1800593a8  js      loc_1800596F7
0x1800593ae  mov     rdx, r13
0x1800593b1  lea     rcx, [rbp+260h+var_2B8]
0x1800593b5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800593bb  mov     ebx, eax
0x1800593bd  test    eax, eax
0x1800593bf  js      loc_1800596F7
0x1800593c5  lea     rcx, [rbp+260h+var_2B8]
0x1800593c9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800593cf  lea     rcx, [rsp+360h+var_2F0]
0x1800593d4  mov     rbx, rax
0x1800593d7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800593dd  mov     r14d, [rbp+260h+dwLogonType]
0x1800593e4  lea     rcx, [rbp+260h+var_240]; this
0x1800593e8  mov     rdx, rax; unsigned __int16 *
0x1800593eb  mov     r9d, r14d; unsigned int
0x1800593ee  mov     r8, rbx; unsigned __int16 *
0x1800593f1  call    ?CreateCacheKey@TOKEN_CACHE_KEY@@QEAAJPEBG0K@Z; TOKEN_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x1800593f6  mov     ebx, eax
0x1800593f8  test    eax, eax
0x1800593fa  js      loc_1800596F7
0x180059400  mov     rcx, [rsp+360h+var_2F8]
0x180059405  lea     r8, [rsp+360h+lpszDomain]
0x18005940a  xor     ebx, ebx
0x18005940c  lea     rdx, [rbp+260h+var_240]
0x180059410  mov     [rsi], rbx
0x180059413  mov     [rsp+360h+lpszDomain], rbx
0x180059418  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18005941e  mov     rcx, [rsp+360h+lpszDomain]; this
0x180059423  mov     [rsi], rcx
0x180059426  test    eax, eax
0x180059428  jnz     short loc_180059469
0x18005942a  lea     r8, [rsp+360h+var_308]; int *
0x18005942f  mov     rdx, r15; unsigned __int16 *
0x180059432  call    ?EqualPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAH@Z; TOKEN_CACHE_ENTRY::EqualPasswordHash(ushort const *,int *)
0x180059437  mov     ebx, eax
0x180059439  test    eax, eax
0x18005943b  jns     short loc_180059451
0x18005943d  mov     rcx, [rsi]; this
0x180059440  call    ?DereferenceCacheEntry@TOKEN_CACHE_ENTRY@@QEAAXXZ; TOKEN_CACHE_ENTRY::DereferenceCacheEntry(void)
0x180059445  mov     qword ptr [rsi], 0
0x18005944c  jmp     loc_1800596F7
0x180059451  cmp     [rsp+360h+var_308], 0
0x180059456  jnz     loc_180059707
0x18005945c  mov     rcx, [rsi]; this
0x18005945f  call    ?DereferenceCacheEntry@TOKEN_CACHE_ENTRY@@QEAAXXZ; TOKEN_CACHE_ENTRY::DereferenceCacheEntry(void)
0x180059464  xor     ebx, ebx
0x180059466  mov     [rsi], rbx
0x180059469  lea     rcx, [rsp+360h+var_2F0]
0x18005946e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180059474  mov     rcx, rax; Str
0x180059477  mov     edx, 40h ; '@'; Ch
0x18005947c  call    cs:__imp_wcschr
0x180059482  lea     rcx, [rbp+260h+var_2B8]
0x180059486  test    rax, rax
0x180059489  jz      loc_180059554
0x18005948f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180059495  lea     rcx, [rsp+360h+var_2F0]
0x18005949a  mov     [rsp+360h+lpszDomain], rax
0x18005949f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800594a5  mov     [rsp+360h+pQuotaLimits], rbx; pQuotaLimits
0x1800594aa  lea     rcx, [rsp+360h+hObject]
0x1800594af  mov     [rsp+360h+pdwProfileLength], rbx; pdwProfileLength
0x1800594b4  lea     rdx, szDomain; lpszDomain
0x1800594bb  mov     [rsp+360h+ppProfileBuffer], rbx; ppProfileBuffer
0x1800594c0  mov     r9d, r14d; dwLogonType
0x1800594c3  mov     [rsp+360h+ppLogonSid], rbx; ppLogonSid
0x1800594c8  mov     r8, r15; lpszPassword
0x1800594cb  mov     [rsp+360h+phToken], rcx; phToken
0x1800594d0  mov     rcx, rax; lpszUsername
0x1800594d3  mov     [rsp+360h+dwLogonProvider], ebx; dwLogonProvider
0x1800594d7  call    cs:__imp_LogonUserExW
0x1800594dd  test    eax, eax
0x1800594df  jnz     loc_1800595CD
0x1800594e5  call    cs:__imp_GetLastError
0x1800594eb  mov     ebx, 775h
0x1800594f0  mov     [rdi], eax
0x1800594f2  cmp     eax, ebx
0x1800594f4  jz      loc_1800595B5
0x1800594fa  cmp     eax, 52Eh
0x1800594ff  jnz     loc_1800595C4
0x180059505  lea     rcx, [rsp+360h+var_2F0]
0x18005950a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180059510  xor     edx, edx
0x180059512  lea     rcx, [rsp+360h+hObject]
0x180059517  mov     [rsp+360h+pQuotaLimits], rdx; pQuotaLimits
0x18005951c  mov     r9d, r14d; dwLogonType
0x18005951f  mov     [rsp+360h+pdwProfileLength], rdx; pdwProfileLength
0x180059524  mov     r8, r15; lpszPassword
0x180059527  mov     [rsp+360h+ppProfileBuffer], rdx; ppProfileBuffer
0x18005952c  mov     [rsp+360h+ppLogonSid], rdx; ppLogonSid
0x180059531  mov     [rsp+360h+phToken], rcx; phToken
0x180059536  mov     rcx, rax; lpszUsername
0x180059539  mov     [rsp+360h+dwLogonProvider], edx; dwLogonProvider
0x18005953d  mov     rdx, [rsp+360h+lpszDomain]; lpszDomain
0x180059542  call    cs:__imp_LogonUserExW
0x180059548  test    eax, eax
0x18005954a  jnz     short loc_1800595CB
0x18005954c  call    cs:__imp_GetLastError
0x180059552  jmp     short loc_1800595AF
0x180059554  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18005955a  lea     rcx, [rsp+360h+var_2F0]
0x18005955f  mov     rbx, rax
0x180059562  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180059568  xor     edx, edx
0x18005956a  lea     rcx, [rsp+360h+hObject]
0x18005956f  mov     [rsp+360h+pQuotaLimits], rdx; pQuotaLimits
0x180059574  mov     r9d, r14d; dwLogonType
0x180059577  mov     [rsp+360h+pdwProfileLength], rdx; pdwProfileLength
0x18005957c  mov     r8, r15; lpszPassword
0x18005957f  mov     [rsp+360h+ppProfileBuffer], rdx; ppProfileBuffer
0x180059584  mov     [rsp+360h+ppLogonSid], rdx; ppLogonSid
0x180059589  mov     [rsp+360h+phToken], rcx; phToken
0x18005958e  mov     rcx, rax; lpszUsername
0x180059591  mov     [rsp+360h+dwLogonProvider], edx; dwLogonProvider
0x180059595  mov     rdx, rbx; lpszDomain
0x180059598  call    cs:__imp_LogonUserExW
0x18005959e  xor     ebx, ebx
0x1800595a0  test    eax, eax
0x1800595a2  jnz     short loc_1800595CD
0x1800595a4  call    cs:__imp_GetLastError
0x1800595aa  mov     ebx, 775h
0x1800595af  mov     [rdi], eax
0x1800595b1  cmp     eax, ebx
0x1800595b3  jnz     short loc_1800595C4
0x1800595b5  mov     rcx, [rsp+360h+var_2F8]
0x1800595ba  lea     rdx, [rbp+260h+var_240]
0x1800595be  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x1800595c4  xor     ebx, ebx
0x1800595c6  jmp     loc_180059707
0x1800595cb  xor     ebx, ebx
0x1800595cd  mov     ecx, 170h; Size
0x1800595d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800595d7  mov     rdi, rax
0x1800595da  test    rax, rax
0x1800595dd  jz      loc_1800596F2
0x1800595e3  lea     rax, ??_7TOKEN_CACHE_ENTRY@@6B@; const TOKEN_CACHE_ENTRY::`vftable'
0x1800595ea  mov     dword ptr [rdi+1Ch], 1
0x1800595f1  lea     rcx, [rdi+20h]
0x1800595f5  mov     [rdi], rax
0x1800595f8  call    cs:__imp_??0CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::CSmallSpinLock(void)
0x1800595fe  lea     rcx, [rdi+28h]
0x180059602  mov     r8d, 40h ; '@'
0x180059608  lea     rdx, [rcx+38h]
0x18005960c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180059612  lea     rdx, [rdi+0E0h]
0x180059619  mov     r8d, 41h ; 'A'
0x18005961f  lea     rcx, [rdi+128h]
0x180059626  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18005962c  lea     rcx, [rbp+260h+var_240]
0x180059630  mov     [rdi+160h], rbx
0x180059637  mov     [rdi+168h], rbx
0x18005963e  mov     dword ptr [rdi+18h], 54433357h
0x180059645  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18005964b  mov     rdx, rax
0x18005964e  lea     rcx, [rdi+28h]
0x180059652  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180059658  xor     edx, edx
0x18005965a  mov     ebx, eax
0x18005965c  test    eax, eax
0x18005965e  js      loc_1800596E8
0x180059664  cmp     r14d, 3
0x180059668  jz      short loc_180059672
0x18005966a  mov     ecx, edx
0x18005966c  cmp     r14d, 8
0x180059670  jnz     short loc_180059677
0x180059672  mov     ecx, 1; this
0x180059677  mov     rax, [rsp+360h+hObject]
0x18005967c  test    rax, rax
0x18005967f  jz      short loc_1800596E3
0x180059681  test    ecx, ecx
0x180059683  jz      short loc_18005968E
0x180059685  mov     [rdi+160h], rax
0x18005968c  jmp     short loc_180059695
0x18005968e  mov     [rdi+168h], rax
0x180059695  lea     r8, [rdi+128h]; struct STRA *
0x18005969c  mov     rdx, r15; unsigned __int16 *
0x18005969f  call    ?GenPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z; TOKEN_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)
0x1800596a4  mov     ebx, eax
0x1800596a6  test    eax, eax
0x1800596a8  js      short loc_1800596E8
0x1800596aa  mov     rcx, [rsp+360h+var_2F8]
0x1800596af  xor     r8d, r8d
0x1800596b2  mov     rdx, rdi
0x1800596b5  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800596bb  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 1
0x1800596c2  jz      short loc_1800596DE
0x1800596c4  mov     rax, [rsp+360h+hObject]
0x1800596c9  mov     r9, r12
0x1800596cc  mov     [rsp+360h+phToken], rax
0x1800596d1  mov     r8, r13
0x1800596d4  mov     qword ptr [rsp+360h+dwLogonProvider], r15
0x1800596d9  call    McTemplateU0zzzp_EtwEventWriteTransfer
0x1800596de  mov     [rsi], rdi
0x1800596e1  jmp     short loc_180059707
0x1800596e3  mov     ebx, 80070057h
0x1800596e8  mov     rcx, rdi; this
0x1800596eb  call    ?DereferenceCacheEntry@TOKEN_CACHE_ENTRY@@QEAAXXZ; TOKEN_CACHE_ENTRY::DereferenceCacheEntry(void)
0x1800596f0  jmp     short loc_1800596F7
0x1800596f2  mov     ebx, 80070008h
0x1800596f7  mov     rcx, [rsp+360h+hObject]; hObject
0x1800596fc  test    rcx, rcx
0x1800596ff  jz      short loc_180059707
0x180059701  call    cs:__imp_CloseHandle
0x180059707  lea     rcx, [rbp+260h+var_2B8]
0x18005970b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180059711  lea     rcx, [rsp+360h+var_2F0]
0x180059716  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005971c  lea     rcx, [rbp+260h+var_280]
0x180059720  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
  ... truncated ...
```
