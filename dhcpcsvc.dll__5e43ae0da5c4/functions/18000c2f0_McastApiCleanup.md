# McastApiCleanup

- ea: `0x18000c2f0`
- end: `0x18000c3f2`
- name: `McastApiCleanup`
- size: `258`
- prototype: `void __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x18000c2f0`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c35e`
- `RPCRT4!NdrClientCall3` at `0x18000c35e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010d60`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010d60`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c32d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c368`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c382`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c32d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c368`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c382`

## pseudocode

```c
void __stdcall McastApiCleanup()
{
  unsigned int v0; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v2; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_(1028, 260, WPP_e15037783097355a5233924022d92169_Traceguids);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v0 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 261, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_10;
  }
  v0 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 262, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x26u, 0);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v2 = GetCommandLineW();
    WPP_SF_S(1028, 263, WPP_e15037783097355a5233924022d92169_Traceguids, v2);
LABEL_10:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_d(1028, 264, WPP_e15037783097355a5233924022d92169_Traceguids, v0);
  }
}

```

## disassembly

```asm
0x18000c2f0  push    rbx
0x18000c2f2  sub     rsp, 20h
0x18000c2f6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c2fd  jz      short loc_18000C315
0x18000c2ff  mov     edx, 104h
0x18000c304  mov     ecx, 404h
0x18000c309  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c310  call    WPP_SF_
0x18000c315  call    DhcpIsFSEGuestSystem
0x18000c31a  test    eax, eax
0x18000c31c  jnz     loc_18000C3A3
0x18000c322  xor     ebx, ebx
0x18000c324  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c32b  jz      short loc_18000C34D
0x18000c32d  call    cs:__imp_GetCommandLineW
0x18000c333  mov     r9, rax
0x18000c336  mov     edx, 106h
0x18000c33b  mov     ecx, 404h
0x18000c340  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c347  call    WPP_SF_S
0x18000c34c  nop
0x18000c34d  xor     r9d, r9d
0x18000c350  xor     r8d, r8d; pReturnValue
0x18000c353  lea     edx, [r9+26h]; nProcNum
0x18000c357  lea     rcx, pProxyInfo; pProxyInfo
0x18000c35e  call    cs:__imp_NdrClientCall3
0x18000c364  jmp     short loc_18000C379
0x18000c366  mov     ebx, eax
0x18000c368  call    cs:__imp_GetCommandLineW
0x18000c36e  mov     rdx, rax
0x18000c371  mov     ecx, ebx
0x18000c373  call    TraceRpcException
0x18000c378  nop
0x18000c379  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c380  jz      short loc_18000C3EC
0x18000c382  call    cs:__imp_GetCommandLineW
0x18000c388  mov     r9, rax
0x18000c38b  mov     edx, 107h
0x18000c390  mov     ecx, 404h
0x18000c395  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c39c  call    WPP_SF_S
0x18000c3a1  jmp     short loc_18000C3CA
0x18000c3a3  mov     ebx, 32h ; '2'
0x18000c3a8  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c3af  jz      short loc_18000C3CA
0x18000c3b1  mov     edx, 105h
0x18000c3b6  mov     ecx, 401h
0x18000c3bb  mov     r9d, ebx
0x18000c3be  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c3c5  call    WPP_SF_d
0x18000c3ca  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c3d1  jz      short loc_18000C3EC
0x18000c3d3  mov     edx, 108h
0x18000c3d8  mov     ecx, 404h
0x18000c3dd  mov     r9d, ebx
0x18000c3e0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c3e7  call    WPP_SF_d
0x18000c3ec  add     rsp, 20h
0x18000c3f0  pop     rbx
0x18000c3f1  retn
0x180010d52  push    rbp
0x180010d54  sub     rsp, 20h
0x180010d58  mov     rbp, rdx
0x180010d5b  mov     rcx, [rcx]
0x180010d5e  mov     ecx, [rcx]; ExceptionCode
0x180010d60  call    cs:__imp_I_RpcExceptionFilter
0x180010d66  nop
0x180010d67  add     rsp, 20h
0x180010d6b  pop     rbp
0x180010d6c  retn
```
