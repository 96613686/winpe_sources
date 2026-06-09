# ThreadFirstInitialize(COleTls &,ulong)

- ea: `0x18000d1b4`
- end: `0x18000d512`
- name: `?ThreadFirstInitialize@@YAJAEAVCOleTls@@K@Z`
- size: `862`
- prototype: `HRESULT __fastcall(COleTls *Tls, unsigned int flags)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x18001c83c`

## callees

- `0x180006250`
- `0x180006ea0`
- `0x18000712c`
- `0x18000d190`
- `0x18000d1b4`
- `0x18000d518`
- `0x18000d5bc`
- `0x18000d678`
- `0x18000d7b8`
- `0x18000d8c8`
- `0x18000d9f0`
- `0x1800101c8`
- `0x18001132c`
- `0x18003a8bc`
- `0x180087ab8`
- `0x18008db2c`
- `0x180135788`
- `0x180136244`
- `0x18013641c`
- `0x180141170`
- `0x18019cb24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d399`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d2fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d2fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2d0`
- `ext-ms-win-com-apartmentrestriction-l1-1-0!OnInitializationOfSingleThreadedApartment` at `0x18000d4a5`
- `ext-ms-win-com-apartmentrestriction-l1-1-0!OnInitializationOfSingleThreadedApartment` at `0x18000d4a5`

## string_xrefs

- `0x18000d262`: `onecore\com\combase\class\compobj.cxx`
- `0x18000d4ba`: `onecore\com\combase\class\compobj.cxx`
- `0x1802456f4`: `onecore\com\combase\class\compobj.cxx`
- `0x1802456e9`: `ThreadFirstInitialize`

## pseudocode

```c
HRESULT __fastcall ThreadFirstInitialize(COleTls *Tls, signed int flags)
{
  __int64 v4; // rcx
  HRESULT result; // eax
  HRESULT inited; // esi
  __int64 v7; // rcx
  const char *v8; // r9
  CObjectContext *v9; // rax
  CComApartment *v10; // rbx
  CObjectContext *v11; // rbp
  __int64 v12; // rcx
  _DWORD *ReservedForOle; // rbx
  int v14; // edi
  __int64 v15; // rcx
  ApartmentType v16; // ebx
  CComApartment *v17; // rax
  CComApartment *v18; // r8
  CComApartment *v19; // rax
  COleStaticMutexSem *v20; // rcx
  __int64 v21; // rcx
  HRESULT v22; // eax
  HRESULT v23; // ebx
  TraceLevel v24; // r9d
  void *retaddr; // [rsp+78h] [rbp+0h]

  if ( g_mxsSingleThreadOle._cs.OwningThread != (void *)GetCurrentThreadId() )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  result = IncrementProcessInitializeCount();
  if ( result >= 0 )
  {
    if ( (flags & 2) == 0 )
    {
      inited = wCoIncrementMTAUsage();
      if ( inited >= 0 )
      {
        if ( flags < 0 )
          Tls->_pData->dwFlags |= 0x200000u;
        if ( g_mxsSingleThreadOle._cs.OwningThread != (void *)GetCurrentThreadId() )
          MicrosoftTelemetryAssertTriggeredNoArgs(v7);
        Tls->_pData->dwFlags |= 0x140u;
        _InterlockedAdd((volatile signed __int32 *)gpMTAApartment, 1u);
        v9 = g_pMTAEmptyCtx;
        _InterlockedAdd((volatile signed __int32 *)&g_pMTAEmptyCtx->_cRefs, 1u);
        _InterlockedAdd(&v9->_cInternalRefs, 1u);
        v10 = gpMTAApartment;
        v11 = g_pMTAEmptyCtx;
        goto LABEL_11;
      }
      goto LABEL_41;
    }
    if ( IsOnInitializationOfSingleThreadedApartmentPresent() )
    {
      v22 = OnInitializationOfSingleThreadedApartment();
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0xCCBu, "onecore\\com\\combase\\class\\compobj.cxx", v22);
        return v23;
      }
    }
    Tls->_pData->dwFlags |= 0x80u;
    if ( (flags & 4) != 0 )
      Tls->_pData->dwFlags |= 0x40u;
    if ( flags < 0 )
      Tls->_pData->dwFlags |= 0x200000u;
    if ( (flags & 0x40000000) != 0 )
      Tls->_pData->dwFlags |= 0x400000u;
    if ( (flags & 0x20000000) != 0 )
      Tls->_pData->dwFlags |= 0x40000000u;
    if ( (flags & 0x40000000) != 0 )
      v16 = ApartmentType_ASTA;
    else
      v16 = (flags & 0x20000000) != 0 ? ApartmentType_BSTA : ApartmentType_STA;
    inited = -2147024882;
    v17 = (CComApartment *)HeapAlloc(g_hHeap, 0, 0x1B0u);
    if ( !v17 )
    {
LABEL_41:
      v10 = 0;
      v11 = 0;
      goto $ErrorReturn;
    }
    v11 = 0;
    CComApartment::CComApartment(v17, v16, v18);
    v10 = v19;
    if ( v19 )
    {
      inited = CComApartment::FinalConstruct(v19);
      if ( inited >= 0 )
      {
        v11 = CObjectContext::CreateAndFreezeDefaultObjectContext(v10);
        if ( v11 )
          goto LABEL_36;
        inited = -2147024882;
      }
      ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CComApartment,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CComApartment,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CComApartment,ObjectLibrary::Details::MixinBase<CComApartment,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(v10);
      v10 = 0;
      goto $ErrorReturn;
    }
