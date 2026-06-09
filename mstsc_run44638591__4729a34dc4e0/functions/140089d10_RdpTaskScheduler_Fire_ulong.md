# RdpTaskScheduler::Fire(ulong)

- ea: `0x140089d10`
- end: `0x140089e6b`
- name: `?Fire@RdpTaskScheduler@@UEAAXK@Z`
- size: `347`
- prototype: `void(RdpTaskScheduler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1400019e8`
- `0x140089d10`
- `0x14008a4dc`
- `0x140114010`

## import_xrefs

- `KERNEL32!IsThreadpoolTimerSet` at `0x140089d4e`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140089d4e`
- `KERNEL32!SubmitThreadpoolWork` at `0x140089e4f`
- `KERNEL32!SubmitThreadpoolWork` at `0x140089e4f`
- `KERNEL32!GetTickCount64` at `0x140089d32`
- `KERNEL32!GetTickCount64` at `0x140089d32`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089d2c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089d2c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089e64`

## string_xrefs

- `0x140089dcd`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089de7`: `Fire - m_workThreadPool is null`

## pseudocode

```c
void __fastcall RdpTaskScheduler::Fire(RdpTaskScheduler *this, unsigned int a2)
{
  RTL_SRWLOCK *v2; // r14
  __int64 v3; // rbp
  ULONGLONG TickCount64; // rax
  __int64 v6; // r15
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+50h] [rbp-48h] BYREF
  int v13; // [rsp+A0h] [rbp+8h] BYREF
  int v14; // [rsp+A8h] [rbp+10h] BYREF
  const char *v15; // [rsp+B0h] [rbp+18h] BYREF
  const char *v16; // [rsp+B8h] [rbp+20h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 224);
  v3 = a2;
  AcquireSRWLockExclusive((PSRWLOCK)this + 28);
  TickCount64 = GetTickCount64();
  if ( (_DWORD)v3 )
  {
    v6 = TickCount64 + v3;
    v7 = (_QWORD *)((char *)this + 160);
    if ( !IsThreadpoolTimerSet(*((PTP_TIMER *)this + 18)) || v6 < *v7 )
    {
      v8 = *((_QWORD *)this + 5);
      *v7 = v6;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      RdpTaskScheduler::ResetTimer((RdpTaskScheduler *)((char *)this - 8), v3);
    }
  }
  else
  {
    RdpTaskScheduler::ResetTimer((RdpTaskScheduler *)((char *)this - 8), 0);
    if ( *((_QWORD *)this + 17) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
      SubmitThreadpoolWork(*((PTP_WORK *)this + 17));
    }
    else if ( (unsigned int)dword_140152118 > 2 )
    {
      v14 = 780;
      v15 = "Fire";
      v13 = -2147467261;
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v12 = "Fire - m_workThreadPool is null";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)qword_140143520,
        v10,
        v11,
        (__int64)&v12,
        (__int64)&v13,
        (__int64)&v16,
        (__int64)&v14,
        (__int64)&v15);
    }
  }
  ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x140089d10  push    rbx
0x140089d12  push    rbp
0x140089d13  push    rsi
0x140089d14  push    rdi
0x140089d15  push    r14
0x140089d17  push    r15
0x140089d19  sub     rsp, 68h
0x140089d1d  lea     r14, [rcx+0E0h]
0x140089d24  mov     ebp, edx
0x140089d26  mov     rbx, rcx
0x140089d29  mov     rcx, r14; SRWLock
0x140089d2c  call    cs:__imp_AcquireSRWLockExclusive
0x140089d32  call    cs:__imp_GetTickCount64
0x140089d38  test    ebp, ebp
0x140089d3a  jz      short loc_140089D84
0x140089d3c  mov     rcx, [rbx+90h]; pti
0x140089d43  lea     r15, [rax+rbp]
0x140089d47  lea     rdi, [rbx+0A0h]
0x140089d4e  call    cs:__imp_IsThreadpoolTimerSet
0x140089d54  test    eax, eax
0x140089d56  jz      short loc_140089D61
0x140089d58  cmp     r15, [rdi]
0x140089d5b  jge     loc_140089E55
0x140089d61  mov     rcx, [rbx+28h]
0x140089d65  mov     [rdi], r15
0x140089d68  mov     rax, [rcx]
0x140089d6b  mov     rax, [rax+8]
0x140089d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089d74  mov     edx, ebp; unsigned int
0x140089d76  lea     rcx, [rbx-8]; this
0x140089d7a  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x140089d7f  jmp     loc_140089E55
0x140089d84  xor     edx, edx; unsigned int
0x140089d86  lea     rcx, [rbx-8]; this
0x140089d8a  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x140089d8f  cmp     qword ptr [rbx+88h], 0
0x140089d97  jnz     loc_140089E38
0x140089d9d  mov     eax, cs:dword_140152118
0x140089da3  cmp     eax, 2
0x140089da6  jbe     loc_140089E55
0x140089dac  lea     rax, aFire; "Fire"
0x140089db3  mov     [rsp+98h+arg_8], 30Ch
0x140089dbe  mov     [rsp+98h+arg_10], rax
0x140089dc6  lea     rdx, qword_140143520
0x140089dcd  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140089dd4  mov     [rsp+98h+arg_0], 80004003h
0x140089ddf  mov     [rsp+98h+arg_18], rax
0x140089de7  lea     rax, aFireMWorkthrea; "Fire - m_workThreadPool is null"
0x140089dee  mov     [rsp+98h+var_48], rax
0x140089df3  lea     rax, [rsp+98h+arg_10]
0x140089dfb  mov     [rsp+98h+var_58], rax
0x140089e00  lea     rax, [rsp+98h+arg_8]
0x140089e08  mov     [rsp+98h+var_60], rax
0x140089e0d  lea     rax, [rsp+98h+arg_18]
0x140089e15  mov     [rsp+98h+var_68], rax
0x140089e1a  lea     rax, [rsp+98h+arg_0]
0x140089e22  mov     [rsp+98h+var_70], rax
0x140089e27  lea     rax, [rsp+98h+var_48]
0x140089e2c  mov     [rsp+98h+var_78], rax
0x140089e31  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140089e36  jmp     short loc_140089E55
0x140089e38  mov     rcx, [rbx+28h]
0x140089e3c  mov     rax, [rcx]
0x140089e3f  mov     rax, [rax+8]
0x140089e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089e48  mov     rcx, [rbx+88h]; pwk
0x140089e4f  call    cs:__imp_SubmitThreadpoolWork
0x140089e55  mov     rcx, r14
0x140089e58  add     rsp, 68h
0x140089e5c  pop     r15
0x140089e5e  pop     r14
0x140089e60  pop     rdi
0x140089e61  pop     rsi
0x140089e62  pop     rbp
0x140089e63  pop     rbx
0x140089e64  jmp     cs:__imp_ReleaseSRWLockExclusive
```
