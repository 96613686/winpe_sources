# DhcpAcquireParametersByBroadcast

- ea: `0x180005d30`
- end: `0x180005e6d`
- name: `DhcpAcquireParametersByBroadcast`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180005d30`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180005ddc`
- `RPCRT4!NdrClientCall3` at `0x180005ddc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005d9a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005df8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005e16`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005d9a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005df8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005e16`

## pseudocode

```c
__int64 __fastcall DhcpAcquireParametersByBroadcast(__int64 a1)
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
    WPP_SF_S(1028, 24, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( !a1 )
  {
    Pointer = 87;
    goto LABEL_10;
  }
  Pointer = DhcpAdapterNameToIfId(a1, &v9);
  if ( Pointer )
  {
LABEL_10:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 27, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v4,
      Pointer + 25,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      a1,
      (__int64)CommandLineW);
  }
  v10.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v10.Pointer = v5.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DSS(v7, 26, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v6);
    goto LABEL_10;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180005d30  mov     [rsp+arg_18], rbx
0x180005d35  mov     [rsp+arg_0], rcx
0x180005d3a  push    rdi
0x180005d3b  sub     rsp, 40h
0x180005d3f  mov     rdi, rcx
0x180005d42  mov     [rsp+48h+arg_8], 0
0x180005d4b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005d52  jz      short loc_180005D6D
0x180005d54  mov     edx, 18h
0x180005d59  mov     ecx, 404h
0x180005d5e  mov     r9, rdi
0x180005d61  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005d68  call    WPP_SF_S
0x180005d6d  test    rdi, rdi
0x180005d70  jnz     short loc_180005D7A
0x180005d72  lea     ebx, [rdi+57h]
0x180005d75  jmp     loc_180005E3A
0x180005d7a  lea     rdx, [rsp+48h+arg_8]
0x180005d7f  mov     rcx, rdi
0x180005d82  call    DhcpAdapterNameToIfId
0x180005d87  mov     ebx, eax
0x180005d89  test    eax, eax
0x180005d8b  jnz     loc_180005E3A
0x180005d91  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005d98  jz      short loc_180005DB8
0x180005d9a  call    cs:__imp_GetCommandLineW
0x180005da0  lea     edx, [rbx+19h]
0x180005da3  mov     [rsp+48h+var_28], rax
0x180005da8  mov     r9, rdi
0x180005dab  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005db2  call    WPP_SF_SS
0x180005db7  nop
0x180005db8  mov     [rsp+48h+arg_10], 0
0x180005dc1  lea     rax, [rsp+48h+arg_8]
0x180005dc6  mov     [rsp+48h+var_28], rax
0x180005dcb  xor     r9d, r9d
0x180005dce  xor     r8d, r8d; pReturnValue
0x180005dd1  lea     edx, [r9+5]; nProcNum
0x180005dd5  lea     rcx, pProxyInfo; pProxyInfo
0x180005ddc  call    cs:__imp_NdrClientCall3
0x180005de2  mov     rbx, rax
0x180005de5  mov     [rsp+48h+arg_10], rax
0x180005dea  mov     [rsp+48h+var_18], eax
0x180005dee  jmp     short loc_180005E0D
0x180005df0  mov     edi, eax
0x180005df2  mov     ebx, eax
0x180005df4  mov     [rsp+48h+var_18], eax
0x180005df8  call    cs:__imp_GetCommandLineW
0x180005dfe  mov     rdx, rax
0x180005e01  mov     ecx, ebx
0x180005e03  call    TraceRpcException
0x180005e08  mov     rdi, [rsp+48h+arg_0]
0x180005e0d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005e14  jz      short loc_180005E60
0x180005e16  call    cs:__imp_GetCommandLineW
0x180005e1c  mov     edx, 1Ah
0x180005e21  mov     [rsp+48h+var_20], rax
0x180005e26  mov     [rsp+48h+var_28], rdi
0x180005e2b  mov     r9d, ebx
0x180005e2e  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005e35  call    WPP_SF_DSS
0x180005e3a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005e41  jz      short loc_180005E60
0x180005e43  mov     edx, 1Bh
0x180005e48  mov     ecx, 404h
0x180005e4d  mov     dword ptr [rsp+48h+var_28], ebx
0x180005e51  mov     r9, rdi
0x180005e54  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005e5b  call    WPP_SF_SD
0x180005e60  mov     eax, ebx
0x180005e62  mov     rbx, [rsp+48h+arg_18]
0x180005e67  add     rsp, 40h
0x180005e6b  pop     rdi
0x180005e6c  retn
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
