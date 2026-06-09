# ctl::Service::stopService(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> const &,ulong)

- ea: `0x18008caf4`
- end: `0x18008cc7f`
- name: `?stopService@Service@ctl@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18008c184`
- `0x18008cac0`

## callees

- `0x180013748`
- `0x18008caf4`
- `0x1800a4388`
- `0x1800a88a0`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cbb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008cbc0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008cc0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008cbc0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008cc0a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008cc1d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008cc1d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18008cb4f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18008cbfa`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18008cb4f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18008cbfa`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18008cba6`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18008cba6`

## string_xrefs

- `0x18008cb5d`: `onecoreuap\private\net\inc\winsock2\ctl\headers\ctServiceControl.hpp`
- `0x18008cc29`: `onecoreuap\private\net\inc\winsock2\ctl\headers\ctServiceControl.hpp`
- `0x18008cc6a`: `onecoreuap\private\net\inc\winsock2\ctl\headers\ctServiceControl.hpp`

## pseudocode

```c
char __fastcall ctl::Service::stopService(SC_HANDLE *a1, unsigned int a2)
{
  ULONGLONG v2; // r15
  SC_HANDLE v4; // rcx
  const char *v5; // r9
  char v6; // bl
  char result; // al
  SC_HANDLE v8; // rcx
  DWORD LastError; // eax
  ULONGLONG TickCount64; // r14
  SC_HANDLE v11; // rcx
  const char *v12; // r9
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-39h]
  DWORD v14; // [rsp+30h] [rbp-29h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-21h] BYREF
  __int128 v16; // [rsp+48h] [rbp-11h]
  int v17; // [rsp+58h] [rbp-1h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = a2;
  v17 = 0;
  v14 = 0;
  v4 = *a1;
  *(_OWORD *)Buffer = 0;
  v16 = 0;
  if ( !QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v14) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecoreuap\\private\\net\\inc\\winsock2\\ctl\\headers\\ctServiceControl.hpp",
      v5);
  v6 = 1;
  if ( *(_DWORD *)&Buffer[4] != 1 && *(_DWORD *)&Buffer[4] != 3 )
  {
    result = ctl::Service::stopDependentServices(a1, (unsigned int)v2);
    if ( !result )
      return result;
    v8 = *a1;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v8, 1u, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( LastError != 1062 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecoreuap\\private\\net\\inc\\winsock2\\ctl\\headers\\ctServiceControl.hpp",
          (const char *)LastError,
          pcbBytesNeeded);
      *(_DWORD *)&Buffer[4] = 1;
    }
  }
  TickCount64 = GetTickCount64();
  while ( *(_DWORD *)&Buffer[4] != 1 )
  {
    v11 = *a1;
    v17 = 0;
    *(_OWORD *)Buffer = 0;
    v16 = 0;
    if ( !QueryServiceStatusEx(v11, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v14) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\private\\net\\inc\\winsock2\\ctl\\headers\\ctServiceControl.hpp",
        v12);
    if ( *(_DWORD *)&Buffer[4] == 3 )
    {
      if ( GetTickCount64() - TickCount64 >= v2 )
      {
        if ( *(_DWORD *)&Buffer[4] != 1 )
          return 0;
        return v6;
      }
      Sleep(0x3E8u);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18008caf4  mov     [rsp-8+arg_10], rbx
0x18008caf9  push    rbp
0x18008cafa  push    rsi
0x18008cafb  push    rdi
0x18008cafc  push    r14
0x18008cafe  push    r15
0x18008cb00  lea     rbp, [rsp-37h]
0x18008cb05  sub     rsp, 90h
0x18008cb0c  mov     rax, cs:__security_cookie
0x18008cb13  xor     rax, rsp
0x18008cb16  mov     [rbp+57h+var_30], rax
0x18008cb1a  xor     eax, eax
0x18008cb1c  mov     r15d, edx
0x18008cb1f  xorps   xmm0, xmm0
0x18008cb22  mov     [rbp+57h+var_58], eax
0x18008cb25  lea     rax, [rbp+57h+var_80]
0x18008cb29  mov     [rbp+57h+var_80], 0
0x18008cb30  mov     rdi, rcx
0x18008cb33  mov     qword ptr [rsp+0B0h+pcbBytesNeeded], rax; unsigned int
0x18008cb38  mov     rcx, [rcx]; hService
0x18008cb3b  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18008cb3f  mov     r9d, 24h ; '$'; cbBufSize
0x18008cb45  xor     edx, edx; InfoLevel
0x18008cb47  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18008cb4b  movups  [rbp+57h+var_68], xmm0
0x18008cb4f  call    cs:__imp_QueryServiceStatusEx
0x18008cb55  test    eax, eax
0x18008cb57  jnz     short loc_18008CB6F
0x18008cb59  mov     rcx, [rbp+5Fh]; this
0x18008cb5d  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\winsock2"...
0x18008cb64  mov     edx, 139h; void *
0x18008cb69  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008cb6f  mov     ebx, 1
0x18008cb74  cmp     dword ptr [rbp+57h+Buffer+4], ebx
0x18008cb77  jz      short loc_18008CBC0
0x18008cb79  cmp     dword ptr [rbp+57h+Buffer+4], 3
0x18008cb7d  jz      short loc_18008CBC0
0x18008cb7f  mov     edx, r15d
0x18008cb82  mov     rcx, rdi
0x18008cb85  call    ?stopDependentServices@Service@ctl@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ctl::Service::stopDependentServices(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> const &,ulong)
0x18008cb8a  test    al, al
0x18008cb8c  jz      loc_18008CC47
0x18008cb92  mov     rcx, [rdi]; hService
0x18008cb95  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18008cb99  xorps   xmm0, xmm0
0x18008cb9c  mov     edx, ebx; dwControl
0x18008cb9e  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18008cba2  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18008cba6  call    cs:__imp_ControlService
0x18008cbac  test    eax, eax
0x18008cbae  jnz     short loc_18008CBC0
0x18008cbb0  call    cs:__imp_GetLastError
0x18008cbb6  cmp     eax, 426h
0x18008cbbb  jnz     short loc_18008CC25
0x18008cbbd  mov     dword ptr [rbp+57h+Buffer+4], ebx
0x18008cbc0  call    cs:__imp_GetTickCount64
0x18008cbc6  mov     r14, rax
0x18008cbc9  cmp     dword ptr [rbp+57h+Buffer+4], ebx
0x18008cbcc  jz      short loc_18008CC45
0x18008cbce  mov     rcx, [rdi]; hService
0x18008cbd1  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18008cbd5  mov     rsi, [rbp+5Fh]
0x18008cbd9  xor     eax, eax
0x18008cbdb  xorps   xmm0, xmm0
0x18008cbde  mov     [rbp+57h+var_58], eax
0x18008cbe1  lea     rax, [rbp+57h+var_80]
0x18008cbe5  mov     r9d, 24h ; '$'; cbBufSize
0x18008cbeb  xor     edx, edx; InfoLevel
0x18008cbed  mov     qword ptr [rsp+0B0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18008cbf2  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18008cbf6  movups  [rbp+57h+var_68], xmm0
0x18008cbfa  call    cs:__imp_QueryServiceStatusEx
0x18008cc00  test    eax, eax
0x18008cc02  jz      short loc_18008CC6A
0x18008cc04  cmp     dword ptr [rbp+57h+Buffer+4], 3
0x18008cc08  jnz     short loc_18008CBC9
0x18008cc0a  call    cs:__imp_GetTickCount64
0x18008cc10  sub     rax, r14
0x18008cc13  cmp     rax, r15
0x18008cc16  jnb     short loc_18008CC3E
0x18008cc18  mov     ecx, 3E8h; dwMilliseconds
0x18008cc1d  call    cs:__imp_Sleep
0x18008cc23  jmp     short loc_18008CBC9
0x18008cc25  mov     rcx, [rbp+5Fh]; this
0x18008cc29  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\winsock2"...
0x18008cc30  mov     r9d, eax; char *
0x18008cc33  mov     edx, 14Fh; void *
0x18008cc38  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008cc3e  cmp     dword ptr [rbp+57h+Buffer+4], ebx
0x18008cc41  jz      short loc_18008CC45
0x18008cc43  xor     bl, bl
0x18008cc45  mov     al, bl
0x18008cc47  mov     rcx, [rbp+57h+var_30]
0x18008cc4b  xor     rcx, rsp; StackCookie
0x18008cc4e  call    __security_check_cookie
0x18008cc53  mov     rbx, [rsp+0B0h+arg_10]
0x18008cc5b  add     rsp, 90h
0x18008cc62  pop     r15
0x18008cc64  pop     r14
0x18008cc66  pop     rdi
0x18008cc67  pop     rsi
0x18008cc68  pop     rbp
0x18008cc69  retn
0x18008cc6a  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\winsock2"...
0x18008cc71  mov     edx, 15Bh; void *
0x18008cc76  mov     rcx, rsi; this
0x18008cc79  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
