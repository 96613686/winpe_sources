# TOKEN_CACHE::GetCachedToken2(ushort *,ushort *,ushort *,ulong,ulong,int,sockaddr *,TOKEN_CACHE_ENTRY * *,ulong *,_TOKEN_GROUPS *,THREAD_POOL *)

- ea: `0x18001f394`
- end: `0x18001fbba`
- name: `?GetCachedToken2@TOKEN_CACHE@@QEAAJPEAG00KKHPEAUsockaddr@@PEAPEAVTOKEN_CACHE_ENTRY@@PEAKPEAU_TOKEN_GROUPS@@PEAVTHREAD_POOL@@@Z`
- size: `2086`
- prototype: `__int64 __fastcall(int (__fastcall **this)(struct sockaddr *, __int64, int *), unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, int, struct sockaddr *, struct TOKEN_CACHE_ENTRY **, unsigned int *, struct _TOKEN_GROUPS *, struct THREAD_POOL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18001fbc0`

## callees

- `0x1800022b8`
- `0x18001a77c`
- `0x18001f04c`
- `0x18001f0b8`
- `0x18001f178`
- `0x18001f394`
- `0x18001fec8`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!wcschr` at `0x18001f522`
- `msvcrt!wcschr` at `0x18001f871`
- `msvcrt!wcschr` at `0x18001f522`
- `msvcrt!wcschr` at `0x18001f871`
- `msvcrt!_wcsicmp` at `0x18001f6e0`
- `msvcrt!_wcsicmp` at `0x18001f6f9`
- `msvcrt!_wcsicmp` at `0x18001f6e0`
- `msvcrt!_wcsicmp` at `0x18001f6f9`
- `KERNEL32!GetCurrentProcess` at `0x18001f707`
- `KERNEL32!GetCurrentProcess` at `0x18001f707`
- `KERNEL32!GetLastError` at `0x18001f728`
- `KERNEL32!GetLastError` at `0x18001f94b`
- `KERNEL32!GetLastError` at `0x18001fa00`
- `KERNEL32!GetLastError` at `0x18001fa99`
- `KERNEL32!GetLastError` at `0x18001f728`
- `KERNEL32!GetLastError` at `0x18001f94b`
- `KERNEL32!GetLastError` at `0x18001fa00`
- `KERNEL32!GetLastError` at `0x18001fa99`
- `KERNEL32!CloseHandle` at `0x18001f7a2`
- `KERNEL32!CloseHandle` at `0x18001f7a2`
- `ADVAPI32!OpenProcessToken` at `0x18001f71a`
- `ADVAPI32!OpenProcessToken` at `0x18001f71a`
- `Secur32!LsaFreeReturnBuffer` at `0x18001f7b5`
- `Secur32!LsaFreeReturnBuffer` at `0x18001f7b5`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001f614`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001f614`
- `iisutil!?Equals@STRA@@QEBA_NAEBV1@@Z` at `0x18001f690`
- `iisutil!?Equals@STRA@@QEBA_NAEBV1@@Z` at `0x18001f690`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001f641`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001f6a1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001f641`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001f6a1`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001f671`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001f760`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001f791`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001f671`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001f760`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001f791`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001fb48`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001fb48`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001fb39`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001fb39`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001f5e6`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18001f5e6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f56d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f588`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fac6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f56d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f588`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fac6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001f544`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001f544`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f415`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f458`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f48a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f4bc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f415`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f458`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f48a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f4bc`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001fa72`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001fa72`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18001fa2d`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18001fa2d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f7d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f7e6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f7f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f804`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb5f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb7d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f7d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f7e6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f7f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f804`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb5f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb6e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb7d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fb8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TOKEN_CACHE::GetCachedToken2(
        int (__fastcall **this)(struct sockaddr *, __int64, int *),
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        struct sockaddr *a8,
        struct TOKEN_CACHE_ENTRY **a9,
        unsigned int *a10,
        struct _TOKEN_GROUPS *a11,
        struct THREAD_POOL *a12)
{
  TOKEN_CACHE *v15; // r13
  volatile signed __int32 *v16; // r15
  wchar_t *v17; // rax
  wchar_t *v18; // rsi
  const unsigned __int16 *v19; // rdx
  signed int CacheKey; // edi
  STRU *v21; // rcx
  int Key; // eax
  unsigned __int16 *v23; // rbx
  TOKEN_CACHE_ENTRY *v24; // rcx
  TOKEN_CACHE_ENTRY *v25; // rsi
  BOOL v26; // ebx
  volatile signed __int32 *v27; // rsi
  int v28; // r13d
  HANDLE CurrentProcess; // rax
  unsigned int v31; // r14d
  int (__fastcall *v32)(struct sockaddr *, __int64, int *); // rax
  __int64 v33; // rdx
  wchar_t *v34; // rax
  TOKEN_CACHE *v35; // rcx
  unsigned __int16 *v36; // r8
  OLECHAR *v37; // rax
  __int64 v38; // rax
  int v39; // edx
  __int64 v40; // rax
  unsigned __int16 *v41; // r8
  int v42; // edx
  DWORD v43; // eax
  __int64 v44; // rax
  TOKEN_CACHE_ENTRY *v45; // rax
  signed int LastError; // eax
  union _LARGE_INTEGER *v47; // r9
  struct _TOKEN_GROUPS *v48; // [rsp+20h] [rbp-408h]
  unsigned int v49; // [rsp+28h] [rbp-400h]
  void **v50; // [rsp+38h] [rbp-3F0h]
  struct _QUOTA_LIMITS *v51; // [rsp+50h] [rbp-3D8h]
  struct _TOKEN_GROUPS *v52; // [rsp+58h] [rbp-3D0h]
  unsigned int v54; // [rsp+68h] [rbp-3C0h] BYREF
  int v55; // [rsp+6Ch] [rbp-3BCh] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-3B8h] BYREF
  unsigned int *v57; // [rsp+78h] [rbp-3B0h]
  unsigned __int16 *v58; // [rsp+80h] [rbp-3A8h]
  PVOID Buffer; // [rsp+88h] [rbp-3A0h] BYREF
  unsigned __int16 *v60; // [rsp+90h] [rbp-398h] BYREF
  union _LARGE_INTEGER v61; // [rsp+98h] [rbp-390h] BYREF
  struct sockaddr *v62; // [rsp+A0h] [rbp-388h]
  _BYTE v63[32]; // [rsp+A8h] [rbp-380h] BYREF
  wchar_t *String2; // [rsp+C8h] [rbp-360h]
  _BYTE v65[32]; // [rsp+E0h] [rbp-348h] BYREF
  unsigned __int16 *v66; // [rsp+100h] [rbp-328h]
  _BYTE v67[56]; // [rsp+118h] [rbp-310h] BYREF
  _BYTE v68[64]; // [rsp+150h] [rbp-2D8h] BYREF
  _BYTE v69[32]; // [rsp+190h] [rbp-298h] BYREF
  const unsigned __int16 *v70; // [rsp+1B0h] [rbp-278h]
  unsigned __int16 v71[68]; // [rsp+1C8h] [rbp-260h] BYREF
  unsigned __int16 v72[32]; // [rsp+250h] [rbp-1D8h] BYREF
  char v73[80]; // [rsp+290h] [rbp-198h] BYREF
  unsigned __int16 v74[64]; // [rsp+2E0h] [rbp-148h] BYREF
  unsigned __int16 v75[64]; // [rsp+360h] [rbp-C8h] BYREF

  v58 = a4;
  v15 = (TOKEN_CACHE *)this;
  v62 = a8;
  v57 = a10;
  STRU::STRU((STRU *)v69, v71, 0x40u);
  TokenHandle = 0;
  Buffer = 0;
  v54 = 0;
  memset_0(v72, 0, sizeof(v72));
  STRU::STRU((STRU *)v68, v72, 0x20u);
  memset_0(v74, 0, sizeof(v74));
  STRU::STRU((STRU *)v63, v74, 0x40u);
  memset_0(v75, 0, sizeof(v75));
  STRU::STRU((STRU *)v65, v75, 0x40u);
  v55 = 0;
  if ( !a2 || !a3 || !a4 || (v16 = 0, !a9) || !a10 )
  {
    STRU::~STRU(v65);
    STRU::~STRU(v63);
    STRU::~STRU(v68);
    STRU::~STRU(v69);
    return 2147942487LL;
  }
  v61.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  *a9 = 0;
  *a10 = 0;
  if ( *a3 )
  {
    CacheKey = STRU::Copy((STRU *)v63, a2);
    if ( CacheKey < 0 )
      goto LABEL_37;
    v19 = a3;
    v21 = (STRU *)v65;
  }
  else
  {
    v17 = wcschr(a2, 0x5Cu);
    v18 = v17;
    v19 = a2;
    if ( v17 )
    {
      CacheKey = STRU::Copy((STRU *)v65, a2, v17 - a2);
      if ( CacheKey < 0 )
        goto LABEL_37;
      v19 = v18 + 1;
    }
    v21 = (STRU *)v63;
  }
  CacheKey = STRU::Copy(v21, v19);
  if ( CacheKey < 0
    || (CacheKey = TOKEN_CACHE_KEY::CreateCacheKey((TOKEN_CACHE_KEY *)v69, String2, v66, a5, v48), CacheKey < 0) )
  {
LABEL_37:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_39;
  }
  *a9 = 0;
  v60 = 0;
  Key = CLKRHashTable::FindKey(v15, v69, &v60);
  v23 = v60;
  *a9 = (struct TOKEN_CACHE_ENTRY *)v60;
  if ( Key )
  {
LABEL_23:
    v27 = 0;
    v28 = 1;
    if ( a5 == -2 && (!_wcsicmp(L"LocalSystem", String2) || !_wcsicmp(L"System", String2)) )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
      {
LABEL_27:
        *v57 = GetLastError();
LABEL_28:
        CacheKey = 0;
        goto LABEL_29;
      }
      v31 = 5;
LABEL_89:
      v45 = (TOKEN_CACHE_ENTRY *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry);
      v62 = (struct sockaddr *)v45;
      if ( v45 )
        v27 = (volatile signed __int32 *)TOKEN_CACHE_ENTRY::TOKEN_CACHE_ENTRY(v45);
      else
        v27 = 0;
      if ( v27 )
      {
        CacheKey = STRU::Copy((STRU *)(v27 + 34), v70);
        if ( CacheKey >= 0 )
        {
          if ( v31 != 3 && v31 != 8 )
            v28 = 0;
          v47 = (union _LARGE_INTEGER *)((char *)Buffer + 48);
          if ( !Buffer )
            v47 = &v61;
          CacheKey = TOKEN_CACHE_ENTRY::Create((TOKEN_CACHE_ENTRY *)v27, TokenHandle, v58, v47, v28);
          v15 = (TOKEN_CACHE *)this;
          if ( CacheKey >= 0 )
          {
            if ( ((_BYTE)this[13] & 2) != 0 )
            {
              if ( v16 )
                CLKRHashTable::DeleteRecord(this, v16);
              CLKRHashTable::InsertRecord(this, v27, 0);
            }
            *a9 = (struct TOKEN_CACHE_ENTRY *)v27;
          }
          goto LABEL_30;
        }
      }
      else
      {
        LastError = GetLastError();
        CacheKey = LastError;
        if ( LastError > 0 )
          CacheKey = (unsigned __int16)LastError | 0x80070000;
      }
LABEL_29:
      v15 = (TOKEN_CACHE *)this;
LABEL_30:
      if ( v16 && _InterlockedExchangeAdd(v16 + 5, 0xFFFFFFFF) == 1 )
      {
        TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v16);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v16);
      }
      if ( CacheKey >= 0 )
        goto LABEL_39;
      if ( v27 && _InterlockedExchangeAdd(v27 + 5, 0xFFFFFFFF) == 1 )
      {
        TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v27);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v27);
      }
      goto LABEL_37;
    }
    if ( v62 )
    {
      v32 = this[16];
      if ( v32 )
      {
        if ( v62->sa_family == 2 )
        {
          v33 = 16;
        }
        else
        {
          if ( v62->sa_family != 23 )
            goto LABEL_52;
          v33 = 28;
        }
        if ( v32(v62, v33, &v55) < 0 )
          goto LABEL_27;
      }
    }
LABEL_52:
    v34 = wcschr(String2, 0x40u);
    v35 = 0;
    if ( v34 && a7 )
    {
      if ( *((_DWORD *)this + 27) )
      {
        v36 = v66;
        v37 = (OLECHAR *)&WideCharStr;
      }
      else
      {
        v36 = (unsigned __int16 *)&WideCharStr;
        v37 = v66;
      }
      v60 = v37;
      if ( a12 )
      {
        v38 = *(_QWORD *)a12;
      }
      else
      {
        if ( !g_pThreadPool )
          goto LABEL_62;
        v38 = *(_QWORD *)g_pThreadPool;
      }
      _InterlockedAdd((volatile signed __int32 *)(v38 + 56), 1u);
LABEL_62:
      v39 = TOKEN_CACHE::LogonUserW(0, String2, v36, v58, a5, v49, &TokenHandle, v50, &Buffer, &v54, v51, v52);
      if ( a12 )
      {
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)a12 + 56LL), 0xFFFFFFFF);
      }
      else if ( g_pThreadPool )
      {
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)g_pThreadPool + 56LL), 0xFFFFFFFF);
      }
      if ( v39 )
        goto LABEL_88;
      v35 = (TOKEN_CACHE *)GetLastError();
      *v57 = (unsigned int)v35;
      if ( (_DWORD)v35 == 1909 )
        goto LABEL_81;
      if ( (_DWORD)v35 != 1326 )
        goto LABEL_28;
      if ( a12 )
      {
        v40 = *(_QWORD *)a12;
      }
      else
      {
        if ( !g_pThreadPool )
        {
LABEL_74:
          v41 = v60;
          goto LABEL_75;
        }
        v40 = *(_QWORD *)g_pThreadPool;
      }
      _InterlockedAdd((volatile signed __int32 *)(v40 + 56), 1u);
      goto LABEL_74;
    }
    if ( a12 )
    {
      v44 = *(_QWORD *)a12;
    }
    else
    {
      if ( !g_pThreadPool )
      {
LABEL_87:
        v41 = v66;
LABEL_75:
        v42 = TOKEN_CACHE::LogonUserW(v35, String2, v41, v58, a5, v49, &TokenHandle, v50, &Buffer, &v54, v51, v52);
        if ( a12 )
        {
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)a12 + 56LL), 0xFFFFFFFF);
        }
        else if ( g_pThreadPool )
        {
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)g_pThreadPool + 56LL), 0xFFFFFFFF);
        }
        if ( !v42 )
        {
          v43 = GetLastError();
          *v57 = v43;
          if ( v43 != 1909 )
            goto LABEL_28;
LABEL_81:
          CLKRHashTable::DeleteKey(this, v69);
          goto LABEL_28;
        }
LABEL_88:
        v31 = a5;
        goto LABEL_89;
      }
      v44 = *(_QWORD *)g_pThreadPool;
    }
    _InterlockedAdd((volatile signed __int32 *)(v44 + 56), 1u);
    goto LABEL_87;
  }
  STRA::STRA((STRA *)v67, v73, 0x41u);
  CacheKey = TOKEN_CACHE_ENTRY::GenPasswordHash(v24, v58, (struct STRA *)v67);
  if ( CacheKey < 0 )
  {
    STRA::~STRA((STRA *)v67);
    v25 = *a9;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a9 + 5, 0xFFFFFFFF) == 1 && v25 )
    {
      TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(v25);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, v25);
    }
    *a9 = 0;
    goto LABEL_37;
  }
  v26 = STRA::Equals((STRA *)(v23 + 164), (const struct STRA *)v67);
  STRA::~STRA((STRA *)v67);
  CacheKey = 0;
  if ( !v26 )
  {
    v16 = (volatile signed __int32 *)*a9;
    *a9 = 0;
    goto LABEL_23;
  }
LABEL_39:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v55 )
    (*((void (**)(void))v15 + 17))();
  STRU::~STRU(v65);
  STRU::~STRU(v63);
  STRU::~STRU(v68);
  STRU::~STRU(v69);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x18001f394  push    rbx
0x18001f396  push    rsi
0x18001f397  push    rdi
0x18001f398  push    r12
0x18001f39a  push    r13
0x18001f39c  push    r14
0x18001f39e  push    r15
0x18001f3a0  sub     rsp, 3F0h
0x18001f3a7  mov     rax, cs:__security_cookie
0x18001f3ae  xor     rax, rsp
0x18001f3b1  mov     [rsp+428h+var_48], rax
0x18001f3b9  mov     r15, r9
0x18001f3bc  mov     [rsp+428h+var_3A8], r9
0x18001f3c4  mov     rsi, r8
0x18001f3c7  mov     rbx, rdx
0x18001f3ca  mov     r13, rcx
0x18001f3cd  mov     [rsp+428h+var_3C8], rcx
0x18001f3d2  mov     r14, [rsp+428h+arg_58]
0x18001f3da  mov     rax, [rsp+428h+arg_38]
0x18001f3e2  mov     [rsp+428h+var_388], rax
0x18001f3ea  mov     r12, [rsp+428h+arg_40]
0x18001f3f2  mov     rdi, [rsp+428h+arg_48]
0x18001f3fa  mov     [rsp+428h+var_3B0], rdi
0x18001f3ff  mov     r8d, 40h ; '@'
0x18001f405  lea     rdx, [rsp+428h+var_260]
0x18001f40d  lea     rcx, [rsp+428h+var_298]
0x18001f415  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f41b  nop
0x18001f41c  xor     eax, eax
0x18001f41e  mov     [rsp+428h+TokenHandle], rax
0x18001f423  mov     [rsp+428h+Buffer], rax
0x18001f42b  mov     [rsp+428h+var_3C0], eax
0x18001f42f  xor     edx, edx; Val
0x18001f431  lea     r8d, [rax+40h]; Size
0x18001f435  lea     rcx, [rsp+428h+var_1D8]; void *
0x18001f43d  call    memset_0
0x18001f442  mov     r8d, 20h ; ' '
0x18001f448  lea     rdx, [rsp+428h+var_1D8]
0x18001f450  lea     rcx, [rsp+428h+var_2D8]
0x18001f458  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f45e  nop
0x18001f45f  xor     edx, edx; Val
0x18001f461  mov     r8d, 80h; Size
0x18001f467  lea     rcx, [rsp+428h+var_148]; void *
0x18001f46f  call    memset_0
0x18001f474  mov     r8d, 40h ; '@'
0x18001f47a  lea     rdx, [rsp+428h+var_148]
0x18001f482  lea     rcx, [rsp+428h+var_380]
0x18001f48a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f490  nop
0x18001f491  xor     edx, edx; Val
0x18001f493  mov     r8d, 80h; Size
0x18001f499  lea     rcx, [rsp+428h+var_C8]; void *
0x18001f4a1  call    memset_0
0x18001f4a6  mov     r8d, 40h ; '@'
0x18001f4ac  lea     rdx, [rsp+428h+var_C8]
0x18001f4b4  lea     rcx, [rsp+428h+var_348]
0x18001f4bc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f4c2  nop
0x18001f4c3  xor     eax, eax
0x18001f4c5  mov     [rsp+428h+var_3BC], eax
0x18001f4c9  test    rbx, rbx
0x18001f4cc  jz      loc_18001FB57
0x18001f4d2  test    rsi, rsi
0x18001f4d5  jz      loc_18001FB57
0x18001f4db  test    r15, r15
0x18001f4de  jz      loc_18001FB57
0x18001f4e4  xor     r15d, r15d
0x18001f4e7  test    r12, r12
0x18001f4ea  jz      loc_18001FB57
0x18001f4f0  test    rdi, rdi
0x18001f4f3  jz      loc_18001FB57
0x18001f4f9  mov     dword ptr [rsp+428h+var_390+4], 7FFFFFFFh
0x18001f504  mov     dword ptr [rsp+428h+var_390], 0FFFFFFFFh
0x18001f50f  mov     [r12], r15
0x18001f513  mov     [rdi], r15d
0x18001f516  cmp     [rsi], r15w
0x18001f51a  jnz     short loc_18001F562
0x18001f51c  lea     edx, [rax+5Ch]; Ch
0x18001f51f  mov     rcx, rbx; Str
0x18001f522  call    cs:__imp_wcschr
0x18001f528  mov     rsi, rax
0x18001f52b  mov     rdx, rbx
0x18001f52e  test    rax, rax
0x18001f531  jz      short loc_18001F558
0x18001f533  mov     r8, rax
0x18001f536  sub     r8, rbx
0x18001f539  sar     r8, 1
0x18001f53c  lea     rcx, [rsp+428h+var_348]
0x18001f544  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001f54a  mov     edi, eax
0x18001f54c  test    eax, eax
0x18001f54e  js      loc_18001F798
0x18001f554  lea     rdx, [rsi+2]
0x18001f558  lea     rcx, [rsp+428h+var_380]
0x18001f560  jmp     short loc_18001F588
0x18001f562  mov     rdx, rbx
0x18001f565  lea     rcx, [rsp+428h+var_380]
0x18001f56d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f573  mov     edi, eax
0x18001f575  test    eax, eax
0x18001f577  js      loc_18001F798
0x18001f57d  mov     rdx, rsi
0x18001f580  lea     rcx, [rsp+428h+var_348]
0x18001f588  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f58e  mov     edi, eax
0x18001f590  test    eax, eax
0x18001f592  js      loc_18001F798
0x18001f598  mov     r9d, [rsp+428h+arg_20]; unsigned int
0x18001f5a0  mov     r8, [rsp+428h+var_328]; unsigned __int16 *
0x18001f5a8  mov     rdx, [rsp+428h+String2]; unsigned __int16 *
0x18001f5b0  lea     rcx, [rsp+428h+var_298]; this
0x18001f5b8  call    ?CreateCacheKey@TOKEN_CACHE_KEY@@QEAAJPEBG0KPEAU_TOKEN_GROUPS@@@Z; TOKEN_CACHE_KEY::CreateCacheKey(ushort const *,ushort const *,ulong,_TOKEN_GROUPS *)
0x18001f5bd  mov     edi, eax
0x18001f5bf  test    eax, eax
0x18001f5c1  js      loc_18001F798
0x18001f5c7  mov     [r12], r15
0x18001f5cb  mov     [rsp+428h+var_398], r15
0x18001f5d3  lea     r8, [rsp+428h+var_398]
0x18001f5db  lea     rdx, [rsp+428h+var_298]
0x18001f5e3  mov     rcx, r13
0x18001f5e6  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18001f5ec  mov     rbx, [rsp+428h+var_398]
0x18001f5f4  mov     [r12], rbx
0x18001f5f8  test    eax, eax
0x18001f5fa  jnz     loc_18001F6BA
0x18001f600  lea     r8d, [rax+41h]
0x18001f604  lea     rdx, [rsp+428h+var_198]
0x18001f60c  lea     rcx, [rsp+428h+var_310]
0x18001f614  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18001f61a  nop
0x18001f61b  lea     r8, [rsp+428h+var_310]; struct STRA *
0x18001f623  mov     rdx, [rsp+428h+var_3A8]; unsigned __int16 *
0x18001f62b  call    ?GenPasswordHash@TOKEN_CACHE_ENTRY@@QEAAJPEBGPEAVSTRA@@@Z; TOKEN_CACHE_ENTRY::GenPasswordHash(ushort const *,STRA *)
0x18001f630  mov     edi, eax
0x18001f632  xor     r15d, r15d
0x18001f635  test    eax, eax
0x18001f637  jns     short loc_18001F681
0x18001f639  lea     rcx, [rsp+428h+var_310]
0x18001f641  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001f647  mov     rsi, [r12]
0x18001f64b  or      ebx, 0FFFFFFFFh
0x18001f64e  mov     eax, ebx
0x18001f650  lock xadd [rsi+14h], eax
0x18001f655  add     eax, ebx
0x18001f657  jnz     short loc_18001F678
0x18001f659  test    rsi, rsi
0x18001f65c  jz      short loc_18001F678
0x18001f65e  mov     rcx, rsi; this
0x18001f661  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18001f666  nop
0x18001f667  mov     rdx, rsi
0x18001f66a  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001f671  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001f677  nop
0x18001f678  mov     [r12], r15
0x18001f67c  jmp     loc_18001F798
0x18001f681  lea     rcx, [rbx+148h]
0x18001f688  lea     rdx, [rsp+428h+var_310]
0x18001f690  call    cs:__imp_?Equals@STRA@@QEBA_NAEBV1@@Z; STRA::Equals(STRA const &)
0x18001f696  movzx   ebx, al
0x18001f699  lea     rcx, [rsp+428h+var_310]
0x18001f6a1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001f6a7  mov     edi, r15d
0x18001f6aa  test    ebx, ebx
0x18001f6ac  jnz     loc_18001F7A8
0x18001f6b2  mov     r15, [r12]
0x18001f6b6  mov     [r12], rdi
0x18001f6ba  xor     esi, esi
0x18001f6bc  or      ebx, 0FFFFFFFFh
0x18001f6bf  lea     r13d, [rsi+1]
0x18001f6c3  cmp     [rsp+428h+arg_20], 0FFFFFFFEh
0x18001f6cb  jnz     loc_18001F81C
0x18001f6d1  mov     rdx, [rsp+428h+String2]; String2
0x18001f6d9  lea     rcx, aLocalsystem; "LocalSystem"
0x18001f6e0  call    cs:__imp__wcsicmp
0x18001f6e6  test    eax, eax
0x18001f6e8  jz      short loc_18001F707
0x18001f6ea  mov     rdx, [rsp+428h+String2]; String2
0x18001f6f2  lea     rcx, aSystem; "System"
0x18001f6f9  call    cs:__imp__wcsicmp
0x18001f6ff  test    eax, eax
0x18001f701  jnz     loc_18001F81C
0x18001f707  call    cs:__imp_GetCurrentProcess
0x18001f70d  mov     rcx, rax; ProcessHandle
0x18001f710  lea     r8, [rsp+428h+TokenHandle]; TokenHandle
0x18001f715  mov     edx, 0F01FFh; DesiredAccess
0x18001f71a  call    cs:__imp_OpenProcessToken
0x18001f720  test    eax, eax
0x18001f722  jnz     loc_18001F811
0x18001f728  call    cs:__imp_GetLastError
0x18001f72e  mov     rcx, [rsp+428h+var_3B0]
0x18001f733  mov     [rcx], eax
0x18001f735  xor     edi, edi
0x18001f737  mov     r13, [rsp+428h+var_3C8]
0x18001f73c  test    r15, r15
0x18001f73f  jz      short loc_18001F767
0x18001f741  mov     eax, ebx
0x18001f743  lock xadd [r15+14h], eax
0x18001f749  add     eax, ebx
0x18001f74b  jnz     short loc_18001F767
0x18001f74d  mov     rcx, r15; this
0x18001f750  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18001f755  nop
0x18001f756  mov     rdx, r15
0x18001f759  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001f760  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001f766  nop
0x18001f767  xor     r15d, r15d
0x18001f76a  test    edi, edi
0x18001f76c  jns     short loc_18001F7A8
0x18001f76e  test    rsi, rsi
0x18001f771  jz      short loc_18001F798
0x18001f773  mov     eax, ebx
0x18001f775  lock xadd [rsi+14h], eax
0x18001f77a  add     eax, ebx
0x18001f77c  jnz     short loc_18001F798
0x18001f77e  mov     rcx, rsi; this
0x18001f781  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18001f786  nop
0x18001f787  mov     rdx, rsi
0x18001f78a  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001f791  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001f797  nop
0x18001f798  mov     rcx, [rsp+428h+TokenHandle]; hObject
0x18001f79d  test    rcx, rcx
0x18001f7a0  jz      short loc_18001F7A8
0x18001f7a2  call    cs:__imp_CloseHandle
0x18001f7a8  mov     rcx, [rsp+428h+Buffer]; Buffer
0x18001f7b0  test    rcx, rcx
0x18001f7b3  jz      short loc_18001F7BB
0x18001f7b5  call    cs:__imp_LsaFreeReturnBuffer
0x18001f7bb  cmp     [rsp+428h+var_3BC], r15d
0x18001f7c0  jz      short loc_18001F7CF
0x18001f7c2  mov     rax, [r13+88h]
0x18001f7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7ce  nop
0x18001f7cf  lea     rcx, [rsp+428h+var_348]
0x18001f7d7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f7dd  nop
0x18001f7de  lea     rcx, [rsp+428h+var_380]
0x18001f7e6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f7ec  nop
0x18001f7ed  lea     rcx, [rsp+428h+var_2D8]
0x18001f7f5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f7fb  nop
0x18001f7fc  lea     rcx, [rsp+428h+var_298]
0x18001f804  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f80a  mov     eax, edi
0x18001f80c  jmp     loc_18001FB97
0x18001f811  mov     r14d, 5
0x18001f817  jmp     loc_18001FA6B
0x18001f81c  mov     rcx, [rsp+428h+var_388]
0x18001f824  test    rcx, rcx
0x18001f827  jz      short loc_18001F864
0x18001f829  mov     rax, [rsp+428h+var_3C8]
0x18001f82e  mov     rax, [rax+80h]
0x18001f835  test    rax, rax
0x18001f838  jz      short loc_18001F864
0x18001f83a  cmp     word ptr [rcx], 2
0x18001f83e  jnz     short loc_18001F847
0x18001f840  mov     edx, 10h
0x18001f845  jmp     short loc_18001F852
0x18001f847  cmp     word ptr [rcx], 17h
0x18001f84b  jnz     short loc_18001F864
0x18001f84d  mov     edx, 1Ch
0x18001f852  lea     r8, [rsp+428h+var_3BC]
0x18001f857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f85c  test    eax, eax
0x18001f85e  js      loc_18001F728
0x18001f864  mov     edx, 40h ; '@'; Ch
0x18001f869  mov     rcx, [rsp+428h+String2]; Str
0x18001f871  call    cs:__imp_wcschr
0x18001f877  xor     ecx, ecx; this
0x18001f879  test    rax, rax
0x18001f87c  jz      loc_18001FA38
0x18001f882  cmp     [rsp+428h+arg_30], ecx
0x18001f889  jz      loc_18001FA38
0x18001f88f  mov     rax, [rsp+428h+var_3C8]
0x18001f894  cmp     [rax+6Ch], ecx
0x18001f897  jnz     short loc_18001F8AA
0x18001f899  lea     r8, WideCharStr
0x18001f8a0  mov     rax, [rsp+428h+var_328]
0x18001f8a8  jmp     short loc_18001F8B9
0x18001f8aa  mov     r8, [rsp+428h+var_328]; unsigned __int16 *
0x18001f8b2  lea     rax, WideCharStr
0x18001f8b9  mov     [rsp+428h+var_398], rax
0x18001f8c1  test    r14, r14
0x18001f8c4  jnz     short loc_18001F8D7
0x18001f8c6  mov     rax, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; THREAD_POOL * g_pThreadPool
0x18001f8cd  test    rax, rax
0x18001f8d0  jz      short loc_18001F8DF
0x18001f8d2  mov     rax, [rax]
0x18001f8d5  jmp     short loc_18001F8DA
0x18001f8d7  mov     rax, [r14]
0x18001f8da  lock add [rax+38h], r13d
0x18001f8df  lea     rax, [rsp+428h+var_3C0]
0x18001f8e4  mov     [rsp+428h+var_3E0], rax; unsigned int *
0x18001f8e9  lea     rax, [rsp+428h+Buffer]
0x18001f8f1  mov     [rsp+428h+var_3E8], rax; void **
  ... truncated ...
```
