# CClipBase::Terminate(void)

- ea: `0x140057420`
- end: `0x1400577e0`
- name: `?Terminate@CClipBase@@MEAAJXZ`
- size: `960`
- prototype: `__int64 __fastcall(CClipBase *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x14003ed60`

## callees

- `0x140004b1c`
- `0x140004cf4`
- `0x140004d24`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x140035e34`
- `0x14003bcb4`
- `0x140049730`
- `0x14004c360`
- `0x14004f014`
- `0x140057420`
- `0x14006b010`

## import_xrefs

- `USER32!UnregisterClassW` at `0x1400574b3`
- `USER32!UnregisterClassW` at `0x1400574b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400576e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400576e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400577c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400577c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140057772`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140057772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005757a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400575e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005757a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400575e1`

## string_xrefs

- `0x14005746d`: `RemoveNotificationSinks failed!`

## pseudocode

```c
__int64 __fastcall CClipBase::Terminate(CClipBase *this)
{
  int v2; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  int v8; // esi
  __int64 v9; // rdi
  unsigned int v10; // eax
  int v11; // esi
  __int64 v12; // rdi
  unsigned int v13; // eax
  _QWORD *v14; // rdi
  __int64 v15; // rcx
  unsigned int i; // esi
  unsigned int v17; // eax
  int v19; // [rsp+28h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-48h] BYREF
  int v21; // [rsp+38h] [rbp-40h]

  v2 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 96LL))((char *)this - 8);
  if ( v2 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v19 = v2;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"RemoveNotificationSinks failed!",
      v19);
  }
  if ( *((_WORD *)this + 104) )
  {
    UnregisterClassW(L"RdpClipRdrWindowClass", *((HINSTANCE *)this + 27));
    *((_WORD *)this + 104) = 0;
  }
  if ( *((_QWORD *)this + 103) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 824);
    *((_QWORD *)this + 103) = 0;
  }
  v4 = (_QWORD *)((char *)this + 264);
  v5 = *((_QWORD *)this + 33);
  if ( v5 )
  {
    CProxyDataObjectManager::Terminate((CProxyDataObjectManager *)(v5 + 8));
    if ( *v4 )
    {
      TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 264);
      *v4 = 0;
    }
  }
  v6 = (_QWORD *)((char *)this + 272);
  v7 = *((_QWORD *)this + 34);
  if ( v7 )
  {
    CProxyStreamManager::Terminate((CProxyStreamManager *)(v7 + 8));
    if ( *v6 )
    {
      TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 272);
      *v6 = 0;
    }
  }
  v8 = 0;
  v9 = 0;
  do
  {
    if ( *((_QWORD *)this + v9 + 9) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v10, v8);
      }
      CloseHandle(*((HANDLE *)this + v9 + 9));
      *((_QWORD *)this + v9 + 9) = 0;
    }
    ++v8;
    ++v9;
  }
  while ( v8 < 3 );
  v11 = 0;
  v12 = 0;
  do
  {
    if ( *((_QWORD *)this + v12 + 12) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v13, v11);
      }
      CloseHandle(*((HANDLE *)this + v12 + 12));
      *((_QWORD *)this + v12 + 12) = 0;
    }
    ++v11;
    ++v12;
  }
  while ( v11 < 3 );
  if ( *((_QWORD *)this + 83) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 664);
    *((_QWORD *)this + 83) = 0;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 664);
  }
  if ( *((_QWORD *)this + 76) )
  {
    TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 608);
    *((_QWORD *)this + 76) = 0;
  }
  if ( *((_QWORD *)this + 43) )
  {
    TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease((char *)this + 344);
    *((_QWORD *)this + 43) = 0;
  }
  if ( *((_QWORD *)this + 77) )
  {
    TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 616);
    *((_QWORD *)this + 77) = 0;
  }
  if ( *((_QWORD *)this + 78) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 624);
    *((_QWORD *)this + 78) = 0;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 624);
  }
  v14 = (_QWORD *)((char *)this + 632);
  v15 = *((_QWORD *)this + 79);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
  if ( *v14 )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 632);
    *v14 = 0;
  }
  if ( *((_QWORD *)this + 84) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 672);
    *((_QWORD *)this + 84) = 0;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 672);
  }
  if ( *((_QWORD *)this + 105) )
  {
    TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 840);
    *((_QWORD *)this + 105) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  if ( *((_QWORD *)this + 35) )
  {
    TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 280);
    *((_QWORD *)this + 35) = 0;
    TCntPtr<CRdpWindowTracker>::SafeAddRef((char *)this + 280);
  }
  for ( i = 0; i < *((_DWORD *)this + 171); ++i )
  {
    v20 = 0;
    v21 = 0;
    if ( (unsigned int)DynArray<SmartMap<CFileContentsReaderManager,unsigned long>::CCleanType,unsigned long>::GetAt(
                         (char *)this + 680,
                         i,
                         &v20)
      && v20 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 32) + 16LL))(*(_QWORD *)(v20 + 32));
      v20 = 0;
      DynArray<SmartMap<CFileContentsReaderManager,unsigned long>::CCleanType,unsigned long>::AddAt(
        (char *)this + 680,
        i,
        &v20);
    }
  }
  *((_DWORD *)this + 171) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  if ( *((_DWORD *)this + 174) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v17);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
    *((_DWORD *)this + 174) = 0;
  }
  *((_DWORD *)this + 5) |= 4u;
  return 0;
}

```

