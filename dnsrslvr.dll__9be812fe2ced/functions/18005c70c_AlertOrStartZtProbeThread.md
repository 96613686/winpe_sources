# AlertOrStartZtProbeThread

- ea: `0x18005c70c`
- end: `0x18005c9aa`
- name: `AlertOrStartZtProbeThread`
- size: `670`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180039350`
- `0x180039560`
- `0x180055780`
- `0x180056b70`
- `0x18005b398`

## callees

- `0x180046ec0`
- `0x18005b368`
- `0x18005bc6c`
- `0x18005c70c`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c82d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c82d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c85e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c87f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c85e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c87f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c7b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c7ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c7b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c7ce`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c908`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c908`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005c818`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005c818`

## pseudocode

```c
__int64 __fastcall AlertOrStartZtProbeThread(DWORD LastError)
{
  HANDLE v2; // rcx
  char v3; // al
  __int64 v4; // rdx
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h]
  DWORD ThreadId; // [rsp+40h] [rbp-18h] BYREF

  v7 = 0;
  v6 = &g_csZtProbeThread;
  ThreadId = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 27, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
  AutoCritSec::Lock((AutoCritSec *)&v6);
  if ( g_hZtProbeThread )
  {
    v3 = BYTE1(xmmword_1800AB5A0);
  }
  else
  {
    if ( !LastError )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 28, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
      goto LABEL_35;
    }
    g_hZtdnsProbeEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_hZtdnsProbeEvent )
      goto LABEL_12;
    g_hZtdnsProbeStopEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_hZtdnsProbeStopEvent )
      goto LABEL_12;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 29, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
    g_hZtProbeThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ZtProbeThread, 0, 0, &ThreadId);
    v2 = g_hZtProbeThread;
    if ( !g_hZtProbeThread )
    {
LABEL_12:
      LastError = GetLastError();
      if ( g_hZtdnsProbeEvent )
      {
        CloseHandle(g_hZtdnsProbeEvent);
        g_hZtdnsProbeEvent = 0;
      }
      if ( g_hZtdnsProbeStopEvent )
      {
        CloseHandle(g_hZtdnsProbeStopEvent);
        g_hZtdnsProbeStopEvent = 0;
      }
      if ( g_hZtProbeThread )
      {
        CloseHandle(g_hZtProbeThread);
        g_hZtProbeThread = 0;
      }
      goto LABEL_35;
    }
    g_fZtProbeThreadRunning = 1;
    v3 = BYTE1(xmmword_1800AB5A0);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_d(1035, 30, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids, ThreadId);
      v3 = BYTE1(xmmword_1800AB5A0);
      v2 = g_hZtProbeThread;
    }
    if ( !v2 )
    {
      LastError = 1359;
      if ( (v3 & 8) == 0 )
        goto LABEL_35;
      v4 = 31;
      goto LABEL_34;
    }
  }
  if ( !g_fZtProbeThreadRunning )
  {
    LastError = 1359;
    if ( (v3 & 8) == 0 )
      goto LABEL_35;
    v4 = 32;
    goto LABEL_34;
  }
  if ( !g_hZtdnsProbeEvent )
  {
    LastError = 1359;
    if ( (v3 & 8) == 0 )
      goto LABEL_35;
    v4 = 33;
    goto LABEL_34;
  }
  if ( g_hZtdnsProbeStopEvent )
  {
    LastError = 0;
    SetEvent(g_hZtdnsProbeEvent);
    goto LABEL_35;
  }
  LastError = 1359;
  if ( (v3 & 8) != 0 )
  {
    v4 = 34;
LABEL_34:
    WPP_SF_d(1035, v4, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids, 1359);
  }
LABEL_35:
  AutoCritSec::Unlock((AutoCritSec *)&v6);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 35, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids, LastError);
  if ( (_DWORD)v7 )
    AutoCritSec::Unlock((AutoCritSec *)&v6);
  return LastError;
}

```

## disassembly

