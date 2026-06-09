# TImgPipelineManager::~TImgPipelineManager(void)

- ea: `0x14001c5cc`
- end: `0x14001c718`
- name: `??1TImgPipelineManager@@UEAA@XZ`
- size: `332`
- prototype: `void __fastcall(TImgPipelineManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001caf0`

## callees

- `0x1400084a0`
- `0x1400086f8`
- `0x14000fa68`
- `0x14000fa98`
- `0x14001c2fc`
- `0x14001c32c`
- `0x14001c5cc`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001c691`
- `KERNEL32!DeleteCriticalSection` at `0x14001c691`

## pseudocode

```c
void __fastcall TImgPipelineManager::~TImgPipelineManager(TImgPipelineManager *this)
{
  __int64 *v2; // rdi
  __int64 *v3; // rsi

  *(_QWORD *)this = &TImgPipelineManager::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &TImgPipelineManager::`vftable'{for `IPrintPipelineManagerX'};
  *((_QWORD *)this + 3) = &TImgPipelineManager::`vftable'{for `IPrintPipelineManagerControl'};
  v2 = (__int64 *)((char *)this + 240);
  v3 = (__int64 *)((char *)this + 136);
  if ( !*((_BYTE *)this + 258) )
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*v3 + 24LL))(*v3, *((unsigned int *)this + 62), *v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids);
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 36);
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 33);
  PrnExcept::SmartRelease<IPartResourceDictionary>(v2);
  if ( *((int *)this + 56) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    *((_DWORD *)this + 56) = -2147467259;
  }
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>((NCoreLibrary::TReferenceCount **)this + 20);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 19);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 18);
  PrnExcept::SmartRelease<IPartResourceDictionary>(v3);
  std::deque<FilterInterfaceInfo>::~deque<FilterInterfaceInfo>((char *)this + 96);
  std::deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>::~deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>((void **)this + 7);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 6);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 5);
  PrnExcept::SmartRelease<PrnSharedState::LoadedModule>((char *)this + 32);
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x14001c5cc  mov     [rsp+arg_0], rbx
0x14001c5d1  mov     [rsp+arg_8], rsi
0x14001c5d6  push    rdi
0x14001c5d7  sub     rsp, 20h
0x14001c5db  mov     rbx, rcx
0x14001c5de  lea     rax, ??_7TImgPipelineManager@@6BTUnknown@NCOMLibrary@@@; const TImgPipelineManager::`vftable'{for `NCOMLibrary::TUnknown'}
0x14001c5e5  mov     [rcx], rax
0x14001c5e8  lea     rax, ??_7TImgPipelineManager@@6BIPrintPipelineManagerX@@@; const TImgPipelineManager::`vftable'{for `IPrintPipelineManagerX'}
0x14001c5ef  mov     [rcx+10h], rax
0x14001c5f3  lea     rax, ??_7TImgPipelineManager@@6BIPrintPipelineManagerControl@@@; const TImgPipelineManager::`vftable'{for `IPrintPipelineManagerControl'}
0x14001c5fa  mov     [rcx+18h], rax
0x14001c5fe  lea     rdi, [rcx+0F0h]
0x14001c605  lea     rsi, [rcx+88h]
0x14001c60c  cmp     byte ptr [rcx+102h], 0
0x14001c613  jnz     short loc_14001C62D
0x14001c615  mov     rcx, [rsi]
0x14001c618  mov     rax, [rcx]
0x14001c61b  mov     r8, [rdi]
0x14001c61e  mov     edx, [rbx+0F8h]
0x14001c624  mov     rax, [rax+18h]
0x14001c628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c62d  lea     rax, WPP_GLOBAL_Control
0x14001c634  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c63b  cmp     rcx, rax
0x14001c63e  jz      short loc_14001C661
0x14001c640  test    byte ptr [rcx+1Ch], 8
0x14001c644  jz      short loc_14001C661
0x14001c646  cmp     byte ptr [rcx+19h], 2
0x14001c64a  jb      short loc_14001C661
0x14001c64c  mov     edx, 0Ah
0x14001c651  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14001c658  mov     rcx, [rcx+10h]
0x14001c65c  call    WPP_SF_
0x14001c661  lea     rcx, [rbx+120h]
0x14001c668  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c66d  lea     rcx, [rbx+108h]
0x14001c674  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14001c679  mov     rcx, rdi
0x14001c67c  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c681  lea     rdi, [rbx+0B0h]
0x14001c688  cmp     dword ptr [rdi+30h], 0
0x14001c68c  jl      short loc_14001C69E
0x14001c68e  mov     rcx, rdi; lpCriticalSection
0x14001c691  call    cs:__imp_DeleteCriticalSection
0x14001c697  mov     dword ptr [rdi+30h], 80004005h
0x14001c69e  lea     rcx, [rbx+0A0h]
0x14001c6a5  call    ??$SmartRelease@VTFrameGlobalState@FrameState@@@PrnExcept@@YAXPEAPEAVTFrameGlobalState@FrameState@@@Z; PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(FrameState::TFrameGlobalState * *)
0x14001c6aa  lea     rcx, [rbx+98h]
0x14001c6b1  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c6b6  lea     rcx, [rbx+90h]
0x14001c6bd  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c6c2  mov     rcx, rsi
0x14001c6c5  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c6ca  lea     rcx, [rbx+60h]
0x14001c6ce  call    ??1?$deque@UFilterInterfaceInfo@@V?$allocator@UFilterInterfaceInfo@@@std@@@std@@QEAA@XZ; std::deque<FilterInterfaceInfo>::~deque<FilterInterfaceInfo>(void)
0x14001c6d3  lea     rcx, [rbx+38h]
0x14001c6d7  call    ??1?$deque@V?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@@std@@@std@@QEAA@XZ; std::deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>::~deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>(void)
0x14001c6dc  lea     rcx, [rbx+30h]
0x14001c6e0  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c6e5  lea     rcx, [rbx+28h]
0x14001c6e9  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001c6ee  lea     rcx, [rbx+20h]
0x14001c6f2  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x14001c6f7  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x14001c6fe  mov     [rbx], rax
0x14001c701  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14001c708  mov     rbx, [rsp+28h+arg_0]
0x14001c70d  mov     rsi, [rsp+28h+arg_8]
0x14001c712  add     rsp, 20h
0x14001c716  pop     rdi
0x14001c717  retn
```