LABEL_36:
    if ( inited >= 0 )
    {
      if ( (flags & 0x60000000) == 0 )
      {
        if ( ++g_cClassicSTAInits == 1 )
        {
          inited = RegisterOleWndClass();
          if ( inited < 0 )
          {
            --g_cClassicSTAInits;
            goto $ErrorReturn;
          }
        }
        if ( !gdwMainThreadId )
        {
          inited = InitMainThreadWnd();
          if ( inited < 0 )
          {
            if ( !--g_cClassicSTAInits )
              UnRegisterOleWndClass();
            goto $ErrorReturn;
          }
        }
      }
      ++g_cSTAInits;
      CoVrfIndicateNewSTA();
      LogApartmentInitialize();
LABEL_11:
      COleStaticMutexSem::Request(&gTlsLock, "onecore\\com\\combase\\class\\compobj.cxx", 0x262u, v8);
      Tls->_pData->pNativeApt = v10;
      Tls->_pData->pEmptyCtx = v11;
      if ( !--gTlsLock._cLocks && gTlsLock._lockOrder != Highest )
      {
        ReservedForOle = NtCurrentTeb()->ReservedForOle;
        if ( ReservedForOle )
        {
          LOBYTE(v12) = gTlsLock._lockOrder;
          v14 = 1 << gTlsLock._lockOrder;
          if ( ((1 << gTlsLock._lockOrder) & ReservedForOle[144]) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v12);
          ReservedForOle[144] &= ~v14;
        }
      }
      LeaveCriticalSection(&gTlsLock._cs);
      Tls->_pData->pCurrentContext = v11;
      Tls->_pData->pCurrentCtxForNefariousReaders = v11;
      Tls->_pData->ContextId = v11->_urtCtxId;
      Tls->_pData->pContextStack = 0;
      if ( g_mxsSingleThreadOle._cs.OwningThread != (void *)GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs(v15);
      return 0;
    }
$ErrorReturn:
    Tls->_pData->dwFlags = Tls->_pData->dwFlags & 2 | 1;
    if ( v10 )
    {
      CObjectContext::InternalRelease(v11);
      ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CComApartment,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CComApartment,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CComApartment,ObjectLibrary::Details::MixinBase<CComApartment,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(v10);
    }
    DecrementProcessInitializeCount();
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<unsigned long,unsigned long,long>(
        "onecore\\com\\combase\\class\\compobj.cxx",
        "ThreadFirstInitialize",
        3438,
        v24,
        L"Failed. Flags:%d TLS->Flags %d %!HRESULT!",
        flags,
        Tls->_pData->dwFlags,
        inited);
    if ( !COleStaticMutexSem::IsLockHeld(v20) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v21);
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x18000d1b4  push    rbx
0x18000d1b6  push    rbp
0x18000d1b7  push    rsi
0x18000d1b8  push    rdi
0x18000d1b9  push    r14
0x18000d1bb  push    r15
0x18000d1bd  sub     rsp, 48h
0x18000d1c1  mov     r15d, flags
0x18000d1c4  mov     r14, Tls
0x18000d1c7  call    cs:__imp_GetCurrentThreadId
0x18000d1cd  mov     eax, eax
0x18000d1cf  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000d1d6  jz      short loc_18000D1DD
0x18000d1d8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000d1dd  call    ?IncrementProcessInitializeCount@@YAJXZ; IncrementProcessInitializeCount(void)
0x18000d1e2  test    eax, eax
0x18000d1e4  js      loc_18000D315
0x18000d1ea  mov     edi, 1
0x18000d1ef  test    r15b, 2
0x18000d1f3  jnz     loc_18000D322
0x18000d1f9  call    ?wCoIncrementMTAUsage@@YAJXZ; wCoIncrementMTAUsage(void)
0x18000d1fe  mov     esi, eax
0x18000d200  test    eax, eax
0x18000d202  js      loc_18000D41F
0x18000d208  test    r15d, r15d
0x18000d20b  jns     short loc_18000D215
0x18000d20d  mov     rax, [r14]
0x18000d210  bts     dword ptr [rax+14h], 15h
0x18000d215  call    cs:__imp_GetCurrentThreadId
0x18000d21b  mov     eax, eax
0x18000d21d  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000d224  jz      short loc_18000D22B
0x18000d226  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000d22b  mov     rax, [r14]
0x18000d22e  or      dword ptr [rax+14h], 140h
0x18000d235  mov     rax, cs:?gpMTAApartment@@3PEAVCComApartment@@EA; CComApartment * gpMTAApartment
0x18000d23c  lock add [rax], edi
0x18000d23f  mov     rax, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x18000d246  lock add [rax+38h], edi
0x18000d24a  lock add [rax+40h], edi
0x18000d24e  mov     rbx, cs:?gpMTAApartment@@3PEAVCComApartment@@EA; CComApartment * gpMTAApartment
0x18000d255  mov     rbp, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x18000d25c  mov     r8d, 262h; dwLine
0x18000d262  lea     rdx, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x18000d269  lea     Tls, ?gTlsLock@@3VCOleStaticMutexSem@@A; this
0x18000d270  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x18000d275  mov     rax, [r14]
0x18000d278  mov     [rax+80h], rbx
0x18000d27f  mov     rax, [r14]
0x18000d282  mov     [rax+70h], rbp
0x18000d286  add     cs:?gTlsLock@@3VCOleStaticMutexSem@@A._cLocks, 0FFFFFFFFh; COleStaticMutexSem gTlsLock ...
0x18000d28d  jnz     short loc_18000D2C9
0x18000d28f  cmp     cs:?gTlsLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gTlsLock ...
0x18000d296  jz      short loc_18000D2C9
0x18000d298  mov     rax, gs:30h
0x18000d2a1  mov     rbx, [rax+1758h]
0x18000d2a8  test    rbx, rbx
0x18000d2ab  jz      short loc_18000D2C9
0x18000d2ad  mov     cl, cs:?gTlsLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gTlsLock ...
0x18000d2b3  shl     edi, cl
0x18000d2b5  test    [rbx+240h], edi
0x18000d2bb  jz      loc_18000D4D5
0x18000d2c1  not     edi
0x18000d2c3  and     [rbx+240h], edi
0x18000d2c9  lea     Tls, ?gTlsLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x18000d2d0  call    cs:__imp_LeaveCriticalSection
0x18000d2d6  mov     rax, [r14]
0x18000d2d9  mov     [rax+68h], rbp
0x18000d2dd  mov     rax, [r14]
0x18000d2e0  mov     [rax+60h], rbp
0x18000d2e4  mov     rax, [rbp+98h]
0x18000d2eb  mov     Tls, [r14]
0x18000d2ee  mov     [Tls+78h], rax
0x18000d2f2  mov     rax, [r14]
0x18000d2f5  mov     qword ptr [rax+48h], 0
0x18000d2fd  call    cs:__imp_GetCurrentThreadId
0x18000d303  mov     eax, eax
0x18000d305  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000d30c  jz      short loc_18000D313
0x18000d30e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000d313  xor     eax, eax
0x18000d315  add     rsp, 48h
0x18000d319  pop     r15
0x18000d31b  pop     r14
0x18000d31d  pop     rdi
0x18000d31e  pop     rsi
0x18000d31f  pop     rbp
0x18000d320  pop     rbx
0x18000d321  retn
0x18000d322  call    IsOnInitializationOfSingleThreadedApartmentPresent
0x18000d327  test    al, al
0x18000d329  jnz     loc_18000D4A5
0x18000d32f  mov     rax, [r14]
0x18000d332  bts     dword ptr [rax+14h], 7
0x18000d337  test    r15b, 4
0x18000d33b  jz      short loc_18000D344
0x18000d33d  mov     rax, [r14]
0x18000d340  or      dword ptr [rax+14h], 40h
0x18000d344  test    r15d, r15d
0x18000d347  jns     short loc_18000D351
0x18000d349  mov     rax, [r14]
0x18000d34c  bts     dword ptr [rax+14h], 15h
0x18000d351  mov     flags, r15d
0x18000d354  mov     r8d, 40000000h
0x18000d35a  and     flags, r8d
0x18000d35d  jz      short loc_18000D367
0x18000d35f  mov     rax, [r14]
0x18000d362  bts     dword ptr [rax+14h], 16h
0x18000d367  mov     ecx, r15d
0x18000d36a  and     ecx, 20000000h
0x18000d370  jnz     loc_18000D460
0x18000d376  test    flags, flags
0x18000d378  jnz     loc_18000D49E
0x18000d37e  neg     ecx
0x18000d380  sbb     ebx, ebx
0x18000d382  and     ebx, 4
0x18000d385  mov     Tls, cs:?g_hHeap@@3QEAXEA; hHeap
0x18000d38c  xor     flags, flags; dwFlags
0x18000d38e  mov     r8d, 1B0h; dwBytes
0x18000d394  mov     esi, 8007000Eh
0x18000d399  call    cs:__imp_HeapAlloc
0x18000d39f  test    rax, rax
0x18000d3a2  jz      short loc_18000D41F
0x18000d3a4  mov     flags, ebx; type
0x18000d3a6  mov     Tls, rax; this
0x18000d3a9  xor     ebp, ebp
0x18000d3ab  call    ??0CComApartment@@QEAA@W4ApartmentType@@PEAV0@@Z; CComApartment::CComApartment(ApartmentType,CComApartment *)
0x18000d3b0  mov     rbx, rax
0x18000d3b3  test    rax, rax
0x18000d3b6  jz      short loc_18000D3DE
0x18000d3b8  mov     Tls, rax; this
0x18000d3bb  call    ?FinalConstruct@CComApartment@@QEAAJXZ; CComApartment::FinalConstruct(void)
0x18000d3c0  mov     esi, eax
0x18000d3c2  test    eax, eax
0x18000d3c4  js      loc_18000D4E4
0x18000d3ca  mov     Tls, rbx; pComApartment
0x18000d3cd  call    ?CreateAndFreezeDefaultObjectContext@CObjectContext@@SAPEAV1@PEAVCComApartment@@@Z; CObjectContext::CreateAndFreezeDefaultObjectContext(CComApartment *)
0x18000d3d2  mov     rbp, rax
0x18000d3d5  test    rax, rax
0x18000d3d8  jz      loc_18000D4DF
0x18000d3de  test    esi, esi
0x18000d3e0  js      short $ErrorReturn
0x18000d3e2  test    r15d, 60000000h
0x18000d3e9  jnz     short loc_18000D40A
0x18000d3eb  mov     eax, cs:g_cClassicSTAInits
0x18000d3f1  add     eax, edi
0x18000d3f3  mov     cs:g_cClassicSTAInits, eax
0x18000d3f9  cmp     eax, edi
0x18000d3fb  jz      loc_18000D487
0x18000d401  cmp     cs:?gdwMainThreadId@@3KA, 0; ulong gdwMainThreadId
0x18000d408  jz      short loc_18000D46C
0x18000d40a  add     cs:g_cSTAInits, edi
0x18000d410  call    ?CoVrfIndicateNewSTA@@YAXXZ; CoVrfIndicateNewSTA(void)
0x18000d415  call    ?LogApartmentInitialize@@YAXXZ; LogApartmentInitialize(void)
0x18000d41a  jmp     loc_18000D25C
0x18000d41f  xor     ebx, ebx
0x18000d421  xor     ebp, ebp
0x18000d423  mov     rdx, [r14]
0x18000d426  mov     eax, [rdx+14h]
0x18000d429  and     eax, 2
0x18000d42c  or      eax, edi
0x18000d42e  mov     [rdx+14h], eax
0x18000d431  test    rbx, rbx
0x18000d434  jnz     loc_18000D4F3
0x18000d43a  call    ?DecrementProcessInitializeCount@@YA_NXZ; DecrementProcessInitializeCount(void)
0x18000d43f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18000d446  jnz     loc_1802456D0
0x18000d44c  call    ?IsLockHeld@COleStaticMutexSem@@QEAA_NXZ; COleStaticMutexSem::IsLockHeld(void)
0x18000d451  test    al, al
0x18000d453  jz      loc_18000D508
0x18000d459  mov     eax, esi
0x18000d45b  jmp     loc_18000D315
0x18000d460  mov     rax, [r14]
0x18000d463  or      [rax+14h], r8d
0x18000d467  jmp     loc_18000D376
0x18000d46c  call    ?InitMainThreadWnd@@YAJXZ; InitMainThreadWnd(void)
0x18000d471  mov     esi, eax
0x18000d473  test    eax, eax
0x18000d475  jns     short loc_18000D40A
0x18000d477  add     cs:g_cClassicSTAInits, 0FFFFFFFFh
0x18000d47e  jnz     short $ErrorReturn
0x18000d480  call    ?UnRegisterOleWndClass@@YAXXZ; UnRegisterOleWndClass(void)
0x18000d485  jmp     short $ErrorReturn
0x18000d487  call    ?RegisterOleWndClass@@YAJXZ; RegisterOleWndClass(void)
0x18000d48c  mov     esi, eax
0x18000d48e  test    eax, eax
0x18000d490  jns     loc_18000D401
0x18000d496  dec     cs:g_cClassicSTAInits
0x18000d49c  jmp     short $ErrorReturn
0x18000d49e  mov     ebx, edi
0x18000d4a0  jmp     loc_18000D385
0x18000d4a5  call    cs:__imp_OnInitializationOfSingleThreadedApartment
0x18000d4ab  mov     ebx, eax
0x18000d4ad  test    eax, eax
0x18000d4af  jns     loc_18000D32F
0x18000d4b5  mov     Tls, [rsp+78h]; callerReturnAddress
0x18000d4ba  lea     r8, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x18000d4c1  mov     r9d, eax; hr
0x18000d4c4  mov     flags, 0CCBh; lineNumber
0x18000d4c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4ce  mov     eax, ebx
0x18000d4d0  jmp     loc_18000D315
0x18000d4d5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x18000d4da  jmp     loc_18000D2C1
0x18000d4df  mov     esi, 8007000Eh
0x18000d4e4  mov     Tls, rbx; this
0x18000d4e7  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VCComApartment@@V?$AddComReferenceCounting_ReferenceCountLayer@VCComApartment@@V?$Allocation_SealedClassDeleteSelfLayer@VCComApartment@@V?$MixinBase@VCComApartment@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CComApartment,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CComApartment,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CComApartment,ObjectLibrary::Details::MixinBase<CComApartment,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x18000d4ec  xor     ebx, ebx
0x18000d4ee  jmp     $ErrorReturn
0x18000d4f3  mov     Tls, rbp; this
0x18000d4f6  call    ?InternalRelease@CObjectContext@@QEAAKXZ; CObjectContext::InternalRelease(void)
0x18000d4fb  mov     Tls, rbx; this
0x18000d4fe  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VCComApartment@@V?$AddComReferenceCounting_ReferenceCountLayer@VCComApartment@@V?$Allocation_SealedClassDeleteSelfLayer@VCComApartment@@V?$MixinBase@VCComApartment@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CComApartment,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CComApartment,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CComApartment,ObjectLibrary::Details::MixinBase<CComApartment,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x18000d503  jmp     loc_18000D43A
0x18000d508  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000d50d  jmp     loc_18000D459
0x1802456d0  mov     r9d, 3
0x1802456d6  mov     ecx, r9d; level
0x1802456d9  call    IsWppLevelEnabled
0x1802456de  test    al, al
0x1802456e0  jz      loc_18000D44C
0x1802456e6  mov     rax, [r14]
0x1802456e9  lea     rdx, aThreadfirstini; "ThreadFirstInitialize"
0x1802456f0  mov     [rsp+78h+var_40], esi; <args_2>
0x1802456f4  lea     rcx, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x1802456fb  mov     r8d, 0D6Eh; line
0x180245701  mov     eax, [rax+14h]
0x180245704  mov     [rsp+78h+var_48], eax; <args_1>
0x180245708  lea     rax, aFailedFlagsDTl; "Failed. Flags:%d TLS->Flags %d %!HRESUL"...
0x18024570f  mov     [rsp+78h+var_50], r15d; <args_0>
0x180245714  mov     [rsp+78h+format], rax; format
0x180245719  call    ??$ComTraceMessageT@KKJ@@YAXPEBD0HW4TraceLevel@@PEBGKKJ@Z; ComTraceMessageT<ulong,ulong,long>(char const *,char const *,int,TraceLevel,ushort const *,ulong,ulong,long)
0x18024571e  nop
0x18024571f  jmp     loc_18000D44C
```
