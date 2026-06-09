# InterfaceBuilder::XpsToStream(ulong)

- ea: `0x1400201a0`
- end: `0x140020623`
- name: `?XpsToStream@InterfaceBuilder@@AEAAXK@Z`
- size: `1155`
- prototype: `void __fastcall(InterfaceBuilder *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000fa1c`
- `0x14000fa68`
- `0x14000fac4`
- `0x14000fb28`
- `0x1400172e8`
- `0x14001a750`
- `0x14001a848`
- `0x14001b624`
- `0x14001c7f4`
- `0x14001c82c`
- `0x14001d774`
- `0x1400201a0`
- `0x140020dc0`
- `0x1400212dc`
- `0x14002a7d0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x1400520ec`
- `0x140063010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400205a8`
- `KERNEL32!LeaveCriticalSection` at `0x1400205a8`
- `XpsPushLayer!__imp_ProdXpsPackageToStream1` at `0x140020388`
- `XpsPushLayer!__imp_ProdXpsPackageToStream1` at `0x140020388`

## string_xrefs

- `0x140020435`: `This version of XPS PUSH does not support OpenXPS.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall InterfaceBuilder::XpsToStream(__int64 **this, const char *a2, unsigned int a3)
{
  __int64 v3; // r15
  unsigned int v5; // edi
  __int64 v6; // r13
  TImgPipelineJobDataBuffer *v7; // rax
  TImgPipelineJobDataBuffer *v8; // rbx
  struct IPrintWriteStream *v9; // rbx
  const char *v10; // rdx
  unsigned int v11; // r8d
  PrintWriteStreamToIStream *v12; // rax
  PrintWriteStreamToIStream *v13; // r14
  int v14; // r12d
  bool v15; // bl
  _QWORD *Interface; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // eax
  int v20; // edx
  const char *v21; // r8
  unsigned int v22; // r9d
  int v23; // eax
  int v24; // edx
  const char *v25; // r8
  unsigned int v26; // r9d
  int v27; // eax
  const char *v28; // rdx
  const char *v29; // r8
  unsigned int v30; // r9d
  const struct SplException::TSystemException *v31; // r8
  const struct _GUID *v32; // r9
  __int64 *v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 *v36; // rbx
  const struct win_musl::TStringEllipseBase *v37; // [rsp+28h] [rbp-D8h]
  HINSTANCE v38; // [rsp+30h] [rbp-D0h]
  _BYTE v39[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  PrintWriteStreamToIStream *v41; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A8h] BYREF
  PrintWriteStreamToIStream *v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44[2]; // [rsp+68h] [rbp-98h] BYREF
  struct IPrintWriteStream *v45; // [rsp+70h] [rbp-90h] BYREF
  TImgPipelineJobDataBuffer *v46; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  TImgPipelineJobDataBuffer *v48; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v49; // [rsp+90h] [rbp-70h]
  __int64 *v50; // [rsp+98h] [rbp-68h]
  _BYTE v51[160]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+140h] [rbp+40h] BYREF

  v3 = (unsigned int)a2;
  v5 = 3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids,
      (unsigned int)a2,
      (_DWORD)a2 + 1);
  }
  v6 = 0;
  v48 = 0;
  v7 = (TImgPipelineJobDataBuffer *)operator new(0x28u, a2, a3);
  v46 = v7;
  if ( v7 )
    v8 = TImgPipelineJobDataBuffer::TImgPipelineJobDataBuffer(
           v7,
           (struct PrnSharedState::SharedState *)this[4],
           (struct IImgFilePool *)this[5],
           (struct IMemoryPool *)this[6]);
  else
    v8 = 0;
  v45 = 0;
  v48 = v8;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v45);
  v45 = 0;
  v46 = (TImgPipelineJobDataBuffer *)((char *)v8 + 16);
  v9 = (struct IPrintWriteStream *)(*(__int64 (__fastcall **)(__int64, GUID *, GUID *))(*((_QWORD *)v8 + 2) + 32LL))(
                                     (__int64)v8 + 16,
                                     &GUID_NULL,
                                     &IID_IPrintWriteStreamX);
  v43 = 0;
  v45 = v9;
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v43);
  v43 = 0;
  v12 = (PrintWriteStreamToIStream *)operator new(0x30u, v10, v11);
  v43 = v12;
  if ( v12 )
    v13 = PrintWriteStreamToIStream::PrintWriteStreamToIStream(v12, v9);
  else
    v13 = 0;
  v42 = 0;
  v43 = v13;
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v42);
  v14 = *((_DWORD *)this[2] + 69);
  *(_QWORD *)v44 = 0;
  v41 = v13;
  PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject::TDoneNotifier>(v13);
  v50 = (__int64 *)&v41;
  v40 = (__int64)v13;
  PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject::TDoneNotifier>(v13);
  v49 = &v40;
  win_dox::to_interface<IOpcUri>::resolve(&v42);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v40);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>((__int64 *)&v41);
  if ( v14 != 1 )
    v5 = 1;
  v15 = *((_DWORD *)this + 25) == 0;
  Interface = (_QWORD *)win_dox::Stream::GetInterface(&v42, &v40);
  LOBYTE(v17) = v15;
  LOBYTE(v18) = 1;
  v19 = ProdXpsPackageToStream1(*Interface, v18, v17, v5);
  if ( v19 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v19, v20, v21, v22);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  v39[0] = 0;
  v47 = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v44 + 24LL))(*(_QWORD *)v44, &v47);
  if ( v23 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v23, v24, v25, v26);
  v27 = (*(__int64 (__fastcall **)(__int64, bool, _BYTE *))(*(_QWORD *)v47 + 48LL))(v47, v14 == 1, v39);
  if ( v27 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v27, (int)v28, v29, v30);
  if ( v14 == 1 && !v39[0] )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v51, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v51,
      0x80004005,
      v31,
      v32,
      (unsigned int)v44,
      v37,
      v38);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v51,
      "This version of XPS PUSH does not support OpenXPS.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v51);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v40 = 0;
  v33 = (__int64 *)operator new(0x98u, v28, (unsigned int)v29);
  v49 = v33;
  if ( v33 )
    v6 = XpsSerializerPibo::XpsSerializerPibo(v33, this[3], *(_QWORD *)v44, this[12]);
  v41 = 0;
  v40 = v6;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v41);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 3);
  PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(
    16 * v3 + 8 + **this,
    (v6 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64));
  v34 = **this;
  v35 = (*(__int64 (__fastcall **)(TImgPipelineJobDataBuffer *, GUID *, GUID *))(*(_QWORD *)v46 + 24LL))(
          v46,
          &GUID_NULL,
          &IID_IUnknown);
  v46 = *(TImgPipelineJobDataBuffer **)(v34 + 16LL * (unsigned int)(v3 + 1));
  *(_QWORD *)(v34 + 16LL * (unsigned int)(v3 + 1)) = v35;
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v46);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 9);
  PrnExcept::TRefSmartPtr<XpsSerializerPibo>::operator=(this + 9, &v40);
  v36 = this[2];
  v41 = 0;
  PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(
    &v41,
    (v6 + 24) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64));
  std::deque<PrnExcept::TRefSmartPtr<IUnknown>>::_Emplace_back_internal<PrnExcept::TRefSmartPtr<IUnknown> const &>(
    v36 + 7,
    &v41);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v41);
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)(v6 + 32));
  PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(v6 + 144, ((unsigned __int64)v13 + 24) & -(__int64)(v13 != 0));
  if ( !--*(_DWORD *)(v6 + 76) )
    *(_DWORD *)(v6 + 72) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 32));
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(&v40);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v47);
  win_dox::Uri::~Uri((win_dox::Uri *)&v42);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)v44);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>((__int64 *)&v43);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v45);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v48);
}

```

