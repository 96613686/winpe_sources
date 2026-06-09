# DhcpRetrieveOptionsViaInform

- ea: `0x18000b180`
- end: `0x18000b351`
- name: `DhcpRetrieveOptionsViaInform`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180004290`
- `0x18000b180`
- `0x18000f4ec`
- `0x180011260`
- `0x1800127f0`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b291`
- `RPCRT4!NdrClientCall3` at `0x18000b291`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b1bb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b242`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b2ad`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b2d8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b1bb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b242`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b2ad`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b2d8`

## pseudocode

```c
__int64 __fastcall DhcpRetrieveOptionsViaInform(__int64 a1, __int64 a2, _QWORD *a3, int a4, __int64 a5)
{
  LPWSTR CommandLineW; // rax
  CLIENT_CALL_RETURN v9; // rbx
  __int64 v10; // rcx
  LPWSTR v11; // rax
  int v12; // ecx
  LPWSTR v13; // rax
  int v14; // ecx
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+58h] [rbp-20h]

  v16 = 0;
  v17 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 245, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  if ( !a3 || (*a3 = 0, !a1 || a4 || a5) )
  {
    LODWORD(v9.Pointer) = 87;
  }
  else
  {
    LODWORD(v9.Pointer) = DhcpAdapterNameToIfId(a1, &v17);
    if ( !LODWORD(v9.Pointer) )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        WPP_SF_J(v10, 246, WPP_e15037783097355a5233924022d92169_Traceguids, v17);
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v11 = GetCommandLineW();
          WPP_SF_SS(v12, 247, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)v11);
        }
      }
      v18.Simple = 0;
      v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x23u, 0).Pointer;
      v18.Pointer = v9.Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v13 = GetCommandLineW();
        WPP_SF_DSS(
          v14,
          248,
          (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
          v9.Pointer,
          a1,
          (__int64)v13);
      }
      if ( !LODWORD(v9.Pointer) )
      {
        *a3 = v16;
        v16 = 0;
      }
    }
  }
  DhcpFreeMem(&v16);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 249, WPP_e15037783097355a5233924022d92169_Traceguids, LODWORD(v9.Pointer));
  return LODWORD(v9.Pointer);
}

