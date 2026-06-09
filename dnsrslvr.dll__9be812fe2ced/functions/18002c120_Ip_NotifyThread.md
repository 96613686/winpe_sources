# Ip_NotifyThread

- ea: `0x18002c120`
- end: `0x18002c6a5`
- name: `Ip_NotifyThread`
- size: `1413`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b130`
- `0x18001da64`
- `0x18002c120`
- `0x18002c6ac`
- `0x18002d5b0`
- `0x18002d9f8`
- `0x180046ec0`
- `0x180086700`
- `0x180086b1c`
- `0x180088578`

## import_xrefs

- `DNSAPI!DnsApiOnNetworkChange` at `0x18002c308`
- `DNSAPI!DnsApiOnNetworkChange` at `0x18002c308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c62f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c63a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c68d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c62f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c63a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c68d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c1cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c1e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c206`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c1cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c1e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c206`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c31f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c57a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c5cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c61d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c31f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c57a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c5cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c61d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002c2a7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002c2a7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002c2d0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002c2d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c539`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c67f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c539`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c67f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c232`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c232`
- `WS2_32!__imp_closesocket` at `0x18002c661`
- `WS2_32!__imp_closesocket` at `0x18002c661`

## pseudocode

```c
__int64 __fastcall Ip_NotifyThread(PVOID Parameter)
{
  int v1; // r13d
  SOCKET v2; // rdi
  void *v3; // r14
  HANDLE v4; // r12
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // edi
  unsigned int v8; // esi
  BOOL v9; // ebx
  DWORD v10; // r9d
  DWORD v11; // eax
  DWORD v12; // edi
  __int64 v13; // rcx
  DWORD v14; // ebx
  bool v15; // zf
  unsigned __int32 v16; // eax
  unsigned __int32 v17; // ett
  HANDLE v18; // rcx
  _DWORD *v20; // rsi
  DWORD LastError; // eax
  __int64 v22; // rdx
  int v23; // eax
  BOOL v24; // [rsp+30h] [rbp-59h]
  unsigned int v25; // [rsp+34h] [rbp-55h] BYREF
  int v26; // [rsp+38h] [rbp-51h]
  void *v27; // [rsp+40h] [rbp-49h] BYREF
  SOCKET s; // [rsp+48h] [rbp-41h] BYREF
  void *v29; // [rsp+50h] [rbp-39h] BYREF
  __int128 Parametera; // [rsp+58h] [rbp-31h] BYREF
  HANDLE hEvent; // [rsp+68h] [rbp-21h]
  _OWORD v32[2]; // [rsp+70h] [rbp-19h] BYREF
  HANDLE Handles[2]; // [rsp+90h] [rbp+7h] BYREF

  v1 = 0;
  v2 = -1;
  v24 = 0;
  v3 = 0;
  s = -1;
  v27 = 0;
  memset(v32, 0, sizeof(v32));
  v29 = 0;
  v4 = 0;
  v25 = 0;
  Parametera = 0;
  hEvent = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 16, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
  ReadRegistrationRetryTimers(&v29, &v25);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 17, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
  v5 = 1;
  if ( v25 )
  {
    v20 = v29;
    do
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_dd(1035, 18, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids, v5, v20[v5]);
      ++v5;
    }
    while ( v5 <= v25 );
  }
  *(_QWORD *)&Parametera = CreateEventW(0, 0, 0, 0);
  if ( !(_QWORD)Parametera )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_38;
    v22 = 19;
    goto LABEL_58;
  }
  *((_QWORD *)&Parametera + 1) = CreateEventW(0, 0, 0, 0);
  if ( !*((_QWORD *)&Parametera + 1) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_38;
    v22 = 20;
    goto LABEL_58;
  }
  hEvent = CreateEventW(0, 0, 0, 0);
  if ( !hEvent )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_38;
    v22 = 21;
    goto LABEL_58;
  }
  v4 = CreateThread(0, 0, ProcessIpChangeNotificationRequestThread, &Parametera, 0, 0);
  if ( !v4 )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_38;
    v22 = 22;
LABEL_58:
    WPP_SF_d(1035, v22, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids, LastError);
    goto LABEL_36;
  }
  v7 = 1;
  v26 = 1;
  v8 = 1;
LABEL_11:
  v9 = v24;
  while ( !v1 )
  {
LABEL_13:
    if ( !v9 )
    {
      v23 = Dns_RegisterIpChangeNotification(v6, &s, &v27, v32);
      v3 = v27;
      v9 = v23 == 0;
      v24 = v9;
    }
    if ( v7 )
    {
      SetEvent((HANDLE)Parametera);
      HandleConfigChange("IP-notification-start", 0, 6);
      v7 = 0;
      v26 = 0;
    }
    if ( v9 )
    {
      Handles[0] = v3;
      Handles[1] = g_hIpNotifyThreadStopEvent;
      if ( v29 )
        v10 = *((_DWORD *)v29 + v8);
      else
        v10 = -1;
      v11 = WaitForMultipleObjectsEx(2u, Handles, 0, v10, 0);
      v12 = v11;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 23, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids, v11);
      if ( v12 )
      {
        v14 = 0;
        if ( v12 == 1 )
          goto LABEL_35;
        v9 = v24;
        v15 = v12 == 258;
        v7 = v26;
        if ( v15 )
        {
          _m_prefetchw(&g_retryRegistrationFlags);
          v16 = g_retryRegistrationFlags;
          do
          {
            v6 = v16;
            v17 = v16;
            v16 = _InterlockedCompareExchange(&g_retryRegistrationFlags, v16, v16);
          }
          while ( v17 != v16 );
          if ( (v16 & 1) != 0 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_d(1035, 25, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids, v8);
            SetEvent(*((HANDLE *)&Parametera + 1));
            if ( v25 < ++v8 )
              v8 = v25;
          }
          else
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_(1035, 26, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
            v8 = v25;
          }
          goto LABEL_11;
        }
      }
      else
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 24, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
        ResetEvent(v3);
        v9 = Dns_RegisterIpChangeNotification(v13, &s, &v27, v32) == 0;
        v24 = v9;
        HandleConfigChange("IP-notification", 0, 5);
        DnsApiOnNetworkChange(8);
        v8 = 1;
        _InterlockedAnd(&g_retryRegistrationFlags, 0xFFFFFFFE);
        SetEvent((HANDLE)Parametera);
        v3 = v27;
        v7 = v26;
      }
    }
    else
    {
      v1 = 1;
    }
  }
  v14 = 0;
  if ( WaitForSingleObject(g_hIpNotifyThreadStopEvent, 0xEA60u) )
  {
    v9 = v24;
    v1 = 0;
    goto LABEL_13;
  }
LABEL_35:
  v1 = v24;
  v2 = s;
LABEL_36:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 27, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
LABEL_38:
  v18 = hEvent;
  if ( hEvent )
  {
    if ( v4 )
    {
      SetEvent(hEvent);
      ThreadShutdownWait(v4);
      v18 = hEvent;
    }
    CloseHandle(v18);
  }
  if ( (_QWORD)Parametera )
    CloseHandle((HANDLE)Parametera);
  if ( *((_QWORD *)&Parametera + 1) )
    CloseHandle(*((HANDLE *)&Parametera + 1));
  if ( v4 )
    CloseHandle(v4);
  if ( v2 == -1 || (closesocket(v2), !v1) )
  {
LABEL_46:
    if ( v3 )
      CloseHandle(v3);
  }
  else if ( v3 )
  {
    WaitForSingleObject(v3, 0xFFFFFFFF);
    goto LABEL_46;
  }
  if ( v29 )
    MIDL_user_free(v29);
  return v14;
}

```

