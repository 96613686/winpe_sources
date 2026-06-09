# DhcpGetFallbackParams

- ea: `0x180007480`
- end: `0x1800075c8`
- name: `DhcpGetFallbackParams`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180007480`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000753a`
- `RPCRT4!NdrClientCall3` at `0x18000753a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800074f1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007556`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007574`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800074f1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007556`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180007574`

## pseudocode

```c
__int64 __fastcall DhcpGetFallbackParams(__int64 a1, __int64 a2)
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
    WPP_SF_S(1028, 181, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( !a1 || !a2 )
  {
    Pointer = 87;
    goto LABEL_11;
  }
  Pointer = DhcpAdapterNameToIfId(a1, &v11);
  if ( Pointer )
  {
LABEL_11:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 184, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(v6, 182, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
  }
  v12.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 8u, 0).Pointer;
  Pointer = (unsigned int)v7.Pointer;
  v12.Pointer = v7.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v8 = GetCommandLineW();
    WPP_SF_DSS(v9, 183, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v8);
    goto LABEL_11;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180007480  mov     [rsp+arg_0], rcx
0x180007485  push    rbx
0x180007486  push    rsi
0x180007487  push    rdi
0x180007488  sub     rsp, 40h
0x18000748c  mov     rsi, rdx
0x18000748f  mov     rdi, rcx
0x180007492  mov     [rsp+58h+arg_10], 0
0x18000749b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800074a2  jz      short loc_1800074BD
0x1800074a4  mov     edx, 0B5h
0x1800074a9  mov     ecx, 404h
0x1800074ae  mov     r9, rdi
0x1800074b1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800074b8  call    WPP_SF_S
0x1800074bd  test    rdi, rdi
0x1800074c0  jnz     short loc_1800074CC
0x1800074c2  mov     ebx, 57h ; 'W'
0x1800074c7  jmp     loc_180007598
0x1800074cc  test    rsi, rsi
0x1800074cf  jz      short loc_1800074C2
0x1800074d1  lea     rdx, [rsp+58h+arg_10]
0x1800074d6  mov     rcx, rdi
0x1800074d9  call    DhcpAdapterNameToIfId
0x1800074de  mov     ebx, eax
0x1800074e0  test    eax, eax
0x1800074e2  jnz     loc_180007598
0x1800074e8  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800074ef  jz      short loc_180007511
0x1800074f1  call    cs:__imp_GetCommandLineW
0x1800074f7  mov     edx, 0B6h
0x1800074fc  mov     [rsp+58h+var_38], rax
0x180007501  mov     r9, rdi
0x180007504  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000750b  call    WPP_SF_SS
0x180007510  nop
0x180007511  mov     [rsp+58h+arg_18], 0
0x18000751a  mov     [rsp+58h+var_30], rsi
0x18000751f  lea     rax, [rsp+58h+arg_10]
0x180007524  mov     [rsp+58h+var_38], rax
0x180007529  xor     r9d, r9d
0x18000752c  xor     r8d, r8d; pReturnValue
0x18000752f  lea     edx, [r9+8]; nProcNum
0x180007533  lea     rcx, pProxyInfo; pProxyInfo
0x18000753a  call    cs:__imp_NdrClientCall3
0x180007540  mov     rbx, rax
0x180007543  mov     [rsp+58h+arg_18], rax
0x180007548  mov     [rsp+58h+var_28], eax
0x18000754c  jmp     short loc_18000756B
0x18000754e  mov     edi, eax
0x180007550  mov     ebx, eax
0x180007552  mov     [rsp+58h+var_28], eax
0x180007556  call    cs:__imp_GetCommandLineW
0x18000755c  mov     rdx, rax
0x18000755f  mov     ecx, ebx
0x180007561  call    TraceRpcException
0x180007566  mov     rdi, [rsp+58h+arg_0]
0x18000756b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007572  jz      short loc_1800075BE
0x180007574  call    cs:__imp_GetCommandLineW
0x18000757a  mov     edx, 0B7h
0x18000757f  mov     [rsp+58h+var_30], rax
0x180007584  mov     [rsp+58h+var_38], rdi
0x180007589  mov     r9d, ebx
0x18000758c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007593  call    WPP_SF_DSS
0x180007598  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000759f  jz      short loc_1800075BE
0x1800075a1  mov     edx, 0B8h
0x1800075a6  mov     ecx, 404h
0x1800075ab  mov     dword ptr [rsp+58h+var_38], ebx
0x1800075af  mov     r9, rdi
0x1800075b2  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800075b9  call    WPP_SF_SD
0x1800075be  mov     eax, ebx
0x1800075c0  add     rsp, 40h
0x1800075c4  pop     rdi
0x1800075c5  pop     rsi
0x1800075c6  pop     rbx
0x1800075c7  retn
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
