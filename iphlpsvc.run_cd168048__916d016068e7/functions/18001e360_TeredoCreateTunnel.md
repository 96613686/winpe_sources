# TeredoCreateTunnel

- ea: `0x18001e360`
- end: `0x18001e61c`
- name: `TeredoCreateTunnel`
- size: `700`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180009000`
- `0x18000d7b0`
- `0x1800190e0`
- `0x18001caf0`
- `0x18001e360`
- `0x18001e630`
- `0x18001e6c0`
- `0x18001e7b4`
- `0x18001e8f0`
- `0x18001f1c0`
- `0x1800389a4`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001e3cf`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001e3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e54f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e466`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001e466`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e4ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e4ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e53a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001e53a`

## string_xrefs

- `0x18001e442`: `Updating the link layer address has failed`
- `0x18001e585`: `Created Tunnel.`
- `0x18001e5c7`: `Created Tunnel.`

## pseudocode

```c
__int64 __fastcall TeredoCreateTunnel(__int64 *a1)
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
  v3 = *(_QWORD *)(*a1 + 2760);
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
    a1[3] = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      *(_DWORD *)(v3 + 2876) = LastError;
      *(_DWORD *)(v3 + 19396) = 5;
    }
    else
    {
      ThreadpoolIo = CreateThreadpoolIo(FileW, TeredoTunnelIoComplete, 0, &CallbackEnvironment);
      a1[2] = (__int64)ThreadpoolIo;
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
0x18001e360  push    rbx
0x18001e362  push    rbp
0x18001e363  push    rsi
0x18001e364  push    rdi
0x18001e365  push    r12
0x18001e367  push    r14
0x18001e369  push    r15
0x18001e36b  sub     rsp, 40h
0x18001e36f  mov     rsi, [rcx]
0x18001e372  lea     rdx, aTeredoIsCreati; "Teredo is creating tunnel device: Devic"...
0x18001e379  mov     r14, rcx
0x18001e37c  mov     r8, rcx
0x18001e37f  mov     ebp, 100000h
0x18001e384  mov     ecx, ebp
0x18001e386  mov     rbx, [rsi+0AC8h]
0x18001e38d  call    EventWrite0
0x18001e392  mov     rcx, rbx
0x18001e395  call    TeredoInstallDeviceInCompartment
0x18001e39a  test    eax, eax
0x18001e39c  jz      short loc_18001E3B3
0x18001e39e  mov     dword ptr [rbx+0B34h], 5
0x18001e3a8  mov     [rbx+0B3Ch], eax
0x18001e3ae  jmp     loc_18001E60C
0x18001e3b3  movups  xmm0, xmmword ptr [rbx+4BE4h]
0x18001e3ba  lea     rcx, [rsi+0A80h]; InterfaceGuid
0x18001e3c1  lea     r15, [rsi+0A90h]
0x18001e3c8  mov     rdx, r15; InterfaceLuid
0x18001e3cb  movdqu  xmmword ptr [rcx], xmm0
0x18001e3cf  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18001e3d6  nop     dword ptr [rax+rax+00h]
0x18001e3db  mov     edi, eax
0x18001e3dd  test    eax, eax
0x18001e3df  jz      short loc_18001E3F0
0x18001e3e1  mov     dword ptr [rbx+4BC4h], 8
0x18001e3eb  jmp     loc_18001E5F8
0x18001e3f0  cmp     cs:RunningOnXboxOne, 0
0x18001e3f7  jnz     short loc_18001E427
0x18001e3f9  mov     rdx, [r15]
0x18001e3fc  call    SetInterfaceMtuIfUninitialized
0x18001e401  mov     edi, eax
0x18001e403  test    eax, eax
0x18001e405  jz      short loc_18001E427
0x18001e407  mov     r8d, eax
0x18001e40a  lea     rdx, aSetinterfacemt; "SetInterfaceMtuIfUninitialized failed: "...
0x18001e411  mov     ecx, ebp
0x18001e413  call    EventWrite0
0x18001e418  mov     dword ptr [rbx+4BC4h], 7
0x18001e422  jmp     loc_18001E5F8
0x18001e427  xor     ebp, ebp
0x18001e429  mov     r8d, 1Eh
0x18001e42f  lea     rdx, [rsi+0A98h]
0x18001e436  mov     rcx, r15
0x18001e439  call    UpdateLinkAddress
0x18001e43e  test    eax, eax
0x18001e440  jnz     short loc_18001E494
0x18001e442  lea     rdx, aUpdatingTheLin; "Updating the link layer address has fai"...
0x18001e449  mov     ecx, 100000h
0x18001e44e  call    EventWriteError0
0x18001e453  call    cs:__imp_GetLastError
0x18001e45a  nop     dword ptr [rax+rax+00h]
0x18001e45f  mov     ecx, 32h ; '2'; dwMilliseconds
0x18001e464  mov     edi, eax
0x18001e466  call    cs:__imp_Sleep
0x18001e46d  nop     dword ptr [rax+rax+00h]
0x18001e472  cmp     edi, 490h
0x18001e478  jnz     short loc_18001E481
0x18001e47a  inc     ebp
0x18001e47c  cmp     ebp, 0Ah
0x18001e47f  jb      short loc_18001E429
0x18001e481  test    edi, edi
0x18001e483  jz      short loc_18001E494
0x18001e485  mov     dword ptr [rbx+4BC4h], 6
0x18001e48f  jmp     loc_18001E5F8
0x18001e494  mov     rax, [rsi+0AC8h]
0x18001e49b  xor     edi, edi
0x18001e49d  cmp     [rax+4BD4h], edi
0x18001e4a3  jz      short loc_18001E4AB
0x18001e4a5  cmp     dword ptr [rax+10h], 1
0x18001e4a9  jz      short loc_18001E4B7
0x18001e4ab  lea     rcx, [rbx+1360h]
0x18001e4b2  call    TeredoRestoreConnectivityStatusFromHistory
0x18001e4b7  cmp     cs:RunningOnXboxOne, dil
0x18001e4be  lea     rcx, FileName; "\\\\.\\\\TeredoTun"
0x18001e4c5  mov     ebp, 3
0x18001e4ca  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18001e4d3  cmovnz  edi, ebp
0x18001e4d6  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18001e4de  mov     r8d, edi; dwShareMode
0x18001e4e1  mov     [rsp+78h+dwCreationDisposition], ebp; dwCreationDisposition
0x18001e4e5  xor     r9d, r9d; lpSecurityAttributes
0x18001e4e8  mov     edx, 0C0000000h; dwDesiredAccess
0x18001e4ed  call    cs:__imp_CreateFileW
0x18001e4f4  nop     dword ptr [rax+rax+00h]
0x18001e4f9  mov     [r14+18h], rax
0x18001e4fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e501  jnz     short loc_18001E526
0x18001e503  call    cs:__imp_GetLastError
0x18001e50a  nop     dword ptr [rax+rax+00h]
0x18001e50f  mov     edi, eax
0x18001e511  mov     [rbx+0B3Ch], eax
0x18001e517  mov     dword ptr [rbx+4BC4h], 5
0x18001e521  jmp     loc_18001E5F8
0x18001e526  lea     r9, CallbackEnvironment; pcbe
0x18001e52d  xor     r8d, r8d; pv
0x18001e530  lea     rdx, TeredoTunnelIoComplete; pfnio
0x18001e537  mov     rcx, rax; fl
0x18001e53a  call    cs:__imp_CreateThreadpoolIo
0x18001e541  nop     dword ptr [rax+rax+00h]
0x18001e546  mov     [r14+10h], rax
0x18001e54a  test    rax, rax
0x18001e54d  jnz     short loc_18001E56C
0x18001e54f  call    cs:__imp_GetLastError
0x18001e556  nop     dword ptr [rax+rax+00h]
0x18001e55b  mov     edi, eax
0x18001e55d  mov     dword ptr [rbx+4BC4h], 4
0x18001e567  jmp     loc_18001E5F8
0x18001e56c  mov     rcx, [rsi+0AC8h]
0x18001e573  call    TeredoTypeServer
0x18001e578  test    eax, eax
0x18001e57a  jz      short loc_18001E5A3
0x18001e57c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001e583  jz      short loc_18001E59F
0x18001e585  lea     r8, aCreatedTunnel; "Created Tunnel."
0x18001e58c  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001e593  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001e59a  call    McTemplateU0z_EventWriteTransfer
0x18001e59f  xor     eax, eax
0x18001e5a1  jmp     short loc_18001E60C
0x18001e5a3  xor     edi, edi
0x18001e5a5  xor     edx, edx
0x18001e5a7  mov     rcx, r14
0x18001e5aa  call    TeredoTunnelPostReceive
0x18001e5af  test    eax, eax
0x18001e5b1  jz      short loc_18001E5BA
0x18001e5b3  inc     edi
0x18001e5b5  cmp     edi, 5
0x18001e5b8  jb      short loc_18001E5A5
0x18001e5ba  test    edi, edi
0x18001e5bc  jz      short loc_18001E5ED
0x18001e5be  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x18001e5c5  jz      short loc_18001E5E1
0x18001e5c7  lea     r8, aCreatedTunnel; "Created Tunnel."
0x18001e5ce  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x18001e5d5  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18001e5dc  call    McTemplateU0z_EventWriteTransfer
0x18001e5e1  mov     dword ptr [rbx+4BC4h], 1
0x18001e5eb  jmp     short loc_18001E59F
0x18001e5ed  mov     edi, 1Eh
0x18001e5f2  mov     [rbx+4BC4h], ebp
0x18001e5f8  mov     rcx, r14
0x18001e5fb  mov     dword ptr [rbx+0B34h], 5
0x18001e605  call    TeredoDestroyTunnel
0x18001e60a  mov     eax, edi
0x18001e60c  add     rsp, 40h
0x18001e610  pop     r15
0x18001e612  pop     r14
0x18001e614  pop     r12
0x18001e616  pop     rdi
0x18001e617  pop     rsi
0x18001e618  pop     rbp
0x18001e619  pop     rbx
0x18001e61a  retn
```
