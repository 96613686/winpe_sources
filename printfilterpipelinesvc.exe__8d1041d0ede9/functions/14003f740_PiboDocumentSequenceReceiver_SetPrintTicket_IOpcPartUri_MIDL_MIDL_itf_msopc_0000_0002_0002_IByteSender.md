# PiboDocumentSequenceReceiver::SetPrintTicket(IOpcPartUri *,__MIDL___MIDL_itf_msopc_0000_0002_0002,IByteSender *)

- ea: `0x14003f740`
- end: `0x14003faf0`
- name: `?SetPrintTicket@PiboDocumentSequenceReceiver@@UEAAJPEAUIOpcPartUri@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAUIByteSender@@@Z`
- size: `944`
- prototype: `int(PiboDocumentSequenceReceiver *__hidden this, struct IOpcPartUri *, enum __MIDL___MIDL_itf_msopc_0000_0002_0002, struct IByteSender *)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000fa68`
- `0x14000fa98`
- `0x140015980`
- `0x1400172e8`
- `0x140027b74`
- `0x140027bac`
- `0x140029488`
- `0x1400295a8`
- `0x14002ede8`
- `0x14003b2c8`
- `0x14003f740`
- `0x140041258`
- `0x140041f74`
- `0x140042084`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x140055c44`
- `0x140055e58`
- `0x140063010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14003fa93`
- `KERNEL32!LeaveCriticalSection` at `0x14003fa93`

## string_xrefs

- `0x14003f812`: `SetPrintTicket MUSL unpexpected to already have a PT`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall PiboDocumentSequenceReceiver::SetPrintTicket(
        PiboDocumentSequenceReceiver *this,
        struct IOpcPartUri *a2,
        int a3,
        struct IByteSender *a4)
{
  char v7; // si
  const char *v8; // rdx
  unsigned int v9; // r8d
  unsigned int *v10; // rax
  const struct SplException::TSystemException *v11; // r8
  const struct _GUID *v12; // r9
  MuslPrintTicketConvertedStream *v13; // rbx
  struct win_dox::ByteSender *v14; // rax
  const char *v15; // rdx
  unsigned int v16; // r8d
  MuslPrintTicketConvertedStream *v17; // rax
  __int64 v18; // rdx
  MuslConstructPartStream *v19; // rbx
  struct win_dox::ByteSender *v20; // rax
  const char *v21; // rdx
  unsigned int v22; // r8d
  MuslPrintTicketConvertedStream *v23; // rax
  SplException *v26; // rbx
  struct SplException::TSystemException *v27; // rdx
  __int64 v28; // [rsp+0h] [rbp-238h] BYREF
  struct win_dox::ByteSender *v29; // [rsp+20h] [rbp-218h]
  const struct win_musl::TStringEllipseBase *v30; // [rsp+28h] [rbp-210h]
  HINSTANCE v31; // [rsp+30h] [rbp-208h]
  NCoreLibrary::TReferenceCount *v32; // [rsp+40h] [rbp-1F8h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-1F0h]
  NCoreLibrary::TReferenceCount *v34; // [rsp+50h] [rbp-1E8h] BYREF
  MuslPrintTicketConvertedStream *v35; // [rsp+58h] [rbp-1E0h]
  void **v36; // [rsp+60h] [rbp-1D8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-1D0h]
  SplException::TSystemException *v38; // [rsp+70h] [rbp-1C8h] BYREF
  __int64 v39[3]; // [rsp+78h] [rbp-1C0h] BYREF
  unsigned int v40[2]; // [rsp+90h] [rbp-1A8h] BYREF
  unsigned __int64 v41; // [rsp+A8h] [rbp-190h]
  _BYTE v42[160]; // [rsp+B0h] [rbp-188h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+150h] [rbp-E8h] BYREF
  std::bad_alloc *v44; // [rsp+1F0h] [rbp-48h] BYREF
  std::exception *v45; // [rsp+1F8h] [rbp-40h] BYREF

  v7 = 0;
  LODWORD(v32) = 0;
  v33 = 0;
  try
  {
    win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v39, a2);
    win_dox::Uri::GetAbsoluteUri(v39, (OLECHAR *)v40);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v10 = v40;
      if ( v41 > 7 )
        v10 = *(unsigned int **)v40;
      WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, v9, (_DWORD)this - 40, (__int64)v10);
    }
    if ( *((_QWORD *)this + 6) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v42, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v42,
        0x8000FFFF,
        v11,
        v12,
        (unsigned int)v29,
        v30,
        v31);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v42,
        "SetPrintTicket MUSL unpexpected to already have a PT");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v42);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v34 = 0;
    if ( *((_BYTE *)this + 112) )
    {
      v13 = (MuslPrintTicketConvertedStream *)operator new(0x80u, v8, v9);
      v35 = v13;
      if ( v13 )
      {
        v14 = (struct win_dox::ByteSender *)win_dox::ByteSender::ByteSender((win_dox::ByteSender *)&v36, a4);
        v7 = 1;
        LODWORD(v32) = 1;
        v13 = MuslPrintTicketConvertedStream::MuslPrintTicketConvertedStream(
                v13,
                *((struct PrnExcept::SharedString **)this + 15),
                *(struct IImgFilePool **)(*((_QWORD *)this + 5) + 216LL),
                *(struct IMemoryPool **)(*((_QWORD *)this + 5) + 224LL),
                v14);
      }
      v32 = 0;
      v34 = v13;
      PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v32);
      if ( (v7 & 1) != 0 )
      {
        v36 = &win_dox::StartSendBase<IByteSender>::`vftable';
        if ( v37 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          v37 = 0;
        }
      }
      v17 = (MuslPrintTicketConvertedStream *)operator new(0x60u, v15, v16);
      v35 = v17;
      if ( v17 )
        v18 = PiboPrintTicket<MuslPrintTicketConvertedStream>::PiboPrintTicket<MuslPrintTicketConvertedStream>(
                (__int64)v17,
                (const struct win_dox::OpcPartUri *)v39,
                a3,
                (__int64)v13);
      else
        v18 = 0;
    }
    else
    {
      v19 = (MuslConstructPartStream *)operator new(0x78u, v8, v9);
      v35 = v19;
      if ( v19 )
      {
        v20 = (struct win_dox::ByteSender *)win_dox::ByteSender::ByteSender((win_dox::ByteSender *)&v36, a4);
        v7 = 2;
        LODWORD(v32) = 2;
        v19 = MuslConstructPartStream::MuslConstructPartStream(
                v19,
                *(struct IImgFilePool **)(*((_QWORD *)this + 5) + 216LL),
                *(struct IMemoryPool **)(*((_QWORD *)this + 5) + 224LL),
                v20);
      }
      v32 = 0;
      v34 = v19;
      PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v32);
      if ( (v7 & 2) != 0 )
      {
        v36 = &win_dox::StartSendBase<IByteSender>::`vftable';
        if ( v37 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          v37 = 0;
        }
      }
      v23 = (MuslPrintTicketConvertedStream *)operator new(0x60u, v21, v22);
      v35 = v23;
      if ( v23 )
        v18 = PiboPrintTicket<MuslConstructPartStream>::PiboPrintTicket<MuslConstructPartStream>(
                (__int64)v23,
                (const struct win_dox::OpcPartUri *)v39,
                a3,
                (__int64)v19);
      else
        v18 = 0;
    }
    v32 = (NCoreLibrary::TReferenceCount *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = (v18 + 16) & -(__int64)(v18 != 0);
    PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v32);
    PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v34);
    XpsObjectModelState::AddUniquePartToLut(
      *((XpsObjectModelState **)this + 5),
      (const struct win_dox::OpcPartUri *)v39,
      *((struct IUnknown **)this + 6));
    NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 128));
    *((_BYTE *)this + 184) = 1;
    if ( (*((_DWORD *)this + 43))-- == 1 )
      *((_DWORD *)this + 42) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    PiboDocumentSequenceReceiver::SendFdsIfNeeded((PiboDocumentSequenceReceiver *)((char *)this - 40), 1);
    std::wstring::_Tidy_deallocate(v40);
    win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v39);
  }
  catch ( SplException::TSystemException *v38 )
  {
    v27 = (struct SplException::TSystemException *)&v28;
    v26 = v38;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v38);
    return (unsigned int)SplException::SetErrorInfoFromException(v26, v27);
  }
  catch ( std::bad_alloc *v44 )
  {
    v33 = -2147024882;
    SetErrorInfo(0, 0);
    return v33;
  }
  catch ( std::exception *v45 )
  {
    v33 = -2147418113;
    SetErrorInfo(0, 0);
  }
  return v33;
}

```

## disassembly

```asm
0x14003f740  mov     [rsp+arg_10], rbx
0x14003f745  push    rsi
0x14003f746  push    rdi
0x14003f747  push    r12
0x14003f749  push    r14
0x14003f74b  push    r15
0x14003f74d  sub     rsp, 210h
0x14003f754  mov     rax, cs:__security_cookie
0x14003f75b  xor     rax, rsp
0x14003f75e  mov     [rsp+238h+var_38], rax
0x14003f766  mov     r14, r9
0x14003f769  mov     r12d, r8d
0x14003f76c  mov     rdi, rcx
0x14003f76f  xor     esi, esi
0x14003f771  mov     dword ptr [rsp+238h+var_1F8], esi
0x14003f775  mov     [rsp+238h+var_1F0], esi
0x14003f779  lea     rcx, [rsp+238h+var_1C0]; this
0x14003f77e  call    ??$?0PEAUIOpcPartUri@@@OpcPartUri@win_dox@@QEAA@PEAUIOpcPartUri@@@Z; win_dox::OpcPartUri::OpcPartUri(IOpcPartUri *)
0x14003f783  nop
0x14003f784  lea     rdx, [rsp+238h+var_1A8]
0x14003f78c  lea     rcx, [rsp+238h+var_1C0]
0x14003f791  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x14003f796  nop
0x14003f797  lea     rax, WPP_GLOBAL_Control
0x14003f79e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f7a5  cmp     rcx, rax
0x14003f7a8  jz      short loc_14003F7E1
0x14003f7aa  test    byte ptr [rcx+1Ch], 20h
0x14003f7ae  jz      short loc_14003F7E1
0x14003f7b0  lea     rax, [rsp+238h+var_1A8]
0x14003f7b8  cmp     [rsp+238h+var_190], 7
0x14003f7c1  cmova   rax, qword ptr [rsp+238h+var_1A8]
0x14003f7ca  lea     r9, [rdi-28h]
0x14003f7ce  mov     edx, 85h
0x14003f7d3  mov     [rsp+238h+var_218], rax; unsigned int
0x14003f7d8  mov     rcx, [rcx+10h]
0x14003f7dc  call    WPP_SF_qS
0x14003f7e1  cmp     qword ptr [rdi+30h], 0
0x14003f7e6  jz      short loc_14003F850
0x14003f7e8  xor     r8d, r8d; unsigned int
0x14003f7eb  lea     rdx, asc_1400696D8; "-"
0x14003f7f2  lea     rcx, [rsp+238h+var_188]; this
0x14003f7fa  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14003f7ff  nop
0x14003f800  mov     edx, 8000FFFFh; unsigned int
0x14003f805  lea     rcx, [rsp+238h+var_188]; this
0x14003f80d  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14003f812  lea     rdx, aSetprintticket; "SetPrintTicket MUSL unpexpected to alre"...
0x14003f819  lea     rcx, [rsp+238h+var_188]; this
0x14003f821  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14003f826  lea     rdx, [rsp+238h+var_188]; struct SplException::THResultException *
0x14003f82e  lea     rcx, [rsp+238h+pExceptionObject]; this
0x14003f836  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14003f83b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14003f842  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x14003f84a  call    _CxxThrowException_0
0x14003f850  mov     [rsp+238h+var_1E8], 0
0x14003f859  cmp     byte ptr [rdi+70h], 0
0x14003f85d  jz      loc_14003F963
0x14003f863  mov     ecx, 80h; unsigned __int64
0x14003f868  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14003f86d  mov     rbx, rax
0x14003f870  mov     [rsp+238h+var_1E0], rax
0x14003f875  test    rbx, rbx
0x14003f878  jz      short loc_14003F8B7
0x14003f87a  mov     rdx, r14; struct IByteSender *
0x14003f87d  lea     rcx, [rsp+238h+var_1D8]; this
0x14003f882  call    ??$?0PEAUIByteSender@@@ByteSender@win_dox@@QEAA@PEAUIByteSender@@@Z; win_dox::ByteSender::ByteSender(IByteSender *)
0x14003f887  nop
0x14003f888  mov     esi, 1
0x14003f88d  mov     dword ptr [rsp+238h+var_1F8], esi
0x14003f891  mov     r8, [rdi+28h]
0x14003f895  mov     [rsp+238h+var_218], rax; struct win_dox::ByteSender *
0x14003f89a  mov     r9, [r8+0E0h]; struct IMemoryPool *
0x14003f8a1  mov     r8, [r8+0D8h]; struct IImgFilePool *
0x14003f8a8  mov     rdx, [rdi+78h]; struct PrnExcept::SharedString *
0x14003f8ac  mov     rcx, rbx; this
0x14003f8af  call    ??0MuslPrintTicketConvertedStream@@QEAA@PEAVSharedString@PrnExcept@@PEAUIImgFilePool@@PEAUIMemoryPool@@AEAVByteSender@win_dox@@@Z; MuslPrintTicketConvertedStream::MuslPrintTicketConvertedStream(PrnExcept::SharedString *,IImgFilePool *,IMemoryPool *,win_dox::ByteSender &)
0x14003f8b4  mov     rbx, rax
0x14003f8b7  mov     [rsp+238h+var_1F8], 0
0x14003f8c0  mov     [rsp+238h+var_1E8], rbx
0x14003f8c5  lea     rcx, [rsp+238h+var_1F8]
0x14003f8ca  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14003f8cf  nop
0x14003f8d0  test    sil, 1
0x14003f8d4  jz      short loc_14003F901
0x14003f8d6  lea     rax, ??_7?$StartSendBase@UIByteSender@@@win_dox@@6B@; const win_dox::StartSendBase<IByteSender>::`vftable'
0x14003f8dd  mov     [rsp+238h+var_1D8], rax
0x14003f8e2  mov     rcx, [rsp+238h+var_1D0]
0x14003f8e7  test    rcx, rcx
0x14003f8ea  jz      short loc_14003F901
0x14003f8ec  mov     rax, [rcx]
0x14003f8ef  mov     rax, [rax+10h]
0x14003f8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f8f8  mov     [rsp+238h+var_1D0], 0
0x14003f901  mov     ecx, 60h ; '`'; unsigned __int64
0x14003f906  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14003f90b  mov     [rsp+238h+var_1E0], rax
0x14003f910  test    rax, rax
0x14003f913  jz      short loc_14003F92D
0x14003f915  mov     r9, rbx
0x14003f918  mov     r8d, r12d
0x14003f91b  lea     rdx, [rsp+238h+var_1C0]
0x14003f920  mov     rcx, rax
0x14003f923  call    ??0?$PiboPrintTicket@VMuslPrintTicketConvertedStream@@@@QEAA@AEBVOpcPartUri@win_dox@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAVMuslPrintTicketConvertedStream@@@Z; PiboPrintTicket<MuslPrintTicketConvertedStream>::PiboPrintTicket<MuslPrintTicketConvertedStream>(win_dox::OpcPartUri const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,MuslPrintTicketConvertedStream *)
0x14003f928  mov     rdx, rax
0x14003f92b  jmp     short loc_14003F92F
0x14003f92d  xor     edx, edx
0x14003f92f  mov     rax, [rdi+30h]
0x14003f933  mov     [rsp+238h+var_1F8], rax
0x14003f938  lea     rcx, [rdx+10h]
0x14003f93c  neg     rdx
0x14003f93f  sbb     rax, rax
0x14003f942  and     rax, rcx
0x14003f945  mov     [rdi+30h], rax
0x14003f949  lea     rcx, [rsp+238h+var_1F8]
0x14003f94e  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14003f953  nop
0x14003f954  lea     rcx, [rsp+238h+var_1E8]
0x14003f959  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14003f95e  jmp     loc_14003FA58
0x14003f963  mov     ecx, 78h ; 'x'; unsigned __int64
0x14003f968  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14003f96d  mov     rbx, rax
0x14003f970  mov     [rsp+238h+var_1E0], rax
0x14003f975  test    rbx, rbx
0x14003f978  jz      short loc_14003F9B1
0x14003f97a  mov     rdx, r14; struct IByteSender *
0x14003f97d  lea     rcx, [rsp+238h+var_1D8]; this
0x14003f982  call    ??$?0PEAUIByteSender@@@ByteSender@win_dox@@QEAA@PEAUIByteSender@@@Z; win_dox::ByteSender::ByteSender(IByteSender *)
0x14003f987  nop
0x14003f988  mov     esi, 2
0x14003f98d  mov     dword ptr [rsp+238h+var_1F8], esi
0x14003f991  mov     rdx, [rdi+28h]
0x14003f995  mov     r9, rax; struct win_dox::ByteSender *
0x14003f998  mov     r8, [rdx+0E0h]; struct IMemoryPool *
0x14003f99f  mov     rdx, [rdx+0D8h]; struct IImgFilePool *
0x14003f9a6  mov     rcx, rbx; this
0x14003f9a9  call    ??0MuslConstructPartStream@@QEAA@PEAUIImgFilePool@@PEAUIMemoryPool@@AEAVByteSender@win_dox@@@Z; MuslConstructPartStream::MuslConstructPartStream(IImgFilePool *,IMemoryPool *,win_dox::ByteSender &)
0x14003f9ae  mov     rbx, rax
0x14003f9b1  mov     [rsp+238h+var_1F8], 0
0x14003f9ba  mov     [rsp+238h+var_1E8], rbx
0x14003f9bf  lea     rcx, [rsp+238h+var_1F8]
0x14003f9c4  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14003f9c9  nop
0x14003f9ca  test    sil, 2
0x14003f9ce  jz      short loc_14003F9FB
0x14003f9d0  lea     rax, ??_7?$StartSendBase@UIByteSender@@@win_dox@@6B@; const win_dox::StartSendBase<IByteSender>::`vftable'
0x14003f9d7  mov     [rsp+238h+var_1D8], rax
0x14003f9dc  mov     rcx, [rsp+238h+var_1D0]
0x14003f9e1  test    rcx, rcx
0x14003f9e4  jz      short loc_14003F9FB
0x14003f9e6  mov     rax, [rcx]
0x14003f9e9  mov     rax, [rax+10h]
0x14003f9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f9f2  mov     [rsp+238h+var_1D0], 0
0x14003f9fb  mov     ecx, 60h ; '`'; unsigned __int64
0x14003fa00  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14003fa05  mov     [rsp+238h+var_1E0], rax
0x14003fa0a  test    rax, rax
0x14003fa0d  jz      short loc_14003FA27
0x14003fa0f  mov     r9, rbx
0x14003fa12  mov     r8d, r12d
0x14003fa15  lea     rdx, [rsp+238h+var_1C0]
0x14003fa1a  mov     rcx, rax
0x14003fa1d  call    ??0?$PiboPrintTicket@VMuslConstructPartStream@@@@QEAA@AEBVOpcPartUri@win_dox@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAVMuslConstructPartStream@@@Z; PiboPrintTicket<MuslConstructPartStream>::PiboPrintTicket<MuslConstructPartStream>(win_dox::OpcPartUri const &,__MIDL___MIDL_itf_msopc_0000_0002_0002,MuslConstructPartStream *)
0x14003fa22  mov     rdx, rax
0x14003fa25  jmp     short loc_14003FA29
0x14003fa27  xor     edx, edx
0x14003fa29  mov     rax, [rdi+30h]
0x14003fa2d  mov     [rsp+238h+var_1F8], rax
0x14003fa32  lea     rcx, [rdx+10h]
0x14003fa36  neg     rdx
0x14003fa39  sbb     rax, rax
0x14003fa3c  and     rax, rcx
0x14003fa3f  mov     [rdi+30h], rax
0x14003fa43  lea     rcx, [rsp+238h+var_1F8]
0x14003fa48  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14003fa4d  nop
0x14003fa4e  lea     rcx, [rsp+238h+var_1E8]
0x14003fa53  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14003fa58  mov     r8, [rdi+30h]; struct IUnknown *
0x14003fa5c  lea     rdx, [rsp+238h+var_1C0]; struct win_dox::OpcPartUri *
0x14003fa61  mov     rcx, [rdi+28h]; this
0x14003fa65  call    ?AddUniquePartToLut@XpsObjectModelState@@QEAAXAEBVOpcPartUri@win_dox@@PEAUIUnknown@@@Z; XpsObjectModelState::AddUniquePartToLut(win_dox::OpcPartUri const &,IUnknown *)
0x14003fa6a  lea     rbx, [rdi+80h]
0x14003fa71  mov     rcx, rbx; this
0x14003fa74  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14003fa79  mov     byte ptr [rdi+0B8h], 1
0x14003fa80  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14003fa84  mov     eax, [rbx+2Ch]
0x14003fa87  jnz     short loc_14003FA90
0x14003fa89  mov     dword ptr [rbx+28h], 0
0x14003fa90  mov     rcx, rbx; lpCriticalSection
0x14003fa93  call    cs:__imp_LeaveCriticalSection
0x14003fa99  mov     dl, 1; bool
0x14003fa9b  lea     rcx, [rdi-28h]; this
0x14003fa9f  call    ?SendFdsIfNeeded@PiboDocumentSequenceReceiver@@AEAAX_N@Z; PiboDocumentSequenceReceiver::SendFdsIfNeeded(bool)
0x14003faa4  nop
0x14003faa5  lea     rcx, [rsp+238h+var_1A8]
0x14003faad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003fab2  nop
0x14003fab3  lea     rcx, [rsp+238h+var_1C0]; this
0x14003fab8  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x14003fabd  nop
0x14003fabe  jmp     short loc_14003FAC4
0x14003fac0  jmp     short loc_14003FAC4
0x14003fac2  jmp     short $+2
0x14003fac4  mov     eax, [rsp+238h+var_1F0]
0x14003fac8  mov     rcx, [rsp+238h+var_38]
0x14003fad0  xor     rcx, rsp; StackCookie
0x14003fad3  call    __security_check_cookie
0x14003fad8  mov     rbx, [rsp+238h+arg_10]
0x14003fae0  add     rsp, 210h
0x14003fae7  pop     r15
0x14003fae9  pop     r14
0x14003faeb  pop     r12
0x14003faed  pop     rdi
0x14003faee  pop     rsi
0x14003faef  retn
```
