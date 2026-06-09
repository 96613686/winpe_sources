# CDllHost::GetApartmentActivators(ulong &,ulong &)

- ea: `0x18001186c`
- end: `0x180011b60`
- name: `?GetApartmentActivators@CDllHost@@AEAAJAEAK0@Z`
- size: `756`
- prototype: `__int64 __fastcall(CDllHost *this, unsigned int *hCOMActivator, unsigned int *hWinRTActivator)`
- caller_count: `8`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011510`
- `0x180011750`
- `0x180101854`
- `0x180110ccc`
- `0x180144d40`
- `0x18018858c`
- `0x1801885f4`
- `0x18019fdc0`

## callees

- `0x180006250`
- `0x180006570`
- `0x180006ea0`
- `0x18000712c`
- `0x18001186c`
- `0x180012dd4`
- `0x180027cfc`
- `0x180037eb0`
- `0x180038028`
- `0x18003a8bc`
- `0x18007340c`
- `0x18007b38c`
- `0x18008ba3c`
- `0x1800cf598`
- `0x18013dcac`
- `0x180140a58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011932`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011932`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800119d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800119d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001199a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001199a`

## string_xrefs

- `0x1800118a5`: `onecore\com\combase\objact\dllhost.cxx`
- `0x18001195d`: `onecore\com\combase\objact\dllhost.cxx`

## pseudocode

```c
__int64 __fastcall CDllHost::GetApartmentActivators(
        CDllHost *this,
        unsigned int *hCOMActivator,
        unsigned int *hWinRTActivator)
{
  HRESULT inited; // edi
  const char *v7; // r9
  COleStaticMutexSem *p_mxs; // r14
  __int64 v9; // rcx
  _DWORD *ReservedForOle; // rbx
  int v12; // esi
  unsigned int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  HANDLE EventW; // rax
  unsigned int v19; // eax
  CObjectContext *v20; // r15
  unsigned int v21; // ebp
  DWORD CurrentThreadId; // eax
  CApartmentHashTable *v23; // rcx
  HRESULT COMActivatorForCurrentApartment; // eax
  CObjectContext *ThreadDefaultContext; // rdi
  CObjectContext *v26; // r15
  int v27; // ebp
  signed __int32 v28[26]; // [rsp+0h] [rbp-68h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]
  CComApartment *hActivatorLocal; // [rsp+88h] [rbp+20h] BYREF

  inited = InitChannelIfNecessary();
  if ( inited < 0 )
  {
    v14 = 483;
    goto LABEL_14;
  }
  p_mxs = &this->_mxs;
  COleStaticMutexSem::Request(&this->_mxs, "onecore\\com\\combase\\objact\\dllhost.cxx", 0x1E7u, v7);
  *hCOMActivator = 0;
  inited = -2146959352;
  *hWinRTActivator = 0;
  if ( (this->_dwType & 0x100) == 0 )
  {
    inited = 0;
    if ( !this->_hCOMActivator )
    {
      v15 = this->_dwType & 0x1F;
      if ( v15 == 1 && !gdwMainThreadId )
        goto LABEL_44;
      v16 = v15 - 1;
      if ( !v16 )
      {
        ThreadDefaultContext = GetThreadDefaultContext();
        if ( GetCurrentThreadId() == gdwMainThreadId && IsThreadInNTA() )
        {
          v27 = 1;
          v26 = LeaveNTA(ThreadDefaultContext);
        }
        else
        {
          v26 = 0;
          v27 = 0;
        }
        hActivatorLocal = 0;
        inited = GetApartmentByID(gdwMainThreadId, &hActivatorLocal);
        if ( inited >= 0 )
        {
          this->_hr = -2146959352;
          CComApartment::ClassicSTASendMessage(
            hActivatorLocal,
            0x405u,
            (IMessageParam *)((unsigned __int64)&this->IMessageParam & -(__int64)(this != 0)));
          inited = this->_hr;
          ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CComApartment,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CComApartment,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CComApartment,ObjectLibrary::Details::MixinBase<CComApartment,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(hActivatorLocal);
        }
        if ( v27 )
          EnterNTA(v26);
        goto LABEL_4;
      }
      v17 = v16 - 1;
      if ( v17 )
      {
        v19 = v17 - 2;
        if ( v19 )
        {
          if ( v19 == 4 )
          {
            _InterlockedAdd((volatile signed __int32 *)&gcNAHosts, 1u);
            v20 = 0;
            v21 = this->_dwType & 8;
            if ( v21 )
              v20 = EnterNTA(g_pNTAEmptyCtx);
            this->_dwHostAptId = GetCurrentApartmentId();
            CurrentThreadId = GetCurrentThreadId();
            this->_dwType |= 0x20u;
            this->_dwTid = CurrentThreadId;
            LODWORD(hActivatorLocal) = 0;
            COMActivatorForCurrentApartment = CApartmentHashTable::GetOrCreateCOMActivatorForCurrentApartment(
                                                v23,
                                                1,
                                                (unsigned int *)&hActivatorLocal);
            v9 = (unsigned int)hActivatorLocal;
            inited = COMActivatorForCurrentApartment;
            this->_hCOMActivator = (unsigned int)hActivatorLocal;
            if ( v21 )
              LeaveNTA(v20);
          }
        }
        else
        {
          inited = CDllHost::MTAInitializeActivators(this);
        }
      }
      else
      {
LABEL_44:
        if ( this->_hEvent || (EventW = CreateEventW(0, 0, 0, 0), (this->_hEvent = EventW) != 0) )
        {
          this->_dwType |= 0x20u;
          inited = CacheCreateThread(DLLHostThreadEntry, this, 0);
          if ( inited < 0 || (WaitForSingleObject(this->_hEvent, 0xFFFFFFFF), inited = this->_hr, inited < 0) )
            this->_dwType &= ~0x20u;
        }
        else
        {
          inited = GetLastError() | 0x80070000;
        }
      }
    }
LABEL_4:
    _InterlockedOr(v28, 0);
    *hCOMActivator = this->_hCOMActivator;
    *hWinRTActivator = this->_hWinRTActivator;
  }
  if ( this->_mxs._cLocks-- == 1 )
  {
    LOBYTE(v9) = p_mxs->_lockOrder;
    if ( p_mxs->_lockOrder != Highest )
    {
      ReservedForOle = NtCurrentTeb()->ReservedForOle;
      if ( ReservedForOle )
      {
        v12 = 1 << v9;
        if ( ((1 << v9) & ReservedForOle[144]) == 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v9);
        ReservedForOle[144] &= ~v12;
      }
    }
  }
  LeaveCriticalSection(&p_mxs->_cs);
  if ( inited >= 0 )
    return 0;
  v14 = 658;
LABEL_14:
  wil::details::in1diag3::Return_Hr(retaddr, v14, "onecore\\com\\combase\\objact\\dllhost.cxx", inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001186c  push    rbx
0x18001186e  push    rbp
0x18001186f  push    rsi
0x180011870  push    rdi
0x180011871  push    r12
0x180011873  push    r13
0x180011875  push    r14
0x180011877  push    r15
0x180011879  sub     rsp, 28h
0x18001187d  mov     r12, hWinRTActivator
0x180011880  mov     r13, hCOMActivator
0x180011883  mov     rbx, this
0x180011886  call    ?InitChannelIfNecessary@@YAJXZ; InitChannelIfNecessary(void)
0x18001188b  mov     edi, eax
0x18001188d  test    eax, eax
0x18001188f  js      loc_180011953
0x180011895  lea     r14, [rbx+0B8h]
0x18001189c  mov     r8d, 1E7h; dwLine
0x1800118a2  mov     this, r14; this
0x1800118a5  lea     hCOMActivator, aOnecoreComComb_161; "onecore\\com\\combase\\objact\\dllhost."...
0x1800118ac  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1800118b1  mov     dword ptr [r13+0], 0
0x1800118b9  mov     edi, 80080008h
0x1800118be  mov     dword ptr [r12], 0
0x1800118c6  mov     esi, 1
0x1800118cb  test    dword ptr [rbx+30h], 100h
0x1800118d2  jnz     short loc_1800118F4
0x1800118d4  mov     eax, [rbx+38h]
0x1800118d7  xor     edi, edi
0x1800118d9  test    eax, eax
0x1800118db  jz      loc_180011970
0x1800118e1  lock or [rsp+68h+var_68], 0
0x1800118e6  mov     eax, [rbx+38h]
0x1800118e9  mov     [r13+0], eax
0x1800118ed  mov     eax, [rbx+3Ch]
0x1800118f0  mov     [r12], eax
0x1800118f4  add     dword ptr [r14+4], 0FFFFFFFFh
0x1800118f9  jnz     short loc_18001192E
0x1800118fb  mov     cl, [r14]
0x1800118fe  cmp     cl, 13h
0x180011901  jz      short loc_18001192E
0x180011903  mov     rax, gs:30h
0x18001190c  mov     rbx, [rax+1758h]
0x180011913  test    rbx, rbx
0x180011916  jz      short loc_18001192E
0x180011918  shl     esi, cl
0x18001191a  test    [rbx+240h], esi
0x180011920  jz      loc_1800119EA
0x180011926  not     esi
0x180011928  and     [rbx+240h], esi
0x18001192e  lea     this, [r14+20h]; lpCriticalSection
0x180011932  call    cs:__imp_LeaveCriticalSection
0x180011938  test    edi, edi
0x18001193a  js      loc_180011B56
0x180011940  xor     eax, eax
0x180011942  add     rsp, 28h
0x180011946  pop     r15
0x180011948  pop     r14
0x18001194a  pop     r13
0x18001194c  pop     r12
0x18001194e  pop     rdi
0x18001194f  pop     rsi
0x180011950  pop     rbp
0x180011951  pop     rbx
0x180011952  retn
0x180011953  mov     edx, 1E3h; lineNumber
0x180011958  mov     this, [rsp+68h]; callerReturnAddress
0x18001195d  lea     hWinRTActivator, aOnecoreComComb_161; "onecore\\com\\combase\\objact\\dllhost."...
0x180011964  mov     r9d, edi; hr
0x180011967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001196c  mov     eax, edi
0x18001196e  jmp     short loc_180011942
0x180011970  mov     eax, [rbx+30h]
0x180011973  and     eax, 1Fh
0x180011976  cmp     eax, esi
0x180011978  jz      loc_180011B13
0x18001197e  sub     eax, esi
0x180011980  jz      loc_180011A7F
0x180011986  sub     eax, esi
0x180011988  jnz     short loc_1800119F4
0x18001198a  cmp     [rbx+48h], rdi
0x18001198e  jnz     short loc_1800119AD
0x180011990  xor     r9d, r9d; lpName
0x180011993  xor     r8d, r8d; bInitialState
0x180011996  xor     edx, edx; bManualReset
0x180011998  xor     ecx, ecx; lpEventAttributes
0x18001199a  call    cs:__imp_CreateEventW
0x1800119a0  mov     [rbx+48h], rax
0x1800119a4  test    rax, rax
0x1800119a7  jz      loc_180011B24
0x1800119ad  or      dword ptr [rbx+30h], 20h
0x1800119b1  lea     this, ?DLLHostThreadEntry@@YAKPEAX@Z; fn
0x1800119b8  xor     r8d, r8d; pdwThreadID
0x1800119bb  mov     hCOMActivator, rbx; param
0x1800119be  call    ?CacheCreateThread@@YAJP6AKPEAX@Z0PEAK@Z; CacheCreateThread(ulong (*)(void *),void *,ulong *)
0x1800119c3  mov     edi, eax
0x1800119c5  test    eax, eax
0x1800119c7  js      short loc_1800119E1
0x1800119c9  mov     this, [rbx+48h]; hHandle
0x1800119cd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800119d0  call    cs:__imp_WaitForSingleObject
0x1800119d6  mov     edi, [rbx+58h]
0x1800119d9  test    edi, edi
0x1800119db  jns     loc_1800118E1
0x1800119e1  and     dword ptr [rbx+30h], 0FFFFFFDFh
0x1800119e5  jmp     loc_1800118E1
0x1800119ea  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x1800119ef  jmp     loc_180011926
0x1800119f4  sub     eax, 2
0x1800119f7  jnz     short loc_180011A08
0x1800119f9  mov     this, rbx; this
0x1800119fc  call    ?MTAInitializeActivators@CDllHost@@AEAAJXZ; CDllHost::MTAInitializeActivators(void)
0x180011a01  mov     edi, eax
0x180011a03  jmp     loc_1800118E1
0x180011a08  cmp     eax, 4
0x180011a0b  jnz     loc_1800118E1
0x180011a11  lock add cs:?gcNAHosts@@3KA, esi; ulong gcNAHosts
0x180011a18  mov     ebp, [rbx+30h]
0x180011a1b  xor     r15d, r15d
0x180011a1e  and     ebp, 8
0x180011a21  jz      short loc_180011A32
0x180011a23  mov     this, cs:?g_pNTAEmptyCtx@@3PEAVCObjectContext@@EA; pChangeCtx
0x180011a2a  call    ?EnterNTA@@YAPEAVCObjectContext@@PEAV1@@Z; EnterNTA(CObjectContext *)
0x180011a2f  mov     r15, rax
0x180011a32  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x180011a37  mov     [rbx+34h], eax
0x180011a3a  call    cs:__imp_GetCurrentThreadId
0x180011a40  or      dword ptr [rbx+30h], 20h
0x180011a44  lea     hWinRTActivator, [rsp+68h+hActivatorLocal]; hCOMActivator
0x180011a4c  mov     dl, sil; bOkToCreate
0x180011a4f  mov     [rbx+40h], eax
0x180011a52  mov     dword ptr [rsp+68h+hActivatorLocal], edi
0x180011a59  call    ?GetOrCreateCOMActivatorForCurrentApartment@CApartmentHashTable@@QEAAJ_NAEAK@Z; CApartmentHashTable::GetOrCreateCOMActivatorForCurrentApartment(bool,ulong &)
0x180011a5e  mov     ecx, dword ptr [rsp+68h+hActivatorLocal]
0x180011a65  mov     edi, eax
0x180011a67  mov     [rbx+38h], ecx
0x180011a6a  test    ebp, ebp
0x180011a6c  jz      loc_1800118E1
0x180011a72  mov     this, r15; pChangeCtx
0x180011a75  call    ?LeaveNTA@@YAPEAVCObjectContext@@PEAV1@@Z; LeaveNTA(CObjectContext *)
0x180011a7a  jmp     loc_1800118E1
0x180011a7f  call    ?GetThreadDefaultContext@@YAPEAVCObjectContext@@XZ; GetThreadDefaultContext(void)
0x180011a84  mov     rdi, rax
0x180011a87  call    cs:__imp_GetCurrentThreadId
0x180011a8d  cmp     eax, cs:?gdwMainThreadId@@3KA; ulong gdwMainThreadId
0x180011a93  jz      loc_180011B37
0x180011a99  xor     r15d, r15d
0x180011a9c  xor     ebp, ebp
0x180011a9e  mov     ecx, cs:?gdwMainThreadId@@3KA; dwAptID
0x180011aa4  lea     hCOMActivator, [rsp+68h+hActivatorLocal]; ppComApt
0x180011aac  mov     [rsp+68h+hActivatorLocal], 0
0x180011ab8  call    ?GetApartmentByID@@YAJKPEAPEAVCComApartment@@@Z; GetApartmentByID(ulong,CComApartment * *)
0x180011abd  mov     edi, eax
0x180011abf  test    eax, eax
0x180011ac1  jns     short loc_180011AD8
0x180011ac3  test    ebp, ebp
0x180011ac5  jz      loc_1800118E1
0x180011acb  mov     this, r15; pChangeCtx
0x180011ace  call    ?EnterNTA@@YAPEAVCObjectContext@@PEAV1@@Z; EnterNTA(CObjectContext *)
0x180011ad3  jmp     loc_1800118E1
0x180011ad8  lea     this, [rbx+8]
0x180011adc  mov     dword ptr [rbx+58h], 80080008h
0x180011ae3  mov     rax, rbx
0x180011ae6  mov     edx, 405h; msg
0x180011aeb  neg     rax
0x180011aee  sbb     hWinRTActivator, hWinRTActivator
0x180011af1  and     hWinRTActivator, this; pParam
0x180011af4  mov     this, [rsp+68h+hActivatorLocal]; this
0x180011afc  call    ?ClassicSTASendMessage@CComApartment@@QEAAJIPEAVIMessageParam@@@Z; CComApartment::ClassicSTASendMessage(uint,IMessageParam *)
0x180011b01  mov     this, [rsp+68h+hActivatorLocal]; this
0x180011b09  mov     edi, [rbx+58h]
0x180011b0c  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VCComApartment@@V?$AddComReferenceCounting_ReferenceCountLayer@VCComApartment@@V?$Allocation_SealedClassDeleteSelfLayer@VCComApartment@@V?$MixinBase@VCComApartment@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CComApartment,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CComApartment,ObjectLibrary::Details::Allocation_SealedClassDeleteSelfLayer<CComApartment,ObjectLibrary::Details::MixinBase<CComApartment,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x180011b11  jmp     short loc_180011AC3
0x180011b13  cmp     cs:?gdwMainThreadId@@3KA, edi; ulong gdwMainThreadId
0x180011b19  jz      loc_18001198A
0x180011b1f  jmp     loc_18001197E
0x180011b24  call    cs:__imp_GetLastError
0x180011b2a  mov     edi, eax
0x180011b2c  or      edi, 80070000h
0x180011b32  jmp     loc_1800118E1
0x180011b37  call    ?IsThreadInNTA@@YAHXZ; IsThreadInNTA(void)
0x180011b3c  test    eax, eax
0x180011b3e  jz      loc_180011A99
0x180011b44  mov     this, rdi; pChangeCtx
0x180011b47  mov     ebp, esi
0x180011b49  call    ?LeaveNTA@@YAPEAVCObjectContext@@PEAV1@@Z; LeaveNTA(CObjectContext *)
0x180011b4e  mov     r15, rax
0x180011b51  jmp     loc_180011A9E
0x180011b56  mov     edx, 292h
0x180011b5b  jmp     loc_180011958
```
