# ServerConfiguredToStart(SC_HANDLE__ *)

- ea: `0x18002b688`
- end: `0x18002b71d`
- name: `?ServerConfiguredToStart@@YAHPEAUSC_HANDLE__@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002b4e4`

## callees

- `0x1800254e0`
- `0x18002b688`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002b6b4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002b6b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b6f0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b6f0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002b6db`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18002b6db`

## pseudocode

```c
__int64 __fastcall ServerConfiguredToStart(SC_HANDLE a1)
{
  SC_HANDLE v1; // rax
  unsigned int v2; // ebx
  SC_HANDLE v3; // rdi
  DWORD pcbBytesNeeded[4]; // [rsp+20h] [rbp-428h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+30h] [rbp-418h] BYREF

  v1 = OpenServiceW(a1, L"LanmanServer", 1u);
  v2 = 0;
  v3 = v1;
  if ( !v1 )
    return 0;
  pcbBytesNeeded[0] = 0;
  if ( !QueryServiceConfigW(v1, &ServiceConfig, 0x400u, pcbBytesNeeded) )
    return 0;
  LOBYTE(v2) = ServiceConfig.dwStartType == 2;
  CloseServiceHandle(v3);
  return v2;
}

```

## disassembly

```asm
0x18002b688  mov     [rsp+arg_8], rbx
0x18002b68d  push    rdi
0x18002b68e  sub     rsp, 440h
0x18002b695  mov     rax, cs:__security_cookie
0x18002b69c  xor     rax, rsp
0x18002b69f  mov     [rsp+448h+var_18], rax
0x18002b6a7  mov     r8d, 1; dwDesiredAccess
0x18002b6ad  lea     rdx, ServiceName; "LanmanServer"
0x18002b6b4  call    cs:__imp_OpenServiceW
0x18002b6ba  xor     ebx, ebx
0x18002b6bc  mov     rdi, rax
0x18002b6bf  test    rax, rax
0x18002b6c2  jz      short loc_18002B6FA
0x18002b6c4  lea     r9, [rsp+448h+pcbBytesNeeded]; pcbBytesNeeded
0x18002b6c9  mov     [rsp+448h+pcbBytesNeeded], ebx
0x18002b6cd  mov     r8d, 400h; cbBufSize
0x18002b6d3  lea     rdx, [rsp+448h+ServiceConfig]; lpServiceConfig
0x18002b6d8  mov     rcx, rax; hService
0x18002b6db  call    cs:__imp_QueryServiceConfigW
0x18002b6e1  test    eax, eax
0x18002b6e3  jz      short loc_18002B6FA
0x18002b6e5  cmp     [rsp+448h+ServiceConfig.dwStartType], 2
0x18002b6ea  mov     rcx, rdi; hSCObject
0x18002b6ed  setz    bl
0x18002b6f0  call    cs:__imp_CloseServiceHandle
0x18002b6f6  mov     eax, ebx
0x18002b6f8  jmp     short loc_18002B6FC
0x18002b6fa  xor     eax, eax
0x18002b6fc  mov     rcx, [rsp+448h+var_18]
0x18002b704  xor     rcx, rsp; StackCookie
0x18002b707  call    __security_check_cookie
0x18002b70c  mov     rbx, [rsp+448h+arg_8]
0x18002b714  add     rsp, 440h
0x18002b71b  pop     rdi
0x18002b71c  retn
```
