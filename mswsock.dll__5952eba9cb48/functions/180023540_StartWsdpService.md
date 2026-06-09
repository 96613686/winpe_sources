# StartWsdpService

- ea: `0x180023540`
- end: `0x18002385f`
- name: `StartWsdpService`
- size: `799`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800028b8`
- `0x18000ca20`
- `0x18000db30`
- `0x18000ed0c`
- `0x1800222f0`
- `0x180022bd2`
- `0x180023540`
- `0x180038104`
- `0x18003aec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237cf`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18002379e`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18002379e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18002375b`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18002375b`
- `WS2_32!WSASocketW` at `0x1800236f1`
- `WS2_32!WSASocketW` at `0x1800236f1`
- `WS2_32!WSAProviderConfigChange` at `0x18002372f`
- `WS2_32!WSAProviderConfigChange` at `0x18002372f`
- `WS2_32!__imp_closesocket` at `0x18002370a`
- `WS2_32!__imp_closesocket` at `0x18002370a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800237e4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800237e4`
- `WS2_32!__imp_WSAStartup` at `0x180023577`
- `WS2_32!__imp_WSAStartup` at `0x180023577`
- `WS2_32!__imp_WSACleanup` at `0x18002381a`
- `WS2_32!__imp_WSACleanup` at `0x18002381a`

## pseudocode

```c
__int64 StartWsdpService()
{
  __int64 v0; // rcx
  DWORD ProtocolInfoArray; // ebx
  struct _WSAPROTOCOL_INFOW *p_ProtocolInfo; // rcx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r9
  char *v6; // rax
  __int128 v7; // xmm1
  SOCKET v8; // rax
  DWORD LastError; // eax
  WSAData WSAData; // [rsp+30h] [rbp-438h] BYREF
  struct _WSAPROTOCOL_INFOW ProtocolInfo; // [rsp+1D0h] [rbp-298h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  ProtocolInfoArray = WSAStartup(2u, &WSAData);
  if ( !ProtocolInfoArray )
  {
    ProtocolInfoArray = SockpGetProtocolInfoArray();
    if ( !ProtocolInfoArray )
    {
      memset_0(&ProtocolInfo, 0, sizeof(ProtocolInfo));
      SockAcquireRwLockExclusive();
      if ( SockSanProviderChangeHandle )
      {
        ((void (*)(void))SockReleaseRwLockExclusive)();
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 96, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
        ProtocolInfoArray = 0;
        goto LABEL_30;
      }
      ProtocolInfoArray = 10043;
      v3 = HIDWORD(qword_1800637D8);
      v4 = 0;
      v5 = (unsigned int)qword_1800637D8;
      while ( (int)v4 < SockProtocolInfoCount )
      {
        v6 = (char *)SockProtocolInfoArray + 628 * (int)v4;
        if ( *((_DWORD *)v6 + 19) == dword_1800637CC && *((_QWORD *)v6 + 11) == qword_1800637D8 )
        {
          p_ProtocolInfo = (struct _WSAPROTOCOL_INFOW *)(*(_QWORD *)(v6 + 20) - qword_180063794);
          if ( !p_ProtocolInfo )
            p_ProtocolInfo = (struct _WSAPROTOCOL_INFOW *)(*(_QWORD *)(v6 + 28) - qword_18006379C);
          if ( !p_ProtocolInfo )
          {
            ProtocolInfoArray = 0;
            p_ProtocolInfo = &ProtocolInfo;
            v4 = 4;
            v3 = 128;
            do
            {
              *(_OWORD *)&p_ProtocolInfo->dwServiceFlags1 = *(_OWORD *)v6;
              *(_OWORD *)&p_ProtocolInfo->dwProviderFlags = *((_OWORD *)v6 + 1);
              *(_OWORD *)&p_ProtocolInfo->ProviderId.Data4[4] = *((_OWORD *)v6 + 2);
              *(_OWORD *)&p_ProtocolInfo->ProtocolChain.ChainEntries[1] = *((_OWORD *)v6 + 3);
              *(_OWORD *)&p_ProtocolInfo->ProtocolChain.ChainEntries[5] = *((_OWORD *)v6 + 4);
              *(_OWORD *)&p_ProtocolInfo->iMaxSockAddr = *((_OWORD *)v6 + 5);
              *(_OWORD *)&p_ProtocolInfo->iProtocolMaxOffset = *((_OWORD *)v6 + 6);
              v7 = *((_OWORD *)v6 + 7);
              v6 += 128;
              *(_OWORD *)&p_ProtocolInfo->dwProviderReserved = v7;
              p_ProtocolInfo = (struct _WSAPROTOCOL_INFOW *)((char *)p_ProtocolInfo + 128);
              --v4;
            }
            while ( v4 );
            *(_OWORD *)&p_ProtocolInfo->dwServiceFlags1 = *(_OWORD *)v6;
            *(_OWORD *)&p_ProtocolInfo->dwProviderFlags = *((_OWORD *)v6 + 1);
            *(_OWORD *)&p_ProtocolInfo->ProviderId.Data4[4] = *((_OWORD *)v6 + 2);
            *(_OWORD *)&p_ProtocolInfo->ProtocolChain.ChainEntries[1] = *((_OWORD *)v6 + 3);
            *(_OWORD *)&p_ProtocolInfo->ProtocolChain.ChainEntries[5] = *((_OWORD *)v6 + 4);
            *(_OWORD *)&p_ProtocolInfo->iMaxSockAddr = *((_OWORD *)v6 + 5);
            *(_OWORD *)&p_ProtocolInfo->iProtocolMaxOffset = *((_OWORD *)v6 + 6);
            p_ProtocolInfo->dwProviderReserved = *((_DWORD *)v6 + 28);
            break;
          }
        }
        v4 = (unsigned int)(v4 + 1);
      }
      SockReleaseRwLockExclusive(p_ProtocolInfo, v4, v3, v5);
      if ( ProtocolInfoArray )
        goto LABEL_30;
      v8 = WSASocketW(2, 1, 6, &ProtocolInfo, 0, 0);
      if ( v8 == -1 )
        goto LABEL_25;
      closesocket(v8);
      if ( (unsigned __int8)SockCheckAndReferenceAsyncThread() )
      {
        if ( !WSAProviderConfigChange(&SockSanProviderChangeHandle, 0, 0) )
        {
          if ( CreateIoCompletionPort(
                 SockSanProviderChangeHandle,
                 SockAsyncQueuePort,
                 (ULONG_PTR)SockSanProviderChange,
                 0) )
          {
            SockSanServiceProcessLoadProviders = 1;
            *(_OWORD *)&SockSanProviderChangeOvlp.Internal = 0;
            *(_OWORD *)&SockSanProviderChangeOvlp.Offset = 0;
            if ( PostQueuedCompletionStatus(
                   SockAsyncQueuePort,
                   0,
                   (ULONG_PTR)SockSanProviderChange,
                   &SockSanProviderChangeOvlp) )
            {
              return 0;
            }
            ProtocolInfoArray = GetLastError();
            SockSanServiceProcessLoadProviders = 0;
            goto LABEL_30;
          }
          LastError = GetLastError();
          goto LABEL_26;
        }
LABEL_25:
        LastError = WSAGetLastError();
LABEL_26:
        ProtocolInfoArray = LastError;
        goto LABEL_30;
      }
      ProtocolInfoArray = 8;
    }
LABEL_30:
    WSACleanup();
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_l(v0, 97, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, ProtocolInfoArray);
  return ProtocolInfoArray;
}

```

