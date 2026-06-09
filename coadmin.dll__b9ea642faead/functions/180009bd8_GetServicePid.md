# _GetServicePid

- ea: `0x180009bd8`
- end: `0x180009daa`
- name: `_GetServicePid`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006128`

## callees

- `0x180009bd8`
- `0x18000fb50`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180009c1d`
- `ADVAPI32!OpenSCManagerW` at `0x180009c1d`
- `ADVAPI32!OpenServiceW` at `0x180009c90`
- `ADVAPI32!OpenServiceW` at `0x180009c90`
- `ADVAPI32!CloseServiceHandle` at `0x180009d7a`
- `ADVAPI32!CloseServiceHandle` at `0x180009d83`
- `ADVAPI32!CloseServiceHandle` at `0x180009d7a`
- `ADVAPI32!CloseServiceHandle` at `0x180009d83`
- `ADVAPI32!QueryServiceStatusEx` at `0x180009d10`
- `ADVAPI32!QueryServiceStatusEx` at `0x180009d10`
- `KERNEL32!GetLastError` at `0x180009c2b`
- `KERNEL32!GetLastError` at `0x180009c9e`
- `KERNEL32!GetLastError` at `0x180009d1a`
- `KERNEL32!GetLastError` at `0x180009c2b`
- `KERNEL32!GetLastError` at `0x180009c9e`
- `KERNEL32!GetLastError` at `0x180009d1a`
- `IisRTL!PuDbgPrint` at `0x180009c78`
- `IisRTL!PuDbgPrint` at `0x180009ceb`
- `IisRTL!PuDbgPrint` at `0x180009d63`
- `IisRTL!PuDbgPrint` at `0x180009c78`
- `IisRTL!PuDbgPrint` at `0x180009ceb`
- `IisRTL!PuDbgPrint` at `0x180009d63`

## string_xrefs

- `0x180009c71`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180009ce4`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180009d5c`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180009c54`: `OpenSCManager() failed hr=0x%08x.\n`
- `0x180009c5f`: `_GetServicePid`
- `0x180009cd2`: `_GetServicePid`
- `0x180009d4a`: `_GetServicePid`
- `0x180009cc7`: `OpenService() failed hr=0x%08x.\n`
- `0x180009d3f`: `QueryServiceStatusEx() failed hr=0x%08x.\n`

## pseudocode

```c
__int64 GetServicePid()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  signed int v2; // eax
  unsigned int v3; // ebx
  SC_HANDLE v4; // rdi
  signed int v5; // eax
  signed int LastError; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v10; // [rsp+48h] [rbp-30h]
  int v11; // [rsp+58h] [rbp-20h]

  v11 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  CADMCOMW::sm_dwProcessIdRpcSs = 0;
  v10 = 0;
  v0 = OpenSCManagerW(0, 0, 4u);
  v1 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"RpcSs", 4u);
    if ( v4 )
    {
      if ( QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v3 = 0;
        CADMCOMW::sm_dwProcessIdRpcSs = HIDWORD(v10);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
            7532,
            "_GetServicePid",
            "QueryServiceStatusEx() failed hr=0x%08x.\n",
            v3);
      }
      CloseServiceHandle(v4);
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          7521,
          "_GetServicePid",
          "OpenService() failed hr=0x%08x.\n",
          v3);
    }
    CloseServiceHandle(v1);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        7511,
        "_GetServicePid",
        "OpenSCManager() failed hr=0x%08x.\n",
        v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180009bd8  mov     [rsp+arg_0], rbx
