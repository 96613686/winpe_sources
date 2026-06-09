# CBaseAllocator::Decommit(void)

- ea: `0x10033090`
- end: `0x1003311e`
- name: `?Decommit@CBaseAllocator@@UAGJXZ`
- size: `142`
- prototype: `int __stdcall(CBaseAllocator *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10010ba0`
- `0x1002d5d9`
- `0x100333eb`

## callees

- `0x1002d510`
- `0x10032fcf`
- `0x10033090`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100330bf`
- `KERNEL32!LeaveCriticalSection` at `0x100330fb`
- `KERNEL32!LeaveCriticalSection` at `0x100330bf`
- `KERNEL32!LeaveCriticalSection` at `0x100330fb`
- `KERNEL32!EnterCriticalSection` at `0x100330aa`
- `KERNEL32!EnterCriticalSection` at `0x100330aa`

## pseudocode

```c
int __stdcall CBaseAllocator::Decommit(CBaseAllocator *this)
{
  int v1; // edi
  struct _RTL_CRITICAL_SECTION *v2; // esi
  int *p_m_lPrefix; // ecx
  void *LockSemaphore; // eax
  int m_bDecommitInProgress; // eax

  v1 = 0;
  v2 = this != (CBaseAllocator *)12 ? (struct _RTL_CRITICAL_SECTION *)&this->m_pUnknown : 0;
  EnterCriticalSection(v2);
  p_m_lPrefix = &this->m_lPrefix;
  if ( this->m_lAlignment || *p_m_lPrefix )
  {
    LockSemaphore = this->m_CritSec.LockSemaphore;
    this->m_lAlignment = 0;
    if ( (int)LockSemaphore >= (int)this->m_hSem )
    {
      m_bDecommitInProgress = this[-1].m_bDecommitInProgress;
      *p_m_lPrefix = 0;
      (*(void (__thiscall **)(int *))(m_bDecommitInProgress + 16))(&this[-1].m_bDecommitInProgress);
      v1 = 1;
    }
    else
    {
      *p_m_lPrefix = 1;
    }
    CBaseAllocator::NotifySample((CBaseAllocator *)((char *)this - 12));
    LeaveCriticalSection(v2);
    if ( v1 )
      ((void (__thiscall *)(unsigned int (__stdcall *)(struct CBaseAllocator *), CBaseAllocator *))this->NonDelegatingRelease)(
        this->NonDelegatingRelease,
        this);
  }
  else
  {
    LeaveCriticalSection(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x10033090  mov     edi, edi
0x10033092  push    ebp
0x10033093  mov     ebp, esp
0x10033095  push    ebx
0x10033096  mov     ebx, [ebp+this]
0x10033099  push    esi
0x1003309a  push    edi
0x1003309b  xor     edi, edi
0x1003309d  lea     esi, [ebx-0Ch]
0x100330a0  neg     esi
0x100330a2  lea     eax, [ebx+4]
0x100330a5  sbb     esi, esi
0x100330a7  and     esi, eax
0x100330a9  push    esi; lpCriticalSection
0x100330aa  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100330b0  xor     edx, edx
0x100330b2  lea     ecx, [ebx+48h]
0x100330b5  cmp     [ebx+44h], edx
0x100330b8  jnz     short loc_100330C7
0x100330ba  cmp     [ecx], edx
0x100330bc  jnz     short loc_100330C7
0x100330be  push    esi; lpCriticalSection
0x100330bf  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100330c5  jmp     short loc_10033115
0x100330c7  mov     eax, [ebx+20h]
0x100330ca  mov     [ebx+44h], edx
0x100330cd  cmp     eax, [ebx+30h]
0x100330d0  jge     short loc_100330DA
0x100330d2  mov     dword ptr [ecx], 1
0x100330d8  jmp     short loc_100330F2
0x100330da  mov     eax, [ebx-0Ch]
0x100330dd  mov     [ecx], edx
0x100330df  mov     edi, [eax+10h]
0x100330e2  mov     ecx, edi; this
0x100330e4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100330ea  lea     ecx, [ebx-0Ch]
0x100330ed  call    edi
0x100330ef  xor     edi, edi
0x100330f1  inc     edi
0x100330f2  lea     ecx, [ebx-0Ch]; this
0x100330f5  call    ?NotifySample@CBaseAllocator@@QAEXXZ; CBaseAllocator::NotifySample(void)
0x100330fa  push    esi; lpCriticalSection
0x100330fb  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033101  test    edi, edi
0x10033103  jz      short loc_10033115
0x10033105  mov     eax, [ebx]
0x10033107  push    ebx
0x10033108  mov     esi, [eax+8]
0x1003310b  mov     ecx, esi; this
0x1003310d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10033113  call    esi
0x10033115  pop     edi
0x10033116  pop     esi
0x10033117  xor     eax, eax
0x10033119  pop     ebx
0x1003311a  pop     ebp
0x1003311b  retn    4
```
