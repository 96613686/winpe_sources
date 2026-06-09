# _CreateOrAcquireUserCacheEntry(int,_GUID *,ushort const *,int,_USER_CACHE_ENTRY * *)

- ea: `0x180032998`
- end: `0x180032ef0`
- name: `?_CreateOrAcquireUserCacheEntry@@YAJHPEAU_GUID@@PEBGHPEAPEAU_USER_CACHE_ENTRY@@@Z`
- size: `1368`
- prototype: `__int64 __fastcall(int, struct _GUID *, const unsigned __int16 *, int, struct _USER_CACHE_ENTRY **)`
- caller_count: `7`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800035b4`
- `0x180011960`
- `0x180017780`
- `0x180037240`
- `0x180048e60`
- `0x180052358`
- `0x1800571b0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x18002fdec`
- `0x1800319ec`
- `0x180032998`
- `0x180032ef8`
- `0x18003308c`
- `0x180042410`
- `0x18004d134`
- `0x18004d1e0`
- `0x180081010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180032b2b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180032b2b`
- `ntdll!RtlReleaseResource` at `0x180032e77`
- `ntdll!RtlReleaseResource` at `0x180032e77`
- `ntdll!RtlDeleteCriticalSection` at `0x180032d25`
- `ntdll!RtlDeleteCriticalSection` at `0x180032d25`
- `ntdll!RtlInitializeCriticalSection` at `0x180032cc3`
- `ntdll!RtlInitializeCriticalSection` at `0x180032cc3`

## string_xrefs

- `0x180032a11`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032a86`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032ae4`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032b58`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032b9a`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032bfb`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032ccf`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032d2b`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032e1b`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180032e30`: `_CreateOrAcquireUserCacheEntry`
- `0x180032b73`: `_LocateUserCacheEntryByNameHash(success)`
- `0x180032bb5`: `Rename operation in progress for this identity`
- `0x180032d46`: `_CreateOrAcquireUserLockEntry`

## pseudocode

