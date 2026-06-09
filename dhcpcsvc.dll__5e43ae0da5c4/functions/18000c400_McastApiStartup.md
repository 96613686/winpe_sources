# McastApiStartup

- ea: `0x18000c400`
- end: `0x18000c53a`
- name: `McastApiStartup`
- size: `314`
- prototype: `DWORD __stdcall(PDWORD Version)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x18000c400`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012a00`
- `0x180012a40`
- `0x180012df0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c487`
- `RPCRT4!NdrClientCall3` at `0x18000c487`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c448`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c4a3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c4bd`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c448`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c4a3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c4bd`

## pseudocode

```c
DWORD __stdcall McastApiStartup(PDWORD Version)
{
  __int64 v1; // r8
  DWORD Pointer; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v5; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_q(Version, 255, v1);
  if ( !Version )
  {
    Pointer = 87;
    goto LABEL_12;
  }
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 256, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_12;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 257, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x25u, 0).Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v5 = GetCommandLineW();
    WPP_SF_DS(1028, 258, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v5);
LABEL_12:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_d(1028, 259, WPP_e15037783097355a5233924022d92169_Traceguids, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000c400  mov     [rsp+arg_8], rbx
0x18000c405  push    rdi
0x18000c406  sub     rsp, 40h
0x18000c40a  mov     rbx, rcx
0x18000c40d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c414  jz      short loc_18000C423
0x18000c416  mov     edx, 0FFh
0x18000c41b  mov     r9, rcx
0x18000c41e  call    WPP_SF_q
0x18000c423  test    rbx, rbx
0x18000c426  jnz     short loc_18000C432
0x18000c428  mov     ebx, 57h ; 'W'
0x18000c42d  jmp     loc_18000C50B
0x18000c432  call    DhcpIsFSEGuestSystem
0x18000c437  test    eax, eax
0x18000c439  jnz     loc_18000C4E3
0x18000c43f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c446  jz      short loc_18000C468
0x18000c448  call    cs:__imp_GetCommandLineW
0x18000c44e  mov     r9, rax
0x18000c451  mov     edx, 101h
0x18000c456  mov     ecx, 404h
0x18000c45b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c462  call    WPP_SF_S
0x18000c467  nop
0x18000c468  mov     [rsp+48h+arg_0], 0
0x18000c471  mov     [rsp+48h+var_28], rbx
0x18000c476  xor     r9d, r9d
0x18000c479  xor     r8d, r8d; pReturnValue
0x18000c47c  lea     edx, [r9+25h]; nProcNum
0x18000c480  lea     rcx, pProxyInfo; pProxyInfo
0x18000c487  call    cs:__imp_NdrClientCall3
0x18000c48d  mov     rbx, rax
0x18000c490  mov     [rsp+48h+arg_0], rax
0x18000c495  mov     [rsp+48h+var_18], eax
0x18000c499  jmp     short loc_18000C4B4
0x18000c49b  mov     edi, eax
0x18000c49d  mov     ebx, eax
0x18000c49f  mov     [rsp+48h+var_18], eax
0x18000c4a3  call    cs:__imp_GetCommandLineW
0x18000c4a9  mov     rdx, rax
0x18000c4ac  mov     ecx, ebx
0x18000c4ae  call    TraceRpcException
0x18000c4b3  nop
0x18000c4b4  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c4bb  jz      short loc_18000C52D
0x18000c4bd  call    cs:__imp_GetCommandLineW
0x18000c4c3  mov     edx, 102h
0x18000c4c8  mov     ecx, 404h
0x18000c4cd  mov     [rsp+48h+var_28], rax
0x18000c4d2  mov     r9d, ebx
0x18000c4d5  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c4dc  call    WPP_SF_DS
0x18000c4e1  jmp     short loc_18000C50B
0x18000c4e3  mov     r9d, 32h ; '2'
0x18000c4e9  mov     ebx, r9d
0x18000c4ec  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c4f3  jz      short loc_18000C50B
0x18000c4f5  mov     edx, 100h
0x18000c4fa  mov     ecx, 401h
0x18000c4ff  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c506  call    WPP_SF_d
0x18000c50b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c512  jz      short loc_18000C52D
0x18000c514  mov     edx, 103h
0x18000c519  mov     ecx, 404h
0x18000c51e  mov     r9d, ebx
0x18000c521  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c528  call    WPP_SF_d
0x18000c52d  mov     eax, ebx
0x18000c52f  mov     rbx, [rsp+48h+arg_8]
0x18000c534  add     rsp, 40h
0x18000c538  pop     rdi
0x18000c539  retn
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
