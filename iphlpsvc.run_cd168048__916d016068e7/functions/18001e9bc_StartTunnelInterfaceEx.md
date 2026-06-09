# StartTunnelInterfaceEx

- ea: `0x18001e9bc`
- end: `0x18001ed4b`
- name: `StartTunnelInterfaceEx`
- size: `911`
- prototype: `__int64 __fastcall(LPVOID lpInBuffer)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e8f0`
- `0x18001f6c8`
- `0x18003a080`
- `0x180045df8`

## callees

- `0x18000d7b0`
- `0x18001e9bc`
- `0x18001f014`
- `0x18001f534`
- `0x18002e150`
- `0x18004b630`
- `0x18004c1c8`
- `0x180073e08`
- `0x180073e34`

## import_xrefs

- `IPHLPAPI!ConvertGuidToStringW` at `0x18001ea09`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18001ea09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ea3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ea3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ec3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ec3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ebd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ebd5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ec7b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ec7b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ead7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ead7`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001eb42`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001eb42`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001eceb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001eceb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecff`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea66`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea66`

## string_xrefs

- `0x18001ea22`: `StartTunnelInterface: Attempting start of tunnel type: %d with InterfaceGuid: %ws`
- `0x18001ea5d`: `ServicesActive`
- `0x18001eb6a`: `Failed to start tunnel service 0x%x`
- `0x18001ea86`: `Failed to open handle to SCM 0x%x`
- `0x18001eaf7`: `Failed to open handle to tunnel service 0x%x`
- `0x18001ebfa`: `Failed to open file handle to tunnel 0x%x`

## pseudocode

