# CMapiManager::CMapiManager(ulong)

- ea: `0x1800304d4`
- end: `0x18003067f`
- name: `??0CMapiManager@@AEAA@K@Z`
- size: `427`
- prototype: `CMapiManager *__fastcall(CMapiManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800314c0`

## callees

- `0x1800045e4`
- `0x18002b230`
- `0x18002d37c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030611`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030611`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800305bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180030632`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800305bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180030632`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800305fa`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800305fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CMapiManager *__fastcall CMapiManager::CMapiManager(CMapiManager *this, unsigned int a2, int a3, int a4)
{
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // xmm5_4
  __int64 v10; // r8
  __int64 v11; // r8

  *(_QWORD *)this = &CMapiManager::`vftable';
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 16,
    a2,
    a3,
    a4,
    LODWORD(FLOAT_2_25));
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 280,
    v6,
    v7,
    v8,
    v9);
  CLogger::Info(L"CMapiManager::CMapiManager() Enter");
  *((_DWORD *)this + 41) = a2 & 1;
  *((_DWORD *)this + 39) = (a2 >> 1) & 1;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 38) = (a2 & 4) == 0;
  *((_DWORD *)this + 42) = (a2 >> 3) & 1;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  LOBYTE(v10) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 16,
    7,
    v10);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 17) = CreateSemaphoreW(0, 0, 1, 0);
  *((_QWORD *)this + 34) = CreateEventW(0, 0, 0, 0);
  LOBYTE(v11) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 280,
    7,
    v11);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  CLogger::Info(L"CMapiManager::CMapiManager() Exit");
  return this;
}

```

## disassembly

```asm
0x1800304d4  mov     [rsp+arg_8], rbx
0x1800304d9  mov     [rsp+arg_10], rsi
0x1800304de  mov     [rsp+arg_0], rcx
0x1800304e3  push    rdi
0x1800304e4  push    r14
0x1800304e6  push    r15
0x1800304e8  sub     rsp, 30h
0x1800304ec  mov     ebx, edx
0x1800304ee  mov     r14, rcx
0x1800304f1  lea     rax, ??_7CMapiManager@@6B@; const CMapiManager::`vftable'
0x1800304f8  mov     [rcx], rax
0x1800304fb  movss   xmm5, cs:__real@40100000
0x180030503  movss   [rsp+48h+var_28], xmm5
0x180030509  movss   xmm3, cs:__real@3e800000
0x180030511  movss   xmm4, cs:__real@3f400000
0x180030519  movaps  xmm2, xmm4
0x18003051c  add     rcx, 10h
0x180030520  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x180030525  nop
0x180030526  lea     rsi, [r14+118h]
0x18003052d  movss   [rsp+48h+var_28], xmm5
0x180030533  movaps  xmm2, xmm4
0x180030536  mov     rcx, rsi
0x180030539  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x18003053e  nop
0x18003053f  lea     rcx, aCmapimanagerCm; "CMapiManager::CMapiManager() Enter"
0x180030546  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18003054b  mov     eax, ebx
0x18003054d  and     eax, 1
0x180030550  mov     [r14+0A4h], eax
0x180030557  mov     eax, ebx
0x180030559  shr     eax, 1
0x18003055b  and     eax, 1
0x18003055e  mov     [r14+9Ch], eax
0x180030565  xor     r15d, r15d
0x180030568  mov     [r14+0A0h], r15d
0x18003056f  mov     eax, ebx
0x180030571  shr     eax, 2
0x180030574  not     eax
0x180030576  and     eax, 1
0x180030579  mov     [r14+98h], eax
0x180030580  shr     ebx, 3
0x180030583  and     ebx, 1
0x180030586  mov     [r14+0A8h], ebx
0x18003058d  mov     [r14+80h], r15
0x180030594  mov     [r14+88h], r15
0x18003059b  mov     [r14+108h], r15
0x1800305a2  mov     [r14+110h], r15
0x1800305a9  mov     r8b, 1
0x1800305ac  lea     ebx, [r15+7]
0x1800305b0  mov     edx, ebx
0x1800305b2  lea     rcx, [r14+10h]
0x1800305b6  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x1800305bb  lea     rcx, [r14+58h]; lpCriticalSection
0x1800305bf  call    cs:__imp_InitializeCriticalSection
0x1800305c5  mov     [r14+0B0h], r15
0x1800305cc  mov     [r14+0B8h], r15
0x1800305d3  mov     [r14+0C0h], r15d
0x1800305da  mov     [r14+0D8h], r15d
0x1800305e1  mov     [r14+0C8h], r15
0x1800305e8  mov     [r14+0D0h], r15
0x1800305ef  xor     r9d, r9d; lpName
0x1800305f2  xor     edx, edx; lInitialCount
0x1800305f4  xor     ecx, ecx; lpSemaphoreAttributes
0x1800305f6  lea     r8d, [r15+1]; lMaximumCount
0x1800305fa  call    cs:__imp_CreateSemaphoreW
0x180030600  mov     [r14+88h], rax
0x180030607  xor     r9d, r9d; lpName
0x18003060a  xor     r8d, r8d; bInitialState
0x18003060d  xor     edx, edx; bManualReset
0x18003060f  xor     ecx, ecx; lpEventAttributes
0x180030611  call    cs:__imp_CreateEventW
0x180030617  mov     [r14+110h], rax
0x18003061e  mov     r8b, 1
0x180030621  mov     edx, ebx
0x180030623  mov     rcx, rsi
0x180030626  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x18003062b  lea     rcx, [r14+160h]; lpCriticalSection
0x180030632  call    cs:__imp_InitializeCriticalSection
0x180030638  mov     [r14+0E0h], r15
0x18003063f  mov     [r14+0E8h], r15
0x180030646  mov     [r14+0F0h], r15
0x18003064d  mov     [r14+0F8h], r15
0x180030654  mov     [r14+100h], r15
0x18003065b  lea     rcx, aCmapimanagerCm_2; "CMapiManager::CMapiManager() Exit"
0x180030662  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180030667  nop
0x180030668  mov     rax, r14
0x18003066b  mov     rbx, [rsp+48h+arg_8]
0x180030670  mov     rsi, [rsp+48h+arg_10]
0x180030675  add     rsp, 30h
0x180030679  pop     r15
0x18003067b  pop     r14
0x18003067d  pop     rdi
0x18003067e  retn
```
