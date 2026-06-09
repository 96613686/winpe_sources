# AlpcConnectionServer::WaitBeforeServerShutdown(void)

- ea: `0x180070964`
- end: `0x180070a43`
- name: `?WaitBeforeServerShutdown@AlpcConnectionServer@@AEAAXXZ`
- size: `223`
- prototype: `void __fastcall(AlpcConnectionServer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180070748`

## callees

- `0x180006ae8`
- `0x18000aa40`
- `0x180070964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800709ba`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180070a02`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800709ba`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180070a02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800709d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800709d0`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180070983`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180070983`

## pseudocode

```c
void __fastcall AlpcConnectionServer::WaitBeforeServerShutdown(AlpcConnectionServer *this)
{
  HANDLE WaitableTimerW; // rax
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  DueTime.QuadPart = 0;
  WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
  *((_QWORD *)this + 1) = WaitableTimerW;
  if ( WaitableTimerW )
  {
    DueTime.QuadPart = -600000000;
    if ( SetWaitableTimer(WaitableTimerW, &DueTime, 0, 0, 0, 0) )
    {
      while ( 1 )
      {
        if ( WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\usagereporting\\alpcconnectionserver.cpp",
            v3);
        if ( !*((_QWORD *)this + 3) )
          break;
        if ( !SetWaitableTimer(*((HANDLE *)this + 1), &DueTime, 0, 0, 0, 0) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x55,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\usagereporting\\alpcconnectionserver.cpp",
            v4);
      }
    }
  }
}

```

## disassembly

```asm
0x180070964  mov     [rsp+arg_8], rbx
0x180070969  push    rdi
0x18007096a  sub     rsp, 30h
0x18007096e  xor     r8d, r8d; lpTimerName
0x180070971  mov     qword ptr [rsp+38h+DueTime], 0
0x18007097a  mov     rbx, rcx
0x18007097d  xor     ecx, ecx; lpTimerAttributes
0x18007097f  lea     edx, [r8+1]; bManualReset
0x180070983  call    cs:__imp_CreateWaitableTimerW
0x180070989  mov     [rbx+8], rax
0x18007098d  test    rax, rax
0x180070990  jz      short loc_180070A0E
0x180070992  mov     [rsp+38h+fResume], 0; fResume
0x18007099a  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x18007099f  xor     r9d, r9d; pfnCompletionRoutine
0x1800709a2  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x1800709ab  xor     r8d, r8d; lPeriod
0x1800709ae  mov     qword ptr [rsp+38h+DueTime], 0FFFFFFFFDC3CBA00h
0x1800709b7  mov     rcx, rax; hTimer
0x1800709ba  call    cs:__imp_SetWaitableTimer
0x1800709c0  test    eax, eax
0x1800709c2  jz      short loc_180070A0E
0x1800709c4  mov     rcx, [rbx+8]; hHandle
0x1800709c8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800709cb  mov     rdi, [rsp+38h]
0x1800709d0  call    cs:__imp_WaitForSingleObject
0x1800709d6  test    eax, eax
0x1800709d8  jnz     short loc_180070A19
0x1800709da  cmp     qword ptr [rbx+18h], 0
0x1800709df  jz      short loc_180070A0E
0x1800709e1  mov     rcx, [rbx+8]; hTimer
0x1800709e5  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x1800709ea  mov     rdi, [rsp+38h]
0x1800709ef  xor     r9d, r9d; pfnCompletionRoutine
0x1800709f2  mov     [rsp+38h+fResume], eax; fResume
0x1800709f6  xor     r8d, r8d; lPeriod
0x1800709f9  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x180070a02  call    cs:__imp_SetWaitableTimer
0x180070a08  test    eax, eax
0x180070a0a  jz      short loc_180070A2E
0x180070a0c  jmp     short loc_1800709C4
0x180070a0e  mov     rbx, [rsp+38h+arg_8]
0x180070a13  add     rsp, 30h
0x180070a17  pop     rdi
0x180070a18  retn
0x180070a19  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\featuremanage"...
0x180070a20  mov     edx, 4Fh ; 'O'; void *
0x180070a25  mov     rcx, rdi; this
0x180070a28  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180070a2e  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\featuremanage"...
0x180070a35  mov     edx, 55h ; 'U'; void *
0x180070a3a  mov     rcx, rdi; this
0x180070a3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
