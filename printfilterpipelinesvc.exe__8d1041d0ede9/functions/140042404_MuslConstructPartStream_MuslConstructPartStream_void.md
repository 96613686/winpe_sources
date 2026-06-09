# MuslConstructPartStream::~MuslConstructPartStream(void)

- ea: `0x140042404`
- end: `0x1400424ca`
- name: `??1MuslConstructPartStream@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(MuslConstructPartStream *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400427f0`

## callees

- `0x14000fa68`
- `0x14000fb28`
- `0x140016660`
- `0x140042404`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400424a8`
- `KERNEL32!DeleteCriticalSection` at `0x1400424a8`

## pseudocode

```c
void __fastcall MuslConstructPartStream::~MuslConstructPartStream(MuslConstructPartStream *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &MuslConstructPartStream::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_493655d623ee38c77a142fb5cefccf42_Traceguids, this);
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 14);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 13);
  *((_QWORD *)this + 11) = &win_dox::StartSendBase<IByteSender>::`vftable';
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 12) = 0;
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 10);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 9);
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
0x140042404  mov     [rsp+arg_0], rbx
0x140042409  push    rdi
0x14004240a  sub     rsp, 20h
0x14004240e  mov     rbx, rcx
0x140042411  lea     rax, ??_7MuslConstructPartStream@@6B@; const MuslConstructPartStream::`vftable'
0x140042418  mov     [rcx], rax
0x14004241b  lea     rax, WPP_GLOBAL_Control
0x140042422  mov     rcx, cs:WPP_GLOBAL_Control
0x140042429  cmp     rcx, rax
0x14004242c  jz      short loc_140042452
0x14004242e  test    byte ptr [rcx+1Ch], 10h
0x140042432  jz      short loc_140042452
0x140042434  cmp     byte ptr [rcx+19h], 4
0x140042438  jb      short loc_140042452
0x14004243a  mov     edx, 12h
0x14004243f  mov     r9, rbx
0x140042442  lea     r8, WPP_493655d623ee38c77a142fb5cefccf42_Traceguids
0x140042449  mov     rcx, [rcx+10h]
0x14004244d  call    WPP_SF_q
0x140042452  lea     rcx, [rbx+70h]
0x140042456  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14004245b  lea     rcx, [rbx+68h]
0x14004245f  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140042464  lea     rax, ??_7?$StartSendBase@UIByteSender@@@win_dox@@6B@; const win_dox::StartSendBase<IByteSender>::`vftable'
0x14004246b  mov     [rbx+58h], rax
0x14004246f  mov     rcx, [rbx+60h]
0x140042473  test    rcx, rcx
0x140042476  jz      short loc_14004248C
0x140042478  mov     rax, [rcx]
0x14004247b  mov     rax, [rax+10h]
0x14004247f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042484  mov     qword ptr [rbx+60h], 0
0x14004248c  lea     rcx, [rbx+50h]
0x140042490  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140042495  lea     rcx, [rbx+48h]
0x140042499  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14004249e  cmp     dword ptr [rbx+40h], 0
0x1400424a2  jl      short loc_1400424B5
0x1400424a4  lea     rcx, [rbx+10h]; lpCriticalSection
0x1400424a8  call    cs:__imp_DeleteCriticalSection
0x1400424ae  mov     dword ptr [rbx+40h], 80004005h
0x1400424b5  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x1400424bc  mov     [rbx], rax
0x1400424bf  mov     rbx, [rsp+28h+arg_0]
0x1400424c4  add     rsp, 20h
0x1400424c8  pop     rdi
0x1400424c9  retn
```
