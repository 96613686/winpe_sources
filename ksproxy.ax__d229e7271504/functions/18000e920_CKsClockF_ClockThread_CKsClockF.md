# CKsClockF::ClockThread(CKsClockF *)

- ea: `0x18000e920`
- end: `0x18000eb97`
- name: `?ClockThread@CKsClockF@@CAJPEAV1@@Z`
- size: `631`
- prototype: `__int64 __fastcall(CKsClockF *Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a694`
- `0x18000e920`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ea7d`
- `KERNEL32!GetLastError` at `0x18000eadd`
- `KERNEL32!GetLastError` at `0x18000eb11`
- `KERNEL32!GetLastError` at `0x18000ea7d`
- `KERNEL32!GetLastError` at `0x18000eadd`
- `KERNEL32!GetLastError` at `0x18000eb11`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000e993`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000e993`
- `KERNEL32!CreateEventW` at `0x18000ea14`
- `KERNEL32!CreateEventW` at `0x18000ea14`
- `KERNEL32!CloseHandle` at `0x18000eaa1`
- `KERNEL32!CloseHandle` at `0x18000eaa1`
- `KERNEL32!GetOverlappedResult` at `0x18000eb01`
- `KERNEL32!GetOverlappedResult` at `0x18000eb01`
- `KERNEL32!DeviceIoControl` at `0x18000ea6d`
- `KERNEL32!DeviceIoControl` at `0x18000ea6d`

## pseudocode

```c
__int64 __fastcall CKsClockF::ClockThread(CKsClockF *Parameter)
{
  _FilterState m_State; // ecx
  __int64 v3; // rdx
  char *m_ClockHandle; // rdi
  signed int LastError; // eax
  __int64 m_StartTime; // rax
  GUID InBuffer; // [rsp+40h] [rbp-58h] BYREF
  int v9; // [rsp+50h] [rbp-48h]
  int v10; // [rsp+54h] [rbp-44h]
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+8h] BYREF
  __int64 OutBuffer; // [rsp+A8h] [rbp+10h] BYREF

  v10 = 2;
  v9 = 0;
  m_State = Parameter->m_State;
  for ( InBuffer = GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000; m_State; m_State = Parameter->m_State )
  {
    OutBuffer = 0;
    if ( Parameter->m_PendingRun )
    {
      Parameter->m_RefClock->GetTime(Parameter->m_RefClock, &OutBuffer);
      m_StartTime = Parameter->m_StartTime;
      if ( OutBuffer <= m_StartTime )
        LODWORD(v3) = 0;
      else
        v3 = (OutBuffer - m_StartTime) / 10000;
    }
    else
    {
      LODWORD(v3) = 1000;
      if ( m_State != State_Running )
        LODWORD(v3) = -1;
    }
    WaitForSingleObjectEx(Parameter->m_ThreadEvent, v3, 0);
    if ( Parameter->m_State == State_Running )
    {
      BytesReturned = 0;
      if ( _InterlockedCompareExchange(&Parameter->m_PendingRun, 0, 1) )
      {
        CKsClockF::SetState(Parameter, KSSTATE_RUN);
        if ( Parameter->m_State != State_Running )
          CKsClockF::SetState(Parameter, KSSTATE_PAUSE);
      }
      Parameter->m_RefClock->GetTime(Parameter->m_RefClock, &OutBuffer);
      OutBuffer -= Parameter->m_StartTime;
      m_ClockHandle = (char *)Parameter->m_ClockHandle;
      if ( (unsigned __int64)(m_ClockHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        memset(&Overlapped, 0, sizeof(Overlapped));
        Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
        if ( Overlapped.hEvent )
        {
          if ( !DeviceIoControl(m_ClockHandle, 0x2F0003u, &InBuffer, 0x18u, &OutBuffer, 8u, &BytesReturned, &Overlapped) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            if ( LastError == -2147023899 && !GetOverlappedResult(m_ClockHandle, &Overlapped, &BytesReturned, 1) )
              GetLastError();
          }
          CloseHandle(Overlapped.hEvent);
        }
        else
        {
          GetLastError();
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e920  mov     rax, rsp
0x18000e923  push    rbx
0x18000e924  push    rsi
0x18000e925  sub     rsp, 88h
0x18000e92c  movups  xmm0, xmmword ptr cs:_GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000.Data1
0x18000e933  xor     esi, esi
0x18000e935  mov     dword ptr [rax-44h], 2
0x18000e93c  mov     rbx, rcx
0x18000e93f  mov     [rax-48h], esi
0x18000e942  mov     ecx, [rcx+48h]
0x18000e945  movups  xmmword ptr [rax-58h], xmm0
0x18000e949  test    ecx, ecx
0x18000e94b  jz      loc_18000EAD0
0x18000e951  mov     [rax+18h], rbp
0x18000e955  mov     ebp, 0FFFFFFFFh
0x18000e95a  mov     [rax-18h], r14
0x18000e95e  mov     r14, 346DC5D63886594Bh
0x18000e968  mov     [rax+20h], rdi
0x18000e96c  nop     dword ptr [rax+00h]
0x18000e970  mov     [rsp+98h+OutBuffer], rsi
0x18000e978  cmp     [rbx+58h], esi
0x18000e97b  jnz     loc_18000EB22
0x18000e981  cmp     ecx, 2
0x18000e984  mov     edx, 3E8h
0x18000e989  cmovnz  edx, ebp; dwMilliseconds
0x18000e98c  mov     rcx, [rbx+38h]; hHandle
0x18000e990  xor     r8d, r8d; bAlertable
0x18000e993  call    cs:__imp_WaitForSingleObjectEx
0x18000e99a  nop     dword ptr [rax+rax+00h]
0x18000e99f  cmp     dword ptr [rbx+48h], 2
0x18000e9a3  jnz     loc_18000EAAD
0x18000e9a9  mov     [rsp+98h+BytesReturned], esi
0x18000e9b0  mov     ecx, esi
0x18000e9b2  mov     eax, 1
0x18000e9b7  lock cmpxchg [rbx+58h], ecx
0x18000e9bc  test    eax, eax
0x18000e9be  jnz     loc_18000EB6E
0x18000e9c4  mov     rcx, [rbx+28h]
0x18000e9c8  lea     rdx, [rsp+98h+OutBuffer]
0x18000e9d0  mov     rax, [rcx]
0x18000e9d3  mov     rax, [rax+18h]
0x18000e9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9dc  mov     rax, [rbx+50h]
0x18000e9e0  sub     [rsp+98h+OutBuffer], rax
0x18000e9e8  mov     rdi, [rbx+40h]
0x18000e9ec  lea     rax, [rdi-1]
0x18000e9f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e9f4  ja      loc_18000EAAD
0x18000e9fa  xorps   xmm0, xmm0
0x18000e9fd  xor     r9d, r9d; lpName
0x18000ea00  xor     r8d, r8d; bInitialState
0x18000ea03  mov     edx, 1; bManualReset
0x18000ea08  xor     ecx, ecx; lpEventAttributes
0x18000ea0a  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x18000ea0f  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x18000ea14  call    cs:__imp_CreateEventW
0x18000ea1b  nop     dword ptr [rax+rax+00h]
0x18000ea20  mov     [rsp+98h+Overlapped.hEvent], rax
0x18000ea25  test    rax, rax
0x18000ea28  jz      loc_18000EADD
0x18000ea2e  lea     rax, [rsp+98h+Overlapped]
0x18000ea33  mov     r9d, 18h; nInBufferSize
0x18000ea39  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x18000ea3e  lea     r8, [rsp+98h+InBuffer]; lpInBuffer
0x18000ea43  lea     rax, [rsp+98h+BytesReturned]
0x18000ea4b  mov     edx, 2F0003h; dwIoControlCode
0x18000ea50  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x18000ea55  mov     rcx, rdi; hDevice
0x18000ea58  lea     rax, [rsp+98h+OutBuffer]
0x18000ea60  mov     [rsp+98h+nOutBufferSize], 8; nOutBufferSize
0x18000ea68  mov     [rsp+98h+lpOutBuffer], rax; lpOutBuffer
0x18000ea6d  call    cs:__imp_DeviceIoControl
0x18000ea74  nop     dword ptr [rax+rax+00h]
0x18000ea79  test    eax, eax
0x18000ea7b  jnz     short loc_18000EA9C
0x18000ea7d  call    cs:__imp_GetLastError
0x18000ea84  nop     dword ptr [rax+rax+00h]
0x18000ea89  test    eax, eax
0x18000ea8b  jle     short loc_18000EA95
0x18000ea8d  movzx   eax, ax
0x18000ea90  or      eax, 80070000h
0x18000ea95  cmp     eax, 800703E5h
0x18000ea9a  jz      short loc_18000EAEB
0x18000ea9c  mov     rcx, [rsp+98h+Overlapped.hEvent]; hObject
0x18000eaa1  call    cs:__imp_CloseHandle
0x18000eaa8  nop     dword ptr [rax+rax+00h]
0x18000eaad  mov     ecx, [rbx+48h]
0x18000eab0  test    ecx, ecx
0x18000eab2  jnz     loc_18000E970
0x18000eab8  mov     r14, [rsp+98h+var_18]
0x18000eac0  mov     rdi, [rsp+98h+arg_18]
0x18000eac8  mov     rbp, [rsp+98h+arg_10]
0x18000ead0  xor     eax, eax
0x18000ead2  add     rsp, 88h
0x18000ead9  pop     rsi
0x18000eada  pop     rbx
0x18000eadb  retn
0x18000eadd  call    cs:__imp_GetLastError
0x18000eae4  nop     dword ptr [rax+rax+00h]
0x18000eae9  jmp     short loc_18000EAAD
0x18000eaeb  mov     r9d, 1; bWait
0x18000eaf1  lea     r8, [rsp+98h+BytesReturned]; lpNumberOfBytesTransferred
0x18000eaf9  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x18000eafe  mov     rcx, rdi; hFile
0x18000eb01  call    cs:__imp_GetOverlappedResult
0x18000eb08  nop     dword ptr [rax+rax+00h]
0x18000eb0d  test    eax, eax
0x18000eb0f  jnz     short loc_18000EA9C
0x18000eb11  call    cs:__imp_GetLastError
0x18000eb18  nop     dword ptr [rax+rax+00h]
0x18000eb1d  jmp     loc_18000EA9C
0x18000eb22  mov     rcx, [rbx+28h]
0x18000eb26  lea     rdx, [rsp+98h+OutBuffer]
0x18000eb2e  mov     rax, [rcx]
0x18000eb31  mov     rax, [rax+18h]
0x18000eb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb3a  mov     rax, [rbx+50h]
0x18000eb3e  mov     rcx, [rsp+98h+OutBuffer]
0x18000eb46  cmp     rcx, rax
0x18000eb49  jle     short loc_18000EB67
0x18000eb4b  sub     rcx, rax
0x18000eb4e  mov     rax, r14
0x18000eb51  imul    rcx
0x18000eb54  sar     rdx, 0Bh
0x18000eb58  mov     rax, rdx
0x18000eb5b  shr     rax, 3Fh
0x18000eb5f  add     rdx, rax
0x18000eb62  jmp     loc_18000E98C
0x18000eb67  mov     edx, esi
0x18000eb69  jmp     loc_18000E98C
0x18000eb6e  mov     edx, 3; enum KSSTATE
0x18000eb73  mov     rcx, rbx; this
0x18000eb76  call    ?SetState@CKsClockF@@AEAAJW4KSSTATE@@@Z; CKsClockF::SetState(KSSTATE)
0x18000eb7b  cmp     dword ptr [rbx+48h], 2
0x18000eb7f  jz      loc_18000E9C4
0x18000eb85  mov     edx, 2; enum KSSTATE
0x18000eb8a  mov     rcx, rbx; this
0x18000eb8d  call    ?SetState@CKsClockF@@AEAAJW4KSSTATE@@@Z; CKsClockF::SetState(KSSTATE)
0x18000eb92  jmp     loc_18000E9C4
```