0x180009bdd  mov     [rsp+arg_8], rsi
0x180009be2  push    rdi
0x180009be3  sub     rsp, 70h
0x180009be7  mov     rax, cs:__security_cookie
0x180009bee  xor     rax, rsp
0x180009bf1  mov     [rsp+78h+var_18], rax
0x180009bf6  xor     eax, eax
0x180009bf8  xorps   xmm0, xmm0
0x180009bfb  xor     edx, edx; lpDatabaseName
0x180009bfd  mov     [rsp+78h+var_20], eax
0x180009c01  xor     ecx, ecx; lpMachineName
0x180009c03  mov     [rsp+78h+var_48], eax
0x180009c07  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180009c0c  lea     ebx, [rax+4]
0x180009c0f  mov     cs:?sm_dwProcessIdRpcSs@CADMCOMW@@2KA, eax; ulong CADMCOMW::sm_dwProcessIdRpcSs
0x180009c15  mov     r8d, ebx; dwDesiredAccess
0x180009c18  movups  [rsp+78h+var_30], xmm0
0x180009c1d  call    cs:__imp_OpenSCManagerW
0x180009c23  mov     rsi, rax
0x180009c26  test    rax, rax
0x180009c29  jnz     short loc_180009C83
0x180009c2b  call    cs:__imp_GetLastError
0x180009c31  mov     ebx, eax
0x180009c33  test    eax, eax
0x180009c35  jle     short loc_180009C40
0x180009c37  movzx   ebx, ax
0x180009c3a  or      ebx, 80070000h
0x180009c40  test    byte ptr cs:g_dwDebugFlags, 3
0x180009c47  jz      loc_180009D89
0x180009c4d  mov     rcx, cs:g_pDebug
0x180009c54  lea     rax, aOpenscmanagerF; "OpenSCManager() failed hr=0x%08x.\n"
0x180009c5b  mov     [rsp+78h+var_50], ebx
0x180009c5f  lea     r9, aGetservicepid; "_GetServicePid"
0x180009c66  mov     r8d, 1D57h
0x180009c6c  mov     [rsp+78h+pcbBytesNeeded], rax
0x180009c71  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180009c78  call    cs:__imp_PuDbgPrint
0x180009c7e  jmp     loc_180009D89
0x180009c83  mov     r8d, ebx; dwDesiredAccess
0x180009c86  lea     rdx, aRpcss; "RpcSs"
0x180009c8d  mov     rcx, rsi; hSCManager
0x180009c90  call    cs:__imp_OpenServiceW
0x180009c96  mov     rdi, rax
0x180009c99  test    rax, rax
0x180009c9c  jnz     short loc_180009CF6
0x180009c9e  call    cs:__imp_GetLastError
0x180009ca4  mov     ebx, eax
0x180009ca6  test    eax, eax
0x180009ca8  jle     short loc_180009CB3
0x180009caa  movzx   ebx, ax
0x180009cad  or      ebx, 80070000h
0x180009cb3  test    byte ptr cs:g_dwDebugFlags, 3
0x180009cba  jz      loc_180009D80
0x180009cc0  mov     rcx, cs:g_pDebug
0x180009cc7  lea     rax, aOpenserviceFai; "OpenService() failed hr=0x%08x.\n"
0x180009cce  mov     [rsp+78h+var_50], ebx
0x180009cd2  lea     r9, aGetservicepid; "_GetServicePid"
0x180009cd9  mov     r8d, 1D61h
0x180009cdf  mov     [rsp+78h+pcbBytesNeeded], rax
0x180009ce4  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180009ceb  call    cs:__imp_PuDbgPrint
0x180009cf1  jmp     loc_180009D80
0x180009cf6  lea     rax, [rsp+78h+var_48]
0x180009cfb  mov     r9d, 24h ; '$'; cbBufSize
0x180009d01  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180009d06  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180009d0b  xor     edx, edx; InfoLevel
0x180009d0d  mov     rcx, rdi; hService
0x180009d10  call    cs:__imp_QueryServiceStatusEx
0x180009d16  test    eax, eax
0x180009d18  jnz     short loc_180009D6B
0x180009d1a  call    cs:__imp_GetLastError
0x180009d20  mov     ebx, eax
0x180009d22  test    eax, eax
0x180009d24  jle     short loc_180009D2F
0x180009d26  movzx   ebx, ax
0x180009d29  or      ebx, 80070000h
0x180009d2f  test    byte ptr cs:g_dwDebugFlags, 3
0x180009d36  jz      short loc_180009D77
0x180009d38  mov     rcx, cs:g_pDebug
0x180009d3f  lea     rax, aQueryservicest; "QueryServiceStatusEx() failed hr=0x%08x"...
0x180009d46  mov     [rsp+78h+var_50], ebx
0x180009d4a  lea     r9, aGetservicepid; "_GetServicePid"
0x180009d51  mov     r8d, 1D6Ch
0x180009d57  mov     [rsp+78h+pcbBytesNeeded], rax
0x180009d5c  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180009d63  call    cs:__imp_PuDbgPrint
0x180009d69  jmp     short loc_180009D77
0x180009d6b  mov     ecx, dword ptr [rsp+78h+var_30+0Ch]
0x180009d6f  xor     ebx, ebx
0x180009d71  mov     cs:?sm_dwProcessIdRpcSs@CADMCOMW@@2KA, ecx; ulong CADMCOMW::sm_dwProcessIdRpcSs
0x180009d77  mov     rcx, rdi; hSCObject
0x180009d7a  call    cs:__imp_CloseServiceHandle
0x180009d80  mov     rcx, rsi; hSCObject
0x180009d83  call    cs:__imp_CloseServiceHandle
0x180009d89  mov     eax, ebx
0x180009d8b  mov     rcx, [rsp+78h+var_18]
0x180009d90  xor     rcx, rsp; StackCookie
0x180009d93  call    __security_check_cookie
0x180009d98  lea     r11, [rsp+78h+var_8]
0x180009d9d  mov     rbx, [r11+10h]
0x180009da1  mov     rsi, [r11+18h]
0x180009da5  mov     rsp, r11
0x180009da8  pop     rdi
0x180009da9  retn
```
