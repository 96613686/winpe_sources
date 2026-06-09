# HandleSolicitations

- ea: `0x18004f084`
- end: `0x18004f61f`
- name: `HandleSolicitations`
- size: `1435`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180050e40`

## callees

- `0x18000ac60`
- `0x180011790`
- `0x18004deac`
- `0x18004f084`
- `0x18004fa98`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f1bb`
- `KERNEL32!GetLastError` at `0x18004f1bb`
- `WS2_32!WSAEnumNetworkEvents` at `0x18004f1b0`
- `WS2_32!WSAEnumNetworkEvents` at `0x18004f1b0`
- `WS2_32!WSARecvFrom` at `0x18004f303`
- `WS2_32!WSARecvFrom` at `0x18004f303`
- `WS2_32!__imp_ntohs` at `0x18004f466`
- `WS2_32!__imp_ntohs` at `0x18004f466`
- `WS2_32!__imp_WSAGetLastError` at `0x18004f30e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004f30e`

## string_xrefs

- `0x18004f297`: `HandleSolicitations: Error %d associated with socket %d on %ws for FD_READ`
- `0x18004f360`: `HandleSolicitations: Error %d in WSARecvFrom on  socket %d.%d.%d.%d over %ws. Bytes read %d`

## pseudocode

```c
__int64 *HandleSolicitations()
{
  __int64 v0; // rbx
  __int64 v1; // r13
  __int64 *result; // rax
  unsigned int i; // r15d
  SOCKET v4; // rcx
  DWORD LastError; // eax
  const wchar_t *v6; // r8
  __int128 *v7; // r9
  __int64 v8; // rax
  unsigned int Error; // edi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int128 *v12; // r9
  __int64 v13; // r14
  __int64 v14; // rdi
  int v15; // r9d
  __int128 *v16; // r9
  __int128 *v17; // r9
  LPDWORD lpFlags; // [rsp+20h] [rbp-E0h]
  struct sockaddr *lpFrom; // [rsp+28h] [rbp-D8h]
  LPINT lpFromlen; // [rsp+30h] [rbp-D0h]
  LPWSAOVERLAPPED_COMPLETION_ROUTINE lpCompletionRoutine; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesRecvd; // [rsp+50h] [rbp-B0h] BYREF
  int Fromlen; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Flags; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h] BYREF
  struct _WSANETWORKEVENTS NetworkEvents; // [rsp+70h] [rbp-90h] BYREF
  struct sockaddr From; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v29; // [rsp+B4h] [rbp-4Ch]
  __int128 v30; // [rsp+C4h] [rbp-3Ch]
  int v31; // [rsp+D4h] [rbp-2Ch]
  int v32; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v33[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  Fromlen = 0;
  NumberOfBytesRecvd = 0;
  Flags = 0;
  memset(&NetworkEvents, 0, sizeof(NetworkEvents));
  v32 = 0;
  From = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v25 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"Entered: %ws", L"HandleSolicitations");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v32);
  }
  v0 = ICBList;
  v1 = 0;
  while ( 1 )
  {
    result = &ICBList;
    if ( (__int64 *)v0 == &ICBList )
      break;
    v1 = v0;
    if ( *(_DWORD *)(v0 + 668) && *(_DWORD *)(v0 + 224) )
    {
      for ( i = 0; i < *(_DWORD *)(v0 + 668); ++i )
      {
        v4 = *(_QWORD *)(*(_QWORD *)(v0 + 288) + 8LL * i);
        if ( v4 != -1 )
        {
          if ( WSAEnumNetworkEvents(v4, 0, &NetworkEvents) == -1 )
          {
            LastError = GetLastError();
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              continue;
            LOWORD(v32) = 0;
            LOWORD(v28) = 0;
            FormatRRASErrorString(&v32, L"HandleSolicitations: WSAEnumNetworkEvents() returned %d", LastError);
            goto LABEL_14;
          }
          if ( (NetworkEvents.lNetworkEvents & 1) == 0 )
            continue;
          if ( NetworkEvents.iErrorCode[0] )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              continue;
            LOWORD(v32) = 0;
            LOWORD(v28) = 0;
            v8 = *(_QWORD *)(v0 + 712);
            LODWORD(lpFromlen) = *(unsigned __int8 *)(28LL * i + v8 + 3);
            LODWORD(lpFrom) = *(unsigned __int8 *)(28LL * i + v8 + 2);
            LODWORD(lpFlags) = *(unsigned __int8 *)(28LL * i + v8 + 1);
            FormatRRASErrorString(
              &v32,
              L"HandleSolicitations: Error %d associated with socket %d on %ws for FD_READ",
              (unsigned int)NetworkEvents.iErrorCode[0],
              *(unsigned __int8 *)(28LL * i + v8),
              lpFlags,
              lpFrom,
              lpFromlen,
              *(_QWORD *)(v0 + 72));
            goto LABEL_14;
          }
          Fromlen = 16;
          Flags = 0;
          if ( WSARecvFrom(
                 *(_QWORD *)(*(_QWORD *)(v0 + 288) + 8LL * i),
                 &g_wsaIpRcvBuf,
                 1u,
                 &NumberOfBytesRecvd,
                 &Flags,
                 &From,
                 &Fromlen,
                 0,
                 0) == -1 )
          {
            Error = WSAGetLastError();
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              continue;
            LOWORD(v32) = 0;
            LOWORD(v28) = 0;
            v10 = *(_QWORD *)(v0 + 712);
            LODWORD(lpCompletionRoutine) = NumberOfBytesRecvd;
            LODWORD(lpFromlen) = *(unsigned __int8 *)(28LL * i + v10 + 3);
            LODWORD(lpFrom) = *(unsigned __int8 *)(28LL * i + v10 + 2);
            LODWORD(lpFlags) = *(unsigned __int8 *)(28LL * i + v10 + 1);
            FormatRRASErrorString(
              &v32,
              L"HandleSolicitations: Error %d in WSARecvFrom on  socket %d.%d.%d.%d over %ws. Bytes read %d",
              Error,
              *(unsigned __int8 *)(28LL * i + v10),
              lpFlags,
              lpFrom,
              lpFromlen,
              *(_QWORD *)(v0 + 72),
              lpCompletionRoutine);
            goto LABEL_14;
          }
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v32) = 0;
            LOWORD(v28) = 0;
            v11 = *(_QWORD *)(v0 + 712);
            LODWORD(lpFromlen) = *(unsigned __int8 *)(28LL * i + v11 + 3);
            LODWORD(lpFrom) = *(unsigned __int8 *)(28LL * i + v11 + 2);
            LODWORD(lpFlags) = *(unsigned __int8 *)(28LL * i + v11 + 1);
            FormatRRASErrorString(
              &v32,
              L"HandleSolicitations: Received %d bytes on %d.%d.%d.%d",
              NumberOfBytesRecvd,
              *(unsigned __int8 *)(28LL * i + v11),
              lpFlags,
              lpFrom,
              lpFromlen);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              v12 = &v25;
              if ( v0 != -688 )
                LODWORD(v12) = v0 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v32,
                (_DWORD)v12,
                *(_QWORD *)(v0 + 72),
                (__int64)&v28);
            }
          }
          if ( !*(_DWORD *)(v0 + 264) )
          {
            v13 = 4 * (*(_BYTE *)g_pIpHeader & 0xFu);
            v14 = g_pIpHeader + v13;
            if ( *(_BYTE *)(g_pIpHeader + v13) == 10 && !*(_BYTE *)(v14 + 1) )
            {
              if ( ntohs(*(_WORD *)(g_pIpHeader + 2)) - (unsigned int)v13 < 8 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
                  continue;
                LOWORD(v28) = 0;
                v6 = L"HandleSolicitations: Received ICMP packet of length less than 8, discarding";
                goto LABEL_16;
              }
              if ( (unsigned __int16)Compute16BitXSum(v14, 8) )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
                  continue;
                LOWORD(v28) = 0;
                v6 = L"HandleSolicitations: ICMP packet checksum wrong";
                goto LABEL_16;
              }
              v15 = *(_DWORD *)(g_pIpHeader + 12);
              if ( v15
                && (*(_DWORD *)(28LL * i + *(_QWORD *)(v0 + 712) + 4) & v15) != (*(_DWORD *)(28LL * i
                                                                                           + *(_QWORD *)(v0 + 712))
                                                                               & *(_DWORD *)(28LL * i
                                                                                           + *(_QWORD *)(v0 + 712)
                                                                                           + 4)) )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
                  continue;
                LOWORD(v32) = 0;
                LOWORD(v28) = 0;
                LODWORD(lpFrom) = *(unsigned __int8 *)(g_pIpHeader + 19);
                LODWORD(lpFlags) = *(unsigned __int8 *)(g_pIpHeader + 18);
                FormatRRASErrorString(
                  &v32,
                  L"HandleSolicitations: Received ICMP solicitation from invalid neigbour %d.%d.%d.%d",
                  *(unsigned __int8 *)(g_pIpHeader + 16),
                  *(unsigned __int8 *)(g_pIpHeader + 17),
                  lpFlags,
                  lpFrom);
LABEL_14:
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
                  continue;
                v6 = (const wchar_t *)&v32;
LABEL_16:
                v7 = &v25;
                if ( v0 != -688 )
                  LODWORD(v7) = v0 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (_DWORD)v6,
                  (_DWORD)v7,
                  *(_QWORD *)(v0 + 72),
                  (__int64)&v28);
                continue;
              }
              if ( *(_DWORD *)(g_pIpHeader + 16) == -1 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                LOWORD(v28) = 0;
                v16 = &v25;
                if ( v0 != -688 )
                  LODWORD(v16) = v0 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)L"HandleSolicitations: Received a broadcast ICMP solicitation",
                  (_DWORD)v16,
                  *(_QWORD *)(v0 + 72),
                  (__int64)&v28);
              }
              *(_DWORD *)(v0 + 264) = 1;
              SetFiringTimeForReply(v0);
            }
          }
        }
      }
    }
    v0 = *(_QWORD *)v0;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v28) = 0;
    v17 = &v25;
    if ( v1 != -688 )
      LODWORD(v17) = v1 + 688;
    return (__int64 *)McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (unsigned int)RasRtrmgrParamTraceInfo,
                        (unsigned int)L"Leaving: HandleSolicitations",
                        (_DWORD)v17,
                        *(_QWORD *)(v1 + 72),
                        (__int64)&v28);
  }
  return result;
}

```

