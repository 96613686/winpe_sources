# PiboFixedDocumentReceiver::~PiboFixedDocumentReceiver(void)

- ea: `0x14002b164`
- end: `0x14002b262`
- name: `??1PiboFixedDocumentReceiver@@UEAA@XZ`
- size: `254`
- prototype: `void __fastcall(PiboFixedDocumentReceiver *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002bc70`

## callees

- `0x14000fa68`
- `0x14000fa98`
- `0x14000fb28`
- `0x140016660`
- `0x1400215e8`
- `0x14002b164`
- `0x140055c44`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002b239`
- `KERNEL32!DeleteCriticalSection` at `0x14002b239`

## pseudocode

```c
void __fastcall PiboFixedDocumentReceiver::~PiboFixedDocumentReceiver(PiboFixedDocumentReceiver *this)
{
  *(_QWORD *)this = &PiboFixedDocumentReceiver::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &PiboFixedDocumentReceiver::`vftable'{for `IFixedDocument'};
  *((_QWORD *)this + 3) = &PiboFixedDocumentReceiver::`vftable'{for `ISerializeFixedDocument'};
  *((_QWORD *)this + 4) = &PiboFixedDocumentReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerPageReceiver'};
  *((_QWORD *)this + 5) = &PiboFixedDocumentReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerDocumentRelationshipReceiver'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids, this);
  }
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 28);
  std::deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>::~deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>((char *)this + 184);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 21);
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 20);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 18);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 17);
  win_dox::OpcPartUri::~OpcPartUri((PiboFixedDocumentReceiver *)((char *)this + 104));
  if ( *((int *)this + 24) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    *((_DWORD *)this + 24) = -2147467259;
  }
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x14002b164  mov     [rsp+arg_0], rbx
0x14002b169  push    rdi
0x14002b16a  sub     rsp, 20h
0x14002b16e  lea     rax, ??_7PiboFixedDocumentReceiver@@6BTUnknown@NCOMLibrary@@@; const PiboFixedDocumentReceiver::`vftable'{for `NCOMLibrary::TUnknown'}
0x14002b175  mov     rbx, rcx
0x14002b178  mov     [rcx], rax
0x14002b17b  lea     rax, ??_7PiboFixedDocumentReceiver@@6BIFixedDocument@@@; const PiboFixedDocumentReceiver::`vftable'{for `IFixedDocument'}
0x14002b182  mov     [rcx+10h], rax
0x14002b186  lea     rax, ??_7PiboFixedDocumentReceiver@@6BISerializeFixedDocument@@@; const PiboFixedDocumentReceiver::`vftable'{for `ISerializeFixedDocument'}
0x14002b18d  mov     [rcx+18h], rax
0x14002b191  lea     rax, ??_7PiboFixedDocumentReceiver@@6BIXpsConsumerPageReceiver@XpsConsumerLayer@XpsPush@@@; const PiboFixedDocumentReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerPageReceiver'}
0x14002b198  mov     [rcx+20h], rax
0x14002b19c  lea     rax, ??_7PiboFixedDocumentReceiver@@6BIXpsConsumerDocumentRelationshipReceiver@XpsConsumerLayer@XpsPush@@@; const PiboFixedDocumentReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerDocumentRelationshipReceiver'}
0x14002b1a3  mov     [rcx+28h], rax
0x14002b1a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b1ae  lea     rax, WPP_GLOBAL_Control
0x14002b1b5  cmp     rcx, rax
0x14002b1b8  jz      short loc_14002B1DE
0x14002b1ba  test    byte ptr [rcx+1Ch], 10h
0x14002b1be  jz      short loc_14002B1DE
0x14002b1c0  cmp     byte ptr [rcx+19h], 4
0x14002b1c4  jb      short loc_14002B1DE
0x14002b1c6  mov     rcx, [rcx+10h]
0x14002b1ca  lea     r8, WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids
0x14002b1d1  mov     edx, 61h ; 'a'
0x14002b1d6  mov     r9, rbx
0x14002b1d9  call    WPP_SF_q
0x14002b1de  lea     rcx, [rbx+0E0h]
0x14002b1e5  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14002b1ea  lea     rcx, [rbx+0B8h]
0x14002b1f1  call    ??1?$deque@V?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@@std@@@std@@QEAA@XZ; std::deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>::~deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>(void)
0x14002b1f6  lea     rcx, [rbx+0A8h]
0x14002b1fd  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b202  lea     rcx, [rbx+0A0h]
0x14002b209  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14002b20e  lea     rcx, [rbx+90h]
0x14002b215  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b21a  lea     rcx, [rbx+88h]
0x14002b221  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x14002b226  lea     rcx, [rbx+68h]; this
0x14002b22a  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x14002b22f  cmp     dword ptr [rbx+60h], 0
0x14002b233  jl      short loc_14002B246
0x14002b235  lea     rcx, [rbx+30h]; lpCriticalSection
0x14002b239  call    cs:__imp_DeleteCriticalSection
0x14002b23f  mov     dword ptr [rbx+60h], 80004005h
0x14002b246  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x14002b24d  mov     [rbx], rax
0x14002b250  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14002b257  mov     rbx, [rsp+28h+arg_0]
0x14002b25c  add     rsp, 20h
0x14002b260  pop     rdi
0x14002b261  retn
```
