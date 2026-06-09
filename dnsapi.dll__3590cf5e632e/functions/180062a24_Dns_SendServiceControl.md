# Dns_SendServiceControl

- ea: `0x180062a24`
- end: `0x180062be8`
- name: `Dns_SendServiceControl`
- size: `452`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180062990`

## callees

- `0x180062a24`
- `0x18008b5f0`
- `0x1800cd504`
- `0x1800cee80`
- `0x1800dbc44`
- `0x1800dc9e0`
- `0x1800dfcac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062bba`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180062ae3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180062af7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180062ae3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180062af7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180062a68`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180062a68`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180062a85`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180062a85`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180062aa7`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180062aa7`

## pseudocode

```c
__int64 __fastcall Dns_SendServiceControl(LPCWSTR lpServiceName)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  DWORD v6; // edi
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  DWORD LastError; // eax
  char v12; // al
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  DWORD v16; // eax
  int v17; // [rsp+20h] [rbp-78h]
  int v18; // [rsp+28h] [rbp-70h]
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( SBYTE3(xmmword_1801119E0) < 0 )
    WPP_SF_SDD(1055, 19, (unsigned int)WPP_e274dd36ec403988c5b9a752a755d740_Traceguids, (_DWORD)lpServiceName, 64, 6);
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    v5 = 0;
    if ( SBYTE3(xmmword_1801119E0) < 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(1055, 20, WPP_e274dd36ec403988c5b9a752a755d740_Traceguids, LastError);
    }
LABEL_9:
    v6 = GetLastError();
    if ( !v5 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v4 = OpenServiceW(v2, lpServiceName, 0x40u);
  v5 = v4;
  if ( !v4 )
  {
    if ( SBYTE3(xmmword_1801119E0) < 0 )
    {
      v12 = GetLastError();
      WPP_SF_SDd(v14, v13, v15, (_DWORD)lpServiceName, v17, v12);
    }
    goto LABEL_9;
  }
  if ( !ControlService(v4, 6u, &ServiceStatus) )
  {
    if ( SBYTE3(xmmword_1801119E0) < 0 )
    {
      v16 = GetLastError();
      WPP_SF_Dd(1055, 22, WPP_e274dd36ec403988c5b9a752a755d740_Traceguids, 6, v16);
    }
    goto LABEL_9;
  }
  v6 = 0;
LABEL_10:
  CloseServiceHandle(v5);
LABEL_11:
  if ( v3 )
    CloseServiceHandle(v3);
  if ( SBYTE3(xmmword_1801119E0) < 0 )
    WPP_SF_SDDd(v8, v7, v9, (_DWORD)lpServiceName, v17, v18, v6);
  return v6;
}

