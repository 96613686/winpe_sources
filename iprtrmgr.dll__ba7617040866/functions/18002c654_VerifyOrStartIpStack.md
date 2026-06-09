# VerifyOrStartIpStack

- ea: `0x18002c654`
- end: `0x18002c7d8`
- name: `VerifyOrStartIpStack`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a9b0`

## callees

- `0x18000ac60`
- `0x18002c654`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c714`
- `KERNEL32!GetLastError` at `0x18002c714`
- `ADVAPI32!OpenSCManagerA` at `0x18002c701`
- `ADVAPI32!OpenSCManagerA` at `0x18002c701`
- `ADVAPI32!CloseServiceHandle` at `0x18002c79d`
- `ADVAPI32!CloseServiceHandle` at `0x18002c7ab`
- `ADVAPI32!CloseServiceHandle` at `0x180058b4e`
- `ADVAPI32!CloseServiceHandle` at `0x180058b5e`
- `ADVAPI32!CloseServiceHandle` at `0x18002c79d`
- `ADVAPI32!CloseServiceHandle` at `0x18002c7ab`
- `ADVAPI32!CloseServiceHandle` at `0x180058b4e`
- `ADVAPI32!CloseServiceHandle` at `0x180058b5e`
- `ADVAPI32!OpenServiceW` at `0x18002c72e`
- `ADVAPI32!OpenServiceW` at `0x18002c72e`
- `ADVAPI32!QueryServiceStatus` at `0x18002c749`
- `ADVAPI32!QueryServiceStatus` at `0x18002c77b`
- `ADVAPI32!QueryServiceStatus` at `0x18002c749`
- `ADVAPI32!QueryServiceStatus` at `0x18002c77b`
- `ADVAPI32!StartServiceA` at `0x18002c769`
- `ADVAPI32!StartServiceA` at `0x18002c769`

## pseudocode

```c
__int64 VerifyOrStartIpStack()
{
  SC_HANDLE v0; // rdi
  DWORD LastError; // ebx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-838h] BYREF
  int v7; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+54h] [rbp-814h] BYREF

  v0 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  LastError = 0;
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString(&v7, L"Entered: %ws", L"VerifyOrStartIpStack");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v7);
  }
  v2 = OpenSCManagerA(0, 0, 0xA0000000);
  v3 = v2;
  if ( !v2 )
    goto LABEL_5;
  v4 = OpenServiceW(v2, L"TcpIp", 0x14u);
  v0 = v4;
  if ( !v4 || !QueryServiceStatus(v4, &ServiceStatus) )
    goto LABEL_5;
  if ( ServiceStatus.dwCurrentState == 4 )
    goto LABEL_15;
  if ( ServiceStatus.dwCurrentState != 1 )
  {
    LastError = 0;
    goto LABEL_15;
  }
  if ( !StartServiceA(v0, 0, 0) || !QueryServiceStatus(v0, &ServiceStatus) )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_15;
  }
  if ( ServiceStatus.dwCurrentState != 4 )
    LastError = 1003;
LABEL_15:
  if ( v3 )
    CloseServiceHandle(v3);
  if ( v0 )
    CloseServiceHandle(v0);
  return LastError;
}

```

## disassembly

