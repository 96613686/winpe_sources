# CClassCache::CDllPathEntry::MakeValidInApartment_rl16(_GUID const *)

- ea: `0x18002c0b4`
- end: `0x18002c3b9`
- name: `?MakeValidInApartment_rl16@CDllPathEntry@CClassCache@@QEAAJPEBU_GUID@@@Z`
- size: `773`
- prototype: `HRESULT __fastcall(CClassCache::CDllPathEntry *this, const _GUID *pclsid)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ba40`
- `0x18002c808`
- `0x18003aa1c`
- `0x1801d4170`
- `0x1801d43d0`

## callees

- `0x1800188a0`
- `0x18002a640`
- `0x18002c0b4`
- `0x18002c3c0`
- `0x18002d330`
- `0x18002d710`
- `0x18002e120`
- `0x18002e4c8`
- `0x18002e55c`
- `0x18002e624`
- `0x18017a264`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002c33e`
- `ntdll!RtlDllShutdownInProgress` at `0x18002c33e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c348`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c348`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c229`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c1f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c2a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c32c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c1f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c2a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c32c`

## string_xrefs

- `0x18002c3a1`: `onecore\com\combase\objact\dllcache.cxx`

## pseudocode

```c
__int64 __fastcall CClassCache::CDllPathEntry::MakeValidInApartment_rl16(
        CClassCache::CDllPathEntry *this,
        tagSOleTlsData *pclsid)
{
  tagSOleTlsData *ReservedForOle; // rax
  DWORD CurrentThreadId; // ebx
  CClassCache::CDllAptEntry **p_pAptEntryFront; // rdi
  CClassCache::CDllAptEntry *i; // rax
  CRWLock *v7; // rcx
  DWORD v9; // r12d
  LockEntry *LockEntry; // rax
  int v11; // r13d
  volatile unsigned int dwWriterSeqNum; // r14d
  CClassCache::CDllAptEntry *v13; // rax
  CRWLock *v14; // rcx
  unsigned int v15; // ebx
  LockCookie cookie; // [rsp+20h] [rbp-10h] BYREF
  void *retaddr; // [rsp+58h] [rbp+28h]
  COleTls v18; // [rsp+68h] [rbp+38h] BYREF

  v18._pData = pclsid;
  cookie = 0;
  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  v18._pData = ReservedForOle;
  if ( !ReservedForOle )
  {
    if ( COleTls::TLSAllocData(&v18) < 0 )
      goto LABEL_4;
    ReservedForOle = v18._pData;
  }
  if ( (ReservedForOle->dwFlags & 0x800) != 0 )
  {
    CurrentThreadId = -1;
  }
  else
  {
    if ( SLOBYTE(ReservedForOle->dwFlags) >= 0 )
    {
LABEL_4:
      CurrentThreadId = 0;
      goto LABEL_5;
    }
    CurrentThreadId = GetCurrentThreadId();
  }
LABEL_5:
  if ( this->_isOle32 )
    return 0;
  p_pAptEntryFront = &this->_pAptEntryFront;
  for ( i = this->_pAptEntryFront; i != (CClassCache::CDllAptEntry *)p_pAptEntryFront; i = i->_pNext )
  {
    if ( i->_hApt == CurrentThreadId )
      return 0;
  }
  v9 = GetCurrentThreadId();
  if ( CClassCache::_mxs._dwWriterID == v9 )
  {
    cookie.wWriterLevel = CClassCache::_mxs._wWriterLevel;
    cookie.dwWriterSeqNum = CClassCache::_mxs._dwWriterSeqNum;
    cookie.dwFlags = 139264;
    CRWLock::AcquireWriterLock(&CClassCache::_mxs, 0xFFFFFFFF);
LABEL_30:
    cookie.dwThreadID = v9;
    goto LABEL_21;
  }
  LockEntry = LockEntry::GetLockEntry(&CClassCache::_mxs);
  if ( !LockEntry )
  {
    v11 = 73728;
    dwWriterSeqNum = 0;
    *(_QWORD *)&cookie.dwFlags = 73728;
    goto LABEL_17;
  }
  v11 = 270336;
  dwWriterSeqNum = CClassCache::_mxs._dwWriterSeqNum;
  cookie.wReaderLevel = LockEntry->_wReaderLevel;
  cookie.dwFlags = 270336;
  cookie.dwWriterSeqNum = CClassCache::_mxs._dwWriterSeqNum;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&CClassCache::_mxs, 0x100000, 1) == 1 )
  {
    LockEntry->_wReaderLevel = 0;
    LockEntry::RecycleLockEntry(LockEntry);
    CClassCache::_mxs._dwWriterID = v9;
    CClassCache::_mxs._wWriterLevel = 1;
    ++CClassCache::_mxs._dwWriterSeqNum;
    goto LABEL_30;
  }
  LockEntry->_wReaderLevel = 1;
  CRWLock::ReleaseReaderLock(&CClassCache::_mxs);
LABEL_17:
  if ( CRWLock::AcquireWriterLock(&CClassCache::_mxs, 0xFFFFFFFF) )
  {
    cookie.dwFlags = -483329;
    if ( (v11 & 0x40000) != 0 )
    {
      if ( (unsigned int)CRWLock::AcquireReaderLock(&CClassCache::_mxs, 0xFFFFFFFF) )
      {
        GetCurrentThreadId();
        if ( !RtlDllShutdownInProgress() )
          IsDebuggerPresent();
        CRWLock::RWLockFailfast();
        __debugbreak();
      }
      LockEntry::GetLockEntry(&CClassCache::_mxs)->_wReaderLevel = cookie.wReaderLevel;
    }
  }
  if ( CClassCache::_mxs._dwWriterID == GetCurrentThreadId() )
    ++dwWriterSeqNum;
  cookie.dwThreadID = v9;
  if ( CClassCache::_mxs._dwWriterSeqNum != dwWriterSeqNum
    && CClassCache::CDllPathEntry::IsValidInApartment(this, CurrentThreadId) )
  {
    CRWLock::DowngradeFromWriterLock(v7, &cookie);
    return 0;
  }
LABEL_21:
  v13 = (CClassCache::CDllAptEntry *)HeapAlloc(g_hHeap, 0, 0x20u);
  if ( v13 )
  {
    v14 = (CRWLock *)(unsigned int)CClassCache::CDllAptEntry::SIG;
    v13->_dwSig = (unsigned int)CClassCache::CDllAptEntry::SIG;
    v13->_hApt = CurrentThreadId;
    v13->_hDll = 0;
    if ( this->_isSixteenBit && !this->_isOle32 )
      wil::details::in1diag3::FailFast_Hr(retaddr, 0x939u, "onecore\\com\\combase\\objact\\dllcache.cxx", -2147418113);
    v15 = 0;
    v13->_pNext = *p_pAptEntryFront;
    v13->_pPrev = (CClassCache::CDllAptEntry *)p_pAptEntryFront;
    (*p_pAptEntryFront)->_pPrev = v13;
    *p_pAptEntryFront = v13;
  }
  else
  {
    v15 = -2147024882;
  }
  CRWLock::DowngradeFromWriterLock(v14, &cookie);
  return v15;
}

```

