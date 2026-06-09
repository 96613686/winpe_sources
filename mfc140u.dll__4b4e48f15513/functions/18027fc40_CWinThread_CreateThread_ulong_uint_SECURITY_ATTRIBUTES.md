# CWinThread::CreateThread(ulong,uint,_SECURITY_ATTRIBUTES *)

- ea: `0x18027fc40`
- end: `0x18027fdb5`
- name: `?CreateThread@CWinThread@@QEAAHKIPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `373`
- prototype: `int __fastcall(CWinThread *this, unsigned int dwCreateFlags, unsigned int nStackSize, _SECURITY_ATTRIBUTES *lpSecurityAttrs)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18027f7e0`
- `0x18027f890`

## callees

- `0x180139190`
- `0x180231d70`
- `0x18027fc40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18027fd09`
- `KERNEL32!CloseHandle` at `0x18027fd31`
- `KERNEL32!CloseHandle` at `0x18027fd5d`
- `KERNEL32!CloseHandle` at `0x18027fd7b`
- `KERNEL32!CloseHandle` at `0x18027fd8d`
- `KERNEL32!CloseHandle` at `0x18027fd09`
- `KERNEL32!CloseHandle` at `0x18027fd31`
- `KERNEL32!CloseHandle` at `0x18027fd5d`
- `KERNEL32!CloseHandle` at `0x18027fd7b`
- `KERNEL32!CloseHandle` at `0x18027fd8d`
- `KERNEL32!SuspendThread` at `0x18027fd41`
- `KERNEL32!SuspendThread` at `0x18027fd41`
- `KERNEL32!ResumeThread` at `0x18027fd18`
- `KERNEL32!ResumeThread` at `0x18027fd18`
- `KERNEL32!SetEvent` at `0x18027fd6e`
- `KERNEL32!SetEvent` at `0x18027fd6e`
- `KERNEL32!CreateEventW` at `0x18027fc9a`
- `KERNEL32!CreateEventW` at `0x18027fcb0`
- `KERNEL32!CreateEventW` at `0x18027fc9a`
- `KERNEL32!CreateEventW` at `0x18027fcb0`
- `KERNEL32!WaitForSingleObject` at `0x18027fd27`
- `KERNEL32!WaitForSingleObject` at `0x18027fd53`
- `KERNEL32!WaitForSingleObject` at `0x18027fd27`
- `KERNEL32!WaitForSingleObject` at `0x18027fd53`
- `VCRUNTIME140!memset` at `0x18027fc7b`
- `VCRUNTIME140!memset` at `0x18027fc7b`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x18027fcf6`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x18027fcf6`

## pseudocode

```c
__int64 __fastcall CWinThread::CreateThread(
        CWinThread *this,
        unsigned int dwCreateFlags,
        unsigned int nStackSize,
        _SECURITY_ATTRIBUTES *lpSecurityAttrs)
{
  HANDLE EventW; // rax
  void *v9; // rax
  void *hEvent2; // rcx
  _AFX_THREAD_STARTUP startup; // [rsp+30h] [rbp-40h] BYREF

  if ( this->m_hThread )
    AfxThrowInvalidArgException();
  memset(&startup, 0, sizeof(startup));
  startup.pThreadState = AfxGetThreadState();
  startup.pThread = this;
  startup.hEvent = CreateEventW(0, 1, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  startup.hEvent2 = EventW;
  startup.dwCreateFlags = dwCreateFlags;
  if ( startup.hEvent )
  {
    if ( EventW )
    {
      v9 = (void *)_beginthreadex(
                     lpSecurityAttrs,
                     nStackSize,
                     _AfxThreadEntry,
                     &startup,
                     dwCreateFlags | 4,
                     &this->m_nThreadID);
      this->m_hThread = v9;
      if ( v9 )
      {
        ResumeThread(v9);
        WaitForSingleObject(startup.hEvent, 0xFFFFFFFF);
        CloseHandle(startup.hEvent);
        if ( (dwCreateFlags & 4) != 0 )
          SuspendThread(this->m_hThread);
        if ( !startup.bError )
        {
          SetEvent(startup.hEvent2);
          return 1;
        }
        WaitForSingleObject(this->m_hThread, 0xFFFFFFFF);
        CloseHandle(this->m_hThread);
        this->m_hThread = 0;
      }
      else
      {
        CloseHandle(startup.hEvent);
      }
      hEvent2 = startup.hEvent2;
      goto LABEL_15;
    }
    CloseHandle(startup.hEvent);
    EventW = startup.hEvent2;
  }
  if ( EventW )
  {
    hEvent2 = EventW;
LABEL_15:
    CloseHandle(hEvent2);
  }
  return 0;
}

```

## disassembly

```asm
0x18027fc40  mov     rax, rsp
0x18027fc43  mov     [rax+8], rbx
0x18027fc47  mov     [rax+10h], rsi
0x18027fc4b  mov     [rax+18h], rdi
0x18027fc4f  mov     [rax+20h], r14
0x18027fc53  push    rbp
0x18027fc54  mov     rbp, rsp
0x18027fc57  sub     rsp, 70h
0x18027fc5b  cmp     qword ptr [this+58h], 0
0x18027fc60  mov     rsi, lpSecurityAttrs
0x18027fc63  mov     r14d, nStackSize
0x18027fc66  mov     edi, dwCreateFlags
0x18027fc68  mov     rbx, this
0x18027fc6b  jnz     loc_18027FDAF
0x18027fc71  xor     dwCreateFlags, dwCreateFlags; Val
0x18027fc73  lea     this, [rbp+startup]; void *
0x18027fc77  lea     nStackSize, [rdx+38h]; Size
0x18027fc7b  call    cs:__imp_memset
0x18027fc81  call    ?AfxGetThreadState@@YAPEAV_AFX_THREAD_STATE@@XZ; AfxGetThreadState(void)
0x18027fc86  xor     r9d, r9d; lpName
0x18027fc89  mov     [rbp+startup.pThreadState], rax
0x18027fc8d  xor     nStackSize, nStackSize; bInitialState
0x18027fc90  mov     [rbp+startup.pThread], rbx
0x18027fc94  xor     ecx, ecx; lpEventAttributes
0x18027fc96  lea     dwCreateFlags, [lpSecurityAttrs+1]; bManualReset
0x18027fc9a  call    cs:__imp_CreateEventW
0x18027fca0  xor     r9d, r9d; lpName
0x18027fca3  xor     nStackSize, nStackSize; bInitialState
0x18027fca6  xor     ecx, ecx; lpEventAttributes
0x18027fca8  mov     [rbp+startup.hEvent], rax
0x18027fcac  lea     dwCreateFlags, [lpSecurityAttrs+1]; bManualReset
0x18027fcb0  call    cs:__imp_CreateEventW
0x18027fcb6  mov     this, [rbp+startup.hEvent]; hObject
0x18027fcba  mov     [rbp+startup.hEvent2], rax
0x18027fcbe  mov     [rbp+startup.dwCreateFlags], edi
0x18027fcc1  test    this, this
0x18027fcc4  jz      loc_18027FD85
0x18027fcca  test    rax, rax
0x18027fccd  jz      loc_18027FD7B
0x18027fcd3  mov     ecx, edi
0x18027fcd5  lea     rax, [rbx+60h]
0x18027fcd9  or      ecx, 4
0x18027fcdc  mov     [rsp+70h+ThrdAddr], rax; ThrdAddr
0x18027fce1  mov     [rsp+70h+InitFlag], ecx; InitFlag
0x18027fce5  lea     lpSecurityAttrs, [rbp+startup]; ArgList
0x18027fce9  mov     this, rsi; Security
0x18027fcec  lea     r8, ?_AfxThreadEntry@@YAIPEAX@Z; StartAddress
0x18027fcf3  mov     dwCreateFlags, r14d; StackSize
0x18027fcf6  call    cs:__imp__beginthreadex
0x18027fcfc  mov     [rbx+58h], rax
0x18027fd00  test    rax, rax
0x18027fd03  jnz     short loc_18027FD15
0x18027fd05  mov     this, [rbp+startup.hEvent]; hObject
0x18027fd09  call    cs:__imp_CloseHandle
0x18027fd0f  mov     this, [rbp+startup.hEvent2]
0x18027fd13  jmp     short loc_18027FD8D
0x18027fd15  mov     this, rax; hThread
0x18027fd18  call    cs:__imp_ResumeThread
0x18027fd1e  mov     this, [rbp+startup.hEvent]; hHandle
0x18027fd22  or      esi, 0FFFFFFFFh
0x18027fd25  mov     dwCreateFlags, esi; dwMilliseconds
0x18027fd27  call    cs:__imp_WaitForSingleObject
0x18027fd2d  mov     this, [rbp+startup.hEvent]; hObject
0x18027fd31  call    cs:__imp_CloseHandle
0x18027fd37  test    dil, 4
0x18027fd3b  jz      short loc_18027FD47
0x18027fd3d  mov     this, [rbx+58h]; hThread
0x18027fd41  call    cs:__imp_SuspendThread
0x18027fd47  cmp     [rbp+startup.bError], 0
0x18027fd4b  jz      short loc_18027FD6A
0x18027fd4d  mov     this, [rbx+58h]; hHandle
0x18027fd51  mov     dwCreateFlags, esi; dwMilliseconds
0x18027fd53  call    cs:__imp_WaitForSingleObject
0x18027fd59  mov     this, [rbx+58h]; hObject
0x18027fd5d  call    cs:__imp_CloseHandle
0x18027fd63  and     qword ptr [rbx+58h], 0
0x18027fd68  jmp     short loc_18027FD0F
0x18027fd6a  mov     this, [rbp+startup.hEvent2]; hEvent
0x18027fd6e  call    cs:__imp_SetEvent
0x18027fd74  mov     eax, 1
0x18027fd79  jmp     short loc_18027FD95
0x18027fd7b  call    cs:__imp_CloseHandle
0x18027fd81  mov     rax, [rbp+startup.hEvent2]
0x18027fd85  test    rax, rax
0x18027fd88  jz      short loc_18027FD93
0x18027fd8a  mov     this, rax; hObject
0x18027fd8d  call    cs:__imp_CloseHandle
0x18027fd93  xor     eax, eax
0x18027fd95  lea     r11, [rsp+70h+var_s0]
0x18027fd9a  mov     rbx, [r11+10h]
0x18027fd9e  mov     rsi, [r11+18h]
0x18027fda2  mov     rdi, [r11+20h]
0x18027fda6  mov     r14, [r11+28h]
0x18027fdaa  mov     rsp, r11
0x18027fdad  pop     rbp
0x18027fdae  retn
0x18027fdaf  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