```c
__int64 __fastcall _CreateOrAcquireUserCacheEntry(
        int a1,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        struct _USER_CACHE_ENTRY **a5)
{
  __int64 v8; // rdi
  LPCWSTR v9; // r14
  unsigned int HashString; // ebx
  const char *v11; // r9
  const char *v12; // rax
  bool v13; // zf
  struct _USER_LOCK_ENTRY *v14; // rsi
  const char *v15; // rax
  const char *v16; // r9
  struct _USER_CACHE_ENTRY *UserCacheEntryByNameHash; // rax
  const char *v18; // r9
  const char *v19; // r9
  const char *v20; // r9
  __int64 v21; // rax
  volatile signed __int32 *v22; // rbx
  const char *v23; // r9
  const char *v24; // rax
  __int64 *v25; // rax
  const char *v26; // rax
  LPCWSTR lpSrcStr; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-A8h] BYREF
  struct _USER_LOCK_ENTRY *v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[8]; // [rsp+68h] [rbp-98h] BYREF
  volatile signed __int32 *v33; // [rsp+70h] [rbp-90h]
  unsigned __int16 v34[72]; // [rsp+80h] [rbp-80h] BYREF

  v31 = 0;
  v8 = 0;
  v30 = 0;
  v9 = 0;
  lpSrcStr = 0;
  *a5 = 0;
  HashString = DuplicateString(a3, 0, &v30);
  if ( HashString )
  {
    v11 = "";
    while ( 1 )
    {
      v12 = v11--;
      v13 = *v11 == 92;
      if ( *v11 == 92 )
        break;
      if ( v11 <= "onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp" )
      {
        v13 = *v11 == 92;
        break;
      }
    }
    if ( v13 )
      v11 = v12;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v11, 541, "DuplicateString", &Class);
    goto LABEL_9;
  }
  HashString = DuplicateString(a3, 1, (unsigned __int16 **)&lpSrcStr);
  if ( HashString )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v15, 547, "DuplicateString", &Class);
    v9 = lpSrcStr;
LABEL_9:
    v14 = 0;
    goto LABEL_39;
  }
  v9 = lpSrcStr;
  HashString = GetHashString(lpSrcStr, v34);
  if ( HashString )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v16, 552, "GetHashString", &Class);
    goto LABEL_9;
  }
  if ( a1 )
  {
    RtlAcquireResourceExclusive(&g_UserCacheListLock, 1u);
    UserCacheEntryByNameHash = _LocateUserCacheEntryByNameHash(a2, v34);
    *a5 = UserCacheEntryByNameHash;
    if ( UserCacheEntryByNameHash )
    {
      if ( a4 )
      {
        *a5 = 0;
        HashString = -1073741725;
        v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221225571LL,
          v18,
          568,
          "_LocateUserCacheEntryByNameHash(success)",
          &Class);
      }
      else if ( *((_DWORD *)UserCacheEntryByNameHash + 20) )
      {
        *a5 = 0;
        HashString = -1073740682;
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221226614LL,
          v19,
          578,
          "Rename operation in progress for this identity",
          &Class);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)UserCacheEntryByNameHash + 4);
        HashString = 0;
      }
      goto LABEL_9;
    }
  }
  v8 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(376);
  if ( !v8 )
  {
    HashString = -1073741801;
    v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v20, 593, "AllocateLsaHeap", &Class);
    goto LABEL_9;
  }
  LODWORD(lpSrcStr) = 0;
  v21 = utl::make_shared<utl::atomic<unsigned long>,int>(v32, &lpSrcStr);
  utl::shared_ptr<utl::atomic<unsigned long>>::operator=(v8 + 360, v21);
  v22 = v33;
  if ( v33 )
  {
    if ( *((_QWORD *)v33 + 1) == 0x100000001LL )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
LABEL_29:
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      goto LABEL_30;
    }
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( *((_DWORD *)v22 + 3) == 1 || _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        goto LABEL_29;
    }
  }
LABEL_30:
  HashString = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v8 + 32));
  if ( HashString )
  {
    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v23, 601, "RtlInitializeCriticalSection", &Class);
    goto LABEL_9;
  }
  *(_DWORD *)(v8 + 72) = 1;
  HashString = _CreateOrAcquireUserLockEntry(a2, v34, &v31);
  if ( (HashString & 0x80000000) == 0 )
  {
    *(_QWORD *)(v8 + 24) = v31;
    HashString = 0;
    v14 = 0;
    *(struct _GUID *)(v8 + 248) = *a2;
    *(_QWORD *)(v8 + 88) = v30;
    v30 = 0;
    *(_QWORD *)(v8 + 96) = v9;
    v9 = 0;
    RtlStringCchCopyW((unsigned __int16 *)(v8 + 104), 0x41u, v34);
    *(_DWORD *)(v8 + 80) = a4;
    *(union _LARGE_INTEGER *)(v8 + 320) = g_TimeForever;
    *(_DWORD *)(v8 + 348) = 0;
    *(_QWORD *)(v8 + 8) = v8;
    *(_QWORD *)v8 = v8;
    *(_DWORD *)(v8 + 16) = 1;
    *(_DWORD *)(v8 + 76) = 0;
    if ( a1 )
    {
      v25 = (__int64 *)qword_18009ACD8;
      if ( *(struct _LIST_ENTRY **)qword_18009ACD8 != &g_UserCacheList )
        __fastfail(3u);
      *(_QWORD *)v8 = &g_UserCacheList;
      *(_QWORD *)(v8 + 8) = v25;
      *v25 = v8;
      qword_18009ACD8 = v8;
    }
    *(_DWORD *)(v8 + 352) = 0;
    v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", 0, v26, 649, "_CreateOrAcquireUserCacheEntry", *(_QWORD *)(v8 + 96));
    *a5 = (struct _USER_CACHE_ENTRY *)v8;
    v8 = 0;
  }
  else
  {
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v8 + 32));
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v24, 612, "_CreateOrAcquireUserLockEntry", &Class);
    v14 = v31;
  }
LABEL_39:
  _ReleaseUserLockEntry(v14);
  if ( a1 )
    RtlReleaseResource(&g_UserCacheListLock);
  if ( v8 )
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  if ( v30 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v9 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  return HashString;
}

```