```

## disassembly

```asm
0x18000b180  mov     rax, rsp
0x18000b183  mov     [rax+10h], rbx
0x18000b187  mov     [rax+20h], rsi
0x18000b18b  mov     [rax+18h], r8
0x18000b18f  mov     [rax+8], rcx
0x18000b193  push    rdi
0x18000b194  push    r12
0x18000b196  push    r15
0x18000b198  sub     rsp, 60h
0x18000b19c  mov     ebx, r9d
0x18000b19f  mov     rsi, r8
0x18000b1a2  mov     r12, rdx
0x18000b1a5  mov     r15, rcx
0x18000b1a8  xor     edi, edi
0x18000b1aa  mov     [rax-30h], rdi
0x18000b1ae  mov     [rax-28h], rdi
0x18000b1b2  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b1b9  jz      short loc_18000B1DA
0x18000b1bb  call    cs:__imp_GetCommandLineW
0x18000b1c1  mov     r9, rax
0x18000b1c4  mov     edx, 0F5h
0x18000b1c9  mov     ecx, 404h
0x18000b1ce  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b1d5  call    WPP_SF_S
0x18000b1da  test    rsi, rsi
0x18000b1dd  jz      short loc_18000B1E4
0x18000b1df  mov     [rsi], rdi
0x18000b1e2  jmp     short loc_18000B1EE
0x18000b1e4  mov     ebx, 57h ; 'W'
0x18000b1e9  jmp     loc_18000B30D
0x18000b1ee  test    r15, r15
0x18000b1f1  jz      short loc_18000B1E4
0x18000b1f3  test    ebx, ebx
0x18000b1f5  jnz     short loc_18000B1E4
0x18000b1f7  cmp     [rsp+78h+arg_20], rdi
0x18000b1ff  jnz     short loc_18000B1E4
0x18000b201  lea     rdx, [rsp+78h+var_28]
0x18000b206  mov     rcx, r15
0x18000b209  call    DhcpAdapterNameToIfId
0x18000b20e  mov     ebx, eax
0x18000b210  test    eax, eax
0x18000b212  jnz     loc_18000B30D
0x18000b218  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000b21e  test    al, 10h
0x18000b220  jz      short loc_18000B262
0x18000b222  mov     edx, 0F6h
0x18000b227  mov     r9, [rsp+78h+var_28]
0x18000b22c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b233  call    WPP_SF_J
0x18000b238  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000b23e  test    al, 10h
0x18000b240  jz      short loc_18000B262
0x18000b242  call    cs:__imp_GetCommandLineW
0x18000b248  mov     edx, 0F7h
0x18000b24d  mov     [rsp+78h+var_58], rax
0x18000b252  mov     r9, r15
0x18000b255  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b25c  call    WPP_SF_SS
0x18000b261  nop
0x18000b262  mov     [rsp+78h+var_20], rdi
0x18000b267  lea     rax, [rsp+78h+var_30]
0x18000b26c  mov     [rsp+78h+var_48], rax
0x18000b271  mov     [rsp+78h+var_50], r12
0x18000b276  lea     rax, [rsp+78h+var_28]
0x18000b27b  mov     [rsp+78h+var_58], rax
0x18000b280  xor     r9d, r9d
0x18000b283  xor     r8d, r8d; pReturnValue
0x18000b286  lea     edx, [r9+23h]; nProcNum
0x18000b28a  lea     rcx, pProxyInfo; pProxyInfo
0x18000b291  call    cs:__imp_NdrClientCall3
0x18000b297  mov     rbx, rax
0x18000b29a  mov     [rsp+78h+var_20], rax
0x18000b29f  mov     [rsp+78h+var_38], eax
0x18000b2a3  jmp     short loc_18000B2CF
0x18000b2a5  mov     edi, eax
0x18000b2a7  mov     ebx, eax
0x18000b2a9  mov     [rsp+78h+var_38], eax
0x18000b2ad  call    cs:__imp_GetCommandLineW
0x18000b2b3  mov     rdx, rax
0x18000b2b6  mov     ecx, ebx
0x18000b2b8  call    TraceRpcException
0x18000b2bd  xor     edi, edi
0x18000b2bf  mov     rsi, [rsp+78h+arg_10]
0x18000b2c7  mov     r15, [rsp+78h+arg_0]
0x18000b2cf  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b2d6  jz      short loc_18000B2FC
0x18000b2d8  call    cs:__imp_GetCommandLineW
0x18000b2de  mov     edx, 0F8h
0x18000b2e3  mov     [rsp+78h+var_50], rax
0x18000b2e8  mov     [rsp+78h+var_58], r15
0x18000b2ed  mov     r9d, ebx
0x18000b2f0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b2f7  call    WPP_SF_DSS
0x18000b2fc  test    ebx, ebx
0x18000b2fe  jnz     short loc_18000B30D
0x18000b300  mov     rax, [rsp+78h+var_30]
0x18000b305  mov     [rsi], rax
0x18000b308  mov     [rsp+78h+var_30], rdi
0x18000b30d  lea     rcx, [rsp+78h+var_30]
0x18000b312  call    DhcpFreeMem
0x18000b317  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b31e  jz      short loc_18000B339
0x18000b320  mov     edx, 0F9h
0x18000b325  mov     ecx, 404h
0x18000b32a  mov     r9d, ebx
0x18000b32d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b334  call    WPP_SF_d
0x18000b339  mov     eax, ebx
0x18000b33b  lea     r11, [rsp+78h+var_18]
0x18000b340  mov     rbx, [r11+28h]
0x18000b344  mov     rsi, [r11+38h]
0x18000b348  mov     rsp, r11
0x18000b34b  pop     r15
0x18000b34d  pop     r12
0x18000b34f  pop     rdi
0x18000b350  retn
0x180010d30  push    rbp
0x180010d32  sub     rsp, 40h
0x180010d36  mov     rbp, rdx
0x180010d39  mov     rcx, [rcx]
0x180010d3c  mov     ecx, [rcx]; ExceptionCode
0x180010d3e  call    cs:__imp_I_RpcExceptionFilter
0x180010d44  nop
0x180010d45  add     rsp, 40h
0x180010d49  pop     rbp
0x180010d4a  retn
```
