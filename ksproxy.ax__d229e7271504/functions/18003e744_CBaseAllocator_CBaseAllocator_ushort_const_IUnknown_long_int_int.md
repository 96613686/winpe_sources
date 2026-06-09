# CBaseAllocator::CBaseAllocator(ushort const *,IUnknown *,long *,int,int)

- ea: `0x18003e744`
- end: `0x18003e7f3`
- name: `??0CBaseAllocator@@QEAA@PEBGPEAUIUnknown@@PEAJHH@Z`
- size: `175`
- prototype: `CBaseAllocator *__fastcall(CBaseAllocator *this, const unsigned __int16 *, struct IUnknown *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800260d0`
- `0x180029d70`

## callees

- `0x18003e744`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18003e76d`
- `KERNEL32!InitializeCriticalSection` at `0x18003e76d`
- `KERNEL32!CreateSemaphoreExW` at `0x18003e7c4`
- `KERNEL32!CreateSemaphoreExW` at `0x18003e7c4`

## pseudocode

```c
CBaseAllocator *__fastcall CBaseAllocator::CBaseAllocator(
        CBaseAllocator *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        int *a4)
{
  HANDLE Semaphore; // rax

  _InterlockedIncrement(&CBaseObject::m_cObjects);
  this->m_pUnknown = (IUnknown *const)this;
  this->m_cRef = 0;
  InitializeCriticalSection(&this->m_CritSec);
  this->m_lFree.m_List = 0;
  this->m_lFree.m_nOnList = 0;
  this->m_hSem = 0;
  *(_QWORD *)&this->m_lWaiting = 0;
  *(_QWORD *)&this->m_lAllocated = 0;
  *(_QWORD *)&this->m_lAlignment = 0;
  *(_QWORD *)&this->m_bChanged = 0;
  this->m_bDecommitInProgress = 0;
  this->m_pNotify = 0;
  this->m_fEnableReleaseCallback = 1;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  this->m_hSem = Semaphore;
  if ( !Semaphore )
    *a4 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x18003e744  mov     [rsp+arg_0], rbx
0x18003e749  mov     [rsp+arg_8], rsi
0x18003e74e  push    rdi
0x18003e74f  sub     rsp, 30h
0x18003e753  mov     rdi, r9
0x18003e756  mov     rbx, rcx
0x18003e759  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18003e760  mov     [rcx+8], rcx
0x18003e764  xor     esi, esi
0x18003e766  mov     [rcx+10h], esi
0x18003e769  add     rcx, 20h ; ' '; lpCriticalSection
0x18003e76d  call    cs:__imp_InitializeCriticalSection
0x18003e774  nop     dword ptr [rax+rax+00h]
0x18003e779  mov     [rbx+48h], rsi
0x18003e77d  xor     r9d, r9d; lpName
0x18003e780  mov     [rbx+50h], esi
0x18003e783  xor     edx, edx; lInitialCount
0x18003e785  xor     ecx, ecx; lpSemaphoreAttributes
0x18003e787  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18003e78f  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18003e795  mov     [rbx+58h], rsi
0x18003e799  mov     [rbx+60h], rsi
0x18003e79d  mov     [rbx+68h], rsi
0x18003e7a1  mov     [rbx+70h], rsi
0x18003e7a5  mov     [rbx+78h], rsi
0x18003e7a9  mov     [rbx+80h], esi
0x18003e7af  mov     [rbx+88h], rsi
0x18003e7b6  mov     dword ptr [rbx+90h], 1
0x18003e7c0  mov     [rsp+38h+dwFlags], esi; dwFlags
0x18003e7c4  call    cs:__imp_CreateSemaphoreExW
0x18003e7cb  nop     dword ptr [rax+rax+00h]
0x18003e7d0  mov     [rbx+58h], rax
0x18003e7d4  test    rax, rax
0x18003e7d7  jnz     short loc_18003E7DF
0x18003e7d9  mov     dword ptr [rdi], 8007000Eh
0x18003e7df  mov     rsi, [rsp+38h+arg_8]
0x18003e7e4  mov     rax, rbx
0x18003e7e7  mov     rbx, [rsp+38h+arg_0]
0x18003e7ec  add     rsp, 30h
0x18003e7f0  pop     rdi
0x18003e7f1  retn
```
