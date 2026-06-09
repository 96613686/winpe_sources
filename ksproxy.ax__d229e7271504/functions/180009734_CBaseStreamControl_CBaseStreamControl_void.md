# CBaseStreamControl::~CBaseStreamControl(void)

- ea: `0x180009734`
- end: `0x1800097ac`
- name: `??1CBaseStreamControl@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CBaseStreamControl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009250`

## callees

- `0x180009734`
- `0x180009ce0`
- `0x180045010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800097a0`
- `KERNEL32!LeaveCriticalSection` at `0x18000977e`
- `KERNEL32!LeaveCriticalSection` at `0x18000977e`
- `KERNEL32!EnterCriticalSection` at `0x180009752`
- `KERNEL32!EnterCriticalSection` at `0x180009752`

## pseudocode

```c
void __fastcall CBaseStreamControl::~CBaseStreamControl(CBaseStreamControl *this)
{
  CCritSec *p_m_CritSec; // rdi
  IReferenceClock *m_pRefClock; // rcx

  p_m_CritSec = &this->m_CritSec;
  this->__vftable = (CBaseStreamControl_vtbl *)&CBaseStreamControl::`vftable';
  EnterCriticalSection(&this->m_CritSec.m_CritSec);
  m_pRefClock = this->m_pRefClock;
  if ( m_pRefClock )
    m_pRefClock->Release(m_pRefClock);
  this->m_pRefClock = 0;
  LeaveCriticalSection(&p_m_CritSec->m_CritSec);
  CAMEvent::~CAMEvent(&this->m_StreamEvent);
  DeleteCriticalSection(&p_m_CritSec->m_CritSec);
}

```

## disassembly

```asm
0x180009734  mov     [rsp+arg_0], rbx
0x180009739  push    rdi
0x18000973a  sub     rsp, 20h
0x18000973e  lea     rax, ??_7CBaseStreamControl@@6B@; const CBaseStreamControl::`vftable'
0x180009745  mov     rbx, rcx
0x180009748  lea     rdi, [rcx+38h]
0x18000974c  mov     [rcx], rax
0x18000974f  mov     rcx, rdi; lpCriticalSection
0x180009752  call    cs:__imp_EnterCriticalSection
0x180009759  nop     dword ptr [rax+rax+00h]
0x18000975e  mov     rcx, [rbx+68h]
0x180009762  test    rcx, rcx
0x180009765  jz      short loc_180009773
0x180009767  mov     rax, [rcx]
0x18000976a  mov     rax, [rax+10h]
0x18000976e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009773  mov     rcx, rdi; lpCriticalSection
0x180009776  mov     qword ptr [rbx+68h], 0
0x18000977e  call    cs:__imp_LeaveCriticalSection
0x180009785  nop     dword ptr [rax+rax+00h]
0x18000978a  lea     rcx, [rbx+60h]; this
0x18000978e  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x180009793  mov     rcx, rdi
0x180009796  mov     rbx, [rsp+28h+arg_0]
0x18000979b  add     rsp, 20h
0x18000979f  pop     rdi
0x1800097a0  jmp     cs:__imp_DeleteCriticalSection
```
