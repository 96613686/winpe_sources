# GetServicePid(ushort const *)

- ea: `0x180080ad8`
- end: `0x180080bb7`
- name: `?GetServicePid@@YAKPEBG@Z`
- size: `223`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180080d9c`

## callees

- `0x18004e850`
- `0x180080ad8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180080b20`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180080b20`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180080af8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180080af8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080b78`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080b87`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080b78`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080b87`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180080b65`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180080b65`

## string_xrefs

- `0x180080b16`: `Termservice`

## pseudocode

```c
__int64 __fastcall GetServicePid(const unsigned __int16 *a1)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  SC_HANDLE v3; // rdi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  v1 = OpenSCManagerW(0, 0, 0);
  v2 = v1;
  if ( !v1 )
    return 0;
  v3 = OpenServiceW(v1, L"Termservice", 4u);
  if ( !v3 )
    return 0;
  v8 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v7 = 0;
  if ( !QueryServiceStatusEx(v3, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    return 0;
  CloseServiceHandle(v3);
  CloseServiceHandle(v2);
  return HIDWORD(v7);
}

```

## disassembly

```asm
0x180080ad8  mov     [rsp+arg_0], rbx
0x180080add  push    rdi
0x180080ade  sub     rsp, 70h
0x180080ae2  mov     rax, cs:__security_cookie
0x180080ae9  xor     rax, rsp
0x180080aec  mov     [rsp+78h+var_18], rax
0x180080af1  xor     r8d, r8d; dwDesiredAccess
0x180080af4  xor     edx, edx; lpDatabaseName
0x180080af6  xor     ecx, ecx; lpMachineName
0x180080af8  call    cs:__imp_OpenSCManagerW
0x180080aff  nop     dword ptr [rax+rax+00h]
0x180080b04  mov     rbx, rax
0x180080b07  test    rax, rax
0x180080b0a  jz      loc_180080B99
0x180080b10  mov     r8d, 4; dwDesiredAccess
0x180080b16  lea     rdx, aTermservice; "Termservice"
0x180080b1d  mov     rcx, rax; hSCManager
0x180080b20  call    cs:__imp_OpenServiceW
0x180080b27  nop     dword ptr [rax+rax+00h]
0x180080b2c  mov     rdi, rax
0x180080b2f  test    rax, rax
0x180080b32  jz      short loc_180080B99
0x180080b34  xor     eax, eax
0x180080b36  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180080b3b  xorps   xmm0, xmm0
0x180080b3e  mov     [rsp+78h+var_20], eax
0x180080b42  mov     [rsp+78h+var_48], eax
0x180080b46  mov     r9d, 24h ; '$'; cbBufSize
0x180080b4c  lea     rax, [rsp+78h+var_48]
0x180080b51  xor     edx, edx; InfoLevel
0x180080b53  mov     rcx, rdi; hService
0x180080b56  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180080b5b  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180080b60  movups  [rsp+78h+var_30], xmm0
0x180080b65  call    cs:__imp_QueryServiceStatusEx
0x180080b6c  nop     dword ptr [rax+rax+00h]
0x180080b71  test    eax, eax
0x180080b73  jz      short loc_180080B99
0x180080b75  mov     rcx, rdi; hSCObject
0x180080b78  call    cs:__imp_CloseServiceHandle
0x180080b7f  nop     dword ptr [rax+rax+00h]
0x180080b84  mov     rcx, rbx; hSCObject
0x180080b87  call    cs:__imp_CloseServiceHandle
0x180080b8e  nop     dword ptr [rax+rax+00h]
0x180080b93  mov     eax, dword ptr [rsp+78h+var_30+0Ch]
0x180080b97  jmp     short loc_180080B9B
0x180080b99  xor     eax, eax
0x180080b9b  mov     rcx, [rsp+78h+var_18]
0x180080ba0  xor     rcx, rsp; StackCookie
0x180080ba3  call    __security_check_cookie
0x180080ba8  mov     rbx, [rsp+78h+arg_0]
0x180080bb0  add     rsp, 70h
0x180080bb4  pop     rdi
0x180080bb5  retn
```
