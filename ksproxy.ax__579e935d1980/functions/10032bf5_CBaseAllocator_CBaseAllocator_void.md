# CBaseAllocator::~CBaseAllocator(void)

- ea: `0x10032bf5`
- end: `0x10032c35`
- name: `??1CBaseAllocator@@UAE@XZ`
- size: `64`
- prototype: `void __thiscall(CBaseAllocator *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1002d5d9`
- `0x100333eb`

## callees

- `0x1002d510`
- `0x10032bf5`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x10032c03`
- `KERNEL32!CloseHandle` at `0x10032c03`
- `KERNEL32!DeleteCriticalSection` at `0x10032c26`
- `KERNEL32!DeleteCriticalSection` at `0x10032c26`

## pseudocode

```c
void __thiscall CBaseAllocator::~CBaseAllocator(CBaseAllocator *this)
{
  IMemAllocatorNotifyCallbackTemp *m_pNotify; // ecx

  if ( this->m_hSem )
    CloseHandle(this->m_hSem);
  m_pNotify = this->m_pNotify;
  if ( m_pNotify )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMemAllocatorNotifyCallbackTemp *))m_pNotify->Release)(
      m_pNotify->Release,
      m_pNotify);
  DeleteCriticalSection(&this->m_CritSec);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x10032bf5  mov     edi, edi
0x10032bf7  push    edi
0x10032bf8  mov     edi, ecx
0x10032bfa  cmp     dword ptr [edi+30h], 0
0x10032bfe  jz      short loc_10032C09
0x10032c00  push    dword ptr [edi+30h]; hObject
0x10032c03  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10032c09  mov     ecx, [edi+58h]
0x10032c0c  test    ecx, ecx
0x10032c0e  jz      short loc_10032C22
0x10032c10  mov     eax, [ecx]
0x10032c12  push    esi
0x10032c13  push    ecx
0x10032c14  mov     esi, [eax+8]
0x10032c17  mov     ecx, esi; this
0x10032c19  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10032c1f  call    esi
0x10032c21  pop     esi
0x10032c22  lea     eax, [edi+10h]
0x10032c25  push    eax; lpCriticalSection
0x10032c26  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10032c2c  lock dec ?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x10032c33  pop     edi
0x10032c34  retn
```
