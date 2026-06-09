# DfsSvcMakeStartParameterAuto(void)

- ea: `0x140019ebc`
- end: `0x14001a02f`
- name: `?DfsSvcMakeStartParameterAuto@@YAKXZ`
- size: `371`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14000be04`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140019ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019fe2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140019edd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140019edd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140019ffb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001a00a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140019ffb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001a00a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140019f14`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140019f14`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x140019fd2`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x140019fd2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140019f4a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140019f8a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140019f4a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140019f8a`

## pseudocode

```c
__int64 DfsSvcMakeStartParameterAuto(void)
{
  DWORD LastError; // ebx
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbp
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rdi
  DWORD pcbBytesNeeded; // [rsp+70h] [rbp+8h] BYREF

  LastError = 0;
  pcbBytesNeeded = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, L"DFS", 0x23u);
    v4 = v3;
    if ( v3 )
    {
      if ( QueryServiceConfigW(v3, 0, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        LastError = 6;
      }
      else
      {
        v5 = (struct _QUERY_SERVICE_CONFIGW *)operator new(pcbBytesNeeded);
        v6 = v5;
        if ( v5 )
        {
          if ( !QueryServiceConfigW(v4, v5, pcbBytesNeeded, &pcbBytesNeeded)
            || v6->dwStartType == 3 && !ChangeServiceConfigW(v4, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
          {
            LastError = GetLastError();
          }
          operator delete(v6);
        }
        else
        {
          LastError = 8;
        }
      }
      CloseServiceHandle(v4);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x140019ebc  mov     rax, rsp
0x140019ebf  mov     [rax+10h], rbx
0x140019ec3  mov     [rax+18h], rbp
0x140019ec7  mov     [rax+20h], rsi
0x140019ecb  push    rdi
0x140019ecc  sub     rsp, 60h
0x140019ed0  xor     ebx, ebx
0x140019ed2  xor     edx, edx; lpDatabaseName
0x140019ed4  xor     ecx, ecx; lpMachineName
0x140019ed6  mov     [rax+8], ebx
0x140019ed9  lea     r8d, [rbx+1]; dwDesiredAccess
0x140019edd  call    cs:__imp_OpenSCManagerW
0x140019ee4  nop     dword ptr [rax+rax+00h]
0x140019ee9  mov     rbp, rax
0x140019eec  test    rax, rax
0x140019eef  jnz     short loc_140019F04
0x140019ef1  call    cs:__imp_GetLastError
0x140019ef8  nop     dword ptr [rax+rax+00h]
0x140019efd  mov     ebx, eax
0x140019eff  jmp     loc_14001A016
0x140019f04  mov     r8d, 23h ; '#'; dwDesiredAccess
0x140019f0a  lea     rdx, ServiceName; "DFS"
0x140019f11  mov     rcx, rbp; hSCManager
0x140019f14  call    cs:__imp_OpenServiceW
0x140019f1b  nop     dword ptr [rax+rax+00h]
0x140019f20  mov     rsi, rax
0x140019f23  test    rax, rax
0x140019f26  jnz     short loc_140019F3B
0x140019f28  call    cs:__imp_GetLastError
0x140019f2f  nop     dword ptr [rax+rax+00h]
0x140019f34  mov     ebx, eax
0x140019f36  jmp     loc_14001A007
0x140019f3b  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x140019f40  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x140019f45  xor     edx, edx; lpServiceConfig
0x140019f47  mov     rcx, rsi; hService
0x140019f4a  call    cs:__imp_QueryServiceConfigW
0x140019f51  nop     dword ptr [rax+rax+00h]
0x140019f56  test    eax, eax
0x140019f58  jz      short loc_140019F64
0x140019f5a  mov     ebx, 6
0x140019f5f  jmp     loc_140019FF8
0x140019f64  mov     ecx, [rsp+68h+pcbBytesNeeded]; Size
0x140019f68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019f6d  mov     rdi, rax
0x140019f70  test    rax, rax
0x140019f73  jnz     short loc_140019F7A
0x140019f75  lea     ebx, [rax+8]
0x140019f78  jmp     short loc_140019FF8
0x140019f7a  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x140019f7f  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x140019f84  mov     rdx, rdi; lpServiceConfig
0x140019f87  mov     rcx, rsi; hService
0x140019f8a  call    cs:__imp_QueryServiceConfigW
0x140019f91  nop     dword ptr [rax+rax+00h]
0x140019f96  test    eax, eax
0x140019f98  jz      short loc_140019FE2
0x140019f9a  cmp     dword ptr [rdi+4], 3
0x140019f9e  jnz     short loc_140019FF0
0x140019fa0  mov     [rsp+68h+lpDisplayName], rbx; lpDisplayName
0x140019fa5  or      edx, 0FFFFFFFFh; dwServiceType
0x140019fa8  mov     [rsp+68h+lpPassword], rbx; lpPassword
0x140019fad  mov     r9d, edx; dwErrorControl
0x140019fb0  mov     [rsp+68h+lpServiceStartName], rbx; lpServiceStartName
0x140019fb5  mov     r8d, 2; dwStartType
0x140019fbb  mov     [rsp+68h+lpDependencies], rbx; lpDependencies
0x140019fc0  mov     rcx, rsi; hService
0x140019fc3  mov     [rsp+68h+lpdwTagId], rbx; lpdwTagId
0x140019fc8  mov     [rsp+68h+lpLoadOrderGroup], rbx; lpLoadOrderGroup
0x140019fcd  mov     [rsp+68h+lpBinaryPathName], rbx; lpBinaryPathName
0x140019fd2  call    cs:__imp_ChangeServiceConfigW
0x140019fd9  nop     dword ptr [rax+rax+00h]
0x140019fde  test    eax, eax
0x140019fe0  jnz     short loc_140019FF0
0x140019fe2  call    cs:__imp_GetLastError
0x140019fe9  nop     dword ptr [rax+rax+00h]
0x140019fee  mov     ebx, eax
0x140019ff0  mov     rcx, rdi; Block
0x140019ff3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140019ff8  mov     rcx, rsi; hSCObject
0x140019ffb  call    cs:__imp_CloseServiceHandle
0x14001a002  nop     dword ptr [rax+rax+00h]
0x14001a007  mov     rcx, rbp; hSCObject
0x14001a00a  call    cs:__imp_CloseServiceHandle
0x14001a011  nop     dword ptr [rax+rax+00h]
0x14001a016  lea     r11, [rsp+68h+var_8]
0x14001a01b  mov     eax, ebx
0x14001a01d  mov     rbx, [r11+18h]
0x14001a021  mov     rbp, [r11+20h]
0x14001a025  mov     rsi, [r11+28h]
0x14001a029  mov     rsp, r11
0x14001a02c  pop     rdi
0x14001a02d  retn
```
