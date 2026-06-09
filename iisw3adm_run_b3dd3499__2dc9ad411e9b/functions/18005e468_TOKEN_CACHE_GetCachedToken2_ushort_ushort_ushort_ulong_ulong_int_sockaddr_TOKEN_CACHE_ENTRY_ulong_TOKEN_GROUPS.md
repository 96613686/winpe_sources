# TOKEN_CACHE::GetCachedToken2(ushort *,ushort *,ushort *,ulong,ulong,int,sockaddr *,TOKEN_CACHE_ENTRY * *,ulong *,_TOKEN_GROUPS *,THREAD_POOL *)

- ea: `0x18005e468`
- end: `0x18005eaaa`
- name: `?GetCachedToken2@TOKEN_CACHE@@QEAAJPEAG00KKHPEAUsockaddr@@PEAPEAVTOKEN_CACHE_ENTRY@@PEAKPEAU_TOKEN_GROUPS@@PEAVTHREAD_POOL@@@Z`
- size: `1602`
- prototype: `int(TOKEN_CACHE *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, int, struct sockaddr *, struct TOKEN_CACHE_ENTRY **, unsigned int *, struct _TOKEN_GROUPS *, struct THREAD_POOL *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000479c`
- `0x1800362d8`

## callees

- `0x180003e24`
- `0x18005df08`
- `0x18005e1c4`
- `0x18005e468`
- `0x18005ef04`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!wcschr` at `0x18005e5c2`
- `msvcrt!wcschr` at `0x18005e7b4`
- `msvcrt!wcschr` at `0x18005e5c2`
- `msvcrt!wcschr` at `0x18005e7b4`
- `msvcrt!_wcsicmp` at `0x18005e751`
- `msvcrt!_wcsicmp` at `0x18005e766`
- `msvcrt!_wcsicmp` at `0x18005e751`
- `msvcrt!_wcsicmp` at `0x18005e766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e78d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e78d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005e783`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005e783`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ea0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ea0b`
- `iisutil!?Equals@STRA@@QEBA_NAEBV1@@Z` at `0x18005e70e`
- `iisutil!?Equals@STRA@@QEBA_NAEBV1@@Z` at `0x18005e70e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18005e682`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18005e682`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18005e991`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18005e991`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18005e83f`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18005e83f`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18005e9a0`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18005e9a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea3c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea4a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea58`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea7c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea3c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea4a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea58`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005ea7c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18005e6f1`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18005e9cf`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18005e9fb`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18005e6f1`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18005e9cf`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18005e9fb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18005e6c3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18005e71b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18005e6c3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18005e71b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e5f8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e616`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e62d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e90c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e5f8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e616`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e62d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005e90c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e4db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e515`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e541`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e56d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e89a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e4db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e515`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e541`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e56d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005e89a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18005e6a6`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18005e8bb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18005e6a6`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18005e8bb`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18005e5e0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18005e5e0`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18005e855`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18005e855`
- `W3TP!ThreadPoolSetInfo` at `0x18005e7be`
- `W3TP!ThreadPoolSetInfo` at `0x18005e812`
- `W3TP!ThreadPoolSetInfo` at `0x18005e7be`
- `W3TP!ThreadPoolSetInfo` at `0x18005e812`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005ea1b`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005ea1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall TOKEN_CACHE::GetCachedToken2(
        TOKEN_CACHE *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        struct sockaddr *a8,
        struct TOKEN_CACHE_ENTRY **a9,
        unsigned int *a10,
        struct _TOKEN_GROUPS *a11)
{
  TOKEN_CACHE *v14; // rsi
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  const unsigned __int16 *v17; // rdx
  signed int CacheKey; // edi
  unsigned int v19; // r12d
  volatile signed __int32 *v20; // r14
  int Key; // eax
  struct TOKEN_CACHE_ENTRY *v22; // rbx
  TOKEN_CACHE_ENTRY *v23; // rcx
  TOKEN_CACHE_ENTRY *v24; // rsi
  BOOL v25; // ebx
  char *v26; // rsi
  int v27; // r13d
  HANDLE CurrentProcess; // rax
  TOKEN_CACHE *v29; // rcx
  int v30; // ebx
  DWORD LastError; // eax
  char *v32; // rax
  signed int v33; // eax
  _QWORD *v34; // r12
  void *v35; // rbx
  void **v37; // [rsp+38h] [rbp-C8h]
  struct _QUOTA_LIMITS *v38; // [rsp+50h] [rbp-B0h]
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v41; // [rsp+70h] [rbp-90h] BYREF
  PVOID Buffer; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v43; // [rsp+80h] [rbp-80h]
  struct TOKEN_CACHE_ENTRY *v44; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v45[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v46; // [rsp+98h] [rbp-68h]
  struct _TOKEN_GROUPS *v47; // [rsp+A0h] [rbp-60h]
  _BYTE v48[32]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *String2; // [rsp+C8h] [rbp-38h]
  _BYTE v50[32]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v51; // [rsp+100h] [rbp+0h]
  _BYTE v52[56]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v53[64]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v54[32]; // [rsp+190h] [rbp+90h] BYREF
  const unsigned __int16 *v55; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 v56[68]; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int16 v57[32]; // [rsp+250h] [rbp+150h] BYREF
  char v58[80]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v59[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v60[64]; // [rsp+360h] [rbp+260h] BYREF

  v46 = a4;
  v14 = this;
  v43 = a10;
  v47 = a11;
  STRU::STRU((STRU *)v54, v56, 0x40u);
  TokenHandle = 0;
  Buffer = 0;
  v41 = 0;
  memset_0(v57, 0, sizeof(v57));
  STRU::STRU((STRU *)v53, v57, 0x20u);
  memset_0(v59, 0, sizeof(v59));
  STRU::STRU((STRU *)v48, v59, 0x40u);
  memset_0(v60, 0, sizeof(v60));
  STRU::STRU((STRU *)v50, v60, 0x40u);
  if ( !a2 || !a3 || !a4 || !a9 || !a10 )
  {
    STRU::~STRU((STRU *)v50);
    STRU::~STRU((STRU *)v48);
    STRU::~STRU((STRU *)v53);
    STRU::~STRU((STRU *)v54);
    return 2147942487LL;
  }
  v45[1] = 0x7FFFFFFF;
  v45[0] = -1;
  *a9 = 0;
  *a10 = 0;
  if ( !*a3 )
  {
    v15 = wcschr(a2, 0x5Cu);
    v16 = v15;
    v17 = a2;
    if ( v15 )
    {
      CacheKey = STRU::Copy((STRU *)v50, a2, v15 - a2);
      if ( CacheKey < 0 )
        goto LABEL_63;
      v17 = v16 + 1;
    }
    CacheKey = STRU::Copy((STRU *)v48, v17);
    if ( CacheKey >= 0 )
    {
      v14 = this;
      goto LABEL_14;
    }
LABEL_63:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_65;
  }
  CacheKey = STRU::Copy((STRU *)v48, a2);
  if ( CacheKey < 0 )
    goto LABEL_63;
  CacheKey = STRU::Copy((STRU *)v50, a3);
  if ( CacheKey < 0 )
    goto LABEL_63;
LABEL_14:
  v19 = a5;
  CacheKey = TOKEN_CACHE_KEY::CreateCacheKey((TOKEN_CACHE_KEY *)v54, String2, v51, a5, a11);
  if ( CacheKey < 0 )
    goto LABEL_63;
  v20 = 0;
  *a9 = 0;
  v44 = 0;
  Key = CLKRHashTable::FindKey(v14, v54, &v44);
  v22 = v44;
  *a9 = v44;
  if ( Key )
  {
LABEL_23:
    v26 = 0;
    v27 = 1;
    if ( a5 != -2 || _wcsicmp(L"LocalSystem", String2) && _wcsicmp(L"System", String2) )
    {
      wcschr(String2, 0x40u);
      ThreadPoolSetInfo(0, 0);
      v30 = TOKEN_CACHE::LogonUserW(v29, String2, v51, v46, a5, a6, &TokenHandle, v37, &Buffer, &v41, v38, v47);
      ThreadPoolSetInfo(1, 0);
      if ( !v30 )
      {
        LastError = GetLastError();
        *v43 = LastError;
        if ( LastError == 1909 )
          CLKRHashTable::DeleteKey(this, v54);
        CacheKey = 0;
        goto LABEL_56;
      }
    }
    else
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
      {
        *v43 = GetLastError();
        CacheKey = 0;
LABEL_56:
        if ( v20 && _InterlockedExchangeAdd(v20 + 5, 0xFFFFFFFF) == 1 )
        {
          TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v20);
          ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v20);
        }
        if ( CacheKey >= 0 )
          goto LABEL_65;
        if ( v26 && _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 5, 0xFFFFFFFF) == 1 )
        {
          TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v26);
          ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, v26);
        }
        goto LABEL_63;
      }
      v19 = 5;
    }
    v32 = (char *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry);
    v26 = v32;
    v47 = (struct _TOKEN_GROUPS *)v32;
    if ( v32 )
    {
      *((_DWORD *)v32 + 5) = 1;
      *((_QWORD *)v32 + 3) = 0;
      *((_QWORD *)v32 + 4) = 0;
      *((_QWORD *)v32 + 5) = 0;
      *((_QWORD *)v32 + 7) = 0;
      *((_DWORD *)v32 + 33) = 2;
      STRU::STRU((STRU *)(v32 + 136), (unsigned __int16 *)v32 + 96, 0x40u);
      *((_DWORD *)v26 + 80) = 0;
      STRA::STRA((STRA *)(v26 + 328), v26 + 384, 0x44u);
      *((_DWORD *)v26 + 13) = 0x7FFFFFFF;
      *((_DWORD *)v26 + 12) = -1;
      *((_DWORD *)v26 + 4) = 1462977364;
    }
    else
    {
      v26 = 0;
    }
    if ( v26 )
    {
      CacheKey = STRU::Copy((STRU *)(v26 + 136), v55);
      if ( CacheKey >= 0 )
      {
        if ( v19 != 3 && v19 != 8 )
          v27 = 0;
        v34 = (char *)Buffer + 48;
        if ( !Buffer )
          v34 = v45;
        v35 = TokenHandle;
        if ( TokenHandle )
        {
          CacheKey = TOKEN_CACHE_ENTRY::GenPasswordHash((TOKEN_CACHE_ENTRY *)Buffer, v46, (struct STRA *)(v26 + 328));
          if ( CacheKey >= 0 )
          {
            if ( v27 )
              *((_QWORD *)v26 + 3) = v35;
            else
              *((_QWORD *)v26 + 4) = v35;
            *((_QWORD *)v26 + 6) = *v34;
            if ( (*((_BYTE *)this + 104) & 2) != 0 )
            {
              if ( v20 )
                CLKRHashTable::DeleteRecord(this, v20);
              CLKRHashTable::InsertRecord(this, v26, 0);
            }
            *a9 = (struct TOKEN_CACHE_ENTRY *)v26;
          }
        }
        else
        {
          CacheKey = -2147024809;
        }
      }
    }
    else
    {
      v33 = GetLastError();
      CacheKey = v33;
      if ( v33 > 0 )
        CacheKey = (unsigned __int16)v33 | 0x80070000;
    }
    goto LABEL_56;
  }
  STRA::STRA((STRA *)v52, v58, 0x41u);
  CacheKey = TOKEN_CACHE_ENTRY::GenPasswordHash(v23, a4, (struct STRA *)v52);
  if ( CacheKey < 0 )
  {
    STRA::~STRA((STRA *)v52);
    v24 = *a9;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a9 + 5, 0xFFFFFFFF) == 1 && v24 )
    {
      TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(v24);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, v24);
    }
    *a9 = 0;
    goto LABEL_63;
  }
  v25 = STRA::Equals((struct TOKEN_CACHE_ENTRY *)((char *)v22 + 328), (const struct STRA *)v52);
  STRA::~STRA((STRA *)v52);
  CacheKey = 0;
  if ( !v25 )
  {
    v20 = (volatile signed __int32 *)*a9;
    *a9 = 0;
    goto LABEL_23;
  }
LABEL_65:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  STRU::~STRU((STRU *)v50);
  STRU::~STRU((STRU *)v48);
  STRU::~STRU((STRU *)v53);
  STRU::~STRU((STRU *)v54);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x18005e468  push    rbp
0x18005e46a  push    rbx
0x18005e46b  push    rsi
0x18005e46c  push    rdi
0x18005e46d  push    r12
0x18005e46f  push    r13
0x18005e471  push    r14
0x18005e473  push    r15
0x18005e475  lea     rbp, [rsp-2F8h]
0x18005e47d  sub     rsp, 3F8h
0x18005e484  mov     rax, cs:__security_cookie
0x18005e48b  xor     rax, rsp
0x18005e48e  mov     [rbp+330h+var_50], rax
0x18005e495  mov     r13, r9
0x18005e498  mov     [rbp+330h+var_398], r9
0x18005e49c  mov     r14, r8
0x18005e49f  mov     rbx, rdx
0x18005e4a2  mov     rsi, rcx
0x18005e4a5  mov     [rsp+430h+var_3D0], rcx
0x18005e4aa  mov     r15, [rbp+330h+arg_40]
0x18005e4b1  mov     rdi, [rbp+330h+arg_48]
0x18005e4b8  mov     [rbp+330h+var_3B0], rdi
0x18005e4bc  mov     r12, [rbp+330h+arg_50]
0x18005e4c3  mov     [rbp+330h+var_390], r12
0x18005e4c7  mov     r8d, 40h ; '@'
0x18005e4cd  lea     rdx, [rbp+330h+var_268]
0x18005e4d4  lea     rcx, [rbp+330h+var_2A0]
0x18005e4db  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005e4e1  nop
0x18005e4e2  xor     eax, eax
0x18005e4e4  mov     [rsp+430h+TokenHandle], rax
0x18005e4e9  mov     [rsp+430h+Buffer], rax
0x18005e4ee  mov     [rsp+430h+var_3C0], eax
0x18005e4f2  xor     edx, edx; Val
0x18005e4f4  lea     r8d, [rax+40h]; Size
0x18005e4f8  lea     rcx, [rbp+330h+var_1E0]; void *
0x18005e4ff  call    memset_0
0x18005e504  mov     r8d, 20h ; ' '
0x18005e50a  lea     rdx, [rbp+330h+var_1E0]
0x18005e511  lea     rcx, [rbp+330h+var_2E0]
0x18005e515  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005e51b  nop
0x18005e51c  xor     edx, edx; Val
0x18005e51e  mov     r8d, 80h; Size
0x18005e524  lea     rcx, [rbp+330h+var_150]; void *
0x18005e52b  call    memset_0
0x18005e530  mov     r8d, 40h ; '@'
0x18005e536  lea     rdx, [rbp+330h+var_150]
0x18005e53d  lea     rcx, [rbp+330h+var_388]
0x18005e541  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005e547  nop
0x18005e548  xor     edx, edx; Val
0x18005e54a  mov     r8d, 80h; Size
0x18005e550  lea     rcx, [rbp+330h+var_D0]; void *
0x18005e557  call    memset_0
0x18005e55c  mov     r8d, 40h ; '@'
0x18005e562  lea     rdx, [rbp+330h+var_D0]
0x18005e569  lea     rcx, [rbp+330h+var_350]
0x18005e56d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005e573  nop
0x18005e574  xor     eax, eax
0x18005e576  test    rbx, rbx
0x18005e579  jz      loc_18005EA54
0x18005e57f  test    r14, r14
0x18005e582  jz      loc_18005EA54
0x18005e588  test    r13, r13
0x18005e58b  jz      loc_18005EA54
0x18005e591  test    r15, r15
0x18005e594  jz      loc_18005EA54
0x18005e59a  test    rdi, rdi
0x18005e59d  jz      loc_18005EA54
0x18005e5a3  mov     [rbp+330h+var_39C], 7FFFFFFFh
0x18005e5aa  mov     [rbp+330h+var_3A0], 0FFFFFFFFh
0x18005e5b1  mov     [r15], rax
0x18005e5b4  mov     [rdi], eax
0x18005e5b6  cmp     [r14], ax
0x18005e5ba  jnz     short loc_18005E60F
0x18005e5bc  lea     edx, [rax+5Ch]; Ch
0x18005e5bf  mov     rcx, rbx; Str
0x18005e5c2  call    cs:__imp_wcschr
0x18005e5c8  mov     rsi, rax
0x18005e5cb  mov     rdx, rbx
0x18005e5ce  test    rax, rax
0x18005e5d1  jz      short loc_18005E5F4
0x18005e5d3  mov     r8, rax
0x18005e5d6  sub     r8, rbx
0x18005e5d9  sar     r8, 1
0x18005e5dc  lea     rcx, [rbp+330h+var_350]
0x18005e5e0  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18005e5e6  mov     edi, eax
0x18005e5e8  test    eax, eax
0x18005e5ea  js      loc_18005EA01
0x18005e5f0  lea     rdx, [rsi+2]
0x18005e5f4  lea     rcx, [rbp+330h+var_388]
0x18005e5f8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005e5fe  mov     edi, eax
0x18005e600  test    eax, eax
0x18005e602  js      loc_18005EA01
0x18005e608  mov     rsi, [rsp+430h+var_3D0]
0x18005e60d  jmp     short loc_18005E63D
0x18005e60f  mov     rdx, rbx
0x18005e612  lea     rcx, [rbp+330h+var_388]
0x18005e616  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005e61c  mov     edi, eax
0x18005e61e  test    eax, eax
0x18005e620  js      loc_18005EA01
0x18005e626  mov     rdx, r14
0x18005e629  lea     rcx, [rbp+330h+var_350]
0x18005e62d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005e633  mov     edi, eax
0x18005e635  test    eax, eax
0x18005e637  js      loc_18005EA01
0x18005e63d  mov     [rsp+430h+var_410], r12; struct _TOKEN_GROUPS *
0x18005e642  mov     r12d, [rbp+330h+arg_20]
0x18005e649  mov     r9d, r12d; unsigned int
0x18005e64c  mov     r8, [rbp+330h+var_330]; unsigned __int16 *
0x18005e650  mov     rdx, [rbp+330h+String2]; unsigned __int16 *
0x18005e654  lea     rcx, [rbp+330h+var_2A0]; this
0x18005e65b  call    ?CreateCacheKey@TOKEN_CACHE_KEY@@QEAAJPEBG0KPEAU_TOKEN_GROUPS@@@Z; TOKEN_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ulong,_TOKEN_GROUPS *)
0x18005e660  mov     edi, eax
0x18005e662  test    eax, eax
0x18005e664  js      loc_18005EA01
0x18005e66a  xor     r14d, r14d
0x18005e66d  mov     [r15], r14
0x18005e670  mov     [rbp+330h+var_3A8], r14
0x18005e674  lea     r8, [rbp+330h+var_3A8]
0x18005e678  lea     rdx, [rbp+330h+var_2A0]
0x18005e67f  mov     rcx, rsi
0x18005e682  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18005e688  mov     rbx, [rbp+330h+var_3A8]
0x18005e68c  mov     [r15], rbx
0x18005e68f  test    eax, eax
0x18005e691  jnz     loc_18005E735
0x18005e697  lea     r8d, [r14+41h]
0x18005e69b  lea     rdx, [rbp+330h+var_1A0]
0x18005e6a2  lea     rcx, [rbp+330h+var_318]
0x18005e6a6  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18005e6ac  nop
0x18005e6ad  lea     r8, [rbp+330h+var_318]; struct STRA *
0x18005e6b1  mov     rdx, r13; unsigned __int16 *
0x18005e6b4  call    ?GenPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z; TOKEN_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)
0x18005e6b9  mov     edi, eax
0x18005e6bb  test    eax, eax
0x18005e6bd  jns     short loc_18005E703
0x18005e6bf  lea     rcx, [rbp+330h+var_318]
0x18005e6c3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18005e6c9  mov     rsi, [r15]
0x18005e6cc  or      ebx, 0FFFFFFFFh
0x18005e6cf  mov     eax, ebx
0x18005e6d1  lock xadd [rsi+14h], eax
0x18005e6d6  add     eax, ebx
0x18005e6d8  jnz     short loc_18005E6F7
0x18005e6da  test    rsi, rsi
0x18005e6dd  jz      short loc_18005E6F7
0x18005e6df  mov     rcx, rsi; this
0x18005e6e2  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18005e6e7  mov     rdx, rsi
0x18005e6ea  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18005e6f1  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18005e6f7  mov     qword ptr [r15], 0
0x18005e6fe  jmp     loc_18005EA01
0x18005e703  lea     rcx, [rbx+148h]
0x18005e70a  lea     rdx, [rbp+330h+var_318]
0x18005e70e  call    cs:__imp_?Equals@STRA@@QEBA_NAEBV1@@Z; STRA::Equals(STRA const &)
0x18005e714  movzx   ebx, al
0x18005e717  lea     rcx, [rbp+330h+var_318]
0x18005e71b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18005e721  xor     edi, edi
0x18005e723  test    ebx, ebx
0x18005e725  jnz     loc_18005EA11
0x18005e72b  mov     r14, [r15]
0x18005e72e  xor     ebx, ebx
0x18005e730  mov     [r15], rbx
0x18005e733  jmp     short loc_18005E737
0x18005e735  xor     ebx, ebx
0x18005e737  mov     rsi, rbx
0x18005e73a  mov     r13d, 1
0x18005e740  cmp     r12d, 0FFFFFFFEh
0x18005e744  jnz     short loc_18005E7AB
0x18005e746  mov     rdx, [rbp+330h+String2]; String2
0x18005e74a  lea     rcx, aLocalsystem; "LocalSystem"
0x18005e751  call    cs:__imp__wcsicmp
0x18005e757  test    eax, eax
0x18005e759  jz      short loc_18005E770
0x18005e75b  mov     rdx, [rbp+330h+String2]; String2
0x18005e75f  lea     rcx, aSystem; "System"
0x18005e766  call    cs:__imp__wcsicmp
0x18005e76c  test    eax, eax
0x18005e76e  jnz     short loc_18005E7AB
0x18005e770  call    cs:__imp_GetCurrentProcess
0x18005e776  mov     rcx, rax; ProcessHandle
0x18005e779  lea     r8, [rsp+430h+TokenHandle]; TokenHandle
0x18005e77e  mov     edx, 0F01FFh; DesiredAccess
0x18005e783  call    cs:__imp_OpenProcessToken
0x18005e789  test    eax, eax
0x18005e78b  jnz     short loc_18005E7A0
0x18005e78d  call    cs:__imp_GetLastError
0x18005e793  mov     rcx, [rbp+330h+var_3B0]
0x18005e797  mov     [rcx], eax
0x18005e799  mov     edi, ebx
0x18005e79b  jmp     loc_18005E9A9
0x18005e7a0  mov     r12d, 5
0x18005e7a6  jmp     loc_18005E84E
0x18005e7ab  mov     edx, 40h ; '@'; Ch
0x18005e7b0  mov     rcx, [rbp+330h+String2]; Str
0x18005e7b4  call    cs:__imp_wcschr
0x18005e7ba  xor     edx, edx
0x18005e7bc  xor     ecx, ecx
0x18005e7be  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x18005e7c4  mov     rax, [rbp+330h+var_390]
0x18005e7c8  mov     [rsp+430h+var_3D8], rax; struct _TOKEN_GROUPS *
0x18005e7cd  lea     rax, [rsp+430h+var_3C0]
0x18005e7d2  mov     [rsp+430h+var_3E8], rax; unsigned int *
0x18005e7d7  lea     rax, [rsp+430h+Buffer]
0x18005e7dc  mov     [rsp+430h+var_3F0], rax; void **
0x18005e7e1  lea     rax, [rsp+430h+TokenHandle]
0x18005e7e6  mov     [rsp+430h+var_400], rax; void **
0x18005e7eb  mov     eax, [rbp+330h+arg_28]
0x18005e7f1  mov     [rsp+430h+var_408], eax; unsigned int
0x18005e7f5  mov     dword ptr [rsp+430h+var_410], r12d; unsigned int
0x18005e7fa  mov     r9, [rbp+330h+var_398]; unsigned __int16 *
0x18005e7fe  mov     r8, [rbp+330h+var_330]; unsigned __int16 *
0x18005e802  mov     rdx, [rbp+330h+String2]; unsigned __int16 *
0x18005e806  call    ?LogonUserW@TOKEN_CACHE@@QEAAHPEBG00KKPEAPEAX11PEAKPEAU_QUOTA_LIMITS@@PEAU_TOKEN_GROUPS@@@Z; TOKEN_CACHE::LogonUserW(ushort const *,ushort const *,ushort const *,ulong,ulong,void * *,void * *,void * *,ulong *,_QUOTA_LIMITS *,_TOKEN_GROUPS *)
0x18005e80b  mov     ebx, eax
0x18005e80d  xor     edx, edx
0x18005e80f  mov     ecx, r13d
0x18005e812  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x18005e818  test    ebx, ebx
0x18005e81a  jnz     short loc_18005E84C
0x18005e81c  call    cs:__imp_GetLastError
0x18005e822  mov     rcx, [rbp+330h+var_3B0]
0x18005e826  mov     [rcx], eax
0x18005e828  cmp     eax, 775h
0x18005e82d  jnz     short loc_18005E845
0x18005e82f  test    edi, edi
0x18005e831  js      short loc_18005E845
0x18005e833  lea     rdx, [rbp+330h+var_2A0]
0x18005e83a  mov     rcx, [rsp+430h+var_3D0]
0x18005e83f  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x18005e845  xor     edi, edi
0x18005e847  jmp     loc_18005E9A9
0x18005e84c  xor     ebx, ebx
0x18005e84e  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18005e855  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18005e85b  mov     rsi, rax
0x18005e85e  mov     [rbp+330h+var_390], rax
0x18005e862  test    rax, rax
0x18005e865  jz      short loc_18005E8D8
0x18005e867  mov     [rax+14h], r13d
0x18005e86b  mov     [rax+18h], rbx
0x18005e86f  mov     [rax+20h], rbx
0x18005e873  mov     qword ptr [rax+28h], 0
0x18005e87b  mov     [rax+38h], rbx
0x18005e87f  mov     dword ptr [rax+84h], 2
0x18005e889  lea     rcx, [rax+88h]
0x18005e890  lea     rdx, [rcx+38h]
0x18005e894  mov     r8d, 40h ; '@'
0x18005e89a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005e8a0  nop
0x18005e8a1  mov     [rsi+140h], ebx
0x18005e8a7  lea     rdx, [rsi+180h]
0x18005e8ae  lea     rcx, [rsi+148h]
0x18005e8b5  mov     r8d, 44h ; 'D'
0x18005e8bb  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18005e8c1  mov     dword ptr [rsi+34h], 7FFFFFFFh
0x18005e8c8  mov     dword ptr [rsi+30h], 0FFFFFFFFh
0x18005e8cf  mov     dword ptr [rsi+10h], 57334354h
0x18005e8d6  jmp     short loc_18005E8DB
0x18005e8d8  mov     rsi, rbx
0x18005e8db  test    rsi, rsi
0x18005e8de  jnz     short loc_18005E8FE
0x18005e8e0  call    cs:__imp_GetLastError
0x18005e8e6  mov     edi, eax
0x18005e8e8  test    eax, eax
0x18005e8ea  jle     loc_18005E9A9
0x18005e8f0  movzx   edi, ax
0x18005e8f3  or      edi, 80070000h
0x18005e8f9  jmp     loc_18005E9A9
0x18005e8fe  lea     rcx, [rsi+88h]
0x18005e905  mov     rdx, [rbp+330h+var_280]
0x18005e90c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005e912  mov     edi, eax
0x18005e914  test    eax, eax
0x18005e916  js      loc_18005E9A9
0x18005e91c  cmp     r12d, 3
0x18005e920  jz      short loc_18005E92B
0x18005e922  cmp     r12d, 8
0x18005e926  jz      short loc_18005E92B
0x18005e928  mov     r13d, ebx
0x18005e92b  mov     rcx, [rsp+430h+Buffer]; this
0x18005e930  test    rcx, rcx
0x18005e933  lea     r12, [rcx+30h]
0x18005e937  jnz     short loc_18005E93D
0x18005e939  lea     r12, [rbp+330h+var_3A0]
0x18005e93d  mov     rbx, [rsp+430h+TokenHandle]
0x18005e942  test    rbx, rbx
0x18005e945  jnz     short loc_18005E94E
0x18005e947  mov     edi, 80070057h
0x18005e94c  jmp     short loc_18005E9A9
  ... truncated ...
```
