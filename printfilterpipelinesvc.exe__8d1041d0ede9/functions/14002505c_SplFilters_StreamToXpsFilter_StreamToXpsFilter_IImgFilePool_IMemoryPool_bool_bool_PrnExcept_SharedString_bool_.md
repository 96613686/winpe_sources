# SplFilters::StreamToXpsFilter::StreamToXpsFilter(IImgFilePool *,IMemoryPool *,bool,bool,PrnExcept::SharedString *,bool,PFPM_XPS_TYPE,PFPM_XPS_TYPE,void *,bool,ulong)

- ea: `0x14002505c`
- end: `0x1400252db`
- name: `??0StreamToXpsFilter@SplFilters@@QEAA@PEAUIImgFilePool@@PEAUIMemoryPool@@_N2PEAVSharedString@PrnExcept@@2W4PFPM_XPS_TYPE@@4PEAX_NK@Z`
- size: `639`
- prototype: `__int64 __fastcall(__int64, const char *, __int64, char, char, __int64, char, unsigned int, int, char *, char, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14001e3f8`
- `0x14001e558`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140005470`
- `0x14000fa40`
- `0x14000fb28`
- `0x14001b1f8`
- `0x14001ce08`
- `0x14002505c`
- `0x14002a660`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14002521f`
- `KERNEL32!CreateEventW` at `0x14002521f`

## string_xrefs

- `0x1400252ab`: `StreamToXpsFilter() : CreateEvent failed.`

## pseudocode

```c
__int64 __fastcall SplFilters::StreamToXpsFilter::StreamToXpsFilter(
        __int64 a1,
        const char *a2,
        __int64 a3,
        char a4,
        char a5,
        __int64 a6,
        char a7,
        unsigned int a8,
        int a9,
        char *a10,
        char a11,
        int a12)
{
  _QWORD *v16; // r14
  void *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rcx
  const char *v20; // rdx
  unsigned int v21; // r8d
  _DWORD *v22; // rax
  _DWORD *v23; // rbx
  __int64 v24; // rcx
  HANDLE EventW; // rax
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  unsigned int v29; // r9d
  NCoreLibrary *v31; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v33; // r8
  const struct _GUID *v34; // r9
  unsigned int v35; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v36; // [rsp+28h] [rbp-D8h]
  HINSTANCE v37; // [rsp+30h] [rbp-D0h]
  __int64 v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v39[160]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-10h] BYREF

  v38[1] = a1;
  *(_QWORD *)a1 = &NCOMLibrary::TUnknown::`vftable';
  *(_DWORD *)(a1 + 8) = 1852534389;
  *(_DWORD *)(a1 + 12) = 1;
  _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
  *(_QWORD *)a1 = &SplFilters::StreamToXpsFilter::`vftable'{for `NCOMLibrary::TUnknown'};
  *(_QWORD *)(a1 + 16) = &SplFilters::StreamToXpsFilter::`vftable'{for `IPrintPipelineFilter'};
  *(_QWORD *)(a1 + 24) = &SplFilters::StreamToXpsFilter::`vftable'{for `IXpsFilterProducer'};
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 64) = 0;
  *(_BYTE *)(a1 + 65) = a5;
  v16 = (_QWORD *)(a1 + 72);
  *(_QWORD *)(a1 + 72) = -1;
  *(_QWORD *)(a1 + 80) = -1;
  *(_BYTE *)(a1 + 88) = 0;
  *(_BYTE *)(a1 + 89) = a11;
  v17 = operator new(0x120u, a2, a3);
  v38[0] = (__int64)v17;
  if ( v17 )
  {
    LODWORD(v37) = a12;
    LODWORD(v36) = a9;
    v35 = a8;
    LOBYTE(v18) = a7;
    v19 = XpsObjectModelState::XpsObjectModelState(v17, a2, a3, v18);
  }
  else
  {
    v19 = 0;
  }
  v38[0] = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = v19;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(v38);
  v22 = operator new(0x38u, v20, v21);
  v23 = v22;
  v38[0] = (__int64)v22;
  if ( v22 )
  {
    v24 = *(_QWORD *)(a1 + 48);
    *(_QWORD *)v22 = &NCOMLibrary::TUnknown::`vftable';
    v22[2] = 1852534389;
    v22[3] = 1;
    _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
    *(_QWORD *)v22 = &XpsPiboMuslConstructed::`vftable'{for `NCOMLibrary::TUnknown'};
    *((_QWORD *)v22 + 2) = &XpsPiboMuslConstructed::`vftable'{for `IXpsDocumentProvider'};
    *((_QWORD *)v22 + 3) = &XpsPiboMuslConstructed::`vftable'{for `IShutdownComponent'};
    *((_QWORD *)v22 + 4) = v24;
    PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(v24);
    *((_QWORD *)v23 + 5) = a6;
    PrnExcept::SmartAddRef<PrnExcept::SharedString>(a6);
    *((_BYTE *)v23 + 48) = a4;
  }
  else
  {
    v23 = 0;
  }
  v38[0] = *(_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v23;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(v38);
  EventW = CreateEventW(0, 1, 0, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(v16, EventW);
  if ( *v16 == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v39, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v31);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v39,
      LastErrorAsHResult,
      v33,
      v34,
      v35,
      v36,
      v37);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v39,
      "StreamToXpsFilter() : CreateEvent failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v39);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( (unsigned __int64)(a10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v26 = NCoreLibrary::TRefHandleNT::CopyFrom((NCoreLibrary::TRefHandleNT *)(a1 + 80), a10);
    if ( v26 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v26, v27, v28, v29);
  }
  return a1;
}

