# CMapiStore::~CMapiStore(void)

- ea: `0x18002bd94`
- end: `0x18002bf6f`
- name: `??1CMapiStore@@UEAA@XZ`
- size: `475`
- prototype: `void __fastcall(CMapiStore *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002bfe0`

## callees

- `0x1800048c0`
- `0x180005210`
- `0x18000be2c`
- `0x18002a7f4`
- `0x18002bd94`
- `0x18002bfb0`
- `0x18002d37c`
- `0x18002e134`
- `0x18002e1d0`
- `0x18002e26c`
- `0x18002e308`
- `0x18002e344`
- `0x18002e3a8`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002be23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002be23`

## string_xrefs

- `0x18002be2c`: `CMapiStore::~CMapiStore(%s) Deleted`

## pseudocode

```c
void __fastcall CMapiStore::~CMapiStore(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // edx
  CEntryId *SpinCount; // rcx
  struct IUnknown **p_LockCount; // rdi
  HANDLE *p_LockSemaphore; // rsi
  struct IUnknown *v6; // rcx
  unsigned int v7; // ebp

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMapiStore::`vftable';
  CMapiStore::RemoveAllSinks((CMapiStore *)this);
  CMapiStore::RemoveAllFolderNotifyProps((CMapiStore *)this);
  SpinCount = (CEntryId *)this->SpinCount;
  if ( SpinCount )
    CEntryId::`scalar deleting destructor'(SpinCount, v2);
  p_LockCount = (struct IUnknown **)&this[1].LockCount;
  p_LockSemaphore = &this[1].LockSemaphore;
  if ( *(_QWORD *)&this[1].LockCount )
  {
    CLogger::Info(L"CMapiStore::~CMapiStore(%s) Releasing pMsgStore", *p_LockSemaphore);
    v6 = *p_LockCount;
    *p_LockCount = 0;
    v7 = ((__int64 (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
    if ( *p_LockCount )
      ATL::AtlComPtrAssign(p_LockCount, 0);
    CLogger::Info(L"CMapiStore::~CMapiStore(%s) Released pMsgStore (refCnt=%d)", *p_LockSemaphore, v7);
  }
  DeleteCriticalSection(this + 4);
  CLogger::Info(L"CMapiStore::~CMapiStore(%s) Deleted", *p_LockSemaphore);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[16].LockSemaphore);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&this[15].SpinCount);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[15].OwningThread);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[15].LockCount);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[15]);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[14].SpinCount);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[14].LockSemaphore);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[14].OwningThread);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[14].LockCount);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[14]);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[13].SpinCount);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[13].LockSemaphore);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[13].OwningThread);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,_GUID,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<_GUID>>::RemoveAll(&this[11].LockSemaphore);
  ATL::CAtlMap<_GUID,CFolderNotificationProps *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CFolderNotificationProps *>>::RemoveAll(&this[9].SpinCount);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(&this[8]);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(&this[6].LockCount);
  ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(&this[5].SpinCount);
  ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(&this[5].OwningThread);
  ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(&this[5]);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[3].LockSemaphore);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[1].LockSemaphore);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&this[1].OwningThread);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(p_LockCount);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&this[1]);
  CEntryId::FreeBuffer((CEntryId *)&this->OwningThread);
  LODWORD(this->OwningThread) = 0;
}

