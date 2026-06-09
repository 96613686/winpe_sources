# CDetectionAndSharing::StartServiceW(ushort const *)

- ea: `0x18000388c`
- end: `0x180003a90`
- name: `?StartServiceW@CDetectionAndSharing@@AEAAJPEBG@Z`
- size: `516`
- prototype: `int __fastcall(SC_HANDLE *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180002b64`

## callees

- `0x18000388c`
- `0x180004920`

## import_xrefs

- `ADVAPI32!ChangeServiceConfigW` at `0x18000399c`
- `ADVAPI32!ChangeServiceConfigW` at `0x18000399c`
- `ADVAPI32!StartServiceW` at `0x18000395b`
- `ADVAPI32!StartServiceW` at `0x180003a0c`
- `ADVAPI32!StartServiceW` at `0x18000395b`
- `ADVAPI32!StartServiceW` at `0x180003a0c`
- `ADVAPI32!ControlService` at `0x180003936`
- `ADVAPI32!ControlService` at `0x1800039e4`
- `ADVAPI32!ControlService` at `0x180003936`
- `ADVAPI32!ControlService` at `0x1800039e4`
- `ADVAPI32!OpenServiceW` at `0x180003901`
- `ADVAPI32!OpenServiceW` at `0x180003901`
- `ADVAPI32!CloseServiceHandle` at `0x180003a4d`
- `ADVAPI32!CloseServiceHandle` at `0x180003a56`
- `ADVAPI32!CloseServiceHandle` at `0x180003a4d`
- `ADVAPI32!CloseServiceHandle` at `0x180003a56`
- `ADVAPI32!OpenSCManagerW` at `0x1800038cb`
- `ADVAPI32!OpenSCManagerW` at `0x1800038cb`
- `KERNEL32!GetLastError` at `0x1800038d9`
- `KERNEL32!GetLastError` at `0x18000390f`
- `KERNEL32!GetLastError` at `0x180003940`
- `KERNEL32!GetLastError` at `0x180003a16`
- `KERNEL32!GetLastError` at `0x1800038d9`
- `KERNEL32!GetLastError` at `0x18000390f`
- `KERNEL32!GetLastError` at `0x180003940`
- `KERNEL32!GetLastError` at `0x180003a16`
- `KERNEL32!Sleep` at `0x1800039fe`
- `KERNEL32!Sleep` at `0x180003a36`
- `KERNEL32!Sleep` at `0x1800039fe`
- `KERNEL32!Sleep` at `0x180003a36`

## pseudocode

