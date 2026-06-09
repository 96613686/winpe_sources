# DmSvcSetServiceStartType

- ea: `0x18001ba3c`
- end: `0x18001bc0a`
- name: `DmSvcSetServiceStartType`
- size: `462`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fac0`

## callees

- `0x1800039f0`
- `0x18000ba94`
- `0x18000dc6c`
- `0x18001ba3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb6c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bb42`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bbd2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bbdd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bb42`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bbd2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bbdd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001baa2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001baa2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ba68`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ba68`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18001bb62`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18001bb62`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001bb1c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001bb1c`

## string_xrefs

- `0x18001ba98`: `dmwappushservice`
- `0x18001ba7e`: `onecoreuap\admin\dm\pushrouter\prservicecontrol\pushcontroller.cpp`
- `0x18001bab8`: `onecoreuap\admin\dm\pushrouter\prservicecontrol\pushcontroller.cpp`
- `0x18001bb2e`: `onecoreuap\admin\dm\pushrouter\prservicecontrol\pushcontroller.cpp`

## pseudocode

```c
__int64 DmSvcSetServiceStartType()
{
  SC_HANDLE v0; // rax
  const char *v1; // r9
  SC_HANDLE v2; // rdi
  SC_HANDLE v4; // rax
  const char *v5; // r9
  SC_HANDLE v6; // rbx
  unsigned int v7; // esi
  const char *v8; // r9
  signed int LastError; // eax
  __int64 v10; // r8
  int Info; // [rsp+60h] [rbp-48h] BYREF
  unsigned int v12; // [rsp+68h] [rbp-40h] BYREF
  _BYTE v13[16]; // [rsp+70h] [rbp-38h] BYREF
  int *v14; // [rsp+80h] [rbp-28h]
  __int64 v15; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v0 = OpenSCManagerW(0, 0, 1u);
  v2 = v0;
  if ( !v0 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x14,
             (int)"onecoreuap\\admin\\dm\\pushrouter\\prservicecontrol\\pushcontroller.cpp",
             v1);
  v4 = OpenServiceW(v0, L"dmwappushservice", 2u);
  v6 = v4;
  if ( v4 )
  {
    if ( ChangeServiceConfigW(v4, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      Info = 1;
      if ( ChangeServiceConfig2W(v6, 3u, &Info) )
      {
        CloseServiceHandle(v6);
        v7 = 0;
        goto LABEL_14;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
      {
        v12 = v7;
        v14 = (int *)&v12;
        v15 = 4;
        McGenEventWrite_EventWriteTransfer(
          MDM_PUSHROUTER_Context,
          PushRouterChangingPushRouterToDelayedAutoStartupTypeFailed,
          v10,
          2,
          v13);
      }
    }
    else
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x24,
             (int)"onecoreuap\\admin\\dm\\pushrouter\\prservicecontrol\\pushcontroller.cpp",
             v8);
    }
    CloseServiceHandle(v6);
  }
  else
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x17,
           (int)"onecoreuap\\admin\\dm\\pushrouter\\prservicecontrol\\pushcontroller.cpp",
           v5);
  }
LABEL_14:
  CloseServiceHandle(v2);
  return v7;
}

