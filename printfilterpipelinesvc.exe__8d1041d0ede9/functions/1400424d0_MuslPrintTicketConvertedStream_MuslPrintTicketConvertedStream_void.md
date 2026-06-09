# MuslPrintTicketConvertedStream::~MuslPrintTicketConvertedStream(void)

- ea: `0x1400424d0`
- end: `0x14004259f`
- name: `??1MuslPrintTicketConvertedStream@@UEAA@XZ`
- size: `207`
- prototype: `void __fastcall(MuslPrintTicketConvertedStream *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140042830`

## callees

- `0x14000fa68`
- `0x14000fa98`
- `0x14000fb28`
- `0x140016660`
- `0x1400424d0`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14004257d`
- `KERNEL32!DeleteCriticalSection` at `0x14004257d`

## pseudocode

```c
void __fastcall MuslPrintTicketConvertedStream::~MuslPrintTicketConvertedStream(MuslPrintTicketConvertedStream *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &MuslPrintTicketConvertedStream::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_493655d623ee38c77a142fb5cefccf42_Traceguids, this);
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 15);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 14);
  *((_QWORD *)this + 12) = &win_dox::StartSendBase<IByteSender>::`vftable';
  v2 = *((_QWORD *)this + 13);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 13) = 0;
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 11);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 10);
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 9);
  if ( *((int *)this + 16) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    *((_DWORD *)this + 16) = -2147467259;
  }
  *(_QWORD *)this = &NCoreLibrary::TReferenceCount::`vftable';
}

```

## disassembly

```asm
0x1400424d0  mov     [rsp+arg_0], rbx
0x1400424d5  push    rdi
0x1400424d6  sub     rsp, 20h
0x1400424da  mov     rbx, rcx
0x1400424dd  lea     rax, ??_7MuslPrintTicketConvertedStream@@6B@; const MuslPrintTicketConvertedStream::`vftable'
0x1400424e4  mov     [rcx], rax
0x1400424e7  lea     rax, WPP_GLOBAL_Control
0x1400424ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400424f5  cmp     rcx, rax
0x1400424f8  jz      short loc_14004251E
0x1400424fa  test    byte ptr [rcx+1Ch], 10h
0x1400424fe  jz      short loc_14004251E
0x140042500  cmp     byte ptr [rcx+19h], 4
0x140042504  jb      short loc_14004251E
0x140042506  mov     edx, 16h
0x14004250b  mov     r9, rbx
0x14004250e  lea     r8, WPP_493655d623ee38c77a142fb5cefccf42_Traceguids
0x140042515  mov     rcx, [rcx+10h]
0x140042519  call    WPP_SF_q
0x14004251e  lea     rcx, [rbx+78h]
0x140042522  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140042527  lea     rcx, [rbx+70h]
0x14004252b  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140042530  lea     rax, ??_7?$StartSendBase@UIByteSender@@@win_dox@@6B@; const win_dox::StartSendBase<IByteSender>::`vftable'
0x140042537  mov     [rbx+60h], rax
0x14004253b  mov     rcx, [rbx+68h]
0x14004253f  test    rcx, rcx
0x140042542  jz      short loc_140042558
0x140042544  mov     rax, [rcx]
0x140042547  mov     rax, [rax+10h]
0x14004254b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042550  mov     qword ptr [rbx+68h], 0
0x140042558  lea     rcx, [rbx+58h]
0x14004255c  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140042561  lea     rcx, [rbx+50h]
0x140042565  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14004256a  lea     rcx, [rbx+48h]
0x14004256e  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x140042573  cmp     dword ptr [rbx+40h], 0
0x140042577  jl      short loc_14004258A
0x140042579  lea     rcx, [rbx+10h]; lpCriticalSection
0x14004257d  call    cs:__imp_DeleteCriticalSection
0x140042583  mov     dword ptr [rbx+40h], 80004005h
0x14004258a  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x140042591  mov     [rbx], rax
0x140042594  mov     rbx, [rsp+28h+arg_0]
0x140042599  add     rsp, 20h
0x14004259d  pop     rdi
0x14004259e  retn
```
