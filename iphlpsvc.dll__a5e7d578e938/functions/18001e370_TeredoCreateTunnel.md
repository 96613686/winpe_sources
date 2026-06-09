# TeredoCreateTunnel

- ea: `0x18001e370`
- end: `0x18001e62c`
- name: `TeredoCreateTunnel`
- size: `700`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180009010`
- `0x18000d7c0`
- `0x1800190f0`
- `0x18001cb00`
- `0x18001e370`
- `0x18001e640`
- `0x18001e6d0`
- `0x18001e7c4`
- `0x18001e900`
- `0x18001f1d0`
- `0x1800389b4`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001e3df`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001e3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e55f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e55f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e476`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e476`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e4fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e4fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e54a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e54a`

## string_xrefs

- `0x18001e452`: `Updating the link layer address has failed`
- `0x18001e595`: `Created Tunnel.`
- `0x18001e5d7`: `Created Tunnel.`

## pseudocode

```c
__int64 __fastcall TeredoCreateTunnel(_QWORD *a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  __int64 result; // rax
  __int64 v5; // rcx
  DWORD LastError; // edi
  DWORD v7; // eax
  int v8; // ebp
  __int64 v9; // rax
  DWORD v10; // edi
  HANDLE FileW; // rax
  PTP_IO ThreadpoolIo; // rax
  unsigned int i; // edi

  v1 = *a1;
  v3 = *(_QWORD *)(*a1 + 2760LL);
  EventWrite0(0x100000, L"Teredo is creating tunnel device: Device %p", a1);
  result = TeredoInstallDeviceInCompartment(v3);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(v3 + 2868) = 5;
    *(_DWORD *)(v3 + 2876) = result;
    return result;
  }
  *(_OWORD *)(v1 + 2688) = *(_OWORD *)(v3 + 19428);
  LastError = ConvertInterfaceGuidToLuid((const GUID *)(v1 + 2688), (PNET_LUID)(v1 + 2704));
  if ( LastError )
  {
    *(_DWORD *)(v3 + 19396) = 8;
  }
  else if ( RunningOnXboxOne || (v7 = SetInterfaceMtuIfUninitialized(v5, *(_QWORD *)(v1 + 2704)), (LastError = v7) == 0) )
  {
    v8 = 0;
    while ( !(unsigned int)UpdateLinkAddress(v1 + 2704, v1 + 2712, 30) )
    {
      EventWriteError0(0x100000, L"Updating the link layer address has failed");
      LastError = GetLastError();
      Sleep(0x32u);
      if ( LastError == 1168 && (unsigned int)++v8 < 0xA )
        continue;
      if ( LastError )
      {
        *(_DWORD *)(v3 + 19396) = 6;
        goto LABEL_35;
      }
      break;
    }
    v9 = *(_QWORD *)(v1 + 2760);
    v10 = 0;
    if ( !*(_DWORD *)(v9 + 19412) || *(_DWORD *)(v9 + 16) != 1 )
      TeredoRestoreConnectivityStatusFromHistory(v3 + 4960);
    if ( RunningOnXboxOne )
      v10 = 3;
    FileW = CreateFileW(FileName, 0xC0000000, v10, 0, 3u, 0x40000000u, 0);
    a1[3] = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      *(_DWORD *)(v3 + 2876) = LastError;
      *(_DWORD *)(v3 + 19396) = 5;
    }
    else
    {
      ThreadpoolIo = CreateThreadpoolIo(FileW, TeredoTunnelIoComplete, 0, &CallbackEnvironment);
      a1[2] = ThreadpoolIo;
      if ( ThreadpoolIo )
      {
        if ( (unsigned int)TeredoTypeServer(*(_QWORD *)(v1 + 2760)) )
        {
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
              EVENT_IPHLPSVC_ETW_TEREDO_IO,
              L"Created Tunnel.");
        }
        else
        {
          for ( i = 0; i < 5; ++i )
          {
            if ( !(unsigned int)TeredoTunnelPostReceive(a1, 0) )
              break;
          }
          if ( !i )
          {
            LastError = 30;
            *(_DWORD *)(v3 + 19396) = 3;
            goto LABEL_35;
          }
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
              EVENT_IPHLPSVC_ETW_TEREDO_IO,
              L"Created Tunnel.");
          *(_DWORD *)(v3 + 19396) = 1;
        }
        return 0;
      }
      LastError = GetLastError();
      *(_DWORD *)(v3 + 19396) = 4;
    }
  }
  else
  {
    EventWrite0(0x100000, L"SetInterfaceMtuIfUninitialized failed: %u", v7);
    *(_DWORD *)(v3 + 19396) = 7;
  }
