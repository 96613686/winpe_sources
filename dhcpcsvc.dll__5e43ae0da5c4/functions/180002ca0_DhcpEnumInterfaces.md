# DhcpEnumInterfaces

- ea: `0x180002ca0`
- end: `0x180002e16`
- name: `DhcpEnumInterfaces`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002ca0`
- `0x180002e20`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002d08`
- `RPCRT4!NdrClientCall3` at `0x180002d08`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010bfe`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010bfe`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002d24`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002dab`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002dcf`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002d24`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002dab`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002dcf`

## pseudocode

```c
__int64 __fastcall DhcpEnumInterfaces(_OWORD *a1)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v5; // rax
  _OWORD v6[2]; // [rsp+38h] [rbp-20h] BYREF

  v6[0] = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 134, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( a1 )
  {
    *a1 = 0;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_S(1028, 135, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
    }
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x10u, 0, 0, v6).Pointer;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v5 = GetCommandLineW();
      WPP_SF_DS(1028, 136, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v5);
    }
    if ( !Pointer )
    {
      *a1 = v6[0];
      *((_QWORD *)&v6[0] + 1) = 0;
      LODWORD(v6[0]) = 0;
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpFreeEnumeratedInterfaces(v6);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 137, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180002ca0  mov     [rsp+arg_10], rbx
0x180002ca5  mov     [rsp+arg_0], rcx
0x180002caa  push    rdi
0x180002cab  sub     rsp, 50h
0x180002caf  mov     rdi, rcx
0x180002cb2  xorps   xmm0, xmm0
0x180002cb5  movups  [rsp+58h+var_20], xmm0
0x180002cba  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002cc1  jnz     loc_180002D89
0x180002cc7  test    rdi, rdi
0x180002cca  jz      loc_180002DA4
0x180002cd0  xorps   xmm0, xmm0
0x180002cd3  movups  xmmword ptr [rdi], xmm0
0x180002cd6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002cdd  jnz     loc_180002DAB
0x180002ce3  mov     [rsp+58h+arg_8], 0
0x180002cec  lea     rax, [rsp+58h+var_20]
0x180002cf1  mov     [rsp+58h+var_38], rax
0x180002cf6  xor     r9d, r9d
0x180002cf9  xor     r8d, r8d; pReturnValue
0x180002cfc  mov     edx, 10h; nProcNum
0x180002d01  lea     rcx, pProxyInfo; pProxyInfo
0x180002d08  call    cs:__imp_NdrClientCall3
0x180002d0e  mov     rbx, rax
0x180002d11  mov     [rsp+58h+arg_8], rax
0x180002d16  mov     [rsp+58h+var_28], eax
0x180002d1a  jmp     short loc_180002D39
0x180002d1c  mov     edi, eax
0x180002d1e  mov     ebx, eax
0x180002d20  mov     [rsp+58h+var_28], eax
0x180002d24  call    cs:__imp_GetCommandLineW
0x180002d2a  mov     rdx, rax
0x180002d2d  mov     ecx, ebx
0x180002d2f  call    TraceRpcException
0x180002d34  mov     rdi, [rsp+58h+arg_0]
0x180002d39  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002d40  jnz     loc_180002DCF
0x180002d46  test    ebx, ebx
0x180002d48  jz      short loc_180002D6E
0x180002d4a  lea     rcx, [rsp+58h+var_20]
0x180002d4f  call    DhcpFreeEnumeratedInterfaces
0x180002d54  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002d5b  jnz     loc_180002DF8
0x180002d61  mov     eax, ebx
0x180002d63  mov     rbx, [rsp+58h+arg_10]
0x180002d68  add     rsp, 50h
0x180002d6c  pop     rdi
0x180002d6d  retn
0x180002d6e  movups  xmm0, [rsp+58h+var_20]
0x180002d73  movups  xmmword ptr [rdi], xmm0
0x180002d76  mov     qword ptr [rsp+58h+var_20+8], 0
0x180002d7f  mov     dword ptr [rsp+58h+var_20], 0
0x180002d87  jmp     short loc_180002D4A
0x180002d89  mov     edx, 86h
0x180002d8e  mov     ecx, 404h
0x180002d93  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180002d9a  call    WPP_SF_
0x180002d9f  jmp     loc_180002CC7
0x180002da4  mov     ebx, 57h ; 'W'
0x180002da9  jmp     short loc_180002D4A
0x180002dab  call    cs:__imp_GetCommandLineW
0x180002db1  mov     r9, rax
0x180002db4  mov     edx, 87h
0x180002db9  mov     ecx, 404h
0x180002dbe  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180002dc5  call    WPP_SF_S
0x180002dca  jmp     loc_180002CE3
0x180002dcf  call    cs:__imp_GetCommandLineW
0x180002dd5  mov     edx, 88h
0x180002dda  mov     ecx, 404h
0x180002ddf  mov     [rsp+58h+var_38], rax
0x180002de4  mov     r9d, ebx
0x180002de7  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180002dee  call    WPP_SF_DS
0x180002df3  jmp     loc_180002D46
0x180002df8  mov     edx, 89h
0x180002dfd  mov     ecx, 404h
0x180002e02  mov     r9d, ebx
0x180002e05  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180002e0c  call    WPP_SF_d
0x180002e11  jmp     loc_180002D61
0x180010bf0  push    rbp
0x180010bf2  sub     rsp, 30h
0x180010bf6  mov     rbp, rdx
0x180010bf9  mov     rcx, [rcx]
0x180010bfc  mov     ecx, [rcx]; ExceptionCode
0x180010bfe  call    cs:__imp_I_RpcExceptionFilter
0x180010c04  nop
0x180010c05  add     rsp, 30h
0x180010c09  pop     rbp
0x180010c0a  retn
```
