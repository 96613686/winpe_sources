# CCatalogServer::RefreshServiceSettings(__MIDL___MIDL_itf_catsrv_0000_0004_0001)

- ea: `0x18001e870`
- end: `0x18001e9c1`
- name: `?RefreshServiceSettings@CCatalogServer@@UEAAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18001e744`
- `0x18001e870`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e968`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e980`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e98e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e980`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e98e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e919`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e919`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e93c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e93c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001e95e`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001e95e`

## pseudocode

```c
__int64 __fastcall CCatalogServer::RefreshServiceSettings(__int64 *a1, int a2)
{
  __int64 v2; // rdi
  signed int LoadBalancingIfNeeded; // ebx
  __int64 v5; // rax
  const WCHAR *v6; // rbp
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rsi
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rdi
  signed int LastError; // eax
  int v13; // [rsp+20h] [rbp-48h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-40h] BYREF

  v2 = a2;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a2 != 1 || !*(&dwSaferTrustedLevel - 9) )
    return 2147942487LL;
  LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(1);
  if ( LoadBalancingIfNeeded < 0 )
    return (unsigned int)LoadBalancingIfNeeded;
  v5 = *a1;
  v6 = (&csServices)[10 * v2 - 5];
  v13 = 0;
  LoadBalancingIfNeeded = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *))(v5 + 64))(a1, (unsigned int)v2, &v13);
  if ( LoadBalancingIfNeeded >= 0 && (v13 & 0xFFFFFFFD) != 0 )
  {
    v7 = OpenSCManagerW(0, 0, 0xA0000000);
    v8 = v7;
    if ( v7 )
    {
      v10 = OpenServiceW(v7, v6, 0x120u);
      v11 = v10;
      if ( v10 )
      {
        if ( !ControlService(v10, 0x80u, &ServiceStatus) )
        {
          LastError = GetLastError();
          LoadBalancingIfNeeded = LastError;
          if ( LastError > 0 )
            LoadBalancingIfNeeded = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        LoadBalancingIfNeeded = -2147418113;
      }
      CloseServiceHandle(v8);
      if ( v11 )
        CloseServiceHandle(v11);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return (unsigned int)LoadBalancingIfNeeded;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e870  mov     [rsp+arg_10], rbx
0x18001e875  mov     [rsp+arg_18], rbp
0x18001e87a  push    rsi
0x18001e87b  push    rdi
0x18001e87c  push    r14
0x18001e87e  sub     rsp, 50h
0x18001e882  mov     rax, cs:__security_cookie
0x18001e889  xor     rax, rsp
0x18001e88c  mov     [rsp+68h+var_20], rax
0x18001e891  xorps   xmm0, xmm0
0x18001e894  movsxd  rdi, edx
0x18001e897  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18001e89c  mov     r14, rcx
0x18001e89f  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001e8a4  lea     eax, [rdi-1]
0x18001e8a7  test    eax, eax
0x18001e8a9  jnz     loc_18001E99A
0x18001e8af  lea     rsi, [rdi+rdi*4]
0x18001e8b3  add     rsi, rsi
0x18001e8b6  lea     rbp, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001e8bd  cmp     [rbp+rsi*8-24h], eax
0x18001e8c1  jz      loc_18001E99A
0x18001e8c7  mov     ecx, edi
0x18001e8c9  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001e8ce  mov     ebx, eax
0x18001e8d0  test    eax, eax
0x18001e8d2  js      short loc_18001E92C
0x18001e8d4  mov     rax, [r14]
0x18001e8d7  lea     r8, [rsp+68h+var_48]
0x18001e8dc  mov     rbp, [rbp+rsi*8-50h]
0x18001e8e1  mov     edx, edi
0x18001e8e3  mov     rcx, r14
0x18001e8e6  mov     [rsp+68h+var_48], 0
0x18001e8ee  mov     rax, [rax+40h]
0x18001e8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8f7  mov     ebx, eax
0x18001e8f9  test    eax, eax
0x18001e8fb  js      loc_18001E996
0x18001e901  test    [rsp+68h+var_48], 0FFFFFFFDh
0x18001e909  jz      loc_18001E996
0x18001e90f  xor     edx, edx; lpDatabaseName
0x18001e911  xor     ecx, ecx; lpMachineName
0x18001e913  mov     r8d, 0A0000000h; dwDesiredAccess
0x18001e919  call    cs:__imp_OpenSCManagerW
0x18001e91f  mov     rsi, rax
0x18001e922  test    rax, rax
0x18001e925  jnz     short loc_18001E930
0x18001e927  mov     ebx, 8000FFFFh
0x18001e92c  mov     eax, ebx
0x18001e92e  jmp     short loc_18001E99F
0x18001e930  mov     r8d, 120h; dwDesiredAccess
0x18001e936  mov     rdx, rbp; lpServiceName
0x18001e939  mov     rcx, rsi; hSCManager
0x18001e93c  call    cs:__imp_OpenServiceW
0x18001e942  mov     rdi, rax
0x18001e945  test    rax, rax
0x18001e948  jnz     short loc_18001E951
0x18001e94a  mov     ebx, 8000FFFFh
0x18001e94f  jmp     short loc_18001E97D
0x18001e951  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18001e956  mov     edx, 80h; dwControl
0x18001e95b  mov     rcx, rdi; hService
0x18001e95e  call    cs:__imp_ControlService
0x18001e964  test    eax, eax
0x18001e966  jnz     short loc_18001E97D
0x18001e968  call    cs:__imp_GetLastError
0x18001e96e  mov     ebx, eax
0x18001e970  test    eax, eax
0x18001e972  jle     short loc_18001E97D
0x18001e974  movzx   ebx, ax
0x18001e977  or      ebx, 80070000h
0x18001e97d  mov     rcx, rsi; hSCObject
0x18001e980  call    cs:__imp_CloseServiceHandle
0x18001e986  test    rdi, rdi
0x18001e989  jz      short loc_18001E92C
0x18001e98b  mov     rcx, rdi; hSCObject
0x18001e98e  call    cs:__imp_CloseServiceHandle
0x18001e994  jmp     short loc_18001E92C
0x18001e996  xor     eax, eax
0x18001e998  jmp     short loc_18001E99F
0x18001e99a  mov     eax, 80070057h
0x18001e99f  mov     rcx, [rsp+68h+var_20]
0x18001e9a4  xor     rcx, rsp; StackCookie
0x18001e9a7  call    __security_check_cookie
0x18001e9ac  lea     r11, [rsp+68h+var_18]
0x18001e9b1  mov     rbx, [r11+30h]
0x18001e9b5  mov     rbp, [r11+38h]
0x18001e9b9  mov     rsp, r11
0x18001e9bc  pop     r14
0x18001e9be  pop     rdi
0x18001e9bf  pop     rsi
0x18001e9c0  retn
```