## disassembly

```asm
0x1400201a0  mov     [rsp-8+arg_10], rbx
0x1400201a5  push    rbp
0x1400201a6  push    rsi
0x1400201a7  push    rdi
0x1400201a8  push    r12
0x1400201aa  push    r13
0x1400201ac  push    r14
0x1400201ae  push    r15
0x1400201b0  lea     rbp, [rsp-0F0h]
0x1400201b8  sub     rsp, 1F0h
0x1400201bf  mov     rax, cs:__security_cookie
0x1400201c6  xor     rax, rsp
0x1400201c9  mov     [rbp+120h+var_40], rax
0x1400201d0  mov     r15d, edx
0x1400201d3  mov     rsi, rcx
0x1400201d6  lea     rax, WPP_GLOBAL_Control
0x1400201dd  mov     edi, 3
0x1400201e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400201e9  cmp     rcx, rax
0x1400201ec  jz      short loc_140020218
0x1400201ee  test    byte ptr [rcx+1Ch], 8
0x1400201f2  jz      short loc_140020218
0x1400201f4  cmp     [rcx+19h], dil
0x1400201f8  jb      short loc_140020218
0x1400201fa  lea     eax, [r15+1]
0x1400201fe  lea     edx, [rdi+21h]
0x140020201  mov     [rsp+220h+var_200], eax
0x140020205  mov     r9d, r15d
0x140020208  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14002020f  mov     rcx, [rcx+10h]
0x140020213  call    WPP_SF_dd
0x140020218  xor     r13d, r13d
0x14002021b  mov     [rbp+120h+var_198], r13
0x14002021f  lea     ecx, [r13+28h]; unsigned __int64
0x140020223  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140020228  mov     [rsp+220h+var_1A8], rax
0x14002022d  test    rax, rax
0x140020230  jz      short loc_14002024B
0x140020232  mov     r9, [rsi+30h]; struct IMemoryPool *
0x140020236  mov     r8, [rsi+28h]; struct IImgFilePool *
0x14002023a  mov     rdx, [rsi+20h]; struct PrnSharedState::SharedState *
0x14002023e  mov     rcx, rax; this
0x140020241  call    ??0TImgPipelineJobDataBuffer@@QEAA@PEAVSharedState@PrnSharedState@@PEAUIImgFilePool@@PEAUIMemoryPool@@@Z; TImgPipelineJobDataBuffer::TImgPipelineJobDataBuffer(PrnSharedState::SharedState *,IImgFilePool *,IMemoryPool *)
0x140020246  mov     rbx, rax
0x140020249  jmp     short loc_14002024E
0x14002024b  mov     rbx, r13
0x14002024e  mov     [rsp+220h+var_1B0], r13
0x140020253  mov     [rbp+120h+var_198], rbx
0x140020257  lea     rcx, [rsp+220h+var_1B0]
0x14002025c  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140020261  mov     [rsp+220h+var_1B0], r13
0x140020266  lea     rcx, [rbx+10h]
0x14002026a  mov     [rsp+220h+var_1A8], rcx
0x14002026f  mov     rax, [rcx]
0x140020272  lea     r8, IID_IPrintWriteStreamX
0x140020279  lea     rdx, GUID_NULL
0x140020280  mov     rax, [rax+20h]
0x140020284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020289  mov     rbx, rax
0x14002028c  mov     [rsp+220h+var_1C0], r13
0x140020291  mov     [rsp+220h+var_1B0], rax
0x140020296  lea     rcx, [rsp+220h+var_1C0]
0x14002029b  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400202a0  mov     [rsp+220h+var_1C0], r13
0x1400202a5  mov     ecx, 30h ; '0'; unsigned __int64
0x1400202aa  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400202af  mov     [rsp+220h+var_1C0], rax
0x1400202b4  test    rax, rax
0x1400202b7  jz      short loc_1400202C9
0x1400202b9  mov     rdx, rbx; struct IPrintWriteStream *
0x1400202bc  mov     rcx, rax; this
0x1400202bf  call    ??0PrintWriteStreamToIStream@@QEAA@PEAUIPrintWriteStream@@@Z; PrintWriteStreamToIStream::PrintWriteStreamToIStream(IPrintWriteStream *)
0x1400202c4  mov     r14, rax
0x1400202c7  jmp     short loc_1400202CC
0x1400202c9  mov     r14, r13
0x1400202cc  mov     [rsp+220h+var_1C8], r13
0x1400202d1  mov     [rsp+220h+var_1C0], r14
0x1400202d6  lea     rcx, [rsp+220h+var_1C8]
0x1400202db  call    ??$SmartRelease@VSequentialSpoolReaderWriter@SplReadWrite@@@PrnExcept@@YAXPEAPEAVSequentialSpoolReaderWriter@SplReadWrite@@@Z; PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(SplReadWrite::SequentialSpoolReaderWriter * *)
0x1400202e0  mov     rax, [rsi+10h]
0x1400202e4  mov     r12d, [rax+114h]
0x1400202eb  mov     qword ptr [rsp+220h+var_1B8], r13
0x1400202f0  mov     [rsp+220h+var_1D0], r14
0x1400202f5  mov     rcx, r14
0x1400202f8  call    ??$SmartAddRef@VTDoneNotifier@SplFilterPipelineCallObject@SplPipeline@@@PrnExcept@@YAXPEAVTDoneNotifier@SplFilterPipelineCallObject@SplPipeline@@@Z; PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject::TDoneNotifier>(SplPipeline::SplFilterPipelineCallObject::TDoneNotifier *)
0x1400202fd  lea     rax, [rsp+220h+var_1D0]
0x140020302  mov     [rbp+120h+var_188], rax
0x140020306  mov     rcx, [rsp+220h+var_1D0]
0x14002030b  mov     [rsp+220h+var_1D8], rcx
0x140020310  call    ??$SmartAddRef@VTDoneNotifier@SplFilterPipelineCallObject@SplPipeline@@@PrnExcept@@YAXPEAVTDoneNotifier@SplFilterPipelineCallObject@SplPipeline@@@Z; PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject::TDoneNotifier>(SplPipeline::SplFilterPipelineCallObject::TDoneNotifier *)
0x140020315  lea     rax, [rsp+220h+var_1D8]
0x14002031a  mov     [rbp+120h+var_190], rax
0x14002031e  mov     rax, [rsp+220h+var_1D8]
0x140020323  lea     rcx, [rax+10h]
0x140020327  neg     rax
0x14002032a  sbb     rdx, rdx
0x14002032d  and     rdx, rcx
0x140020330  lea     rcx, [rsp+220h+var_1C8]
0x140020335  call    ?resolve@?$to_interface@UIOpcUri@@@win_dox@@SA?AV?$scope@PEAUIOpcUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIOpcUri@@@Z; win_dox::to_interface<IOpcUri>::resolve(IOpcUri *)
0x14002033a  nop
0x14002033b  lea     rcx, [rsp+220h+var_1D8]
0x140020340  call    ??$SmartRelease@VSequentialSpoolReaderWriter@SplReadWrite@@@PrnExcept@@YAXPEAPEAVSequentialSpoolReaderWriter@SplReadWrite@@@Z; PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(SplReadWrite::SequentialSpoolReaderWriter * *)
0x140020345  nop
0x140020346  lea     rcx, [rsp+220h+var_1D0]
0x14002034b  call    ??$SmartRelease@VSequentialSpoolReaderWriter@SplReadWrite@@@PrnExcept@@YAXPEAPEAVSequentialSpoolReaderWriter@SplReadWrite@@@Z; PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(SplReadWrite::SequentialSpoolReaderWriter * *)
0x140020350  nop
0x140020351  mov     eax, 1
0x140020356  cmp     r12d, eax
0x140020359  cmovnz  edi, eax
0x14002035c  cmp     [rsi+64h], r13d
0x140020360  setbe   bl
0x140020363  lea     rdx, [rsp+220h+var_1D8]
0x140020368  lea     rcx, [rsp+220h+var_1C8]
0x14002036d  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x140020372  nop
0x140020373  lea     rcx, [rsp+220h+var_1B8]
0x140020378  mov     qword ptr [rsp+220h+var_200], rcx; unsigned int
0x14002037d  mov     r9d, edi
0x140020380  mov     r8b, bl
0x140020383  mov     dl, 1
0x140020385  mov     rcx, [rax]
0x140020388  call    cs:__imp_ProdXpsPackageToStream1
0x14002038e  test    eax, eax
0x140020390  jns     short loc_14002039A
0x140020392  mov     ecx, eax; this
0x140020394  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14002039a  mov     rcx, [rsp+220h+var_1D8]
0x14002039f  test    rcx, rcx
0x1400203a2  jz      short loc_1400203B1
0x1400203a4  mov     rax, [rcx]
0x1400203a7  mov     rax, [rax+10h]
0x1400203ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400203b0  nop
0x1400203b1  mov     [rsp+220h+var_1E0], r13b
0x1400203b6  mov     [rbp+120h+var_1A0], r13
0x1400203ba  mov     rcx, qword ptr [rsp+220h+var_1B8]
0x1400203bf  mov     rax, [rcx]
0x1400203c2  lea     rdx, [rbp+120h+var_1A0]
0x1400203c6  mov     rax, [rax+18h]
0x1400203ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400203cf  test    eax, eax
0x1400203d1  jns     short loc_1400203DB
0x1400203d3  mov     ecx, eax; this
0x1400203d5  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400203db  mov     rcx, [rbp+120h+var_1A0]
0x1400203df  mov     rax, [rcx]
0x1400203e2  mov     edx, r13d
0x1400203e5  cmp     r12d, 1
0x1400203e9  setz    dl
0x1400203ec  lea     r8, [rsp+220h+var_1E0]
0x1400203f1  mov     rax, [rax+30h]
0x1400203f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400203fa  test    eax, eax
0x1400203fc  jns     short loc_140020406
0x1400203fe  mov     ecx, eax; this
0x140020400  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140020406  cmp     r12d, 1
0x14002040a  jnz     short loc_140020463
0x14002040c  cmp     [rsp+220h+var_1E0], r13b
0x140020411  jnz     short loc_140020463
0x140020413  xor     r8d, r8d; unsigned int
0x140020416  lea     rdx, asc_1400696D8; "-"
0x14002041d  lea     rcx, [rbp+120h+var_180]; this
0x140020421  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140020426  nop
0x140020427  mov     edx, 80004005h; unsigned int
0x14002042c  lea     rcx, [rbp+120h+var_180]; this
0x140020430  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140020435  lea     rdx, aThisVersionOfX; "This version of XPS PUSH does not suppo"...
0x14002043c  lea     rcx, [rbp+120h+var_180]; this
0x140020440  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140020445  lea     rdx, [rbp+120h+var_180]; struct SplException::THResultException *
0x140020449  lea     rcx, [rbp+120h+pExceptionObject]; this
0x14002044d  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140020452  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140020459  lea     rcx, [rbp+120h+pExceptionObject]; pExceptionObject
0x14002045d  call    _CxxThrowException_0
0x140020463  mov     [rsp+220h+var_1D8], r13
0x140020468  mov     ecx, 98h; unsigned __int64
0x14002046d  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140020472  mov     [rbp+120h+var_190], rax
0x140020476  test    rax, rax
0x140020479  jz      short loc_140020493
0x14002047b  mov     r9, [rsi+60h]
0x14002047f  mov     r8, qword ptr [rsp+220h+var_1B8]
0x140020484  mov     rdx, [rsi+18h]
0x140020488  mov     rcx, rax
0x14002048b  call    ??0XpsSerializerPibo@@QEAA@PEAVXpsObjectModelState@@PEAUIXpsProdPackageContent@XpsProductionLayer@XpsPush@@U__MIDL___MIDL_itf_filterpipelinei_0000_0000_0003@@@Z; XpsSerializerPibo::XpsSerializerPibo(XpsObjectModelState *,XpsPush::XpsProductionLayer::IXpsProdPackageContent *,__MIDL___MIDL_itf_filterpipelinei_0000_0000_0003)
0x140020490  mov     r13, rax
0x140020493  xor     r12d, r12d
0x140020496  mov     [rsp+220h+var_1D0], r12
0x14002049b  mov     [rsp+220h+var_1D8], r13
0x1400204a0  lea     rcx, [rsp+220h+var_1D0]
0x1400204a5  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400204aa  lea     rcx, [rsi+18h]
0x1400204ae  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400204b3  mov     rax, r13
0x1400204b6  lea     rcx, [r13+10h]
0x1400204ba  neg     rax
0x1400204bd  sbb     rdx, rdx
0x1400204c0  and     rdx, rcx
0x1400204c3  mov     r9, r15
0x1400204c6  shl     r9, 4
0x1400204ca  mov     rax, [rsi]
0x1400204cd  mov     rcx, [rax]
0x1400204d0  add     r9, 8
0x1400204d4  add     rcx, r9
0x1400204d7  call    ??4?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@QEAAAEAV01@PEAUIShutdownComponent@@@Z; PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(IShutdownComponent *)
0x1400204dc  lea     edi, [r15+1]
0x1400204e0  add     rdi, rdi
0x1400204e3  mov     rax, [rsi]
0x1400204e6  mov     rbx, [rax]
0x1400204e9  mov     rcx, [rsp+220h+var_1A8]
0x1400204ee  mov     rax, [rcx]
0x1400204f1  lea     r8, IID_IUnknown
0x1400204f8  lea     rdx, GUID_NULL
0x1400204ff  mov     rax, [rax+18h]
0x140020503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020508  mov     rcx, [rbx+rdi*8]
0x14002050c  mov     [rsp+220h+var_1A8], rcx
0x140020511  mov     [rbx+rdi*8], rax
0x140020515  lea     rcx, [rsp+220h+var_1A8]
0x14002051a  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002051f  lea     rcx, [rsi+48h]
0x140020523  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140020528  lea     rdx, [rsp+220h+var_1D8]
0x14002052d  lea     rcx, [rsi+48h]
0x140020531  call    ??4?$TRefSmartPtr@VXpsSerializerPibo@@@PrnExcept@@QEAAAEAV01@AEBV01@@Z; PrnExcept::TRefSmartPtr<XpsSerializerPibo>::operator=(PrnExcept::TRefSmartPtr<XpsSerializerPibo> const &)
0x140020536  mov     rbx, [rsi+10h]
0x14002053a  mov     rax, r13
0x14002053d  lea     rcx, [r13+18h]
0x140020541  neg     rax
0x140020544  sbb     rdx, rdx
0x140020547  and     rdx, rcx
0x14002054a  mov     [rsp+220h+var_1D0], r12
0x14002054f  lea     rcx, [rsp+220h+var_1D0]
0x140020554  call    ??4?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@QEAAAEAV01@PEAUIShutdownComponent@@@Z; PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(IShutdownComponent *)
0x140020559  lea     rcx, [rbx+38h]
0x14002055d  lea     rdx, [rsp+220h+var_1D0]
0x140020562  call    ??$_Emplace_back_internal@AEBV?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@?$deque@V?$TRefSmartPtr@UIUnknown@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@std@@@std@@AEAAXAEBV?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@Z; std::deque<PrnExcept::TRefSmartPtr<IUnknown>>::_Emplace_back_internal<PrnExcept::TRefSmartPtr<IUnknown> const &>(PrnExcept::TRefSmartPtr<IUnknown> const &)
0x140020567  nop
0x140020568  lea     rcx, [rsp+220h+var_1D0]
0x14002056d  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140020572  lea     rcx, [r13+20h]; this
0x140020576  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14002057b  lea     rax, [r14+18h]
0x14002057f  neg     r14
0x140020582  sbb     rdx, rdx
0x140020585  and     rdx, rax
0x140020588  lea     rcx, [r13+90h]
0x14002058f  call    ??4?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@QEAAAEAV01@PEAUIShutdownComponent@@@Z; PrnExcept::TRefSmartPtr<IShutdownComponent>::operator=(IShutdownComponent *)
0x140020594  dec     dword ptr [r13+4Ch]
0x140020598  mov     eax, [r13+4Ch]
0x14002059c  test    eax, eax
0x14002059e  jnz     short loc_1400205A4
0x1400205a0  mov     [r13+48h], r12d
0x1400205a4  lea     rcx, [r13+20h]; lpCriticalSection
0x1400205a8  call    cs:__imp_LeaveCriticalSection
0x1400205ae  nop
0x1400205af  lea     rcx, [rsp+220h+var_1D8]
0x1400205b4  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400205b9  nop
0x1400205ba  lea     rcx, [rbp+120h+var_1A0]
0x1400205be  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400205c3  nop
0x1400205c4  lea     rcx, [rsp+220h+var_1C8]; this
0x1400205c9  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1400205ce  nop
0x1400205cf  lea     rcx, [rsp+220h+var_1B8]
0x1400205d4  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400205d9  nop
0x1400205da  lea     rcx, [rsp+220h+var_1C0]
0x1400205df  call    ??$SmartRelease@VSequentialSpoolReaderWriter@SplReadWrite@@@PrnExcept@@YAXPEAPEAVSequentialSpoolReaderWriter@SplReadWrite@@@Z; PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(SplReadWrite::SequentialSpoolReaderWriter * *)
0x1400205e4  nop
0x1400205e5  lea     rcx, [rsp+220h+var_1B0]
0x1400205ea  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400205ef  nop
0x1400205f0  lea     rcx, [rbp+120h+var_198]
0x1400205f4  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400205f9  mov     rcx, [rbp+120h+var_40]
0x140020600  xor     rcx, rsp; StackCookie
0x140020603  call    __security_check_cookie
0x140020608  mov     rbx, [rsp+220h+arg_10]
0x140020610  add     rsp, 1F0h
0x140020617  pop     r15
0x140020619  pop     r14
0x14002061b  pop     r13
0x14002061d  pop     r12
0x14002061f  pop     rdi
0x140020620  pop     rsi
0x140020621  pop     rbp
0x140020622  retn
```
