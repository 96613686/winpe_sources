# Dhcpv4CheckServerAvailability

- ea: `0x18000bf80`
- end: `0x18000c0fe`
- name: `Dhcpv4CheckServerAvailability`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x18000bf80`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c047`
- `RPCRT4!NdrClientCall3` at `0x18000c047`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c000`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c063`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c081`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c000`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c063`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c081`

## pseudocode

```c
__int64 __fastcall Dhcpv4CheckServerAvailability(__int64 a1, _DWORD *a2)
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
    WPP_SF_S(1028, 10, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 11, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_14;
  }
  if ( !a1 || !a2 )
  {
    Pointer = 87;
    goto LABEL_14;
  }
  Pointer = DhcpAdapterNameToIfId(a1, &v11);
  if ( Pointer )
  {
LABEL_14:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 14, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  *a2 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v6,
      Pointer + 12,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      a1,
      (__int64)CommandLineW);
  }
  v12.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0).Pointer;
  Pointer = (unsigned int)v7.Pointer;
  v12.Pointer = v7.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v8 = GetCommandLineW();
    WPP_SF_DSS(v9, 13, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v8);
    goto LABEL_14;
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000bf80  mov     [rsp+arg_0], rcx
0x18000bf85  push    rbx
0x18000bf86  push    rsi
0x18000bf87  push    rdi
0x18000bf88  sub     rsp, 40h
0x18000bf8c  mov     rsi, rdx
0x18000bf8f  mov     rdi, rcx
0x18000bf92  mov     [rsp+58h+arg_10], 0
0x18000bf9b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bfa2  jz      short loc_18000BFBD
0x18000bfa4  mov     edx, 0Ah
0x18000bfa9  mov     ecx, 404h
0x18000bfae  mov     r9, rdi
0x18000bfb1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bfb8  call    WPP_SF_S
0x18000bfbd  call    DhcpIsFSEGuestSystem
0x18000bfc2  test    eax, eax
0x18000bfc4  jnz     loc_18000C0A7
0x18000bfca  test    rdi, rdi
0x18000bfcd  jnz     short loc_18000BFD9
0x18000bfcf  mov     ebx, 57h ; 'W'
0x18000bfd4  jmp     loc_18000C0CE
0x18000bfd9  test    rsi, rsi
0x18000bfdc  jz      short loc_18000BFCF
0x18000bfde  lea     rdx, [rsp+58h+arg_10]
0x18000bfe3  mov     rcx, rdi
0x18000bfe6  call    DhcpAdapterNameToIfId
0x18000bfeb  mov     ebx, eax
0x18000bfed  test    eax, eax
0x18000bfef  jnz     loc_18000C0CE
0x18000bff5  mov     [rsi], eax
0x18000bff7  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bffe  jz      short loc_18000C01E
0x18000c000  call    cs:__imp_GetCommandLineW
0x18000c006  lea     edx, [rbx+0Ch]
0x18000c009  mov     [rsp+58h+var_38], rax
0x18000c00e  mov     r9, rdi
0x18000c011  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c018  call    WPP_SF_SS
0x18000c01d  nop
0x18000c01e  mov     [rsp+58h+arg_18], 0
0x18000c027  mov     [rsp+58h+var_30], rsi
0x18000c02c  lea     rax, [rsp+58h+arg_10]
0x18000c031  mov     [rsp+58h+var_38], rax
0x18000c036  xor     r9d, r9d
0x18000c039  xor     r8d, r8d; pReturnValue
0x18000c03c  lea     edx, [r9+4]; nProcNum
0x18000c040  lea     rcx, pProxyInfo; pProxyInfo
0x18000c047  call    cs:__imp_NdrClientCall3
0x18000c04d  mov     rbx, rax
0x18000c050  mov     [rsp+58h+arg_18], rax
0x18000c055  mov     [rsp+58h+var_28], eax
0x18000c059  jmp     short loc_18000C078
0x18000c05b  mov     edi, eax
0x18000c05d  mov     ebx, eax
0x18000c05f  mov     [rsp+58h+var_28], eax
0x18000c063  call    cs:__imp_GetCommandLineW
0x18000c069  mov     rdx, rax
0x18000c06c  mov     ecx, ebx
0x18000c06e  call    TraceRpcException
0x18000c073  mov     rdi, [rsp+58h+arg_0]
0x18000c078  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c07f  jz      short loc_18000C0F4
0x18000c081  call    cs:__imp_GetCommandLineW
0x18000c087  mov     edx, 0Dh
0x18000c08c  mov     [rsp+58h+var_30], rax
0x18000c091  mov     [rsp+58h+var_38], rdi
0x18000c096  mov     r9d, ebx
0x18000c099  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c0a0  call    WPP_SF_DSS
0x18000c0a5  jmp     short loc_18000C0CE
0x18000c0a7  mov     r9d, 32h ; '2'
0x18000c0ad  mov     ebx, r9d
0x18000c0b0  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c0b7  jz      short loc_18000C0CE
0x18000c0b9  lea     edx, [r9-27h]
0x18000c0bd  mov     ecx, 401h
0x18000c0c2  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c0c9  call    WPP_SF_d
0x18000c0ce  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c0d5  jz      short loc_18000C0F4
0x18000c0d7  mov     edx, 0Eh
0x18000c0dc  mov     ecx, 404h
0x18000c0e1  mov     dword ptr [rsp+58h+var_38], ebx
0x18000c0e5  mov     r9, rdi
0x18000c0e8  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c0ef  call    WPP_SF_SD
0x18000c0f4  mov     eax, ebx
0x18000c0f6  add     rsp, 40h
0x18000c0fa  pop     rdi
0x18000c0fb  pop     rsi
0x18000c0fc  pop     rbx
0x18000c0fd  retn
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
