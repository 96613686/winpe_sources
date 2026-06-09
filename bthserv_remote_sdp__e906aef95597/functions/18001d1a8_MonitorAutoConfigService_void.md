# MonitorAutoConfigService(void)

- ea: `0x18001d1a8`
- end: `0x18001d440`
- name: `?MonitorAutoConfigService@@YAXXZ`
- size: `664`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001ca3c`

## callees

- `0x1800017a0`
- `0x1800120b8`
- `0x18001c720`
- `0x18001cde0`
- `0x18001d1a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d373`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d28d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001d28d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d1ed`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001d1ed`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d40e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001d40e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001d32d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001d32d`

## pseudocode

```c
void MonitorAutoConfigService(void)
{
  char v0; // bl
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  bool v3; // di
  int v4; // r8d
  int v5; // edx
  SC_HANDLE v6; // rcx
  bool v7; // di
  int v8; // edx
  int v9; // r8d
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+58h] [rbp-40h] BYREF
  __int128 v12; // [rsp+68h] [rbp-30h]
  int v13; // [rsp+78h] [rbp-20h]

  pcbBytesNeeded = 0;
  v13 = 0;
  *(_OWORD *)Buffer = 0;
  v0 = 1;
  v12 = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    *((_QWORD *)pInterfaceGuid + 13) = OpenServiceW(v1, L"wlansvc", 4u);
    v6 = (SC_HANDLE)*((_QWORD *)pInterfaceGuid + 13);
    if ( v6 )
    {
      if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        *((_DWORD *)pInterfaceGuid + 4) = 2;
        *((_QWORD *)pInterfaceGuid + 4) = 0;
        *((_QWORD *)pInterfaceGuid + 3) = AutoConfigServiceStatusChangeCallback;
        *((_DWORD *)pInterfaceGuid + 12) = *(_DWORD *)&Buffer[4];
        *((_DWORD *)pInterfaceGuid + 10) = 0;
        AutoConfigServiceStatusChangeCallback((char *)pInterfaceGuid + 16);
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        v0 = 0;
      v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_24:
        BthServStopAutoConfigServiceMonitor();
LABEL_26:
        CloseServiceHandle(v2);
        return;
      }
      GetLastError();
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        v0 = 0;
      v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_24;
      GetLastError();
    }
    LOBYTE(v9) = v7;
    LOBYTE(v8) = v0;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, *((_QWORD *)WPP_GLOBAL_Control + 5));
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    v0 = 0;
  v3 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    GetLastError();
    LOBYTE(v4) = v3;
    LOBYTE(v5) = v0;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v4, *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  BthServStopAutoConfigServiceMonitor();
}

```

## disassembly

