# Dhcpv6GetTraceArray

- ea: `0x180004cc0`
- end: `0x180004e0a`
- name: `Dhcpv6GetTraceArray`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002650`
- `0x180004cc0`
- `0x1800072fc`
- `0x180007891`
- `0x1800081c0`
- `0x180008220`
- `0x1800082b0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004d62`
- `RPCRT4!NdrClientCall3` at `0x180004d62`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004d23`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004d7e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004d9c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004d23`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004d7e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004d9c`

## pseudocode

```c
__int64 __fastcall Dhcpv6GetTraceArray(_QWORD *a1)
{
  char v2; // al
  LPWSTR CommandLineW; // rax
  __int64 v4; // rcx
  unsigned int Pointer; // ebx
  LPWSTR v6; // rax
  void *Src[2]; // [rsp+38h] [rbp-20h] BYREF

  *(_OWORD *)Src = 0;
  v2 = xmmword_18000F160;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    WPP_SF_(a1, 64, WPP_cb48999f8e5838f952918348529d50de_Traceguids);
    v2 = xmmword_18000F160;
  }
  if ( !a1 || !*a1 )
    return 87;
  LODWORD(Src[1]) = 0;
  Src[0] = 0;
  if ( (v2 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(v4, 65, WPP_cb48999f8e5838f952918348529d50de_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 8u, 0).Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DS(1028, 66, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, Pointer, (__int64)v6);
  }
  DhcpMidlUserFree(Src);
  return Pointer;
}

```

## disassembly

```asm
0x180004cc0  mov     [rsp+arg_10], rbx
0x180004cc5  mov     [rsp+arg_0], rcx
0x180004cca  push    rdi
0x180004ccb  sub     rsp, 50h
0x180004ccf  mov     rdi, rcx
0x180004cd2  xorps   xmm0, xmm0
0x180004cd5  movups  xmmword ptr [rsp+58h+Src], xmm0
0x180004cda  mov     al, byte ptr cs:xmmword_18000F160
0x180004ce0  test    al, 10h
0x180004ce2  jz      short loc_180004CFB
0x180004ce4  mov     edx, 40h ; '@'
0x180004ce9  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004cf0  call    WPP_SF_
0x180004cf5  mov     al, byte ptr cs:xmmword_18000F160
0x180004cfb  test    rdi, rdi
0x180004cfe  jz      loc_180004DFA
0x180004d04  cmp     qword ptr [rdi], 0
0x180004d08  jz      loc_180004DFA
0x180004d0e  mov     dword ptr [rsp+58h+Src+8], 0
0x180004d16  mov     [rsp+58h+Src], 0
0x180004d1f  test    al, 10h
0x180004d21  jz      short loc_180004D3E
0x180004d23  call    cs:__imp_GetCommandLineW
0x180004d29  mov     r9, rax
0x180004d2c  mov     edx, 41h ; 'A'
0x180004d31  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004d38  call    WPP_SF_S
0x180004d3d  nop
0x180004d3e  mov     [rsp+58h+arg_8], 0
0x180004d47  lea     rax, [rsp+58h+Src]
0x180004d4c  mov     [rsp+58h+var_38], rax
0x180004d51  xor     r9d, r9d
0x180004d54  xor     r8d, r8d; pReturnValue
0x180004d57  lea     edx, [r9+8]; nProcNum
0x180004d5b  lea     rcx, pProxyInfo; pProxyInfo
0x180004d62  call    cs:__imp_NdrClientCall3
0x180004d68  mov     rbx, rax
0x180004d6b  mov     [rsp+58h+arg_8], rax
0x180004d70  mov     [rsp+58h+var_28], eax
0x180004d74  jmp     short loc_180004D93
0x180004d76  mov     edi, eax
0x180004d78  mov     ebx, eax
0x180004d7a  mov     [rsp+58h+var_28], eax
0x180004d7e  call    cs:__imp_GetCommandLineW
0x180004d84  mov     rdx, rax
0x180004d87  mov     ecx, ebx
0x180004d89  call    TraceRpcException
0x180004d8e  mov     rdi, [rsp+58h+arg_0]
0x180004d93  test    byte ptr cs:xmmword_18000F160, 10h
0x180004d9a  jz      short loc_180004DC0
0x180004d9c  call    cs:__imp_GetCommandLineW
0x180004da2  mov     edx, 42h ; 'B'
0x180004da7  mov     ecx, 404h
0x180004dac  mov     [rsp+58h+var_38], rax
0x180004db1  mov     r9d, ebx
0x180004db4  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004dbb  call    WPP_SF_DS
0x180004dc0  test    ebx, ebx
0x180004dc2  jnz     short loc_180004DEC
0x180004dc4  mov     eax, dword ptr [rsp+58h+Src+8]
0x180004dc8  test    eax, eax
0x180004dca  jz      short loc_180004DEC
0x180004dcc  mov     rdx, [rsp+58h+Src]; Src
0x180004dd1  test    rdx, rdx
0x180004dd4  jz      short loc_180004DEC
0x180004dd6  imul    r8, rax, 0E0h; Size
0x180004ddd  mov     rcx, [rdi]; void *
0x180004de0  call    memcpy_0
0x180004de5  mov     eax, dword ptr [rsp+58h+Src+8]
0x180004de9  mov     [rdi+8], eax
0x180004dec  lea     rcx, [rsp+58h+Src]
0x180004df1  call    DhcpMidlUserFree
0x180004df6  mov     eax, ebx
0x180004df8  jmp     short loc_180004DFF
0x180004dfa  mov     eax, 57h ; 'W'
0x180004dff  mov     rbx, [rsp+58h+arg_10]
0x180004e04  add     rsp, 50h
0x180004e08  pop     rdi
0x180004e09  retn
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
