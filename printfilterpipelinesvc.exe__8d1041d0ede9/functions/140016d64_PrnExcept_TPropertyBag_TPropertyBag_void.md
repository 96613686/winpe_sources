# PrnExcept::TPropertyBag::~TPropertyBag(void)

- ea: `0x140016d64`
- end: `0x140016dc2`
- name: `??1TPropertyBag@PrnExcept@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(PrnExcept::TPropertyBag *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140016ec0`

## callees

- `0x14000feac`
- `0x140016d64`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140016d90`
- `KERNEL32!DeleteCriticalSection` at `0x140016d90`

## pseudocode

```c
void __fastcall PrnExcept::TPropertyBag::~TPropertyBag(PrnExcept::TPropertyBag *this)
{
  *(_QWORD *)this = &PrnExcept::TPropertyBag::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &PrnExcept::TPropertyBag::`vftable'{for `IPrintPipelinePropertyBagX'};
  if ( *((int *)this + 28) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    *((_DWORD *)this + 28) = -2147467259;
  }
  NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>((__int64)this + 24);
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x140016d64  mov     [rsp+arg_0], rbx
0x140016d69  push    rdi
0x140016d6a  sub     rsp, 20h
0x140016d6e  lea     rax, ??_7TPropertyBag@PrnExcept@@6BTUnknown@NCOMLibrary@@@; const PrnExcept::TPropertyBag::`vftable'{for `NCOMLibrary::TUnknown'}
0x140016d75  mov     rbx, rcx
0x140016d78  mov     [rcx], rax
0x140016d7b  lea     rax, ??_7TPropertyBag@PrnExcept@@6BIPrintPipelinePropertyBagX@@@; const PrnExcept::TPropertyBag::`vftable'{for `IPrintPipelinePropertyBagX'}
0x140016d82  mov     [rcx+10h], rax
0x140016d86  cmp     dword ptr [rcx+70h], 0
0x140016d8a  jl      short loc_140016D9D
0x140016d8c  add     rcx, 40h ; '@'; lpCriticalSection
0x140016d90  call    cs:__imp_DeleteCriticalSection
0x140016d96  mov     dword ptr [rbx+70h], 80004005h
0x140016d9d  lea     rcx, [rbx+18h]
0x140016da1  call    ??1?$TList@VTEmbeddedLink@TImgReaderFileItem@PrnComps@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>::~TList<PrnComps::TImgReaderFileItem::TEmbeddedLink>(void)
0x140016da6  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140016dad  mov     [rbx], rax
0x140016db0  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140016db7  mov     rbx, [rsp+28h+arg_0]
0x140016dbc  add     rsp, 20h
0x140016dc0  pop     rdi
0x140016dc1  retn
```