```asm
0x18005c70c  mov     r11, rsp
0x18005c70f  mov     [r11+8], rbx
0x18005c713  mov     [r11+10h], rbp
0x18005c717  push    r14
0x18005c719  sub     rsp, 50h
0x18005c71d  mov     rax, cs:__security_cookie
0x18005c724  xor     rax, rsp
0x18005c727  mov     [rsp+58h+var_10], rax
0x18005c72c  lea     rax, ?g_csZtProbeThread@@3VWxCriticalSection@@A; WxCriticalSection g_csZtProbeThread
0x18005c733  mov     qword ptr [r11-20h], 0
0x18005c73b  mov     [r11-28h], rax
0x18005c73f  mov     ebx, ecx
0x18005c741  mov     [rsp+58h+ThreadId], 0
0x18005c749  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c750  lea     r14, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c757  mov     ebp, 40Bh
0x18005c75c  jz      short loc_18005C76D
0x18005c75e  mov     edx, 1Bh
0x18005c763  mov     ecx, ebp
0x18005c765  mov     r8, r14
0x18005c768  call    WPP_SF_
0x18005c76d  lea     rcx, [rsp+58h+var_28]; this
0x18005c772  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x18005c777  cmp     cs:?g_hZtProbeThread@@3PEAXEA, 0; void * g_hZtProbeThread
0x18005c77f  jnz     loc_18005C8E1
0x18005c785  test    ebx, ebx
0x18005c787  jnz     short loc_18005C7A8
0x18005c789  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c790  jz      loc_18005C954
0x18005c796  lea     edx, [rbx+1Ch]
0x18005c799  mov     ecx, ebp
0x18005c79b  mov     r8, r14
0x18005c79e  call    WPP_SF_
0x18005c7a3  jmp     loc_18005C954
0x18005c7a8  xor     r9d, r9d; lpName
0x18005c7ab  xor     r8d, r8d; bInitialState
0x18005c7ae  xor     edx, edx; bManualReset
0x18005c7b0  xor     ecx, ecx; lpEventAttributes
0x18005c7b2  call    cs:__imp_CreateEventW
0x18005c7b8  mov     cs:?g_hZtdnsProbeEvent@@3PEAXEA, rax; void * g_hZtdnsProbeEvent
0x18005c7bf  test    rax, rax
0x18005c7c2  jz      short loc_18005C82D
0x18005c7c4  xor     r9d, r9d; lpName
0x18005c7c7  xor     r8d, r8d; bInitialState
0x18005c7ca  xor     edx, edx; bManualReset
0x18005c7cc  xor     ecx, ecx; lpEventAttributes
0x18005c7ce  call    cs:__imp_CreateEventW
0x18005c7d4  mov     cs:?g_hZtdnsProbeStopEvent@@3PEAXEA, rax; void * g_hZtdnsProbeStopEvent
0x18005c7db  test    rax, rax
0x18005c7de  jz      short loc_18005C82D
0x18005c7e0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c7e7  jz      short loc_18005C7F8
0x18005c7e9  mov     edx, 1Dh
0x18005c7ee  mov     ecx, ebp
0x18005c7f0  mov     r8, r14
0x18005c7f3  call    WPP_SF_
0x18005c7f8  lea     rax, [rsp+58h+ThreadId]
0x18005c7fd  xor     r9d, r9d; lpParameter
0x18005c800  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18005c805  lea     r8, ?ZtProbeThread@@YAJXZ; lpStartAddress
0x18005c80c  xor     edx, edx; dwStackSize
0x18005c80e  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18005c816  xor     ecx, ecx; lpThreadAttributes
0x18005c818  call    cs:__imp_CreateThread
0x18005c81e  mov     cs:?g_hZtProbeThread@@3PEAXEA, rax; void * g_hZtProbeThread
0x18005c825  mov     rcx, rax
0x18005c828  test    rax, rax
0x18005c82b  jnz     short loc_18005C895
0x18005c82d  call    cs:__imp_GetLastError
0x18005c833  mov     rcx, cs:?g_hZtdnsProbeEvent@@3PEAXEA; hObject
0x18005c83a  mov     ebx, eax
0x18005c83c  test    rcx, rcx
0x18005c83f  jz      short loc_18005C852
0x18005c841  call    cs:__imp_CloseHandle
0x18005c847  mov     cs:?g_hZtdnsProbeEvent@@3PEAXEA, 0; void * g_hZtdnsProbeEvent
0x18005c852  mov     rcx, cs:?g_hZtdnsProbeStopEvent@@3PEAXEA; hObject
0x18005c859  test    rcx, rcx
0x18005c85c  jz      short loc_18005C86F
0x18005c85e  call    cs:__imp_CloseHandle
0x18005c864  mov     cs:?g_hZtdnsProbeStopEvent@@3PEAXEA, 0; void * g_hZtdnsProbeStopEvent
0x18005c86f  mov     rcx, cs:?g_hZtProbeThread@@3PEAXEA; hObject
0x18005c876  test    rcx, rcx
0x18005c879  jz      loc_18005C954
0x18005c87f  call    cs:__imp_CloseHandle
0x18005c885  mov     cs:?g_hZtProbeThread@@3PEAXEA, 0; void * g_hZtProbeThread
0x18005c890  jmp     loc_18005C954
0x18005c895  mov     cs:?g_fZtProbeThreadRunning@@3HA, 1; int g_fZtProbeThreadRunning
0x18005c89f  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18005c8a5  test    al, 8
0x18005c8a7  jz      short loc_18005C8CA
0x18005c8a9  mov     r9d, [rsp+58h+ThreadId]
0x18005c8ae  mov     edx, 1Eh
0x18005c8b3  mov     ecx, ebp
0x18005c8b5  mov     r8, r14
0x18005c8b8  call    WPP_SF_d
0x18005c8bd  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18005c8c3  mov     rcx, cs:?g_hZtProbeThread@@3PEAXEA; void * g_hZtProbeThread
0x18005c8ca  test    rcx, rcx
0x18005c8cd  jnz     short loc_18005C8E7
0x18005c8cf  mov     r9d, 54Fh
0x18005c8d5  mov     ebx, r9d
0x18005c8d8  test    al, 8
0x18005c8da  jz      short loc_18005C954
0x18005c8dc  lea     edx, [rcx+1Fh]
0x18005c8df  jmp     short loc_18005C94A
0x18005c8e1  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18005c8e7  cmp     cs:?g_fZtProbeThreadRunning@@3HA, 0; int g_fZtProbeThreadRunning
0x18005c8ee  jz      short loc_18005C938
0x18005c8f0  mov     rcx, cs:?g_hZtdnsProbeEvent@@3PEAXEA; hEvent
0x18005c8f7  test    rcx, rcx
0x18005c8fa  jz      short loc_18005C924
0x18005c8fc  cmp     cs:?g_hZtdnsProbeStopEvent@@3PEAXEA, 0; void * g_hZtdnsProbeStopEvent
0x18005c904  jz      short loc_18005C910
0x18005c906  xor     ebx, ebx
0x18005c908  call    cs:__imp_SetEvent
0x18005c90e  jmp     short loc_18005C954
0x18005c910  mov     r9d, 54Fh
0x18005c916  mov     ebx, r9d
0x18005c919  test    al, 8
0x18005c91b  jz      short loc_18005C954
0x18005c91d  mov     edx, 22h ; '"'
0x18005c922  jmp     short loc_18005C94A
0x18005c924  mov     r9d, 54Fh
0x18005c92a  mov     ebx, r9d
0x18005c92d  test    al, 8
0x18005c92f  jz      short loc_18005C954
0x18005c931  mov     edx, 21h ; '!'
0x18005c936  jmp     short loc_18005C94A
0x18005c938  mov     r9d, 54Fh
0x18005c93e  mov     ebx, r9d
0x18005c941  test    al, 8
0x18005c943  jz      short loc_18005C954
0x18005c945  mov     edx, 20h ; ' '
0x18005c94a  mov     r8, r14
0x18005c94d  mov     ecx, ebp
0x18005c94f  call    WPP_SF_d
0x18005c954  lea     rcx, [rsp+58h+var_28]; this
0x18005c959  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x18005c95e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c965  jz      short loc_18005C979
0x18005c967  mov     edx, 23h ; '#'
0x18005c96c  mov     ecx, ebp
0x18005c96e  mov     r9d, ebx
0x18005c971  mov     r8, r14
0x18005c974  call    WPP_SF_d
0x18005c979  cmp     dword ptr [rsp+58h+var_20], 0
0x18005c97e  jz      short loc_18005C98A
0x18005c980  lea     rcx, [rsp+58h+var_28]; this
0x18005c985  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x18005c98a  mov     eax, ebx
0x18005c98c  mov     rcx, [rsp+58h+var_10]
0x18005c991  xor     rcx, rsp; StackCookie
0x18005c994  call    __security_check_cookie
0x18005c999  mov     rbx, [rsp+58h+arg_0]
0x18005c99e  mov     rbp, [rsp+58h+arg_8]
0x18005c9a3  add     rsp, 50h
0x18005c9a7  pop     r14
0x18005c9a9  retn
```
