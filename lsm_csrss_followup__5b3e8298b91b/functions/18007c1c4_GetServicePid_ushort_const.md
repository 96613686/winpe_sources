# GetServicePid(ushort const *)

- ea: `0x18007c1c4`
- end: `0x18007c280`
- name: `?GetServicePid@@YAKPEBG@Z`
- size: `188`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18007c448`

## callees

- `0x18004b460`
- `0x18007c1c4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007c202`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007c202`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007c1e4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007c1e4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007c24e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007c257`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007c24e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007c257`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18007c241`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18007c241`

## string_xrefs

- `0x18007c1f8`: `Termservice`

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
0x18007c1c4  mov     [rsp+arg_0], rbx
0x18007c1c9  push    rdi
0x18007c1ca  sub     rsp, 70h
0x18007c1ce  mov     rax, cs:__security_cookie
0x18007c1d5  xor     rax, rsp
0x18007c1d8  mov     [rsp+78h+var_18], rax
0x18007c1dd  xor     r8d, r8d; dwDesiredAccess
0x18007c1e0  xor     edx, edx; lpDatabaseName
0x18007c1e2  xor     ecx, ecx; lpMachineName
0x18007c1e4  call    cs:__imp_OpenSCManagerW
0x18007c1ea  mov     rbx, rax
0x18007c1ed  test    rax, rax
0x18007c1f0  jz      short loc_18007C263
0x18007c1f2  mov     r8d, 4; dwDesiredAccess
0x18007c1f8  lea     rdx, aTermservice; "Termservice"
0x18007c1ff  mov     rcx, rax; hSCManager
0x18007c202  call    cs:__imp_OpenServiceW
0x18007c208  mov     rdi, rax
0x18007c20b  test    rax, rax
0x18007c20e  jz      short loc_18007C263
0x18007c210  xor     eax, eax
0x18007c212  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18007c217  xorps   xmm0, xmm0
0x18007c21a  mov     [rsp+78h+var_20], eax
0x18007c21e  mov     [rsp+78h+var_48], eax
0x18007c222  mov     r9d, 24h ; '$'; cbBufSize
0x18007c228  lea     rax, [rsp+78h+var_48]
0x18007c22d  xor     edx, edx; InfoLevel
0x18007c22f  mov     rcx, rdi; hService
0x18007c232  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18007c237  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18007c23c  movups  [rsp+78h+var_30], xmm0
0x18007c241  call    cs:__imp_QueryServiceStatusEx
0x18007c247  test    eax, eax
0x18007c249  jz      short loc_18007C263
0x18007c24b  mov     rcx, rdi; hSCObject
0x18007c24e  call    cs:__imp_CloseServiceHandle
0x18007c254  mov     rcx, rbx; hSCObject
0x18007c257  call    cs:__imp_CloseServiceHandle
0x18007c25d  mov     eax, dword ptr [rsp+78h+var_30+0Ch]
0x18007c261  jmp     short loc_18007C265
0x18007c263  xor     eax, eax
0x18007c265  mov     rcx, [rsp+78h+var_18]
0x18007c26a  xor     rcx, rsp; StackCookie
0x18007c26d  call    __security_check_cookie
0x18007c272  mov     rbx, [rsp+78h+arg_0]
0x18007c27a  add     rsp, 70h
0x18007c27e  pop     rdi
0x18007c27f  retn
```