## disassembly

```asm
0x140057420  push    rbx
0x140057422  push    rbp
0x140057423  push    rsi
0x140057424  push    rdi
0x140057425  push    r12
0x140057427  push    r14
0x140057429  sub     rsp, 48h
0x14005742d  mov     rbx, rcx
0x140057430  add     rcx, 0FFFFFFFFFFFFFFF8h
0x140057434  mov     rax, [rcx]
0x140057437  mov     rax, [rax+60h]
0x14005743b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057440  xor     r14d, r14d
0x140057443  lea     r12, WPP_GLOBAL_Control
0x14005744a  mov     edi, eax
0x14005744c  test    eax, eax
0x14005744e  jns     short loc_14005749B
0x140057450  mov     rcx, cs:WPP_GLOBAL_Control
0x140057457  cmp     rcx, r12
0x14005745a  jz      short loc_14005749B
0x14005745c  test    byte ptr [rcx+1Ch], 8
0x140057460  jz      short loc_14005749B
0x140057462  cmp     byte ptr [rcx+19h], 2
0x140057466  jb      short loc_14005749B
0x140057468  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005746d  lea     rcx, aRemovenotifica_2; "RemoveNotificationSinks failed!"
0x140057474  mov     [rsp+78h+var_50], edi
0x140057478  mov     [rsp+78h+var_58], rcx
0x14005747d  lea     edx, [r14+1Fh]
0x140057481  mov     rcx, cs:WPP_GLOBAL_Control
0x140057488  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14005748f  mov     r9d, eax
0x140057492  mov     rcx, [rcx+10h]
0x140057496  call    WPP_SF_DsD
0x14005749b  cmp     [rbx+0D0h], r14w
0x1400574a3  jz      short loc_1400574C1
0x1400574a5  mov     rdx, [rbx+0D8h]; hInstance
0x1400574ac  lea     rcx, aRdpcliprdrwind; "RdpClipRdrWindowClass"
0x1400574b3  call    cs:__imp_UnregisterClassW
0x1400574b9  mov     [rbx+0D0h], r14w
0x1400574c1  lea     rdi, [rbx+338h]
0x1400574c8  cmp     [rdi], r14
0x1400574cb  jz      short loc_1400574D8
0x1400574cd  mov     rcx, rdi
0x1400574d0  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400574d5  mov     [rdi], r14
0x1400574d8  lea     rdi, [rbx+108h]
0x1400574df  mov     rcx, [rdi]
0x1400574e2  test    rcx, rcx
0x1400574e5  jz      short loc_140057500
0x1400574e7  add     rcx, 8; this
0x1400574eb  call    ?Terminate@CProxyDataObjectManager@@UEAAJXZ; CProxyDataObjectManager::Terminate(void)
0x1400574f0  cmp     [rdi], r14
0x1400574f3  jz      short loc_140057500
0x1400574f5  mov     rcx, rdi
0x1400574f8  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x1400574fd  mov     [rdi], r14
0x140057500  lea     rdi, [rbx+110h]
0x140057507  mov     rcx, [rdi]
0x14005750a  test    rcx, rcx
0x14005750d  jz      short loc_140057528
0x14005750f  add     rcx, 8; this
0x140057513  call    ?Terminate@CProxyStreamManager@@UEAAJXZ; CProxyStreamManager::Terminate(void)
0x140057518  cmp     [rdi], r14
0x14005751b  jz      short loc_140057528
0x14005751d  mov     rcx, rdi
0x140057520  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140057525  mov     [rdi], r14
0x140057528  mov     esi, r14d
0x14005752b  mov     rdi, r14
0x14005752e  cmp     [rbx+rdi*8+48h], r14
0x140057533  jz      short loc_140057585
0x140057535  mov     rcx, cs:WPP_GLOBAL_Control
0x14005753c  cmp     rcx, r12
0x14005753f  jz      short loc_140057575
0x140057541  test    byte ptr [rcx+1Ch], 1
0x140057545  jz      short loc_140057575
0x140057547  cmp     byte ptr [rcx+19h], 5
0x14005754b  jb      short loc_140057575
0x14005754d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140057552  mov     rcx, cs:WPP_GLOBAL_Control
0x140057559  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140057560  mov     edx, 20h ; ' '
0x140057565  mov     dword ptr [rsp+78h+var_58], esi
0x140057569  mov     r9d, eax
0x14005756c  mov     rcx, [rcx+10h]
0x140057570  call    WPP_SF_Dd
0x140057575  mov     rcx, [rbx+rdi*8+48h]; hObject
0x14005757a  call    cs:__imp_CloseHandle
0x140057580  mov     [rbx+rdi*8+48h], r14
0x140057585  inc     esi
0x140057587  inc     rdi
0x14005758a  cmp     esi, 3
0x14005758d  jl      short loc_14005752E
0x14005758f  mov     esi, r14d
0x140057592  mov     rdi, r14
0x140057595  cmp     [rbx+rdi*8+60h], r14
0x14005759a  jz      short loc_1400575EC
0x14005759c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400575a3  cmp     rcx, r12
0x1400575a6  jz      short loc_1400575DC
0x1400575a8  test    byte ptr [rcx+1Ch], 1
0x1400575ac  jz      short loc_1400575DC
0x1400575ae  cmp     byte ptr [rcx+19h], 5
0x1400575b2  jb      short loc_1400575DC
0x1400575b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400575b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400575c0  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400575c7  mov     edx, 21h ; '!'
0x1400575cc  mov     dword ptr [rsp+78h+var_58], esi
0x1400575d0  mov     r9d, eax
0x1400575d3  mov     rcx, [rcx+10h]
0x1400575d7  call    WPP_SF_Dd
0x1400575dc  mov     rcx, [rbx+rdi*8+60h]; hObject
0x1400575e1  call    cs:__imp_CloseHandle
0x1400575e7  mov     [rbx+rdi*8+60h], r14
0x1400575ec  inc     esi
0x1400575ee  inc     rdi
0x1400575f1  cmp     esi, 3
0x1400575f4  jl      short loc_140057595
0x1400575f6  lea     rdi, [rbx+298h]
0x1400575fd  cmp     [rdi], r14
0x140057600  jz      short loc_140057615
0x140057602  mov     rcx, rdi
0x140057605  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005760a  mov     rcx, rdi
0x14005760d  mov     [rdi], r14
0x140057610  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140057615  lea     rdi, [rbx+260h]
0x14005761c  cmp     [rdi], r14
0x14005761f  jz      short loc_14005762C
0x140057621  mov     rcx, rdi
0x140057624  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140057629  mov     [rdi], r14
0x14005762c  lea     rdi, [rbx+158h]
0x140057633  cmp     [rdi], r14
0x140057636  jz      short loc_140057643
0x140057638  mov     rcx, rdi
0x14005763b  call    ?SafeRelease@?$TCntPtr@V?$CTSObjectPool@VCTSBufferResult@@@@@@AEAAXXZ; TCntPtr<CTSObjectPool<CTSBufferResult>>::SafeRelease(void)
0x140057640  mov     [rdi], r14
0x140057643  lea     rdi, [rbx+268h]
0x14005764a  cmp     [rdi], r14
0x14005764d  jz      short loc_14005765A
0x14005764f  mov     rcx, rdi
0x140057652  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140057657  mov     [rdi], r14
0x14005765a  lea     rdi, [rbx+270h]
0x140057661  cmp     [rdi], r14
0x140057664  jz      short loc_140057679
0x140057666  mov     rcx, rdi
0x140057669  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005766e  mov     rcx, rdi
0x140057671  mov     [rdi], r14
0x140057674  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140057679  lea     rdi, [rbx+278h]
0x140057680  mov     rcx, [rdi]
0x140057683  test    rcx, rcx
0x140057686  jz      short loc_140057694
0x140057688  mov     rax, [rcx]
0x14005768b  mov     rax, [rax+20h]
0x14005768f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057694  cmp     [rdi], r14
0x140057697  jz      short loc_1400576A4
0x140057699  mov     rcx, rdi
0x14005769c  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400576a1  mov     [rdi], r14
0x1400576a4  lea     rdi, [rbx+2A0h]
0x1400576ab  cmp     [rdi], r14
0x1400576ae  jz      short loc_1400576C3
0x1400576b0  mov     rcx, rdi
0x1400576b3  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400576b8  mov     rcx, rdi
0x1400576bb  mov     [rdi], r14
0x1400576be  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x1400576c3  lea     rdi, [rbx+348h]
0x1400576ca  cmp     [rdi], r14
0x1400576cd  jz      short loc_1400576DA
0x1400576cf  mov     rcx, rdi
0x1400576d2  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x1400576d7  mov     [rdi], r14
0x1400576da  lea     rbp, [rbx+2C0h]
0x1400576e1  mov     rcx, rbp; lpCriticalSection
0x1400576e4  call    cs:__imp_EnterCriticalSection
0x1400576ea  lea     rdi, [rbx+118h]
0x1400576f1  cmp     [rdi], r14
0x1400576f4  jz      short loc_140057709
0x1400576f6  mov     rcx, rdi
0x1400576f9  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x1400576fe  mov     rcx, rdi
0x140057701  mov     [rdi], r14
0x140057704  call    ?SafeAddRef@?$TCntPtr@VCRdpWindowTracker@@@@AEAAXXZ; TCntPtr<CRdpWindowTracker>::SafeAddRef(void)
0x140057709  lea     rdi, [rbx+2A8h]
0x140057710  mov     esi, r14d
0x140057713  cmp     [rdi+4], r14d
0x140057717  jbe     short loc_14005776B
0x140057719  lea     r8, [rsp+78h+var_48]
0x14005771e  mov     [rsp+78h+var_48], r14
0x140057723  mov     edx, esi
0x140057725  mov     [rsp+78h+var_40], r14d
0x14005772a  mov     rcx, rdi
0x14005772d  call    ?GetAt@?$DynArray@VCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@K@@QEAAHKPEAVCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@@Z; DynArray<SmartMap<CFileContentsReaderManager,ulong>::CCleanType,ulong>::GetAt(ulong,SmartMap<CFileContentsReaderManager,ulong>::CCleanType *)
0x140057732  test    eax, eax
0x140057734  jz      short loc_140057764
0x140057736  mov     rcx, [rsp+78h+var_48]
0x14005773b  test    rcx, rcx
0x14005773e  jz      short loc_140057764
0x140057740  mov     rcx, [rcx+20h]
0x140057744  mov     rax, [rcx]
0x140057747  mov     rax, [rax+10h]
0x14005774b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057750  lea     r8, [rsp+78h+var_48]
0x140057755  mov     [rsp+78h+var_48], r14
0x14005775a  mov     edx, esi
0x14005775c  mov     rcx, rdi
0x14005775f  call    ?AddAt@?$DynArray@VCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@K@@QEAAHKAEAVCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@@Z; DynArray<SmartMap<CFileContentsReaderManager,ulong>::CCleanType,ulong>::AddAt(ulong,SmartMap<CFileContentsReaderManager,ulong>::CCleanType &)
0x140057764  inc     esi
0x140057766  cmp     esi, [rdi+4]
0x140057769  jb      short loc_140057719
0x14005776b  mov     rcx, rbp; lpCriticalSection
0x14005776e  mov     [rdi+4], r14d
0x140057772  call    cs:__imp_LeaveCriticalSection
0x140057778  cmp     [rbx+2B8h], r14d
0x14005777f  jz      short loc_1400577CD
0x140057781  mov     rax, cs:WPP_GLOBAL_Control
0x140057788  cmp     rax, r12
0x14005778b  jz      short loc_1400577BD
0x14005778d  test    byte ptr [rax+1Ch], 1
0x140057791  jz      short loc_1400577BD
0x140057793  cmp     byte ptr [rax+19h], 5
0x140057797  jb      short loc_1400577BD
0x140057799  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005779e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400577a5  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400577ac  mov     edx, 22h ; '"'
0x1400577b1  mov     r9d, eax
0x1400577b4  mov     rcx, [rcx+10h]
0x1400577b8  call    WPP_SF_d
0x1400577bd  mov     rcx, rbp; lpCriticalSection
0x1400577c0  call    cs:__imp_DeleteCriticalSection
0x1400577c6  mov     [rbx+2B8h], r14d
0x1400577cd  or      dword ptr [rbx+14h], 4
0x1400577d1  xor     eax, eax
0x1400577d3  add     rsp, 48h
0x1400577d7  pop     r14
0x1400577d9  pop     r12
0x1400577db  pop     rdi
0x1400577dc  pop     rsi
0x1400577dd  pop     rbp
0x1400577de  pop     rbx
0x1400577df  retn
```