## disassembly

```asm
0x180032998  mov     [rsp-8+arg_0], rbx
0x18003299d  push    rbp
0x18003299e  push    rsi
0x18003299f  push    rdi
0x1800329a0  push    r12
0x1800329a2  push    r13
0x1800329a4  push    r14
0x1800329a6  push    r15
0x1800329a8  lea     rbp, [rsp-20h]
0x1800329ad  sub     rsp, 120h
0x1800329b4  mov     rax, cs:__security_cookie
0x1800329bb  xor     rax, rsp
0x1800329be  mov     [rbp+50h+var_40], rax
0x1800329c2  mov     r13d, r9d
0x1800329c5  mov     rsi, r8
0x1800329c8  mov     r15, rdx
0x1800329cb  mov     [rsp+150h+var_108], ecx
0x1800329cf  mov     r12, [rbp+50h+arg_20]
0x1800329d6  xor     eax, eax
0x1800329d8  mov     [rsp+150h+var_110], rax
0x1800329dd  mov     [rsp+150h+var_F0], rax
0x1800329e2  xor     edi, edi
0x1800329e4  mov     [rsp+150h+var_F8], rax
0x1800329e9  xor     r14d, r14d
0x1800329ec  mov     [rsp+150h+lpSrcStr], r14
0x1800329f1  mov     [r12], rax
0x1800329f5  lea     r8, [rsp+150h+var_F8]; unsigned __int16 **
0x1800329fa  xor     edx, edx; int
0x1800329fc  mov     rcx, rsi; Src
0x1800329ff  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180032a04  mov     ebx, eax
0x180032a06  test    eax, eax
0x180032a08  jz      short loc_180032A6C
0x180032a0a  lea     r9, aOnecoreDsExtCl_7+28h; ""
0x180032a11  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032a18  mov     rax, r9
0x180032a1b  dec     r9
0x180032a1e  cmp     byte ptr [r9], 5Ch ; '\'
0x180032a22  jz      short loc_180032A2D
0x180032a24  cmp     r9, rcx
0x180032a27  ja      short loc_180032A18
0x180032a29  cmp     byte ptr [r9], 5Ch ; '\'
0x180032a2d  cmovz   r9, rax
0x180032a31  lea     rax, Class
0x180032a38  mov     [rsp+150h+var_120], rax
0x180032a3d  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x180032a44  mov     [rsp+150h+var_128], rax
0x180032a49  mov     [rsp+150h+var_130], 21Dh
0x180032a51  mov     r8d, ebx
0x180032a54  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180032a5b  xor     ecx, ecx
0x180032a5d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180032a62  mov     rsi, [rsp+150h+var_110]
0x180032a67  jmp     loc_180032E61
0x180032a6c  lea     r8, [rsp+150h+lpSrcStr]; unsigned __int16 **
0x180032a71  mov     edx, 1; int
0x180032a76  mov     rcx, rsi; Src
0x180032a79  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180032a7e  mov     ebx, eax
0x180032a80  xor     esi, esi
0x180032a82  test    eax, eax
0x180032a84  jz      short loc_180032ACD
0x180032a86  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032a8d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032a92  mov     r9, rax
0x180032a95  lea     rax, Class
0x180032a9c  mov     [rsp+150h+var_120], rax
0x180032aa1  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x180032aa8  mov     [rsp+150h+var_128], rax
0x180032aad  mov     [rsp+150h+var_130], 223h
0x180032ab5  mov     r8d, ebx
0x180032ab8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180032abf  xor     ecx, ecx
0x180032ac1  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180032ac6  mov     r14, [rsp+150h+lpSrcStr]
0x180032acb  jmp     short loc_180032A62
0x180032acd  lea     rdx, [rbp+50h+var_D0]; unsigned __int16 *
0x180032ad1  mov     r14, [rsp+150h+lpSrcStr]
0x180032ad6  mov     rcx, r14; lpSrcStr
0x180032ad9  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x180032ade  mov     ebx, eax
0x180032ae0  test    eax, eax
0x180032ae2  jz      short loc_180032B18
0x180032ae4  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032aeb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032af0  mov     r9, rax
0x180032af3  lea     rax, Class
0x180032afa  mov     [rsp+150h+var_120], rax
0x180032aff  lea     rax, aGethashstring; "GetHashString"
0x180032b06  mov     [rsp+150h+var_128], rax
0x180032b0b  mov     [rsp+150h+var_130], 228h
0x180032b13  jmp     loc_180032A51
0x180032b18  cmp     [rsp+150h+var_108], esi
0x180032b1c  jz      loc_180032BD9
0x180032b22  mov     dl, 1; Wait
0x180032b24  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x180032b2b  call    cs:__imp_RtlAcquireResourceExclusive
0x180032b31  lea     rdx, [rbp+50h+var_D0]; unsigned __int16 *
0x180032b35  mov     rcx, r15; struct _GUID *
0x180032b38  call    ?_LocateUserCacheEntryByNameHash@@YAPEAU_USER_CACHE_ENTRY@@PEAU_GUID@@PEBG@Z; _LocateUserCacheEntryByNameHash(_GUID *,ushort const *)
0x180032b3d  mov     [r12], rax
0x180032b41  test    rax, rax
0x180032b44  jz      loc_180032BD9
0x180032b4a  test    r13d, r13d
0x180032b4d  jz      short loc_180032B8C
0x180032b4f  mov     [r12], rsi
0x180032b53  mov     ebx, 0C0000063h
0x180032b58  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032b5f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032b64  mov     r9, rax
0x180032b67  lea     rax, Class
0x180032b6e  mov     [rsp+150h+var_120], rax
0x180032b73  lea     rax, aLocateusercach; "_LocateUserCacheEntryByNameHash(success"...
0x180032b7a  mov     [rsp+150h+var_128], rax
0x180032b7f  mov     [rsp+150h+var_130], 238h
0x180032b87  jmp     loc_180032A51
0x180032b8c  cmp     [rax+50h], esi
0x180032b8f  jz      short loc_180032BCE
0x180032b91  mov     [r12], rsi
0x180032b95  mov     ebx, 0C0000476h
0x180032b9a  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032ba1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032ba6  mov     r9, rax
0x180032ba9  lea     rax, Class
0x180032bb0  mov     [rsp+150h+var_120], rax
0x180032bb5  lea     rax, aRenameOperatio; "Rename operation in progress for this i"...
0x180032bbc  mov     [rsp+150h+var_128], rax
0x180032bc1  mov     [rsp+150h+var_130], 242h
0x180032bc9  jmp     loc_180032A51
0x180032bce  lock inc dword ptr [rax+10h]
0x180032bd2  mov     ebx, esi
0x180032bd4  jmp     loc_180032A62
0x180032bd9  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180032be0  mov     ecx, 178h
0x180032be5  mov     rax, [rax+28h]
0x180032be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bee  mov     rdi, rax
0x180032bf1  test    rax, rax
0x180032bf4  jnz     short loc_180032C2F
0x180032bf6  mov     ebx, 0C0000017h
0x180032bfb  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032c02  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032c07  mov     r9, rax
0x180032c0a  lea     rax, Class
0x180032c11  mov     [rsp+150h+var_120], rax
0x180032c16  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180032c1d  mov     [rsp+150h+var_128], rax
0x180032c22  mov     [rsp+150h+var_130], 251h
0x180032c2a  jmp     loc_180032A51
0x180032c2f  mov     dword ptr [rsp+150h+lpSrcStr], esi
0x180032c33  lea     rdx, [rsp+150h+lpSrcStr]
0x180032c38  lea     rcx, [rsp+150h+var_E8]
0x180032c3d  call    ??$make_shared@U?$atomic@K@utl@@H@utl@@YA?AV?$shared_ptr@U?$atomic@K@utl@@@0@$$QEAH@Z; utl::make_shared<utl::atomic<ulong>,int>(int &&)
0x180032c42  lea     rcx, [rdi+168h]
0x180032c49  mov     rdx, rax
0x180032c4c  call    ??4?$shared_ptr@U?$atomic@K@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<utl::atomic<ulong>>::operator=(utl::shared_ptr<utl::atomic<ulong>> &&)
0x180032c51  nop
0x180032c52  mov     rbx, [rsp+150h+var_E0]
0x180032c57  test    rbx, rbx
0x180032c5a  jz      short loc_180032CBF
0x180032c5c  mov     rax, [rbx+8]
0x180032c60  mov     rcx, 100000001h
0x180032c6a  cmp     rax, rcx
0x180032c6d  jnz     short loc_180032C7F
0x180032c6f  mov     rax, [rbx]
0x180032c72  mov     rcx, rbx
0x180032c75  mov     rax, [rax]
0x180032c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c7d  jmp     short loc_180032CAF
0x180032c7f  or      esi, 0FFFFFFFFh
0x180032c82  mov     eax, esi
0x180032c84  lock xadd [rbx+8], eax
0x180032c89  cmp     eax, 1
0x180032c8c  jnz     short loc_180032CBF
0x180032c8e  mov     rax, [rbx]
0x180032c91  mov     rcx, rbx
0x180032c94  mov     rax, [rax]
0x180032c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c9c  mov     eax, [rbx+0Ch]
0x180032c9f  cmp     eax, 1
0x180032ca2  jz      short loc_180032CAF
0x180032ca4  nop
0x180032ca5  lock xadd [rbx+0Ch], esi
0x180032caa  cmp     esi, 1
0x180032cad  jnz     short loc_180032CBF
0x180032caf  mov     rax, [rbx]
0x180032cb2  mov     rcx, rbx
0x180032cb5  mov     rax, [rax+8]
0x180032cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cbe  nop
0x180032cbf  lea     rcx, [rdi+20h]; CriticalSection
0x180032cc3  call    cs:__imp_RtlInitializeCriticalSection
0x180032cc9  mov     ebx, eax
0x180032ccb  test    eax, eax
0x180032ccd  jz      short loc_180032D03
0x180032ccf  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032cd6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032cdb  mov     r9, rax
0x180032cde  lea     rax, Class
0x180032ce5  mov     [rsp+150h+var_120], rax
0x180032cea  lea     rax, aRtlinitializec; "RtlInitializeCriticalSection"
0x180032cf1  mov     [rsp+150h+var_128], rax
0x180032cf6  mov     [rsp+150h+var_130], 259h
0x180032cfe  jmp     loc_180032A51
0x180032d03  mov     dword ptr [rdi+48h], 1
0x180032d0a  lea     r8, [rsp+150h+var_F0]; struct _USER_LOCK_ENTRY **
0x180032d0f  lea     rdx, [rbp+50h+var_D0]; unsigned __int16 *
0x180032d13  mov     rcx, r15; struct _GUID *
0x180032d16  call    ?_CreateOrAcquireUserLockEntry@@YAJPEAU_GUID@@PEBGPEAPEAU_USER_LOCK_ENTRY@@@Z; _CreateOrAcquireUserLockEntry(_GUID *,ushort const *,_USER_LOCK_ENTRY * *)
0x180032d1b  mov     ebx, eax
0x180032d1d  test    eax, eax
0x180032d1f  jns     short loc_180032D75
0x180032d21  lea     rcx, [rdi+20h]; CriticalSection
0x180032d25  call    cs:__imp_RtlDeleteCriticalSection
0x180032d2b  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032d32  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032d37  mov     r9, rax
0x180032d3a  lea     rax, Class
0x180032d41  mov     [rsp+150h+var_120], rax
0x180032d46  lea     rax, aCreateoracquir_0; "_CreateOrAcquireUserLockEntry"
0x180032d4d  mov     [rsp+150h+var_128], rax
0x180032d52  mov     [rsp+150h+var_130], 264h
0x180032d5a  mov     r8d, ebx
0x180032d5d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180032d64  xor     ecx, ecx
0x180032d66  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180032d6b  mov     rsi, [rsp+150h+var_F0]
0x180032d70  jmp     loc_180032E61
0x180032d75  mov     rax, [rsp+150h+var_F0]
0x180032d7a  mov     [rdi+18h], rax
0x180032d7e  xor     ebx, ebx
0x180032d80  mov     esi, ebx
0x180032d82  movups  xmm0, xmmword ptr [r15]
0x180032d86  movdqu  xmmword ptr [rdi+0F8h], xmm0
0x180032d8e  mov     rax, [rsp+150h+var_F8]
0x180032d93  mov     [rdi+58h], rax
0x180032d97  mov     [rsp+150h+var_F8], rbx
0x180032d9c  mov     [rdi+60h], r14
0x180032da0  mov     r14d, ebx
0x180032da3  lea     rcx, [rdi+68h]; unsigned __int16 *
0x180032da7  lea     r8, [rbp+50h+var_D0]; unsigned __int16 *
0x180032dab  lea     edx, [rbx+41h]; unsigned __int64
0x180032dae  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032db3  mov     [rdi+50h], r13d
0x180032db7  mov     eax, dword ptr cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x180032dbd  mov     [rdi+140h], eax
0x180032dc3  mov     eax, dword ptr cs:?g_TimeForever@@3T_LARGE_INTEGER@@A+4; _LARGE_INTEGER g_TimeForever
0x180032dc9  mov     [rdi+144h], eax
0x180032dcf  mov     [rdi+15Ch], ebx
0x180032dd5  mov     [rdi+8], rdi
0x180032dd9  mov     [rdi], rdi
0x180032ddc  mov     dword ptr [rdi+10h], 1
0x180032de3  mov     [rdi+4Ch], ebx
0x180032de6  cmp     [rsp+150h+var_108], ebx
0x180032dea  jz      short loc_180032E15
0x180032dec  mov     rax, cs:qword_18009ACD8
0x180032df3  lea     rcx, ?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x180032dfa  cmp     [rax], rcx
0x180032dfd  jz      short loc_180032E04
0x180032dff  lea     ecx, [rbx+3]
0x180032e02  int     29h; Win8: RtlFailFast(ecx)
0x180032e04  mov     [rdi], rcx
0x180032e07  mov     [rdi+8], rax
0x180032e0b  mov     [rax], rdi
0x180032e0e  mov     cs:qword_18009ACD8, rdi
0x180032e15  mov     [rdi+160h], ebx
0x180032e1b  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180032e22  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180032e27  mov     rcx, [rdi+60h]
0x180032e2b  mov     [rsp+150h+var_120], rcx
0x180032e30  lea     rcx, aCreateoracquir; "_CreateOrAcquireUserCacheEntry"
0x180032e37  mov     [rsp+150h+var_128], rcx
0x180032e3c  mov     [rsp+150h+var_130], 289h
0x180032e44  mov     r9, rax
0x180032e47  xor     r8d, r8d
0x180032e4a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180032e51  lea     ecx, [r8+2]
0x180032e55  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180032e5a  mov     [r12], rdi
0x180032e5e  mov     rdi, rbx
0x180032e61  mov     rcx, rsi; struct _USER_LOCK_ENTRY *
0x180032e64  call    ?_ReleaseUserLockEntry@@YAXPEAU_USER_LOCK_ENTRY@@@Z; _ReleaseUserLockEntry(_USER_LOCK_ENTRY *)
0x180032e69  cmp     [rsp+150h+var_108], 0
0x180032e6e  jz      short loc_180032E7D
0x180032e70  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x180032e77  call    cs:__imp_RtlReleaseResource
0x180032e7d  test    rdi, rdi
0x180032e80  jz      short loc_180032E95
0x180032e82  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180032e89  mov     rcx, rdi
0x180032e8c  mov     rax, [rax+30h]
0x180032e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e95  mov     rcx, [rsp+150h+var_F8]
0x180032e9a  test    rcx, rcx
0x180032e9d  jz      short loc_180032EAF
0x180032e9f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180032ea6  mov     rax, [rax+30h]
0x180032eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032eaf  test    r14, r14
0x180032eb2  jz      short loc_180032EC7
  ... truncated ...
```
