# DhcpSetFallbackParams

- ea: `0x18000b7c0`
- end: `0x18000b9c8`
- name: `DhcpSetFallbackParams`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x18000b7c0`
- `0x18000f4ec`
- `0x180011498`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b90a`
- `RPCRT4!NdrClientCall3` at `0x18000b90a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010d1c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010d1c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b8bb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b929`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b94a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b8bb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b929`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b94a`

## pseudocode

```c
__int64 __fastcall DhcpSetFallbackParams(__int64 a1, _DWORD *a2)
{
  unsigned int Pointer; // ebx
  int v5; // r8d
  int v6; // edx
  LPWSTR CommandLineW; // rax
  int v8; // ecx
  CLIENT_CALL_RETURN v9; // rax
  LPWSTR v10; // rax
  int v11; // ecx
  __int64 v13; // [rsp+A0h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v14; // [rsp+A8h] [rbp+20h]

  v13 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 174, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 175, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_20;
  }
  if ( !a1 || !a2 )
  {
    Pointer = 87;
    goto LABEL_20;
  }
  Pointer = DhcpAdapterNameToIfId(a1, &v13);
  if ( !Pointer )
  {
    if ( *a2 && (v6 = a2[1]) != 0 )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        WPP_SF_SDDDDDDD(*a2, v6, v5, a1, *a2, v6, a2[2], a2[3], a2[4], a2[5], a2[6]);
        goto LABEL_14;
      }
    }
    else if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      WPP_SF_S(1028, 176, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
LABEL_14:
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_SS(v8, 178, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
      }
    }
    v14.Simple = 0;
    v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 7u, 0).Pointer;
    Pointer = (unsigned int)v9.Pointer;
    v14.Pointer = v9.Pointer;
    if ( (xmmword_18001E1E0 & 0x10) == 0 )
      return Pointer;
    v10 = GetCommandLineW();
    WPP_SF_DSS(v11, 179, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v10);
  }
LABEL_20:
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 180, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000b7c0  mov     rax, rsp
0x18000b7c3  mov     [rax+8], rcx
0x18000b7c7  push    rbx
0x18000b7c8  push    rdi
0x18000b7c9  push    r14
0x18000b7cb  sub     rsp, 70h
0x18000b7cf  mov     r14, rdx
0x18000b7d2  mov     rdi, rcx
0x18000b7d5  mov     qword ptr [rax+18h], 0
0x18000b7dd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b7e4  jz      short loc_18000B7FF
0x18000b7e6  mov     edx, 0AEh
0x18000b7eb  mov     ecx, 404h
0x18000b7f0  mov     r9, rdi
0x18000b7f3  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b7fa  call    WPP_SF_S
0x18000b7ff  call    DhcpIsFSEGuestSystem
0x18000b804  test    eax, eax
0x18000b806  jnz     loc_18000B970
0x18000b80c  test    rdi, rdi
0x18000b80f  jnz     short loc_18000B81B
0x18000b811  mov     ebx, 57h ; 'W'
0x18000b816  jmp     loc_18000B997
0x18000b81b  test    r14, r14
0x18000b81e  jz      short loc_18000B811
0x18000b820  lea     rdx, [rsp+88h+arg_10]
0x18000b828  mov     rcx, rdi
0x18000b82b  call    DhcpAdapterNameToIfId
0x18000b830  mov     ebx, eax
0x18000b832  test    eax, eax
0x18000b834  jnz     loc_18000B997
0x18000b83a  mov     ecx, [r14]
0x18000b83d  test    ecx, ecx
0x18000b83f  jz      short loc_18000B890
0x18000b841  mov     edx, [r14+4]
0x18000b845  test    edx, edx
0x18000b847  jz      short loc_18000B890
0x18000b849  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b850  jz      loc_18000B8DB
0x18000b856  mov     eax, [r14+18h]
0x18000b85a  mov     [rsp+88h+var_38], eax
0x18000b85e  mov     eax, [r14+14h]
0x18000b862  mov     [rsp+88h+var_40], eax
0x18000b866  mov     eax, [r14+10h]
0x18000b86a  mov     [rsp+88h+var_48], eax
0x18000b86e  mov     eax, [r14+0Ch]
0x18000b872  mov     [rsp+88h+var_50], eax
0x18000b876  mov     eax, [r14+8]
0x18000b87a  mov     [rsp+88h+var_58], eax
0x18000b87e  mov     dword ptr [rsp+88h+var_60], edx
0x18000b882  mov     dword ptr [rsp+88h+var_68], ecx
0x18000b886  mov     r9, rdi
0x18000b889  call    WPP_SF_SDDDDDDD
0x18000b88e  jmp     short loc_18000B8B2
0x18000b890  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b897  jz      short loc_18000B8DB
0x18000b899  mov     edx, 0B0h
0x18000b89e  mov     ecx, 404h
0x18000b8a3  mov     r9, rdi
0x18000b8a6  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b8ad  call    WPP_SF_S
0x18000b8b2  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b8b9  jz      short loc_18000B8DB
0x18000b8bb  call    cs:__imp_GetCommandLineW
0x18000b8c1  mov     edx, 0B2h
0x18000b8c6  mov     [rsp+88h+var_68], rax
0x18000b8cb  mov     r9, rdi
0x18000b8ce  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b8d5  call    WPP_SF_SS
0x18000b8da  nop
0x18000b8db  mov     [rsp+88h+arg_18], 0
0x18000b8e7  mov     [rsp+88h+var_60], r14
0x18000b8ec  lea     rax, [rsp+88h+arg_10]
0x18000b8f4  mov     [rsp+88h+var_68], rax
0x18000b8f9  xor     r9d, r9d
0x18000b8fc  xor     r8d, r8d; pReturnValue
0x18000b8ff  lea     edx, [r9+7]; nProcNum
0x18000b903  lea     rcx, pProxyInfo; pProxyInfo
0x18000b90a  call    cs:__imp_NdrClientCall3
0x18000b910  mov     rbx, rax
0x18000b913  mov     [rsp+88h+arg_18], rax
0x18000b91b  mov     [rsp+88h+var_28], eax
0x18000b91f  jmp     short loc_18000B941
0x18000b921  mov     edi, eax
0x18000b923  mov     ebx, eax
0x18000b925  mov     [rsp+88h+var_28], eax
0x18000b929  call    cs:__imp_GetCommandLineW
0x18000b92f  mov     rdx, rax
0x18000b932  mov     ecx, ebx
0x18000b934  call    TraceRpcException
0x18000b939  mov     rdi, [rsp+88h+arg_0]
0x18000b941  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b948  jz      short loc_18000B9BD
0x18000b94a  call    cs:__imp_GetCommandLineW
0x18000b950  mov     edx, 0B3h
0x18000b955  mov     [rsp+88h+var_60], rax
0x18000b95a  mov     [rsp+88h+var_68], rdi
0x18000b95f  mov     r9d, ebx
0x18000b962  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b969  call    WPP_SF_DSS
0x18000b96e  jmp     short loc_18000B997
0x18000b970  mov     r9d, 32h ; '2'
0x18000b976  mov     ebx, r9d
0x18000b979  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000b980  jz      short loc_18000B997
0x18000b982  lea     edx, [r9+7Dh]
0x18000b986  mov     ecx, 401h
0x18000b98b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b992  call    WPP_SF_d
0x18000b997  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b99e  jz      short loc_18000B9BD
0x18000b9a0  mov     edx, 0B4h
0x18000b9a5  mov     ecx, 404h
0x18000b9aa  mov     dword ptr [rsp+88h+var_68], ebx
0x18000b9ae  mov     r9, rdi
0x18000b9b1  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b9b8  call    WPP_SF_SD
0x18000b9bd  mov     eax, ebx
0x18000b9bf  add     rsp, 70h
0x18000b9c3  pop     r14
0x18000b9c5  pop     rdi
0x18000b9c6  pop     rbx
0x18000b9c7  retn
0x180010d0e  push    rbp
0x180010d10  sub     rsp, 60h
0x180010d14  mov     rbp, rdx
0x180010d17  mov     rcx, [rcx]
0x180010d1a  mov     ecx, [rcx]; ExceptionCode
0x180010d1c  call    cs:__imp_I_RpcExceptionFilter
0x180010d22  nop
0x180010d23  add     rsp, 60h
0x180010d27  pop     rbp
0x180010d28  retn
```
