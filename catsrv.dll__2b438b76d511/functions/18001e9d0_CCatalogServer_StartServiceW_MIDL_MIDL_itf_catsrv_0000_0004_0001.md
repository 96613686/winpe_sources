# CCatalogServer::StartServiceW(__MIDL___MIDL_itf_catsrv_0000_0004_0001)

- ea: `0x18001e9d0`
- end: `0x18001eab1`
- name: `?StartServiceW@CCatalogServer@@UEAAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001e744`
- `0x18001e9d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea63`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ea84`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ea92`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ea84`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ea92`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea1b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ea1b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ea3c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ea3c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001ea59`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001ea59`

## pseudocode

```c
__int64 __fastcall CCatalogServer::StartServiceW(__int64 a1, int a2)
{
  __int64 v2; // rdi
  signed int LoadBalancingIfNeeded; // ebx
  const WCHAR *v4; // rdi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  signed int LastError; // eax

  v2 = a2;
  if ( a2 != 1 )
    return 2147942487LL;
  LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(1);
  if ( LoadBalancingIfNeeded >= 0 )
  {
    v4 = (&csServices)[10 * v2 - 5];
    v5 = OpenSCManagerW(0, 0, 0xA0000000);
    v6 = v5;
    if ( v5 )
    {
      v7 = OpenServiceW(v5, v4, 0x10u);
      v8 = v7;
      if ( v7 )
      {
        if ( !StartServiceW(v7, 0, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 1056 )
          {
            if ( LastError > 0 )
              LoadBalancingIfNeeded = (unsigned __int16)LastError | 0x80070000;
            else
              LoadBalancingIfNeeded = LastError;
          }
        }
      }
      else
      {
        LoadBalancingIfNeeded = -2147418113;
      }
      CloseServiceHandle(v6);
      if ( v8 )
        CloseServiceHandle(v8);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)LoadBalancingIfNeeded;
}

```

## disassembly

```asm
0x18001e9d0  mov     [rsp+arg_0], rbx
0x18001e9d5  mov     [rsp+arg_8], rsi
0x18001e9da  push    rdi
0x18001e9db  sub     rsp, 20h
0x18001e9df  movsxd  rdi, edx
0x18001e9e2  lea     eax, [rdi-1]
0x18001e9e5  test    eax, eax
0x18001e9e7  jnz     loc_18001EA9C
0x18001e9ed  mov     ecx, edi
0x18001e9ef  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001e9f4  mov     ebx, eax
0x18001e9f6  test    eax, eax
0x18001e9f8  js      loc_18001EA98
0x18001e9fe  lea     rdx, [rdi+rdi*4]
0x18001ea02  xor     ecx, ecx; lpMachineName
0x18001ea04  add     rdx, rdx
0x18001ea07  lea     rdi, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001ea0e  mov     r8d, 0A0000000h; dwDesiredAccess
0x18001ea14  mov     rdi, [rdi+rdx*8-50h]
0x18001ea19  xor     edx, edx; lpDatabaseName
0x18001ea1b  call    cs:__imp_OpenSCManagerW
0x18001ea21  mov     rsi, rax
0x18001ea24  test    rax, rax
0x18001ea27  jnz     short loc_18001EA30
0x18001ea29  mov     ebx, 8000FFFFh
0x18001ea2e  jmp     short loc_18001EA98
0x18001ea30  mov     r8d, 10h; dwDesiredAccess
0x18001ea36  mov     rdx, rdi; lpServiceName
0x18001ea39  mov     rcx, rsi; hSCManager
0x18001ea3c  call    cs:__imp_OpenServiceW
0x18001ea42  mov     rdi, rax
0x18001ea45  test    rax, rax
0x18001ea48  jnz     short loc_18001EA51
0x18001ea4a  mov     ebx, 8000FFFFh
0x18001ea4f  jmp     short loc_18001EA81
0x18001ea51  xor     r8d, r8d; lpServiceArgVectors
0x18001ea54  xor     edx, edx; dwNumServiceArgs
0x18001ea56  mov     rcx, rdi; hService
0x18001ea59  call    cs:__imp_StartServiceW
0x18001ea5f  test    eax, eax
0x18001ea61  jnz     short loc_18001EA81
0x18001ea63  call    cs:__imp_GetLastError
0x18001ea69  cmp     eax, 420h
0x18001ea6e  jz      short loc_18001EA81
0x18001ea70  test    eax, eax
0x18001ea72  jg      short loc_18001EA78
0x18001ea74  mov     ebx, eax
0x18001ea76  jmp     short loc_18001EA81
0x18001ea78  movzx   ebx, ax
0x18001ea7b  or      ebx, 80070000h
0x18001ea81  mov     rcx, rsi; hSCObject
0x18001ea84  call    cs:__imp_CloseServiceHandle
0x18001ea8a  test    rdi, rdi
0x18001ea8d  jz      short loc_18001EA98
0x18001ea8f  mov     rcx, rdi; hSCObject
0x18001ea92  call    cs:__imp_CloseServiceHandle
0x18001ea98  mov     eax, ebx
0x18001ea9a  jmp     short loc_18001EAA1
0x18001ea9c  mov     eax, 80070057h
0x18001eaa1  mov     rbx, [rsp+28h+arg_0]
0x18001eaa6  mov     rsi, [rsp+28h+arg_8]
0x18001eaab  add     rsp, 20h
0x18001eaaf  pop     rdi
0x18001eab0  retn
```
