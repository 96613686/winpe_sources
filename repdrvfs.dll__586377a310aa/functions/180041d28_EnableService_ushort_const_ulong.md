# EnableService(ushort const *,ulong)

- ea: `0x180041d28`
- end: `0x180041e31`
- name: `?EnableService@@YAJPEBGK@Z`
- size: `265`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800411c0`
- `0x180041610`

## callees

- `0x180041d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e0a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041d41`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180041d41`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041de2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041e02`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041de2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180041e02`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041d63`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180041d63`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180041dbc`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180041dbc`

## pseudocode

```c
__int64 __fastcall EnableService(const unsigned __int16 *a1, DWORD a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  unsigned int v7; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  signed int v10; // eax

  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"WinMgmt", 2u);
    v6 = v5;
    if ( v5 )
    {
      if ( ChangeServiceConfigW(v5, 0xFFFFFFFF, a2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        v7 = 0;
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v6);
    }
    else
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x180041d28  mov     [rsp+arg_0], rbx
0x180041d2d  mov     [rsp+arg_8], rsi
0x180041d32  push    rdi
0x180041d33  sub     rsp, 60h
0x180041d37  mov     ebx, edx
0x180041d39  xor     ecx, ecx; lpMachineName
0x180041d3b  xor     edx, edx; lpDatabaseName
0x180041d3d  lea     r8d, [rdx+1]; dwDesiredAccess
0x180041d41  call    cs:__imp_OpenSCManagerW
0x180041d47  mov     rsi, rax
0x180041d4a  test    rax, rax
0x180041d4d  jz      loc_180041E0A
0x180041d53  mov     r8d, 2; dwDesiredAccess
0x180041d59  lea     rdx, ServiceName; "WinMgmt"
0x180041d60  mov     rcx, rax; hSCManager
0x180041d63  call    cs:__imp_OpenServiceW
0x180041d69  mov     rdi, rax
0x180041d6c  test    rax, rax
0x180041d6f  jz      short loc_180041DEA
0x180041d71  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x180041d7a  or      edx, 0FFFFFFFFh; dwServiceType
0x180041d7d  mov     [rsp+68h+lpPassword], 0; lpPassword
0x180041d86  mov     r9d, edx; dwErrorControl
0x180041d89  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x180041d92  mov     r8d, ebx; dwStartType
0x180041d95  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x180041d9e  mov     rcx, rax; hService
0x180041da1  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x180041daa  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180041db3  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x180041dbc  call    cs:__imp_ChangeServiceConfigW
0x180041dc2  test    eax, eax
0x180041dc4  jz      short loc_180041DCA
0x180041dc6  xor     ebx, ebx
0x180041dc8  jmp     short loc_180041DDF
0x180041dca  call    cs:__imp_GetLastError
0x180041dd0  mov     ebx, eax
0x180041dd2  test    eax, eax
0x180041dd4  jle     short loc_180041DDF
0x180041dd6  movzx   ebx, ax
0x180041dd9  or      ebx, 80070000h
0x180041ddf  mov     rcx, rdi; hSCObject
0x180041de2  call    cs:__imp_CloseServiceHandle
0x180041de8  jmp     short loc_180041DFF
0x180041dea  call    cs:__imp_GetLastError
0x180041df0  mov     ebx, eax
0x180041df2  test    eax, eax
0x180041df4  jle     short loc_180041DFF
0x180041df6  movzx   ebx, ax
0x180041df9  or      ebx, 80070000h
0x180041dff  mov     rcx, rsi; hSCObject
0x180041e02  call    cs:__imp_CloseServiceHandle
0x180041e08  jmp     short loc_180041E1F
0x180041e0a  call    cs:__imp_GetLastError
0x180041e10  mov     ebx, eax
0x180041e12  test    eax, eax
0x180041e14  jle     short loc_180041E1F
0x180041e16  movzx   ebx, ax
0x180041e19  or      ebx, 80070000h
0x180041e1f  mov     rsi, [rsp+68h+arg_8]
0x180041e24  mov     eax, ebx
0x180041e26  mov     rbx, [rsp+68h+arg_0]
0x180041e2b  add     rsp, 60h
0x180041e2f  pop     rdi
0x180041e30  retn
```
