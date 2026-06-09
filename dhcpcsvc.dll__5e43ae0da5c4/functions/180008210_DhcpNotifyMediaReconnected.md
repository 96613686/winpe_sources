# DhcpNotifyMediaReconnected

- ea: `0x180008210`
- end: `0x180008383`
- name: `DhcpNotifyMediaReconnected`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x180008210`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800082c9`
- `RPCRT4!NdrClientCall3` at `0x1800082c9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008287`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800082e5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008303`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008287`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800082e5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008303`

## pseudocode

```c
__int64 __fastcall DhcpNotifyMediaReconnected(__int64 a1)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v4; // ecx
  CLIENT_CALL_RETURN v5; // rax
  LPWSTR v6; // rax
  int v7; // ecx
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+60h] [rbp+18h]

  v9 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 28, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 29, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_13;
  }
  if ( !a1 )
  {
    Pointer = 87;
    goto LABEL_13;
  }
  Pointer = DhcpAdapterNameToIfId(a1, &v9);
  if ( Pointer )
  {
LABEL_13:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 32, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v4,
      Pointer + 30,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      a1,
      (__int64)CommandLineW);
  }
  v10.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x17u, 0).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v10.Pointer = v5.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DSS(v7, 31, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v6);
    goto LABEL_13;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180008210  mov     [rsp+arg_18], rbx
0x180008215  mov     [rsp+arg_0], rcx
0x18000821a  push    rdi
0x18000821b  sub     rsp, 40h
0x18000821f  mov     rdi, rcx
0x180008222  mov     [rsp+48h+arg_8], 0
0x18000822b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008232  jz      short loc_18000824D
0x180008234  mov     edx, 1Ch
0x180008239  mov     ecx, 404h
0x18000823e  mov     r9, rdi
0x180008241  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008248  call    WPP_SF_S
0x18000824d  call    DhcpIsFSEGuestSystem
0x180008252  test    eax, eax
0x180008254  jnz     loc_180008329
0x18000825a  test    rdi, rdi
0x18000825d  jnz     short loc_180008267
0x18000825f  lea     ebx, [rax+57h]
0x180008262  jmp     loc_180008350
0x180008267  lea     rdx, [rsp+48h+arg_8]
0x18000826c  mov     rcx, rdi
0x18000826f  call    DhcpAdapterNameToIfId
0x180008274  mov     ebx, eax
0x180008276  test    eax, eax
0x180008278  jnz     loc_180008350
0x18000827e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008285  jz      short loc_1800082A5
0x180008287  call    cs:__imp_GetCommandLineW
0x18000828d  lea     edx, [rbx+1Eh]
0x180008290  mov     [rsp+48h+var_28], rax
0x180008295  mov     r9, rdi
0x180008298  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000829f  call    WPP_SF_SS
0x1800082a4  nop
0x1800082a5  mov     [rsp+48h+arg_10], 0
0x1800082ae  lea     rax, [rsp+48h+arg_8]
0x1800082b3  mov     [rsp+48h+var_28], rax
0x1800082b8  xor     r9d, r9d
0x1800082bb  xor     r8d, r8d; pReturnValue
0x1800082be  lea     edx, [r9+17h]; nProcNum
0x1800082c2  lea     rcx, pProxyInfo; pProxyInfo
0x1800082c9  call    cs:__imp_NdrClientCall3
0x1800082cf  mov     rbx, rax
0x1800082d2  mov     [rsp+48h+arg_10], rax
0x1800082d7  mov     [rsp+48h+var_18], eax
0x1800082db  jmp     short loc_1800082FA
0x1800082dd  mov     edi, eax
0x1800082df  mov     ebx, eax
0x1800082e1  mov     [rsp+48h+var_18], eax
0x1800082e5  call    cs:__imp_GetCommandLineW
0x1800082eb  mov     rdx, rax
0x1800082ee  mov     ecx, ebx
0x1800082f0  call    TraceRpcException
0x1800082f5  mov     rdi, [rsp+48h+arg_0]
0x1800082fa  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008301  jz      short loc_180008376
0x180008303  call    cs:__imp_GetCommandLineW
0x180008309  mov     edx, 1Fh
0x18000830e  mov     [rsp+48h+var_20], rax
0x180008313  mov     [rsp+48h+var_28], rdi
0x180008318  mov     r9d, ebx
0x18000831b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008322  call    WPP_SF_DSS
0x180008327  jmp     short loc_180008350
0x180008329  mov     r9d, 32h ; '2'
0x18000832f  mov     ebx, r9d
0x180008332  test    byte ptr cs:xmmword_18001E1E0, 2
0x180008339  jz      short loc_180008350
0x18000833b  lea     edx, [r9-15h]
0x18000833f  mov     ecx, 401h
0x180008344  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000834b  call    WPP_SF_d
0x180008350  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008357  jz      short loc_180008376
0x180008359  mov     edx, 20h ; ' '
0x18000835e  mov     ecx, 404h
0x180008363  mov     dword ptr [rsp+48h+var_28], ebx
0x180008367  mov     r9, rdi
0x18000836a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008371  call    WPP_SF_SD
0x180008376  mov     eax, ebx
0x180008378  mov     rbx, [rsp+48h+arg_18]
0x18000837d  add     rsp, 40h
0x180008381  pop     rdi
0x180008382  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```