```

## disassembly

```asm
0x14002505c  mov     [rsp-8+arg_18], rbx
0x140025061  push    rbp
0x140025062  push    rsi
0x140025063  push    rdi
0x140025064  push    r12
0x140025066  push    r13
0x140025068  push    r14
0x14002506a  push    r15
0x14002506c  lea     rbp, [rsp-0A0h]
0x140025074  sub     rsp, 1A0h
0x14002507b  mov     rax, cs:__security_cookie
0x140025082  xor     rax, rsp
0x140025085  mov     [rbp+0D0h+var_40], rax
0x14002508c  mov     r13b, r9b
0x14002508f  mov     r12, r8
0x140025092  mov     rbx, rdx
0x140025095  mov     rdi, rcx
0x140025098  mov     [rsp+1D0h+var_188], rcx
0x14002509d  mov     rsi, [rbp+0D0h+arg_48]
0x1400250a4  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x1400250ab  mov     [rcx], rax
0x1400250ae  mov     dword ptr [rcx+8], 6E6B6E75h
0x1400250b5  mov     dword ptr [rcx+0Ch], 1
0x1400250bc  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x1400250c3  lea     rax, ??_7StreamToXpsFilter@SplFilters@@6BTUnknown@NCOMLibrary@@@; const SplFilters::StreamToXpsFilter::`vftable'{for `NCOMLibrary::TUnknown'}
0x1400250ca  mov     [rcx], rax
0x1400250cd  lea     rax, ??_7StreamToXpsFilter@SplFilters@@6BIPrintPipelineFilter@@@; const SplFilters::StreamToXpsFilter::`vftable'{for `IPrintPipelineFilter'}
0x1400250d4  mov     [rcx+10h], rax
0x1400250d8  lea     rax, ??_7StreamToXpsFilter@SplFilters@@6BIXpsFilterProducer@@@; const SplFilters::StreamToXpsFilter::`vftable'{for `IXpsFilterProducer'}
0x1400250df  mov     [rcx+18h], rax
0x1400250e3  xor     ecx, ecx
0x1400250e5  mov     [rdi+20h], rcx
0x1400250e9  mov     [rdi+28h], rcx
0x1400250ed  mov     [rdi+30h], rcx
0x1400250f1  mov     [rdi+38h], rcx
0x1400250f5  mov     [rdi+40h], cl
0x1400250f8  mov     al, [rbp+0D0h+arg_20]
0x1400250fe  mov     [rdi+41h], al
0x140025101  lea     r14, [rdi+48h]
0x140025105  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025109  mov     [r14], rax
0x14002510c  mov     [rdi+50h], rax
0x140025110  mov     [rdi+58h], cl
0x140025113  mov     al, [rbp+0D0h+arg_50]
0x140025119  mov     [rdi+59h], al
0x14002511c  mov     ecx, 120h; unsigned __int64
0x140025121  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140025126  mov     rcx, rax
0x140025129  mov     [rsp+1D0h+var_190], rax
0x14002512e  test    rax, rax
0x140025131  jz      short loc_140025168
0x140025133  mov     eax, [rbp+0D0h+arg_58]
0x140025139  mov     dword ptr [rsp+1D0h+var_1A0], eax
0x14002513d  mov     eax, [rbp+0D0h+arg_40]
0x140025143  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x140025147  mov     eax, [rbp+0D0h+arg_38]
0x14002514d  mov     [rsp+1D0h+var_1B0], eax
0x140025151  mov     r9b, [rbp+0D0h+arg_30]
0x140025158  mov     r8, r12
0x14002515b  mov     rdx, rbx
0x14002515e  call    ??0XpsObjectModelState@@QEAA@PEAUIImgFilePool@@PEAUIMemoryPool@@_NW4PFPM_XPS_TYPE@@3K@Z; XpsObjectModelState::XpsObjectModelState(IImgFilePool *,IMemoryPool *,bool,PFPM_XPS_TYPE,PFPM_XPS_TYPE,ulong)
0x140025163  mov     rcx, rax
0x140025166  jmp     short loc_14002516A
0x140025168  xor     ecx, ecx
0x14002516a  mov     rax, [rdi+30h]
0x14002516e  mov     [rsp+1D0h+var_190], rax
0x140025173  mov     [rdi+30h], rcx
0x140025177  lea     rcx, [rsp+1D0h+var_190]
0x14002517c  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140025181  mov     ecx, 38h ; '8'; unsigned __int64
0x140025186  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14002518b  mov     rbx, rax
0x14002518e  mov     [rsp+1D0h+var_190], rax
0x140025193  test    rax, rax
0x140025196  jz      short loc_1400251FA
0x140025198  mov     rcx, [rdi+30h]
0x14002519c  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x1400251a3  mov     [rbx], rax
0x1400251a6  mov     dword ptr [rbx+8], 6E6B6E75h
0x1400251ad  mov     dword ptr [rbx+0Ch], 1
0x1400251b4  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x1400251bb  lea     rax, ??_7XpsPiboMuslConstructed@@6BTUnknown@NCOMLibrary@@@; const XpsPiboMuslConstructed::`vftable'{for `NCOMLibrary::TUnknown'}
0x1400251c2  mov     [rbx], rax
0x1400251c5  lea     rax, ??_7XpsPiboMuslConstructed@@6BIXpsDocumentProvider@@@; const XpsPiboMuslConstructed::`vftable'{for `IXpsDocumentProvider'}
0x1400251cc  mov     [rbx+10h], rax
0x1400251d0  lea     rax, ??_7XpsPiboMuslConstructed@@6BIShutdownComponent@@@; const XpsPiboMuslConstructed::`vftable'{for `IShutdownComponent'}
0x1400251d7  mov     [rbx+18h], rax
0x1400251db  mov     [rbx+20h], rcx
0x1400251df  call    ??$SmartAddRef@V?$PiboResourceDictionary@VMuslConstructPartStream@@@@@PrnExcept@@YAXPEAV?$PiboResourceDictionary@VMuslConstructPartStream@@@@@Z; PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(PiboResourceDictionary<MuslConstructPartStream> *)
0x1400251e4  mov     rcx, [rbp+0D0h+arg_28]
0x1400251eb  mov     [rbx+28h], rcx
0x1400251ef  call    ??$SmartAddRef@VSharedString@PrnExcept@@@PrnExcept@@YAXPEAVSharedString@0@@Z; PrnExcept::SmartAddRef<PrnExcept::SharedString>(PrnExcept::SharedString *)
0x1400251f4  mov     [rbx+30h], r13b
0x1400251f8  jmp     short loc_1400251FC
0x1400251fa  xor     ebx, ebx
0x1400251fc  mov     rax, [rdi+28h]
0x140025200  mov     [rsp+1D0h+var_190], rax
0x140025205  mov     [rdi+28h], rbx
0x140025209  lea     rcx, [rsp+1D0h+var_190]
0x14002520e  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140025213  xor     r9d, r9d; lpName
0x140025216  xor     r8d, r8d; bInitialState
0x140025219  lea     edx, [r9+1]; bManualReset
0x14002521d  xor     ecx, ecx; lpEventAttributes
0x14002521f  call    cs:__imp_CreateEventW
0x140025225  mov     rdx, rax
0x140025228  mov     rcx, r14
0x14002522b  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140025230  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140025234  jz      short loc_140025285
0x140025236  lea     rax, [rsi-1]
0x14002523a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002523e  ja      short loc_140025258
0x140025240  mov     rdx, rsi; void *
0x140025243  lea     rcx, [rdi+50h]; this
0x140025247  call    ?CopyFrom@TRefHandleNT@NCoreLibrary@@QEAAJPEAX@Z; NCoreLibrary::TRefHandleNT::CopyFrom(void *)
0x14002524c  test    eax, eax
0x14002524e  jns     short loc_140025258
0x140025250  mov     ecx, eax; this
0x140025252  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140025258  mov     rax, rdi
0x14002525b  mov     rcx, [rbp+0D0h+var_40]
0x140025262  xor     rcx, rsp; StackCookie
0x140025265  call    __security_check_cookie
0x14002526a  mov     rbx, [rsp+1D0h+arg_18]
0x140025272  add     rsp, 1A0h
0x140025279  pop     r15
0x14002527b  pop     r14
0x14002527d  pop     r13
0x14002527f  pop     r12
0x140025281  pop     rdi
0x140025282  pop     rsi
0x140025283  pop     rbp
0x140025284  retn
0x140025285  xor     r8d, r8d; unsigned int
0x140025288  lea     rdx, asc_1400696D8; "-"
0x14002528f  lea     rcx, [rsp+1D0h+var_180]; this
0x140025294  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140025299  nop
0x14002529a  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14002529f  mov     edx, eax; unsigned int
0x1400252a1  lea     rcx, [rsp+1D0h+var_180]; this
0x1400252a6  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400252ab  lea     rdx, aStreamtoxpsfil_0; "StreamToXpsFilter() : CreateEvent faile"...
0x1400252b2  lea     rcx, [rsp+1D0h+var_180]; this
0x1400252b7  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400252bc  lea     rdx, [rsp+1D0h+var_180]; struct SplException::THResultException *
0x1400252c1  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x1400252c5  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400252ca  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400252d1  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x1400252d5  call    _CxxThrowException_0
```
