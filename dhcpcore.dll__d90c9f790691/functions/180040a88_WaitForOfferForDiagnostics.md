# WaitForOfferForDiagnostics

- ea: `0x180040a88`
- end: `0x180040d7b`
- name: `WaitForOfferForDiagnostics`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e890`

## callees

- `0x180009038`
- `0x180010b1c`
- `0x18001cef0`
- `0x180040a88`
- `0x180047dd0`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004dbc4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040b70`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040c81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040b70`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040c81`
- `WS2_32!WSACreateEvent` at `0x180040b1e`
- `WS2_32!WSACreateEvent` at `0x180040b1e`
- `WS2_32!WSAEventSelect` at `0x180040b3e`
- `WS2_32!WSAEventSelect` at `0x180040b3e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x180040bb0`
- `WS2_32!WSAWaitForMultipleEvents` at `0x180040bb0`
- `WS2_32!WSAEnumNetworkEvents` at `0x180040bfd`
- `WS2_32!WSAEnumNetworkEvents` at `0x180040bfd`
- `WS2_32!WSACloseEvent` at `0x180040d49`
- `WS2_32!WSACloseEvent` at `0x180040d49`
- `WS2_32!__imp_recvfrom` at `0x180040c40`
- `WS2_32!__imp_recvfrom` at `0x180040c40`
- `WS2_32!__imp_WSAGetLastError` at `0x180040c4a`
- `WS2_32!__imp_WSAGetLastError` at `0x180040d37`
- `WS2_32!__imp_WSAGetLastError` at `0x180040c4a`
- `WS2_32!__imp_WSAGetLastError` at `0x180040d37`

## pseudocode

```c
__int64 __fastcall WaitForOfferForDiagnostics(__int64 a1, int a2, SOCKET a3, _DWORD *a4)
{
  HANDLE v7; // rax
  __int64 v8; // rax
  ULONGLONG v9; // rdi
  BOOL v10; // r13d
  ULONGLONG TickCount64; // rax
  __int64 v12; // rdx
  ULONGLONG v13; // r15
  unsigned int Error; // ebx
  DWORD v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  ULONGLONG v19; // rax
  int fromlen; // [rsp+30h] [rbp-D0h] BYREF
  ULONGLONG pullResult; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h]
  HANDLE hEvents[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct sockaddr from; // [rsp+58h] [rbp-A8h] BYREF
  struct _WSANETWORKEVENTS NetworkEvents; // [rsp+68h] [rbp-98h] BYREF
  char buf[32]; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+C0h] [rbp-40h]

  *a4 = 0;
  v23 = a2;
  fromlen = 0;
  *(_OWORD *)hEvents = 0;
  from = 0;
  if ( DhcpGlobalPdcCount <= 0 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_dJ(
      1025,
      19,
      WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids,
      (unsigned int)DhcpGlobalPdcCount,
      *(_QWORD *)(a1 + 24));
  v7 = WSACreateEvent();
  hEvents[0] = v7;
  if ( !v7 || WSAEventSelect(a3, v7, 1) )
  {
    Error = WSAGetLastError();
  }
  else
  {
    v8 = *(_QWORD *)(a1 + 832);
    if ( v8 )
      hEvents[1] = *(HANDLE *)(a1 + 832);
    v9 = 10000;
    pullResult = 10000;
    v10 = v8 != 0;
    TickCount64 = GetTickCount64();
    v12 = -1;
    if ( TickCount64 + 10000 >= TickCount64 )
      v12 = TickCount64 + 10000;
    v13 = 0;
    if ( TickCount64 + 10000 >= TickCount64 )
      v13 = v12;
    while ( 1 )
    {
      Error = 0;
      if ( !v9 )
        break;
      v15 = WSAWaitForMultipleEvents(v10 + 1, hEvents, 0, v9, 0);
      Error = v15;
      switch ( v15 )
      {
        case 0xFFFFFFFF:
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_D(1025, 20, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, 0xFFFFFFFFLL);
          goto LABEL_40;
        case 0x102u:
          if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 0x10) != 0 )
            McTemplateU0q_EtwEventWriteTransfer(v16, OfferReceiveTimeout, *(unsigned int *)(a1 + 48));
          *a4 = 0;
          Error = 0;
          goto LABEL_40;
        case 1u:
          Error = 1223;
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_(1025, 21, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids);
          goto LABEL_40;
        case 0u:
          memset(&NetworkEvents, 0, sizeof(NetworkEvents));
          Error = WSAEnumNetworkEvents(a3, hEvents[0], &NetworkEvents);
          if ( Error != -1 )
            Error = NetworkEvents.iErrorCode[0];
          if ( Error )
            goto LABEL_40;
          fromlen = 16;
          if ( recvfrom(a3, buf, 0x2000, 0, &from, &fromlen) == -1 )
          {
            v18 = WSAGetLastError();
            Error = v18;
            if ( v18 != 10054 && v18 != 10035 )
              goto LABEL_40;
          }
          else if ( buf[28] == 2 && v28 == v23 )
          {
            Error = 0;
            if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
              McTemplateU0q_EtwEventWriteTransfer(v17, OfferReceivedForDiagnostics, *(unsigned int *)(a1 + 48));
            *a4 = 1;
            goto LABEL_40;
          }
          break;
      }
      v19 = GetTickCount64();
      if ( ULongLongSub(v13, v19, &pullResult) )
      {
        v9 = 0;
        pullResult = 0;
      }
      else
      {
        v9 = pullResult;
      }
    }
  }
LABEL_40:
  if ( hEvents[0] )
    WSACloseEvent(hEvents[0]);
  return Error;
}

```

