# PrnComps::TImgFilePool::~TImgFilePool(void)

- ea: `0x140017a90`
- end: `0x140017b41`
- name: `??1TImgFilePool@PrnComps@@UEAA@XZ`
- size: `177`
- prototype: `void __fastcall(PrnComps::TImgFilePool *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140017be0`

## callees

- `0x1400084a0`
- `0x14000fa98`
- `0x14000feac`
- `0x140013250`
- `0x140017a90`
- `0x140017e98`
- `0x140018894`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140017af3`
- `KERNEL32!DeleteCriticalSection` at `0x140017af3`

## pseudocode

```c
void __fastcall PrnComps::TImgFilePool::~TImgFilePool(PrnComps::TImgFilePool *this)
{
  NCoreLibrary::TString *v2; // rcx
  NCoreLibrary::TString *v3; // rcx

  *(_QWORD *)this = &PrnComps::TImgFilePool::`vftable'{for `IImgFilePoolX'};
  *((_QWORD *)this + 1) = &PrnComps::TImgFilePool::`vftable'{for `NCOMLibrary::TUnknown'};
  PrnComps::TImgFilePool::RemoveAllItems(this);
  PrnComps::TImgFilePool::ClearStartupItems(this);
  NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>((__int64)this + 216);
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 24);
  PrnExcept::SmartRelease<PrnSharedState::LoadedModule>((char *)this + 184);
  if ( *((int *)this + 44) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    *((_DWORD *)this + 44) = -2147467259;
  }
  NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>((__int64)this + 88);
  NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>((__int64)this + 48);
  NCoreLibrary::TString::vFree(v2, *((void **)this + 4));
  NCoreLibrary::TString::vFree(v3, *((void **)this + 3));
  *((_QWORD *)this + 1) = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x140017a90  mov     [rsp+arg_0], rbx
0x140017a95  push    rdi
0x140017a96  sub     rsp, 20h
0x140017a9a  lea     rax, ??_7TImgFilePool@PrnComps@@6BIImgFilePoolX@@@; const PrnComps::TImgFilePool::`vftable'{for `IImgFilePoolX'}
0x140017aa1  mov     rbx, rcx
0x140017aa4  mov     [rcx], rax
0x140017aa7  lea     rax, ??_7TImgFilePool@PrnComps@@6BTUnknown@NCOMLibrary@@@; const PrnComps::TImgFilePool::`vftable'{for `NCOMLibrary::TUnknown'}
0x140017aae  mov     [rcx+8], rax
0x140017ab2  call    ?RemoveAllItems@TImgFilePool@PrnComps@@AEAAXXZ; PrnComps::TImgFilePool::RemoveAllItems(void)
0x140017ab7  mov     rcx, rbx; this
0x140017aba  call    ?ClearStartupItems@TImgFilePool@PrnComps@@AEAAXXZ; PrnComps::TImgFilePool::ClearStartupItems(void)
0x140017abf  lea     rcx, [rbx+0D8h]
0x140017ac6  call    ??1?$TList@VTEmbeddedLink@TImgReaderFileItem@PrnComps@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>(void)
0x140017acb  lea     rcx, [rbx+0C0h]
0x140017ad2  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x140017ad7  lea     rcx, [rbx+0B8h]
0x140017ade  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140017ae3  lea     rdi, [rbx+80h]
0x140017aea  cmp     dword ptr [rdi+30h], 0
0x140017aee  jl      short loc_140017B00
0x140017af0  mov     rcx, rdi; lpCriticalSection
0x140017af3  call    cs:__imp_DeleteCriticalSection
0x140017af9  mov     dword ptr [rdi+30h], 80004005h
0x140017b00  lea     rcx, [rbx+58h]
0x140017b04  call    ??1?$TList@VTEmbeddedLink@TImgReaderFileItem@PrnComps@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>(void)
0x140017b09  lea     rcx, [rbx+30h]
0x140017b0d  call    ??1?$TList@VTEmbeddedLink@TImgReaderFileItem@PrnComps@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>(void)
0x140017b12  mov     rdx, [rbx+20h]; void *
0x140017b16  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x140017b1b  mov     rdx, [rbx+18h]; void *
0x140017b1f  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x140017b24  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140017b2b  mov     [rbx+8], rax
0x140017b2f  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140017b36  mov     rbx, [rsp+28h+arg_0]
0x140017b3b  add     rsp, 20h
0x140017b3f  pop     rdi
0x140017b40  retn
```
