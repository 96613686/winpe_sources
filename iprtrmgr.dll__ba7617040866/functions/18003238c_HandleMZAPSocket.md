# HandleMZAPSocket

- ea: `0x18003238c`
- end: `0x1800325b9`
- name: `HandleMZAPSocket`
- size: `557`
- prototype: `unsigned int __fastcall(__int64, SOCKET)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003225c`

## callees

- `0x18000ac60`
- `0x18003238c`
- `0x1800327ec`
- `0x180032e80`
- `0x180033344`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `WS2_32!WSAEnumNetworkEvents` at `0x180032418`
- `WS2_32!WSAEnumNetworkEvents` at `0x180032418`
- `WS2_32!WSARecvFrom` at `0x180032525`
- `WS2_32!WSARecvFrom` at `0x180032525`
- `WS2_32!__imp_WSAGetLastError` at `0x180032423`
- `WS2_32!__imp_WSAGetLastError` at `0x180032591`
- `WS2_32!__imp_WSAGetLastError` at `0x180032423`
- `WS2_32!__imp_WSAGetLastError` at `0x180032591`

## string_xrefs

- `0x180032479`: `HandleMZAPMessages: Error %d on FD_READ`

## pseudocode

```c
unsigned int __fastcall HandleMZAPSocket(__int64 a1, SOCKET a2)
{
  unsigned int result; // eax
  __int64 *v5; // rdx
  int Fromlen; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Flags; // [rsp+54h] [rbp-ACh] BYREF
  DWORD NumberOfBytesRecvd; // [rsp+58h] [rbp-A8h] BYREF
  _WSANETWORKEVENTS NetworkEvents; // [rsp+60h] [rbp-A0h] BYREF
  struct sockaddr From; // [rsp+90h] [rbp-70h] BYREF
  int v11; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v12[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  NumberOfBytesRecvd = 0;
  Flags = 0;
  Fromlen = 0;
  v11 = 0;
  From = 0;
  memset(&NetworkEvents, 0, sizeof(NetworkEvents));
  result = (unsigned int)memset_0(v12, 0, sizeof(v12));
  if ( a2 == -1 )
    return result;
  result = WSAEnumNetworkEvents(a2, 0, &NetworkEvents);
  if ( result != -1 )
  {
    if ( (NetworkEvents.lNetworkEvents & 1) == 0 )
      return result;
    if ( NetworkEvents.iErrorCode[0] )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return result;
      LOWORD(v11) = 0;
      result = FormatRRASErrorString(&v11, L"HandleMZAPMessages: Error %d on FD_READ");
    }
    else
    {
      Fromlen = 16;
      Flags = 0;
      result = WSARecvFrom(a2, &g_wsaMcRcvBuf, 1u, &NumberOfBytesRecvd, &Flags, &From, &Fromlen, 0, 0);
      if ( !result && NumberOfBytesRecvd && g_wsaMcRcvBuf.len > 2 )
      {
        if ( !*g_wsaMcRcvBuf.buf )
        {
          if ( (g_wsaMcRcvBuf.buf[1] & 0x7F) != 0 )
          {
            if ( (g_wsaMcRcvBuf.buf[1] & 0x7F) == 1 )
            {
              return HandleZLE();
            }
            else if ( (g_wsaMcRcvBuf.buf[1] & 0x7F) == 2 )
            {
              return HandleZCM(g_wsaMcRcvBuf.buf, NumberOfBytesRecvd, a1);
            }
          }
          else
          {
            return HandleZAM(g_wsaMcRcvBuf.buf, NumberOfBytesRecvd);
          }
        }
        return result;
      }
      result = WSAGetLastError();
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return result;
      LOWORD(v11) = 0;
      result = FormatRRASErrorString(&v11, L"HandleMZAPSocket: Error %d receiving MZAP message");
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return result;
    v5 = RasRtrMgrTraceError;
    return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v5, &v11);
  }
  result = WSAGetLastError();
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v11) = 0;
    result = FormatRRASErrorString(&v11, L"HandleMZAPMessages: WSAEnumNetworkEvents() returned %d", result);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v5 = RasRtrmgrTraceInfo;
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v5, &v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003238c  mov     [rsp-8+arg_10], rbx
0x180032391  mov     [rsp-8+arg_18], rdi
0x180032396  push    rbp
0x180032397  lea     rbp, [rsp-7B0h]
0x18003239f  sub     rsp, 8B0h
0x1800323a6  mov     rax, cs:__security_cookie
0x1800323ad  xor     rax, rsp
0x1800323b0  mov     [rbp+7B0h+var_10], rax
0x1800323b7  xorps   xmm1, xmm1
0x1800323ba  mov     [rsp+8B0h+NumberOfBytesRecvd], 0
0x1800323c2  mov     rdi, rdx
0x1800323c5  mov     [rsp+8B0h+Flags], 0
0x1800323cd  mov     rbx, rcx
0x1800323d0  mov     [rsp+8B0h+Fromlen], 0
0x1800323d8  xorps   xmm0, xmm0
0x1800323db  lea     rcx, [rbp+7B0h+var_80C]; void *
0x1800323df  xor     eax, eax
0x1800323e1  xor     edx, edx; Val
0x1800323e3  movups  xmmword ptr [rsp+8B0h+NetworkEvents.iErrorCode+0Ch], xmm1
0x1800323e8  mov     r8d, 7FCh; Size
0x1800323ee  mov     [rbp+7B0h+var_810], eax
0x1800323f1  movups  xmmword ptr [rsp+8B0h+NetworkEvents.iErrorCode+18h], xmm1
0x1800323f6  movups  xmmword ptr [rbp+7B0h+From.sa_family], xmm0
0x1800323fa  movups  xmmword ptr [rsp+8B0h+NetworkEvents.lNetworkEvents], xmm1
0x1800323ff  call    memset_0
0x180032404  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180032408  jz      loc_1800324AD
0x18003240e  lea     r8, [rsp+8B0h+NetworkEvents]; lpNetworkEvents
0x180032413  xor     edx, edx; hEventObject
0x180032415  mov     rcx, rdi; s
0x180032418  call    cs:__imp_WSAEnumNetworkEvents
0x18003241e  cmp     eax, 0FFFFFFFFh
0x180032421  jnz     short loc_18003245D
0x180032423  call    cs:__imp_WSAGetLastError
0x180032429  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180032430  jge     short loc_1800324AD
0x180032432  xor     ecx, ecx
0x180032434  lea     rdx, aHandlemzapmess; "HandleMZAPMessages: WSAEnumNetworkEvent"...
0x18003243b  mov     word ptr [rbp+7B0h+var_810], cx
0x18003243f  mov     r8d, eax
0x180032442  lea     rcx, [rbp+7B0h+var_810]
0x180032446  call    FormatRRASErrorString
0x18003244b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180032452  jge     short loc_1800324AD
0x180032454  lea     rdx, RasRtrmgrTraceInfo
0x18003245b  jmp     short loc_18003249D
0x18003245d  test    byte ptr [rsp+8B0h+NetworkEvents.lNetworkEvents], 1
0x180032462  jz      short loc_1800324AD
0x180032464  mov     r8d, [rsp+8B0h+NetworkEvents.iErrorCode]
0x180032469  test    r8d, r8d
0x18003246c  jz      short loc_1800324D1
0x18003246e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180032475  jz      short loc_1800324AD
0x180032477  xor     eax, eax
0x180032479  lea     rdx, aHandlemzapmess_1; "HandleMZAPMessages: Error %d on FD_READ"
0x180032480  mov     word ptr [rbp+7B0h+var_810], ax
0x180032484  lea     rcx, [rbp+7B0h+var_810]
0x180032488  call    FormatRRASErrorString
0x18003248d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180032494  jz      short loc_1800324AD
0x180032496  lea     rdx, RasRtrMgrTraceError
0x18003249d  lea     r8, [rbp+7B0h+var_810]
0x1800324a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800324a8  call    McTemplateU0z_EventWriteTransfer
0x1800324ad  mov     rcx, [rbp+7B0h+var_10]
0x1800324b4  xor     rcx, rsp; StackCookie
0x1800324b7  call    __security_check_cookie
0x1800324bc  lea     r11, [rsp+8B0h+var_s0]
0x1800324c4  mov     rbx, [r11+20h]
0x1800324c8  mov     rdi, [r11+28h]
0x1800324cc  mov     rsp, r11
0x1800324cf  pop     rbp
0x1800324d0  retn
0x1800324d1  mov     [rsp+8B0h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800324da  lea     rax, [rsp+8B0h+Fromlen]
0x1800324df  mov     [rsp+8B0h+lpOverlapped], 0; lpOverlapped
0x1800324e8  lea     r9, [rsp+8B0h+NumberOfBytesRecvd]; lpNumberOfBytesRecvd
0x1800324ed  mov     [rsp+8B0h+lpFromlen], rax; lpFromlen
0x1800324f2  lea     rdx, g_wsaMcRcvBuf; lpBuffers
0x1800324f9  lea     rax, [rbp+7B0h+From]
0x1800324fd  mov     [rsp+8B0h+Fromlen], 10h
0x180032505  mov     [rsp+8B0h+lpFrom], rax; lpFrom
0x18003250a  mov     r8d, 1; dwBufferCount
0x180032510  lea     rax, [rsp+8B0h+Flags]
0x180032515  mov     [rsp+8B0h+Flags], 0
0x18003251d  mov     rcx, rdi; s
0x180032520  mov     [rsp+8B0h+lpFlags], rax; lpFlags
0x180032525  call    cs:__imp_WSARecvFrom
0x18003252b  test    eax, eax
0x18003252d  jnz     short loc_180032591
0x18003252f  mov     edx, [rsp+8B0h+NumberOfBytesRecvd]; Size
0x180032533  test    edx, edx
0x180032535  jz      short loc_180032591
0x180032537  cmp     cs:g_wsaMcRcvBuf.len, 2
0x18003253e  jbe     short loc_180032591
0x180032540  mov     rcx, cs:g_wsaMcRcvBuf.buf; buf
0x180032547  cmp     [rcx], al
0x180032549  jnz     loc_1800324AD
0x18003254f  movzx   r9d, byte ptr [rcx+1]
0x180032554  and     r9d, 0FFFFFF7Fh
0x18003255b  jz      short loc_180032584
0x18003255d  sub     r9d, 1
0x180032561  jz      short loc_18003257A
0x180032563  cmp     r9d, 1
0x180032567  jnz     loc_1800324AD
0x18003256d  mov     r8, rbx
0x180032570  call    HandleZCM
0x180032575  jmp     loc_1800324AD
0x18003257a  call    HandleZLE
0x18003257f  jmp     loc_1800324AD
0x180032584  mov     r8, rbx
0x180032587  call    HandleZAM
0x18003258c  jmp     loc_1800324AD
0x180032591  call    cs:__imp_WSAGetLastError
0x180032597  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003259e  jz      loc_1800324AD
0x1800325a4  xor     ecx, ecx
0x1800325a6  lea     rdx, aHandlemzapsock; "HandleMZAPSocket: Error %d receiving MZ"...
0x1800325ad  mov     word ptr [rbp+7B0h+var_810], cx
0x1800325b1  mov     r8d, eax
0x1800325b4  jmp     loc_180032484
```
