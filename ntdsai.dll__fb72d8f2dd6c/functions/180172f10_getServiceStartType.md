# getServiceStartType

- ea: `0x180172f10`
- end: `0x180172ff3`
- name: `getServiceStartType`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800b5290`

## callees

- `0x180172f10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180172fe2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180172fe2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180172f95`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180172f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172fbd`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180172f5d`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180172f5d`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180172f34`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180172f34`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172f80`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172fb3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172f80`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172fb3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172fcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172fd4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172fcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172fd4`

## pseudocode

```c
__int64 __fastcall getServiceStartType(__int64 a1)
{
  unsigned int dwStartType; // ebp
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  struct _QUERY_SERVICE_CONFIGA *v4; // rbx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  struct _QUERY_SERVICE_CONFIGA *v7; // rax
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]

  v10 = HIDWORD(a1);
  pcbBytesNeeded = 0;
  dwStartType = 2;
  v2 = OpenSCManagerA(0, 0, 0xF003Fu);
  v3 = v2;
  if ( v2 )
  {
    v4 = 0;
    v5 = OpenServiceA(v2, "ADWS", 1u);
    v6 = v5;
    if ( v5 )
    {
      QueryServiceConfigA(v5, 0, 0, &pcbBytesNeeded);
      if ( GetLastError() == 122 )
      {
        v7 = (struct _QUERY_SERVICE_CONFIGA *)malloc(pcbBytesNeeded);
        v4 = v7;
        if ( v7 )
        {
          if ( QueryServiceConfigA(v6, v7, pcbBytesNeeded, &pcbBytesNeeded) )
            dwStartType = v4->dwStartType;
          else
            GetLastError();
        }
      }
      CloseServiceHandle(v6);
    }
    else
    {
      GetLastError();
    }
    CloseServiceHandle(v3);
    if ( v4 )
      free(v4);
  }
  else
  {
    GetLastError();
  }
  return dwStartType;
}

```

## disassembly

```asm
0x180172f10  mov     qword ptr [rsp+pcbBytesNeeded], rcx
0x180172f15  push    rbx
0x180172f16  push    rbp
0x180172f17  push    rsi
0x180172f18  push    rdi
0x180172f19  sub     rsp, 28h
0x180172f1d  xor     edx, edx; lpDatabaseName
0x180172f1f  mov     [rsp+48h+pcbBytesNeeded], 0
0x180172f27  xor     ecx, ecx; lpMachineName
0x180172f29  mov     r8d, 0F003Fh; dwDesiredAccess
0x180172f2f  mov     ebp, 2
0x180172f34  call    cs:__imp_OpenSCManagerA
0x180172f3a  mov     rsi, rax
0x180172f3d  test    rax, rax
0x180172f40  jnz     short loc_180172F4D
0x180172f42  call    cs:__imp_GetLastError
0x180172f48  jmp     loc_180172FE8
0x180172f4d  xor     ebx, ebx
0x180172f4f  lea     rdx, aAdws; "ADWS"
0x180172f56  mov     rcx, rsi; hSCManager
0x180172f59  lea     r8d, [rbx+1]; dwDesiredAccess
0x180172f5d  call    cs:__imp_OpenServiceA
0x180172f63  mov     rdi, rax
0x180172f66  test    rax, rax
0x180172f69  jnz     short loc_180172F73
0x180172f6b  call    cs:__imp_GetLastError
0x180172f71  jmp     short loc_180172FD1
0x180172f73  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x180172f78  xor     r8d, r8d; cbBufSize
0x180172f7b  xor     edx, edx; lpServiceConfig
0x180172f7d  mov     rcx, rdi; hService
0x180172f80  call    cs:__imp_QueryServiceConfigA
0x180172f86  call    cs:__imp_GetLastError
0x180172f8c  cmp     eax, 7Ah ; 'z'
0x180172f8f  jnz     short loc_180172FC8
0x180172f91  mov     ecx, [rsp+48h+pcbBytesNeeded]; Size
0x180172f95  call    cs:__imp_malloc
0x180172f9b  mov     rbx, rax
0x180172f9e  test    rax, rax
0x180172fa1  jz      short loc_180172FC8
0x180172fa3  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x180172fa8  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x180172fad  mov     rdx, rax; lpServiceConfig
0x180172fb0  mov     rcx, rdi; hService
0x180172fb3  call    cs:__imp_QueryServiceConfigA
0x180172fb9  test    eax, eax
0x180172fbb  jnz     short loc_180172FC5
0x180172fbd  call    cs:__imp_GetLastError
0x180172fc3  jmp     short loc_180172FC8
0x180172fc5  mov     ebp, [rbx+4]
0x180172fc8  mov     rcx, rdi; hSCObject
0x180172fcb  call    cs:__imp_CloseServiceHandle
0x180172fd1  mov     rcx, rsi; hSCObject
0x180172fd4  call    cs:__imp_CloseServiceHandle
0x180172fda  test    rbx, rbx
0x180172fdd  jz      short loc_180172FE8
0x180172fdf  mov     rcx, rbx; Block
0x180172fe2  call    cs:__imp_free
0x180172fe8  mov     eax, ebp
0x180172fea  add     rsp, 28h
0x180172fee  pop     rdi
0x180172fef  pop     rsi
0x180172ff0  pop     rbp
0x180172ff1  pop     rbx
0x180172ff2  retn
```
