# WorkThreadManager::s_QueuePoolTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *)

- ea: `0x180004950`
- end: `0x180004fc3`
- name: `?s_QueuePoolTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@@Z`
- size: `1651`
- prototype: `static int __high(enum Windows::Internal::TaskApartment, enum Windows::Internal::TaskOptions, unsigned int, struct Windows::Internal::IComPoolTask *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003310`
- `0x180032958`

## callees

- `0x180001710`
- `0x180004950`
- `0x1800092c0`
- `0x18000a0ac`
- `0x18000bbc4`
- `0x18000c548`
- `0x180011df4`
- `0x180012667`
- `0x180012673`
- `0x1800318c0`
- `0x18003288c`
- `0x180032b10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180004d9f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180004d9f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004e6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004e6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800049c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800049c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004a66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004b56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004c08`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004d26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004e26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004f1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004a66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004b56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004c08`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004d26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004e26`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004bac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004eb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004bac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ea7`

## string_xrefs

- `0x1800049e9`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180004ad7`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180004cb3`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180004db3`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::s_QueuePoolTask(unsigned int a1, unsigned int a2, unsigned int a3, DWORD *a4)
{
  HANDLE v8; // rbx
  wil::details *v9; // rcx
  HANDLE Event; // rdi
  int LastErrorFailHr; // eax
  unsigned int v12; // edi
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  HMODULE v16; // rcx
  int v18; // eax
  unsigned int v19; // esi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rdi
  HMODULE v23; // rcx
  unsigned int v24; // r8d
  const char *v25; // r9
  DWORD LastError; // edi
  _QWORD *v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // rdi
  HMODULE v30; // rcx
  HANDLE v31; // r14
  DWORD v32; // eax
  unsigned int v33; // r8d
  const char *v34; // r9
  signed int v35; // eax
  void *v36; // rdi
  DWORD v37; // r15d
  unsigned int v38; // r8d
  const char *v39; // r9
  _QWORD *v40; // rax
  __int64 v41; // rcx
  _QWORD *v42; // rdi
  HMODULE v43; // rcx
  unsigned int v44; // r8d
  const char *v45; // r9
  HRESULT v46; // eax
  _QWORD *v47; // rcx
  __int64 v48; // rax
  _QWORD *v49; // rdi
  HMODULE v50; // rcx
  unsigned int v51; // r8d
  const char *v52; // r9
  DWORD v53; // eax
  unsigned int v54; // r8d
  const char *v55; // r9
  HANDLE v56; // rdi
  DWORD v57; // esi
  unsigned int v58; // r8d
  const char *v59; // r9
  _QWORD *v60; // rax
  __int64 v61; // rcx
  _QWORD *v62; // rbx
  HMODULE v63; // rcx
  LPDWORD lpdwindex; // [rsp+20h] [rbp-48h]
  _QWORD *v65; // [rsp+28h] [rbp-40h]
  HANDLE *p_pHandles; // [rsp+30h] [rbp-38h]
  DWORD *p_dwindex; // [rsp+38h] [rbp-30h]
  HANDLE pHandles; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v69[4]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  DWORD dwindex; // [rsp+B8h] [rbp+50h] BYREF

  v69[1] = v69;
  v69[0] = v69;
  pHandles = 0;
  v8 = 0;
  AcquireSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  if ( (a2 & 0x60) != 0 )
  {
    v8 = WorkThreadManager::s_hEventCache;
    WorkThreadManager::s_hEventCache = 0;
    if ( !v8 )
    {
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( Event )
      {
        GetLastError();
        v8 = Event;
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v9);
        v12 = LastErrorFailHr;
        if ( LastErrorFailHr < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x456,
            (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
            (const char *)(unsigned int)LastErrorFailHr,
            (int)lpdwindex);
          ReleaseSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
          while ( 1 )
          {
            v13 = (_QWORD *)v69[0];
            if ( (_QWORD *)v69[0] == v69 )
              return v12;
            if ( *(_QWORD **)(v69[0] + 8LL) != v69 )
              goto LABEL_92;
            v14 = *(_QWORD *)v69[0];
            if ( *(_QWORD *)(*(_QWORD *)v69[0] + 8LL) != v69[0] )
              goto LABEL_92;
            v69[0] = *(_QWORD *)v69[0];
            *(_QWORD *)(v14 + 8) = v69;
            v15 = v13 - 7;
            v13[1] = v13;
            *v13 = v13;
            if ( v13 != (_QWORD *)56 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v15 + 6);
              v16 = (HMODULE)v15[5];
              if ( v16 )
                FreeLibrary(v16);
              operator delete(v15);
            }
          }
        }
      }
    }
  }
  dwindex = 0;
  Microsoft::WRL::ComPtr<WorkThreadManager::CDelayedTaskLifetime>::InternalRelease(&pHandles);
  p_dwindex = &dwindex;
  p_pHandles = &pHandles;
  v65 = v69;
  lpdwindex = a4;
  v18 = WorkThreadManager::s_QueuePoolTaskUnderLock(v8, a1, a2, a3);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45E,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v18,
      (int)lpdwindex);
    ReleaseSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
    while ( 1 )
    {
      v20 = (_QWORD *)v69[0];
      if ( (_QWORD *)v69[0] == v69 )
        break;
      if ( *(_QWORD **)(v69[0] + 8LL) != v69 )
        goto LABEL_92;
      v21 = *(_QWORD *)v69[0];
      if ( *(_QWORD *)(*(_QWORD *)v69[0] + 8LL) != v69[0] )
        goto LABEL_92;
      v69[0] = *(_QWORD *)v69[0];
      *(_QWORD *)(v21 + 8) = v69;
      v22 = v20 - 7;
      v20[1] = v20;
      *v20 = v20;
      if ( v20 != (_QWORD *)56 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v22 + 6);
        v23 = (HMODULE)v22[5];
        if ( v23 )
          FreeLibrary(v23);
        operator delete(v22);
      }
    }
    if ( pHandles )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(pHandles);
    if ( v8 && !CloseHandle(v8) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
    return v19;
  }
  LastError = GetLastError();
  ReleaseSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  SetLastError(LastError);
  while ( 1 )
  {
    v27 = (_QWORD *)v69[0];
    if ( (_QWORD *)v69[0] == v69 )
      break;
    if ( *(_QWORD **)(v69[0] + 8LL) != v69 || (v28 = *(_QWORD *)v69[0], *(_QWORD *)(*(_QWORD *)v69[0] + 8LL) != v69[0]) )
LABEL_92:
      __fastfail(3u);
    v69[0] = *(_QWORD *)v69[0];
    *(_QWORD *)(v28 + 8) = v69;
    v29 = v27 - 7;
    v27[1] = v27;
    *v27 = v27;
    if ( v27 != (_QWORD *)56 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v29 + 6);
      v30 = (HMODULE)v29[5];
      if ( v30 )
        FreeLibrary(v30);
      operator delete(v29);
    }
  }
  v31 = pHandles;
  if ( pHandles )
  {
    v32 = WaitForSingleObjectEx(*((HANDLE *)pHandles + 6), 0xFFFFFFFF, 0);
    if ( v32 == 258 )
    {
      v35 = GetLastError();
      v19 = v35;
      if ( v35 > 0 )
        v19 = (unsigned __int16)v35 | 0x80070000;
    }
    else
    {
      if ( v32 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v33, v34);
      v19 = 0;
    }
    if ( (*((_BYTE *)v31 + 148) & 2) == 0 )
    {
      v36 = (void *)*((_QWORD *)v31 + 6);
      if ( v36 )
      {
        v37 = GetLastError();
        if ( !CloseHandle(v36) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
        SetLastError(v37);
      }
      *((_QWORD *)v31 + 6) = 0;
    }
    if ( (v19 & 0x80000000) != 0 || (v19 = *((_DWORD *)v31 + 11), (v19 & 0x80000000) != 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x467,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)v19,
        (int)lpdwindex);
      while ( 1 )
      {
        v40 = (_QWORD *)v69[0];
        if ( (_QWORD *)v69[0] == v69 )
          break;
        if ( *(_QWORD **)(v69[0] + 8LL) != v69 )
          goto LABEL_92;
        v41 = *(_QWORD *)v69[0];
        if ( *(_QWORD *)(*(_QWORD *)v69[0] + 8LL) != v69[0] )
          goto LABEL_92;
        v69[0] = *(_QWORD *)v69[0];
        *(_QWORD *)(v41 + 8) = v69;
        v42 = v40 - 7;
        v40[1] = v40;
        *v40 = v40;
        if ( v40 != (_QWORD *)56 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v42 + 6);
          v43 = (HMODULE)v42[5];
          if ( v43 )
            FreeLibrary(v43);
          operator delete(v42);
        }
      }
      if ( v31 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v31);
      if ( v8 && !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
      return v19;
    }
  }
  if ( !v8 )
    goto LABEL_85;
  if ( (a2 & 0x40) != 0 )
  {
    dwindex = 0;
    pHandles = v8;
    v46 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
    v19 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48A,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)v46,
        (int)lpdwindex);
      while ( 1 )
      {
        v47 = (_QWORD *)v69[0];
        if ( (_QWORD *)v69[0] == v69 )
          break;
        if ( *(_QWORD **)(v69[0] + 8LL) != v69 )
          goto LABEL_92;
        v48 = *(_QWORD *)v69[0];
        if ( *(_QWORD *)(*(_QWORD *)v69[0] + 8LL) != v69[0] )
          goto LABEL_92;
        v69[0] = *(_QWORD *)v69[0];
        *(_QWORD *)(v48 + 8) = v69;
        v49 = v47 - 7;
        v47[1] = v47;
        *v47 = v47;
        if ( v47 != (_QWORD *)56 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v49 + 6);
          v50 = (HMODULE)v49[5];
          if ( v50 )
            FreeLibrary(v50);
          operator delete(v49);
        }
      }
      if ( v31 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v31);
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v51, v52);
      return v19;
    }
  }
  else if ( (a2 & 0x20) != 0 )
  {
    v53 = WaitForSingleObjectEx(v8, 0xFFFFFFFF, 0);
    if ( v53 != 258 )
    {
      if ( v53 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v54, v55);
    }
  }
  AcquireSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  v56 = WorkThreadManager::s_hEventCache;
  if ( WorkThreadManager::s_hEventCache )
  {
    v57 = GetLastError();
    if ( !CloseHandle(v56) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v58, v59);
    SetLastError(v57);
  }
  WorkThreadManager::s_hEventCache = v8;
  ReleaseSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