## disassembly

```asm
0x180023540  push    rbx
0x180023542  sub     rsp, 460h
0x180023549  mov     rax, cs:__security_cookie
0x180023550  xor     rax, rsp
0x180023553  mov     [rsp+468h+var_18], rax
0x18002355b  xor     edx, edx; Val
0x18002355d  lea     rcx, [rsp+468h+WSAData]; void *
0x180023562  mov     r8d, 198h; Size
0x180023568  call    memset_0
0x18002356d  mov     ecx, 2; wVersionRequested
0x180023572  lea     rdx, [rsp+468h+WSAData]; lpWSAData
0x180023577  call    cs:__imp_WSAStartup
0x18002357e  nop     dword ptr [rax+rax+00h]
0x180023583  mov     ebx, eax
0x180023585  test    eax, eax
0x180023587  jnz     loc_180023826
0x18002358d  call    SockpGetProtocolInfoArray
0x180023592  mov     ebx, eax
0x180023594  test    eax, eax
0x180023596  jnz     loc_18002381A
0x18002359c  xor     edx, edx; Val
0x18002359e  lea     rcx, [rsp+468h+ProtocolInfo]; void *
0x1800235a6  mov     r8d, 274h; Size
0x1800235ac  call    memset_0
0x1800235b1  call    SockAcquireRwLockExclusive
0x1800235b6  cmp     cs:SockSanProviderChangeHandle, 0
0x1800235be  jnz     loc_1800237F4
0x1800235c4  mov     r10, cs:SockProtocolInfoArray
0x1800235cb  mov     ebx, 273Bh
0x1800235d0  mov     r8d, dword ptr cs:qword_1800637D8+4
0x1800235d7  xor     edx, edx
0x1800235d9  mov     r9d, dword ptr cs:qword_1800637D8
0x1800235e0  mov     r11d, cs:dword_1800637CC
0x1800235e7  cmp     edx, cs:SockProtocolInfoCount
0x1800235ed  jge     loc_1800236CA
0x1800235f3  movsxd  rax, edx
0x1800235f6  imul    rax, 274h
0x1800235fd  add     rax, r10
0x180023600  cmp     [rax+4Ch], r11d
0x180023604  jnz     short loc_18002362F
0x180023606  cmp     [rax+58h], r9d
0x18002360a  jnz     short loc_18002362F
0x18002360c  cmp     [rax+5Ch], r8d
0x180023610  jnz     short loc_18002362F
0x180023612  mov     rcx, [rax+14h]
0x180023616  sub     rcx, cs:qword_180063794
0x18002361d  jnz     short loc_18002362A
0x18002361f  mov     rcx, [rax+1Ch]
0x180023623  sub     rcx, cs:qword_18006379C
0x18002362a  test    rcx, rcx
0x18002362d  jz      short loc_180023633
0x18002362f  inc     edx
0x180023631  jmp     short loc_1800235E7
0x180023633  xor     ebx, ebx
0x180023635  lea     rcx, [rsp+468h+ProtocolInfo]
0x18002363d  lea     edx, [rbx+4]
0x180023640  lea     r8d, [rdx+7Ch]
0x180023644  movups  xmm0, xmmword ptr [rax]
0x180023647  movups  xmmword ptr [rcx], xmm0
0x18002364a  movups  xmm1, xmmword ptr [rax+10h]
0x18002364e  movups  xmmword ptr [rcx+10h], xmm1
0x180023652  movups  xmm0, xmmword ptr [rax+20h]
0x180023656  movups  xmmword ptr [rcx+20h], xmm0
0x18002365a  movups  xmm1, xmmword ptr [rax+30h]
0x18002365e  movups  xmmword ptr [rcx+30h], xmm1
0x180023662  movups  xmm0, xmmword ptr [rax+40h]
0x180023666  movups  xmmword ptr [rcx+40h], xmm0
0x18002366a  movups  xmm1, xmmword ptr [rax+50h]
0x18002366e  movups  xmmword ptr [rcx+50h], xmm1
0x180023672  movups  xmm0, xmmword ptr [rax+60h]
0x180023676  movups  xmmword ptr [rcx+60h], xmm0
0x18002367a  movups  xmm1, xmmword ptr [rax+70h]
0x18002367e  add     rax, r8
0x180023681  movups  xmmword ptr [rcx+70h], xmm1
0x180023685  add     rcx, r8
0x180023688  sub     rdx, 1
0x18002368c  jnz     short loc_180023644
0x18002368e  movups  xmm0, xmmword ptr [rax]
0x180023691  movups  xmmword ptr [rcx], xmm0
0x180023694  movups  xmm1, xmmword ptr [rax+10h]
0x180023698  movups  xmmword ptr [rcx+10h], xmm1
0x18002369c  movups  xmm0, xmmword ptr [rax+20h]
0x1800236a0  movups  xmmword ptr [rcx+20h], xmm0
0x1800236a4  movups  xmm1, xmmword ptr [rax+30h]
0x1800236a8  movups  xmmword ptr [rcx+30h], xmm1
0x1800236ac  movups  xmm0, xmmword ptr [rax+40h]
0x1800236b0  movups  xmmword ptr [rcx+40h], xmm0
0x1800236b4  movups  xmm1, xmmword ptr [rax+50h]
0x1800236b8  movups  xmmword ptr [rcx+50h], xmm1
0x1800236bc  movups  xmm0, xmmword ptr [rax+60h]
0x1800236c0  movups  xmmword ptr [rcx+60h], xmm0
0x1800236c4  mov     eax, [rax+70h]
0x1800236c7  mov     [rcx+70h], eax
0x1800236ca  call    SockReleaseRwLockExclusive
0x1800236cf  test    ebx, ebx
0x1800236d1  jnz     loc_18002381A
0x1800236d7  mov     [rsp+468h+dwFlags], ebx; dwFlags
0x1800236db  lea     r9, [rsp+468h+ProtocolInfo]; lpProtocolInfo
0x1800236e3  lea     edx, [rbx+1]; type
0x1800236e6  mov     [rsp+468h+g], ebx; g
0x1800236ea  lea     ecx, [rbx+2]; af
0x1800236ed  lea     r8d, [rbx+6]; protocol
0x1800236f1  call    cs:__imp_WSASocketW
0x1800236f8  nop     dword ptr [rax+rax+00h]
0x1800236fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023701  jz      loc_1800237E4
0x180023707  mov     rcx, rax; s
0x18002370a  call    cs:__imp_closesocket
0x180023711  nop     dword ptr [rax+rax+00h]
0x180023716  call    SockCheckAndReferenceAsyncThread
0x18002371b  test    al, al
0x18002371d  jz      loc_1800237DD
0x180023723  xor     r8d, r8d; lpCompletionRoutine
0x180023726  lea     rcx, SockSanProviderChangeHandle; lpNotificationHandle
0x18002372d  xor     edx, edx; lpOverlapped
0x18002372f  call    cs:__imp_WSAProviderConfigChange
0x180023736  nop     dword ptr [rax+rax+00h]
0x18002373b  test    eax, eax
0x18002373d  jnz     loc_1800237E4
0x180023743  mov     rdx, cs:SockAsyncQueuePort; ExistingCompletionPort
0x18002374a  lea     r8, SockSanProviderChange; CompletionKey
0x180023751  mov     rcx, cs:SockSanProviderChangeHandle; FileHandle
0x180023758  xor     r9d, r9d; NumberOfConcurrentThreads
0x18002375b  call    cs:__imp_CreateIoCompletionPort
0x180023762  nop     dword ptr [rax+rax+00h]
0x180023767  test    rax, rax
0x18002376a  jz      short loc_1800237CF
0x18002376c  mov     rcx, cs:SockAsyncQueuePort; CompletionPort
0x180023773  lea     r9, SockSanProviderChangeOvlp; lpOverlapped
0x18002377a  xorps   xmm0, xmm0
0x18002377d  mov     cs:SockSanServiceProcessLoadProviders, 1
0x180023787  lea     r8, SockSanProviderChange; dwCompletionKey
0x18002378e  xor     edx, edx; dwNumberOfBytesTransferred
0x180023790  movups  xmmword ptr cs:SockSanProviderChangeOvlp.Internal, xmm0
0x180023797  movups  xmmword ptr cs:SockSanProviderChangeOvlp.10h, xmm0
0x18002379e  call    cs:__imp_PostQueuedCompletionStatus
0x1800237a5  nop     dword ptr [rax+rax+00h]
0x1800237aa  test    eax, eax
0x1800237ac  jz      short loc_1800237B5
0x1800237ae  xor     eax, eax
0x1800237b0  jmp     loc_180023845
0x1800237b5  call    cs:__imp_GetLastError
0x1800237bc  nop     dword ptr [rax+rax+00h]
0x1800237c1  mov     ebx, eax
0x1800237c3  mov     cs:SockSanServiceProcessLoadProviders, 0
0x1800237cd  jmp     short loc_18002381A
0x1800237cf  call    cs:__imp_GetLastError
0x1800237d6  nop     dword ptr [rax+rax+00h]
0x1800237db  jmp     short loc_1800237F0
0x1800237dd  mov     ebx, 8
0x1800237e2  jmp     short loc_18002381A
0x1800237e4  call    cs:__imp_WSAGetLastError
0x1800237eb  nop     dword ptr [rax+rax+00h]
0x1800237f0  mov     ebx, eax
0x1800237f2  jmp     short loc_18002381A
0x1800237f4  call    SockReleaseRwLockExclusive
0x1800237f9  test    byte ptr cs:xmmword_180063D60, 2
0x180023800  jz      short loc_180023818
0x180023802  mov     edx, 60h ; '`'
0x180023807  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18002380e  mov     ecx, 401h
0x180023813  call    WPP_SF_
0x180023818  xor     ebx, ebx
0x18002381a  call    cs:__imp_WSACleanup
0x180023821  nop     dword ptr [rax+rax+00h]
0x180023826  test    byte ptr cs:xmmword_180063D60, 2
0x18002382d  jz      short loc_180023843
0x18002382f  mov     edx, 61h ; 'a'
0x180023834  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18002383b  mov     r9d, ebx
0x18002383e  call    WPP_SF_l
0x180023843  mov     eax, ebx
0x180023845  mov     rcx, [rsp+468h+var_18]
0x18002384d  xor     rcx, rsp; StackCookie
0x180023850  call    __security_check_cookie
0x180023855  add     rsp, 460h
0x18002385c  pop     rbx
0x18002385d  retn
```