```c
int __fastcall CDetectionAndSharing::StartServiceW(SC_HANDLE *this, const unsigned __int16 *a2)
{
  SC_HANDLE v4; // rsi
  int result; // eax
  SC_HANDLE v6; // rdi
  signed int LastError; // ebx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = OpenSCManagerW(0, 0, 1u);
  if ( !v4 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = OpenServiceW(this[8], a2, 0xD2u);
  if ( !v6 )
  {
    LastError = GetLastError();
    goto LABEL_32;
  }
LABEL_6:
  LastError = 0;
  while ( ServiceStatus.dwCurrentState != 4 )
  {
    if ( ControlService(v6, 4u, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState != 1 )
      {
        if ( ServiceStatus.dwCurrentState == 2 )
        {
          if ( ServiceStatus.dwWaitHint - 1 > 0x752E )
            LastError = -2147467260;
          else
            Sleep(ServiceStatus.dwWaitHint);
          goto LABEL_25;
        }
        if ( ServiceStatus.dwCurrentState != 3 )
        {
          if ( ServiceStatus.dwCurrentState == 4 )
            goto LABEL_6;
          if ( ServiceStatus.dwCurrentState != 5 && ServiceStatus.dwCurrentState - 6 > 1
            || ControlService(v6, 3u, &ServiceStatus) )
          {
            goto LABEL_25;
          }
          goto LABEL_24;
        }
        if ( ServiceStatus.dwWaitHint - 1 <= 0x752E )
          Sleep(ServiceStatus.dwWaitHint);
      }
      if ( StartServiceW(v6, 0, 0) )
      {
        LastError = -2147467260;
        break;
      }
LABEL_24:
      LastError = GetLastError();
      goto LABEL_25;
    }
    LastError = GetLastError();
    if ( LastError == 1062 )
    {
      if ( !StartServiceW(v6, 0, 0) )
        goto LABEL_24;
      LastError = 0;
      if ( !ChangeServiceConfigW(v6, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
        goto LABEL_24;
    }
    else
    {
LABEL_25:
      if ( LastError )
        break;
    }
  }
  CloseServiceHandle(v6);
LABEL_32:
  CloseServiceHandle(v4);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18000388c  mov     [rsp+arg_10], rbx
0x180003891  mov     [rsp+arg_18], rsi
0x180003896  push    rdi
0x180003897  sub     rsp, 90h
0x18000389e  mov     rax, cs:__security_cookie
0x1800038a5  xor     rax, rsp
0x1800038a8  mov     [rsp+98h+var_18], rax
0x1800038b0  xorps   xmm0, xmm0
0x1800038b3  mov     rdi, rdx
0x1800038b6  xor     edx, edx; lpDatabaseName
0x1800038b8  mov     rbx, rcx
0x1800038bb  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x1800038c0  xor     ecx, ecx; lpMachineName
0x1800038c2  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800038c7  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800038cb  call    cs:__imp_OpenSCManagerW
0x1800038d1  mov     rsi, rax
0x1800038d4  test    rax, rax
0x1800038d7  jnz     short loc_1800038F4
0x1800038d9  call    cs:__imp_GetLastError
0x1800038df  test    eax, eax
0x1800038e1  jle     loc_180003A6B
0x1800038e7  movzx   eax, ax
0x1800038ea  or      eax, 80070000h
0x1800038ef  jmp     loc_180003A6B
0x1800038f4  mov     rcx, [rbx+40h]; hSCManager
0x1800038f8  mov     r8d, 0D2h; dwDesiredAccess
0x1800038fe  mov     rdx, rdi; lpServiceName
0x180003901  call    cs:__imp_OpenServiceW
0x180003907  mov     rdi, rax
0x18000390a  test    rax, rax
0x18000390d  jnz     short loc_18000391C
0x18000390f  call    cs:__imp_GetLastError
0x180003915  mov     ebx, eax
0x180003917  jmp     loc_180003A53
0x18000391c  xor     ebx, ebx
0x18000391e  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 4
0x180003923  jz      loc_180003A4A
0x180003929  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x18000392e  mov     edx, 4; dwControl
0x180003933  mov     rcx, rdi; hService
0x180003936  call    cs:__imp_ControlService
0x18000393c  test    eax, eax
0x18000393e  jnz     short loc_1800039AC
0x180003940  call    cs:__imp_GetLastError
0x180003946  mov     ebx, eax
0x180003948  cmp     eax, 426h
0x18000394d  jnz     loc_180003A1E
0x180003953  xor     r8d, r8d; lpServiceArgVectors
0x180003956  xor     edx, edx; dwNumServiceArgs
0x180003958  mov     rcx, rdi; hService
0x18000395b  call    cs:__imp_StartServiceW
0x180003961  test    eax, eax
0x180003963  jz      loc_180003A16
0x180003969  xor     ebx, ebx
0x18000396b  or      r9d, 0FFFFFFFFh; dwErrorControl
0x18000396f  mov     [rsp+98h+lpDisplayName], rbx; lpDisplayName
0x180003974  or      edx, r9d; dwServiceType
0x180003977  mov     [rsp+98h+lpPassword], rbx; lpPassword
0x18000397c  mov     rcx, rdi; hService
0x18000397f  mov     [rsp+98h+lpServiceStartName], rbx; lpServiceStartName
0x180003984  mov     [rsp+98h+lpDependencies], rbx; lpDependencies
0x180003989  lea     r8d, [rbx+2]; dwStartType
0x18000398d  mov     [rsp+98h+lpdwTagId], rbx; lpdwTagId
0x180003992  mov     [rsp+98h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x180003997  mov     [rsp+98h+lpBinaryPathName], rbx; lpBinaryPathName
0x18000399c  call    cs:__imp_ChangeServiceConfigW
0x1800039a2  test    eax, eax
0x1800039a4  jnz     loc_18000391E
0x1800039aa  jmp     short loc_180003A16
0x1800039ac  mov     eax, [rsp+98h+ServiceStatus.dwCurrentState]
0x1800039b0  sub     eax, 1
0x1800039b3  jz      short loc_180003A04
0x1800039b5  sub     eax, 1
0x1800039b8  jz      short loc_180003A28
0x1800039ba  sub     eax, 1
0x1800039bd  jz      short loc_1800039F0
0x1800039bf  sub     eax, 1
0x1800039c2  jz      loc_18000391C
0x1800039c8  sub     eax, 1
0x1800039cb  jz      short loc_1800039D7
0x1800039cd  sub     eax, 1
0x1800039d0  jz      short loc_1800039D7
0x1800039d2  cmp     eax, 1
0x1800039d5  jnz     short loc_180003A1E
0x1800039d7  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1800039dc  mov     edx, 3; dwControl
0x1800039e1  mov     rcx, rdi; hService
0x1800039e4  call    cs:__imp_ControlService
0x1800039ea  test    eax, eax
0x1800039ec  jnz     short loc_180003A1E
0x1800039ee  jmp     short loc_180003A16
0x1800039f0  mov     ecx, [rsp+98h+ServiceStatus.dwWaitHint]; dwMilliseconds
0x1800039f4  lea     eax, [rcx-1]
0x1800039f7  cmp     eax, 752Eh
0x1800039fc  ja      short loc_180003A04
0x1800039fe  call    cs:__imp_Sleep
0x180003a04  xor     r8d, r8d; lpServiceArgVectors
0x180003a07  xor     edx, edx; dwNumServiceArgs
0x180003a09  mov     rcx, rdi; hService
0x180003a0c  call    cs:__imp_StartServiceW
0x180003a12  test    eax, eax
0x180003a14  jnz     short loc_180003A45
0x180003a16  call    cs:__imp_GetLastError
0x180003a1c  mov     ebx, eax
0x180003a1e  test    ebx, ebx
0x180003a20  jz      loc_18000391E
0x180003a26  jmp     short loc_180003A4A
0x180003a28  mov     ecx, [rsp+98h+ServiceStatus.dwWaitHint]; dwMilliseconds
0x180003a2c  lea     eax, [rcx-1]
0x180003a2f  cmp     eax, 752Eh
0x180003a34  ja      short loc_180003A3E
0x180003a36  call    cs:__imp_Sleep
0x180003a3c  jmp     short loc_180003A1E
0x180003a3e  mov     ebx, 80004004h
0x180003a43  jmp     short loc_180003A1E
0x180003a45  mov     ebx, 80004004h
0x180003a4a  mov     rcx, rdi; hSCObject
0x180003a4d  call    cs:__imp_CloseServiceHandle
0x180003a53  mov     rcx, rsi; hSCObject
0x180003a56  call    cs:__imp_CloseServiceHandle
0x180003a5c  test    ebx, ebx
0x180003a5e  jle     short loc_180003A69
0x180003a60  movzx   ebx, bx
0x180003a63  or      ebx, 80070000h
0x180003a69  mov     eax, ebx
0x180003a6b  mov     rcx, [rsp+98h+var_18]
0x180003a73  xor     rcx, rsp; StackCookie
0x180003a76  call    __security_check_cookie
0x180003a7b  lea     r11, [rsp+98h+var_8]
0x180003a83  mov     rbx, [r11+20h]
0x180003a87  mov     rsi, [r11+28h]
0x180003a8b  mov     rsp, r11
0x180003a8e  pop     rdi
0x180003a8f  retn
```
