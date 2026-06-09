# CCatalogServer::StopService(__MIDL___MIDL_itf_catsrv_0000_0004_0001)

- ea: `0x18001eae0`
- end: `0x18001ec16`
- name: `?StopService@CCatalogServer@@UEAAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001e744`
- `0x18001eae0`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebbb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ebdc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ebea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ebdc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ebea`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001eb47`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001eb47`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001eb6b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001eb6b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001eb8d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001ebb1`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001eb8d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001ebb1`

## pseudocode

```c
__int64 __fastcall CCatalogServer::StopService(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  signed int LoadBalancingIfNeeded; // ebx
  const WCHAR *v4; // rdi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  signed int LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = (int)a2;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a2 != 1 )
    return 2147942487LL;
  LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(a2);
  if ( LoadBalancingIfNeeded >= 0 )
  {
    v4 = (&csServices)[10 * v2 - 5];
    v5 = OpenSCManagerW(0, 0, 0xA0000000);
    v6 = v5;
    if ( v5 )
    {
      v7 = OpenServiceW(v5, v4, 0xA0u);
      v8 = v7;
      if ( v7 )
      {
        if ( ControlService(v7, 4u, &ServiceStatus) )
        {
          if ( ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) != 0 && !ControlService(v8, 1u, &ServiceStatus) )
          {
            LastError = GetLastError();
            if ( LastError != 1062 )
            {
              if ( LastError > 0 )
                LoadBalancingIfNeeded = (unsigned __int16)LastError | 0x80070000;
              else
                LoadBalancingIfNeeded = LastError;
            }
          }
        }
      }
      else
      {
        LoadBalancingIfNeeded = -2147418113;
      }
      CloseServiceHandle(v6);
      if ( v8 )
        CloseServiceHandle(v8);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)LoadBalancingIfNeeded;
}

```

## disassembly

```asm
0x18001eae0  mov     [rsp+arg_0], rbx
0x18001eae5  mov     [rsp+arg_10], rsi
0x18001eaea  push    rdi
0x18001eaeb  sub     rsp, 50h
0x18001eaef  mov     rax, cs:__security_cookie
0x18001eaf6  xor     rax, rsp
0x18001eaf9  mov     [rsp+58h+var_18], rax
0x18001eafe  xorps   xmm0, xmm0
0x18001eb01  movsxd  rdi, edx
0x18001eb04  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001eb09  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001eb0e  lea     eax, [rdi-1]
0x18001eb11  test    eax, eax
0x18001eb13  jnz     loc_18001EBF4
0x18001eb19  mov     ecx, edi
0x18001eb1b  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001eb20  mov     ebx, eax
0x18001eb22  test    eax, eax
0x18001eb24  js      loc_18001EBF0
0x18001eb2a  lea     rdx, [rdi+rdi*4]
0x18001eb2e  xor     ecx, ecx; lpMachineName
0x18001eb30  add     rdx, rdx
0x18001eb33  lea     rdi, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001eb3a  mov     r8d, 0A0000000h; dwDesiredAccess
0x18001eb40  mov     rdi, [rdi+rdx*8-50h]
0x18001eb45  xor     edx, edx; lpDatabaseName
0x18001eb47  call    cs:__imp_OpenSCManagerW
0x18001eb4d  mov     rsi, rax
0x18001eb50  test    rax, rax
0x18001eb53  jnz     short loc_18001EB5F
0x18001eb55  mov     ebx, 8000FFFFh
0x18001eb5a  jmp     loc_18001EBF0
0x18001eb5f  mov     r8d, 0A0h; dwDesiredAccess
0x18001eb65  mov     rdx, rdi; lpServiceName
0x18001eb68  mov     rcx, rsi; hSCManager
0x18001eb6b  call    cs:__imp_OpenServiceW
0x18001eb71  mov     rdi, rax
0x18001eb74  test    rax, rax
0x18001eb77  jnz     short loc_18001EB80
0x18001eb79  mov     ebx, 8000FFFFh
0x18001eb7e  jmp     short loc_18001EBD9
0x18001eb80  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001eb85  mov     edx, 4; dwControl
0x18001eb8a  mov     rcx, rdi; hService
0x18001eb8d  call    cs:__imp_ControlService
0x18001eb93  test    eax, eax
0x18001eb95  jz      short loc_18001EBD9
0x18001eb97  mov     eax, [rsp+58h+ServiceStatus.dwCurrentState]
0x18001eb9b  dec     eax
0x18001eb9d  test    eax, 0FFFFFFFDh
0x18001eba2  jz      short loc_18001EBD9
0x18001eba4  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001eba9  mov     edx, 1; dwControl
0x18001ebae  mov     rcx, rdi; hService
0x18001ebb1  call    cs:__imp_ControlService
0x18001ebb7  test    eax, eax
0x18001ebb9  jnz     short loc_18001EBD9
0x18001ebbb  call    cs:__imp_GetLastError
0x18001ebc1  cmp     eax, 426h
0x18001ebc6  jz      short loc_18001EBD9
0x18001ebc8  test    eax, eax
0x18001ebca  jg      short loc_18001EBD0
0x18001ebcc  mov     ebx, eax
0x18001ebce  jmp     short loc_18001EBD9
0x18001ebd0  movzx   ebx, ax
0x18001ebd3  or      ebx, 80070000h
0x18001ebd9  mov     rcx, rsi; hSCObject
0x18001ebdc  call    cs:__imp_CloseServiceHandle
0x18001ebe2  test    rdi, rdi
0x18001ebe5  jz      short loc_18001EBF0
0x18001ebe7  mov     rcx, rdi; hSCObject
0x18001ebea  call    cs:__imp_CloseServiceHandle
0x18001ebf0  mov     eax, ebx
0x18001ebf2  jmp     short loc_18001EBF9
0x18001ebf4  mov     eax, 80070057h
0x18001ebf9  mov     rcx, [rsp+58h+var_18]
0x18001ebfe  xor     rcx, rsp; StackCookie
0x18001ec01  call    __security_check_cookie
0x18001ec06  mov     rbx, [rsp+58h+arg_0]
0x18001ec0b  mov     rsi, [rsp+58h+arg_10]
0x18001ec10  add     rsp, 50h
0x18001ec14  pop     rdi
0x18001ec15  retn
```