```

## disassembly

```asm
0x18001ba3c  mov     [rsp+arg_0], rbx
0x18001ba41  mov     [rsp+arg_8], rsi
0x18001ba46  push    rdi
0x18001ba47  sub     rsp, 0A0h
0x18001ba4e  mov     rax, cs:__security_cookie
0x18001ba55  xor     rax, rsp
0x18001ba58  mov     [rsp+0A8h+var_18], rax
0x18001ba60  xor     edx, edx; lpDatabaseName
0x18001ba62  xor     ecx, ecx; lpMachineName
0x18001ba64  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001ba68  call    cs:__imp_OpenSCManagerW
0x18001ba6e  mov     rdi, rax
0x18001ba71  test    rax, rax
0x18001ba74  jnz     short loc_18001BA92
0x18001ba76  mov     rcx, [rsp+0A8h]; this
0x18001ba7e  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\pushrouter\\prse"...
0x18001ba85  lea     edx, [rax+14h]; void *
0x18001ba88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ba8d  jmp     loc_18001BBE5
0x18001ba92  mov     r8d, 2; dwDesiredAccess
0x18001ba98  lea     rdx, ServiceName; "dmwappushservice"
0x18001ba9f  mov     rcx, rdi; hSCManager
0x18001baa2  call    cs:__imp_OpenServiceW
0x18001baa8  mov     rbx, rax
0x18001baab  test    rax, rax
0x18001baae  jnz     short loc_18001BACE
0x18001bab0  mov     rcx, [rsp+0A8h]; this
0x18001bab8  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\pushrouter\\prse"...
0x18001babf  lea     edx, [rax+17h]; void *
0x18001bac2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bac7  mov     esi, eax
0x18001bac9  jmp     loc_18001BBDA
0x18001bace  mov     [rsp+0A8h+lpDisplayName], 0; lpDisplayName
0x18001bad7  or      edx, 0FFFFFFFFh; dwServiceType
0x18001bada  mov     [rsp+0A8h+lpPassword], 0; lpPassword
0x18001bae3  mov     r9d, edx; dwErrorControl
0x18001bae6  mov     [rsp+0A8h+lpServiceStartName], 0; lpServiceStartName
0x18001baef  mov     r8d, 2; dwStartType
0x18001baf5  mov     [rsp+0A8h+lpDependencies], 0; lpDependencies
0x18001bafe  mov     rcx, rbx; hService
0x18001bb01  mov     [rsp+0A8h+lpdwTagId], 0; lpdwTagId
0x18001bb0a  mov     [rsp+0A8h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18001bb13  mov     [rsp+0A8h+lpBinaryPathName], 0; lpBinaryPathName
0x18001bb1c  call    cs:__imp_ChangeServiceConfigW
0x18001bb22  test    eax, eax
0x18001bb24  jnz     short loc_18001BB4D
0x18001bb26  mov     rcx, [rsp+0A8h]; this
0x18001bb2e  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\pushrouter\\prse"...
0x18001bb35  lea     edx, [rax+24h]; void *
0x18001bb38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bb3d  mov     esi, eax
0x18001bb3f  mov     rcx, rbx; hSCObject
0x18001bb42  call    cs:__imp_CloseServiceHandle
0x18001bb48  jmp     loc_18001BBDA
0x18001bb4d  lea     r8, [rsp+0A8h+Info]; lpInfo
0x18001bb52  mov     [rsp+0A8h+Info], 1
0x18001bb5a  mov     edx, 3; dwInfoLevel
0x18001bb5f  mov     rcx, rbx; hService
0x18001bb62  call    cs:__imp_ChangeServiceConfig2W
0x18001bb68  test    eax, eax
0x18001bb6a  jnz     short loc_18001BBCF
0x18001bb6c  call    cs:__imp_GetLastError
0x18001bb72  mov     esi, eax
0x18001bb74  test    eax, eax
0x18001bb76  jle     short loc_18001BB81
0x18001bb78  movzx   esi, ax
0x18001bb7b  or      esi, 80070000h
0x18001bb81  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18001bb88  jz      short loc_18001BB3F
0x18001bb8a  lea     rax, [rsp+0A8h+var_40]
0x18001bb8f  mov     [rsp+0A8h+var_40], esi
0x18001bb93  mov     [rsp+0A8h+var_28], rax
0x18001bb9b  lea     rdx, PushRouterChangingPushRouterToDelayedAutoStartupTypeFailed
0x18001bba2  lea     rax, [rsp+0A8h+var_38]
0x18001bba7  mov     [rsp+0A8h+var_20], 4
0x18001bbb3  mov     r9d, 2
0x18001bbb9  mov     [rsp+0A8h+lpBinaryPathName], rax
0x18001bbbe  lea     rcx, MDM_PUSHROUTER_Context
0x18001bbc5  call    McGenEventWrite_EventWriteTransfer
0x18001bbca  jmp     loc_18001BB3F
0x18001bbcf  mov     rcx, rbx; hSCObject
0x18001bbd2  call    cs:__imp_CloseServiceHandle
0x18001bbd8  xor     esi, esi
0x18001bbda  mov     rcx, rdi; hSCObject
0x18001bbdd  call    cs:__imp_CloseServiceHandle
0x18001bbe3  mov     eax, esi
0x18001bbe5  mov     rcx, [rsp+0A8h+var_18]
0x18001bbed  xor     rcx, rsp; StackCookie
0x18001bbf0  call    __security_check_cookie
0x18001bbf5  lea     r11, [rsp+0A8h+var_8]
0x18001bbfd  mov     rbx, [r11+10h]
0x18001bc01  mov     rsi, [r11+18h]
0x18001bc05  mov     rsp, r11
0x18001bc08  pop     rdi
0x18001bc09  retn
```
