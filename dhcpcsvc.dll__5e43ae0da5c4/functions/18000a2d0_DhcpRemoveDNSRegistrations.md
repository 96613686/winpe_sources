# DhcpRemoveDNSRegistrations

- ea: `0x18000a2d0`
- end: `0x18000a3fb`
- name: `DhcpRemoveDNSRegistrations`
- size: `299`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x18000a2d0`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a349`
- `RPCRT4!NdrClientCall3` at `0x18000a349`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a30f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a365`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a37f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a30f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a365`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000a37f`

## pseudocode

```c
DWORD __stdcall DhcpRemoveDNSRegistrations()
{
  LPWSTR CommandLineW; // rax
  DWORD Pointer; // ebx
  LPWSTR v2; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 125, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 126, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_10;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 127, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0).Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v2 = GetCommandLineW();
    WPP_SF_DS(1028, 128, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v2);
LABEL_10:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_d(1028, 129, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000a2d0  mov     [rsp+arg_8], rbx
0x18000a2d5  push    rdi
0x18000a2d6  sub     rsp, 40h
0x18000a2da  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a2e1  jz      short loc_18000A2F9
0x18000a2e3  mov     edx, 7Dh ; '}'
0x18000a2e8  mov     ecx, 404h
0x18000a2ed  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a2f4  call    WPP_SF_
0x18000a2f9  call    DhcpIsFSEGuestSystem
0x18000a2fe  test    eax, eax
0x18000a300  jnz     loc_18000A3A5
0x18000a306  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a30d  jz      short loc_18000A32F
0x18000a30f  call    cs:__imp_GetCommandLineW
0x18000a315  mov     r9, rax
0x18000a318  mov     edx, 7Fh
0x18000a31d  mov     ecx, 404h
0x18000a322  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a329  call    WPP_SF_S
0x18000a32e  nop
0x18000a32f  mov     [rsp+48h+arg_0], 0
0x18000a338  xor     r9d, r9d
0x18000a33b  xor     r8d, r8d; pReturnValue
0x18000a33e  lea     edx, [r9+0Bh]; nProcNum
0x18000a342  lea     rcx, pProxyInfo; pProxyInfo
0x18000a349  call    cs:__imp_NdrClientCall3
0x18000a34f  mov     rbx, rax
0x18000a352  mov     [rsp+48h+arg_0], rax
0x18000a357  mov     [rsp+48h+var_18], eax
0x18000a35b  jmp     short loc_18000A376
0x18000a35d  mov     edi, eax
0x18000a35f  mov     ebx, eax
0x18000a361  mov     [rsp+48h+var_18], eax
0x18000a365  call    cs:__imp_GetCommandLineW
0x18000a36b  mov     rdx, rax
0x18000a36e  mov     ecx, ebx
0x18000a370  call    TraceRpcException
0x18000a375  nop
0x18000a376  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a37d  jz      short loc_18000A3EE
0x18000a37f  call    cs:__imp_GetCommandLineW
0x18000a385  mov     edx, 80h
0x18000a38a  mov     ecx, 404h
0x18000a38f  mov     [rsp+48h+var_28], rax
0x18000a394  mov     r9d, ebx
0x18000a397  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a39e  call    WPP_SF_DS
0x18000a3a3  jmp     short loc_18000A3CC
0x18000a3a5  mov     r9d, 32h ; '2'
0x18000a3ab  mov     ebx, r9d
0x18000a3ae  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000a3b5  jz      short loc_18000A3CC
0x18000a3b7  lea     edx, [r9+4Ch]
0x18000a3bb  mov     ecx, 401h
0x18000a3c0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a3c7  call    WPP_SF_d
0x18000a3cc  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a3d3  jz      short loc_18000A3EE
0x18000a3d5  mov     edx, 81h
0x18000a3da  mov     ecx, 404h
0x18000a3df  mov     r9d, ebx
0x18000a3e2  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a3e9  call    WPP_SF_d
0x18000a3ee  mov     eax, ebx
0x18000a3f0  mov     rbx, [rsp+48h+arg_8]
0x18000a3f5  add     rsp, 40h
0x18000a3f9  pop     rdi
0x18000a3fa  retn
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
