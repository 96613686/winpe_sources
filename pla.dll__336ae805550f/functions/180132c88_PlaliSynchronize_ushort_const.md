# PlaliSynchronize(ushort const *)

- ea: `0x180132c88`
- end: `0x180132e31`
- name: `?PlaliSynchronize@@YAJPEBG@Z`
- size: `425`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800b16b0`
- `0x18012ec18`
- `0x18012edd0`
- `0x1801326c0`
- `0x180132960`

## callees

- `0x180130e30`
- `0x180132c88`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180132df4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180132d25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180132d7e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180132dc0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180132d25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180132d7e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180132dc0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180132dd9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180132dec`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180132dd9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180132dec`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180132ce4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180132ce4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180132d06`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180132d06`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180132d97`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180132d97`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180132d37`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180132d37`

## pseudocode

```c
__int64 __fastcall PlaliSynchronize(const unsigned __int16 *a1)
{
  unsigned int ServiceState; // eax
  unsigned int dwCurrentState; // ebx
  DWORD LastError; // edi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r13
  SC_HANDLE v7; // rsi
  int v8; // r14d
  int v9; // r12d
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v13; // [rsp+20h] [rbp-38h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-30h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v13 = 0;
  ServiceState = PlaliGetServiceState(a1, &v13);
  dwCurrentState = v13;
  LastError = ServiceState;
  if ( !ServiceState && v13 && (v5 = OpenSCManagerW(a1, 0, 1u), (v6 = v5) != 0) )
  {
    v7 = OpenServiceW(v5, L"SysmonLog", 0x110u);
    if ( v7 )
    {
      if ( dwCurrentState == 1 )
        goto LABEL_9;
      if ( dwCurrentState != 3 )
      {
        Sleep(0x64u);
        ControlService(v7, 0x80u, &ServiceStatus);
        dwCurrentState = ServiceStatus.dwCurrentState;
        v13 = ServiceStatus.dwCurrentState;
      }
      if ( ((dwCurrentState - 1) & 0xFFFFFFFD) == 0 )
      {
LABEL_9:
        v8 = 24;
        if ( dwCurrentState == 3 )
        {
          v9 = 24;
          while ( !LastError )
          {
            v10 = PlaliGetServiceState(a1, &v13);
            dwCurrentState = v13;
            LastError = v10;
            if ( v13 == 3 )
            {
              Sleep(0xC8u);
              if ( --v9 )
                continue;
            }
            goto LABEL_14;
          }
        }
        else
        {
LABEL_14:
          if ( dwCurrentState == 1 )
          {
            if ( StartServiceW(v7, 0, 0) )
            {
              do
              {
                if ( LastError )
                  break;
                v11 = PlaliGetServiceState(a1, &v13);
                dwCurrentState = v13;
                LastError = v11;
                if ( v13 != 2 )
                  break;
                Sleep(0xC8u);
                --v8;
              }
              while ( v8 );
            }
            else
            {
              LastError = GetLastError();
            }
          }
        }
      }
      CloseServiceHandle(v7);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v6);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( dwCurrentState )
    return LastError != 0 ? 0xC0000BF1 : 0;
  else
    return 3221228529LL;
}

```

## disassembly

```asm
0x180132c88  push    rbp
0x180132c8a  push    rbx
0x180132c8b  push    rsi
0x180132c8c  push    rdi
0x180132c8d  push    r12
0x180132c8f  push    r13
0x180132c91  push    r14
0x180132c93  push    r15
0x180132c95  mov     rbp, rsp
0x180132c98  sub     rsp, 58h
0x180132c9c  mov     rax, cs:__security_cookie
0x180132ca3  xor     rax, rsp
0x180132ca6  mov     [rbp+var_10], rax
0x180132caa  xorps   xmm0, xmm0
0x180132cad  lea     rdx, [rbp+var_38]; unsigned int *
0x180132cb1  xor     eax, eax
0x180132cb3  mov     r15, rcx
0x180132cb6  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180132cba  mov     [rbp+var_38], eax
0x180132cbd  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180132cc1  call    ?PlaliGetServiceState@@YAKPEBGPEAK@Z; PlaliGetServiceState(ushort const *,ulong *)
0x180132cc6  mov     ebx, [rbp+var_38]
0x180132cc9  mov     edi, eax
0x180132ccb  test    eax, eax
0x180132ccd  jnz     loc_180132DF4
0x180132cd3  test    ebx, ebx
0x180132cd5  jz      loc_180132DF4
0x180132cdb  xor     edx, edx; lpDatabaseName
0x180132cdd  lea     r8d, [rax+1]; dwDesiredAccess
0x180132ce1  mov     rcx, r15; lpMachineName
0x180132ce4  call    cs:__imp_OpenSCManagerW
0x180132cea  mov     r13, rax
0x180132ced  test    rax, rax
0x180132cf0  jz      loc_180132DF4
0x180132cf6  mov     r8d, 110h; dwDesiredAccess
0x180132cfc  lea     rdx, aSysmonlog_0; "SysmonLog"
0x180132d03  mov     rcx, rax; hSCManager
0x180132d06  call    cs:__imp_OpenServiceW
0x180132d0c  mov     rsi, rax
0x180132d0f  test    rax, rax
0x180132d12  jz      loc_180132DE1
0x180132d18  cmp     ebx, 1
0x180132d1b  jz      short loc_180132D51
0x180132d1d  cmp     ebx, 3
0x180132d20  jz      short loc_180132D43
0x180132d22  lea     ecx, [rdi+64h]; dwMilliseconds
0x180132d25  call    cs:__imp_Sleep
0x180132d2b  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x180132d2f  mov     edx, 80h; dwControl
0x180132d34  mov     rcx, rsi; hService
0x180132d37  call    cs:__imp_ControlService
0x180132d3d  mov     ebx, [rbp+ServiceStatus.dwCurrentState]
0x180132d40  mov     [rbp+var_38], ebx
0x180132d43  lea     eax, [rbx-1]
0x180132d46  test    eax, 0FFFFFFFDh
0x180132d4b  jnz     loc_180132DD6
0x180132d51  mov     r14d, 18h
0x180132d57  cmp     ebx, 3
0x180132d5a  jnz     short loc_180132D8A
0x180132d5c  mov     r12d, r14d
0x180132d5f  test    edi, edi
0x180132d61  jnz     short loc_180132DD6
0x180132d63  lea     rdx, [rbp+var_38]; unsigned int *
0x180132d67  mov     rcx, r15; unsigned __int16 *
0x180132d6a  call    ?PlaliGetServiceState@@YAKPEBGPEAK@Z; PlaliGetServiceState(ushort const *,ulong *)
0x180132d6f  mov     ebx, [rbp+var_38]
0x180132d72  mov     edi, eax
0x180132d74  cmp     ebx, 3
0x180132d77  jnz     short loc_180132D8A
0x180132d79  mov     ecx, 0C8h; dwMilliseconds
0x180132d7e  call    cs:__imp_Sleep
0x180132d84  add     r12d, 0FFFFFFFFh
0x180132d88  jnz     short loc_180132D5F
0x180132d8a  cmp     ebx, 1
0x180132d8d  jnz     short loc_180132DD6
0x180132d8f  xor     r8d, r8d; lpServiceArgVectors
0x180132d92  xor     edx, edx; dwNumServiceArgs
0x180132d94  mov     rcx, rsi; hService
0x180132d97  call    cs:__imp_StartServiceW
0x180132d9d  test    eax, eax
0x180132d9f  jz      short loc_180132DCE
0x180132da1  test    edi, edi
0x180132da3  jnz     short loc_180132DD6
0x180132da5  lea     rdx, [rbp+var_38]; unsigned int *
0x180132da9  mov     rcx, r15; unsigned __int16 *
0x180132dac  call    ?PlaliGetServiceState@@YAKPEBGPEAK@Z; PlaliGetServiceState(ushort const *,ulong *)
0x180132db1  mov     ebx, [rbp+var_38]
0x180132db4  mov     edi, eax
0x180132db6  cmp     ebx, 2
0x180132db9  jnz     short loc_180132DD6
0x180132dbb  mov     ecx, 0C8h; dwMilliseconds
0x180132dc0  call    cs:__imp_Sleep
0x180132dc6  add     r14d, 0FFFFFFFFh
0x180132dca  jnz     short loc_180132DA1
0x180132dcc  jmp     short loc_180132DD6
0x180132dce  call    cs:__imp_GetLastError
0x180132dd4  mov     edi, eax
0x180132dd6  mov     rcx, rsi; hSCObject
0x180132dd9  call    cs:__imp_CloseServiceHandle
0x180132ddf  jmp     short loc_180132DE9
0x180132de1  call    cs:__imp_GetLastError
0x180132de7  mov     edi, eax
0x180132de9  mov     rcx, r13; hSCObject
0x180132dec  call    cs:__imp_CloseServiceHandle
0x180132df2  jmp     short loc_180132DFC
0x180132df4  call    cs:__imp_GetLastError
0x180132dfa  mov     edi, eax
0x180132dfc  test    ebx, ebx
0x180132dfe  jz      short loc_180132E0F
0x180132e00  xor     eax, eax
0x180132e02  sub     eax, edi
0x180132e04  neg     eax
0x180132e06  sbb     eax, eax
0x180132e08  and     eax, 0C0000BF1h
0x180132e0d  jmp     short loc_180132E14
0x180132e0f  mov     eax, 0C0000BF1h
0x180132e14  mov     rcx, [rbp+var_10]
0x180132e18  xor     rcx, rsp; StackCookie
0x180132e1b  call    __security_check_cookie
0x180132e20  add     rsp, 58h
0x180132e24  pop     r15
0x180132e26  pop     r14
0x180132e28  pop     r13
0x180132e2a  pop     r12
0x180132e2c  pop     rdi
0x180132e2d  pop     rsi
0x180132e2e  pop     rbx
0x180132e2f  pop     rbp
0x180132e30  retn
```
