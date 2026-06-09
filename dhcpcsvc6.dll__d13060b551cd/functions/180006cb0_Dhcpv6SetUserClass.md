# Dhcpv6SetUserClass

- ea: `0x180006cb0`
- end: `0x180006e3d`
- name: `Dhcpv6SetUserClass`
- size: `397`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001ff0`
- `0x180003650`
- `0x180006cb0`
- `0x1800072fc`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006d85`
- `RPCRT4!NdrClientCall3` at `0x180006d85`
- `RPCRT4!I_RpcExceptionFilter` at `0x180007a80`
- `RPCRT4!I_RpcExceptionFilter` at `0x180007a80`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006d37`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006da1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006dbf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006d37`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006da1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180006dbf`

## pseudocode

```c
__int64 __fastcall Dhcpv6SetUserClass(const WCHAR *a1, __int64 a2, int a3)
{
  int v6; // ecx
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v9; // ecx
  LPWSTR v10; // rax
  int v11; // ecx
  int v12; // r8d
  NET_LUID v14; // [rsp+88h] [rbp+20h] BYREF

  v14.Value = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 71, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a1);
  if ( DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 72, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
    goto LABEL_15;
  }
  if ( !a1 || a3 && !a2 )
  {
    Pointer = 87;
LABEL_15:
    if ( (xmmword_18000F160 & 0x10) != 0 )
      WPP_SF_SD(v6, 75, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a1, Pointer);
    return Pointer;
  }
  Pointer = Dhcpv6AdapterNameToIfId(a1, &v14);
  if ( Pointer )
    goto LABEL_15;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v9,
      Pointer + 73,
      (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
      (_DWORD)a1,
      (__int64)CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 9u, 0).Pointer;
  if ( (xmmword_18000F160 & 0x10) != 0 )
  {
    v10 = GetCommandLineW();
    WPP_SF_DSS(v11, 74, v12, Pointer, (__int64)a1, (__int64)v10);
    goto LABEL_15;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180006cb0  mov     rax, rsp
0x180006cb3  mov     [rax+10h], rbx
0x180006cb7  mov     [rax+8], rcx
0x180006cbb  push    rsi
0x180006cbc  push    rdi
0x180006cbd  push    r14
0x180006cbf  sub     rsp, 50h
0x180006cc3  mov     esi, r8d
0x180006cc6  mov     r14, rdx
0x180006cc9  mov     rdi, rcx
0x180006ccc  mov     qword ptr [rax+20h], 0
0x180006cd4  test    byte ptr cs:xmmword_18000F160, 10h
0x180006cdb  jz      short loc_180006CF1
0x180006cdd  mov     edx, 47h ; 'G'
0x180006ce2  mov     r9, rcx
0x180006ce5  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006cec  call    WPP_SF_S
0x180006cf1  call    DhcpIsFSEGuestSystem
0x180006cf6  test    eax, eax
0x180006cf8  jnz     loc_180006DE5
0x180006cfe  test    rdi, rdi
0x180006d01  jz      loc_180006DDE
0x180006d07  test    esi, esi
0x180006d09  jz      short loc_180006D14
0x180006d0b  test    r14, r14
0x180006d0e  jz      loc_180006DDE
0x180006d14  lea     rdx, [rsp+68h+arg_18]
0x180006d1c  mov     rcx, rdi
0x180006d1f  call    Dhcpv6AdapterNameToIfId
0x180006d24  mov     ebx, eax
0x180006d26  test    eax, eax
0x180006d28  jnz     loc_180006E0C
0x180006d2e  test    byte ptr cs:xmmword_18000F160, 10h
0x180006d35  jz      short loc_180006D55
0x180006d37  call    cs:__imp_GetCommandLineW
0x180006d3d  lea     edx, [rbx+49h]
0x180006d40  mov     [rsp+68h+var_48], rax
0x180006d45  mov     r9, rdi
0x180006d48  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006d4f  call    WPP_SF_SS
0x180006d54  nop
0x180006d55  mov     [rsp+68h+var_20], 0
0x180006d5e  mov     [rsp+68h+var_38], esi
0x180006d62  mov     [rsp+68h+var_40], r14
0x180006d67  lea     rax, [rsp+68h+arg_18]
0x180006d6f  mov     [rsp+68h+var_48], rax
0x180006d74  xor     r9d, r9d
0x180006d77  xor     r8d, r8d; pReturnValue
0x180006d7a  lea     edx, [r9+9]; nProcNum
0x180006d7e  lea     rcx, pProxyInfo; pProxyInfo
0x180006d85  call    cs:__imp_NdrClientCall3
0x180006d8b  mov     rbx, rax
0x180006d8e  mov     [rsp+68h+var_20], rax
0x180006d93  mov     [rsp+68h+var_28], eax
0x180006d97  jmp     short loc_180006DB6
0x180006d99  mov     edi, eax
0x180006d9b  mov     ebx, eax
0x180006d9d  mov     [rsp+68h+var_28], eax
0x180006da1  call    cs:__imp_GetCommandLineW
0x180006da7  mov     rdx, rax
0x180006daa  mov     ecx, ebx
0x180006dac  call    TraceRpcException
0x180006db1  mov     rdi, [rsp+68h+arg_0]
0x180006db6  test    byte ptr cs:xmmword_18000F160, 10h
0x180006dbd  jz      short loc_180006E2D
0x180006dbf  call    cs:__imp_GetCommandLineW
0x180006dc5  mov     edx, 4Ah ; 'J'
0x180006dca  mov     [rsp+68h+var_40], rax
0x180006dcf  mov     [rsp+68h+var_48], rdi
0x180006dd4  mov     r9d, ebx
0x180006dd7  call    WPP_SF_DSS
0x180006ddc  jmp     short loc_180006E0C
0x180006dde  mov     ebx, 57h ; 'W'
0x180006de3  jmp     short loc_180006E0C
0x180006de5  mov     r9d, 32h ; '2'
0x180006deb  mov     ebx, r9d
0x180006dee  test    byte ptr cs:xmmword_18000F160, 2
0x180006df5  jz      short loc_180006E0C
0x180006df7  lea     edx, [r9+16h]
0x180006dfb  mov     ecx, 401h
0x180006e00  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006e07  call    WPP_SF_D
0x180006e0c  test    byte ptr cs:xmmword_18000F160, 10h
0x180006e13  jz      short loc_180006E2D
0x180006e15  mov     edx, 4Bh ; 'K'
0x180006e1a  mov     dword ptr [rsp+68h+var_48], ebx
0x180006e1e  mov     r9, rdi
0x180006e21  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006e28  call    WPP_SF_SD
0x180006e2d  mov     eax, ebx
0x180006e2f  mov     rbx, [rsp+68h+arg_8]
0x180006e34  add     rsp, 50h
0x180006e38  pop     r14
0x180006e3a  pop     rdi
0x180006e3b  pop     rsi
0x180006e3c  retn
0x180007a72  push    rbp
0x180007a74  sub     rsp, 40h
0x180007a78  mov     rbp, rdx
0x180007a7b  mov     rcx, [rcx]
0x180007a7e  mov     ecx, [rcx]; ExceptionCode
0x180007a80  call    cs:__imp_I_RpcExceptionFilter
0x180007a86  nop
0x180007a87  add     rsp, 40h
0x180007a8b  pop     rbp
0x180007a8c  retn
```
