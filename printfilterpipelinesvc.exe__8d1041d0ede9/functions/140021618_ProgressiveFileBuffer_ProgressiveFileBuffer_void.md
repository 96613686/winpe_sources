# ProgressiveFileBuffer::~ProgressiveFileBuffer(void)

- ea: `0x140021618`
- end: `0x14002171f`
- name: `??1ProgressiveFileBuffer@@UEAA@XZ`
- size: `263`
- prototype: `void __fastcall(ProgressiveFileBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140021950`

## callees

- `0x1400071e8`
- `0x1400086f8`
- `0x14000d494`
- `0x14000fa68`
- `0x140021598`
- `0x1400215e8`
- `0x140021618`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400216f1`
- `KERNEL32!DeleteCriticalSection` at `0x1400216f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ProgressiveFileBuffer::~ProgressiveFileBuffer(ProgressiveFileBuffer *this)
{
  *(_QWORD *)this = &ProgressiveFileBuffer::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &ProgressiveFileBuffer::`vftable'{for `IPrintWriteStreamX'};
  *((_QWORD *)this + 3) = &ProgressiveFileBuffer::`vftable'{for `IPrintWriteStreamFlush'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_091d6adf7f6b398302582c7b7c9260ff_Traceguids);
  }
  if ( *((_QWORD *)this + 25) )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 20) + 40LL))(
      *((_QWORD *)this + 20),
      *((unsigned int *)this + 26));
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset((char *)this + 216);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset((char *)this + 200);
  FixedByteFlushBuffer<ProgressiveFileBuffer>::~FixedByteFlushBuffer<ProgressiveFileBuffer>((char *)this + 168);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 20);
  std::deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>::~deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>((char *)this + 120);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 12);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 11);
  if ( *((int *)this + 20) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 20) = -2147467259;
  }
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x140021618  mov     [rsp+arg_0], rbx
0x14002161d  mov     [rsp+arg_8], rsi
0x140021622  push    rdi
0x140021623  sub     rsp, 20h
0x140021627  mov     rbx, rcx
0x14002162a  lea     rax, ??_7ProgressiveFileBuffer@@6BTUnknown@NCOMLibrary@@@; const ProgressiveFileBuffer::`vftable'{for `NCOMLibrary::TUnknown'}
0x140021631  mov     [rcx], rax
0x140021634  lea     rax, ??_7ProgressiveFileBuffer@@6BIPrintWriteStreamX@@@; const ProgressiveFileBuffer::`vftable'{for `IPrintWriteStreamX'}
0x14002163b  mov     [rcx+10h], rax
0x14002163f  lea     rax, ??_7ProgressiveFileBuffer@@6BIPrintWriteStreamFlush@@@; const ProgressiveFileBuffer::`vftable'{for `IPrintWriteStreamFlush'}
0x140021646  mov     [rcx+18h], rax
0x14002164a  lea     rax, WPP_GLOBAL_Control
0x140021651  mov     rcx, cs:WPP_GLOBAL_Control
0x140021658  cmp     rcx, rax
0x14002165b  jz      short loc_14002167E
0x14002165d  test    byte ptr [rcx+1Ch], 8
0x140021661  jz      short loc_14002167E
0x140021663  cmp     byte ptr [rcx+19h], 2
0x140021667  jb      short loc_14002167E
0x140021669  mov     edx, 0Ah
0x14002166e  lea     r8, WPP_091d6adf7f6b398302582c7b7c9260ff_Traceguids
0x140021675  mov     rcx, [rcx+10h]
0x140021679  call    WPP_SF_
0x14002167e  lea     rsi, [rbx+0C8h]
0x140021685  lea     rdi, [rbx+0A0h]
0x14002168c  cmp     qword ptr [rsi], 0
0x140021690  jz      short loc_1400216A4
0x140021692  mov     rcx, [rdi]
0x140021695  mov     rax, [rcx]
0x140021698  mov     edx, [rbx+68h]
0x14002169b  mov     rax, [rax+28h]
0x14002169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400216a4  lea     rcx, [rbx+0D8h]
0x1400216ab  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1400216b0  mov     rcx, rsi
0x1400216b3  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x1400216b8  lea     rcx, [rbx+0A8h]
0x1400216bf  call    ??1?$FixedByteFlushBuffer@VProgressiveFileBuffer@@@@QEAA@XZ; FixedByteFlushBuffer<ProgressiveFileBuffer>::~FixedByteFlushBuffer<ProgressiveFileBuffer>(void)
0x1400216c4  mov     rcx, rdi
0x1400216c7  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400216cc  lea     rcx, [rbx+78h]
0x1400216d0  call    ??1?$deque@V?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@VPiboFixedPageReceiver@@@PrnExcept@@@std@@@std@@QEAA@XZ; std::deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>::~deque<PrnExcept::TRefSmartPtr<PiboFixedPageReceiver>>(void)
0x1400216d5  lea     rcx, [rbx+60h]
0x1400216d9  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400216de  lea     rcx, [rbx+58h]
0x1400216e2  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400216e7  cmp     dword ptr [rbx+50h], 0
0x1400216eb  jl      short loc_1400216FE
0x1400216ed  lea     rcx, [rbx+20h]; lpCriticalSection
0x1400216f1  call    cs:__imp_DeleteCriticalSection
0x1400216f7  mov     dword ptr [rbx+50h], 80004005h
0x1400216fe  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140021705  mov     [rbx], rax
0x140021708  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14002170f  mov     rbx, [rsp+28h+arg_0]
0x140021714  mov     rsi, [rsp+28h+arg_8]
0x140021719  add     rsp, 20h
0x14002171d  pop     rdi
0x14002171e  retn
```
