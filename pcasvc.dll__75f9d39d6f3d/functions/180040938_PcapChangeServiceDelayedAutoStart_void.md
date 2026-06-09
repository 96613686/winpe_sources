# PcapChangeServiceDelayedAutoStart(void)

- ea: `0x180040938`
- end: `0x180040af0`
- name: `?PcapChangeServiceDelayedAutoStart@@YAHXZ`
- size: `440`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001d030`

## callees

- `0x180012920`
- `0x180040938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ab0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004095a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004095a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040ace`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040ad7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040ace`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180040ad7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800409a1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800409a1`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180040aa6`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180040aa6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800409fa`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800409fa`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180040a6f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180040a6f`

## string_xrefs

- `0x180040980`: `PcapChangeServiceDelayedAutoStart`
- `0x1800409c7`: `PcapChangeServiceDelayedAutoStart`
- `0x180040a17`: `PcapChangeServiceDelayedAutoStart`
- `0x18004096e`: `OpenSCManager failed %d`
- `0x180040a0a`: `QueryServiceConfig2 failed %d`
- `0x1800409b5`: `OpenService failed %d`
- `0x180040ab6`: `ChangeServiceConfig2 failed %d`
- `0x180040a7f`: `ChangeServiceConfig failed %d`

## pseudocode

```c
__int64 PcapChangeServiceDelayedAutoStart(void)
{
  unsigned int v0; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rdi
  const char *v4; // r9
  int v5; // r8d
  int Buffer; // [rsp+80h] [rbp+8h] BYREF
  DWORD pcbBytesNeeded; // [rsp+88h] [rbp+10h] BYREF

  v0 = 0;
  Buffer = 0;
  pcbBytesNeeded = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"PcaSvc", 3u);
    if ( !v3 )
    {
      GetLastError();
      AslLogCallPrintf(1, (unsigned int)"PcapChangeServiceDelayedAutoStart", 67, (unsigned int)"OpenService failed %d");
LABEL_15:
      CloseServiceHandle(v2);
      return v0;
    }
    if ( !QueryServiceConfig2W(v3, 3u, (LPBYTE)&Buffer, 4u, &pcbBytesNeeded) )
    {
      GetLastError();
      v4 = "QueryServiceConfig2 failed %d";
      v5 = 76;
LABEL_7:
      AslLogCallPrintf(1, (unsigned int)"PcapChangeServiceDelayedAutoStart", v5, (_DWORD)v4);
LABEL_14:
      CloseServiceHandle(v3);
      goto LABEL_15;
    }
    if ( Buffer != 1 )
    {
      if ( !ChangeServiceConfigW(v3, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        GetLastError();
        v4 = "ChangeServiceConfig failed %d";
        v5 = 96;
        goto LABEL_7;
      }
      Buffer = 1;
      if ( !ChangeServiceConfig2W(v3, 3u, &Buffer) )
      {
        GetLastError();
        v4 = "ChangeServiceConfig2 failed %d";
        v5 = 102;
        goto LABEL_7;
      }
    }
    v0 = 1;
    goto LABEL_14;
  }
  GetLastError();
  AslLogCallPrintf(1, (unsigned int)"PcapChangeServiceDelayedAutoStart", 61, (unsigned int)"OpenSCManager failed %d");
  return v0;
}