LABEL_85:
  while ( 1 )
  {
    v60 = (_QWORD *)v69[0];
    if ( (_QWORD *)v69[0] == v69 )
      break;
    if ( *(_QWORD **)(v69[0] + 8LL) != v69 )
      goto LABEL_92;
    v61 = *(_QWORD *)v69[0];
    if ( *(_QWORD *)(*(_QWORD *)v69[0] + 8LL) != v69[0] )
      goto LABEL_92;
    v69[0] = *(_QWORD *)v69[0];
    *(_QWORD *)(v61 + 8) = v69;
    v62 = v60 - 7;
    v60[1] = v60;
    *v60 = v60;
    if ( v60 != (_QWORD *)56 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v62 + 6);
      v63 = (HMODULE)v62[5];
      if ( v63 )
        FreeLibrary(v63);
      operator delete(v62);
    }
  }
  if ( v31 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v31);
  return 0;
}

```

## disassembly

```asm
0x180004950  push    rbp
0x180004952  push    rbx
0x180004953  push    rsi
0x180004954  push    rdi
0x180004955  push    r12
0x180004957  push    r13
0x180004959  push    r14
0x18000495b  push    r15
0x18000495d  mov     rbp, rsp
0x180004960  sub     rsp, 68h
0x180004964  lea     rax, [rbp+var_20]
0x180004968  mov     r15d, ecx
0x18000496b  mov     [rbp+var_18], rax
0x18000496f  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x180004976  lea     rax, [rbp+var_20]
0x18000497a  xor     r13d, r13d
0x18000497d  mov     [rbp+var_20], rax
0x180004981  mov     rsi, r9
0x180004984  mov     r14d, r8d
0x180004987  mov     [rbp+pHandles], r13
0x18000498b  mov     r12d, edx
0x18000498e  mov     ebx, r13d
0x180004991  call    AcquireSRWLockExclusive_0
0x180004996  test    r12b, 60h
0x18000499a  jz      loc_180004A8B
0x1800049a0  mov     rbx, cs:?s_hEventCache@WorkThreadManager@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x1800049a7  mov     cs:?s_hEventCache@WorkThreadManager@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A, r13
0x1800049ae  test    rbx, rbx
0x1800049b1  jnz     loc_180004A8B
0x1800049b7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800049bd  xor     r8d, r8d; dwFlags
0x1800049c0  xor     edx, edx; lpName
0x1800049c2  xor     ecx, ecx; lpEventAttributes
0x1800049c4  call    cs:__imp_CreateEventExW
0x1800049ca  mov     rdi, rax
0x1800049cd  test    rax, rax
0x1800049d0  jnz     loc_180004A82
0x1800049d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800049db  mov     edi, eax
0x1800049dd  test    eax, eax
0x1800049df  jns     loc_180004A8B
0x1800049e5  mov     rcx, [rbp+40h]; this
0x1800049e9  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800049f0  mov     r9d, eax; char *
0x1800049f3  mov     edx, 456h; void *
0x1800049f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049fd  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x180004a04  call    ReleaseSRWLockExclusive_0
0x180004a09  nop     dword ptr [rax+00000000h]
0x180004a10  mov     rax, [rbp+var_20]
0x180004a14  lea     rcx, [rbp+var_20]
0x180004a18  cmp     rax, rcx
0x180004a1b  jz      short loc_180004A7B
0x180004a1d  lea     rcx, [rbp+var_20]
0x180004a21  cmp     [rax+8], rcx
0x180004a25  jnz     loc_180004F33
0x180004a2b  mov     rcx, [rax]
0x180004a2e  cmp     [rcx+8], rax
0x180004a32  jnz     loc_180004F33
0x180004a38  mov     [rbp+var_20], rcx
0x180004a3c  lea     rdx, [rbp+var_20]
0x180004a40  mov     [rcx+8], rdx
0x180004a44  lea     rbx, [rax-38h]
0x180004a48  mov     [rax+8], rax
0x180004a4c  mov     [rax], rax
0x180004a4f  test    rbx, rbx
0x180004a52  jz      short loc_180004A10
0x180004a54  lea     rcx, [rbx+30h]
0x180004a58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180004a5d  mov     rcx, [rbx+28h]; hLibModule
0x180004a61  test    rcx, rcx
0x180004a64  jz      short loc_180004A6C
0x180004a66  call    cs:__imp_FreeLibrary
0x180004a6c  mov     edx, 48h ; 'H'
0x180004a71  mov     rcx, rbx; Block
0x180004a74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004a79  jmp     short loc_180004A10
0x180004a7b  mov     eax, edi
0x180004a7d  jmp     loc_180004F49
0x180004a82  call    cs:__imp_GetLastError
0x180004a88  mov     rbx, rdi
0x180004a8b  lea     rcx, [rbp+pHandles]
0x180004a8f  mov     [rbp+dwindex], r13d
0x180004a93  call    ?InternalRelease@?$ComPtr@VCDelayedTaskLifetime@WorkThreadManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WorkThreadManager::CDelayedTaskLifetime>::InternalRelease(void)
0x180004a98  lea     rax, [rbp+dwindex]
0x180004a9c  mov     r9d, r14d
0x180004a9f  mov     [rsp+68h+var_30], rax
0x180004aa4  mov     r8d, r12d
0x180004aa7  lea     rax, [rbp+pHandles]
0x180004aab  mov     edx, r15d
0x180004aae  mov     [rsp+68h+var_38], rax
0x180004ab3  mov     rcx, rbx
0x180004ab6  lea     rax, [rbp+var_20]
0x180004aba  mov     [rsp+68h+var_40], rax
0x180004abf  mov     [rsp+68h+lpdwindex], rsi; int
0x180004ac4  call    ?s_QueuePoolTaskUnderLock@WorkThreadManager@@CAJPEAXW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@PEAVTaskList@1@PEAPEAVCThread@1@AEAK@Z; WorkThreadManager::s_QueuePoolTaskUnderLock(void *,Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *,WorkThreadManager::TaskList *,WorkThreadManager::CThread * *,ulong &)
0x180004ac9  mov     esi, eax
0x180004acb  test    eax, eax
0x180004acd  jns     loc_180004B96
0x180004ad3  mov     rcx, [rbp+40h]; this
0x180004ad7  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180004ade  mov     r9d, eax; char *
0x180004ae1  mov     edx, 45Eh; void *
0x180004ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004aeb  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x180004af2  call    ReleaseSRWLockExclusive_0
0x180004af7  nop     word ptr [rax+rax+00000000h]
0x180004b00  mov     rax, [rbp+var_20]
0x180004b04  lea     rcx, [rbp+var_20]
0x180004b08  cmp     rax, rcx
0x180004b0b  jz      short loc_180004B6B
0x180004b0d  lea     rcx, [rbp+var_20]
0x180004b11  cmp     [rax+8], rcx
0x180004b15  jnz     loc_180004F33
0x180004b1b  mov     rcx, [rax]
0x180004b1e  cmp     [rcx+8], rax
0x180004b22  jnz     loc_180004F33
0x180004b28  mov     [rbp+var_20], rcx
0x180004b2c  lea     rdx, [rbp+var_20]
0x180004b30  mov     [rcx+8], rdx
0x180004b34  lea     rdi, [rax-38h]
0x180004b38  mov     [rax+8], rax
0x180004b3c  mov     [rax], rax
0x180004b3f  test    rdi, rdi
0x180004b42  jz      short loc_180004B00
0x180004b44  lea     rcx, [rdi+30h]
0x180004b48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180004b4d  mov     rcx, [rdi+28h]; hLibModule
0x180004b51  test    rcx, rcx
0x180004b54  jz      short loc_180004B5C
0x180004b56  call    cs:__imp_FreeLibrary
0x180004b5c  mov     edx, 48h ; 'H'
0x180004b61  mov     rcx, rdi; Block
0x180004b64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004b69  jmp     short loc_180004B00
0x180004b6b  mov     rcx, [rbp+pHandles]
0x180004b6f  test    rcx, rcx
0x180004b72  jz      short loc_180004B79
0x180004b74  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180004b79  test    rbx, rbx
0x180004b7c  jz      short loc_180004B8F
0x180004b7e  mov     rcx, rbx; hObject
0x180004b81  call    cs:__imp_CloseHandle
0x180004b87  test    eax, eax
0x180004b89  jz      loc_180004F87
0x180004b8f  mov     eax, esi
0x180004b91  jmp     loc_180004F49
0x180004b96  call    cs:__imp_GetLastError
0x180004b9c  lea     rcx, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; SRWLock
0x180004ba3  mov     edi, eax
0x180004ba5  call    ReleaseSRWLockExclusive_0
0x180004baa  mov     ecx, edi; dwErrCode
0x180004bac  call    cs:__imp_SetLastError
0x180004bb2  mov     rax, [rbp+var_20]
0x180004bb6  lea     rcx, [rbp+var_20]
0x180004bba  cmp     rax, rcx
0x180004bbd  jz      short loc_180004C1D
0x180004bbf  lea     rcx, [rbp+var_20]
0x180004bc3  cmp     [rax+8], rcx
0x180004bc7  jnz     loc_180004F33
0x180004bcd  mov     rcx, [rax]
0x180004bd0  cmp     [rcx+8], rax
0x180004bd4  jnz     loc_180004F33
0x180004bda  mov     [rbp+var_20], rcx
0x180004bde  lea     rdx, [rbp+var_20]
0x180004be2  mov     [rcx+8], rdx
0x180004be6  lea     rdi, [rax-38h]
0x180004bea  mov     [rax+8], rax
0x180004bee  mov     [rax], rax
0x180004bf1  test    rdi, rdi
0x180004bf4  jz      short loc_180004BB2
0x180004bf6  lea     rcx, [rdi+30h]
0x180004bfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180004bff  mov     rcx, [rdi+28h]; hLibModule
0x180004c03  test    rcx, rcx
0x180004c06  jz      short loc_180004C0E
0x180004c08  call    cs:__imp_FreeLibrary
0x180004c0e  mov     edx, 48h ; 'H'
0x180004c13  mov     rcx, rdi; Block
0x180004c16  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004c1b  jmp     short loc_180004BB2
0x180004c1d  mov     r14, [rbp+pHandles]
0x180004c21  test    r14, r14
0x180004c24  jz      loc_180004D67
0x180004c2a  mov     rcx, [r14+30h]; hHandle
0x180004c2e  xor     r8d, r8d; bAlertable
0x180004c31  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004c36  call    cs:__imp_WaitForSingleObjectEx
0x180004c3c  cmp     eax, 102h
0x180004c41  jz      short loc_180004C50
0x180004c43  test    eax, eax
0x180004c45  jnz     loc_180004F96
0x180004c4b  mov     esi, r13d
0x180004c4e  jmp     short loc_180004C65
0x180004c50  call    cs:__imp_GetLastError
0x180004c56  mov     esi, eax
0x180004c58  test    eax, eax
0x180004c5a  jle     short loc_180004C65
0x180004c5c  movzx   esi, ax
0x180004c5f  or      esi, 80070000h
0x180004c65  test    byte ptr [r14+94h], 2
0x180004c6d  jnz     short loc_180004C9F
0x180004c6f  mov     rdi, [r14+30h]
0x180004c73  test    rdi, rdi
0x180004c76  jz      short loc_180004C9B
0x180004c78  call    cs:__imp_GetLastError
0x180004c7e  mov     rcx, rdi; hObject
0x180004c81  mov     r15d, eax
0x180004c84  call    cs:__imp_CloseHandle
0x180004c8a  test    eax, eax
0x180004c8c  jz      loc_180004FA5
0x180004c92  mov     ecx, r15d; dwErrCode
0x180004c95  call    cs:__imp_SetLastError
0x180004c9b  mov     [r14+30h], r13
0x180004c9f  test    esi, esi
0x180004ca1  js      short loc_180004CAF
0x180004ca3  mov     esi, [r14+2Ch]
0x180004ca7  test    esi, esi
0x180004ca9  jns     loc_180004D67
0x180004caf  mov     rcx, [rbp+40h]; this
0x180004cb3  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180004cba  mov     r9d, esi; char *
0x180004cbd  mov     edx, 467h; void *
0x180004cc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cc7  nop     word ptr [rax+rax+00000000h]
0x180004cd0  mov     rax, [rbp+var_20]
0x180004cd4  lea     rcx, [rbp+var_20]
0x180004cd8  cmp     rax, rcx
0x180004cdb  jz      short loc_180004D3B
0x180004cdd  lea     rcx, [rbp+var_20]
0x180004ce1  cmp     [rax+8], rcx
0x180004ce5  jnz     loc_180004F33
0x180004ceb  mov     rcx, [rax]
0x180004cee  cmp     [rcx+8], rax
0x180004cf2  jnz     loc_180004F33
0x180004cf8  mov     [rbp+var_20], rcx
0x180004cfc  lea     rdx, [rbp+var_20]
0x180004d00  mov     [rcx+8], rdx
0x180004d04  lea     rdi, [rax-38h]
0x180004d08  mov     [rax+8], rax
0x180004d0c  mov     [rax], rax
0x180004d0f  test    rdi, rdi
0x180004d12  jz      short loc_180004CD0
0x180004d14  lea     rcx, [rdi+30h]
0x180004d18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180004d1d  mov     rcx, [rdi+28h]; hLibModule
0x180004d21  test    rcx, rcx
0x180004d24  jz      short loc_180004D2C
0x180004d26  call    cs:__imp_FreeLibrary
0x180004d2c  mov     edx, 48h ; 'H'
0x180004d31  mov     rcx, rdi; Block
0x180004d34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004d39  jmp     short loc_180004CD0
0x180004d3b  test    r14, r14
0x180004d3e  jz      short loc_180004D48
0x180004d40  mov     rcx, r14
0x180004d43  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180004d48  test    rbx, rbx
0x180004d4b  jz      loc_180004B8F
0x180004d51  mov     rcx, rbx; hObject
0x180004d54  call    cs:__imp_CloseHandle
0x180004d5a  test    eax, eax
0x180004d5c  jz      loc_180004F69
0x180004d62  jmp     loc_180004B8F
0x180004d67  test    rbx, rbx
0x180004d6a  jz      loc_180004ED0
0x180004d70  test    r12b, 40h
0x180004d74  jz      loc_180004E5E
0x180004d7a  lea     rax, [rbp+dwindex]
0x180004d7e  mov     [rbp+dwindex], r13d
0x180004d82  lea     r9, [rbp+pHandles]; pHandles
0x180004d86  mov     [rsp+68h+lpdwindex], rax; int
0x180004d8b  mov     edx, 0FFFFFFFFh; dwTimeout
0x180004d90  mov     [rbp+pHandles], rbx
0x180004d94  mov     ecx, 8; dwFlags
0x180004d99  mov     r8d, 1; cHandles
0x180004d9f  call    cs:__imp_CoWaitForMultipleHandles
0x180004da5  mov     esi, eax
0x180004da7  test    eax, eax
0x180004da9  jns     loc_180004E84
0x180004daf  mov     rcx, [rbp+40h]; this
0x180004db3  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180004dba  mov     r9d, eax; char *
0x180004dbd  mov     edx, 48Ah; void *
0x180004dc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dc7  nop     word ptr [rax+rax+00000000h]
0x180004dd0  mov     rcx, [rbp+var_20]
0x180004dd4  lea     rax, [rbp+var_20]
0x180004dd8  cmp     rcx, rax
0x180004ddb  jz      short loc_180004E3B
0x180004ddd  lea     rax, [rbp+var_20]
0x180004de1  cmp     [rcx+8], rax
0x180004de5  jnz     loc_180004F33
0x180004deb  mov     rax, [rcx]
0x180004dee  cmp     [rax+8], rcx
0x180004df2  jnz     loc_180004F33
0x180004df8  mov     [rbp+var_20], rax
0x180004dfc  lea     rdx, [rbp+var_20]
0x180004e00  mov     [rax+8], rdx
0x180004e04  lea     rdi, [rcx-38h]
  ... truncated ...
```
