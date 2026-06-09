# RdpTaskScheduler::Fire(ulong)

- ea: `0x140087ba0`
- end: `0x140087cfb`
- name: `?Fire@RdpTaskScheduler@@UEAAXK@Z`
- size: `347`
- prototype: `void(RdpTaskScheduler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1400019e8`
- `0x140087ba0`
- `0x14008836c`
- `0x140112010`

## import_xrefs

- `KERNEL32!IsThreadpoolTimerSet` at `0x140087bde`
- `KERNEL32!IsThreadpoolTimerSet` at `0x140087bde`
- `KERNEL32!SubmitThreadpoolWork` at `0x140087cdf`
- `KERNEL32!SubmitThreadpoolWork` at `0x140087cdf`
- `KERNEL32!GetTickCount64` at `0x140087bc2`
- `KERNEL32!GetTickCount64` at `0x140087bc2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140087bbc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140087bbc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087cf4`

## string_xrefs

- `0x140087c5d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140087c77`: `Fire - m_workThreadPool is null`

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
    else if ( (unsigned int)dword_140150118 > 2 )
    {
      v14 = 780;
      v15 = "Fire";
      v13 = -2147467261;
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v12 = "Fire - m_workThreadPool is null";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)qword_1401413E8,
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
0x140087ba0  push    rbx
0x140087ba2  push    rbp
0x140087ba3  push    rsi
0x140087ba4  push    rdi
0x140087ba5  push    r14
0x140087ba7  push    r15
0x140087ba9  sub     rsp, 68h
0x140087bad  lea     r14, [rcx+0E0h]
0x140087bb4  mov     ebp, edx
0x140087bb6  mov     rbx, rcx
0x140087bb9  mov     rcx, r14; SRWLock
0x140087bbc  call    cs:__imp_AcquireSRWLockExclusive
0x140087bc2  call    cs:__imp_GetTickCount64
0x140087bc8  test    ebp, ebp
0x140087bca  jz      short loc_140087C14
0x140087bcc  mov     rcx, [rbx+90h]; pti
0x140087bd3  lea     r15, [rax+rbp]
0x140087bd7  lea     rdi, [rbx+0A0h]
0x140087bde  call    cs:__imp_IsThreadpoolTimerSet
0x140087be4  test    eax, eax
0x140087be6  jz      short loc_140087BF1
0x140087be8  cmp     r15, [rdi]
0x140087beb  jge     loc_140087CE5
0x140087bf1  mov     rcx, [rbx+28h]
0x140087bf5  mov     [rdi], r15
0x140087bf8  mov     rax, [rcx]
0x140087bfb  mov     rax, [rax+8]
0x140087bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087c04  mov     edx, ebp; unsigned int
0x140087c06  lea     rcx, [rbx-8]; this
0x140087c0a  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x140087c0f  jmp     loc_140087CE5
0x140087c14  xor     edx, edx; unsigned int
0x140087c16  lea     rcx, [rbx-8]; this
0x140087c1a  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x140087c1f  cmp     qword ptr [rbx+88h], 0
0x140087c27  jnz     loc_140087CC8
0x140087c2d  mov     eax, cs:dword_140150118
0x140087c33  cmp     eax, 2
0x140087c36  jbe     loc_140087CE5
0x140087c3c  lea     rax, aFire; "Fire"
0x140087c43  mov     [rsp+98h+arg_8], 30Ch
0x140087c4e  mov     [rsp+98h+arg_10], rax
0x140087c56  lea     rdx, qword_1401413E8
0x140087c5d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140087c64  mov     [rsp+98h+arg_0], 80004003h
0x140087c6f  mov     [rsp+98h+arg_18], rax
0x140087c77  lea     rax, aFireMWorkthrea; "Fire - m_workThreadPool is null"
0x140087c7e  mov     [rsp+98h+var_48], rax
0x140087c83  lea     rax, [rsp+98h+arg_10]
0x140087c8b  mov     [rsp+98h+var_58], rax
0x140087c90  lea     rax, [rsp+98h+arg_8]
0x140087c98  mov     [rsp+98h+var_60], rax
0x140087c9d  lea     rax, [rsp+98h+arg_18]
0x140087ca5  mov     [rsp+98h+var_68], rax
0x140087caa  lea     rax, [rsp+98h+arg_0]
0x140087cb2  mov     [rsp+98h+var_70], rax
0x140087cb7  lea     rax, [rsp+98h+var_48]
0x140087cbc  mov     [rsp+98h+var_78], rax
0x140087cc1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140087cc6  jmp     short loc_140087CE5
0x140087cc8  mov     rcx, [rbx+28h]
0x140087ccc  mov     rax, [rcx]
0x140087ccf  mov     rax, [rax+8]
0x140087cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087cd8  mov     rcx, [rbx+88h]; pwk
0x140087cdf  call    cs:__imp_SubmitThreadpoolWork
0x140087ce5  mov     rcx, r14
0x140087ce8  add     rsp, 68h
0x140087cec  pop     r15
0x140087cee  pop     r14
0x140087cf0  pop     rdi
0x140087cf1  pop     rsi
0x140087cf2  pop     rbp
0x140087cf3  pop     rbx
0x140087cf4  jmp     cs:__imp_ReleaseSRWLockExclusive
```