```

## disassembly

```asm
0x180040938  mov     rax, rsp
0x18004093b  mov     [rax+18h], rbx
0x18004093f  push    rsi
0x180040940  push    rdi
0x180040941  push    r14
0x180040943  sub     rsp, 60h
0x180040947  xor     ebx, ebx
0x180040949  xor     edx, edx; lpDatabaseName
0x18004094b  xor     ecx, ecx; lpMachineName
0x18004094d  mov     [rax+8], ebx
0x180040950  mov     [rax+10h], ebx
0x180040953  lea     r14d, [rbx+1]
0x180040957  mov     r8d, r14d; dwDesiredAccess
0x18004095a  call    cs:__imp_OpenSCManagerW
0x180040960  mov     rsi, rax
0x180040963  test    rax, rax
0x180040966  jnz     short loc_180040991
0x180040968  call    cs:__imp_GetLastError
0x18004096e  lea     r9, aOpenscmanagerF; "OpenSCManager failed %d"
0x180040975  mov     ecx, r14d
0x180040978  lea     r8d, [rbx+3Dh]
0x18004097c  mov     dword ptr [rsp+78h+pcbBytesNeeded], eax
0x180040980  lea     rdx, aPcapchangeserv; "PcapChangeServiceDelayedAutoStart"
0x180040987  call    AslLogCallPrintf
0x18004098c  jmp     loc_180040ADD
0x180040991  mov     r8d, 3; dwDesiredAccess
0x180040997  lea     rdx, Annotation; "PcaSvc"
0x18004099e  mov     rcx, rsi; hSCManager
0x1800409a1  call    cs:__imp_OpenServiceW
0x1800409a7  mov     rdi, rax
0x1800409aa  test    rax, rax
0x1800409ad  jnz     short loc_1800409D8
0x1800409af  call    cs:__imp_GetLastError
0x1800409b5  lea     r9, aOpenserviceFai; "OpenService failed %d"
0x1800409bc  mov     ecx, r14d
0x1800409bf  lea     r8d, [rdi+43h]
0x1800409c3  mov     dword ptr [rsp+78h+pcbBytesNeeded], eax
0x1800409c7  lea     rdx, aPcapchangeserv; "PcapChangeServiceDelayedAutoStart"
0x1800409ce  call    AslLogCallPrintf
0x1800409d3  jmp     loc_180040AD4
0x1800409d8  mov     r9d, 4; cbBufSize
0x1800409de  lea     rax, [rsp+78h+arg_8]
0x1800409e6  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x1800409ee  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800409f3  mov     rcx, rdi; hService
0x1800409f6  lea     edx, [r9-1]; dwInfoLevel
0x1800409fa  call    cs:__imp_QueryServiceConfig2W
0x180040a00  test    eax, eax
0x180040a02  jnz     short loc_180040A2F
0x180040a04  call    cs:__imp_GetLastError
0x180040a0a  lea     r9, aQueryserviceco_0; "QueryServiceConfig2 failed %d"
0x180040a11  mov     r8d, 4Ch ; 'L'
0x180040a17  lea     rdx, aPcapchangeserv; "PcapChangeServiceDelayedAutoStart"
0x180040a1e  mov     dword ptr [rsp+78h+pcbBytesNeeded], eax
0x180040a22  mov     ecx, r14d
0x180040a25  call    AslLogCallPrintf
0x180040a2a  jmp     loc_180040ACB
0x180040a2f  cmp     [rsp+78h+Buffer], r14d
0x180040a37  jz      loc_180040AC8
0x180040a3d  mov     [rsp+78h+lpDisplayName], rbx; lpDisplayName
0x180040a42  or      edx, 0FFFFFFFFh; dwServiceType
0x180040a45  mov     [rsp+78h+lpPassword], rbx; lpPassword
0x180040a4a  mov     r9d, edx; dwErrorControl
0x180040a4d  mov     [rsp+78h+lpServiceStartName], rbx; lpServiceStartName
0x180040a52  mov     r8d, 2; dwStartType
0x180040a58  mov     [rsp+78h+lpDependencies], rbx; lpDependencies
0x180040a5d  mov     rcx, rdi; hService
0x180040a60  mov     [rsp+78h+lpdwTagId], rbx; lpdwTagId
0x180040a65  mov     [rsp+78h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x180040a6a  mov     [rsp+78h+pcbBytesNeeded], rbx; lpBinaryPathName
0x180040a6f  call    cs:__imp_ChangeServiceConfigW
0x180040a75  test    eax, eax
0x180040a77  jnz     short loc_180040A8E
0x180040a79  call    cs:__imp_GetLastError
0x180040a7f  lea     r9, aChangeservicec_1; "ChangeServiceConfig failed %d"
0x180040a86  mov     r8d, 60h ; '`'
0x180040a8c  jmp     short loc_180040A17
0x180040a8e  lea     r8, [rsp+78h+Buffer]; lpInfo
0x180040a96  mov     [rsp+78h+Buffer], r14d
0x180040a9e  mov     edx, 3; dwInfoLevel
0x180040aa3  mov     rcx, rdi; hService
0x180040aa6  call    cs:__imp_ChangeServiceConfig2W
0x180040aac  test    eax, eax
0x180040aae  jnz     short loc_180040AC8
0x180040ab0  call    cs:__imp_GetLastError
0x180040ab6  lea     r9, aChangeservicec_2; "ChangeServiceConfig2 failed %d"
0x180040abd  mov     r8d, 66h ; 'f'
0x180040ac3  jmp     loc_180040A17
0x180040ac8  mov     ebx, r14d
0x180040acb  mov     rcx, rdi; hSCObject
0x180040ace  call    cs:__imp_CloseServiceHandle
0x180040ad4  mov     rcx, rsi; hSCObject
0x180040ad7  call    cs:__imp_CloseServiceHandle
0x180040add  mov     eax, ebx
0x180040adf  mov     rbx, [rsp+78h+arg_10]
0x180040ae7  add     rsp, 60h
0x180040aeb  pop     r14
0x180040aed  pop     rdi
0x180040aee  pop     rsi
0x180040aef  retn
```
