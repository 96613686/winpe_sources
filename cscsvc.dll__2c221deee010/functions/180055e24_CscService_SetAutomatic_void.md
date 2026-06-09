# CscService_SetAutomatic(void)

- ea: `0x180055e24`
- end: `0x180055fc0`
- name: `?CscService_SetAutomatic@@YAJXZ`
- size: `412`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800563e0`

## callees

- `0x180036394`
- `0x18003c460`
- `0x180055e24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f6d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180055e9a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180055e9a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180055ee2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180055fa2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180055ee2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180055fa2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180055e39`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180055e39`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180055f3c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180055f3c`

## string_xrefs

- `0x180055e8e`: `CscService`

## pseudocode

```c
__int64 CscService_SetAutomatic(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD LastError; // eax
  signed int v3; // ebx
  SC_HANDLE v4; // rbp
  DWORD v5; // eax
  bool v6; // cc
  DWORD v7; // eax

  v0 = OpenSCManagerW(0, 0, 0x40000000u);
  v1 = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, LastError);
LABEL_18:
    v6 = v3 <= 0;
    goto LABEL_19;
  }
  v3 = 0;
  v4 = OpenServiceW(v0, L"CscService", 0x40000000u);
  if ( !v4 )
  {
    v5 = GetLastError();
    v3 = v5;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, v5);
  }
  CloseServiceHandle(v1);
  v6 = v3 <= 0;
  if ( !v3 )
  {
    if ( ChangeServiceConfigW(v4, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
    }
    else
    {
      v7 = GetLastError();
      v3 = v7;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, v7);
    }
    CloseServiceHandle(v4);
    goto LABEL_18;
  }
LABEL_19:
  if ( !v6 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180055e24  push    rbx
0x180055e26  push    rbp
0x180055e27  push    rsi
0x180055e28  push    rdi
0x180055e29  sub     rsp, 68h
0x180055e2d  mov     edi, 40000000h
0x180055e32  xor     edx, edx; lpDatabaseName
0x180055e34  mov     r8d, edi; dwDesiredAccess
0x180055e37  xor     ecx, ecx; lpMachineName
0x180055e39  call    cs:__imp_OpenSCManagerW
0x180055e3f  mov     rsi, rax
0x180055e42  test    rax, rax
0x180055e45  jnz     short loc_180055E8B
0x180055e47  call    cs:__imp_GetLastError
0x180055e4d  mov     ebx, eax
0x180055e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e56  lea     rdi, WPP_GLOBAL_Control
0x180055e5d  cmp     rcx, rdi
0x180055e60  jz      loc_180055FA8
0x180055e66  test    byte ptr [rcx+1Ch], 8
0x180055e6a  jz      loc_180055FA8
0x180055e70  mov     rcx, [rcx+10h]
0x180055e74  lea     edx, [rsi+17h]
0x180055e77  mov     r9d, eax
0x180055e7a  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180055e81  call    WPP_SF_d
0x180055e86  jmp     loc_180055FA8
0x180055e8b  mov     r8d, edi; dwDesiredAccess
0x180055e8e  lea     rdx, ServiceName; "CscService"
0x180055e95  mov     rcx, rsi; hSCManager
0x180055e98  xor     ebx, ebx
0x180055e9a  call    cs:__imp_OpenServiceW
0x180055ea0  lea     rdi, WPP_GLOBAL_Control
0x180055ea7  mov     rbp, rax
0x180055eaa  test    rax, rax
0x180055ead  jnz     short loc_180055EDF
0x180055eaf  call    cs:__imp_GetLastError
0x180055eb5  mov     ebx, eax
0x180055eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ebe  cmp     rcx, rdi
0x180055ec1  jz      short loc_180055EDF
0x180055ec3  test    byte ptr [rcx+1Ch], 8
0x180055ec7  jz      short loc_180055EDF
0x180055ec9  mov     rcx, [rcx+10h]
0x180055ecd  lea     edx, [rbp+18h]
0x180055ed0  mov     r9d, eax
0x180055ed3  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180055eda  call    WPP_SF_d
0x180055edf  mov     rcx, rsi; hSCObject
0x180055ee2  call    cs:__imp_CloseServiceHandle
0x180055ee8  test    ebx, ebx
0x180055eea  jnz     loc_180055FAA
0x180055ef0  mov     [rsp+88h+lpDisplayName], 0; lpDisplayName
0x180055ef9  lea     r8d, [rbx+2]; dwStartType
0x180055efd  mov     [rsp+88h+lpPassword], 0; lpPassword
0x180055f06  or      edx, 0FFFFFFFFh; dwServiceType
0x180055f09  mov     [rsp+88h+lpServiceStartName], 0; lpServiceStartName
0x180055f12  mov     r9d, edx; dwErrorControl
0x180055f15  mov     [rsp+88h+lpDependencies], 0; lpDependencies
0x180055f1e  mov     rcx, rbp; hService
0x180055f21  mov     [rsp+88h+lpdwTagId], 0; lpdwTagId
0x180055f2a  mov     [rsp+88h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180055f33  mov     [rsp+88h+lpBinaryPathName], 0; lpBinaryPathName
0x180055f3c  call    cs:__imp_ChangeServiceConfigW
0x180055f42  test    eax, eax
0x180055f44  jz      short loc_180055F6D
0x180055f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f4d  cmp     rcx, rdi
0x180055f50  jz      short loc_180055F9F
0x180055f52  test    byte ptr [rcx+1Ch], 8
0x180055f56  jz      short loc_180055F9F
0x180055f58  mov     rcx, [rcx+10h]
0x180055f5c  lea     edx, [rbx+19h]
0x180055f5f  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180055f66  call    WPP_SF_
0x180055f6b  jmp     short loc_180055F9F
0x180055f6d  call    cs:__imp_GetLastError
0x180055f73  mov     ebx, eax
0x180055f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f7c  cmp     rcx, rdi
0x180055f7f  jz      short loc_180055F9F
0x180055f81  test    byte ptr [rcx+1Ch], 8
0x180055f85  jz      short loc_180055F9F
0x180055f87  mov     rcx, [rcx+10h]
0x180055f8b  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180055f92  mov     edx, 1Ah
0x180055f97  mov     r9d, eax
0x180055f9a  call    WPP_SF_d
0x180055f9f  mov     rcx, rbp; hSCObject
0x180055fa2  call    cs:__imp_CloseServiceHandle
0x180055fa8  test    ebx, ebx
0x180055faa  jle     short loc_180055FB5
0x180055fac  movzx   ebx, bx
0x180055faf  or      ebx, 80070000h
0x180055fb5  mov     eax, ebx
0x180055fb7  add     rsp, 68h
0x180055fbb  pop     rdi
0x180055fbc  pop     rsi
0x180055fbd  pop     rbp
0x180055fbe  pop     rbx
0x180055fbf  retn
```
