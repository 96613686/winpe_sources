# CMapiManager::AddStoreWatcher(ulong,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x180030a04`
- end: `0x180030b70`
- name: `?AddStoreWatcher@CMapiManager@@QEAAHKAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, DWORD, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002b2e0`
- `0x18002d9a0`

## callees

- `0x180007110`
- `0x18000a56c`
- `0x180024504`
- `0x180030978`
- `0x180030a04`
- `0x1800319f0`
- `0x180032688`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030b25`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030b25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030a3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b34`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180030ab8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180030ab8`

## string_xrefs

- `0x180030b3a`: `CMapiManager failed to create store watcher`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMapiManager::AddStoreWatcher(__int64 a1, DWORD a2, __int64 a3)
{
  unsigned int v7; // ebx
  HANDLE v8; // rsi
  int v9; // ebp
  _QWORD *v10; // rax
  _QWORD *v11; // [rsp+50h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( !*(_DWORD *)(a1 + 156) )
    return 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 352);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 352));
  v11 = 0;
  if ( !(unsigned __int8)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::Lookup(
                           a1 + 280,
                           a2,
                           &v11) )
  {
    v7 = 1;
    if ( a2 )
    {
      v8 = OpenProcess(0x100000u, 0, a2);
      if ( !v8 )
        goto LABEL_15;
      v9 = 0;
    }
    else
    {
      v8 = *(HANDLE *)(a1 + 264);
      if ( !v8 )
        goto LABEL_15;
      *(_QWORD *)(a1 + 264) = 0;
      v9 = 1;
    }
    v10 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      v10[2] = 0;
      v10[3] = 0;
      *v10 = v8;
      *((_DWORD *)v10 + 2) = v9;
      v11 = v10;
      ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(
        v10 + 2,
        a3);
      ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::SetAt(
        a1 + 280,
        a2,
        &v11);
      SetEvent(*(HANDLE *)(a1 + 272));
      goto LABEL_16;
    }
    if ( !v9 )
      CloseHandle(v8);
    CLogger::Error(-2147024882, L"CMapiManager failed to create store watcher");
LABEL_15:
    v7 = 0;
    goto LABEL_16;
  }
  ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(
    v11 + 2,
    a3);
  v7 = 1;
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x180030a04  mov     [rsp+arg_8], rbx
0x180030a09  mov     [rsp+arg_10], rbp
0x180030a0e  push    rsi
0x180030a0f  push    rdi
0x180030a10  push    r12
0x180030a12  push    r14
0x180030a14  push    r15
0x180030a16  sub     rsp, 20h
0x180030a1a  mov     r15, r8
0x180030a1d  mov     r14d, edx
0x180030a20  mov     rdi, rcx
0x180030a23  cmp     dword ptr [rcx+9Ch], 0
0x180030a2a  jnz     short loc_180030A33
0x180030a2c  xor     eax, eax
0x180030a2e  jmp     loc_180030B59
0x180030a33  add     rcx, 160h; lpCriticalSection
0x180030a3a  mov     [rsp+48h+arg_18], rcx
0x180030a3f  call    cs:__imp_EnterCriticalSection
0x180030a45  nop
0x180030a46  mov     [rsp+48h+arg_0], 0
0x180030a4f  lea     r12, [rdi+118h]
0x180030a56  lea     r8, [rsp+48h+arg_0]
0x180030a5b  mov     edx, r14d
0x180030a5e  mov     rcx, r12
0x180030a61  call    ?Lookup@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBA_NKAEAPEAVCStoreWatcher@CMapiManager@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::Lookup(ulong,CMapiManager::CStoreWatcher * &)
0x180030a66  test    al, al
0x180030a68  jz      short loc_180030A85
0x180030a6a  mov     rcx, [rsp+48h+arg_0]
0x180030a6f  add     rcx, 10h
0x180030a73  mov     rdx, r15
0x180030a76  call    ?Add@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180030a7b  mov     ebx, 1
0x180030a80  jmp     loc_180030B4D
0x180030a85  mov     ebx, 1
0x180030a8a  test    r14d, r14d
0x180030a8d  jnz     short loc_180030AAE
0x180030a8f  mov     rsi, [rdi+108h]
0x180030a96  test    rsi, rsi
0x180030a99  jz      loc_180030B4B
0x180030a9f  mov     qword ptr [rdi+108h], 0
0x180030aaa  mov     ebp, ebx
0x180030aac  jmp     short loc_180030ACC
0x180030aae  mov     r8d, r14d; dwProcessId
0x180030ab1  xor     edx, edx; bInheritHandle
0x180030ab3  mov     ecx, 100000h; dwDesiredAccess
0x180030ab8  call    cs:__imp_OpenProcess
0x180030abe  mov     rsi, rax
0x180030ac1  test    rax, rax
0x180030ac4  jz      loc_180030B4B
0x180030aca  xor     ebp, ebp
0x180030acc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030ad3  mov     ecx, 20h ; ' '; unsigned __int64
0x180030ad8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180030add  mov     [rsp+48h+arg_0], rax
0x180030ae2  test    rax, rax
0x180030ae5  jz      short loc_180030B2D
0x180030ae7  mov     qword ptr [rax+10h], 0
0x180030aef  mov     qword ptr [rax+18h], 0
0x180030af7  mov     [rax], rsi
0x180030afa  mov     [rax+8], ebp
0x180030afd  mov     [rsp+48h+arg_0], rax
0x180030b02  lea     rcx, [rax+10h]
0x180030b06  mov     rdx, r15
0x180030b09  call    ?Add@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180030b0e  lea     r8, [rsp+48h+arg_0]
0x180030b13  mov     edx, r14d
0x180030b16  mov     rcx, r12
0x180030b19  call    ?SetAt@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAPEAU__POSITION@@KAEBQEAVCStoreWatcher@CMapiManager@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::SetAt(ulong,CMapiManager::CStoreWatcher * const &)
0x180030b1e  mov     rcx, [rdi+110h]; hEvent
0x180030b25  call    cs:__imp_SetEvent
0x180030b2b  jmp     short loc_180030B4D
0x180030b2d  test    ebp, ebp
0x180030b2f  jnz     short loc_180030B3A
0x180030b31  mov     rcx, rsi; hObject
0x180030b34  call    cs:__imp_CloseHandle
0x180030b3a  lea     rdx, aCmapimanagerFa; "CMapiManager failed to create store wat"...
0x180030b41  mov     ecx, 8007000Eh; int
0x180030b46  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180030b4b  xor     ebx, ebx
0x180030b4d  lea     rcx, [rsp+48h+arg_18]
0x180030b52  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180030b57  mov     eax, ebx
0x180030b59  mov     rbx, [rsp+48h+arg_8]
0x180030b5e  mov     rbp, [rsp+48h+arg_10]
0x180030b63  add     rsp, 20h
0x180030b67  pop     r15
0x180030b69  pop     r14
0x180030b6b  pop     r12
0x180030b6d  pop     rdi
0x180030b6e  pop     rsi
0x180030b6f  retn
```
