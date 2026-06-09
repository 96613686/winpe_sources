# CBaseAllocator::~CBaseAllocator(void)

- ea: `0x18001cc24`
- end: `0x18001cc78`
- name: `??1CBaseAllocator@@UEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017e5c`
- `0x18003bb98`

## callees

- `0x18001cc24`
- `0x180045010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001cc36`
- `KERNEL32!CloseHandle` at `0x18001cc36`
- `KERNEL32!DeleteCriticalSection` at `0x18001cc5e`
- `KERNEL32!DeleteCriticalSection` at `0x18001cc5e`

## pseudocode

```c
void __fastcall CBaseAllocator::~CBaseAllocator(CBaseAllocator *this)
{
  void *m_hSem; // rcx
  IMemAllocatorNotifyCallbackTemp *m_pNotify; // rcx

  m_hSem = this->m_hSem;
  if ( m_hSem )
    CloseHandle(m_hSem);
  m_pNotify = this->m_pNotify;
  if ( m_pNotify )
    m_pNotify->Release(m_pNotify);
  DeleteCriticalSection(&this->m_CritSec);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x18001cc24  push    rbx
0x18001cc26  sub     rsp, 20h
0x18001cc2a  mov     rbx, rcx
0x18001cc2d  mov     rcx, [rcx+58h]; hObject
0x18001cc31  test    rcx, rcx
0x18001cc34  jz      short loc_18001CC42
0x18001cc36  call    cs:__imp_CloseHandle
0x18001cc3d  nop     dword ptr [rax+rax+00h]
0x18001cc42  mov     rcx, [rbx+88h]
0x18001cc49  test    rcx, rcx
0x18001cc4c  jz      short loc_18001CC5A
0x18001cc4e  mov     rax, [rcx]
0x18001cc51  mov     rax, [rax+10h]
0x18001cc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc5a  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001cc5e  call    cs:__imp_DeleteCriticalSection
0x18001cc65  nop     dword ptr [rax+rax+00h]
0x18001cc6a  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18001cc71  add     rsp, 20h
0x18001cc75  pop     rbx
0x18001cc76  retn
```
