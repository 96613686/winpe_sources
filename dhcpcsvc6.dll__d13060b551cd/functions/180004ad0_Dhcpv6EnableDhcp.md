# Dhcpv6EnableDhcp

- ea: `0x180004ad0`
- end: `0x180004c32`
- name: `Dhcpv6EnableDhcp`
- size: `354`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001ff0`
- `0x180003650`
- `0x180004ad0`
- `0x1800072fc`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004b87`
- `RPCRT4!NdrClientCall3` at `0x180004b87`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004b41`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004ba3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004bc1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004b41`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004ba3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004bc1`

## pseudocode

```c
__int64 __fastcall Dhcpv6EnableDhcp(const WCHAR *a1)
{
  int v2; // ecx
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v5; // ecx
  CLIENT_CALL_RETURN v6; // rax
  LPWSTR v7; // rax
  int v8; // ecx
  int v9; // r8d
  NET_LUID v11; // [rsp+70h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+78h] [rbp+20h]

  v11.Value = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 76, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 77, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
    goto LABEL_13;
  }
  if ( !a1 )
  {
    Pointer = 87;
    goto LABEL_13;
  }
  Pointer = Dhcpv6AdapterNameToIfId(a1, &v11);
  if ( Pointer )
  {
LABEL_13:
    if ( (xmmword_18000F160 & 0x10) != 0 )
      WPP_SF_SD(v2, 80, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v5,
      Pointer + 78,
      (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
      (_DWORD)a1,
      (__int64)CommandLineW);
  }
  v12.Simple = 0;
  v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0).Pointer;
  Pointer = (unsigned int)v6.Pointer;
  v12.Pointer = v6.Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v7 = GetCommandLineW();
    WPP_SF_DSS(v8, 79, v9, Pointer, (__int64)a1, (__int64)v7);
    goto LABEL_13;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180004ad0  mov     [rsp+arg_0], rcx
0x180004ad5  push    rbx
0x180004ad6  push    rsi
0x180004ad7  push    rdi
0x180004ad8  sub     rsp, 40h
0x180004adc  mov     esi, edx
0x180004ade  mov     rdi, rcx
0x180004ae1  mov     [rsp+58h+arg_10], 0
0x180004aea  test    byte ptr cs:xmmword_18000F160, 10h
0x180004af1  jz      short loc_180004B07
0x180004af3  mov     edx, 4Ch ; 'L'
0x180004af8  mov     r9, rcx
0x180004afb  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004b02  call    WPP_SF_S
0x180004b07  call    DhcpIsFSEGuestSystem
0x180004b0c  test    eax, eax
0x180004b0e  jnz     loc_180004BE0
0x180004b14  test    rdi, rdi
0x180004b17  jnz     short loc_180004B21
0x180004b19  lea     ebx, [rax+57h]
0x180004b1c  jmp     loc_180004C07
0x180004b21  lea     rdx, [rsp+58h+arg_10]
0x180004b26  mov     rcx, rdi
0x180004b29  call    Dhcpv6AdapterNameToIfId
0x180004b2e  mov     ebx, eax
0x180004b30  test    eax, eax
0x180004b32  jnz     loc_180004C07
0x180004b38  test    byte ptr cs:xmmword_18000F160, 10h
0x180004b3f  jz      short loc_180004B5F
0x180004b41  call    cs:__imp_GetCommandLineW
0x180004b47  lea     edx, [rbx+4Eh]
0x180004b4a  mov     [rsp+58h+var_38], rax
0x180004b4f  mov     r9, rdi
0x180004b52  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004b59  call    WPP_SF_SS
0x180004b5e  nop
0x180004b5f  mov     [rsp+58h+arg_18], 0
0x180004b68  mov     dword ptr [rsp+58h+var_30], esi
0x180004b6c  lea     rax, [rsp+58h+arg_10]
0x180004b71  mov     [rsp+58h+var_38], rax
0x180004b76  xor     r9d, r9d
0x180004b79  xor     r8d, r8d; pReturnValue
0x180004b7c  lea     edx, [r9+0Bh]; nProcNum
0x180004b80  lea     rcx, pProxyInfo; pProxyInfo
0x180004b87  call    cs:__imp_NdrClientCall3
0x180004b8d  mov     rbx, rax
0x180004b90  mov     [rsp+58h+arg_18], rax
0x180004b95  mov     [rsp+58h+var_28], eax
0x180004b99  jmp     short loc_180004BB8
0x180004b9b  mov     edi, eax
0x180004b9d  mov     ebx, eax
0x180004b9f  mov     [rsp+58h+var_28], eax
0x180004ba3  call    cs:__imp_GetCommandLineW
0x180004ba9  mov     rdx, rax
0x180004bac  mov     ecx, ebx
0x180004bae  call    TraceRpcException
0x180004bb3  mov     rdi, [rsp+58h+arg_0]
0x180004bb8  test    byte ptr cs:xmmword_18000F160, 10h
0x180004bbf  jz      short loc_180004C28
0x180004bc1  call    cs:__imp_GetCommandLineW
0x180004bc7  mov     edx, 4Fh ; 'O'
0x180004bcc  mov     [rsp+58h+var_30], rax
0x180004bd1  mov     [rsp+58h+var_38], rdi
0x180004bd6  mov     r9d, ebx
0x180004bd9  call    WPP_SF_DSS
0x180004bde  jmp     short loc_180004C07
0x180004be0  mov     r9d, 32h ; '2'
0x180004be6  mov     ebx, r9d
0x180004be9  test    byte ptr cs:xmmword_18000F160, 2
0x180004bf0  jz      short loc_180004C07
0x180004bf2  lea     edx, [r9+1Bh]
0x180004bf6  mov     ecx, 401h
0x180004bfb  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004c02  call    WPP_SF_D
0x180004c07  test    byte ptr cs:xmmword_18000F160, 10h
0x180004c0e  jz      short loc_180004C28
0x180004c10  mov     edx, 50h ; 'P'
0x180004c15  mov     dword ptr [rsp+58h+var_38], ebx
0x180004c19  mov     r9, rdi
0x180004c1c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004c23  call    WPP_SF_SD
0x180004c28  mov     eax, ebx
0x180004c2a  add     rsp, 40h
0x180004c2e  pop     rdi
0x180004c2f  pop     rsi
0x180004c30  pop     rbx
0x180004c31  retn
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
