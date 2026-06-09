# ProcessAccept

- ea: `0x18003e210`
- end: `0x18003e497`
- name: `ProcessAccept`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039b60`
- `0x18003e1a4`

## callees

- `0x18000d7c0`
- `0x1800354a4`
- `0x1800355d4`
- `0x18003e1a4`
- `0x18003e210`
- `0x18003e4a0`
- `0x18003e4ec`
- `0x180041a68`
- `0x18005bcd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e387`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e387`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e3a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e3a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e336`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e3b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e44d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e336`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e3b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18003e44d`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x18003e283`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x18003e283`
- `WS2_32!__imp_closesocket` at `0x18003e3c9`
- `WS2_32!__imp_closesocket` at `0x18003e3d9`
- `WS2_32!__imp_closesocket` at `0x18003e465`
- `WS2_32!__imp_closesocket` at `0x18003e3c9`
- `WS2_32!__imp_closesocket` at `0x18003e3d9`
- `WS2_32!__imp_closesocket` at `0x18003e465`
- `WS2_32!__imp_setsockopt` at `0x18003e2fb`
- `WS2_32!__imp_setsockopt` at `0x18003e2fb`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e30c`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e30c`

## string_xrefs

- `0x18003e2b7`: `TpclCreateIo failed on socket %Ix with error %u`
- `0x18003e31c`: `SO_UPDATE_ACCEPT_CONTEXT failed on socket %Ix with error %u`

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
0x18003e210  mov     r11, rsp
0x18003e213  mov     [r11+8], rbx
0x18003e217  push    rbp
0x18003e218  push    rsi
0x18003e219  push    rdi
0x18003e21a  push    r14
0x18003e21c  push    r15
0x18003e21e  mov     rbp, rsp
0x18003e221  sub     rsp, 60h
0x18003e225  lea     rdi, [rdx-90h]
0x18003e22c  mov     [rbp+var_20], 0
0x18003e234  lea     rax, [rbp+arg_8]
0x18003e238  mov     [rbp+var_10], rdi
0x18003e23c  mov     [r11-50h], rax
0x18003e240  mov     r8d, 2Ch ; ','; dwLocalAddressLength
0x18003e246  lea     rax, [rbp+arg_18]
0x18003e24a  mov     [rbp+arg_18], 0
0x18003e252  mov     [r11-58h], rax
0x18003e256  mov     rsi, rdx
0x18003e259  lea     rax, [rbp+arg_10]
0x18003e25d  mov     [rbp+arg_10], 0
0x18003e264  mov     [r11-60h], rax
0x18003e268  mov     r15d, ecx
0x18003e26b  lea     rax, [rbp+var_20]
0x18003e26f  mov     [rbp+arg_8], 0
0x18003e276  lea     rcx, [rdi+38h]; lpOutputBuffer
0x18003e27a  mov     [r11-68h], rax
0x18003e27e  mov     r9d, r8d; dwRemoteAddressLength
0x18003e281  xor     edx, edx; dwReceiveDataLength
0x18003e283  call    cs:__imp_GetAcceptExSockaddrs
0x18003e28a  nop     dword ptr [rax+rax+00h]
0x18003e28f  mov     rdx, [rdi+20h]
0x18003e293  lea     rcx, [rdi+30h]
0x18003e297  lea     r8, TpProcessWorkItem
0x18003e29e  call    TpclCreateIo
0x18003e2a3  test    eax, eax
0x18003e2a5  jnz     short loc_18003E2E0
0x18003e2a7  call    cs:__imp_GetLastError
0x18003e2ae  nop     dword ptr [rax+rax+00h]
0x18003e2b3  mov     r8, [rdi+20h]
0x18003e2b7  lea     rdx, aTpclcreateioFa_0; "TpclCreateIo failed on socket %Ix with "...
0x18003e2be  mov     r9d, eax
0x18003e2c1  mov     ecx, 80000h
0x18003e2c6  mov     ebx, eax
0x18003e2c8  call    EventWrite0
0x18003e2cd  mov     r8d, ebx
0x18003e2d0  mov     rdx, rsi
0x18003e2d3  mov     ecx, r15d
0x18003e2d6  call    ProcessAcceptError
0x18003e2db  jmp     loc_18003E482
0x18003e2e0  mov     rcx, [rdi+20h]; s
0x18003e2e4  lea     r9, [rsi-78h]; optval
0x18003e2e8  mov     edx, 0FFFFh; level
0x18003e2ed  mov     [rsp+60h+optlen], 8; optlen
0x18003e2f5  mov     r8d, 700Bh; optname
0x18003e2fb  call    cs:__imp_setsockopt
0x18003e302  nop     dword ptr [rax+rax+00h]
0x18003e307  cmp     eax, 0FFFFFFFFh
0x18003e30a  jnz     short loc_18003E34C
0x18003e30c  call    cs:__imp_WSAGetLastError
0x18003e313  nop     dword ptr [rax+rax+00h]
0x18003e318  mov     r8, [rdi+20h]
0x18003e31c  lea     rdx, aSoUpdateAccept; "SO_UPDATE_ACCEPT_CONTEXT failed on sock"...
0x18003e323  mov     r9d, eax
0x18003e326  mov     ecx, 80000h
0x18003e32b  mov     ebx, eax
0x18003e32d  call    EventWrite0
0x18003e332  mov     rcx, [rdi+30h]; pio
0x18003e336  call    cs:__imp_CloseThreadpoolIo
0x18003e33d  nop     dword ptr [rax+rax+00h]
0x18003e342  mov     qword ptr [rdi+30h], 0
0x18003e34a  jmp     short loc_18003E2CD
0x18003e34c  movzx   r8d, word ptr [rdi+140h]
0x18003e354  mov     rdx, [rdi+30h]
0x18003e358  mov     rcx, [rdi+20h]
0x18003e35c  call    NewConnection
0x18003e361  mov     [rbp+var_18], rax
0x18003e365  mov     rbx, rax
0x18003e368  test    rax, rax
0x18003e36b  jz      loc_18003E449
0x18003e371  lea     rcx, [rsi+138h]; lpCriticalSection
0x18003e378  mov     qword ptr [rdi+30h], 0
0x18003e380  lea     r14, [rdi+1C8h]
0x18003e387  call    cs:__imp_EnterCriticalSection
0x18003e38e  nop     dword ptr [rax+rax+00h]
0x18003e393  xor     edx, edx
0x18003e395  xor     eax, eax
0x18003e397  lock cmpxchg [rsi-7Ch], edx
0x18003e39c  jz      short loc_18003E400
0x18003e39e  mov     rcx, r14; lpCriticalSection
0x18003e3a1  call    cs:__imp_LeaveCriticalSection
0x18003e3a8  nop     dword ptr [rax+rax+00h]
0x18003e3ad  mov     rcx, [rdi+30h]; pio
0x18003e3b1  call    cs:__imp_CloseThreadpoolIo
0x18003e3b8  nop     dword ptr [rax+rax+00h]
0x18003e3bd  mov     qword ptr [rdi+30h], 0
0x18003e3c5  mov     rcx, [rdi+20h]; s
0x18003e3c9  call    cs:__imp_closesocket
0x18003e3d0  nop     dword ptr [rax+rax+00h]
0x18003e3d5  mov     rcx, [rbx+30h]; s
0x18003e3d9  call    cs:__imp_closesocket
0x18003e3e0  nop     dword ptr [rax+rax+00h]
0x18003e3e5  lea     rdx, aNewconnection; "NewConnection"
0x18003e3ec  lea     rcx, [rbp+var_18]
0x18003e3f0  call    DereferenceConnection
0x18003e3f5  mov     r8d, 12Fh
0x18003e3fb  jmp     loc_18003E2D0
0x18003e400  lock inc dword ptr [rsi-80h]
0x18003e404  lea     rax, [rdi+1F0h]
0x18003e40b  mov     [rbx+18h], rdi
0x18003e40f  mov     rcx, [rax+8]
0x18003e413  cmp     [rcx], rax
0x18003e416  jz      short loc_18003E41F
0x18003e418  mov     ecx, 3
0x18003e41d  int     29h; Win8: RtlFailFast(ecx)
0x18003e41f  mov     [rbx+8], rcx
0x18003e423  mov     [rbx], rax
0x18003e426  mov     [rcx], rbx
0x18003e429  mov     rcx, r14; lpCriticalSection
0x18003e42c  mov     [rax+8], rbx
0x18003e430  call    cs:__imp_LeaveCriticalSection
0x18003e437  nop     dword ptr [rax+rax+00h]
0x18003e43c  mov     rdx, rdi
0x18003e43f  mov     rcx, rbx
0x18003e442  call    StartConnect
0x18003e447  jmp     short loc_18003E471
0x18003e449  mov     rcx, [rdi+30h]; pio
0x18003e44d  call    cs:__imp_CloseThreadpoolIo
0x18003e454  nop     dword ptr [rax+rax+00h]
0x18003e459  mov     qword ptr [rdi+30h], 0
0x18003e461  mov     rcx, [rdi+20h]; s
0x18003e465  call    cs:__imp_closesocket
0x18003e46c  nop     dword ptr [rax+rax+00h]
0x18003e471  mov     rcx, rdi
0x18003e474  call    StartAccept
0x18003e479  lea     rcx, [rbp+var_10]
0x18003e47d  call    DereferencePort
0x18003e482  mov     rbx, [rsp+60h+arg_0]
0x18003e48a  add     rsp, 60h
0x18003e48e  pop     r15
0x18003e490  pop     r14
0x18003e492  pop     rdi
0x18003e493  pop     rsi
0x18003e494  pop     rbp
0x18003e495  retn
```
