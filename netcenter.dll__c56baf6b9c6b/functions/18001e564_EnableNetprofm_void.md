# EnableNetprofm(void)

- ea: `0x18001e564`
- end: `0x18001e668`
- name: `?EnableNetprofm@@YAJXZ`
- size: `260`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001adb0`

## callees

- `0x180010e9c`
- `0x18001e564`
- `0x18001eda8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e633`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e645`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e633`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001e645`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e57d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001e57d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e59f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001e59f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001e61f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001e61f`

## pseudocode

```c
__int64 EnableNetprofm(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  unsigned int started; // ebx
  unsigned int v6; // [rsp+70h] [rbp+8h] BYREF

  v0 = OpenSCManagerW(0, 0, 0x80000008);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"netprofm", 3u);
    v3 = v2;
    if ( v2 )
    {
      v6 = 0;
      started = QueryServiceStartType(v2, &v6);
      if ( !started && v6 == 4 && !ChangeServiceConfigW(v3, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
        started = ResultFromKnownLastError();
      CloseServiceHandle(v3);
    }
    else
    {
      started = ResultFromKnownLastError();
    }
    CloseServiceHandle(v1);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return started;
}

```

## disassembly

```asm
0x18001e564  mov     [rsp+arg_8], rbx
0x18001e569  mov     [rsp+arg_10], rsi
0x18001e56e  push    rdi
0x18001e56f  sub     rsp, 60h
0x18001e573  xor     edx, edx; lpDatabaseName
0x18001e575  xor     ecx, ecx; lpMachineName
0x18001e577  mov     r8d, 80000008h; dwDesiredAccess
0x18001e57d  call    cs:__imp_OpenSCManagerW
0x18001e583  mov     rsi, rax
0x18001e586  test    rax, rax
0x18001e589  jz      loc_18001E64D
0x18001e58f  mov     r8d, 3; dwDesiredAccess
0x18001e595  lea     rdx, ServiceName; "netprofm"
0x18001e59c  mov     rcx, rax; hSCManager
0x18001e59f  call    cs:__imp_OpenServiceW
0x18001e5a5  mov     rdi, rax
0x18001e5a8  test    rax, rax
0x18001e5ab  jz      loc_18001E63B
0x18001e5b1  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x18001e5b6  mov     [rsp+68h+arg_0], 0
0x18001e5be  mov     rcx, rax; hService
0x18001e5c1  call    ?QueryServiceStartType@@YAJPEAUSC_HANDLE__@@PEAK@Z; QueryServiceStartType(SC_HANDLE__ *,ulong *)
0x18001e5c6  mov     ebx, eax
0x18001e5c8  test    eax, eax
0x18001e5ca  jnz     short loc_18001E630
0x18001e5cc  cmp     [rsp+68h+arg_0], 4
0x18001e5d1  jnz     short loc_18001E630
0x18001e5d3  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18001e5dc  lea     r8d, [rax+2]; dwStartType
0x18001e5e0  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18001e5e9  or      edx, 0FFFFFFFFh; dwServiceType
0x18001e5ec  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18001e5f5  mov     r9d, edx; dwErrorControl
0x18001e5f8  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18001e601  mov     rcx, rdi; hService
0x18001e604  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18001e60d  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18001e616  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18001e61f  call    cs:__imp_ChangeServiceConfigW
0x18001e625  test    eax, eax
0x18001e627  jnz     short loc_18001E630
0x18001e629  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e62e  mov     ebx, eax
0x18001e630  mov     rcx, rdi; hSCObject
0x18001e633  call    cs:__imp_CloseServiceHandle
0x18001e639  jmp     short loc_18001E642
0x18001e63b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e640  mov     ebx, eax
0x18001e642  mov     rcx, rsi; hSCObject
0x18001e645  call    cs:__imp_CloseServiceHandle
0x18001e64b  jmp     short loc_18001E654
0x18001e64d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e652  mov     ebx, eax
0x18001e654  lea     r11, [rsp+68h+var_8]
0x18001e659  mov     eax, ebx
0x18001e65b  mov     rbx, [r11+18h]
0x18001e65f  mov     rsi, [r11+20h]
0x18001e663  mov     rsp, r11
0x18001e666  pop     rdi
0x18001e667  retn
```