## disassembly

```asm
0x18004f084  push    rbp
0x18004f086  push    rbx
0x18004f087  push    rsi
0x18004f088  push    rdi
0x18004f089  push    r12
0x18004f08b  push    r13
0x18004f08d  push    r14
0x18004f08f  push    r15
0x18004f091  lea     rbp, [rsp-7F8h]
0x18004f099  sub     rsp, 8F8h
0x18004f0a0  mov     rax, cs:__security_cookie
0x18004f0a7  xor     rax, rsp
0x18004f0aa  mov     [rbp+830h+var_50], rax
0x18004f0b1  xorps   xmm0, xmm0
0x18004f0b4  lea     rcx, [rbp+830h+var_84C]; void *
0x18004f0b8  xor     r12d, r12d
0x18004f0bb  xor     edx, edx; Val
0x18004f0bd  movups  xmmword ptr [rbp+830h+NetworkEvents.iErrorCode+0Ch], xmm0
0x18004f0c1  mov     r8d, 7FCh; Size
0x18004f0c7  mov     [rsp+930h+Fromlen], r12d
0x18004f0cc  movups  xmmword ptr [rbp+830h+NetworkEvents.iErrorCode+18h], xmm0
0x18004f0d0  mov     [rsp+930h+NumberOfBytesRecvd], r12d
0x18004f0d5  mov     [rsp+930h+Flags], r12d
0x18004f0da  movups  xmmword ptr [rsp+930h+NetworkEvents.lNetworkEvents], xmm0
0x18004f0df  mov     [rbp+830h+var_850], r12d
0x18004f0e3  movups  xmmword ptr [rbp+830h+From.sa_family], xmm0
0x18004f0e7  call    memset_0
0x18004f0ec  xorps   xmm0, xmm0
0x18004f0ef  mov     [rbp+830h+var_880], r12d
0x18004f0f3  xor     eax, eax
0x18004f0f5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f0fc  movups  [rbp+830h+var_87C], xmm0
0x18004f100  mov     [rbp+830h+var_85C], eax
0x18004f103  movups  [rbp+830h+var_86C], xmm0
0x18004f107  movups  [rsp+930h+var_8D0], xmm0
0x18004f10c  jge     short loc_18004F14A
0x18004f10e  lea     r8, aHandlesolicita_5; "HandleSolicitations"
0x18004f115  mov     word ptr [rbp+830h+var_850], r12w
0x18004f11a  lea     rdx, aEnteredWs; "Entered: %ws"
0x18004f121  lea     rcx, [rbp+830h+var_850]
0x18004f125  call    FormatRRASErrorString
0x18004f12a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f131  jge     short loc_18004F14A
0x18004f133  lea     r8, [rbp+830h+var_850]
0x18004f137  lea     rdx, RasRtrmgrTraceInfo
0x18004f13e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f145  call    McTemplateU0z_EventWriteTransfer
0x18004f14a  mov     rbx, cs:ICBList
0x18004f151  mov     r13, r12
0x18004f154  lea     rax, ICBList
0x18004f15b  cmp     rbx, rax
0x18004f15e  jz      loc_18004F5AF
0x18004f164  mov     r13, rbx
0x18004f167  cmp     [rbx+29Ch], r12d
0x18004f16e  jz      loc_18004F5A7
0x18004f174  cmp     [rbx+0E0h], r12d
0x18004f17b  jz      loc_18004F5A7
0x18004f181  mov     r15d, r12d
0x18004f184  cmp     r15d, [rbx+29Ch]
0x18004f18b  jnb     loc_18004F5A7
0x18004f191  mov     rax, [rbx+120h]
0x18004f198  mov     esi, r15d
0x18004f19b  mov     rcx, [rax+rsi*8]; s
0x18004f19f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f1a3  jz      loc_18004F59F
0x18004f1a9  lea     r8, [rsp+930h+NetworkEvents]; lpNetworkEvents
0x18004f1ae  xor     edx, edx; hEventObject
0x18004f1b0  call    cs:__imp_WSAEnumNetworkEvents
0x18004f1b6  cmp     eax, 0FFFFFFFFh
0x18004f1b9  jnz     short loc_18004F239
0x18004f1bb  call    cs:__imp_GetLastError
0x18004f1c1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f1c8  jge     loc_18004F59F
0x18004f1ce  mov     r8d, eax
0x18004f1d1  mov     word ptr [rbp+830h+var_850], r12w
0x18004f1d6  lea     rdx, aHandlesolicita_3; "HandleSolicitations: WSAEnumNetworkEven"...
0x18004f1dd  mov     word ptr [rbp+830h+var_880], r12w
0x18004f1e2  lea     rcx, [rbp+830h+var_850]
0x18004f1e6  call    FormatRRASErrorString
0x18004f1eb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f1f2  jge     loc_18004F59F
0x18004f1f8  lea     r8, [rbp+830h+var_850]
0x18004f1fc  lea     rax, [rbx+2B0h]
0x18004f203  test    rax, rax
0x18004f206  lea     r9, [rsp+930h+var_8D0]
0x18004f20b  lea     rdx, RasRtrmgrParamTraceInfo
0x18004f212  cmovnz  r9, rax
0x18004f216  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f21d  lea     rax, [rbp+830h+var_880]
0x18004f221  mov     [rsp+930h+lpFrom], rax
0x18004f226  mov     rax, [rbx+48h]
0x18004f22a  mov     [rsp+930h+lpFlags], rax
0x18004f22f  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f234  jmp     loc_18004F59F
0x18004f239  test    byte ptr [rsp+930h+NetworkEvents.lNetworkEvents], 1
0x18004f23e  jz      loc_18004F59F
0x18004f244  mov     r8d, [rsp+930h+NetworkEvents.iErrorCode]
0x18004f249  test    r8d, r8d
0x18004f24c  jz      short loc_18004F2B2
0x18004f24e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f255  jge     loc_18004F59F
0x18004f25b  mov     word ptr [rbp+830h+var_850], r12w
0x18004f260  mov     word ptr [rbp+830h+var_880], r12w
0x18004f265  mov     rax, [rbx+2C8h]
0x18004f26c  imul    rcx, rsi, 1Ch
0x18004f270  movzx   edx, byte ptr [rcx+rax+3]
0x18004f275  movzx   r10d, byte ptr [rcx+rax+2]
0x18004f27b  movzx   r11d, byte ptr [rcx+rax+1]
0x18004f281  movzx   r9d, byte ptr [rcx+rax]
0x18004f286  lea     rcx, [rbp+830h+var_850]
0x18004f28a  mov     rax, [rbx+48h]
0x18004f28e  mov     [rsp+930h+lpOverlapped], rax
0x18004f293  mov     dword ptr [rsp+930h+lpFromlen], edx
0x18004f297  lea     rdx, aHandlesolicita_0; "HandleSolicitations: Error %d associate"...
0x18004f29e  mov     dword ptr [rsp+930h+lpFrom], r10d
0x18004f2a3  mov     dword ptr [rsp+930h+lpFlags], r11d
0x18004f2a8  call    FormatRRASErrorString
0x18004f2ad  jmp     loc_18004F1EB
0x18004f2b2  mov     [rsp+930h+lpCompletionRoutine], r12; lpCompletionRoutine
0x18004f2b7  lea     rax, [rsp+930h+Fromlen]
0x18004f2bc  mov     [rsp+930h+lpOverlapped], r12; lpOverlapped
0x18004f2c1  lea     r9, [rsp+930h+NumberOfBytesRecvd]; lpNumberOfBytesRecvd
0x18004f2c6  mov     [rsp+930h+lpFromlen], rax; lpFromlen
0x18004f2cb  lea     rdx, g_wsaIpRcvBuf; lpBuffers
0x18004f2d2  mov     [rsp+930h+Fromlen], 10h
0x18004f2da  lea     rax, [rbp+830h+From]
0x18004f2de  mov     [rsp+930h+Flags], r12d
0x18004f2e3  mov     r8d, 1; dwBufferCount
0x18004f2e9  mov     rcx, [rbx+120h]
0x18004f2f0  mov     [rsp+930h+lpFrom], rax; lpFrom
0x18004f2f5  lea     rax, [rsp+930h+Flags]
0x18004f2fa  mov     [rsp+930h+lpFlags], rax; lpFlags
0x18004f2ff  mov     rcx, [rcx+rsi*8]; s
0x18004f303  call    cs:__imp_WSARecvFrom
0x18004f309  cmp     eax, 0FFFFFFFFh
0x18004f30c  jnz     short loc_18004F387
0x18004f30e  call    cs:__imp_WSAGetLastError
0x18004f314  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f31b  mov     edi, eax
0x18004f31d  jge     loc_18004F59F
0x18004f323  mov     eax, [rsp+930h+NumberOfBytesRecvd]
0x18004f327  mov     word ptr [rbp+830h+var_850], r12w
0x18004f32c  mov     word ptr [rbp+830h+var_880], r12w
0x18004f331  mov     rcx, [rbx+2C8h]
0x18004f338  imul    rdx, rsi, 1Ch
0x18004f33c  mov     dword ptr [rsp+930h+lpCompletionRoutine], eax
0x18004f340  mov     rax, [rbx+48h]
0x18004f344  mov     [rsp+930h+lpOverlapped], rax
0x18004f349  movzx   r8d, byte ptr [rdx+rcx+3]
0x18004f34f  movzx   r10d, byte ptr [rdx+rcx+2]
0x18004f355  movzx   r11d, byte ptr [rdx+rcx+1]
0x18004f35b  movzx   r9d, byte ptr [rdx+rcx]
0x18004f360  lea     rdx, aHandlesolicita_6; "HandleSolicitations: Error %d in WSARec"...
0x18004f367  mov     dword ptr [rsp+930h+lpFromlen], r8d
0x18004f36c  lea     rcx, [rbp+830h+var_850]
0x18004f370  mov     dword ptr [rsp+930h+lpFrom], r10d
0x18004f375  mov     r8d, edi
0x18004f378  mov     dword ptr [rsp+930h+lpFlags], r11d
0x18004f37d  call    FormatRRASErrorString
0x18004f382  jmp     loc_18004F1EB
0x18004f387  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f38e  jge     loc_18004F427
0x18004f394  mov     word ptr [rbp+830h+var_850], r12w
0x18004f399  mov     word ptr [rbp+830h+var_880], r12w
0x18004f39e  mov     rax, [rbx+2C8h]
0x18004f3a5  imul    r9, rsi, 1Ch
0x18004f3a9  movzx   ecx, byte ptr [r9+rax+3]
0x18004f3af  movzx   edx, byte ptr [r9+rax+2]
0x18004f3b5  movzx   r8d, byte ptr [r9+rax+1]
0x18004f3bb  movzx   r9d, byte ptr [r9+rax]
0x18004f3c0  mov     dword ptr [rsp+930h+lpFromlen], ecx
0x18004f3c4  lea     rcx, [rbp+830h+var_850]
0x18004f3c8  mov     dword ptr [rsp+930h+lpFrom], edx
0x18004f3cc  lea     rdx, aHandlesolicita; "HandleSolicitations: Received %d bytes "...
0x18004f3d3  mov     dword ptr [rsp+930h+lpFlags], r8d
0x18004f3d8  mov     r8d, [rsp+930h+NumberOfBytesRecvd]
0x18004f3dd  call    FormatRRASErrorString
0x18004f3e2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f3e9  jge     short loc_18004F427
0x18004f3eb  lea     rax, [rbx+2B0h]
0x18004f3f2  test    rax, rax
0x18004f3f5  lea     r9, [rsp+930h+var_8D0]
0x18004f3fa  lea     r8, [rbp+830h+var_850]
0x18004f3fe  cmovnz  r9, rax
0x18004f402  lea     rdx, RasRtrmgrParamTraceInfo
0x18004f409  lea     rax, [rbp+830h+var_880]
0x18004f40d  mov     [rsp+930h+lpFrom], rax
0x18004f412  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f419  mov     rax, [rbx+48h]
0x18004f41d  mov     [rsp+930h+lpFlags], rax
0x18004f422  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f427  cmp     [rbx+108h], r12d
0x18004f42e  jnz     loc_18004F59F
0x18004f434  mov     rcx, cs:g_pIpHeader
0x18004f43b  movzx   eax, byte ptr [rcx]
0x18004f43e  and     eax, 0Fh
0x18004f441  lea     r14d, ds:0[rax*4]
0x18004f449  mov     edi, r14d
0x18004f44c  add     rdi, rcx
0x18004f44f  cmp     byte ptr [rdi], 0Ah
0x18004f452  jnz     loc_18004F59F
0x18004f458  cmp     [rdi+1], r12b
0x18004f45c  jnz     loc_18004F59F
0x18004f462  movzx   ecx, word ptr [rcx+2]; netshort
0x18004f466  call    cs:__imp_ntohs
0x18004f46c  movzx   eax, ax
0x18004f46f  sub     eax, r14d
0x18004f472  cmp     eax, 8
0x18004f475  jnb     short loc_18004F495
0x18004f477  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004f47e  jz      loc_18004F59F
0x18004f484  mov     word ptr [rbp+830h+var_880], r12w
0x18004f489  lea     r8, aHandlesolicita_7; "HandleSolicitations: Received ICMP pack"...
0x18004f490  jmp     loc_18004F1FC
0x18004f495  mov     edx, 8
0x18004f49a  mov     rcx, rdi
0x18004f49d  call    Compute16BitXSum
0x18004f4a2  test    ax, ax
0x18004f4a5  jz      short loc_18004F4C5
0x18004f4a7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004f4ae  jz      loc_18004F59F
0x18004f4b4  mov     word ptr [rbp+830h+var_880], r12w
0x18004f4b9  lea     r8, aHandlesolicita_4; "HandleSolicitations: ICMP packet checks"...
0x18004f4c0  jmp     loc_18004F1FC
0x18004f4c5  mov     r8, cs:g_pIpHeader
0x18004f4cc  mov     r9d, [r8+0Ch]
0x18004f4d0  test    r9d, r9d
0x18004f4d3  jz      short loc_18004F539
0x18004f4d5  mov     rax, [rbx+2C8h]
0x18004f4dc  imul    rdx, rsi, 1Ch
0x18004f4e0  mov     ecx, [rdx+rax+4]
0x18004f4e4  and     ecx, [rdx+rax]
0x18004f4e7  and     r9d, [rdx+rax+4]
0x18004f4ec  cmp     r9d, ecx
0x18004f4ef  jz      short loc_18004F539
0x18004f4f1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004f4f8  jge     loc_18004F59F
0x18004f4fe  mov     word ptr [rbp+830h+var_850], r12w
0x18004f503  lea     rdx, aHandlesolicita_1; "HandleSolicitations: Received ICMP soli"...
0x18004f50a  mov     word ptr [rbp+830h+var_880], r12w
0x18004f50f  movzx   ecx, byte ptr [r8+12h]
0x18004f514  movzx   eax, byte ptr [r8+13h]
0x18004f519  movzx   r9d, byte ptr [r8+11h]
0x18004f51e  movzx   r8d, byte ptr [r8+10h]
0x18004f523  mov     dword ptr [rsp+930h+lpFrom], eax
0x18004f527  mov     dword ptr [rsp+930h+lpFlags], ecx
0x18004f52b  lea     rcx, [rbp+830h+var_850]
0x18004f52f  call    FormatRRASErrorString
0x18004f534  jmp     loc_18004F1EB
0x18004f539  cmp     dword ptr [r8+10h], 0FFFFFFFFh
0x18004f53e  jnz     short loc_18004F58D
0x18004f540  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004f547  jz      short loc_18004F58D
0x18004f549  lea     rax, [rbx+2B0h]
0x18004f550  mov     word ptr [rbp+830h+var_880], r12w
0x18004f555  test    rax, rax
0x18004f558  lea     r9, [rsp+930h+var_8D0]
0x18004f55d  lea     r8, aHandlesolicita_2; "HandleSolicitations: Received a broadca"...
0x18004f564  cmovnz  r9, rax
0x18004f568  lea     rdx, RasRtrmgrParamTraceInfo
0x18004f56f  lea     rax, [rbp+830h+var_880]
0x18004f573  mov     [rsp+930h+lpFrom], rax
0x18004f578  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f57f  mov     rax, [rbx+48h]
0x18004f583  mov     [rsp+930h+lpFlags], rax
0x18004f588  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f58d  mov     rcx, rbx
0x18004f590  mov     dword ptr [rbx+108h], 1
0x18004f59a  call    SetFiringTimeForReply
0x18004f59f  inc     r15d
0x18004f5a2  jmp     loc_18004F184
0x18004f5a7  mov     rbx, [rbx]
0x18004f5aa  jmp     loc_18004F154
0x18004f5af  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004f5b6  jz      short loc_18004F5FC
0x18004f5b8  lea     rax, [r13+2B0h]
0x18004f5bf  mov     word ptr [rbp+830h+var_880], r12w
0x18004f5c4  test    rax, rax
0x18004f5c7  lea     r9, [rsp+930h+var_8D0]
0x18004f5cc  lea     r8, aLeavingHandles; "Leaving: HandleSolicitations"
0x18004f5d3  cmovnz  r9, rax
0x18004f5d7  lea     rdx, RasRtrmgrParamTraceInfo
0x18004f5de  lea     rax, [rbp+830h+var_880]
0x18004f5e2  mov     [rsp+930h+lpFrom], rax
0x18004f5e7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004f5ee  mov     rax, [r13+48h]
0x18004f5f2  mov     [rsp+930h+lpFlags], rax
0x18004f5f7  call    McTemplateU0zjzz_EventWriteTransfer
0x18004f5fc  mov     rcx, [rbp+830h+var_50]
0x18004f603  xor     rcx, rsp; StackCookie
0x18004f606  call    __security_check_cookie
0x18004f60b  add     rsp, 8F8h
0x18004f612  pop     r15
0x18004f614  pop     r14
0x18004f616  pop     r13
0x18004f618  pop     r12
0x18004f61a  pop     rdi
0x18004f61b  pop     rsi
0x18004f61c  pop     rbx
0x18004f61d  pop     rbp
  ... truncated ...
```