```asm
0x18002c654  mov     [rsp+arg_0], rbx
0x18002c659  mov     [rsp+arg_8], rsi
0x18002c65e  push    rdi
0x18002c65f  sub     rsp, 860h
0x18002c666  mov     rax, cs:__security_cookie
0x18002c66d  xor     rax, rsp
0x18002c670  mov     [rsp+868h+var_18], rax
0x18002c678  mov     [rsp+868h+var_848], 0
0x18002c681  xor     edi, edi
0x18002c683  mov     [rsp+868h+var_840], rdi
0x18002c688  xorps   xmm0, xmm0
0x18002c68b  xor     eax, eax
0x18002c68d  movups  xmmword ptr [rsp+868h+ServiceStatus.dwServiceType], xmm0
0x18002c692  movups  xmmword ptr [rsp+868h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002c697  xor     ebx, ebx
0x18002c699  mov     [rsp+868h+var_818], eax
0x18002c69d  xor     edx, edx; Val
0x18002c69f  mov     r8d, 7FCh; Size
0x18002c6a5  lea     rcx, [rsp+868h+var_814]; void *
0x18002c6aa  call    memset_0
0x18002c6af  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002c6b5  jge     short loc_18002C6F7
0x18002c6b7  xor     eax, eax
0x18002c6b9  mov     word ptr [rsp+868h+var_818], ax
0x18002c6be  lea     r8, aVerifyorstarti; "VerifyOrStartIpStack"
0x18002c6c5  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002c6cc  lea     rcx, [rsp+868h+var_818]
0x18002c6d1  call    FormatRRASErrorString
0x18002c6d6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002c6dc  jge     short loc_18002C6F7
0x18002c6de  lea     r8, [rsp+868h+var_818]
0x18002c6e3  lea     rdx, RasRtrmgrTraceInfo
0x18002c6ea  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002c6f1  call    McTemplateU0z_EventWriteTransfer
0x18002c6f6  nop
0x18002c6f7  xor     edx, edx; lpDatabaseName
0x18002c6f9  xor     ecx, ecx; lpMachineName
0x18002c6fb  mov     r8d, 0A0000000h; dwDesiredAccess
0x18002c701  call    cs:__imp_OpenSCManagerA
0x18002c707  mov     rsi, rax
0x18002c70a  mov     [rsp+868h+var_848], rax
0x18002c70f  test    rax, rax
0x18002c712  jnz     short loc_18002C71E
0x18002c714  call    cs:__imp_GetLastError
0x18002c71a  mov     ebx, eax
0x18002c71c  jmp     short loc_18002C795
0x18002c71e  mov     r8d, 14h; dwDesiredAccess
0x18002c724  lea     rdx, ServiceName; "TcpIp"
0x18002c72b  mov     rcx, rsi; hSCManager
0x18002c72e  call    cs:__imp_OpenServiceW
0x18002c734  mov     rdi, rax
0x18002c737  mov     [rsp+868h+var_840], rax
0x18002c73c  test    rax, rax
0x18002c73f  jz      short loc_18002C714
0x18002c741  lea     rdx, [rsp+868h+ServiceStatus]; lpServiceStatus
0x18002c746  mov     rcx, rax; hService
0x18002c749  call    cs:__imp_QueryServiceStatus
0x18002c74f  test    eax, eax
0x18002c751  jz      short loc_18002C714
0x18002c753  cmp     [rsp+868h+ServiceStatus.dwCurrentState], 4
0x18002c758  jz      short loc_18002C795
0x18002c75a  cmp     [rsp+868h+ServiceStatus.dwCurrentState], 1
0x18002c75f  jnz     short loc_18002C793
0x18002c761  xor     r8d, r8d; lpServiceArgVectors
0x18002c764  xor     edx, edx; dwNumServiceArgs
0x18002c766  mov     rcx, rdi; hService
0x18002c769  call    cs:__imp_StartServiceA
0x18002c76f  test    eax, eax
0x18002c771  jz      short loc_18002C714
0x18002c773  lea     rdx, [rsp+868h+ServiceStatus]; lpServiceStatus
0x18002c778  mov     rcx, rdi; hService
0x18002c77b  call    cs:__imp_QueryServiceStatus
0x18002c781  test    eax, eax
0x18002c783  jz      short loc_18002C714
0x18002c785  cmp     [rsp+868h+ServiceStatus.dwCurrentState], 4
0x18002c78a  jz      short loc_18002C795
0x18002c78c  mov     ebx, 3EBh
0x18002c791  jmp     short loc_18002C795
0x18002c793  xor     ebx, ebx
0x18002c795  test    rsi, rsi
0x18002c798  jz      short loc_18002C7A3
0x18002c79a  mov     rcx, rsi; hSCObject
0x18002c79d  call    cs:__imp_CloseServiceHandle
0x18002c7a3  test    rdi, rdi
0x18002c7a6  jz      short loc_18002C7B1
0x18002c7a8  mov     rcx, rdi; hSCObject
0x18002c7ab  call    cs:__imp_CloseServiceHandle
0x18002c7b1  mov     eax, ebx
0x18002c7b3  mov     rcx, [rsp+868h+var_18]
0x18002c7bb  xor     rcx, rsp; StackCookie
0x18002c7be  call    __security_check_cookie
0x18002c7c3  lea     r11, [rsp+868h+var_8]
0x18002c7cb  mov     rbx, [r11+10h]
0x18002c7cf  mov     rsi, [r11+18h]
0x18002c7d3  mov     rsp, r11
0x18002c7d6  pop     rdi
0x18002c7d7  retn
0x180058b3c  push    rbp
0x180058b3e  sub     rsp, 20h
0x180058b42  mov     rbp, rdx
0x180058b45  mov     rcx, [rbp+20h]; hSCObject
0x180058b49  test    rcx, rcx
0x180058b4c  jz      short loc_180058B55
0x180058b4e  call    cs:__imp_CloseServiceHandle
0x180058b54  nop
0x180058b55  mov     rcx, [rbp+28h]; hSCObject
0x180058b59  test    rcx, rcx
0x180058b5c  jz      short loc_180058B65
0x180058b5e  call    cs:__imp_CloseServiceHandle
0x180058b64  nop
0x180058b65  add     rsp, 20h
0x180058b69  pop     rbp
0x180058b6a  retn
```
