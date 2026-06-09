# DhcpReleaseParameters

- ea: `0x18000a180`
- end: `0x18000a2bd`
- name: `DhcpReleaseParameters`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x18000a180`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a22c`
- `RPCRT4!NdrClientCall3` at `0x18000a22c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a1ea`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a248`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a266`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a1ea`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a248`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a266`

## pseudocode

```c
__int64 __fastcall DhcpReleaseParameters(__int64 a1)
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
    WPP_SF_S(1028, 38, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
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
      WPP_SF_SD(1028, 41, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v4,
      Pointer + 39,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      a1,
      (__int64)CommandLineW);
  }
  v10.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v10.Pointer = v5.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DSS(v7, 40, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v6);
    goto LABEL_10;
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000a180  mov     [rsp+arg_18], rbx
0x18000a185  mov     [rsp+arg_0], rcx
0x18000a18a  push    rdi
0x18000a18b  sub     rsp, 40h
0x18000a18f  mov     rdi, rcx
0x18000a192  mov     [rsp+48h+arg_8], 0
0x18000a19b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a1a2  jz      short loc_18000A1BD
0x18000a1a4  mov     edx, 26h ; '&'
0x18000a1a9  mov     ecx, 404h
0x18000a1ae  mov     r9, rdi
0x18000a1b1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a1b8  call    WPP_SF_S
0x18000a1bd  test    rdi, rdi
0x18000a1c0  jnz     short loc_18000A1CA
0x18000a1c2  lea     ebx, [rdi+57h]
0x18000a1c5  jmp     loc_18000A28A
0x18000a1ca  lea     rdx, [rsp+48h+arg_8]
0x18000a1cf  mov     rcx, rdi
0x18000a1d2  call    DhcpAdapterNameToIfId
0x18000a1d7  mov     ebx, eax
0x18000a1d9  test    eax, eax
0x18000a1db  jnz     loc_18000A28A
0x18000a1e1  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a1e8  jz      short loc_18000A208
0x18000a1ea  call    cs:__imp_GetCommandLineW
0x18000a1f0  lea     edx, [rbx+27h]
0x18000a1f3  mov     [rsp+48h+var_28], rax
0x18000a1f8  mov     r9, rdi
0x18000a1fb  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a202  call    WPP_SF_SS
0x18000a207  nop
0x18000a208  mov     [rsp+48h+arg_10], 0
0x18000a211  lea     rax, [rsp+48h+arg_8]
0x18000a216  mov     [rsp+48h+var_28], rax
0x18000a21b  xor     r9d, r9d
0x18000a21e  xor     r8d, r8d; pReturnValue
0x18000a221  lea     edx, [r9+6]; nProcNum
0x18000a225  lea     rcx, pProxyInfo; pProxyInfo
0x18000a22c  call    cs:__imp_NdrClientCall3
0x18000a232  mov     rbx, rax
0x18000a235  mov     [rsp+48h+arg_10], rax
0x18000a23a  mov     [rsp+48h+var_18], eax
0x18000a23e  jmp     short loc_18000A25D
0x18000a240  mov     edi, eax
0x18000a242  mov     ebx, eax
0x18000a244  mov     [rsp+48h+var_18], eax
0x18000a248  call    cs:__imp_GetCommandLineW
0x18000a24e  mov     rdx, rax
0x18000a251  mov     ecx, ebx
0x18000a253  call    TraceRpcException
0x18000a258  mov     rdi, [rsp+48h+arg_0]
0x18000a25d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a264  jz      short loc_18000A2B0
0x18000a266  call    cs:__imp_GetCommandLineW
0x18000a26c  mov     edx, 28h ; '('
0x18000a271  mov     [rsp+48h+var_20], rax
0x18000a276  mov     [rsp+48h+var_28], rdi
0x18000a27b  mov     r9d, ebx
0x18000a27e  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a285  call    WPP_SF_DSS
0x18000a28a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a291  jz      short loc_18000A2B0
0x18000a293  mov     edx, 29h ; ')'
0x18000a298  mov     ecx, 404h
0x18000a29d  mov     dword ptr [rsp+48h+var_28], ebx
0x18000a2a1  mov     r9, rdi
0x18000a2a4  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a2ab  call    WPP_SF_SD
0x18000a2b0  mov     eax, ebx
0x18000a2b2  mov     rbx, [rsp+48h+arg_18]
0x18000a2b7  add     rsp, 40h
0x18000a2bb  pop     rdi
0x18000a2bc  retn
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
