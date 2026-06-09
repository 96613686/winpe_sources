# DhcpGetOriginalSubnetMask

- ea: `0x180007950`
- end: `0x180007a92`
- name: `DhcpGetOriginalSubnetMask`
- size: `322`
- prototype: `DWORD __stdcall(LPCWSTR sAdapterName, DWORD *dwSubnetMask)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180007950`
- `0x18000f4ec`
- `0x180011894`
- `0x180012a40`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180007a03`
- `RPCRT4!NdrClientCall3` at `0x180007a03`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800079ba`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007a1f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007a3d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800079ba`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007a1f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007a3d`

## pseudocode

```c
DWORD __stdcall DhcpGetOriginalSubnetMask(LPCWSTR sAdapterName, DWORD *dwSubnetMask)
{
  int v2; // r8d
  DWORD Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v7; // ecx
  CLIENT_CALL_RETURN v8; // rax
  LPWSTR v9; // rax
  int v10; // ecx
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+78h] [rbp+20h]

  v12 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sq((_DWORD)sAdapterName, 130, v2, (char)sAdapterName);
  if ( !sAdapterName || !dwSubnetMask )
  {
    Pointer = 87;
    goto LABEL_11;
  }
  Pointer = DhcpAdapterNameToIfId(sAdapterName, &v12);
  if ( Pointer )
  {
LABEL_11:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_DS(
        1028,
        133,
        (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
        Pointer,
        (__int64)sAdapterName);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v7,
      131,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      (_DWORD)sAdapterName,
      (__int64)CommandLineW);
  }
  v13.Simple = 0;
  v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x18u, 0).Pointer;
  Pointer = (DWORD)v8.Pointer;
  v13.Pointer = v8.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v9 = GetCommandLineW();
    WPP_SF_DSS(
      v10,
      132,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      Pointer,
      (__int64)sAdapterName,
      (__int64)v9);
    goto LABEL_11;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180007950  mov     [rsp+arg_0], rcx
0x180007955  push    rbx
0x180007956  push    rsi
0x180007957  push    rdi
0x180007958  sub     rsp, 40h
0x18000795c  mov     rsi, rdx
0x18000795f  mov     rdi, rcx
0x180007962  mov     [rsp+58h+arg_10], 0
0x18000796b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007972  jz      short loc_180007986
0x180007974  mov     edx, 82h
0x180007979  mov     [rsp+58h+var_38], rsi
0x18000797e  mov     r9, rcx
0x180007981  call    WPP_SF_Sq
0x180007986  test    rdi, rdi
0x180007989  jnz     short loc_180007995
0x18000798b  mov     ebx, 57h ; 'W'
0x180007990  jmp     loc_180007A61
0x180007995  test    rsi, rsi
0x180007998  jz      short loc_18000798B
0x18000799a  lea     rdx, [rsp+58h+arg_10]
0x18000799f  mov     rcx, rdi
0x1800079a2  call    DhcpAdapterNameToIfId
0x1800079a7  mov     ebx, eax
0x1800079a9  test    eax, eax
0x1800079ab  jnz     loc_180007A61
0x1800079b1  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800079b8  jz      short loc_1800079DA
0x1800079ba  call    cs:__imp_GetCommandLineW
0x1800079c0  mov     edx, 83h
0x1800079c5  mov     [rsp+58h+var_38], rax
0x1800079ca  mov     r9, rdi
0x1800079cd  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800079d4  call    WPP_SF_SS
0x1800079d9  nop
0x1800079da  mov     [rsp+58h+arg_18], 0
0x1800079e3  mov     [rsp+58h+var_30], rsi
0x1800079e8  lea     rax, [rsp+58h+arg_10]
0x1800079ed  mov     [rsp+58h+var_38], rax
0x1800079f2  xor     r9d, r9d
0x1800079f5  xor     r8d, r8d; pReturnValue
0x1800079f8  lea     edx, [r9+18h]; nProcNum
0x1800079fc  lea     rcx, pProxyInfo; pProxyInfo
0x180007a03  call    cs:__imp_NdrClientCall3
0x180007a09  mov     rbx, rax
0x180007a0c  mov     [rsp+58h+arg_18], rax
0x180007a11  mov     [rsp+58h+var_28], eax
0x180007a15  jmp     short loc_180007A34
0x180007a17  mov     edi, eax
0x180007a19  mov     ebx, eax
0x180007a1b  mov     [rsp+58h+var_28], eax
0x180007a1f  call    cs:__imp_GetCommandLineW
0x180007a25  mov     rdx, rax
0x180007a28  mov     ecx, ebx
0x180007a2a  call    TraceRpcException
0x180007a2f  mov     rdi, [rsp+58h+arg_0]
0x180007a34  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007a3b  jz      short loc_180007A88
0x180007a3d  call    cs:__imp_GetCommandLineW
0x180007a43  mov     edx, 84h
0x180007a48  mov     [rsp+58h+var_30], rax
0x180007a4d  mov     [rsp+58h+var_38], rdi
0x180007a52  mov     r9d, ebx
0x180007a55  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007a5c  call    WPP_SF_DSS
0x180007a61  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007a68  jz      short loc_180007A88
0x180007a6a  mov     edx, 85h
0x180007a6f  mov     ecx, 404h
0x180007a74  mov     [rsp+58h+var_38], rdi
0x180007a79  mov     r9d, ebx
0x180007a7c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007a83  call    WPP_SF_DS
0x180007a88  mov     eax, ebx
0x180007a8a  add     rsp, 40h
0x180007a8e  pop     rdi
0x180007a8f  pop     rsi
0x180007a90  pop     rbx
0x180007a91  retn
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
