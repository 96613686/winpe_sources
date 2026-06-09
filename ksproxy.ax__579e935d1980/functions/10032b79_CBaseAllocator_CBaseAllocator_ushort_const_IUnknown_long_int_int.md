# CBaseAllocator::CBaseAllocator(ushort const *,IUnknown *,long *,int,int)

- ea: `0x10032b79`
- end: `0x10032bef`
- name: `??0CBaseAllocator@@QAE@PBGPAUIUnknown@@PAJHH@Z`
- size: `118`
- prototype: `CBaseAllocator *__thiscall(CBaseAllocator *__hidden this, const unsigned __int16 *, struct IUnknown *, int *, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100196a0`
- `0x1003314a`

## callees

- `0x1002f736`
- `0x10032b79`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x10032b8f`
- `KERNEL32!InitializeCriticalSection` at `0x10032b8f`
- `KERNEL32!CreateSemaphoreExW` at `0x10032bd1`
- `KERNEL32!CreateSemaphoreExW` at `0x10032bd1`

## pseudocode

```c
CBaseAllocator *__thiscall CBaseAllocator::CBaseAllocator(
        CBaseAllocator *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        int *a4,
        int a5,
        int a6)
{
  HANDLE Semaphore; // eax

  CUnknown::CUnknown(this, (const unsigned __int16 *)this, 0);
  InitializeCriticalSection(&this->m_CritSec);
  this->m_lFree.m_List = 0;
  this->m_lFree.m_nOnList = 0;
  this->m_hSem = 0;
  this->m_lWaiting = 0;
  this->m_lCount = 0;
  this->m_lAllocated = 0;
  this->m_lSize = 0;
  this->m_lAlignment = 0;
  this->m_lPrefix = 0;
  this->m_bChanged = 0;
  this->m_bCommitted = 0;
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
0x10032b79  mov     edi, edi
0x10032b7b  push    ebp
0x10032b7c  mov     ebp, esp
0x10032b7e  push    esi
0x10032b7f  push    edi
0x10032b80  xor     edi, edi
0x10032b82  mov     esi, ecx
0x10032b84  push    edi; struct IUnknown *
0x10032b85  push    ecx; unsigned __int16 *
0x10032b86  call    ??0CUnknown@@QAE@PBGPAUIUnknown@@@Z; CUnknown::CUnknown(ushort const *,IUnknown *)
0x10032b8b  lea     eax, [esi+10h]
0x10032b8e  push    eax; lpCriticalSection
0x10032b8f  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10032b95  push    1F0003h; dwDesiredAccess
0x10032b9a  push    edi; dwFlags
0x10032b9b  push    edi; lpName
0x10032b9c  push    7FFFFFFFh; lMaximumCount
0x10032ba1  push    edi; lInitialCount
0x10032ba2  mov     [esi+28h], edi
0x10032ba5  mov     [esi+2Ch], edi
0x10032ba8  push    edi; lpSemaphoreAttributes
0x10032ba9  mov     [esi+30h], edi
0x10032bac  mov     [esi+34h], edi
0x10032baf  mov     [esi+38h], edi
0x10032bb2  mov     [esi+3Ch], edi
0x10032bb5  mov     [esi+40h], edi
0x10032bb8  mov     [esi+44h], edi
0x10032bbb  mov     [esi+48h], edi
0x10032bbe  mov     [esi+4Ch], edi
0x10032bc1  mov     [esi+50h], edi
0x10032bc4  mov     [esi+54h], edi
0x10032bc7  mov     [esi+58h], edi
0x10032bca  mov     dword ptr [esi+5Ch], 1
0x10032bd1  call    ds:__imp__CreateSemaphoreExW@24; CreateSemaphoreExW(x,x,x,x,x,x)
0x10032bd7  mov     [esi+30h], eax
0x10032bda  test    eax, eax
0x10032bdc  jnz     short loc_10032BE7
0x10032bde  mov     eax, [ebp+arg_8]
0x10032be1  mov     dword ptr [eax], 8007000Eh
0x10032be7  pop     edi
0x10032be8  mov     eax, esi
0x10032bea  pop     esi
0x10032beb  pop     ebp
0x10032bec  retn    14h
```
