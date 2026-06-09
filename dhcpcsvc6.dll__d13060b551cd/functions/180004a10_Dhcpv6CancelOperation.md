# Dhcpv6CancelOperation

- ea: `0x180004a10`
- end: `0x180004abf`
- name: `Dhcpv6CancelOperation`
- size: `175`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004a10`
- `0x1800072fc`
- `0x1800081c0`
- `0x180008220`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004a58`
- `RPCRT4!NdrClientCall3` at `0x180004a58`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004a23`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004a74`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004a8e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004a23`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004a74`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004a8e`

## pseudocode

```c
__int64 Dhcpv6CancelOperation()
{
  LPWSTR CommandLineW; // rax
  __int64 v1; // rcx
  unsigned int Pointer; // ebx
  LPWSTR v3; // rax

  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(v1, 44, WPP_cb48999f8e5838f952918348529d50de_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0).Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v3 = GetCommandLineW();
    WPP_SF_DS(1028, 45, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, Pointer, (__int64)v3);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180004a10  mov     [rsp+arg_8], rbx
0x180004a15  push    rdi
0x180004a16  sub     rsp, 40h
0x180004a1a  test    byte ptr cs:xmmword_18000F160, 10h
0x180004a21  jz      short loc_180004A3E
0x180004a23  call    cs:__imp_GetCommandLineW
0x180004a29  mov     r9, rax
0x180004a2c  mov     edx, 2Ch ; ','
0x180004a31  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004a38  call    WPP_SF_S
0x180004a3d  nop
0x180004a3e  mov     [rsp+48h+arg_0], 0
0x180004a47  xor     r9d, r9d
0x180004a4a  xor     r8d, r8d; pReturnValue
0x180004a4d  lea     edx, [r9+3]; nProcNum
0x180004a51  lea     rcx, pProxyInfo; pProxyInfo
0x180004a58  call    cs:__imp_NdrClientCall3
0x180004a5e  mov     rbx, rax
0x180004a61  mov     [rsp+48h+arg_0], rax
0x180004a66  mov     [rsp+48h+var_18], eax
0x180004a6a  jmp     short loc_180004A85
0x180004a6c  mov     edi, eax
0x180004a6e  mov     ebx, eax
0x180004a70  mov     [rsp+48h+var_18], eax
0x180004a74  call    cs:__imp_GetCommandLineW
0x180004a7a  mov     rdx, rax
0x180004a7d  mov     ecx, ebx
0x180004a7f  call    TraceRpcException
0x180004a84  nop
0x180004a85  test    byte ptr cs:xmmword_18000F160, 10h
0x180004a8c  jz      short loc_180004AB2
0x180004a8e  call    cs:__imp_GetCommandLineW
0x180004a94  mov     edx, 2Dh ; '-'
0x180004a99  mov     ecx, 404h
0x180004a9e  mov     [rsp+48h+var_28], rax
0x180004aa3  mov     r9d, ebx
0x180004aa6  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004aad  call    WPP_SF_DS
0x180004ab2  mov     eax, ebx
0x180004ab4  mov     rbx, [rsp+48h+arg_8]
0x180004ab9  add     rsp, 40h
0x180004abd  pop     rdi
0x180004abe  retn
0x180007a0c  push    rbp
0x180007a0e  sub     rsp, 30h
0x180007a12  mov     rbp, rdx
0x180007a15  mov     rcx, [rcx]
0x180007a18  mov     ecx, [rcx]; ExceptionCode
0x180007a1a  call    cs:__imp_I_RpcExceptionFilter
0x180007a20  nop
0x180007a21  add     rsp, 30h
0x180007a25  pop     rbp
0x180007a26  retn
```
