# PrnExcept::TPropertyBagWrapper::~TPropertyBagWrapper(void)

- ea: `0x140016dc8`
- end: `0x140016e31`
- name: `??1TPropertyBagWrapper@PrnExcept@@UEAA@XZ`
- size: `105`
- prototype: `void __fastcall(PrnExcept::TPropertyBagWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140016f00`

## callees

- `0x14000fa68`
- `0x140010f04`
- `0x140016dc8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140016e08`
- `KERNEL32!DeleteCriticalSection` at `0x140016e08`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrnExcept::TPropertyBagWrapper::~TPropertyBagWrapper(PrnExcept::TPropertyBagWrapper *this)
{
  *(_QWORD *)this = &PrnExcept::TPropertyBagWrapper::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &PrnExcept::TPropertyBagWrapper::`vftable'{for `IPrintPipelinePropertyBagX'};
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 12);
  PrnExcept::SmartPrinterHandle::Free((PrnExcept::TPropertyBagWrapper *)((char *)this + 80));
  if ( *((int *)this + 18) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 18) = -2147467259;
  }
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x140016dc8  mov     [rsp+arg_0], rbx
0x140016dcd  push    rdi
0x140016dce  sub     rsp, 20h
0x140016dd2  mov     rbx, rcx
0x140016dd5  lea     rax, ??_7TPropertyBagWrapper@PrnExcept@@6BTUnknown@NCOMLibrary@@@; const PrnExcept::TPropertyBagWrapper::`vftable'{for `NCOMLibrary::TUnknown'}
0x140016ddc  mov     [rcx], rax
0x140016ddf  lea     rax, ??_7TPropertyBagWrapper@PrnExcept@@6BIPrintPipelinePropertyBagX@@@; const PrnExcept::TPropertyBagWrapper::`vftable'{for `IPrintPipelinePropertyBagX'}
0x140016de6  mov     [rcx+10h], rax
0x140016dea  add     rcx, 60h ; '`'
0x140016dee  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140016df3  nop
0x140016df4  lea     rcx, [rbx+50h]; this
0x140016df8  call    ?Free@SmartPrinterHandle@PrnExcept@@AEAAXXZ; PrnExcept::SmartPrinterHandle::Free(void)
0x140016dfd  nop
0x140016dfe  cmp     dword ptr [rbx+48h], 0
0x140016e02  jl      short loc_140016E15
0x140016e04  lea     rcx, [rbx+18h]; lpCriticalSection
0x140016e08  call    cs:__imp_DeleteCriticalSection
0x140016e0e  mov     dword ptr [rbx+48h], 80004005h
0x140016e15  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140016e1c  mov     [rbx], rax
0x140016e1f  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x140016e26  mov     rbx, [rsp+28h+arg_0]
0x140016e2b  add     rsp, 20h
0x140016e2f  pop     rdi
0x140016e30  retn
```
