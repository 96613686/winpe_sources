# CDnsSearcher::Stop(void)

- ea: `0x1800490e4`
- end: `0x1800491bf`
- name: `?Stop@CDnsSearcher@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(CDnsSearcher *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180028e9c`
- `0x18002f928`
- `0x180049c10`

## callees

- `0x180047900`
- `0x1800490e4`
- `0x180049fc8`
- `0x1800a1ea4`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049113`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049126`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800491a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049113`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049126`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800491a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049104`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049184`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049104`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049184`
- `DNSAPI!DnsServiceBrowseCancel` at `0x180049172`
- `DNSAPI!DnsServiceBrowseCancel` at `0x180049172`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDnsSearcher::Stop(RTL_SRWLOCK *this)
{
  CTaskThread *Ptr; // rcx
  RTL_SRWLOCK *v4; // rcx
  const char *v5; // r9
  const char *v6; // rax
  unsigned int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Ptr = (CTaskThread *)this[7].Ptr;
  try
  {
    CTaskThread::Unschedule(Ptr, this);
    AcquireSRWLockExclusive(this + 2);
    v4 = this + 2;
    if ( LODWORD(this[9].Ptr) )
    {
      LODWORD(this[9].Ptr) = 2;
      ReleaseSRWLockExclusive(v4);
      v6 = (const char *)&this[3];
      if ( this[6].Ptr > (PVOID)0xF )
        v6 = *(const char **)v6;
      LogMessage(5u, "CDnsSearcher::Stop", 0x5Cu, "Stopping DNS search: %s", v6);
      v7 = DnsServiceBrowseCancel(&this[1]);
      if ( v7 )
        wil::details::in1diag3::_Throw_Win32(retaddr, v8, v9, (const char *)v7, v10);
      AcquireSRWLockExclusive(this + 2);
      LODWORD(this[9].Ptr) = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
      ReleaseSRWLockExclusive(this + 2);
    }
    else
    {
      ReleaseSRWLockExclusive(v4);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6A,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\DnsSearcher.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x1800490e4  mov     [rsp+arg_8], rbx
0x1800490e9  push    rdi
0x1800490ea  sub     rsp, 40h
0x1800490ee  mov     rbx, rcx
0x1800490f1  mov     rdx, rcx; void *
0x1800490f4  mov     rcx, [rcx+38h]; this
0x1800490f8  call    ?Unschedule@CTaskThread@@QEAAXPEBX@Z; CTaskThread::Unschedule(void const *)
0x1800490fd  lea     rdi, [rbx+10h]
0x180049101  mov     rcx, rdi; SRWLock
0x180049104  call    cs:__imp_AcquireSRWLockExclusive
0x18004910a  mov     rcx, rdi; SRWLock
0x18004910d  cmp     dword ptr [rbx+48h], 0
0x180049111  jnz     short loc_18004911F
0x180049113  call    cs:__imp_ReleaseSRWLockExclusive
0x180049119  nop
0x18004911a  jmp     loc_1800491AA
0x18004911f  mov     dword ptr [rbx+48h], 2
0x180049126  call    cs:__imp_ReleaseSRWLockExclusive
0x18004912c  lea     rax, [rbx+18h]
0x180049130  cmp     qword ptr [rax+18h], 0Fh
0x180049135  jbe     short loc_18004913A
0x180049137  mov     rax, [rax]
0x18004913a  mov     qword ptr [rsp+48h+var_28], rax; unsigned int
0x18004913f  lea     r9, aStoppingDnsSea; "Stopping DNS search: %s"
0x180049146  mov     r8d, 5Ch ; '\'; unsigned int
0x18004914c  lea     rdx, aCdnssearcherSt_0; "CDnsSearcher::Stop"
0x180049153  lea     ecx, [r8-57h]; unsigned __int8
0x180049157  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18004915c  xorps   xmm0, xmm0
0x18004915f  movups  [rsp+48h+var_18], xmm0
0x180049164  mov     qword ptr [rsp+48h+var_18], rbx
0x180049169  mov     byte ptr [rsp+48h+var_18+8], 1
0x18004916e  lea     rcx, [rbx+8]
0x180049172  call    cs:__imp_DnsServiceBrowseCancel
0x180049178  mov     rcx, [rsp+48h]; this
0x18004917d  test    eax, eax
0x18004917f  jnz     short loc_1800491B5
0x180049181  mov     rcx, rdi; SRWLock
0x180049184  call    cs:__imp_AcquireSRWLockExclusive
0x18004918a  mov     dword ptr [rbx+48h], 0
0x180049191  mov     rax, [rbx]
0x180049194  mov     rcx, rbx
0x180049197  mov     rax, [rax+8]
0x18004919b  call    _guard_dispatch_icall
0x1800491a0  mov     rcx, rdi; SRWLock
0x1800491a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800491a9  nop
0x1800491aa  mov     rbx, [rsp+48h+arg_8]
0x1800491af  add     rsp, 40h
0x1800491b3  pop     rdi
0x1800491b4  retn
0x1800491b5  mov     r9d, eax; char *
0x1800491b8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
