# Dhcpv6ReleaseParameters

- ea: `0x180005040`
- end: `0x1800051a2`
- name: `Dhcpv6ReleaseParameters`
- size: `354`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001ff0`
- `0x180003650`
- `0x180005040`
- `0x1800072fc`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800050f4`
- `RPCRT4!NdrClientCall3` at `0x1800050f4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800050b2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005110`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000512e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800050b2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180005110`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000512e`

## pseudocode

```c
__int64 __fastcall Dhcpv6ReleaseParameters(const WCHAR *a1)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v4; // ecx
  CLIENT_CALL_RETURN v5; // rax
  LPWSTR v6; // rax
  int v7; // ecx
  int v8; // r8d
  NET_LUID v10; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v11; // [rsp+60h] [rbp+18h]

  v10.Value = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 15, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( !a1 )
  {
    Pointer = 87;
    goto LABEL_13;
  }
  if ( DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 16, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
    goto LABEL_13;
  }
  Pointer = Dhcpv6AdapterNameToIfId(a1, &v10);
  if ( Pointer )
  {
LABEL_13:
    if ( (xmmword_18000F160 & 0x10) != 0 )
      WPP_SF_SD((_DWORD)a1, 19, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v4,
      Pointer + 17,
      (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
      (_DWORD)a1,
      (__int64)CommandLineW);
  }
  v11.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0).Pointer;
  Pointer = (unsigned int)v5.Pointer;
  v11.Pointer = v5.Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v6 = GetCommandLineW();
    WPP_SF_DSS(v7, 18, v8, Pointer, (__int64)a1, (__int64)v6);
    goto LABEL_13;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180005040  mov     [rsp+arg_18], rbx
0x180005045  mov     [rsp+arg_0], rcx
0x18000504a  push    rdi
0x18000504b  sub     rsp, 40h
0x18000504f  mov     rdi, rcx
0x180005052  mov     [rsp+48h+arg_8], 0
0x18000505b  test    byte ptr cs:xmmword_18000F160, 10h
0x180005062  jz      short loc_180005078
0x180005064  mov     edx, 0Fh
0x180005069  mov     r9, rcx
0x18000506c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005073  call    WPP_SF_S
0x180005078  test    rdi, rdi
0x18000507b  jnz     short loc_180005085
0x18000507d  lea     ebx, [rdi+57h]
0x180005080  jmp     loc_180005174
0x180005085  call    DhcpIsFSEGuestSystem
0x18000508a  test    eax, eax
0x18000508c  jnz     loc_18000514D
0x180005092  lea     rdx, [rsp+48h+arg_8]
0x180005097  mov     rcx, rdi
0x18000509a  call    Dhcpv6AdapterNameToIfId
0x18000509f  mov     ebx, eax
0x1800050a1  test    eax, eax
0x1800050a3  jnz     loc_180005174
0x1800050a9  test    byte ptr cs:xmmword_18000F160, 10h
0x1800050b0  jz      short loc_1800050D0
0x1800050b2  call    cs:__imp_GetCommandLineW
0x1800050b8  lea     edx, [rbx+11h]
0x1800050bb  mov     [rsp+48h+var_28], rax
0x1800050c0  mov     r9, rdi
0x1800050c3  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800050ca  call    WPP_SF_SS
0x1800050cf  nop
0x1800050d0  mov     [rsp+48h+arg_10], 0
0x1800050d9  lea     rax, [rsp+48h+arg_8]
0x1800050de  mov     [rsp+48h+var_28], rax
0x1800050e3  xor     r9d, r9d
0x1800050e6  xor     r8d, r8d; pReturnValue
0x1800050e9  lea     edx, [r9+6]; nProcNum
0x1800050ed  lea     rcx, pProxyInfo; pProxyInfo
0x1800050f4  call    cs:__imp_NdrClientCall3
0x1800050fa  mov     rbx, rax
0x1800050fd  mov     [rsp+48h+arg_10], rax
0x180005102  mov     [rsp+48h+var_18], eax
0x180005106  jmp     short loc_180005125
0x180005108  mov     edi, eax
0x18000510a  mov     ebx, eax
0x18000510c  mov     [rsp+48h+var_18], eax
0x180005110  call    cs:__imp_GetCommandLineW
0x180005116  mov     rdx, rax
0x180005119  mov     ecx, ebx
0x18000511b  call    TraceRpcException
0x180005120  mov     rdi, [rsp+48h+arg_0]
0x180005125  test    byte ptr cs:xmmword_18000F160, 10h
0x18000512c  jz      short loc_180005195
0x18000512e  call    cs:__imp_GetCommandLineW
0x180005134  mov     edx, 12h
0x180005139  mov     [rsp+48h+var_20], rax
0x18000513e  mov     [rsp+48h+var_28], rdi
0x180005143  mov     r9d, ebx
0x180005146  call    WPP_SF_DSS
0x18000514b  jmp     short loc_180005174
0x18000514d  mov     r9d, 32h ; '2'
0x180005153  mov     ebx, r9d
0x180005156  test    byte ptr cs:xmmword_18000F160, 2
0x18000515d  jz      short loc_180005174
0x18000515f  lea     edx, [r9-22h]
0x180005163  mov     ecx, 401h
0x180005168  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000516f  call    WPP_SF_D
0x180005174  test    byte ptr cs:xmmword_18000F160, 10h
0x18000517b  jz      short loc_180005195
0x18000517d  mov     edx, 13h
0x180005182  mov     dword ptr [rsp+48h+var_28], ebx
0x180005186  mov     r9, rdi
0x180005189  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005190  call    WPP_SF_SD
0x180005195  mov     eax, ebx
0x180005197  mov     rbx, [rsp+48h+arg_18]
0x18000519c  add     rsp, 40h
0x1800051a0  pop     rdi
0x1800051a1  retn
0x180007a0c  push    rbp
0x180007a0e  sub     rsp, 30h
0x180007a12  mov     rbp, rdx
0x180007a15  mov     rcx, [rcx]
0x180007a18  mov     ecx, [rcx]; ExceptionCode
0x180007a1a  call    cs:__imp_I_RpcExceptionFilter
0x180007a20  nop
0x180007a21  add     rsp, 30h
0x180007a25  pop     rbp
0x180007a26  retn
```