```c
__int64 __fastcall StartTunnelInterfaceEx(char *lpInBuffer)
{
  __int64 LastError; // rsi
  RTL_SRWLOCK *v3; // rbx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r12
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r15
  DWORD v8; // eax
  _DWORD v10[4]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v11[80]; // [rsp+50h] [rbp-29h] BYREF

  memset_0(v11, 0, 0x4Eu);
  LODWORD(LastError) = ConvertGuidToStringW(lpInBuffer + 4, v11, 39);
  EventWrite0(
    0x800000,
    L"StartTunnelInterface: Attempting start of tunnel type: %d with InterfaceGuid: %ws",
    *(unsigned int *)lpInBuffer,
    v11);
  v3 = &ServiceControlLock;
  AcquireSRWLockExclusive(&ServiceControlLock);
  if ( gTunnelFile != (HANDLE)-1LL )
  {
    v5 = 0;
    v7 = 0;
    goto LABEL_18;
  }
  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    EventWrite0(0x800000, L"Failed to open handle to SCM 0x%x", LastError);
    if ( *(_DWORD *)lpInBuffer == 14 )
    {
      v10[0] = 13;
      ForEachCompartment(TeredoSetStartProgressInCompartment, v10, &g_ProtocolStateTeredo);
    }
    goto LABEL_27;
  }
  v6 = OpenServiceW(v4, L"tunnel", 0x10u);
  v7 = v6;
  if ( v6 )
  {
    if ( !StartServiceW(v6, 0, 0) )
    {
      v8 = GetLastError();
      LODWORD(LastError) = v8;
      if ( v8 != 1056 )
      {
        EventWrite0(0x800000, L"Failed to start tunnel service 0x%x", v8);
        if ( *(_DWORD *)lpInBuffer == 14 )
        {
          v10[0] = 11;
LABEL_12:
          ForEachCompartment(TeredoSetStartProgressInCompartment, v10, &g_ProtocolStateTeredo);
        }
LABEL_23:
        CloseServiceHandle(v7);
        goto LABEL_24;
      }
      LODWORD(LastError) = 0;
    }
    gTunnelFile = CreateFileW(L"\\\\.\\TunnelControl", 0xC0000000, 0, 0, 3u, 0, 0);
    if ( gTunnelFile == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      EventWrite0(0x800000, L"Failed to open file handle to tunnel 0x%x", LastError);
      if ( *(_DWORD *)lpInBuffer != 14 )
        goto LABEL_23;
      v10[0] = 10;
      goto LABEL_12;
    }
LABEL_18:
    ++gTunnelsStarted;
    wil::last_error_context::last_error_context((wil::last_error_context *)v10);
    ReleaseSRWLockExclusive(&ServiceControlLock);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
    v3 = 0;
    if ( DeviceIoControl(gTunnelFile, 0x12CC40u, lpInBuffer, 0x58u, 0, 0, 0, 0) )
    {
      WaitForNLBindingEvent((const struct _GUID *)(lpInBuffer + 4), 0);
    }
    else
    {
      LastError = GetLastError();
      EventWrite0(0x800000, L"Failed to send IOCTL to tunnel 0x%x", LastError);
      StopTunnelDriver();
      if ( *(_DWORD *)lpInBuffer == 14 )
      {
        v10[0] = 9;
        ForEachCompartment(TeredoSetStartProgressInCompartment, v10, &g_ProtocolStateTeredo);
      }
    }
    if ( !v7 )
    {
LABEL_24:
      if ( !v5 )
        goto LABEL_26;
      goto LABEL_25;
    }
    goto LABEL_23;
  }
  LastError = GetLastError();
  EventWrite0(0x800000, L"Failed to open handle to tunnel service 0x%x", LastError);
  if ( *(_DWORD *)lpInBuffer == 14 )
  {
    v10[0] = 12;
    ForEachCompartment(TeredoSetStartProgressInCompartment, v10, &g_ProtocolStateTeredo);
  }
LABEL_25:
  CloseServiceHandle(v5);
LABEL_26:
  if ( v3 )
LABEL_27:
    ReleaseSRWLockExclusive(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001e9bc  mov     [rsp-8+arg_8], rbx
0x18001e9c1  mov     [rsp-8+arg_10], rsi
0x18001e9c6  push    rbp
0x18001e9c7  push    r12
0x18001e9c9  push    r13
0x18001e9cb  push    r14
0x18001e9cd  push    r15
0x18001e9cf  lea     rbp, [rsp-37h]
0x18001e9d4  sub     rsp, 0B0h
0x18001e9db  mov     rax, cs:__security_cookie
0x18001e9e2  xor     rax, rsp
0x18001e9e5  mov     [rbp+57h+var_30], rax
0x18001e9e9  xor     edx, edx; Val
0x18001e9eb  mov     r14, rcx
0x18001e9ee  lea     rcx, [rbp+57h+var_80]; void *
0x18001e9f2  lea     r8d, [rdx+4Eh]; Size
0x18001e9f6  call    memset_0
0x18001e9fb  mov     r8d, 27h ; '''
0x18001ea01  lea     rdx, [rbp+57h+var_80]
0x18001ea05  lea     rcx, [r14+4]
0x18001ea09  call    cs:__imp_ConvertGuidToStringW
0x18001ea10  nop     dword ptr [rax+rax+00h]
0x18001ea15  mov     r8d, [r14]
0x18001ea18  lea     r9, [rbp+57h+var_80]
0x18001ea1c  mov     r15d, 800000h
0x18001ea22  lea     rdx, aStarttunnelint; "StartTunnelInterface: Attempting start "...
0x18001ea29  mov     ecx, r15d
0x18001ea2c  mov     esi, eax
0x18001ea2e  call    EventWrite0
0x18001ea33  lea     rbx, ?ServiceControlLock@@3Vsrwlock@wil@@A; wil::srwlock ServiceControlLock
0x18001ea3a  mov     rcx, rbx; SRWLock
0x18001ea3d  call    cs:__imp_AcquireSRWLockExclusive
0x18001ea44  nop     dword ptr [rax+rax+00h]
0x18001ea49  cmp     cs:?gTunnelFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * gTunnelFile
0x18001ea51  jnz     loc_18001EC26
0x18001ea57  mov     r8d, 1; dwDesiredAccess
0x18001ea5d  lea     rdx, DatabaseName; "ServicesActive"
0x18001ea64  xor     ecx, ecx; lpMachineName
0x18001ea66  call    cs:__imp_OpenSCManagerW
0x18001ea6d  nop     dword ptr [rax+rax+00h]
0x18001ea72  mov     r12, rax
0x18001ea75  test    rax, rax
0x18001ea78  jnz     short loc_18001EAC7
0x18001ea7a  call    cs:__imp_GetLastError
0x18001ea81  nop     dword ptr [rax+rax+00h]
0x18001ea86  lea     rdx, aFailedToOpenHa; "Failed to open handle to SCM 0x%x"
0x18001ea8d  mov     ecx, r15d
0x18001ea90  mov     r8d, eax
0x18001ea93  mov     esi, eax
0x18001ea95  call    EventWrite0
0x18001ea9a  cmp     dword ptr [r14], 0Eh
0x18001ea9e  jnz     loc_18001ED10
0x18001eaa4  lea     r8, g_ProtocolStateTeredo
0x18001eaab  mov     [rbp+57h+var_90], 0Dh
0x18001eab2  lea     rdx, [rbp+57h+var_90]
0x18001eab6  lea     rcx, TeredoSetStartProgressInCompartment
0x18001eabd  call    ForEachCompartment
0x18001eac2  jmp     loc_18001ED10
0x18001eac7  mov     r8d, 10h; dwDesiredAccess
0x18001eacd  lea     rdx, aTunnel; "tunnel"
0x18001ead4  mov     rcx, rax; hSCManager
0x18001ead7  call    cs:__imp_OpenServiceW
0x18001eade  nop     dword ptr [rax+rax+00h]
0x18001eae3  mov     r15, rax
0x18001eae6  test    rax, rax
0x18001eae9  jnz     short loc_18001EB3A
0x18001eaeb  call    cs:__imp_GetLastError
0x18001eaf2  nop     dword ptr [rax+rax+00h]
0x18001eaf7  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to tunnel service"...
0x18001eafe  mov     ecx, 800000h
0x18001eb03  mov     r8d, eax
0x18001eb06  mov     esi, eax
0x18001eb08  call    EventWrite0
0x18001eb0d  cmp     dword ptr [r14], 0Eh
0x18001eb11  jnz     loc_18001ECFC
0x18001eb17  lea     r8, g_ProtocolStateTeredo
0x18001eb1e  mov     [rbp+57h+var_90], 0Ch
0x18001eb25  lea     rdx, [rbp+57h+var_90]
0x18001eb29  lea     rcx, TeredoSetStartProgressInCompartment
0x18001eb30  call    ForEachCompartment
0x18001eb35  jmp     loc_18001ECFC
0x18001eb3a  xor     r8d, r8d; lpServiceArgVectors
0x18001eb3d  xor     edx, edx; dwNumServiceArgs
0x18001eb3f  mov     rcx, rax; hService
0x18001eb42  call    cs:__imp_StartServiceW
0x18001eb49  nop     dword ptr [rax+rax+00h]
0x18001eb4e  test    eax, eax
0x18001eb50  jnz     short loc_18001EBAA
0x18001eb52  call    cs:__imp_GetLastError
0x18001eb59  nop     dword ptr [rax+rax+00h]
0x18001eb5e  mov     esi, eax
0x18001eb60  cmp     eax, 420h
0x18001eb65  jz      short loc_18001EBA8
0x18001eb67  mov     r8d, eax
0x18001eb6a  lea     rdx, aFailedToStartT_3; "Failed to start tunnel service 0x%x"
0x18001eb71  mov     ecx, 800000h
0x18001eb76  call    EventWrite0
0x18001eb7b  cmp     dword ptr [r14], 0Eh
0x18001eb7f  jnz     loc_18001ECE8
0x18001eb85  mov     [rbp+57h+var_90], 0Bh
0x18001eb8c  lea     r8, g_ProtocolStateTeredo
0x18001eb93  lea     rdx, [rbp+57h+var_90]
0x18001eb97  lea     rcx, TeredoSetStartProgressInCompartment
0x18001eb9e  call    ForEachCompartment
0x18001eba3  jmp     loc_18001ECE8
0x18001eba8  xor     esi, esi
0x18001ebaa  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18001ebb3  lea     rcx, aTunnelcontrol; "\\\\.\\TunnelControl"
0x18001ebba  mov     [rsp+0D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001ebc2  xor     r9d, r9d; lpSecurityAttributes
0x18001ebc5  xor     r8d, r8d; dwShareMode
0x18001ebc8  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ebd0  mov     edx, 0C0000000h; dwDesiredAccess
0x18001ebd5  call    cs:__imp_CreateFileW
0x18001ebdc  nop     dword ptr [rax+rax+00h]
0x18001ebe1  mov     cs:?gTunnelFile@@3PEAXEA, rax; void * gTunnelFile
0x18001ebe8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ebec  jnz     short loc_18001EC2C
0x18001ebee  call    cs:__imp_GetLastError
0x18001ebf5  nop     dword ptr [rax+rax+00h]
0x18001ebfa  lea     rdx, aFailedToOpenFi; "Failed to open file handle to tunnel 0x"...
0x18001ec01  mov     ecx, 800000h
0x18001ec06  mov     r8d, eax
0x18001ec09  mov     esi, eax
0x18001ec0b  call    EventWrite0
0x18001ec10  cmp     dword ptr [r14], 0Eh
0x18001ec14  jnz     loc_18001ECE8
0x18001ec1a  mov     [rbp+57h+var_90], 0Ah
0x18001ec21  jmp     loc_18001EB8C
0x18001ec26  xor     r12d, r12d
0x18001ec29  xor     r15d, r15d
0x18001ec2c  inc     cs:?gTunnelsStarted@@3KA; ulong gTunnelsStarted
0x18001ec32  lea     rcx, [rbp+57h+var_90]; this
0x18001ec36  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ec3b  mov     rcx, rbx; SRWLock
0x18001ec3e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ec45  nop     dword ptr [rax+rax+00h]
0x18001ec4a  lea     rcx, [rbp+57h+var_90]; this
0x18001ec4e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ec53  mov     rcx, cs:?gTunnelFile@@3PEAXEA; hDevice
0x18001ec5a  xor     ebx, ebx
0x18001ec5c  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x18001ec61  mov     r8, r14; lpInBuffer
0x18001ec64  mov     [rsp+0D0h+hTemplateFile], rbx; lpBytesReturned
0x18001ec69  mov     edx, 12CC40h; dwIoControlCode
0x18001ec6e  mov     [rsp+0D0h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18001ec72  lea     r9d, [rbx+58h]; nInBufferSize
0x18001ec76  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rbx; lpOutBuffer
0x18001ec7b  call    cs:__imp_DeviceIoControl
0x18001ec82  nop     dword ptr [rax+rax+00h]
0x18001ec87  test    eax, eax
0x18001ec89  jnz     short loc_18001ECD8
0x18001ec8b  call    cs:__imp_GetLastError
0x18001ec92  nop     dword ptr [rax+rax+00h]
0x18001ec97  lea     rdx, aFailedToSendIo; "Failed to send IOCTL to tunnel 0x%x"
0x18001ec9e  mov     ecx, 800000h
0x18001eca3  mov     r8d, eax
0x18001eca6  mov     esi, eax
0x18001eca8  call    EventWrite0
0x18001ecad  call    ?StopTunnelDriver@@YAKXZ; StopTunnelDriver(void)
0x18001ecb2  cmp     dword ptr [r14], 0Eh
0x18001ecb6  jnz     short loc_18001ECE3
0x18001ecb8  lea     r8, g_ProtocolStateTeredo
0x18001ecbf  mov     [rbp+57h+var_90], 9
0x18001ecc6  lea     rdx, [rbp+57h+var_90]
0x18001ecca  lea     rcx, TeredoSetStartProgressInCompartment
0x18001ecd1  call    ForEachCompartment
0x18001ecd6  jmp     short loc_18001ECE3
0x18001ecd8  xor     edx, edx; unsigned __int8
0x18001ecda  lea     rcx, [r14+4]; struct _GUID *
0x18001ecde  call    ?WaitForNLBindingEvent@@YAXPEBU_GUID@@E@Z; WaitForNLBindingEvent(_GUID const *,uchar)
0x18001ece3  test    r15, r15
0x18001ece6  jz      short loc_18001ECF7
0x18001ece8  mov     rcx, r15; hSCObject
0x18001eceb  call    cs:__imp_CloseServiceHandle
0x18001ecf2  nop     dword ptr [rax+rax+00h]
0x18001ecf7  test    r12, r12
0x18001ecfa  jz      short loc_18001ED0B
0x18001ecfc  mov     rcx, r12; hSCObject
0x18001ecff  call    cs:__imp_CloseServiceHandle
0x18001ed06  nop     dword ptr [rax+rax+00h]
0x18001ed0b  test    rbx, rbx
0x18001ed0e  jz      short loc_18001ED1F
0x18001ed10  mov     rcx, rbx; SRWLock
0x18001ed13  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ed1a  nop     dword ptr [rax+rax+00h]
0x18001ed1f  mov     eax, esi
0x18001ed21  mov     rcx, [rbp+57h+var_30]
0x18001ed25  xor     rcx, rsp; StackCookie
0x18001ed28  call    __security_check_cookie
0x18001ed2d  lea     r11, [rsp+0D0h+var_20]
0x18001ed35  mov     rbx, [r11+38h]
0x18001ed39  mov     rsi, [r11+40h]
0x18001ed3d  mov     rsp, r11
0x18001ed40  pop     r15
0x18001ed42  pop     r14
0x18001ed44  pop     r13
0x18001ed46  pop     r12
0x18001ed48  pop     rbp
0x18001ed49  retn
```
