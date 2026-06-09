# CRemoteMachineInfoMap::~CRemoteMachineInfoMap(void)

- ea: `0x18001004c`
- end: `0x1800100a2`
- name: `??1CRemoteMachineInfoMap@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180030b80`

## callees

- `0x180012ad0`

## import_xrefs

- `msvcrt!free` at `0x180010076`
- `msvcrt!free` at `0x180010076`
- `KERNEL32!DeleteCriticalSection` at `0x180010090`
- `KERNEL32!DeleteCriticalSection` at `0x180010090`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRemoteMachineInfoMap::~CRemoteMachineInfoMap(LPCRITICAL_SECTION lpCriticalSection)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  std::_Tree<std::_Tmap_traits<wchar_t const *,R<CMachineInfo>,CFunc_wcsicmp,std::allocator<std::pair<wchar_t const * const,R<CMachineInfo>>>,0>>::erase(
    &lpCriticalSection[1].OwningThread,
    &v2,
    *(_QWORD *)lpCriticalSection[1].LockSemaphore,
    lpCriticalSection[1].LockSemaphore);
  free(lpCriticalSection[1].LockSemaphore);
  lpCriticalSection[1].LockSemaphore = 0;
  lpCriticalSection[1].SpinCount = 0;
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001004c  mov     [rsp+arg_8], rbx
0x180010051  push    rdi
0x180010052  sub     rsp, 20h
0x180010056  mov     rdi, rcx
0x180010059  mov     r8, [rcx+40h]
0x18001005d  mov     r9, r8
0x180010060  mov     r8, [r8]
0x180010063  lea     rdx, [rsp+28h+arg_0]
0x180010068  add     rcx, 38h ; '8'
0x18001006c  call    ?erase@?$_Tree@V?$_Tmap_traits@PEB_WV?$R@VCMachineInfo@@@@UCFunc_wcsicmp@@V?$allocator@U?$pair@QEB_WV?$R@VCMachineInfo@@@@@std@@@std@@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tmap_traits<wchar_t const *,R<CMachineInfo>,CFunc_wcsicmp,std::allocator<std::pair<wchar_t const * const,R<CMachineInfo>>>,0>>::erase(std::_Tree<std::_Tmap_traits<wchar_t const *,R<CMachineInfo>,CFunc_wcsicmp,std::allocator<std::pair<wchar_t const * const,R<CMachineInfo>>>,0>>::iterator,std::_Tree<std::_Tmap_traits<wchar_t const *,R<CMachineInfo>,CFunc_wcsicmp,std::allocator<std::pair<wchar_t const * const,R<CMachineInfo>>>,0>>::iterator)
0x180010071  nop
0x180010072  mov     rcx, [rdi+40h]; Block
0x180010076  call    cs:__imp_free
0x18001007c  nop
0x18001007d  mov     qword ptr [rdi+40h], 0
0x180010085  mov     qword ptr [rdi+48h], 0
0x18001008d  mov     rcx, rdi; lpCriticalSection
0x180010090  call    cs:__imp_DeleteCriticalSection
0x180010096  nop
0x180010097  mov     rbx, [rsp+28h+arg_8]
0x18001009c  add     rsp, 20h
0x1800100a0  pop     rdi
0x1800100a1  retn
```
