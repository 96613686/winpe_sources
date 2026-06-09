# _anonymous_namespace_::IsServiceRunning

- ea: `0x1801369a0`
- end: `0x180136b3a`
- name: `_anonymous_namespace_::IsServiceRunning`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180136468`

## callees

- `0x180006290`
- `0x18013606c`
- `0x1801369a0`
- `0x1801378e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801369e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180136a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180136ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801369e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180136a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180136ac4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180136ab1`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180136ab1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801369c8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801369c8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180136a44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180136a44`

## string_xrefs

- `0x180136a7d`: `Couldn't obtain handle to service`
- `0x180136a76`: `OpenServiceW`
- `0x180136ae1`: `Couldn't query service status`
- `0x180136ada`: `QueryServiceStatusEx`
- `0x180136a09`: `OpenSCManagerW`
- `0x180136a15`: ``anonymous-namespace'::IsServiceRunning`
- `0x180136aed`: ``anonymous-namespace'::IsServiceRunning`

## pseudocode

```c
bool anonymous_namespace_::IsServiceRunning()
{
  SC_HANDLE v0; // rax
  char v1; // al
  int v2; // edx
  int v3; // ecx
  SC_HANDLE v5; // rax
  char v6; // al
  int v7; // edx
  int v8; // ecx
  char LastError; // al
  int v10; // edx
  int v11; // ecx
  bool v12; // bl
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp+7h] BYREF
  SC_HANDLE v14; // [rsp+48h] [rbp+Fh] BYREF
  SC_HANDLE v15; // [rsp+50h] [rbp+17h] BYREF
  BYTE Buffer[16]; // [rsp+58h] [rbp+1Fh] BYREF
  __int128 v17; // [rsp+68h] [rbp+2Fh]
  int v18; // [rsp+78h] [rbp+3Fh]

  v0 = OpenSCManagerW(0, 0, 5u);
  v14 = v0;
  if ( v0 )
  {
    v5 = OpenServiceW(v0, L"refsdedupsvc", 4u);
    v15 = v5;
    if ( v5 )
    {
      v18 = 0;
      pcbBytesNeeded = 0;
      *(_OWORD *)Buffer = 0;
      v17 = 0;
      if ( QueryServiceStatusEx(v5, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v12 = *(_DWORD *)&Buffer[4] == 4;
        goto LABEL_13;
      }
      if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
      {
        LastError = GetLastError();
        McTemplateU0sszzd_EventWriteTransfer(
          v11,
          v10,
          (unsigned int)"`anonymous-namespace'::IsServiceRunning",
          (unsigned int)"QueryServiceStatusEx",
          (__int64)L"Couldn't query service status",
          (__int64)L"refsdedupsvc",
          LastError);
      }
    }
    else if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
    {
      v6 = GetLastError();
      McTemplateU0sszzd_EventWriteTransfer(
        v8,
        v7,
        (unsigned int)"`anonymous-namespace'::IsServiceRunning",
        (unsigned int)"OpenServiceW",
        (__int64)L"Couldn't obtain handle to service",
        (__int64)L"refsdedupsvc",
        v6);
    }
    v12 = 0;
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
    return v12;
  }
  if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
  {
    v1 = GetLastError();
    McTemplateU0sszzd_EventWriteTransfer(
      v3,
      v2,
      (unsigned int)"`anonymous-namespace'::IsServiceRunning",
      (unsigned int)"OpenSCManagerW",
      (__int64)L"Couldn't obtain handle to SCM",
      (__int64)L"refsdedupsvc",
      v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
  return 0;
}

```

## disassembly

```asm
0x1801369a0  mov     [rsp-8+arg_0], rbx
0x1801369a5  push    rbp
0x1801369a6  lea     rbp, [rsp-57h]
0x1801369ab  sub     rsp, 90h
0x1801369b2  mov     rax, cs:__security_cookie
0x1801369b9  xor     rax, rsp
0x1801369bc  mov     [rbp+57h+var_10], rax
0x1801369c0  xor     edx, edx; lpDatabaseName
0x1801369c2  xor     ecx, ecx; lpMachineName
0x1801369c4  lea     r8d, [rdx+5]; dwDesiredAccess
0x1801369c8  call    cs:__imp_OpenSCManagerW
0x1801369ce  mov     [rbp+57h+var_48], rax
0x1801369d2  test    rax, rax
0x1801369d5  jnz     short loc_180136A31
0x1801369d7  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x1801369de  jz      short loc_180136A21
0x1801369e0  call    cs:__imp_GetLastError
0x1801369e6  test    eax, eax
0x1801369e8  jle     short loc_1801369F2
0x1801369ea  movzx   eax, ax
0x1801369ed  or      eax, 80070000h
0x1801369f2  mov     [rsp+90h+var_60], eax
0x1801369f6  lea     rbx, ServiceName; "refsdedupsvc"
0x1801369fd  lea     rax, aCouldnTObtainH_0; "Couldn't obtain handle to SCM"
0x180136a04  mov     [rsp+90h+var_68], rbx
0x180136a09  lea     r9, aOpenscmanagerw; "OpenSCManagerW"
0x180136a10  mov     [rsp+90h+pcbBytesNeeded], rax
0x180136a15  lea     r8, aAnonymousNames; "`anonymous-namespace'::IsServiceRunning"
0x180136a1c  call    McTemplateU0sszzd_EventWriteTransfer
0x180136a21  lea     rcx, [rbp+57h+var_48]
0x180136a25  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180136a2a  xor     al, al
0x180136a2c  jmp     loc_180136B1D
0x180136a31  lea     rbx, ServiceName; "refsdedupsvc"
0x180136a38  mov     r8d, 4; dwDesiredAccess
0x180136a3e  mov     rdx, rbx; lpServiceName
0x180136a41  mov     rcx, rax; hSCManager
0x180136a44  call    cs:__imp_OpenServiceW
0x180136a4a  mov     [rbp+57h+var_40], rax
0x180136a4e  test    rax, rax
0x180136a51  jnz     short loc_180136A86
0x180136a53  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x180136a5a  jz      loc_180136AFE
0x180136a60  call    cs:__imp_GetLastError
0x180136a66  test    eax, eax
0x180136a68  jle     short loc_180136A72
0x180136a6a  movzx   eax, ax
0x180136a6d  or      eax, 80070000h
0x180136a72  mov     [rsp+90h+var_60], eax
0x180136a76  lea     r9, aOpenservicew; "OpenServiceW"
0x180136a7d  lea     rax, aCouldnTObtainH; "Couldn't obtain handle to service"
0x180136a84  jmp     short loc_180136AE8
0x180136a86  xor     ecx, ecx
0x180136a88  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180136a8c  mov     [rbp+57h+var_18], ecx
0x180136a8f  xorps   xmm0, xmm0
0x180136a92  mov     [rbp+57h+var_50], ecx
0x180136a95  mov     r9d, 24h ; '$'; cbBufSize
0x180136a9b  lea     rcx, [rbp+57h+var_50]
0x180136a9f  xor     edx, edx; InfoLevel
0x180136aa1  mov     [rsp+90h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x180136aa6  mov     rcx, rax; hService
0x180136aa9  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180136aad  movups  [rbp+57h+var_28], xmm0
0x180136ab1  call    cs:__imp_QueryServiceStatusEx
0x180136ab7  test    eax, eax
0x180136ab9  jnz     short loc_180136B02
0x180136abb  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x180136ac2  jz      short loc_180136AFE
0x180136ac4  call    cs:__imp_GetLastError
0x180136aca  test    eax, eax
0x180136acc  jle     short loc_180136AD6
0x180136ace  movzx   eax, ax
0x180136ad1  or      eax, 80070000h
0x180136ad6  mov     [rsp+90h+var_60], eax
0x180136ada  lea     r9, aQueryservicest; "QueryServiceStatusEx"
0x180136ae1  lea     rax, aCouldnTQuerySe; "Couldn't query service status"
0x180136ae8  mov     [rsp+90h+var_68], rbx
0x180136aed  lea     r8, aAnonymousNames; "`anonymous-namespace'::IsServiceRunning"
0x180136af4  mov     [rsp+90h+pcbBytesNeeded], rax
0x180136af9  call    McTemplateU0sszzd_EventWriteTransfer
0x180136afe  xor     bl, bl
0x180136b00  jmp     short loc_180136B09
0x180136b02  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x180136b06  setz    bl
0x180136b09  lea     rcx, [rbp+57h+var_40]
0x180136b0d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180136b12  lea     rcx, [rbp+57h+var_48]
0x180136b16  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180136b1b  mov     al, bl
0x180136b1d  mov     rcx, [rbp+57h+var_10]
0x180136b21  xor     rcx, rsp; StackCookie
0x180136b24  call    __security_check_cookie
0x180136b29  mov     rbx, [rsp+90h+arg_0]
0x180136b31  add     rsp, 90h
0x180136b38  pop     rbp
0x180136b39  retn
```
