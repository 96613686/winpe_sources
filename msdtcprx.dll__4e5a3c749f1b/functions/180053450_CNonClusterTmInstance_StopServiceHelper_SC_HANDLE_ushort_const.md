# CNonClusterTmInstance::StopServiceHelper(SC_HANDLE__ *,ushort const *)

- ea: `0x180053450`
- end: `0x180053569`
- name: `?StopServiceHelper@CNonClusterTmInstance@@AEAAJPEAUSC_HANDLE__@@PEBG@Z`
- size: `281`
- prototype: `int(CNonClusterTmInstance *__hidden this, struct SC_HANDLE__ *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180053570`

## callees

- `0x180053450`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005349b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800534d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005349b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800534d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053527`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005351d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005351d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053544`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053544`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005348d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005348d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800534c6`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800534c6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005350a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005350a`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::StopServiceHelper(
        CNonClusterTmInstance *this,
        SC_HANDLE a2,
        const unsigned __int16 *a3)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  unsigned int i; // edi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v3 = OpenServiceW(a2, a3, 0xF0024u);
  v4 = v3;
  if ( v3 )
  {
    if ( ControlService(v3, 1u, &ServiceStatus)
      || (LastError = GetLastError(), v6 = LastError, LastError == 1062)
      || LastError == 109 )
    {
      for ( i = 0; i < 0x4E20; i += 500 )
      {
        if ( !QueryServiceStatus(v4, &ServiceStatus) )
        {
          LastError = GetLastError();
          v6 = LastError;
          goto LABEL_7;
        }
        if ( ServiceStatus.dwCurrentState == 1 )
          break;
        Sleep(0x1F4u);
      }
      v6 = 0;
      if ( i >= 0x4E20 )
        v6 = -2147467259;
    }
    else
    {
LABEL_7:
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180053450  mov     [rsp+arg_0], rbx
0x180053455  mov     [rsp+arg_18], rsi
0x18005345a  push    rdi
0x18005345b  sub     rsp, 50h
0x18005345f  mov     rax, cs:__security_cookie
0x180053466  xor     rax, rsp
0x180053469  mov     [rsp+58h+var_18], rax
0x18005346e  mov     r9, r8
0x180053471  mov     rax, rdx
0x180053474  xorps   xmm0, xmm0
0x180053477  mov     rdx, r9; lpServiceName
0x18005347a  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18005347f  mov     rcx, rax; hSCManager
0x180053482  mov     r8d, 0F0024h; dwDesiredAccess
0x180053488  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18005348d  call    cs:__imp_OpenServiceW
0x180053493  mov     rsi, rax
0x180053496  test    rax, rax
0x180053499  jnz     short loc_1800534B9
0x18005349b  call    cs:__imp_GetLastError
0x1800534a1  mov     ebx, eax
0x1800534a3  test    eax, eax
0x1800534a5  jle     loc_18005354A
0x1800534ab  movzx   ebx, ax
0x1800534ae  or      ebx, 80070000h
0x1800534b4  jmp     loc_18005354A
0x1800534b9  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1800534be  mov     edx, 1; dwControl
0x1800534c3  mov     rcx, rsi; hService
0x1800534c6  call    cs:__imp_ControlService
0x1800534cc  test    eax, eax
0x1800534ce  jnz     short loc_1800534F3
0x1800534d0  call    cs:__imp_GetLastError
0x1800534d6  mov     ebx, eax
0x1800534d8  cmp     eax, 426h
0x1800534dd  jz      short loc_1800534F3
0x1800534df  cmp     eax, 6Dh ; 'm'
0x1800534e2  jz      short loc_1800534F3
0x1800534e4  test    eax, eax
0x1800534e6  jle     short loc_180053541
0x1800534e8  movzx   ebx, ax
0x1800534eb  or      ebx, 80070000h
0x1800534f1  jmp     short loc_180053541
0x1800534f3  xor     edi, edi
0x1800534f5  mov     ebx, 1F4h
0x1800534fa  cmp     edi, 4E20h
0x180053500  jnb     short loc_180053531
0x180053502  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180053507  mov     rcx, rsi; hService
0x18005350a  call    cs:__imp_QueryServiceStatus
0x180053510  test    eax, eax
0x180053512  jz      short loc_180053527
0x180053514  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 1
0x180053519  jz      short loc_180053531
0x18005351b  mov     ecx, ebx; dwMilliseconds
0x18005351d  call    cs:__imp_Sleep
0x180053523  add     edi, ebx
0x180053525  jmp     short loc_1800534FA
0x180053527  call    cs:__imp_GetLastError
0x18005352d  mov     ebx, eax
0x18005352f  jmp     short loc_1800534E4
0x180053531  xor     ebx, ebx
0x180053533  mov     eax, 80004005h
0x180053538  cmp     edi, 4E20h
0x18005353e  cmovnb  ebx, eax
0x180053541  mov     rcx, rsi; hSCObject
0x180053544  call    cs:__imp_CloseServiceHandle
0x18005354a  mov     eax, ebx
0x18005354c  mov     rcx, [rsp+58h+var_18]
0x180053551  xor     rcx, rsp; StackCookie
0x180053554  call    __security_check_cookie
0x180053559  mov     rbx, [rsp+58h+arg_0]
0x18005355e  mov     rsi, [rsp+58h+arg_18]
0x180053563  add     rsp, 50h
0x180053567  pop     rdi
0x180053568  retn
```
