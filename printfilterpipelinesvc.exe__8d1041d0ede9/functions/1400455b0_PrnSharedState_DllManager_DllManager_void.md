# PrnSharedState::DllManager::~DllManager(void)

- ea: `0x1400455b0`
- end: `0x14004561a`
- name: `??1DllManager@PrnSharedState@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(PrnSharedState::DllManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14004503c`

## callees

- `0x1400086f8`
- `0x140045544`
- `0x1400455b0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400455fb`
- `KERNEL32!DeleteCriticalSection` at `0x1400455fb`

## pseudocode

```c
void __fastcall PrnSharedState::DllManager::~DllManager(PrnSharedState::DllManager *this)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_741966d44b4333880836975686564805_Traceguids);
  }
  if ( *((int *)this + 18) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 18) = -2147467259;
  }
  std::_Tree<std::_Tset_traits<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>,PrnSharedState::lessLoadedModule,std::allocator<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>>,0>>::~_Tree<std::_Tset_traits<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>,PrnSharedState::lessLoadedModule,std::allocator<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>>,0>>(this);
}

```

## disassembly

```asm
0x1400455b0  mov     [rsp+arg_0], rbx
0x1400455b5  push    rdi
0x1400455b6  sub     rsp, 20h
0x1400455ba  mov     rdi, rcx
0x1400455bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400455c4  lea     rax, WPP_GLOBAL_Control
0x1400455cb  cmp     rcx, rax
0x1400455ce  jz      short loc_1400455F1
0x1400455d0  test    byte ptr [rcx+1Ch], 8
0x1400455d4  jz      short loc_1400455F1
0x1400455d6  cmp     byte ptr [rcx+19h], 2
0x1400455da  jb      short loc_1400455F1
0x1400455dc  mov     rcx, [rcx+10h]
0x1400455e0  lea     r8, WPP_741966d44b4333880836975686564805_Traceguids
0x1400455e7  mov     edx, 0Bh
0x1400455ec  call    WPP_SF_
0x1400455f1  cmp     dword ptr [rdi+48h], 0
0x1400455f5  jl      short loc_140045608
0x1400455f7  lea     rcx, [rdi+18h]; lpCriticalSection
0x1400455fb  call    cs:__imp_DeleteCriticalSection
0x140045601  mov     dword ptr [rdi+48h], 80004005h
0x140045608  mov     rcx, rdi
0x14004560b  mov     rbx, [rsp+28h+arg_0]
0x140045610  add     rsp, 20h
0x140045614  pop     rdi
0x140045615  jmp     ??1?$_Tree@V?$_Tset_traits@V?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@UlessLoadedModule@PrnSharedState@@V?$allocator@V?$TRefSmartPtr@VLoadedModule@PrnSharedState@@@PrnExcept@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>,PrnSharedState::lessLoadedModule,std::allocator<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>>,0>>::~_Tree<std::_Tset_traits<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>,PrnSharedState::lessLoadedModule,std::allocator<PrnExcept::TRefSmartPtr<PrnSharedState::LoadedModule>>,0>>(void)
```
