# DhcpFallbackRefreshParams

- ea: `0x180006c90`
- end: `0x180006e03`
- name: `DhcpFallbackRefreshParams`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x180006c90`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006d49`
- `RPCRT4!NdrClientCall3` at `0x180006d49`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006d07`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006d65`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006d83`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006d07`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006d65`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006d83`

## pseudocode

```c
__int64 __fastcall DhcpFallbackRefreshParams(__int64 a1)
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
    WPP_SF_S(1028, 33, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 34, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
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
      WPP_SF_SD(1028, 37, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v4,
      Pointer + 35,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      a1,
      (__int64)CommandLineW);
  }
  v10.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 9u, 0).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v10.Pointer = v5.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DSS(v7, 36, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v6);
    goto LABEL_13;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180006c90  mov     [rsp+arg_18], rbx
0x180006c95  mov     [rsp+arg_0], rcx
0x180006c9a  push    rdi
0x180006c9b  sub     rsp, 40h
0x180006c9f  mov     rdi, rcx
0x180006ca2  mov     [rsp+48h+arg_8], 0
0x180006cab  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006cb2  jz      short loc_180006CCD
0x180006cb4  mov     edx, 21h ; '!'
0x180006cb9  mov     ecx, 404h
0x180006cbe  mov     r9, rdi
0x180006cc1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006cc8  call    WPP_SF_S
0x180006ccd  call    DhcpIsFSEGuestSystem
0x180006cd2  test    eax, eax
0x180006cd4  jnz     loc_180006DA9
0x180006cda  test    rdi, rdi
0x180006cdd  jnz     short loc_180006CE7
0x180006cdf  lea     ebx, [rax+57h]
0x180006ce2  jmp     loc_180006DD0
0x180006ce7  lea     rdx, [rsp+48h+arg_8]
0x180006cec  mov     rcx, rdi
0x180006cef  call    DhcpAdapterNameToIfId
0x180006cf4  mov     ebx, eax
0x180006cf6  test    eax, eax
0x180006cf8  jnz     loc_180006DD0
0x180006cfe  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006d05  jz      short loc_180006D25
0x180006d07  call    cs:__imp_GetCommandLineW
0x180006d0d  lea     edx, [rbx+23h]
0x180006d10  mov     [rsp+48h+var_28], rax
0x180006d15  mov     r9, rdi
0x180006d18  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006d1f  call    WPP_SF_SS
0x180006d24  nop
0x180006d25  mov     [rsp+48h+arg_10], 0
0x180006d2e  lea     rax, [rsp+48h+arg_8]
0x180006d33  mov     [rsp+48h+var_28], rax
0x180006d38  xor     r9d, r9d
0x180006d3b  xor     r8d, r8d; pReturnValue
0x180006d3e  lea     edx, [r9+9]; nProcNum
0x180006d42  lea     rcx, pProxyInfo; pProxyInfo
0x180006d49  call    cs:__imp_NdrClientCall3
0x180006d4f  mov     rbx, rax
0x180006d52  mov     [rsp+48h+arg_10], rax
0x180006d57  mov     [rsp+48h+var_18], eax
0x180006d5b  jmp     short loc_180006D7A
0x180006d5d  mov     edi, eax
0x180006d5f  mov     ebx, eax
0x180006d61  mov     [rsp+48h+var_18], eax
0x180006d65  call    cs:__imp_GetCommandLineW
0x180006d6b  mov     rdx, rax
0x180006d6e  mov     ecx, ebx
0x180006d70  call    TraceRpcException
0x180006d75  mov     rdi, [rsp+48h+arg_0]
0x180006d7a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006d81  jz      short loc_180006DF6
0x180006d83  call    cs:__imp_GetCommandLineW
0x180006d89  mov     edx, 24h ; '$'
0x180006d8e  mov     [rsp+48h+var_20], rax
0x180006d93  mov     [rsp+48h+var_28], rdi
0x180006d98  mov     r9d, ebx
0x180006d9b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006da2  call    WPP_SF_DSS
0x180006da7  jmp     short loc_180006DD0
0x180006da9  mov     r9d, 32h ; '2'
0x180006daf  mov     ebx, r9d
0x180006db2  test    byte ptr cs:xmmword_18001E1E0, 2
0x180006db9  jz      short loc_180006DD0
0x180006dbb  lea     edx, [r9-10h]
0x180006dbf  mov     ecx, 401h
0x180006dc4  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006dcb  call    WPP_SF_d
0x180006dd0  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006dd7  jz      short loc_180006DF6
0x180006dd9  mov     edx, 25h ; '%'
0x180006dde  mov     ecx, 404h
0x180006de3  mov     dword ptr [rsp+48h+var_28], ebx
0x180006de7  mov     r9, rdi
0x180006dea  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006df1  call    WPP_SF_SD
0x180006df6  mov     eax, ebx
0x180006df8  mov     rbx, [rsp+48h+arg_18]
0x180006dfd  add     rsp, 40h
0x180006e01  pop     rdi
0x180006e02  retn
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
