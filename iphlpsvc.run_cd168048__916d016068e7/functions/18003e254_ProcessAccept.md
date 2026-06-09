# ProcessAccept

- ea: `0x18003e254`
- end: `0x18003e4db`
- name: `ProcessAccept`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039b50`
- `0x18003e1e8`

## callees

- `0x18000d7b0`
- `0x180035494`
- `0x1800355c4`
- `0x18003e1e8`
- `0x18003e254`
- `0x18003e4e4`
- `0x18003e530`
- `0x180041aa8`
- `0x18005bcb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e3cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e3cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e3e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e474`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e3e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e37a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e3f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e491`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e37a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e3f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e491`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x18003e2c7`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x18003e2c7`
- `WS2_32!__imp_closesocket` at `0x18003e40d`
- `WS2_32!__imp_closesocket` at `0x18003e41d`
- `WS2_32!__imp_closesocket` at `0x18003e4a9`
- `WS2_32!__imp_closesocket` at `0x18003e40d`
- `WS2_32!__imp_closesocket` at `0x18003e41d`
- `WS2_32!__imp_closesocket` at `0x18003e4a9`
- `WS2_32!__imp_setsockopt` at `0x18003e33f`
- `WS2_32!__imp_setsockopt` at `0x18003e33f`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e350`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e350`

## string_xrefs

- `0x18003e2fb`: `TpclCreateIo failed on socket %Ix with error %u`
- `0x18003e360`: `SO_UPDATE_ACCEPT_CONTEXT failed on socket %Ix with error %u`

## pseudocode

```c
__int64 __fastcall ProcessAccept(unsigned int a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 LastError; // rbx
  __int64 v6; // r8
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  struct sockaddr *v10; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h] BYREF
  int v13; // [rsp+98h] [rbp+38h] BYREF
  int v14; // [rsp+A0h] [rbp+40h] BYREF
  struct sockaddr *v15; // [rsp+A8h] [rbp+48h] BYREF

  v2 = a2 - 144;
  v10 = 0;
  v12 = a2 - 144;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  GetAcceptExSockaddrs((PVOID)(a2 - 144 + 56), 0, 0x2Cu, 0x2Cu, &v10, &v14, &v15, &v13);
  if ( !(unsigned int)TpclCreateIo(v2 + 48, *(_QWORD *)(v2 + 32), TpProcessWorkItem) )
  {
    LastError = GetLastError();
    EventWrite0(0x80000, L"TpclCreateIo failed on socket %Ix with error %u", *(_QWORD *)(v2 + 32), LastError);
LABEL_3:
    v6 = (unsigned int)LastError;
    return ProcessAcceptError(a1, a2, v6);
  }
  if ( setsockopt(*(_QWORD *)(v2 + 32), 0xFFFF, 28683, (const char *)(a2 - 120), 8) == -1 )
  {
    LastError = (unsigned int)WSAGetLastError();
    EventWrite0(
      0x80000,
      L"SO_UPDATE_ACCEPT_CONTEXT failed on socket %Ix with error %u",
      *(_QWORD *)(v2 + 32),
      LastError);
    CloseThreadpoolIo(*(PTP_IO *)(v2 + 48));
    *(_QWORD *)(v2 + 48) = 0;
    goto LABEL_3;
  }
  v11 = NewConnection(*(_QWORD *)(v2 + 32), *(_QWORD *)(v2 + 48), *(unsigned __int16 *)(v2 + 320));
  v8 = (_QWORD *)v11;
  if ( v11 )
  {
    *(_QWORD *)(v2 + 48) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 312));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(a2 - 124), 0, 0) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 456));
      CloseThreadpoolIo(*(PTP_IO *)(v2 + 48));
      *(_QWORD *)(v2 + 48) = 0;
      closesocket(*(_QWORD *)(v2 + 32));
      closesocket(v8[6]);
      DereferenceConnection(&v11, L"NewConnection");
      v6 = 303;
      return ProcessAcceptError(a1, a2, v6);
    }
    _InterlockedIncrement((volatile signed __int32 *)(a2 - 128));
    v8[3] = v2;
    v9 = *(_QWORD **)(v2 + 504);
    if ( *v9 != v2 + 496 )
      __fastfail(3u);
    v8[1] = v9;
    *v8 = v2 + 496;
    *v9 = v8;
    *(_QWORD *)(v2 + 504) = v8;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 456));
    StartConnect(v8, v2);
  }
  else
  {
    CloseThreadpoolIo(*(PTP_IO *)(v2 + 48));
    *(_QWORD *)(v2 + 48) = 0;
    closesocket(*(_QWORD *)(v2 + 32));
  }
  StartAccept(v2);
  return DereferencePort(&v12);
}

