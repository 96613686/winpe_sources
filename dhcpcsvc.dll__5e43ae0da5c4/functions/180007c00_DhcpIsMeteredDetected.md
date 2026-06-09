# DhcpIsMeteredDetected

- ea: `0x180007c00`
- end: `0x180007d7d`
- name: `DhcpIsMeteredDetected`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180007c00`
- `0x18000f4ec`
- `0x180011298`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180007cc3`
- `RPCRT4!NdrClientCall3` at `0x180007cc3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007c7a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007cdf`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007d02`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007c7a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007cdf`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007d02`

## pseudocode

```c
__int64 __fastcall DhcpIsMeteredDetected(__int64 a1, _DWORD *a2)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v6; // ecx
  CLIENT_CALL_RETURN v7; // rax
  LPWSTR v8; // rax
  int v9; // ecx
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+78h] [rbp+20h]

  v11 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 250, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( a1 && a2 )
  {
    Pointer = DhcpAdapterNameToIfId(a1, &v11);
    if ( !Pointer )
    {
      *a2 = 0;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_SS(v6, 251, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
      }
      v12.Simple = 0;
      v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x24u, 0).Pointer;
      Pointer = (unsigned int)v7.Pointer;
      v12.Pointer = v7.Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v8 = GetCommandLineW();
        WPP_SF_DSS(v9, 252, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v8);
      }
      if ( !Pointer )
      {
        if ( (xmmword_18001E1E0 & 0x10) == 0 )
          return Pointer;
        WPP_SF_l(1028, 253, WPP_e15037783097355a5233924022d92169_Traceguids, (unsigned int)*a2);
      }
    }
  }
  else
  {
    Pointer = 87;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 254, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180007c00  mov     [rsp+arg_8], rdx
0x180007c05  mov     [rsp+arg_0], rcx
0x180007c0a  push    rbx
0x180007c0b  push    rdi
0x180007c0c  push    r14
0x180007c0e  sub     rsp, 40h
0x180007c12  mov     r14, rdx
0x180007c15  mov     rdi, rcx
0x180007c18  mov     [rsp+58h+arg_10], 0
0x180007c21  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007c28  jz      short loc_180007C43
0x180007c2a  mov     edx, 0FAh
0x180007c2f  mov     ecx, 404h
0x180007c34  mov     r9, rdi
0x180007c37  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007c3e  call    WPP_SF_S
0x180007c43  test    rdi, rdi
0x180007c46  jnz     short loc_180007C52
0x180007c48  mov     ebx, 57h ; 'W'
0x180007c4d  jmp     loc_180007D4C
0x180007c52  test    r14, r14
0x180007c55  jz      short loc_180007C48
0x180007c57  lea     rdx, [rsp+58h+arg_10]
0x180007c5c  mov     rcx, rdi
0x180007c5f  call    DhcpAdapterNameToIfId
0x180007c64  mov     ebx, eax
0x180007c66  test    eax, eax
0x180007c68  jnz     loc_180007D4C
0x180007c6e  mov     [r14], eax
0x180007c71  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007c78  jz      short loc_180007C9A
0x180007c7a  call    cs:__imp_GetCommandLineW
0x180007c80  mov     edx, 0FBh
0x180007c85  mov     [rsp+58h+var_38], rax
0x180007c8a  mov     r9, rdi
0x180007c8d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007c94  call    WPP_SF_SS
0x180007c99  nop
0x180007c9a  mov     [rsp+58h+arg_18], 0
0x180007ca3  mov     [rsp+58h+var_30], r14
0x180007ca8  lea     rax, [rsp+58h+arg_10]
0x180007cad  mov     [rsp+58h+var_38], rax
0x180007cb2  xor     r9d, r9d
0x180007cb5  xor     r8d, r8d; pReturnValue
0x180007cb8  lea     edx, [r9+24h]; nProcNum
0x180007cbc  lea     rcx, pProxyInfo; pProxyInfo
0x180007cc3  call    cs:__imp_NdrClientCall3
0x180007cc9  mov     rbx, rax
0x180007ccc  mov     [rsp+58h+arg_18], rax
0x180007cd1  mov     [rsp+58h+var_28], eax
0x180007cd5  jmp     short loc_180007CF9
0x180007cd7  mov     edi, eax
0x180007cd9  mov     ebx, eax
0x180007cdb  mov     [rsp+58h+var_28], eax
0x180007cdf  call    cs:__imp_GetCommandLineW
0x180007ce5  mov     rdx, rax
0x180007ce8  mov     ecx, ebx
0x180007cea  call    TraceRpcException
0x180007cef  mov     r14, [rsp+58h+arg_8]
0x180007cf4  mov     rdi, [rsp+58h+arg_0]
0x180007cf9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007d00  jz      short loc_180007D26
0x180007d02  call    cs:__imp_GetCommandLineW
0x180007d08  mov     edx, 0FCh
0x180007d0d  mov     [rsp+58h+var_30], rax
0x180007d12  mov     [rsp+58h+var_38], rdi
0x180007d17  mov     r9d, ebx
0x180007d1a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007d21  call    WPP_SF_DSS
0x180007d26  test    ebx, ebx
0x180007d28  jnz     short loc_180007D4C
0x180007d2a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007d31  jz      short loc_180007D72
0x180007d33  mov     edx, 0FDh
0x180007d38  mov     ecx, 404h
0x180007d3d  mov     r9d, [r14]
0x180007d40  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007d47  call    WPP_SF_l
0x180007d4c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007d53  jz      short loc_180007D72
0x180007d55  mov     edx, 0FEh
0x180007d5a  mov     ecx, 404h
0x180007d5f  mov     dword ptr [rsp+58h+var_38], ebx
0x180007d63  mov     r9, rdi
0x180007d66  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007d6d  call    WPP_SF_SD
0x180007d72  mov     eax, ebx
0x180007d74  add     rsp, 40h
0x180007d78  pop     r14
0x180007d7a  pop     rdi
0x180007d7b  pop     rbx
0x180007d7c  retn
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