## disassembly

```asm
0x180040a88  mov     [rsp-8+arg_8], rbx
0x180040a8d  push    rbp
0x180040a8e  push    rsi
0x180040a8f  push    rdi
0x180040a90  push    r12
0x180040a92  push    r13
0x180040a94  push    r14
0x180040a96  push    r15
0x180040a98  lea     rbp, [rsp-1FB0h]
0x180040aa0  mov     eax, 20B0h
0x180040aa5  call    _alloca_probe
0x180040aaa  sub     rsp, rax
0x180040aad  mov     rax, cs:__security_cookie
0x180040ab4  xor     rax, rsp
0x180040ab7  mov     [rbp+1FE0h+var_40], rax
0x180040abe  mov     r14, r9
0x180040ac1  mov     dword ptr [r9], 0
0x180040ac8  mov     r9d, cs:DhcpGlobalPdcCount
0x180040acf  xorps   xmm0, xmm0
0x180040ad2  mov     [rsp+20E0h+var_20A0], edx
0x180040ad6  xorps   xmm1, xmm1
0x180040ad9  mov     [rsp+20E0h+var_20B0], 0
0x180040ae1  mov     r12, r8
0x180040ae4  mov     rsi, rcx
0x180040ae7  movups  xmmword ptr [rsp+20E0h+hEvents], xmm0
0x180040aec  movups  xmmword ptr [rsp+20E0h+from.sa_family], xmm1
0x180040af1  test    r9d, r9d
0x180040af4  jg      short loc_180040B1E
0x180040af6  test    byte ptr cs:xmmword_1800616A0, 2
0x180040afd  jz      short loc_180040B1E
0x180040aff  mov     rax, [rsi+18h]
0x180040b03  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x180040b0a  mov     edx, 13h
0x180040b0f  mov     qword ptr [rsp+20E0h+fAlertable], rax
0x180040b14  mov     ecx, 401h
0x180040b19  call    WPP_SF_dJ
0x180040b1e  call    cs:__imp_WSACreateEvent
0x180040b24  mov     [rsp+20E0h+hEvents], rax
0x180040b29  test    rax, rax
0x180040b2c  jz      loc_180040D37
0x180040b32  mov     r8d, 1; lNetworkEvents
0x180040b38  mov     rdx, rax; hEventObject
0x180040b3b  mov     rcx, r12; s
0x180040b3e  call    cs:__imp_WSAEventSelect
0x180040b44  test    eax, eax
0x180040b46  jnz     loc_180040D37
0x180040b4c  mov     rax, [rsi+340h]
0x180040b53  test    rax, rax
0x180040b56  jz      short loc_180040B5D
0x180040b58  mov     [rsp+20E0h+hEvents+8], rax
0x180040b5d  neg     rax
0x180040b60  mov     edi, 2710h
0x180040b65  mov     [rsp+20E0h+pullResult], rdi
0x180040b6a  sbb     r13d, r13d
0x180040b6d  neg     r13d
0x180040b70  call    cs:__imp_GetTickCount64
0x180040b76  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180040b7a  lea     rcx, [rax+2710h]
0x180040b81  cmp     rcx, rax
0x180040b84  cmovnb  rdx, rcx
0x180040b88  xor     r15d, r15d
0x180040b8b  cmp     rcx, rax
0x180040b8e  cmovnb  r15, rdx
0x180040b92  xor     ebx, ebx
0x180040b94  test    rdi, rdi
0x180040b97  jz      loc_180040D3F
0x180040b9d  mov     r9d, edi; dwTimeout
0x180040ba0  mov     [rsp+20E0h+fAlertable], ebx; fAlertable
0x180040ba4  xor     r8d, r8d; fWaitAll
0x180040ba7  lea     rdx, [rsp+20E0h+hEvents]; lphEvents
0x180040bac  lea     ecx, [r13+1]; cEvents
0x180040bb0  call    cs:__imp_WSAWaitForMultipleEvents
0x180040bb6  or      edi, 0FFFFFFFFh
0x180040bb9  mov     ebx, eax
0x180040bbb  cmp     eax, edi
0x180040bbd  jz      loc_180040D13
0x180040bc3  cmp     eax, 102h
0x180040bc8  jz      loc_180040CEF
0x180040bce  cmp     eax, 1
0x180040bd1  jz      loc_180040CC9
0x180040bd7  test    eax, eax
0x180040bd9  jnz     loc_180040C81
0x180040bdf  mov     rdx, [rsp+20E0h+hEvents]; hEventObject
0x180040be4  lea     r8, [rsp+20E0h+NetworkEvents]; lpNetworkEvents
0x180040be9  xorps   xmm0, xmm0
0x180040bec  mov     rcx, r12; s
0x180040bef  movups  xmmword ptr [rsp+20E0h+NetworkEvents.iErrorCode+0Ch], xmm0
0x180040bf4  movups  xmmword ptr [rbp+1FE0h+NetworkEvents.iErrorCode+18h], xmm0
0x180040bf8  movups  xmmword ptr [rsp+20E0h+NetworkEvents.lNetworkEvents], xmm0
0x180040bfd  call    cs:__imp_WSAEnumNetworkEvents
0x180040c03  cmp     eax, edi
0x180040c05  mov     ebx, eax
0x180040c07  cmovnz  ebx, [rsp+20E0h+NetworkEvents.iErrorCode]
0x180040c0c  test    ebx, ebx
0x180040c0e  jnz     loc_180040D3F
0x180040c14  lea     rax, [rsp+20E0h+var_20B0]
0x180040c19  mov     [rsp+20E0h+var_20B0], 10h
0x180040c21  mov     [rsp+20E0h+fromlen], rax; fromlen
0x180040c26  lea     rdx, [rbp+1FE0h+buf]; buf
0x180040c2a  lea     rax, [rsp+20E0h+from]
0x180040c2f  xor     r9d, r9d; flags
0x180040c32  mov     r8d, 2000h; len
0x180040c38  mov     qword ptr [rsp+20E0h+fAlertable], rax; from
0x180040c3d  mov     rcx, r12; s
0x180040c40  call    cs:__imp_recvfrom
0x180040c46  cmp     eax, edi
0x180040c48  jnz     short loc_180040C72
0x180040c4a  call    cs:__imp_WSAGetLastError
0x180040c50  mov     ebx, eax
0x180040c52  cmp     eax, 2746h
0x180040c57  jz      short loc_180040C81
0x180040c59  cmp     eax, 2733h
0x180040c5e  jnz     loc_180040D3F
0x180040c64  jmp     short loc_180040C81
0x180040c66  xor     edi, edi
0x180040c68  mov     [rsp+20E0h+pullResult], rdi
0x180040c6d  jmp     loc_180040B92
0x180040c72  cmp     [rbp+1FE0h+var_2024], 2
0x180040c76  jnz     short loc_180040C81
0x180040c78  mov     eax, [rsp+20E0h+var_20A0]
0x180040c7c  cmp     [rbp+1FE0h+var_2020], eax
0x180040c7f  jz      short loc_180040CA5
0x180040c81  call    cs:__imp_GetTickCount64
0x180040c87  lea     r8, [rsp+20E0h+pullResult]; pullResult
0x180040c8c  mov     rcx, r15; ullMinuend
0x180040c8f  mov     rdx, rax; ullSubtrahend
0x180040c92  call    ULongLongSub
0x180040c97  test    eax, eax
0x180040c99  jnz     short loc_180040C66
0x180040c9b  mov     rdi, [rsp+20E0h+pullResult]
0x180040ca0  jmp     loc_180040B92
0x180040ca5  xor     ebx, ebx
0x180040ca7  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x180040cae  jz      short loc_180040CC0
0x180040cb0  mov     r8d, [rsi+30h]
0x180040cb4  lea     rdx, OfferReceivedForDiagnostics
0x180040cbb  call    McTemplateU0q_EtwEventWriteTransfer
0x180040cc0  mov     dword ptr [r14], 1
0x180040cc7  jmp     short loc_180040D3F
0x180040cc9  mov     ebx, 4C7h
0x180040cce  test    byte ptr cs:xmmword_1800616A0, 2
0x180040cd5  jz      short loc_180040D3F
0x180040cd7  mov     edx, 15h
0x180040cdc  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x180040ce3  mov     ecx, 401h
0x180040ce8  call    WPP_SF_
0x180040ced  jmp     short loc_180040D3F
0x180040cef  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 10h
0x180040cf6  jz      short loc_180040D08
0x180040cf8  mov     r8d, [rsi+30h]
0x180040cfc  lea     rdx, OfferReceiveTimeout
0x180040d03  call    McTemplateU0q_EtwEventWriteTransfer
0x180040d08  mov     dword ptr [r14], 0
0x180040d0f  xor     ebx, ebx
0x180040d11  jmp     short loc_180040D3F
0x180040d13  test    byte ptr cs:xmmword_1800616A0, 2
0x180040d1a  jz      short loc_180040D3F
0x180040d1c  mov     edx, 14h
0x180040d21  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x180040d28  mov     ecx, 401h
0x180040d2d  mov     r9d, edi
0x180040d30  call    WPP_SF_D
0x180040d35  jmp     short loc_180040D3F
0x180040d37  call    cs:__imp_WSAGetLastError
0x180040d3d  mov     ebx, eax
0x180040d3f  mov     rcx, [rsp+20E0h+hEvents]; hEvent
0x180040d44  test    rcx, rcx
0x180040d47  jz      short loc_180040D4F
0x180040d49  call    cs:__imp_WSACloseEvent
0x180040d4f  mov     eax, ebx
0x180040d51  mov     rcx, [rbp+1FE0h+var_40]
0x180040d58  xor     rcx, rsp; StackCookie
0x180040d5b  call    __security_check_cookie
0x180040d60  mov     rbx, [rsp+20E0h+arg_8]
0x180040d68  add     rsp, 20B0h
0x180040d6f  pop     r15
0x180040d71  pop     r14
0x180040d73  pop     r13
0x180040d75  pop     r12
0x180040d77  pop     rdi
0x180040d78  pop     rsi
0x180040d79  pop     rbp
0x180040d7a  retn
```