```asm
0x18001d1a8  mov     [rsp+arg_0], rbx
0x18001d1ad  mov     [rsp+arg_8], rsi
0x18001d1b2  push    rdi
0x18001d1b3  sub     rsp, 90h
0x18001d1ba  mov     rax, cs:__security_cookie
0x18001d1c1  xor     rax, rsp
0x18001d1c4  mov     [rsp+98h+var_18], rax
0x18001d1cc  xor     eax, eax
0x18001d1ce  xorps   xmm0, xmm0
0x18001d1d1  and     [rsp+98h+var_48], eax
0x18001d1d5  xor     edx, edx; lpDatabaseName
0x18001d1d7  xor     ecx, ecx; lpMachineName
0x18001d1d9  mov     [rsp+98h+var_20], eax
0x18001d1dd  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x18001d1e2  lea     ebx, [rax+1]
0x18001d1e5  mov     r8d, ebx; dwDesiredAccess
0x18001d1e8  movups  [rsp+98h+var_30], xmm0
0x18001d1ed  call    cs:__imp_OpenSCManagerW
0x18001d1f4  nop     dword ptr [rax+rax+00h]
0x18001d1f9  mov     rsi, rax
0x18001d1fc  test    rax, rax
0x18001d1ff  jnz     short loc_18001D27D
0x18001d201  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d208  lea     rax, WPP_GLOBAL_Control
0x18001d20f  cmp     rcx, rax
0x18001d212  jz      short loc_18001D21A
0x18001d214  cmp     byte ptr [rcx+19h], 3
0x18001d218  jnb     short loc_18001D21C
0x18001d21a  xor     bl, bl
0x18001d21c  lea     rax, WPP_RECORDER_INITIALIZED
0x18001d223  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001d22a  setnz   dil
0x18001d22e  test    bl, bl
0x18001d230  jnz     short loc_18001D237
0x18001d232  test    dil, dil
0x18001d235  jz      short loc_18001D273
0x18001d237  call    cs:__imp_GetLastError
0x18001d23e  nop     dword ptr [rax+rax+00h]
0x18001d243  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d24a  mov     r8b, dil
0x18001d24d  mov     [rsp+98h+var_50], eax
0x18001d251  mov     dl, bl
0x18001d253  lea     rax, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001d25a  mov     [rsp+98h+var_60], rax
0x18001d25f  mov     r9, [rcx+28h]
0x18001d263  mov     rcx, [rcx+10h]
0x18001d267  mov     [rsp+98h+var_68], 10h
0x18001d26e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001d273  call    ?BthServStopAutoConfigServiceMonitor@@YAXXZ; BthServStopAutoConfigServiceMonitor(void)
0x18001d278  jmp     loc_18001D41A
0x18001d27d  mov     r8d, 4; dwDesiredAccess
0x18001d283  lea     rdx, aWlansvc; "wlansvc"
0x18001d28a  mov     rcx, rsi; hSCManager
0x18001d28d  call    cs:__imp_OpenServiceW
0x18001d294  nop     dword ptr [rax+rax+00h]
0x18001d299  mov     rcx, cs:pInterfaceGuid
0x18001d2a0  mov     [rcx+68h], rax
0x18001d2a4  mov     rax, cs:pInterfaceGuid
0x18001d2ab  mov     rcx, [rax+68h]; hService
0x18001d2af  test    rcx, rcx
0x18001d2b2  jnz     short loc_18001D316
0x18001d2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2bb  lea     rax, WPP_GLOBAL_Control
0x18001d2c2  cmp     rcx, rax
0x18001d2c5  jz      short loc_18001D2CD
0x18001d2c7  cmp     byte ptr [rcx+19h], 3
0x18001d2cb  jnb     short loc_18001D2CF
0x18001d2cd  xor     bl, bl
0x18001d2cf  lea     rax, WPP_RECORDER_INITIALIZED
0x18001d2d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001d2dd  setnz   dil
0x18001d2e1  test    bl, bl
0x18001d2e3  jnz     short loc_18001D2EE
0x18001d2e5  test    dil, dil
0x18001d2e8  jz      loc_18001D3AF
0x18001d2ee  call    cs:__imp_GetLastError
0x18001d2f5  nop     dword ptr [rax+rax+00h]
0x18001d2fa  mov     [rsp+98h+var_50], eax
0x18001d2fe  lea     rax, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001d305  mov     [rsp+98h+var_60], rax
0x18001d30a  mov     [rsp+98h+var_68], 11h
0x18001d311  jmp     loc_18001D396
0x18001d316  lea     rax, [rsp+98h+var_48]
0x18001d31b  mov     r9d, 24h ; '$'; cbBufSize
0x18001d321  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x18001d326  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001d32b  xor     edx, edx; InfoLevel
0x18001d32d  call    cs:__imp_QueryServiceStatusEx
0x18001d334  nop     dword ptr [rax+rax+00h]
0x18001d339  test    eax, eax
0x18001d33b  jnz     short loc_18001D3B6
0x18001d33d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d344  lea     rax, WPP_GLOBAL_Control
0x18001d34b  cmp     rcx, rax
0x18001d34e  jz      short loc_18001D356
0x18001d350  cmp     byte ptr [rcx+19h], 3
0x18001d354  jnb     short loc_18001D358
0x18001d356  xor     bl, bl
0x18001d358  lea     rax, WPP_RECORDER_INITIALIZED
0x18001d35f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001d366  setnz   dil
0x18001d36a  test    bl, bl
0x18001d36c  jnz     short loc_18001D373
0x18001d36e  test    dil, dil
0x18001d371  jz      short loc_18001D3AF
0x18001d373  call    cs:__imp_GetLastError
0x18001d37a  nop     dword ptr [rax+rax+00h]
0x18001d37f  mov     [rsp+98h+var_50], eax
0x18001d383  lea     rax, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001d38a  mov     [rsp+98h+var_60], rax
0x18001d38f  mov     [rsp+98h+var_68], 12h
0x18001d396  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d39d  mov     r8b, dil
0x18001d3a0  mov     dl, bl
0x18001d3a2  mov     r9, [rcx+28h]
0x18001d3a6  mov     rcx, [rcx+10h]
0x18001d3aa  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001d3af  call    ?BthServStopAutoConfigServiceMonitor@@YAXXZ; BthServStopAutoConfigServiceMonitor(void)
0x18001d3b4  jmp     short loc_18001D40B
0x18001d3b6  mov     rax, cs:pInterfaceGuid
0x18001d3bd  lea     rcx, ?AutoConfigServiceStatusChangeCallback@@YAXPEAX@Z; AutoConfigServiceStatusChangeCallback(void *)
0x18001d3c4  mov     dword ptr [rax+10h], 2
0x18001d3cb  mov     rax, cs:pInterfaceGuid
0x18001d3d2  and     qword ptr [rax+20h], 0
0x18001d3d7  mov     rax, cs:pInterfaceGuid
0x18001d3de  mov     [rax+18h], rcx
0x18001d3e2  mov     rax, cs:pInterfaceGuid
0x18001d3e9  mov     ecx, dword ptr [rsp+98h+Buffer+4]
0x18001d3ed  mov     [rax+30h], ecx
0x18001d3f0  mov     rax, cs:pInterfaceGuid
0x18001d3f7  and     dword ptr [rax+28h], 0
0x18001d3fb  mov     rcx, cs:pInterfaceGuid
0x18001d402  add     rcx, 10h; void *
0x18001d406  call    ?AutoConfigServiceStatusChangeCallback@@YAXPEAX@Z; AutoConfigServiceStatusChangeCallback(void *)
0x18001d40b  mov     rcx, rsi; hSCObject
0x18001d40e  call    cs:__imp_CloseServiceHandle
0x18001d415  nop     dword ptr [rax+rax+00h]
0x18001d41a  mov     rcx, [rsp+98h+var_18]
0x18001d422  xor     rcx, rsp; StackCookie
0x18001d425  call    __security_check_cookie
0x18001d42a  lea     r11, [rsp+98h+var_8]
0x18001d432  mov     rbx, [r11+10h]
0x18001d436  mov     rsi, [r11+18h]
0x18001d43a  mov     rsp, r11
0x18001d43d  pop     rdi
0x18001d43e  retn
```