LABEL_35:
  *(_DWORD *)(v3 + 2868) = 5;
  TeredoDestroyTunnel(a1);
  return LastError;
}

```

## disassembly

```asm
0x18001e370  push    rbx
0x18001e372  push    rbp
0x18001e373  push    rsi
0x18001e374  push    rdi
0x18001e375  push    r12
0x18001e377  push    r14
0x18001e379  push    r15
0x18001e37b  sub     rsp, 40h
0x18001e37f  mov     rsi, [rcx]
0x18001e382  lea     rdx, aTeredoIsCreati; "Teredo is creating tunnel device: Devic"...
0x18001e389  mov     r14, rcx
0x18001e38c  mov     r8, rcx
0x18001e38f  mov     ebp, 100000h
0x18001e394  mov     ecx, ebp
0x18001e396  mov     rbx, [rsi+0AC8h]
0x18001e39d  call    EventWrite0
0x18001e3a2  mov     rcx, rbx
0x18001e3a5  call    TeredoInstallDeviceInCompartment
0x18001e3aa  test    eax, eax
0x18001e3ac  jz      short loc_18001E3C3
0x18001e3ae  mov     dword ptr [rbx+0B34h], 5
0x18001e3b8  mov     [rbx+0B3Ch], eax
0x18001e3be  jmp     loc_18001E61C
0x18001e3c3  movups  xmm0, xmmword ptr [rbx+4BE4h]
0x18001e3ca  lea     rcx, [rsi+0A80h]; InterfaceGuid
0x18001e3d1  lea     r15, [rsi+0A90h]
0x18001e3d8  mov     rdx, r15; InterfaceLuid
0x18001e3db  movdqu  xmmword ptr [rcx], xmm0
0x18001e3df  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18001e3e6  nop     dword ptr [rax+rax+00h]
0x18001e3eb  mov     edi, eax
0x18001e3ed  test    eax, eax
0x18001e3ef  jz      short loc_18001E400
0x18001e3f1  mov     dword ptr [rbx+4BC4h], 8
0x18001e3fb  jmp     loc_18001E608
0x18001e400  cmp     cs:RunningOnXboxOne, 0
0x18001e407  jnz     short loc_18001E437
0x18001e409  mov     rdx, [r15]
0x18001e40c  call    SetInterfaceMtuIfUninitialized
0x18001e411  mov     edi, eax
0x18001e413  test    eax, eax
0x18001e415  jz      short loc_18001E437
0x18001e417  mov     r8d, eax
0x18001e41a  lea     rdx, aSetinterfacemt; "SetInterfaceMtuIfUninitialized failed: "...
0x18001e421  mov     ecx, ebp
0x18001e423  call    EventWrite0
0x18001e428  mov     dword ptr [rbx+4BC4h], 7
0x18001e432  jmp     loc_18001E608
0x18001e437  xor     ebp, ebp
0x18001e439  mov     r8d, 1Eh
0x18001e43f  lea     rdx, [rsi+0A98h]
0x18001e446  mov     rcx, r15
0x18001e449  call    UpdateLinkAddress
0x18001e44e  test    eax, eax
0x18001e450  jnz     short loc_18001E4A4
0x18001e452  lea     rdx, aUpdatingTheLin; "Updating the link layer address has fai"...
0x18001e459  mov     ecx, 100000h
0x18001e45e  call    EventWriteError0
0x18001e463  call    cs:__imp_GetLastError
0x18001e46a  nop     dword ptr [rax+rax+00h]
0x18001e46f  mov     ecx, 32h ; '2'; dwMilliseconds
0x18001e474  mov     edi, eax
0x18001e476  call    cs:__imp_Sleep
0x18001e47d  nop     dword ptr [rax+rax+00h]
0x18001e482  cmp     edi, 490h
0x18001e488  jnz     short loc_18001E491
0x18001e48a  inc     ebp
0x18001e48c  cmp     ebp, 0Ah
0x18001e48f  jb      short loc_18001E439
0x18001e491  test    edi, edi
0x18001e493  jz      short loc_18001E4A4
0x18001e495  mov     dword ptr [rbx+4BC4h], 6
0x18001e49f  jmp     loc_18001E608
0x18001e4a4  mov     rax, [rsi+0AC8h]
0x18001e4ab  xor     edi, edi
0x18001e4ad  cmp     [rax+4BD4h], edi
0x18001e4b3  jz      short loc_18001E4BB
0x18001e4b5  cmp     dword ptr [rax+10h], 1
0x18001e4b9  jz      short loc_18001E4C7
0x18001e4bb  lea     rcx, [rbx+1360h]
0x18001e4c2  call    TeredoRestoreConnectivityStatusFromHistory
0x18001e4c7  cmp     cs:RunningOnXboxOne, dil
0x18001e4ce  lea     rcx, FileName; "\\\\.\\\\TeredoTun"
0x18001e4d5  mov     ebp, 3
0x18001e4da  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18001e4e3  cmovnz  edi, ebp
0x18001e4e6  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18001e4ee  mov     r8d, edi; dwShareMode
0x18001e4f1  mov     [rsp+78h+dwCreationDisposition], ebp; dwCreationDisposition
0x18001e4f5  xor     r9d, r9d; lpSecurityAttributes
0x18001e4f8  mov     edx, 0C0000000h; dwDesiredAccess
0x18001e4fd  call    cs:__imp_CreateFileW
0x18001e504  nop     dword ptr [rax+rax+00h]
0x18001e509  mov     [r14+18h], rax
0x18001e50d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e511  jnz     short loc_18001E536
0x18001e513  call    cs:__imp_GetLastError
0x18001e51a  nop     dword ptr [rax+rax+00h]
0x18001e51f  mov     edi, eax
0x18001e521  mov     [rbx+0B3Ch], eax
0x18001e527  mov     dword ptr [rbx+4BC4h], 5
0x18001e531  jmp     loc_18001E608
0x18001e536  lea     r9, CallbackEnvironment; pcbe
0x18001e53d  xor     r8d, r8d; pv
0x18001e540  lea     rdx, TeredoTunnelIoComplete; pfnio
0x18001e547  mov     rcx, rax; fl
0x18001e54a  call    cs:__imp_CreateThreadpoolIo
0x18001e551  nop     dword ptr [rax+rax+00h]
0x18001e556  mov     [r14+10h], rax
0x18001e55a  test    rax, rax
0x18001e55d  jnz     short loc_18001E57C
0x18001e55f  call    cs:__imp_GetLastError
0x18001e566  nop     dword ptr [rax+rax+00h]
0x18001e56b  mov     edi, eax
0x18001e56d  mov     dword ptr [rbx+4BC4h], 4
0x18001e577  jmp     loc_18001E608
0x18001e57c  mov     rcx, [rsi+0AC8h]
0x18001e583  call    TeredoTypeServer
0x18001e588  test    eax, eax
0x18001e58a  jz      short loc_18001E5B3
0x18001e58c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001e593  jz      short loc_18001E5AF
0x18001e595  lea     r8, aCreatedTunnel; "Created Tunnel."
0x18001e59c  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001e5a3  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001e5aa  call    McTemplateU0z_EventWriteTransfer
0x18001e5af  xor     eax, eax
0x18001e5b1  jmp     short loc_18001E61C
0x18001e5b3  xor     edi, edi
0x18001e5b5  xor     edx, edx
0x18001e5b7  mov     rcx, r14
0x18001e5ba  call    TeredoTunnelPostReceive
0x18001e5bf  test    eax, eax
0x18001e5c1  jz      short loc_18001E5CA
0x18001e5c3  inc     edi
0x18001e5c5  cmp     edi, 5
0x18001e5c8  jb      short loc_18001E5B5
0x18001e5ca  test    edi, edi
0x18001e5cc  jz      short loc_18001E5FD
0x18001e5ce  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001e5d5  jz      short loc_18001E5F1
0x18001e5d7  lea     r8, aCreatedTunnel; "Created Tunnel."
0x18001e5de  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001e5e5  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001e5ec  call    McTemplateU0z_EventWriteTransfer
0x18001e5f1  mov     dword ptr [rbx+4BC4h], 1
0x18001e5fb  jmp     short loc_18001E5AF
0x18001e5fd  mov     edi, 1Eh
0x18001e602  mov     [rbx+4BC4h], ebp
0x18001e608  mov     rcx, r14
0x18001e60b  mov     dword ptr [rbx+0B34h], 5
0x18001e615  call    TeredoDestroyTunnel
0x18001e61a  mov     eax, edi
0x18001e61c  add     rsp, 40h
0x18001e620  pop     r15
0x18001e622  pop     r14
0x18001e624  pop     r12
0x18001e626  pop     rdi
0x18001e627  pop     rsi
0x18001e628  pop     rbp
0x18001e629  pop     rbx
0x18001e62a  retn
```
