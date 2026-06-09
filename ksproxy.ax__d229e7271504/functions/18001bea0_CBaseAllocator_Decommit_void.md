# CBaseAllocator::Decommit(void)

- ea: `0x18001bea0`
- end: `0x18001bf58`
- name: `?Decommit@CBaseAllocator@@UEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017e5c`
- `0x180026240`
- `0x18003bb98`

## callees

- `0x18000edf0`
- `0x18001bea0`
- `0x180045010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001bee1`
- `KERNEL32!LeaveCriticalSection` at `0x18001bf2d`
- `KERNEL32!LeaveCriticalSection` at `0x18001bee1`
- `KERNEL32!LeaveCriticalSection` at `0x18001bf2d`
- `KERNEL32!EnterCriticalSection` at `0x18001bec3`
- `KERNEL32!EnterCriticalSection` at `0x18001bec3`

## pseudocode

```c
__int64 __fastcall CBaseAllocator::Decommit(CBaseAllocator *this)
{
  CBaseAllocator *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  int *p_m_lAllocated; // rdx
  int m_nOnList; // eax
  int v6; // ebp
  CBaseAllocator_vtbl *v7; // rax

  v1 = (CBaseAllocator *)((char *)this - 24);
  v3 = (struct _RTL_CRITICAL_SECTION *)((unsigned __int64)&this->m_pUnknown & -(__int64)(this != (CBaseAllocator *)24));
  EnterCriticalSection(v3);
  p_m_lAllocated = &this->m_lAllocated;
  if ( __PAIR64__(this->m_lAllocated, v1->m_bCommitted) )
  {
    m_nOnList = this->m_lFree.m_nOnList;
    this->m_lCount = 0;
    if ( SLODWORD(this->m_CritSec.LockSemaphore) >= m_nOnList )
    {
      v7 = v1->CUnknown::INonDelegatingUnknown::__vftable;
      *p_m_lAllocated = 0;
      v7->Free(v1);
      v6 = 1;
    }
    else
    {
      v6 = 0;
      *p_m_lAllocated = 1;
    }
    CBaseAllocator::NotifySample(v1);
    LeaveCriticalSection(v3);
    if ( v6 )
      this->NonDelegatingRelease(this);
  }
  else
  {
    LeaveCriticalSection(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bea0  push    rbx
0x18001bea2  push    rbp
0x18001bea3  push    rsi
0x18001bea4  push    rdi
0x18001bea5  sub     rsp, 28h
0x18001bea9  lea     rsi, [rcx-18h]
0x18001bead  mov     rbx, rcx
0x18001beb0  lea     rdx, [rcx+8]
0x18001beb4  mov     rax, rsi
0x18001beb7  neg     rax
0x18001beba  sbb     rdi, rdi
0x18001bebd  and     rdi, rdx
0x18001bec0  mov     rcx, rdi; lpCriticalSection
0x18001bec3  call    cs:__imp_EnterCriticalSection
0x18001beca  nop     dword ptr [rax+rax+00h]
0x18001becf  cmp     dword ptr [rsi+7Ch], 0
0x18001bed3  lea     rdx, [rbx+68h]
0x18001bed7  jnz     short loc_18001BEEF
0x18001bed9  cmp     dword ptr [rdx], 0
0x18001bedc  jnz     short loc_18001BEEF
0x18001bede  mov     rcx, rdi; lpCriticalSection
0x18001bee1  call    cs:__imp_LeaveCriticalSection
0x18001bee8  nop     dword ptr [rax+rax+00h]
0x18001beed  jmp     short loc_18001BF4C
0x18001beef  mov     eax, [rbx+50h]
0x18001bef2  mov     dword ptr [rbx+64h], 0
0x18001bef9  cmp     [rbx+38h], eax
0x18001befc  jge     short loc_18001BF08
0x18001befe  xor     ebp, ebp
0x18001bf00  mov     dword ptr [rdx], 1
0x18001bf06  jmp     short loc_18001BF22
0x18001bf08  mov     rax, [rsi]
0x18001bf0b  mov     rcx, rsi
0x18001bf0e  mov     dword ptr [rdx], 0
0x18001bf14  mov     rax, [rax+20h]
0x18001bf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf1d  mov     ebp, 1
0x18001bf22  mov     rcx, rsi; this
0x18001bf25  call    ?NotifySample@CBaseAllocator@@QEAAXXZ; CBaseAllocator::NotifySample(void)
0x18001bf2a  mov     rcx, rdi; lpCriticalSection
0x18001bf2d  call    cs:__imp_LeaveCriticalSection
0x18001bf34  nop     dword ptr [rax+rax+00h]
0x18001bf39  test    ebp, ebp
0x18001bf3b  jz      short loc_18001BF4C
0x18001bf3d  mov     rax, [rbx]
0x18001bf40  mov     rcx, rbx
0x18001bf43  mov     rax, [rax+10h]
0x18001bf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf4c  xor     eax, eax
0x18001bf4e  add     rsp, 28h
0x18001bf52  pop     rdi
0x18001bf53  pop     rsi
0x18001bf54  pop     rbp
0x18001bf55  pop     rbx
0x18001bf56  retn
```
