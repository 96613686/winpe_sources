# CMPEG2Demultiplexer::~CMPEG2Demultiplexer(void)

- ea: `0x18002337c`
- end: `0x180023684`
- name: `??1CMPEG2Demultiplexer@@UEAA@XZ`
- size: `776`
- prototype: `void __fastcall(CMPEG2Demultiplexer *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800a48f0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x18000e2f8`
- `0x18002166c`
- `0x180021d84`
- `0x18002337c`
- `0x180023af8`
- `0x180023b3c`
- `0x180023b84`
- `0x180024244`
- `0x18002455c`
- `0x18002d514`
- `0x1800522f4`
- `0x180073d4c`
- `0x1800a6b6c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800234c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800234c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002362d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002362d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023673`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023673`

## pseudocode

```c
void __fastcall CMPEG2Demultiplexer::~CMPEG2Demultiplexer(CMPEG2Demultiplexer *this)
{
  unsigned int v2; // edx
  __int64 v3; // rdi
  unsigned int v4; // esi
  __int64 v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rcx
  CMPEG2PushClock *v8; // rcx
  CDShowMPEG2Demux *v9; // rdi
  void *v10; // rdi
  CRefCountedCritSec **v11; // rdi
  CMpeg2Stats *v12; // rcx
  HKEY v13; // rcx
  CRefCountedCritSec *v14; // rcx
  BufferWriter::CBufferWriter *v15; // rcx
  void *v16; // rcx
  char v17; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CMPEG2Demultiplexer::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CPsiParserFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CMPEG2Demultiplexer::`vftable'{for `CPersistStream'};
  *((_QWORD *)this + 17) = &CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'};
  *((_QWORD *)this + 18) = &CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'};
  *((_QWORD *)this + 19) = &CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'};
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v17,
    "CMPEG2Demultiplexer::~CMPEG2Demultiplexer",
    1061);
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 19, &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids, this);
  v3 = 0;
  v4 = *((_DWORD *)this + 48);
  v5 = *((_QWORD *)this + 23);
  if ( v4 )
  {
    do
    {
      DEMUX_PIN_RECORD::Release(*(DEMUX_PIN_RECORD **)(v5 + 8 * v3));
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < v4 );
  }
  v6 = *((_QWORD *)this + 20);
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 8) + 16LL))(*(_QWORD *)(v6 + 8));
    *((_QWORD *)this + 20) = 0;
  }
  v7 = *((_QWORD *)this + 43);
  if ( v7 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
  v8 = (CMPEG2PushClock *)*((_QWORD *)this + 35);
  if ( v8 )
    CMPEG2PushClock::`scalar deleting destructor'(v8, v2);
  v9 = (CDShowMPEG2Demux *)*((_QWORD *)this + 21);
  if ( v9 )
  {
    CDShowMPEG2Demux::~CDShowMPEG2Demux(v9);
    operator delete(v9);
  }
  v10 = (void *)*((_QWORD *)this + 22);
  if ( v10 )
  {
    CBDAMPEG2Demux::~CBDAMPEG2Demux(*((CBDAMPEG2Demux **)this + 22));
    operator delete(v10);
  }
  v11 = (CRefCountedCritSec **)*((_QWORD *)this + 44);
  if ( v11 )
  {
    CRefCountedCritSec::Release(v11[4]);
    operator delete(v11);
  }
  CRefCountedCritSec::Release(*((CRefCountedCritSec **)this + 10));
  v12 = (CMpeg2Stats *)*((_QWORD *)this + 33);
  if ( v12 )
  {
    CMpeg2Stats::Release(v12);
    *((_QWORD *)this + 33) = 0;
  }
  v13 = (HKEY)*((_QWORD *)this + 34);
  if ( v13 )
  {
    RegCloseKey(v13);
    *((_QWORD *)this + 34) = 0;
  }
  v14 = (CRefCountedCritSec *)*((_QWORD *)this + 45);
  if ( v14 )
  {
    CRefCountedCritSec::Release(v14);
    *((_QWORD *)this + 45) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  v15 = (BufferWriter::CBufferWriter *)*((_QWORD *)this + 47);
  if ( v15 )
  {
    BufferWriter::CBufferWriter::Release(v15);
    *((_QWORD *)this + 47) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 48);
  if ( v16 )
    CloseHandle(v16);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  FreeMediaType((struct _AMMediaType *)((char *)this + 1552));
  FreeMediaType((struct _AMMediaType *)((char *)this + 1464));
  *((_QWORD *)this + 180) = &CDShowESEventEx::`vftable';
  TSimpleVector<CStreamToPinMap *>::~TSimpleVector<CStreamToPinMap *>((char *)this + 184);
  *((_QWORD *)this + 15) = &CPersistStream::`vftable';
  CBaseFilter::~CBaseFilter(this);
}

```

## disassembly

```asm
0x18002337c  mov     [rsp+arg_8], rbx
0x180023381  mov     [rsp+arg_10], rsi
0x180023386  push    rdi
0x180023387  push    r14
0x180023389  push    r15
0x18002338b  sub     rsp, 20h
0x18002338f  lea     rax, ??_7CMPEG2Demultiplexer@@6BCUnknown@@@; const CMPEG2Demultiplexer::`vftable'{for `CUnknown'}
0x180023396  mov     rbx, rcx
0x180023399  mov     [rcx], rax
0x18002339c  lea     rdx, aCmpeg2demultip_46; "CMPEG2Demultiplexer::~CMPEG2Demultiplex"...
0x1800233a3  lea     rax, ??_7CMPEG2Demultiplexer@@6BIBaseFilter@@@; const CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'}
0x1800233aa  mov     r8d, 425h; int
0x1800233b0  mov     [rcx+18h], rax
0x1800233b4  lea     rax, ??_7CPsiParserFilter@@6BIAMovieSetup@@@; const CPsiParserFilter::`vftable'{for `IAMovieSetup'}
0x1800233bb  mov     [rcx+20h], rax
0x1800233bf  lea     rax, ??_7CMPEG2Demultiplexer@@6BCPersistStream@@@; const CMPEG2Demultiplexer::`vftable'{for `CPersistStream'}
0x1800233c6  mov     [rcx+78h], rax
0x1800233ca  lea     rax, ??_7CMPEG2Demultiplexer@@6BIAMFilterMiscFlags@@@; const CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'}
0x1800233d1  mov     [rcx+88h], rax
0x1800233d8  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIInputStreamEvent@@@; const CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'}
0x1800233df  mov     [rcx+90h], rax
0x1800233e6  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIProgramInfo@@@; const CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'}
0x1800233ed  mov     [rcx+98h], rax
0x1800233f4  lea     rcx, [rsp+38h+arg_0]; this
0x1800233f9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800233fe  cmp     cs:byte_1800EACCB, 8
0x180023405  jnb     loc_1800235D9
0x18002340b  lea     r15, [rbx+0B8h]
0x180023412  xor     edi, edi
0x180023414  mov     esi, [r15+8]
0x180023418  mov     r14, [r15]
0x18002341b  test    esi, esi
0x18002341d  jnz     loc_180023600
0x180023423  mov     rcx, [rbx+0A0h]
0x18002342a  test    rcx, rcx
0x18002342d  jnz     loc_180023568
0x180023433  mov     rcx, [rbx+158h]
0x18002343a  test    rcx, rcx
0x18002343d  jnz     loc_180023552
0x180023443  mov     rcx, [rbx+118h]; this
0x18002344a  test    rcx, rcx
0x18002344d  jnz     loc_1800235CF
0x180023453  mov     rdi, [rbx+0A8h]
0x18002345a  mov     esi, 38h ; '8'
0x18002345f  test    rdi, rdi
0x180023462  jnz     loc_180023588
0x180023468  mov     rdi, [rbx+0B0h]
0x18002346f  test    rdi, rdi
0x180023472  jnz     loc_1800235A0
0x180023478  mov     rdi, [rbx+160h]
0x18002347f  test    rdi, rdi
0x180023482  jnz     loc_180023614
0x180023488  mov     rcx, [rbx+50h]; this
0x18002348c  call    ?Release@CRefCountedCritSec@@QEAAKXZ; CRefCountedCritSec::Release(void)
0x180023491  mov     rcx, [rbx+108h]; this
0x180023498  test    rcx, rcx
0x18002349b  jnz     loc_1800235BA
0x1800234a1  mov     rcx, [rbx+110h]; hKey
0x1800234a8  test    rcx, rcx
0x1800234ab  jnz     loc_18002362D
0x1800234b1  mov     rcx, [rbx+168h]; this
0x1800234b8  test    rcx, rcx
0x1800234bb  jnz     loc_180023649
0x1800234c1  lea     rcx, [rbx+130h]; lpCriticalSection
0x1800234c8  call    cs:__imp_DeleteCriticalSection
0x1800234cf  nop     dword ptr [rax+rax+00h]
0x1800234d4  mov     rcx, [rbx+178h]; this
0x1800234db  test    rcx, rcx
0x1800234de  jnz     loc_18002365E
0x1800234e4  mov     rcx, [rbx+180h]; hObject
0x1800234eb  test    rcx, rcx
0x1800234ee  jnz     loc_180023673
0x1800234f4  lea     rcx, [rsp+38h+arg_0]; this
0x1800234f9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800234fe  lea     rcx, [rbx+610h]; struct _AMMediaType *
0x180023505  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18002350a  lea     rcx, [rbx+5B8h]; struct _AMMediaType *
0x180023511  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180023516  lea     rax, ??_7CDShowESEventEx@@6B@; const CDShowESEventEx::`vftable'
0x18002351d  mov     rcx, r15
0x180023520  mov     [rbx+5A0h], rax
0x180023527  call    ??1?$TSimpleVector@PEAVCStreamToPinMap@@@@QEAA@XZ; TSimpleVector<CStreamToPinMap *>::~TSimpleVector<CStreamToPinMap *>(void)
0x18002352c  lea     rax, ??_7CPersistStream@@6B@; const CPersistStream::`vftable'
0x180023533  mov     rcx, rbx; this
0x180023536  mov     [rbx+78h], rax
0x18002353a  mov     rbx, [rsp+38h+arg_8]
0x18002353f  mov     rsi, [rsp+38h+arg_10]
0x180023544  add     rsp, 20h
0x180023548  pop     r15
0x18002354a  pop     r14
0x18002354c  pop     rdi
0x18002354d  jmp     ??1CBaseFilter@@UEAA@XZ; CBaseFilter::~CBaseFilter(void)
0x180023552  mov     rax, [rcx]
0x180023555  mov     edx, 1
0x18002355a  mov     rax, [rax+28h]
0x18002355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023563  jmp     loc_180023443
0x180023568  mov     rcx, [rcx+8]
0x18002356c  mov     rax, [rcx]
0x18002356f  mov     rax, [rax+10h]
0x180023573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023578  mov     qword ptr [rbx+0A0h], 0
0x180023583  jmp     loc_180023433
0x180023588  mov     rcx, rdi; this
0x18002358b  call    ??1CDShowMPEG2Demux@@QEAA@XZ; CDShowMPEG2Demux::~CDShowMPEG2Demux(void)
0x180023590  mov     rdx, rsi
0x180023593  mov     rcx, rdi; Block
0x180023596  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002359b  jmp     loc_180023468
0x1800235a0  mov     rcx, rdi; this
0x1800235a3  call    ??1CBDAMPEG2Demux@@QEAA@XZ; CBDAMPEG2Demux::~CBDAMPEG2Demux(void)
0x1800235a8  mov     edx, 58h ; 'X'
0x1800235ad  mov     rcx, rdi; Block
0x1800235b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800235b5  jmp     loc_180023478
0x1800235ba  call    ?Release@CMpeg2Stats@@QEAAKXZ; CMpeg2Stats::Release(void)
0x1800235bf  mov     qword ptr [rbx+108h], 0
0x1800235ca  jmp     loc_1800234A1
0x1800235cf  call    ??_GCMPEG2PushClock@@QEAAPEAXI@Z; CMPEG2PushClock::`scalar deleting destructor'(uint)
0x1800235d4  jmp     loc_180023453
0x1800235d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235e0  lea     r8, WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids
0x1800235e7  mov     edx, 13h
0x1800235ec  mov     r9, rbx
0x1800235ef  mov     rcx, [rcx+88h]
0x1800235f6  call    WPP_SF_q
0x1800235fb  jmp     loc_18002340B
0x180023600  mov     rcx, [r14+rdi*8]; this
0x180023604  call    ?Release@DEMUX_PIN_RECORD@@QEAAKXZ; DEMUX_PIN_RECORD::Release(void)
0x180023609  inc     edi
0x18002360b  cmp     edi, esi
0x18002360d  jb      short loc_180023600
0x18002360f  jmp     loc_180023423
0x180023614  mov     rcx, [rdi+20h]; this
0x180023618  call    ?Release@CRefCountedCritSec@@QEAAKXZ; CRefCountedCritSec::Release(void)
0x18002361d  mov     rdx, rsi
0x180023620  mov     rcx, rdi; Block
0x180023623  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023628  jmp     loc_180023488
0x18002362d  call    cs:__imp_RegCloseKey
0x180023634  nop     dword ptr [rax+rax+00h]
0x180023639  mov     qword ptr [rbx+110h], 0
0x180023644  jmp     loc_1800234B1
0x180023649  call    ?Release@CRefCountedCritSec@@QEAAKXZ; CRefCountedCritSec::Release(void)
0x18002364e  mov     qword ptr [rbx+168h], 0
0x180023659  jmp     loc_1800234C1
0x18002365e  call    ?Release@CBufferWriter@BufferWriter@@QEAAJXZ; BufferWriter::CBufferWriter::Release(void)
0x180023663  mov     qword ptr [rbx+178h], 0
0x18002366e  jmp     loc_1800234E4
0x180023673  call    cs:__imp_CloseHandle
0x18002367a  nop     dword ptr [rax+rax+00h]
0x18002367f  jmp     loc_1800234F4
```