```

## disassembly

```asm
0x18002bd94  push    rbx
0x18002bd96  push    rbp
0x18002bd97  push    rsi
0x18002bd98  push    rdi
0x18002bd99  sub     rsp, 28h
0x18002bd9d  mov     rbx, rcx
0x18002bda0  lea     rax, ??_7CMapiStore@@6B@; const CMapiStore::`vftable'
0x18002bda7  mov     [rcx], rax
0x18002bdaa  call    ?RemoveAllSinks@CMapiStore@@QEAAJXZ; CMapiStore::RemoveAllSinks(void)
0x18002bdaf  mov     rcx, rbx; this
0x18002bdb2  call    ?RemoveAllFolderNotifyProps@CMapiStore@@QEAAXXZ; CMapiStore::RemoveAllFolderNotifyProps(void)
0x18002bdb7  mov     rcx, [rbx+20h]; this
0x18002bdbb  test    rcx, rcx
0x18002bdbe  jz      short loc_18002BDC5
0x18002bdc0  call    ??_GCEntryId@@QEAAPEAXI@Z; CEntryId::`scalar deleting destructor'(uint)
0x18002bdc5  lea     rdi, [rbx+30h]
0x18002bdc9  lea     rsi, [rbx+40h]
0x18002bdcd  cmp     qword ptr [rdi], 0
0x18002bdd1  jz      short loc_18002BE1C
0x18002bdd3  mov     rdx, [rsi]
0x18002bdd6  lea     rcx, aCmapistoreCmap_4; "CMapiStore::~CMapiStore(%s) Releasing p"...
0x18002bddd  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002bde2  mov     rcx, [rdi]
0x18002bde5  mov     qword ptr [rdi], 0
0x18002bdec  mov     rax, [rcx]
0x18002bdef  mov     rax, [rax+10h]
0x18002bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdf8  mov     ebp, eax
0x18002bdfa  cmp     qword ptr [rdi], 0
0x18002bdfe  jz      short loc_18002BE0A
0x18002be00  xor     edx, edx; struct IUnknown *
0x18002be02  mov     rcx, rdi; struct IUnknown **
0x18002be05  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002be0a  mov     r8d, ebp
0x18002be0d  mov     rdx, [rsi]
0x18002be10  lea     rcx, aCmapistoreCmap_2; "CMapiStore::~CMapiStore(%s) Released pM"...
0x18002be17  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002be1c  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18002be23  call    cs:__imp_DeleteCriticalSection
0x18002be29  mov     rdx, [rsi]
0x18002be2c  lea     rcx, aCmapistoreCmap; "CMapiStore::~CMapiStore(%s) Deleted"
0x18002be33  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002be38  lea     rcx, [rbx+298h]
0x18002be3f  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be44  lea     rcx, [rbx+278h]
0x18002be4b  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002be50  lea     rcx, [rbx+268h]
0x18002be57  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be5c  lea     rcx, [rbx+260h]
0x18002be63  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be68  lea     rcx, [rbx+258h]
0x18002be6f  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be74  lea     rcx, [rbx+250h]
0x18002be7b  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be80  lea     rcx, [rbx+248h]
0x18002be87  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be8c  lea     rcx, [rbx+240h]
0x18002be93  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002be98  lea     rcx, [rbx+238h]
0x18002be9f  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bea4  lea     rcx, [rbx+230h]
0x18002beab  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002beb0  lea     rcx, [rbx+228h]
0x18002beb7  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bebc  lea     rcx, [rbx+220h]
0x18002bec3  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bec8  lea     rcx, [rbx+218h]
0x18002becf  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bed4  lea     rcx, [rbx+1D0h]
0x18002bedb  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@U_GUID@@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@U_GUID@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,_GUID,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<_GUID>>::RemoveAll(void)
0x18002bee0  lea     rcx, [rbx+188h]
0x18002bee7  call    ?RemoveAll@?$CAtlMap@U_GUID@@PEAVCFolderNotificationProps@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAVCFolderNotificationProps@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,CFolderNotificationProps *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CFolderNotificationProps *>>::RemoveAll(void)
0x18002beec  lea     rcx, [rbx+140h]
0x18002bef3  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002bef8  lea     rcx, [rbx+0F8h]
0x18002beff  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002bf04  lea     rcx, [rbx+0E8h]
0x18002bf0b  call    ??1?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(void)
0x18002bf10  lea     rcx, [rbx+0D8h]
0x18002bf17  call    ??1?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(void)
0x18002bf1c  lea     rcx, [rbx+0C8h]
0x18002bf23  call    ??1?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(void)
0x18002bf28  lea     rcx, [rbx+90h]
0x18002bf2f  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bf34  mov     rcx, rsi
0x18002bf37  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bf3c  lea     rcx, [rbx+38h]
0x18002bf40  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002bf45  mov     rcx, rdi
0x18002bf48  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002bf4d  lea     rcx, [rbx+28h]
0x18002bf51  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002bf56  lea     rcx, [rbx+10h]; this
0x18002bf5a  call    ?FreeBuffer@CEntryId@@AEAAXXZ; CEntryId::FreeBuffer(void)
0x18002bf5f  mov     dword ptr [rbx+10h], 0
0x18002bf66  add     rsp, 28h
0x18002bf6a  pop     rdi
0x18002bf6b  pop     rsi
0x18002bf6c  pop     rbp
0x18002bf6d  pop     rbx
0x18002bf6e  retn
```
