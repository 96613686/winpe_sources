# CMapiManager::~CMapiManager(void)

- ea: `0x1800306ac`
- end: `0x180030796`
- name: `??1CMapiManager@@EEAA@XZ`
- size: `234`
- prototype: `void __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800308b0`

## callees

- `0x180004208`
- `0x18002d37c`
- `0x1800306ac`
- `0x180030b78`
- `0x180031e10`
- `0x180032814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030769`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030776`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030769`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003070b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003071d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003072f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800306f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003070b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003071d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003072f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030753`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180030741`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180030741`

## pseudocode

```c
void __fastcall CMapiManager::~CMapiManager(CMapiManager *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  const void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CMapiManager::`vftable';
  CLogger::Info(L"CMapiManager::~CMapiManager() Enter");
  CMapiManager::UnInitialize(this);
  CMapiManager::CleanupStoreWatchers(this, 1);
  CloseHandle(*((HANDLE *)this + 17));
  v2 = (void *)*((_QWORD *)this + 22);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 23);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 33);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 34);
  if ( v5 )
    CloseHandle(v5);
  v6 = (const void *)*((_QWORD *)this + 26);
  if ( v6 )
    UnmapViewOfFile(v6);
  v7 = (void *)*((_QWORD *)this + 25);
  if ( v7 )
    CloseHandle(v7);
  CLogger::Info(L"CMapiManager::~CMapiManager() Exit");
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::RemoveAll((char *)this + 280);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll((char *)this + 16);
}

```

## disassembly

```asm
0x1800306ac  push    rbx
0x1800306ae  sub     rsp, 20h
0x1800306b2  mov     rbx, rcx
0x1800306b5  lea     rax, ??_7CMapiManager@@6B@; const CMapiManager::`vftable'
0x1800306bc  mov     [rcx], rax
0x1800306bf  lea     rcx, aCmapimanagerCm_0; "CMapiManager::~CMapiManager() Enter"
0x1800306c6  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x1800306cb  mov     rcx, rbx; this
0x1800306ce  call    ?UnInitialize@CMapiManager@@AEAAJXZ; CMapiManager::UnInitialize(void)
0x1800306d3  mov     edx, 1; int
0x1800306d8  mov     rcx, rbx; this
0x1800306db  call    ?CleanupStoreWatchers@CMapiManager@@AEAAXH@Z; CMapiManager::CleanupStoreWatchers(int)
0x1800306e0  mov     rcx, [rbx+88h]; hObject
0x1800306e7  call    cs:__imp_CloseHandle
0x1800306ed  mov     rcx, [rbx+0B0h]; hObject
0x1800306f4  test    rcx, rcx
0x1800306f7  jz      short loc_1800306FF
0x1800306f9  call    cs:__imp_CloseHandle
0x1800306ff  mov     rcx, [rbx+0B8h]; hObject
0x180030706  test    rcx, rcx
0x180030709  jz      short loc_180030711
0x18003070b  call    cs:__imp_CloseHandle
0x180030711  mov     rcx, [rbx+108h]; hObject
0x180030718  test    rcx, rcx
0x18003071b  jz      short loc_180030723
0x18003071d  call    cs:__imp_CloseHandle
0x180030723  mov     rcx, [rbx+110h]; hObject
0x18003072a  test    rcx, rcx
0x18003072d  jz      short loc_180030735
0x18003072f  call    cs:__imp_CloseHandle
0x180030735  mov     rcx, [rbx+0D0h]; lpBaseAddress
0x18003073c  test    rcx, rcx
0x18003073f  jz      short loc_180030747
0x180030741  call    cs:__imp_UnmapViewOfFile
0x180030747  mov     rcx, [rbx+0C8h]; hObject
0x18003074e  test    rcx, rcx
0x180030751  jz      short loc_180030759
0x180030753  call    cs:__imp_CloseHandle
0x180030759  lea     rcx, aCmapimanagerCm_1; "CMapiManager::~CMapiManager() Exit"
0x180030760  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180030765  lea     rcx, [rbx+58h]; lpCriticalSection
0x180030769  call    cs:__imp_DeleteCriticalSection
0x18003076f  lea     rcx, [rbx+160h]; lpCriticalSection
0x180030776  call    cs:__imp_DeleteCriticalSection
0x18003077c  lea     rcx, [rbx+118h]
0x180030783  call    ?RemoveAll@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::RemoveAll(void)
0x180030788  lea     rcx, [rbx+10h]
0x18003078c  add     rsp, 20h
0x180030790  pop     rbx
0x180030791  jmp     ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiStore@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiStore@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll(void)
```