## disassembly

```asm
0x18002c120  push    rbp
0x18002c122  push    rbx
0x18002c123  push    rsi
0x18002c124  push    rdi
0x18002c125  push    r12
0x18002c127  push    r13
0x18002c129  push    r14
0x18002c12b  lea     rbp, [rsp-27h]
0x18002c130  sub     rsp, 0B0h
0x18002c137  mov     rax, cs:__security_cookie
0x18002c13e  xor     rax, rsp
0x18002c141  mov     [rbp+57h+var_40], rax
0x18002c145  xor     r13d, r13d
0x18002c148  xorps   xmm0, xmm0
0x18002c14b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c14f  mov     [rbp+57h+var_B0], r13d
0x18002c153  xor     r14d, r14d
0x18002c156  mov     [rbp+57h+s], rdi
0x18002c15a  xor     eax, eax
0x18002c15c  mov     [rbp+57h+var_A0], r14
0x18002c160  movups  [rbp+57h+var_70], xmm0
0x18002c164  mov     [rbp+57h+var_90], r13
0x18002c168  xor     r12d, r12d
0x18002c16b  movups  [rbp+57h+var_60], xmm0
0x18002c16f  mov     [rbp+57h+var_AC], r13d
0x18002c173  movups  [rbp+57h+Parameter], xmm0
0x18002c177  mov     [rbp+57h+hEvent], rax
0x18002c17b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c182  mov     esi, 40Bh
0x18002c187  jz      short loc_18002C19A
0x18002c189  lea     edx, [rdi+11h]
0x18002c18c  mov     ecx, esi
0x18002c18e  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c195  call    WPP_SF_
0x18002c19a  lea     rdx, [rbp+57h+var_AC]
0x18002c19e  lea     rcx, [rbp+57h+var_90]
0x18002c1a2  call    ReadRegistrationRetryTimers
0x18002c1a7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c1ae  jnz     loc_18002C44D
0x18002c1b4  mov     ebx, 1
0x18002c1b9  cmp     [rbp+57h+var_AC], ebx
0x18002c1bc  jnb     loc_18002C465
0x18002c1c2  xor     r9d, r9d; lpName
0x18002c1c5  xor     r8d, r8d; bInitialState
0x18002c1c8  xor     edx, edx; bManualReset
0x18002c1ca  xor     ecx, ecx; lpEventAttributes
0x18002c1cc  call    cs:__imp_CreateEventW
0x18002c1d2  mov     qword ptr [rbp+57h+Parameter], rax
0x18002c1d6  test    rax, rax
0x18002c1d9  jz      loc_18002C4A5
0x18002c1df  xor     r9d, r9d; lpName
0x18002c1e2  xor     r8d, r8d; bInitialState
0x18002c1e5  xor     edx, edx; bManualReset
0x18002c1e7  xor     ecx, ecx; lpEventAttributes
0x18002c1e9  call    cs:__imp_CreateEventW
0x18002c1ef  mov     qword ptr [rbp+57h+Parameter+8], rax
0x18002c1f3  test    rax, rax
0x18002c1f6  jz      loc_18002C4DC
0x18002c1fc  xor     r9d, r9d; lpName
0x18002c1ff  xor     r8d, r8d; bInitialState
0x18002c202  xor     edx, edx; bManualReset
0x18002c204  xor     ecx, ecx; lpEventAttributes
0x18002c206  call    cs:__imp_CreateEventW
0x18002c20c  mov     [rbp+57h+hEvent], rax
0x18002c210  test    rax, rax
0x18002c213  jz      loc_18002C4F8
0x18002c219  mov     [rsp+0E0h+lpThreadId], r12; lpThreadId
0x18002c21e  lea     r9, [rbp+57h+Parameter]; lpParameter
0x18002c222  lea     r8, ProcessIpChangeNotificationRequestThread; lpStartAddress
0x18002c229  mov     [rsp+0E0h+dwCreationFlags], r12d; dwCreationFlags
0x18002c22e  xor     edx, edx; dwStackSize
0x18002c230  xor     ecx, ecx; lpThreadAttributes
0x18002c232  call    cs:__imp_CreateThread
0x18002c238  mov     r12, rax
0x18002c23b  test    rax, rax
0x18002c23e  jz      loc_18002C514
0x18002c244  mov     edi, 1
0x18002c249  mov     [rbp+57h+var_A8], edi
0x18002c24c  mov     esi, edi
0x18002c24e  mov     ebx, [rbp+57h+var_B0]
0x18002c251  test    r13d, r13d
0x18002c254  jnz     loc_18002C52B
0x18002c25a  test    ebx, ebx
0x18002c25c  jz      loc_18002C552
0x18002c262  test    edi, edi
0x18002c264  jnz     loc_18002C576
0x18002c26a  test    ebx, ebx
0x18002c26c  jz      loc_18002C384
0x18002c272  mov     rcx, [rbp+57h+var_90]
0x18002c276  mov     rax, cs:g_hIpNotifyThreadStopEvent
0x18002c27d  mov     [rbp+57h+Handles], r14
0x18002c281  mov     [rbp+57h+var_48], rax
0x18002c285  test    rcx, rcx
0x18002c288  jz      loc_18002C59C
0x18002c28e  mov     eax, esi
0x18002c290  mov     r9d, [rcx+rax*4]; dwMilliseconds
0x18002c294  xor     r8d, r8d; bWaitAll
0x18002c297  mov     [rsp+0E0h+dwCreationFlags], 0; bAlertable
0x18002c29f  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18002c2a3  lea     ecx, [r8+2]; nCount
0x18002c2a7  call    cs:__imp_WaitForMultipleObjectsEx
0x18002c2ad  mov     edi, eax
0x18002c2af  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c2b6  jnz     loc_18002C38F
0x18002c2bc  test    edi, edi
0x18002c2be  jnz     short loc_18002C331
0x18002c2c0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c2c7  jnz     loc_18002C3AD
0x18002c2cd  mov     rcx, r14; hEvent
0x18002c2d0  call    cs:__imp_ResetEvent
0x18002c2d6  lea     r9, [rbp+57h+var_70]
0x18002c2da  lea     r8, [rbp+57h+var_A0]
0x18002c2de  lea     rdx, [rbp+57h+s]
0x18002c2e2  call    Dns_RegisterIpChangeNotification
0x18002c2e7  xor     ebx, ebx
0x18002c2e9  lea     rcx, aIpNotification_0; "IP-notification"
0x18002c2f0  test    eax, eax
0x18002c2f2  setz    bl
0x18002c2f5  xor     edx, edx
0x18002c2f7  mov     [rbp+57h+var_B0], ebx
0x18002c2fa  lea     r8d, [rdx+5]
0x18002c2fe  call    HandleConfigChange
0x18002c303  mov     ecx, 8
0x18002c308  call    cs:__imp_DnsApiOnNetworkChange
0x18002c30e  mov     esi, 1
0x18002c313  lock and cs:g_retryRegistrationFlags, 0FFFFFFFEh
0x18002c31b  mov     rcx, qword ptr [rbp+57h+Parameter]; hEvent
0x18002c31f  call    cs:__imp_SetEvent
0x18002c325  mov     r14, [rbp+57h+var_A0]
0x18002c329  mov     edi, [rbp+57h+var_A8]
0x18002c32c  jmp     loc_18002C251
0x18002c331  xor     ebx, ebx
0x18002c333  cmp     edi, 1
0x18002c336  jz      loc_18002C3C8
0x18002c33c  mov     ebx, [rbp+57h+var_B0]
0x18002c33f  cmp     edi, 102h
0x18002c345  mov     edi, [rbp+57h+var_A8]
0x18002c348  jnz     loc_18002C251
0x18002c34e  prefetchw byte ptr cs:g_retryRegistrationFlags
0x18002c355  mov     eax, cs:g_retryRegistrationFlags
0x18002c35b  mov     ecx, eax
0x18002c35d  lock cmpxchg cs:g_retryRegistrationFlags, ecx
0x18002c365  jnz     short loc_18002C35B
0x18002c367  test    al, 1
0x18002c369  jnz     loc_18002C5A5
0x18002c36f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c376  jnz     loc_18002C5E2
0x18002c37c  mov     esi, [rbp+57h+var_AC]
0x18002c37f  jmp     loc_18002C24E
0x18002c384  mov     r13d, 1
0x18002c38a  jmp     loc_18002C251
0x18002c38f  mov     edx, 17h
0x18002c394  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c39b  mov     ecx, 40Bh
0x18002c3a0  mov     r9d, edi
0x18002c3a3  call    WPP_SF_d
0x18002c3a8  jmp     loc_18002C2BC
0x18002c3ad  mov     edx, 18h
0x18002c3b2  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c3b9  mov     ecx, 40Bh
0x18002c3be  call    WPP_SF_
0x18002c3c3  jmp     loc_18002C2CD
0x18002c3c8  mov     r13d, [rbp+57h+var_B0]
0x18002c3cc  mov     rdi, [rbp+57h+s]
0x18002c3d0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c3d7  jnz     loc_18002C5FD
0x18002c3dd  mov     rcx, [rbp+57h+hEvent]; hEvent
0x18002c3e1  test    rcx, rcx
0x18002c3e4  jnz     loc_18002C618
0x18002c3ea  mov     rcx, qword ptr [rbp+57h+Parameter]; hObject
0x18002c3ee  test    rcx, rcx
0x18002c3f1  jnz     loc_18002C63A
0x18002c3f7  mov     rcx, qword ptr [rbp+57h+Parameter+8]; hObject
0x18002c3fb  test    rcx, rcx
0x18002c3fe  jnz     loc_18002C645
0x18002c404  test    r12, r12
0x18002c407  jnz     loc_18002C650
0x18002c40d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002c411  jnz     loc_18002C65E
0x18002c417  test    r14, r14
0x18002c41a  jnz     loc_18002C68A
0x18002c420  mov     rax, [rbp+57h+var_90]
0x18002c424  test    rax, rax
0x18002c427  jnz     loc_18002C698
0x18002c42d  mov     eax, ebx
0x18002c42f  mov     rcx, [rbp+57h+var_40]
0x18002c433  xor     rcx, rsp; StackCookie
0x18002c436  call    __security_check_cookie
0x18002c43b  add     rsp, 0B0h
0x18002c442  pop     r14
0x18002c444  pop     r13
0x18002c446  pop     r12
0x18002c448  pop     rdi
0x18002c449  pop     rsi
0x18002c44a  pop     rbx
0x18002c44b  pop     rbp
0x18002c44c  retn
0x18002c44d  mov     edx, 11h
0x18002c452  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c459  mov     ecx, esi
0x18002c45b  call    WPP_SF_
0x18002c460  jmp     loc_18002C1B4
0x18002c465  mov     rsi, [rbp+57h+var_90]
0x18002c469  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c470  jz      short loc_18002C494
0x18002c472  mov     eax, ebx
0x18002c474  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c47b  mov     edx, 12h
0x18002c480  mov     ecx, 40Bh
0x18002c485  mov     r9d, ebx
0x18002c488  mov     eax, [rsi+rax*4]
0x18002c48b  mov     [rsp+0E0h+dwCreationFlags], eax
0x18002c48f  call    WPP_SF_dd
0x18002c494  inc     ebx
0x18002c496  cmp     ebx, [rbp+57h+var_AC]
0x18002c499  jbe     short loc_18002C469
0x18002c49b  mov     esi, 40Bh
0x18002c4a0  jmp     loc_18002C1C2
0x18002c4a5  call    cs:__imp_GetLastError
0x18002c4ab  mov     ebx, eax
0x18002c4ad  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c4b4  jz      loc_18002C3DD
0x18002c4ba  mov     edx, 13h
0x18002c4bf  jmp     short loc_18002C4C6
0x18002c4c1  mov     edx, 16h
0x18002c4c6  mov     ecx, esi
0x18002c4c8  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c4cf  mov     r9d, eax
0x18002c4d2  call    WPP_SF_d
0x18002c4d7  jmp     loc_18002C3D0
0x18002c4dc  call    cs:__imp_GetLastError
0x18002c4e2  mov     ebx, eax
0x18002c4e4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c4eb  jz      loc_18002C3DD
0x18002c4f1  mov     edx, 14h
0x18002c4f6  jmp     short loc_18002C4C6
0x18002c4f8  call    cs:__imp_GetLastError
0x18002c4fe  mov     ebx, eax
0x18002c500  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c507  jz      loc_18002C3DD
0x18002c50d  mov     edx, 15h
0x18002c512  jmp     short loc_18002C4C6
0x18002c514  call    cs:__imp_GetLastError
0x18002c51a  mov     ebx, eax
0x18002c51c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c523  jz      loc_18002C3DD
0x18002c529  jmp     short loc_18002C4C1
0x18002c52b  mov     rcx, cs:g_hIpNotifyThreadStopEvent; hHandle
0x18002c532  mov     edx, 0EA60h; dwMilliseconds
0x18002c537  xor     ebx, ebx
0x18002c539  call    cs:__imp_WaitForSingleObject
0x18002c53f  test    eax, eax
0x18002c541  jz      loc_18002C3C8
0x18002c547  mov     ebx, [rbp+57h+var_B0]
0x18002c54a  xor     r13d, r13d
0x18002c54d  jmp     loc_18002C25A
0x18002c552  lea     r9, [rbp+57h+var_70]
0x18002c556  lea     r8, [rbp+57h+var_A0]
0x18002c55a  lea     rdx, [rbp+57h+s]
0x18002c55e  call    Dns_RegisterIpChangeNotification
0x18002c563  mov     r14, [rbp+57h+var_A0]
0x18002c567  xor     ebx, ebx
0x18002c569  test    eax, eax
0x18002c56b  setz    bl
0x18002c56e  mov     [rbp+57h+var_B0], ebx
0x18002c571  jmp     loc_18002C262
0x18002c576  mov     rcx, qword ptr [rbp+57h+Parameter]; hEvent
0x18002c57a  call    cs:__imp_SetEvent
0x18002c580  xor     edx, edx
0x18002c582  lea     rcx, aIpNotification; "IP-notification-start"
0x18002c589  lea     r8d, [rdx+6]
0x18002c58d  call    HandleConfigChange
0x18002c592  xor     edi, edi
0x18002c594  mov     [rbp+57h+var_A8], edi
0x18002c597  jmp     loc_18002C26A
0x18002c59c  or      r9d, 0FFFFFFFFh
0x18002c5a0  jmp     loc_18002C294
0x18002c5a5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002c5ac  jz      short loc_18002C5C7
0x18002c5ae  mov     edx, 19h
0x18002c5b3  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c5ba  mov     ecx, 40Bh
0x18002c5bf  mov     r9d, esi
0x18002c5c2  call    WPP_SF_d
0x18002c5c7  mov     rcx, qword ptr [rbp+57h+Parameter+8]; hEvent
0x18002c5cb  call    cs:__imp_SetEvent
0x18002c5d1  lea     eax, [rsi+1]
0x18002c5d4  cmp     [rbp+57h+var_AC], eax
0x18002c5d7  mov     esi, eax
0x18002c5d9  cmovb   esi, [rbp+57h+var_AC]
0x18002c5dd  jmp     loc_18002C37F
0x18002c5e2  mov     edx, 1Ah
0x18002c5e7  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c5ee  mov     ecx, 40Bh
0x18002c5f3  call    WPP_SF_
0x18002c5f8  jmp     loc_18002C37C
0x18002c5fd  mov     edx, 1Bh
0x18002c602  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x18002c609  mov     ecx, 40Bh
0x18002c60e  call    WPP_SF_
  ... truncated ...
```