## disassembly

```asm
0x18002c0b4  mov     [rsp-28h+arg_0], rbx
0x18002c0b9  mov     [rsp-28h+arg_10], rdi
0x18002c0be  mov     [rsp-28h+arg_8._pData], rdx
0x18002c0c3  push    rbp
0x18002c0c4  push    r12
0x18002c0c6  push    r13
0x18002c0c8  push    r14
0x18002c0ca  push    r15
0x18002c0cc  mov     rbp, rsp
0x18002c0cf  sub     rsp, 30h
0x18002c0d3  mov     rax, gs:30h
0x18002c0dc  xorps   xmm0, xmm0
0x18002c0df  mov     r15, this
0x18002c0e2  movups  xmmword ptr [rbp+cookie.dwFlags], xmm0
0x18002c0e6  mov     rax, [rax+1758h]
0x18002c0ed  mov     [rbp+arg_8._pData], rax
0x18002c0f1  test    rax, rax
0x18002c0f4  jz      loc_18002C288
0x18002c0fa  test    dword ptr [rax+14h], 800h
0x18002c101  jnz     loc_18002C280
0x18002c107  test    byte ptr [rax+14h], 80h
0x18002c10b  jnz     loc_18002C2A2
0x18002c111  xor     ebx, ebx
0x18002c113  cmp     byte ptr [r15+25h], 0
0x18002c118  jnz     short loc_18002C14B
0x18002c11a  lea     rdi, [r15+68h]
0x18002c11e  mov     rax, [rdi]
0x18002c121  cmp     rax, rdi
0x18002c124  jz      short loc_18002C165
0x18002c126  cmp     [rax+14h], ebx
0x18002c129  jz      short loc_18002C14B
0x18002c12b  mov     rax, [rax]
0x18002c12e  jmp     short loc_18002C121
0x18002c130  mov     edx, ebx; hApt
0x18002c132  mov     this, r15; this
0x18002c135  call    ?IsValidInApartment@CDllPathEntry@CClassCache@@QEAA_NK@Z; CClassCache::CDllPathEntry::IsValidInApartment(ulong)
0x18002c13a  test    al, al
0x18002c13c  jz      loc_18002C21C
0x18002c142  lea     rdx, [rbp+cookie]; pLockCookie
0x18002c146  call    ?DowngradeFromWriterLock@CRWLock@@QEAAKPEAULockCookie@@@Z; CRWLock::DowngradeFromWriterLock(LockCookie *)
0x18002c14b  xor     eax, eax
0x18002c14d  mov     rbx, [rsp+30h+arg_0]
0x18002c152  mov     rdi, [rsp+30h+arg_10]
0x18002c157  add     rsp, 30h
0x18002c15b  pop     r15
0x18002c15d  pop     r14
0x18002c15f  pop     r13
0x18002c161  pop     r12
0x18002c163  pop     rbp
0x18002c164  retn
0x18002c165  call    cs:__imp_GetCurrentThreadId
0x18002c16b  mov     ecx, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterID; CRWLock CClassCache::_mxs ...
0x18002c171  mov     r12d, eax
0x18002c174  cmp     ecx, eax
0x18002c176  jz      loc_18002C2AF
0x18002c17c  lea     this, ?_mxs@CClassCache@@2VCRWLock@@A; pRWLock
0x18002c183  call    ?GetLockEntry@LockEntry@@SAPEAV1@QEAVCRWLock@@@Z; LockEntry::GetLockEntry(CRWLock * const)
0x18002c188  mov     this, rax; this
0x18002c18b  mov     r8d, 1
0x18002c191  test    rax, rax
0x18002c194  jz      loc_18002C2E2
0x18002c19a  movzx   eax, word ptr [rax+18h]
0x18002c19e  mov     r13d, 42000h
0x18002c1a4  mov     r14d, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterSeqNum; CRWLock CClassCache::_mxs ...
0x18002c1ab  mov     edx, 100000h
0x18002c1b0  mov     [rbp+cookie.wReaderLevel], ax
0x18002c1b4  mov     eax, r8d
0x18002c1b7  mov     [rbp+cookie.dwFlags], r13d
0x18002c1bb  mov     [rbp+cookie.dwWriterSeqNum], r14d
0x18002c1bf  lock cmpxchg qword ptr cs:?_mxs@CClassCache@@2VCRWLock@@A.___u0, rdx; CRWLock CClassCache::_mxs ...
0x18002c1c8  jz      loc_18002C2FE
0x18002c1ce  mov     [this+18h], r8w
0x18002c1d3  lea     this, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002c1da  call    ?ReleaseReaderLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseReaderLock(void)
0x18002c1df  or      edx, 0FFFFFFFFh; dwDesiredTimeout
0x18002c1e2  lea     this, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002c1e9  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x18002c1ee  test    eax, eax
0x18002c1f0  jnz     loc_18002C354
0x18002c1f6  call    cs:__imp_GetCurrentThreadId
0x18002c1fc  mov     ecx, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterID; CRWLock CClassCache::_mxs ...
0x18002c202  cmp     ecx, eax
0x18002c204  jnz     short loc_18002C209
0x18002c206  inc     r14d
0x18002c209  mov     eax, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterSeqNum; CRWLock CClassCache::_mxs ...
0x18002c20f  mov     [rbp+cookie.dwThreadID], r12d
0x18002c213  cmp     eax, r14d
0x18002c216  jnz     loc_18002C130
0x18002c21c  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002c223  xor     edx, edx; dwFlags
0x18002c225  lea     r8d, [rdx+20h]; dwBytes
0x18002c229  call    cs:__imp_HeapAlloc
0x18002c22f  mov     rdx, rax
0x18002c232  test    rax, rax
0x18002c235  jz      loc_18002C2F4
0x18002c23b  mov     ecx, cs:?SIG@CDllAptEntry@CClassCache@@2KB; this
0x18002c241  mov     [rax+10h], ecx
0x18002c244  mov     [rax+14h], ebx
0x18002c247  mov     qword ptr [rax+18h], 0
0x18002c24f  cmp     byte ptr [r15+24h], 0
0x18002c254  jnz     loc_18002C392
0x18002c25a  mov     rax, [rdi]
0x18002c25d  xor     ebx, ebx
0x18002c25f  mov     [rdx], rax
0x18002c262  mov     [rdx+8], rdi
0x18002c266  mov     rax, [rdi]
0x18002c269  mov     [rax+8], rdx
0x18002c26d  mov     [rdi], rdx
0x18002c270  lea     rdx, [rbp+cookie]; pLockCookie
0x18002c274  call    ?DowngradeFromWriterLock@CRWLock@@QEAAKPEAULockCookie@@@Z; CRWLock::DowngradeFromWriterLock(LockCookie *)
0x18002c279  mov     eax, ebx
0x18002c27b  jmp     loc_18002C14D
0x18002c280  or      ebx, 0FFFFFFFFh
0x18002c283  jmp     loc_18002C113
0x18002c288  lea     this, [rbp+arg_8]; this
0x18002c28c  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x18002c291  test    eax, eax
0x18002c293  js      loc_18002C111
0x18002c299  mov     rax, [rbp+arg_8._pData]
0x18002c29d  jmp     loc_18002C0FA
0x18002c2a2  call    cs:__imp_GetCurrentThreadId
0x18002c2a8  mov     ebx, eax
0x18002c2aa  jmp     loc_18002C113
0x18002c2af  movzx   ecx, cs:?_mxs@CClassCache@@2VCRWLock@@A._wWriterLevel; CRWLock CClassCache::_mxs ...
0x18002c2b6  or      edx, 0FFFFFFFFh; dwDesiredTimeout
0x18002c2b9  mov     [rbp+cookie.wWriterLevel], cx
0x18002c2bd  mov     ecx, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterSeqNum; CRWLock CClassCache::_mxs ...
0x18002c2c3  mov     [rbp+cookie.dwWriterSeqNum], ecx
0x18002c2c6  lea     this, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002c2cd  mov     [rbp+cookie.dwFlags], 22000h
0x18002c2d4  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x18002c2d9  mov     [rbp+cookie.dwThreadID], r12d
0x18002c2dd  jmp     loc_18002C21C
0x18002c2e2  mov     r13d, 12000h
0x18002c2e8  xor     r14d, r14d
0x18002c2eb  mov     qword ptr [rbp+cookie.dwFlags], r13
0x18002c2ef  jmp     loc_18002C1DF
0x18002c2f4  mov     ebx, 8007000Eh
0x18002c2f9  jmp     $epilog
0x18002c2fe  xor     eax, eax
0x18002c300  mov     [this+18h], ax
0x18002c304  call    ?RecycleLockEntry@LockEntry@@QEAAXXZ; LockEntry::RecycleLockEntry(void)
0x18002c309  mov     cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterID, r12d; CRWLock CClassCache::_mxs ...
0x18002c310  mov     ecx, 1
0x18002c315  mov     eax, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterSeqNum; CRWLock CClassCache::_mxs ...
0x18002c31b  add     eax, ecx
0x18002c31d  mov     cs:?_mxs@CClassCache@@2VCRWLock@@A._wWriterLevel, cx; CRWLock CClassCache::_mxs ...
0x18002c324  mov     cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterSeqNum, eax; CRWLock CClassCache::_mxs ...
0x18002c32a  jmp     short loc_18002C2D9
0x18002c32c  call    cs:__imp_GetCurrentThreadId
0x18002c332  mov     eax, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterID; CRWLock CClassCache::_mxs ...
0x18002c338  mov     eax, cs:?_mxs@CClassCache@@2VCRWLock@@A._dwWriterSeqNum; CRWLock CClassCache::_mxs ...
0x18002c33e  call    cs:__imp_RtlDllShutdownInProgress
0x18002c344  test    al, al
0x18002c346  jnz     short loc_18002C34E
0x18002c348  call    cs:__imp_IsDebuggerPresent
0x18002c34e  call    ?RWLockFailfast@CRWLock@@SAXXZ; CRWLock::RWLockFailfast(void)
0x18002c353  int     3; Trap to Debugger
0x18002c354  mov     [rbp+cookie.dwFlags], 0FFF89FFFh
0x18002c35b  bt      r13d, 12h
0x18002c360  jnb     loc_18002C1F6
0x18002c366  or      edx, 0FFFFFFFFh; dwDesiredTimeout
0x18002c369  lea     this, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002c370  call    ?AcquireReaderLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireReaderLock(ulong)
0x18002c375  test    eax, eax
0x18002c377  jnz     short loc_18002C32C
0x18002c379  lea     this, ?_mxs@CClassCache@@2VCRWLock@@A; pRWLock
0x18002c380  call    ?GetLockEntry@LockEntry@@SAPEAV1@QEAVCRWLock@@@Z; LockEntry::GetLockEntry(CRWLock * const)
0x18002c385  movzx   ecx, [rbp+cookie.wReaderLevel]
0x18002c389  mov     [rax+18h], cx
0x18002c38d  jmp     loc_18002C1F6
0x18002c392  cmp     byte ptr [r15+25h], 0
0x18002c397  jnz     loc_18002C25A
0x18002c39d  mov     this, [rbp+28h]; callerReturnAddress
0x18002c3a1  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002c3a8  mov     r9d, 8000FFFFh; hr
0x18002c3ae  mov     edx, 939h; lineNumber
0x18002c3b3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
