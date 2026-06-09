# StartTunnelInterfaceEx

- ea: `0x18001e9cc`
- end: `0x18001ed5b`
- name: `StartTunnelInterfaceEx`
- size: `911`
- prototype: `__int64 __fastcall(char *lpInBuffer)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e900`
- `0x18001f6d8`
- `0x18003a090`
- `0x180045db8`

## callees

- `0x18000d7c0`
- `0x18001e9cc`
- `0x18001f024`
- `0x18001f544`
- `0x18002e160`
- `0x18004b5f0`
- `0x18004c188`
- `0x180073e28`
- `0x180073e54`

## import_xrefs

- `IPHLPAPI!ConvertGuidToStringW` at `0x18001ea19`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18001ea19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ea4d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ea4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ec4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ec4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec9b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ebe5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ebe5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ec8b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001ec8b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001eae7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001eae7`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001eb52`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001eb52`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecfb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ed0f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ecfb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ed0f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea76`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea76`

## string_xrefs

- `0x18001ea32`: `StartTunnelInterface: Attempting start of tunnel type: %d with InterfaceGuid: %ws`
- `0x18001ea6d`: `ServicesActive`
- `0x18001eb7a`: `Failed to start tunnel service 0x%x`
- `0x18001ea96`: `Failed to open handle to SCM 0x%x`
- `0x18001eb07`: `Failed to open handle to tunnel service 0x%x`
- `0x18001ec0a`: `Failed to open file handle to tunnel 0x%x`

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
0x18001e9cc  mov     [rsp-8+arg_8], rbx
0x18001e9d1  mov     [rsp-8+arg_10], rsi
0x18001e9d6  push    rbp
0x18001e9d7  push    r12
0x18001e9d9  push    r13
0x18001e9db  push    r14
0x18001e9dd  push    r15
0x18001e9df  lea     rbp, [rsp-37h]
0x18001e9e4  sub     rsp, 0B0h
0x18001e9eb  mov     rax, cs:__security_cookie
0x18001e9f2  xor     rax, rsp
0x18001e9f5  mov     [rbp+57h+var_30], rax
0x18001e9f9  xor     edx, edx; Val
0x18001e9fb  mov     r14, rcx
0x18001e9fe  lea     rcx, [rbp+57h+var_80]; void *
0x18001ea02  lea     r8d, [rdx+4Eh]; Size
0x18001ea06  call    memset_0
0x18001ea0b  mov     r8d, 27h ; '''
0x18001ea11  lea     rdx, [rbp+57h+var_80]
0x18001ea15  lea     rcx, [r14+4]
0x18001ea19  call    cs:__imp_ConvertGuidToStringW
0x18001ea20  nop     dword ptr [rax+rax+00h]
0x18001ea25  mov     r8d, [r14]
0x18001ea28  lea     r9, [rbp+57h+var_80]
0x18001ea2c  mov     r15d, 800000h
0x18001ea32  lea     rdx, aStarttunnelint; "StartTunnelInterface: Attempting start "...
0x18001ea39  mov     ecx, r15d
0x18001ea3c  mov     esi, eax
0x18001ea3e  call    EventWrite0
0x18001ea43  lea     rbx, ?ServiceControlLock@@3Vsrwlock@wil@@A; wil::srwlock ServiceControlLock
0x18001ea4a  mov     rcx, rbx; SRWLock
0x18001ea4d  call    cs:__imp_AcquireSRWLockExclusive
0x18001ea54  nop     dword ptr [rax+rax+00h]
0x18001ea59  cmp     cs:?gTunnelFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * gTunnelFile
0x18001ea61  jnz     loc_18001EC36
0x18001ea67  mov     r8d, 1; dwDesiredAccess
0x18001ea6d  lea     rdx, DatabaseName; "ServicesActive"
0x18001ea74  xor     ecx, ecx; lpMachineName
0x18001ea76  call    cs:__imp_OpenSCManagerW
0x18001ea7d  nop     dword ptr [rax+rax+00h]
0x18001ea82  mov     r12, rax
0x18001ea85  test    rax, rax
0x18001ea88  jnz     short loc_18001EAD7
0x18001ea8a  call    cs:__imp_GetLastError
0x18001ea91  nop     dword ptr [rax+rax+00h]
0x18001ea96  lea     rdx, aFailedToOpenHa; "Failed to open handle to SCM 0x%x"
0x18001ea9d  mov     ecx, r15d
0x18001eaa0  mov     r8d, eax
0x18001eaa3  mov     esi, eax
0x18001eaa5  call    EventWrite0
0x18001eaaa  cmp     dword ptr [r14], 0Eh
0x18001eaae  jnz     loc_18001ED20
0x18001eab4  lea     r8, g_ProtocolStateTeredo
0x18001eabb  mov     [rbp+57h+var_90], 0Dh
0x18001eac2  lea     rdx, [rbp+57h+var_90]
0x18001eac6  lea     rcx, TeredoSetStartProgressInCompartment
0x18001eacd  call    ForEachCompartment
0x18001ead2  jmp     loc_18001ED20
0x18001ead7  mov     r8d, 10h; dwDesiredAccess
0x18001eadd  lea     rdx, aTunnel; "tunnel"
0x18001eae4  mov     rcx, rax; hSCManager
0x18001eae7  call    cs:__imp_OpenServiceW
0x18001eaee  nop     dword ptr [rax+rax+00h]
0x18001eaf3  mov     r15, rax
0x18001eaf6  test    rax, rax
0x18001eaf9  jnz     short loc_18001EB4A
0x18001eafb  call    cs:__imp_GetLastError
0x18001eb02  nop     dword ptr [rax+rax+00h]
0x18001eb07  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to tunnel service"...
0x18001eb0e  mov     ecx, 800000h
0x18001eb13  mov     r8d, eax
0x18001eb16  mov     esi, eax
0x18001eb18  call    EventWrite0
0x18001eb1d  cmp     dword ptr [r14], 0Eh
0x18001eb21  jnz     loc_18001ED0C
0x18001eb27  lea     r8, g_ProtocolStateTeredo
0x18001eb2e  mov     [rbp+57h+var_90], 0Ch
0x18001eb35  lea     rdx, [rbp+57h+var_90]
0x18001eb39  lea     rcx, TeredoSetStartProgressInCompartment
0x18001eb40  call    ForEachCompartment
0x18001eb45  jmp     loc_18001ED0C
0x18001eb4a  xor     r8d, r8d; lpServiceArgVectors
0x18001eb4d  xor     edx, edx; dwNumServiceArgs
0x18001eb4f  mov     rcx, rax; hService
0x18001eb52  call    cs:__imp_StartServiceW
0x18001eb59  nop     dword ptr [rax+rax+00h]
0x18001eb5e  test    eax, eax
0x18001eb60  jnz     short loc_18001EBBA
0x18001eb62  call    cs:__imp_GetLastError
0x18001eb69  nop     dword ptr [rax+rax+00h]
0x18001eb6e  mov     esi, eax
0x18001eb70  cmp     eax, 420h
0x18001eb75  jz      short loc_18001EBB8
0x18001eb77  mov     r8d, eax
0x18001eb7a  lea     rdx, aFailedToStartT_3; "Failed to start tunnel service 0x%x"
0x18001eb81  mov     ecx, 800000h
0x18001eb86  call    EventWrite0
0x18001eb8b  cmp     dword ptr [r14], 0Eh
0x18001eb8f  jnz     loc_18001ECF8
0x18001eb95  mov     [rbp+57h+var_90], 0Bh
0x18001eb9c  lea     r8, g_ProtocolStateTeredo
0x18001eba3  lea     rdx, [rbp+57h+var_90]
0x18001eba7  lea     rcx, TeredoSetStartProgressInCompartment
0x18001ebae  call    ForEachCompartment
0x18001ebb3  jmp     loc_18001ECF8
0x18001ebb8  xor     esi, esi
0x18001ebba  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18001ebc3  lea     rcx, aTunnelcontrol; "\\\\.\\TunnelControl"
0x18001ebca  mov     [rsp+0D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001ebd2  xor     r9d, r9d; lpSecurityAttributes
0x18001ebd5  xor     r8d, r8d; dwShareMode
0x18001ebd8  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ebe0  mov     edx, 0C0000000h; dwDesiredAccess
0x18001ebe5  call    cs:__imp_CreateFileW
0x18001ebec  nop     dword ptr [rax+rax+00h]
0x18001ebf1  mov     cs:?gTunnelFile@@3PEAXEA, rax; void * gTunnelFile
0x18001ebf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ebfc  jnz     short loc_18001EC3C
0x18001ebfe  call    cs:__imp_GetLastError
0x18001ec05  nop     dword ptr [rax+rax+00h]
0x18001ec0a  lea     rdx, aFailedToOpenFi; "Failed to open file handle to tunnel 0x"...
0x18001ec11  mov     ecx, 800000h
0x18001ec16  mov     r8d, eax
0x18001ec19  mov     esi, eax
0x18001ec1b  call    EventWrite0
0x18001ec20  cmp     dword ptr [r14], 0Eh
0x18001ec24  jnz     loc_18001ECF8
0x18001ec2a  mov     [rbp+57h+var_90], 0Ah
0x18001ec31  jmp     loc_18001EB9C
0x18001ec36  xor     r12d, r12d
0x18001ec39  xor     r15d, r15d
0x18001ec3c  inc     cs:?gTunnelsStarted@@3KA; ulong gTunnelsStarted
0x18001ec42  lea     rcx, [rbp+57h+var_90]; this
0x18001ec46  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ec4b  mov     rcx, rbx; SRWLock
0x18001ec4e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ec55  nop     dword ptr [rax+rax+00h]
0x18001ec5a  lea     rcx, [rbp+57h+var_90]; this
0x18001ec5e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ec63  mov     rcx, cs:?gTunnelFile@@3PEAXEA; hDevice
0x18001ec6a  xor     ebx, ebx
0x18001ec6c  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x18001ec71  mov     r8, r14; lpInBuffer
0x18001ec74  mov     [rsp+0D0h+hTemplateFile], rbx; lpBytesReturned
0x18001ec79  mov     edx, 12CC40h; dwIoControlCode
0x18001ec7e  mov     [rsp+0D0h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18001ec82  lea     r9d, [rbx+58h]; nInBufferSize
0x18001ec86  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rbx; lpOutBuffer
0x18001ec8b  call    cs:__imp_DeviceIoControl
0x18001ec92  nop     dword ptr [rax+rax+00h]
0x18001ec97  test    eax, eax
0x18001ec99  jnz     short loc_18001ECE8
0x18001ec9b  call    cs:__imp_GetLastError
0x18001eca2  nop     dword ptr [rax+rax+00h]
0x18001eca7  lea     rdx, aFailedToSendIo; "Failed to send IOCTL to tunnel 0x%x"
0x18001ecae  mov     ecx, 800000h
0x18001ecb3  mov     r8d, eax
0x18001ecb6  mov     esi, eax
0x18001ecb8  call    EventWrite0
0x18001ecbd  call    ?StopTunnelDriver@@YAKXZ; StopTunnelDriver(void)
0x18001ecc2  cmp     dword ptr [r14], 0Eh
0x18001ecc6  jnz     short loc_18001ECF3
0x18001ecc8  lea     r8, g_ProtocolStateTeredo
0x18001eccf  mov     [rbp+57h+var_90], 9
0x18001ecd6  lea     rdx, [rbp+57h+var_90]
0x18001ecda  lea     rcx, TeredoSetStartProgressInCompartment
0x18001ece1  call    ForEachCompartment
0x18001ece6  jmp     short loc_18001ECF3
0x18001ece8  xor     edx, edx; unsigned __int8
0x18001ecea  lea     rcx, [r14+4]; struct _GUID *
0x18001ecee  call    ?WaitForNLBindingEvent@@YAXPEBU_GUID@@E@Z; WaitForNLBindingEvent(_GUID const *,uchar)
0x18001ecf3  test    r15, r15
0x18001ecf6  jz      short loc_18001ED07
0x18001ecf8  mov     rcx, r15; hSCObject
0x18001ecfb  call    cs:__imp_CloseServiceHandle
0x18001ed02  nop     dword ptr [rax+rax+00h]
0x18001ed07  test    r12, r12
0x18001ed0a  jz      short loc_18001ED1B
0x18001ed0c  mov     rcx, r12; hSCObject
0x18001ed0f  call    cs:__imp_CloseServiceHandle
0x18001ed16  nop     dword ptr [rax+rax+00h]
0x18001ed1b  test    rbx, rbx
0x18001ed1e  jz      short loc_18001ED2F
0x18001ed20  mov     rcx, rbx; SRWLock
0x18001ed23  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ed2a  nop     dword ptr [rax+rax+00h]
0x18001ed2f  mov     eax, esi
0x18001ed31  mov     rcx, [rbp+57h+var_30]
0x18001ed35  xor     rcx, rsp; StackCookie
0x18001ed38  call    __security_check_cookie
0x18001ed3d  lea     r11, [rsp+0D0h+var_20]
0x18001ed45  mov     rbx, [r11+38h]
0x18001ed49  mov     rsi, [r11+40h]
0x18001ed4d  mov     rsp, r11
0x18001ed50  pop     r15
0x18001ed52  pop     r14
0x18001ed54  pop     r13
0x18001ed56  pop     r12
0x18001ed58  pop     rbp
0x18001ed59  retn
```
