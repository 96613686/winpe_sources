# PiboDocumentSequenceReceiver::~PiboDocumentSequenceReceiver(void)

- ea: `0x14002b058`
- end: `0x14002b15e`
- name: `??1PiboDocumentSequenceReceiver@@UEAA@XZ`
- size: `262`
- prototype: `void __fastcall(PiboDocumentSequenceReceiver *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002bc30`

## callees

- `0x14000fa68`
- `0x14000fa98`
- `0x14000fb28`
- `0x140016660`
- `0x14002ad10`
- `0x14002ae00`
- `0x14002b058`
- `0x140055c44`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002b0f9`
- `KERNEL32!DeleteCriticalSection` at `0x14002b0f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PiboDocumentSequenceReceiver::~PiboDocumentSequenceReceiver(PiboDocumentSequenceReceiver *this)
{
  *(_QWORD *)this = &PiboDocumentSequenceReceiver::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &PiboDocumentSequenceReceiver::`vftable'{for `IFixedDocumentSequence'};
  *((_QWORD *)this + 3) = &PiboDocumentSequenceReceiver::`vftable'{for `ISerializeFixedDocumentSequence'};
  *((_QWORD *)this + 4) = &PiboDocumentSequenceReceiver::`vftable'{for `IPrintFilterFinishCallback'};
  *((_QWORD *)this + 5) = &PiboDocumentSequenceReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerDocumentSequenceRelationshipReceiver'};
  *((_QWORD *)this + 6) = &PiboDocumentSequenceReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerDocumentReceiver'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids, this);
  }
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 29);
  if ( *((int *)this + 54) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    *((_DWORD *)this + 54) = -2147467259;
  }
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 20);
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::~_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>((void **)this + 17);
  std::deque<PrnExcept::TRefSmartPtr<FdElement>>::~deque<PrnExcept::TRefSmartPtr<FdElement>>((char *)this + 96);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 11);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 10);
  win_dox::OpcPartUri::~OpcPartUri((PiboDocumentSequenceReceiver *)((char *)this + 56));
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x14002b058  mov     [rsp+arg_0], rbx
0x14002b05d  push    rdi
0x14002b05e  sub     rsp, 20h
0x14002b062  lea     rax, ??_7PiboDocumentSequenceReceiver@@6BTUnknown@NCOMLibrary@@@; const PiboDocumentSequenceReceiver::`vftable'{for `NCOMLibrary::TUnknown'}
0x14002b069  mov     rbx, rcx
0x14002b06c  mov     [rcx], rax
0x14002b06f  lea     rax, ??_7PiboDocumentSequenceReceiver@@6BIFixedDocumentSequence@@@; const PiboDocumentSequenceReceiver::`vftable'{for `IFixedDocumentSequence'}
0x14002b076  mov     [rcx+10h], rax
0x14002b07a  lea     rax, ??_7PiboDocumentSequenceReceiver@@6BISerializeFixedDocumentSequence@@@; const PiboDocumentSequenceReceiver::`vftable'{for `ISerializeFixedDocumentSequence'}
0x14002b081  mov     [rcx+18h], rax
0x14002b085  lea     rax, ??_7PiboDocumentSequenceReceiver@@6BIPrintFilterFinishCallback@@@; const PiboDocumentSequenceReceiver::`vftable'{for `IPrintFilterFinishCallback'}
0x14002b08c  mov     [rcx+20h], rax
0x14002b090  lea     rax, ??_7PiboDocumentSequenceReceiver@@6BIXpsConsumerDocumentSequenceRelationshipReceiver@XpsConsumerLayer@XpsPush@@@; const PiboDocumentSequenceReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerDocumentSequenceRelationshipReceiver'}
0x14002b097  mov     [rcx+28h], rax
0x14002b09b  lea     rax, ??_7PiboDocumentSequenceReceiver@@6BIXpsConsumerDocumentReceiver@XpsConsumerLayer@XpsPush@@@; const PiboDocumentSequenceReceiver::`vftable'{for `XpsPush::XpsConsumerLayer::IXpsConsumerDocumentReceiver'}
0x14002b0a2  mov     [rcx+30h], rax
0x14002b0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b0ad  lea     rax, WPP_GLOBAL_Control
0x14002b0b4  cmp     rcx, rax
0x14002b0b7  jz      short loc_14002B0DD
0x14002b0b9  test    byte ptr [rcx+1Ch], 10h
0x14002b0bd  jz      short loc_14002B0DD
0x14002b0bf  cmp     byte ptr [rcx+19h], 4
0x14002b0c3  jb      short loc_14002B0DD
0x14002b0c5  mov     rcx, [rcx+10h]
0x14002b0c9  lea     r8, WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids
0x14002b0d0  mov     edx, 75h ; 'u'
0x14002b0d5  mov     r9, rbx
0x14002b0d8  call    WPP_SF_q
0x14002b0dd  lea     rcx, [rbx+0E8h]
0x14002b0e4  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14002b0e9  lea     rdi, [rbx+0A8h]
0x14002b0f0  cmp     dword ptr [rdi+30h], 0
0x14002b0f4  jl      short loc_14002B106
0x14002b0f6  mov     rcx, rdi; lpCriticalSection
0x14002b0f9  call    cs:__imp_DeleteCriticalSection
0x14002b0ff  mov     dword ptr [rdi+30h], 80004005h
0x14002b106  lea     rcx, [rbx+0A0h]
0x14002b10d  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14002b112  lea     rcx, [rbx+88h]
0x14002b119  call    ??1?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::~_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>(void)
0x14002b11e  lea     rcx, [rbx+60h]
0x14002b122  call    ??1?$deque@V?$TRefSmartPtr@VFdElement@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@VFdElement@@@PrnExcept@@@std@@@std@@QEAA@XZ; std::deque<PrnExcept::TRefSmartPtr<FdElement>>::~deque<PrnExcept::TRefSmartPtr<FdElement>>(void)
0x14002b127  lea     rcx, [rbx+58h]
0x14002b12b  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b130  lea     rcx, [rbx+50h]
0x14002b134  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x14002b139  lea     rcx, [rbx+38h]; this
0x14002b13d  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x14002b142  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x14002b149  mov     [rbx], rax
0x14002b14c  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14002b153  mov     rbx, [rsp+28h+arg_0]
0x14002b158  add     rsp, 20h
0x14002b15c  pop     rdi
0x14002b15d  retn
```
