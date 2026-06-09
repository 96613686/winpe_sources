# areg_AlertOrStartRegThread

- ea: `0x180036f4c`
- end: `0x1800370f1`
- name: `areg_AlertOrStartRegThread`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800287f0`
- `0x18002d5b0`
- `0x18004a600`

## callees

- `0x180036f4c`
- `0x180046ec0`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003709d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003709d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036ff4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036ff4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180037069`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180037069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800370b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800370b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036f9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036f9c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003708b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003708b`

## pseudocode

```c
__int64 __fastcall areg_AlertOrStartRegThread(int a1)
{
  __int64 v2; // rdx
  DWORD LastError; // ebx
  __int64 v4; // rdx
  DWORD ThreadId; // [rsp+30h] [rbp-38h] BYREF

  ThreadId = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 10, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  EnterCriticalSection(&g_AregThreadCs);
  if ( g_fAregThreadStop )
  {
    if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
    {
LABEL_7:
      LastError = 1359;
      goto LABEL_23;
    }
    v2 = 11;
LABEL_6:
    WPP_SF_(1055, v2, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    goto LABEL_7;
  }
  LastError = 0;
  if ( g_hAregThread )
  {
    if ( !g_fAregThreadRunning )
    {
      if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
        goto LABEL_7;
      v2 = 13;
      goto LABEL_6;
    }
    g_fAregThreadCheckBeforeExit = 1;
    SetEvent(g_hAregWakeEvent);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v4 = 12;
LABEL_12:
      WPP_SF_(1035, v4, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    }
  }
  else if ( a1 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v4 = 14;
      goto LABEL_12;
    }
  }
  else
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 15, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    g_fAregThreadCheckBeforeExit = 0;
    g_AregThreadWaitCount = 0;
    ResetEvent(g_hAregWakeEvent);
    g_hAregThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)Areg_RegistrationThread, 0, 0, &ThreadId);
    if ( !g_hAregThread )
      LastError = GetLastError();
    g_fAregThreadRunning = 1;
  }
LABEL_23:
  LeaveCriticalSection(&g_AregThreadCs);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 16, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180036f4c  push    rbx
0x180036f4e  push    rbp
0x180036f4f  push    rdi
0x180036f50  push    r15
0x180036f52  sub     rsp, 48h
0x180036f56  mov     rax, cs:__security_cookie
0x180036f5d  xor     rax, rsp
0x180036f60  mov     [rsp+68h+var_30], rax
0x180036f65  mov     edi, ecx
0x180036f67  mov     [rsp+68h+ThreadId], 0
0x180036f6f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180036f76  lea     rbp, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180036f7d  mov     r15d, 40Bh
0x180036f83  jz      short loc_180036F95
0x180036f85  mov     edx, 0Ah
0x180036f8a  mov     ecx, r15d
0x180036f8d  mov     r8, rbp
0x180036f90  call    WPP_SF_
0x180036f95  lea     rcx, g_AregThreadCs; lpCriticalSection
0x180036f9c  call    cs:__imp_EnterCriticalSection
0x180036fa2  cmp     cs:g_fAregThreadStop, 0
0x180036fa9  jz      short loc_180036FD0
0x180036fab  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x180036fb2  jge     short loc_180036FC6
0x180036fb4  mov     edx, 0Bh
0x180036fb9  mov     ecx, 41Fh
0x180036fbe  mov     r8, rbp
0x180036fc1  call    WPP_SF_
0x180036fc6  mov     ebx, 54Fh
0x180036fcb  jmp     loc_1800370AF
0x180036fd0  xor     ebx, ebx
0x180036fd2  cmp     cs:g_hAregThread, rbx
0x180036fd9  jz      short loc_180037029
0x180036fdb  cmp     cs:g_fAregThreadRunning, ebx
0x180036fe1  jz      short loc_18003701A
0x180036fe3  mov     rcx, cs:g_hAregWakeEvent; hEvent
0x180036fea  mov     cs:g_fAregThreadCheckBeforeExit, 1
0x180036ff4  call    cs:__imp_SetEvent
0x180036ffa  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180037001  jz      loc_1800370AF
0x180037007  lea     edx, [rbx+0Ch]
0x18003700a  mov     ecx, r15d
0x18003700d  mov     r8, rbp
0x180037010  call    WPP_SF_
0x180037015  jmp     loc_1800370AF
0x18003701a  cmp     byte ptr cs:xmmword_1800AB5A0+3, bl
0x180037020  jge     short loc_180036FC6
0x180037022  mov     edx, 0Dh
0x180037027  jmp     short loc_180036FB9
0x180037029  test    edi, edi
0x18003702b  jz      short loc_18003703D
0x18003702d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180037034  jz      short loc_1800370AF
0x180037036  mov     edx, 0Eh
0x18003703b  jmp     short loc_18003700A
0x18003703d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180037044  jz      short loc_180037056
0x180037046  mov     edx, 0Fh
0x18003704b  mov     ecx, r15d
0x18003704e  mov     r8, rbp
0x180037051  call    WPP_SF_
0x180037056  mov     rcx, cs:g_hAregWakeEvent; hEvent
0x18003705d  mov     cs:g_fAregThreadCheckBeforeExit, ebx
0x180037063  mov     cs:g_AregThreadWaitCount, ebx
0x180037069  call    cs:__imp_ResetEvent
0x18003706f  lea     rax, [rsp+68h+ThreadId]
0x180037074  xor     r9d, r9d; lpParameter
0x180037077  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18003707c  lea     r8, Areg_RegistrationThread; lpStartAddress
0x180037083  xor     edx, edx; dwStackSize
0x180037085  mov     [rsp+68h+dwCreationFlags], ebx; dwCreationFlags
0x180037089  xor     ecx, ecx; lpThreadAttributes
0x18003708b  call    cs:__imp_CreateThread
0x180037091  mov     cs:g_hAregThread, rax
0x180037098  test    rax, rax
0x18003709b  jnz     short loc_1800370A5
0x18003709d  call    cs:__imp_GetLastError
0x1800370a3  mov     ebx, eax
0x1800370a5  mov     cs:g_fAregThreadRunning, 1
0x1800370af  lea     rcx, g_AregThreadCs; lpCriticalSection
0x1800370b6  call    cs:__imp_LeaveCriticalSection
0x1800370bc  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800370c3  jz      short loc_1800370D8
0x1800370c5  mov     edx, 10h
0x1800370ca  mov     ecx, r15d
0x1800370cd  mov     r9d, ebx
0x1800370d0  mov     r8, rbp
0x1800370d3  call    WPP_SF_d
0x1800370d8  mov     eax, ebx
0x1800370da  mov     rcx, [rsp+68h+var_30]
0x1800370df  xor     rcx, rsp; StackCookie
0x1800370e2  call    __security_check_cookie
0x1800370e7  add     rsp, 48h
0x1800370eb  pop     r15
0x1800370ed  pop     rdi
0x1800370ee  pop     rbp
0x1800370ef  pop     rbx
0x1800370f0  retn
```
