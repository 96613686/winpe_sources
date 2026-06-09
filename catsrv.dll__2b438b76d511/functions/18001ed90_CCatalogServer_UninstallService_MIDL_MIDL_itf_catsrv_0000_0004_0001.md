# CCatalogServer::UninstallService(__MIDL___MIDL_itf_catsrv_0000_0004_0001)

- ea: `0x18001ed90`
- end: `0x18001efb6`
- name: `?UninstallService@CCatalogServer@@UEAAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000a01c`
- `0x18001e744`
- `0x18001ed90`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ee14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ee14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef59`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ef71`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ef7f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ef71`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ef7f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ee53`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ee53`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18001eedf`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x18001eedf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ee8b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ee8b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001eeaa`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001eece`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001eeaa`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001eece`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001ef4b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001ef4b`

## pseudocode

```c
__int64 __fastcall CCatalogServer::UninstallService(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  signed int LoadBalancingIfNeeded; // ebx
  __int64 v4; // rsi
  UINT v5; // edx
  const WCHAR *v6; // rdi
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbp
  signed int LastError; // eax
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rdi
  __int64 (*v13)(void); // rax
  signed int v14; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-238h] BYREF

  v2 = (int)a2;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a2 == 1 )
  {
    LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(a2);
    if ( LoadBalancingIfNeeded >= 0 )
    {
      v4 = 10 * v2;
      v5 = *((_DWORD *)&csServices + 20 * v2 - 18);
      v6 = (&csServices)[10 * v2 - 5];
      if ( v5 )
      {
        if ( !LoadStringW(hInstance, v5, Buffer, 260) )
          return 2147549183LL;
LABEL_7:
        v8 = OpenSCManagerW(0, 0, 0xF003Fu);
        v9 = v8;
        if ( !v8 )
        {
          LastError = GetLastError();
          LoadBalancingIfNeeded = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return (unsigned int)LoadBalancingIfNeeded;
        }
        v11 = OpenServiceW(v8, v6, 0xF01FFu);
        v12 = v11;
        if ( v11 )
        {
          if ( ControlService(v11, 4u, &ServiceStatus) && ((ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) != 0 )
            ControlService(v12, 1u, &ServiceStatus);
          if ( *((_DWORD *)&csServices + 2 * v4 - 10) )
          {
            if ( DeleteService(v12) )
            {
              v13 = (__int64 (*)(void))(&csServices)[v4 - 1];
              if ( v13 )
                LoadBalancingIfNeeded = v13();
              goto LABEL_22;
            }
          }
          else if ( ChangeServiceConfigW(v12, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, Buffer) )
          {
            LoadBalancingIfNeeded = 0;
LABEL_22:
            CloseServiceHandle(v9);
            if ( v12 )
              CloseServiceHandle(v12);
            return (unsigned int)LoadBalancingIfNeeded;
          }
        }
        v14 = GetLastError();
        LoadBalancingIfNeeded = v14;
        if ( v14 > 0 )
          LoadBalancingIfNeeded = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_22;
      }
      LoadBalancingIfNeeded = StringCchCopyW(Buffer, 0x104u, (&csServices)[v4 - 4]);
      if ( LoadBalancingIfNeeded >= 0 )
        goto LABEL_7;
    }
    return (unsigned int)LoadBalancingIfNeeded;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001ed90  mov     [rsp+arg_0], rbx
0x18001ed95  mov     [rsp+arg_10], rbp
0x18001ed9a  push    rsi
0x18001ed9b  push    rdi
0x18001ed9c  push    r15
0x18001ed9e  sub     rsp, 2A0h
0x18001eda5  mov     rax, cs:__security_cookie
0x18001edac  xor     rax, rsp
0x18001edaf  mov     [rsp+2B8h+var_28], rax
0x18001edb7  xorps   xmm0, xmm0
0x18001edba  movsxd  rdi, edx
0x18001edbd  movups  xmmword ptr [rsp+2B8h+ServiceStatus.dwServiceType], xmm0
0x18001edc2  movups  xmmword ptr [rsp+2B8h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001edc7  lea     eax, [rdi-1]
0x18001edca  test    eax, eax
0x18001edcc  jnz     loc_18001EF89
0x18001edd2  mov     ecx, edi
0x18001edd4  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001edd9  mov     ebx, eax
0x18001eddb  test    eax, eax
0x18001eddd  js      loc_18001EF85
0x18001ede3  lea     rsi, [rdi+rdi*4]
0x18001ede7  add     rsi, rsi
0x18001edea  lea     r15, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001edf1  mov     edx, [r15+rsi*8-48h]; uID
0x18001edf6  mov     rdi, [r15+rsi*8-50h]
0x18001edfb  test    edx, edx
0x18001edfd  jz      short loc_18001EE28
0x18001edff  mov     rcx, cs:hInstance; hInstance
0x18001ee06  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x18001ee0e  mov     r9d, 104h; cchBufferMax
0x18001ee14  call    cs:__imp_LoadStringW
0x18001ee1a  test    eax, eax
0x18001ee1c  jnz     short loc_18001EE49
0x18001ee1e  mov     eax, 8000FFFFh
0x18001ee23  jmp     loc_18001EF8E
0x18001ee28  mov     r8, [r15+rsi*8-40h]; unsigned __int16 *
0x18001ee2d  lea     rcx, [rsp+2B8h+Buffer]; unsigned __int16 *
0x18001ee35  mov     edx, 104h; unsigned __int64
0x18001ee3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ee3f  mov     ebx, eax
0x18001ee41  test    eax, eax
0x18001ee43  js      loc_18001EF85
0x18001ee49  xor     edx, edx; lpDatabaseName
0x18001ee4b  xor     ecx, ecx; lpMachineName
0x18001ee4d  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001ee53  call    cs:__imp_OpenSCManagerW
0x18001ee59  mov     rbp, rax
0x18001ee5c  test    rax, rax
0x18001ee5f  jnz     short loc_18001EE7F
0x18001ee61  call    cs:__imp_GetLastError
0x18001ee67  mov     ebx, eax
0x18001ee69  test    eax, eax
0x18001ee6b  jle     loc_18001EF85
0x18001ee71  movzx   ebx, ax
0x18001ee74  or      ebx, 80070000h
0x18001ee7a  jmp     loc_18001EF85
0x18001ee7f  mov     r8d, 0F01FFh; dwDesiredAccess
0x18001ee85  mov     rdx, rdi; lpServiceName
0x18001ee88  mov     rcx, rbp; hSCManager
0x18001ee8b  call    cs:__imp_OpenServiceW
0x18001ee91  mov     rdi, rax
0x18001ee94  test    rax, rax
0x18001ee97  jz      loc_18001EF59
0x18001ee9d  lea     r8, [rsp+2B8h+ServiceStatus]; lpServiceStatus
0x18001eea2  mov     edx, 4; dwControl
0x18001eea7  mov     rcx, rax; hService
0x18001eeaa  call    cs:__imp_ControlService
0x18001eeb0  test    eax, eax
0x18001eeb2  jz      short loc_18001EED4
0x18001eeb4  mov     eax, [rsp+2B8h+ServiceStatus.dwCurrentState]
0x18001eeb8  dec     eax
0x18001eeba  test    eax, 0FFFFFFFDh
0x18001eebf  jz      short loc_18001EED4
0x18001eec1  lea     r8, [rsp+2B8h+ServiceStatus]; lpServiceStatus
0x18001eec6  mov     edx, 1; dwControl
0x18001eecb  mov     rcx, rdi; hService
0x18001eece  call    cs:__imp_ControlService
0x18001eed4  cmp     dword ptr [r15+rsi*8-28h], 0
0x18001eeda  mov     rcx, rdi; hService
0x18001eedd  jz      short loc_18001EEFC
0x18001eedf  call    cs:__imp_DeleteService
0x18001eee5  test    eax, eax
0x18001eee7  jz      short loc_18001EF59
0x18001eee9  mov     rax, [r15+rsi*8-10h]
0x18001eeee  test    rax, rax
0x18001eef1  jz      short loc_18001EF6E
0x18001eef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eef8  mov     ebx, eax
0x18001eefa  jmp     short loc_18001EF6E
0x18001eefc  lea     rax, [rsp+2B8h+Buffer]
0x18001ef04  or      edx, 0FFFFFFFFh; dwServiceType
0x18001ef07  mov     [rsp+2B8h+lpDisplayName], rax; lpDisplayName
0x18001ef0c  mov     r9d, edx; dwErrorControl
0x18001ef0f  mov     [rsp+2B8h+lpPassword], 0; lpPassword
0x18001ef18  mov     r8d, 4; dwStartType
0x18001ef1e  mov     [rsp+2B8h+lpServiceStartName], 0; lpServiceStartName
0x18001ef27  mov     [rsp+2B8h+lpDependencies], 0; lpDependencies
0x18001ef30  mov     [rsp+2B8h+lpdwTagId], 0; lpdwTagId
0x18001ef39  mov     [rsp+2B8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18001ef42  mov     [rsp+2B8h+lpBinaryPathName], 0; lpBinaryPathName
0x18001ef4b  call    cs:__imp_ChangeServiceConfigW
0x18001ef51  test    eax, eax
0x18001ef53  jz      short loc_18001EF59
0x18001ef55  xor     ebx, ebx
0x18001ef57  jmp     short loc_18001EF6E
0x18001ef59  call    cs:__imp_GetLastError
0x18001ef5f  mov     ebx, eax
0x18001ef61  test    eax, eax
0x18001ef63  jle     short loc_18001EF6E
0x18001ef65  movzx   ebx, ax
0x18001ef68  or      ebx, 80070000h
0x18001ef6e  mov     rcx, rbp; hSCObject
0x18001ef71  call    cs:__imp_CloseServiceHandle
0x18001ef77  test    rdi, rdi
0x18001ef7a  jz      short loc_18001EF85
0x18001ef7c  mov     rcx, rdi; hSCObject
0x18001ef7f  call    cs:__imp_CloseServiceHandle
0x18001ef85  mov     eax, ebx
0x18001ef87  jmp     short loc_18001EF8E
0x18001ef89  mov     eax, 80070057h
0x18001ef8e  mov     rcx, [rsp+2B8h+var_28]
0x18001ef96  xor     rcx, rsp; StackCookie
0x18001ef99  call    __security_check_cookie
0x18001ef9e  lea     r11, [rsp+2B8h+var_18]
0x18001efa6  mov     rbx, [r11+20h]
0x18001efaa  mov     rbp, [r11+30h]
0x18001efae  mov     rsp, r11
0x18001efb1  pop     r15
0x18001efb3  pop     rdi
0x18001efb4  pop     rsi
0x18001efb5  retn
```
