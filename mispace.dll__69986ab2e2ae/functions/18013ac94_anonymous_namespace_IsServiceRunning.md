# _anonymous_namespace_::IsServiceRunning

- ea: `0x18013ac94`
- end: `0x18013ae53`
- name: `_anonymous_namespace_::IsServiceRunning`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013a74c`

## callees

- `0x180006350`
- `0x18013a340`
- `0x18013ac94`
- `0x18013bc60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013acda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ad66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013add6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013acda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ad66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013add6`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18013adbd`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18013adbd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18013acbc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18013acbc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18013ad44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18013ad44`

## string_xrefs

- `0x18013ad09`: `OpenSCManagerW`
- `0x18013ad15`: ``anonymous-namespace'::IsServiceRunning`
- `0x18013ae05`: ``anonymous-namespace'::IsServiceRunning`
- `0x18013ad89`: `Couldn't obtain handle to service`
- `0x18013ad82`: `OpenServiceW`
- `0x18013adf9`: `Couldn't query service status`
- `0x18013adf2`: `QueryServiceStatusEx`

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
0x18013ac94  mov     [rsp-8+arg_0], rbx
0x18013ac99  push    rbp
0x18013ac9a  lea     rbp, [rsp-57h]
0x18013ac9f  sub     rsp, 90h
0x18013aca6  mov     rax, cs:__security_cookie
0x18013acad  xor     rax, rsp
0x18013acb0  mov     [rbp+57h+var_10], rax
0x18013acb4  xor     edx, edx; lpDatabaseName
0x18013acb6  xor     ecx, ecx; lpMachineName
0x18013acb8  lea     r8d, [rdx+5]; dwDesiredAccess
0x18013acbc  call    cs:__imp_OpenSCManagerW
0x18013acc3  nop     dword ptr [rax+rax+00h]
0x18013acc8  mov     [rbp+57h+var_48], rax
0x18013accc  test    rax, rax
0x18013accf  jnz     short loc_18013AD31
0x18013acd1  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x18013acd8  jz      short loc_18013AD21
0x18013acda  call    cs:__imp_GetLastError
0x18013ace1  nop     dword ptr [rax+rax+00h]
0x18013ace6  test    eax, eax
0x18013ace8  jle     short loc_18013ACF2
0x18013acea  movzx   eax, ax
0x18013aced  or      eax, 80070000h
0x18013acf2  mov     [rsp+90h+var_60], eax
0x18013acf6  lea     rbx, ServiceName; "refsdedupsvc"
0x18013acfd  lea     rax, aCouldnTObtainH_0; "Couldn't obtain handle to SCM"
0x18013ad04  mov     [rsp+90h+var_68], rbx
0x18013ad09  lea     r9, aOpenscmanagerw; "OpenSCManagerW"
0x18013ad10  mov     [rsp+90h+pcbBytesNeeded], rax
0x18013ad15  lea     r8, aAnonymousNames; "`anonymous-namespace'::IsServiceRunning"
0x18013ad1c  call    McTemplateU0sszzd_EventWriteTransfer
0x18013ad21  lea     rcx, [rbp+57h+var_48]
0x18013ad25  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18013ad2a  xor     al, al
0x18013ad2c  jmp     loc_18013AE35
0x18013ad31  lea     rbx, ServiceName; "refsdedupsvc"
0x18013ad38  mov     r8d, 4; dwDesiredAccess
0x18013ad3e  mov     rdx, rbx; lpServiceName
0x18013ad41  mov     rcx, rax; hSCManager
0x18013ad44  call    cs:__imp_OpenServiceW
0x18013ad4b  nop     dword ptr [rax+rax+00h]
0x18013ad50  mov     [rbp+57h+var_40], rax
0x18013ad54  test    rax, rax
0x18013ad57  jnz     short loc_18013AD92
0x18013ad59  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x18013ad60  jz      loc_18013AE16
0x18013ad66  call    cs:__imp_GetLastError
0x18013ad6d  nop     dword ptr [rax+rax+00h]
0x18013ad72  test    eax, eax
0x18013ad74  jle     short loc_18013AD7E
0x18013ad76  movzx   eax, ax
0x18013ad79  or      eax, 80070000h
0x18013ad7e  mov     [rsp+90h+var_60], eax
0x18013ad82  lea     r9, aOpenservicew; "OpenServiceW"
0x18013ad89  lea     rax, aCouldnTObtainH; "Couldn't obtain handle to service"
0x18013ad90  jmp     short loc_18013AE00
0x18013ad92  xor     ecx, ecx
0x18013ad94  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18013ad98  mov     [rbp+57h+var_18], ecx
0x18013ad9b  xorps   xmm0, xmm0
0x18013ad9e  mov     [rbp+57h+var_50], ecx
0x18013ada1  mov     r9d, 24h ; '$'; cbBufSize
0x18013ada7  lea     rcx, [rbp+57h+var_50]
0x18013adab  xor     edx, edx; InfoLevel
0x18013adad  mov     [rsp+90h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x18013adb2  mov     rcx, rax; hService
0x18013adb5  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18013adb9  movups  [rbp+57h+var_28], xmm0
0x18013adbd  call    cs:__imp_QueryServiceStatusEx
0x18013adc4  nop     dword ptr [rax+rax+00h]
0x18013adc9  test    eax, eax
0x18013adcb  jnz     short loc_18013AE1A
0x18013adcd  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x18013add4  jz      short loc_18013AE16
0x18013add6  call    cs:__imp_GetLastError
0x18013addd  nop     dword ptr [rax+rax+00h]
0x18013ade2  test    eax, eax
0x18013ade4  jle     short loc_18013ADEE
0x18013ade6  movzx   eax, ax
0x18013ade9  or      eax, 80070000h
0x18013adee  mov     [rsp+90h+var_60], eax
0x18013adf2  lea     r9, aQueryservicest; "QueryServiceStatusEx"
0x18013adf9  lea     rax, aCouldnTQuerySe; "Couldn't query service status"
0x18013ae00  mov     [rsp+90h+var_68], rbx
0x18013ae05  lea     r8, aAnonymousNames; "`anonymous-namespace'::IsServiceRunning"
0x18013ae0c  mov     [rsp+90h+pcbBytesNeeded], rax
0x18013ae11  call    McTemplateU0sszzd_EventWriteTransfer
0x18013ae16  xor     bl, bl
0x18013ae18  jmp     short loc_18013AE21
0x18013ae1a  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x18013ae1e  setz    bl
0x18013ae21  lea     rcx, [rbp+57h+var_40]
0x18013ae25  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18013ae2a  lea     rcx, [rbp+57h+var_48]
0x18013ae2e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18013ae33  mov     al, bl
0x18013ae35  mov     rcx, [rbp+57h+var_10]
0x18013ae39  xor     rcx, rsp; StackCookie
0x18013ae3c  call    __security_check_cookie
0x18013ae41  mov     rbx, [rsp+90h+arg_0]
0x18013ae49  add     rsp, 90h
0x18013ae50  pop     rbp
0x18013ae51  retn
```