```

## disassembly

```asm
0x18003e254  mov     r11, rsp
0x18003e257  mov     [r11+8], rbx
0x18003e25b  push    rbp
0x18003e25c  push    rsi
0x18003e25d  push    rdi
0x18003e25e  push    r14
0x18003e260  push    r15
0x18003e262  mov     rbp, rsp
0x18003e265  sub     rsp, 60h
0x18003e269  lea     rdi, [rdx-90h]
0x18003e270  mov     [rbp+var_20], 0
0x18003e278  lea     rax, [rbp+arg_8]
0x18003e27c  mov     [rbp+var_10], rdi
0x18003e280  mov     [r11-50h], rax
0x18003e284  mov     r8d, 2Ch ; ','; dwLocalAddressLength
0x18003e28a  lea     rax, [rbp+arg_18]
0x18003e28e  mov     [rbp+arg_18], 0
0x18003e296  mov     [r11-58h], rax
0x18003e29a  mov     rsi, rdx
0x18003e29d  lea     rax, [rbp+arg_10]
0x18003e2a1  mov     [rbp+arg_10], 0
0x18003e2a8  mov     [r11-60h], rax
0x18003e2ac  mov     r15d, ecx
0x18003e2af  lea     rax, [rbp+var_20]
0x18003e2b3  mov     [rbp+arg_8], 0
0x18003e2ba  lea     rcx, [rdi+38h]; lpOutputBuffer
0x18003e2be  mov     [r11-68h], rax
0x18003e2c2  mov     r9d, r8d; dwRemoteAddressLength
0x18003e2c5  xor     edx, edx; dwReceiveDataLength
0x18003e2c7  call    cs:__imp_GetAcceptExSockaddrs
0x18003e2ce  nop     dword ptr [rax+rax+00h]
0x18003e2d3  mov     rdx, [rdi+20h]
0x18003e2d7  lea     rcx, [rdi+30h]
0x18003e2db  lea     r8, TpProcessWorkItem
0x18003e2e2  call    TpclCreateIo
0x18003e2e7  test    eax, eax
0x18003e2e9  jnz     short loc_18003E324
0x18003e2eb  call    cs:__imp_GetLastError
0x18003e2f2  nop     dword ptr [rax+rax+00h]
0x18003e2f7  mov     r8, [rdi+20h]
0x18003e2fb  lea     rdx, aTpclcreateioFa_0; "TpclCreateIo failed on socket %Ix with "...
0x18003e302  mov     r9d, eax
0x18003e305  mov     ecx, 80000h
0x18003e30a  mov     ebx, eax
0x18003e30c  call    EventWrite0
0x18003e311  mov     r8d, ebx
0x18003e314  mov     rdx, rsi
0x18003e317  mov     ecx, r15d
0x18003e31a  call    ProcessAcceptError
0x18003e31f  jmp     loc_18003E4C6
0x18003e324  mov     rcx, [rdi+20h]; s
0x18003e328  lea     r9, [rsi-78h]; optval
0x18003e32c  mov     edx, 0FFFFh; level
0x18003e331  mov     [rsp+60h+optlen], 8; optlen
0x18003e339  mov     r8d, 700Bh; optname
0x18003e33f  call    cs:__imp_setsockopt
0x18003e346  nop     dword ptr [rax+rax+00h]
0x18003e34b  cmp     eax, 0FFFFFFFFh
0x18003e34e  jnz     short loc_18003E390
0x18003e350  call    cs:__imp_WSAGetLastError
0x18003e357  nop     dword ptr [rax+rax+00h]
0x18003e35c  mov     r8, [rdi+20h]
0x18003e360  lea     rdx, aSoUpdateAccept; "SO_UPDATE_ACCEPT_CONTEXT failed on sock"...
0x18003e367  mov     r9d, eax
0x18003e36a  mov     ecx, 80000h
0x18003e36f  mov     ebx, eax
0x18003e371  call    EventWrite0
0x18003e376  mov     rcx, [rdi+30h]; pio
0x18003e37a  call    cs:__imp_CloseThreadpoolIo
0x18003e381  nop     dword ptr [rax+rax+00h]
0x18003e386  mov     qword ptr [rdi+30h], 0
0x18003e38e  jmp     short loc_18003E311
0x18003e390  movzx   r8d, word ptr [rdi+140h]
0x18003e398  mov     rdx, [rdi+30h]
0x18003e39c  mov     rcx, [rdi+20h]
0x18003e3a0  call    NewConnection
0x18003e3a5  mov     [rbp+var_18], rax
0x18003e3a9  mov     rbx, rax
0x18003e3ac  test    rax, rax
0x18003e3af  jz      loc_18003E48D
0x18003e3b5  lea     rcx, [rsi+138h]; lpCriticalSection
0x18003e3bc  mov     qword ptr [rdi+30h], 0
0x18003e3c4  lea     r14, [rdi+1C8h]
0x18003e3cb  call    cs:__imp_EnterCriticalSection
0x18003e3d2  nop     dword ptr [rax+rax+00h]
0x18003e3d7  xor     edx, edx
0x18003e3d9  xor     eax, eax
0x18003e3db  lock cmpxchg [rsi-7Ch], edx
0x18003e3e0  jz      short loc_18003E444
0x18003e3e2  mov     rcx, r14; lpCriticalSection
0x18003e3e5  call    cs:__imp_LeaveCriticalSection
0x18003e3ec  nop     dword ptr [rax+rax+00h]
0x18003e3f1  mov     rcx, [rdi+30h]; pio
0x18003e3f5  call    cs:__imp_CloseThreadpoolIo
0x18003e3fc  nop     dword ptr [rax+rax+00h]
0x18003e401  mov     qword ptr [rdi+30h], 0
0x18003e409  mov     rcx, [rdi+20h]; s
0x18003e40d  call    cs:__imp_closesocket
0x18003e414  nop     dword ptr [rax+rax+00h]
0x18003e419  mov     rcx, [rbx+30h]; s
0x18003e41d  call    cs:__imp_closesocket
0x18003e424  nop     dword ptr [rax+rax+00h]
0x18003e429  lea     rdx, aNewconnection; "NewConnection"
0x18003e430  lea     rcx, [rbp+var_18]
0x18003e434  call    DereferenceConnection
0x18003e439  mov     r8d, 12Fh
0x18003e43f  jmp     loc_18003E314
0x18003e444  lock inc dword ptr [rsi-80h]
0x18003e448  lea     rax, [rdi+1F0h]
0x18003e44f  mov     [rbx+18h], rdi
0x18003e453  mov     rcx, [rax+8]
0x18003e457  cmp     [rcx], rax
0x18003e45a  jz      short loc_18003E463
0x18003e45c  mov     ecx, 3
0x18003e461  int     29h; Win8: RtlFailFast(ecx)
0x18003e463  mov     [rbx+8], rcx
0x18003e467  mov     [rbx], rax
0x18003e46a  mov     [rcx], rbx
0x18003e46d  mov     rcx, r14; lpCriticalSection
0x18003e470  mov     [rax+8], rbx
0x18003e474  call    cs:__imp_LeaveCriticalSection
0x18003e47b  nop     dword ptr [rax+rax+00h]
0x18003e480  mov     rdx, rdi
0x18003e483  mov     rcx, rbx
0x18003e486  call    StartConnect
0x18003e48b  jmp     short loc_18003E4B5
0x18003e48d  mov     rcx, [rdi+30h]; pio
0x18003e491  call    cs:__imp_CloseThreadpoolIo
0x18003e498  nop     dword ptr [rax+rax+00h]
0x18003e49d  mov     qword ptr [rdi+30h], 0
0x18003e4a5  mov     rcx, [rdi+20h]; s
0x18003e4a9  call    cs:__imp_closesocket
0x18003e4b0  nop     dword ptr [rax+rax+00h]
0x18003e4b5  mov     rcx, rdi
0x18003e4b8  call    StartAccept
0x18003e4bd  lea     rcx, [rbp+var_10]
0x18003e4c1  call    DereferencePort
0x18003e4c6  mov     rbx, [rsp+60h+arg_0]
0x18003e4ce  add     rsp, 60h
0x18003e4d2  pop     r15
0x18003e4d4  pop     r14
0x18003e4d6  pop     rdi
0x18003e4d7  pop     rsi
0x18003e4d8  pop     rbp
0x18003e4d9  retn
```