```

## disassembly

```asm
0x180062a24  push    rbx
0x180062a26  push    rbp
0x180062a27  push    rsi
0x180062a28  push    rdi
0x180062a29  sub     rsp, 78h
0x180062a2d  mov     rax, cs:__security_cookie
0x180062a34  xor     rax, rsp
0x180062a37  mov     [rsp+98h+var_38], rax
0x180062a3c  xorps   xmm0, xmm0
0x180062a3f  mov     rbp, rcx
0x180062a42  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x180062a47  xor     eax, eax
0x180062a49  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x180062a4e  cmp     byte ptr cs:xmmword_1801119E0+3, al
0x180062a54  lea     edi, [rax+6]
0x180062a57  lea     ebx, [rax+40h]
0x180062a5a  jl      loc_180062B33
0x180062a60  xor     edx, edx; lpDatabaseName
0x180062a62  xor     ecx, ecx; lpMachineName
0x180062a64  lea     r8d, [rdx+1]; dwDesiredAccess
0x180062a68  call    cs:__imp_OpenSCManagerW
0x180062a6f  nop     dword ptr [rax+rax+00h]
0x180062a74  mov     rsi, rax
0x180062a77  test    rax, rax
0x180062a7a  jz      short loc_180062ABF
0x180062a7c  mov     r8d, ebx; dwDesiredAccess
0x180062a7f  mov     rdx, rbp; lpServiceName
0x180062a82  mov     rcx, rax; hSCManager
0x180062a85  call    cs:__imp_OpenServiceW
0x180062a8c  nop     dword ptr [rax+rax+00h]
0x180062a91  mov     rbx, rax
0x180062a94  test    rax, rax
0x180062a97  jz      loc_180062B83
0x180062a9d  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x180062aa2  mov     edx, edi; dwControl
0x180062aa4  mov     rcx, rax; hService
0x180062aa7  call    cs:__imp_ControlService
0x180062aae  nop     dword ptr [rax+rax+00h]
0x180062ab3  test    eax, eax
0x180062ab5  jz      loc_180062BAD
0x180062abb  xor     edi, edi
0x180062abd  jmp     short loc_180062AE0
0x180062abf  xor     ebx, ebx
0x180062ac1  cmp     byte ptr cs:xmmword_1801119E0+3, bl
0x180062ac7  jl      loc_180062B59
0x180062acd  call    cs:__imp_GetLastError
0x180062ad4  nop     dword ptr [rax+rax+00h]
0x180062ad9  mov     edi, eax
0x180062adb  test    rbx, rbx
0x180062ade  jz      short loc_180062AEF
0x180062ae0  mov     rcx, rbx; hSCObject
0x180062ae3  call    cs:__imp_CloseServiceHandle
0x180062aea  nop     dword ptr [rax+rax+00h]
0x180062aef  test    rsi, rsi
0x180062af2  jz      short loc_180062B03
0x180062af4  mov     rcx, rsi; hSCObject
0x180062af7  call    cs:__imp_CloseServiceHandle
0x180062afe  nop     dword ptr [rax+rax+00h]
0x180062b03  cmp     byte ptr cs:xmmword_1801119E0+3, 0
0x180062b0a  jl      short loc_180062B25
0x180062b0c  mov     eax, edi
0x180062b0e  mov     rcx, [rsp+98h+var_38]
0x180062b13  xor     rcx, rsp; StackCookie
0x180062b16  call    __security_check_cookie
0x180062b1b  add     rsp, 78h
0x180062b1f  pop     rdi
0x180062b20  pop     rsi
0x180062b21  pop     rbp
0x180062b22  pop     rbx
0x180062b23  retn
0x180062b25  mov     r9, rbp
0x180062b28  mov     [rsp+98h+var_68], edi
0x180062b2c  call    WPP_SF_SDDd
0x180062b31  jmp     short loc_180062B0C
0x180062b33  mov     edx, 13h
0x180062b38  mov     [rsp+98h+var_70], edi
0x180062b3c  mov     ecx, 41Fh
0x180062b41  mov     [rsp+98h+var_78], ebx
0x180062b45  mov     r9, rbp
0x180062b48  lea     r8, WPP_e274dd36ec403988c5b9a752a755d740_Traceguids
0x180062b4f  call    WPP_SF_SDD
0x180062b54  jmp     loc_180062A60
0x180062b59  call    cs:__imp_GetLastError
0x180062b60  nop     dword ptr [rax+rax+00h]
0x180062b65  mov     edx, 14h
0x180062b6a  lea     r8, WPP_e274dd36ec403988c5b9a752a755d740_Traceguids
0x180062b71  mov     r9d, eax
0x180062b74  mov     ecx, 41Fh
0x180062b79  call    WPP_SF_d
0x180062b7e  jmp     loc_180062ACD
0x180062b83  cmp     byte ptr cs:xmmword_1801119E0+3, 0
0x180062b8a  jge     loc_180062ACD
0x180062b90  call    cs:__imp_GetLastError
0x180062b97  nop     dword ptr [rax+rax+00h]
0x180062b9c  mov     r9, rbp
0x180062b9f  mov     [rsp+98h+var_70], eax
0x180062ba3  call    WPP_SF_SDd
0x180062ba8  jmp     loc_180062ACD
0x180062bad  cmp     byte ptr cs:xmmword_1801119E0+3, 0
0x180062bb4  jge     loc_180062ACD
0x180062bba  call    cs:__imp_GetLastError
0x180062bc1  nop     dword ptr [rax+rax+00h]
0x180062bc6  mov     edx, 16h
0x180062bcb  lea     r8, WPP_e274dd36ec403988c5b9a752a755d740_Traceguids
0x180062bd2  mov     ecx, 41Fh
0x180062bd7  mov     [rsp+98h+var_78], eax
0x180062bdb  mov     r9d, edi
0x180062bde  call    WPP_SF_Dd
0x180062be3  jmp     loc_180062ACD
```
