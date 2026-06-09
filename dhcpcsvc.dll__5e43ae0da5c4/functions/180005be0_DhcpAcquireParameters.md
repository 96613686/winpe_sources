# DhcpAcquireParameters

- ea: `0x180005be0`
- end: `0x180005d1d`
- name: `DhcpAcquireParameters`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d8e0`

## callees

- `0x180002620`
- `0x180005be0`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180005c8c`
- `RPCRT4!NdrClientCall3` at `0x180005c8c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005c4a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005ca8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005cc6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005c4a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005ca8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005cc6`

## pseudocode

```c
__int64 __fastcall DhcpAcquireParameters(__int64 a1)
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
    WPP_SF_S(1028, 20, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
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
      WPP_SF_SD(1028, 23, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v4,
      Pointer + 21,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      a1,
      (__int64)CommandLineW);
  }
  v10.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v10.Pointer = v5.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DSS(v7, 22, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v6);
    goto LABEL_10;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180005be0  mov     [rsp+arg_18], rbx
0x180005be5  mov     [rsp+arg_0], rcx
0x180005bea  push    rdi
0x180005beb  sub     rsp, 40h
0x180005bef  mov     rdi, rcx
0x180005bf2  mov     [rsp+48h+arg_8], 0
0x180005bfb  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005c02  jz      short loc_180005C1D
0x180005c04  mov     edx, 14h
0x180005c09  mov     ecx, 404h
0x180005c0e  mov     r9, rdi
0x180005c11  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005c18  call    WPP_SF_S
0x180005c1d  test    rdi, rdi
0x180005c20  jnz     short loc_180005C2A
0x180005c22  lea     ebx, [rdi+57h]
0x180005c25  jmp     loc_180005CEA
0x180005c2a  lea     rdx, [rsp+48h+arg_8]
0x180005c2f  mov     rcx, rdi
0x180005c32  call    DhcpAdapterNameToIfId
0x180005c37  mov     ebx, eax
0x180005c39  test    eax, eax
0x180005c3b  jnz     loc_180005CEA
0x180005c41  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005c48  jz      short loc_180005C68
0x180005c4a  call    cs:__imp_GetCommandLineW
0x180005c50  lea     edx, [rbx+15h]
0x180005c53  mov     [rsp+48h+var_28], rax
0x180005c58  mov     r9, rdi
0x180005c5b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005c62  call    WPP_SF_SS
0x180005c67  nop
0x180005c68  mov     [rsp+48h+arg_10], 0
0x180005c71  lea     rax, [rsp+48h+arg_8]
0x180005c76  mov     [rsp+48h+var_28], rax
0x180005c7b  xor     r9d, r9d
0x180005c7e  xor     r8d, r8d; pReturnValue
0x180005c81  lea     edx, [r9+2]; nProcNum
0x180005c85  lea     rcx, pProxyInfo; pProxyInfo
0x180005c8c  call    cs:__imp_NdrClientCall3
0x180005c92  mov     rbx, rax
0x180005c95  mov     [rsp+48h+arg_10], rax
0x180005c9a  mov     [rsp+48h+var_18], eax
0x180005c9e  jmp     short loc_180005CBD
0x180005ca0  mov     edi, eax
0x180005ca2  mov     ebx, eax
0x180005ca4  mov     [rsp+48h+var_18], eax
0x180005ca8  call    cs:__imp_GetCommandLineW
0x180005cae  mov     rdx, rax
0x180005cb1  mov     ecx, ebx
0x180005cb3  call    TraceRpcException
0x180005cb8  mov     rdi, [rsp+48h+arg_0]
0x180005cbd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005cc4  jz      short loc_180005D10
0x180005cc6  call    cs:__imp_GetCommandLineW
0x180005ccc  mov     edx, 16h
0x180005cd1  mov     [rsp+48h+var_20], rax
0x180005cd6  mov     [rsp+48h+var_28], rdi
0x180005cdb  mov     r9d, ebx
0x180005cde  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005ce5  call    WPP_SF_DSS
0x180005cea  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005cf1  jz      short loc_180005D10
0x180005cf3  mov     edx, 17h
0x180005cf8  mov     ecx, 404h
0x180005cfd  mov     dword ptr [rsp+48h+var_28], ebx
0x180005d01  mov     r9, rdi
0x180005d04  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005d0b  call    WPP_SF_SD
0x180005d10  mov     eax, ebx
0x180005d12  mov     rbx, [rsp+48h+arg_18]
0x180005d17  add     rsp, 40h
0x180005d1b  pop     rdi
0x180005d1c  retn
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
