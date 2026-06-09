# DhcpSetClientId

- ea: `0x18000b590`
- end: `0x18000b7b4`
- name: `DhcpSetClientId`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x18000b590`
- `0x18000f4ec`
- `0x180011614`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b6f7`
- `RPCRT4!NdrClientCall3` at `0x18000b6f7`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b6a8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b716`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b737`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b6a8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b716`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b737`

## pseudocode

```c
__int64 __fastcall DhcpSetClientId(__int64 a1, __int64 a2)
{
  int v4; // r8d
  unsigned int Pointer; // ebx
  unsigned int v6; // ecx
  unsigned __int64 v7; // rax
  LPWSTR CommandLineW; // rax
  int v9; // ecx
  CLIENT_CALL_RETURN v10; // rax
  LPWSTR v11; // rax
  int v12; // ecx
  _OWORD v14[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v16; // [rsp+98h] [rbp+20h]

  v15 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 163, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 164, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_26;
  }
  if ( !a1 )
    goto LABEL_5;
  if ( !a2 )
    goto LABEL_17;
  if ( !*(_DWORD *)(a2 + 4) || !*(_QWORD *)(a2 + 8) )
    a2 = 0;
  if ( a2 )
  {
    v6 = *(_DWORD *)(a2 + 4);
    if ( v6 > 0xFE )
    {
LABEL_5:
      Pointer = 87;
      goto LABEL_26;
    }
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v7 = *(_QWORD *)(a2 + 8);
      v14[0] = v7;
      if ( v7 )
        WORD4(v14[0]) = v6;
      else
        WORD4(v14[0]) = 0;
      WPP_SF_SdD_HEX_(v6, (unsigned int)v14, v4, a1, v6, *(_BYTE *)a2, (__int64)v14);
    }
  }
  else
  {
LABEL_17:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_S(1028, 166, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  }
  Pointer = DhcpAdapterNameToIfId(a1, &v15);
  if ( Pointer )
  {
LABEL_26:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 169, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
    return Pointer;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(v9, 167, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
  }
  v16.Simple = 0;
  v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x15u, 0).Pointer;
  Pointer = (unsigned int)v10.Pointer;
  v16.Pointer = v10.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v11 = GetCommandLineW();
    WPP_SF_DSS(v12, 168, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v11);
    goto LABEL_26;
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000b590  mov     rax, rsp
0x18000b593  mov     [rax+8], rcx
0x18000b597  push    rbx
0x18000b598  push    rsi
0x18000b599  push    rdi
0x18000b59a  sub     rsp, 60h
0x18000b59e  mov     rdi, rdx
0x18000b5a1  mov     rsi, rcx
0x18000b5a4  mov     qword ptr [rax+18h], 0
0x18000b5ac  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b5b3  jz      short loc_18000B5CE
0x18000b5b5  mov     edx, 0A3h
0x18000b5ba  mov     ecx, 404h
0x18000b5bf  mov     r9, rsi
0x18000b5c2  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b5c9  call    WPP_SF_S
0x18000b5ce  call    DhcpIsFSEGuestSystem
0x18000b5d3  test    eax, eax
0x18000b5d5  jnz     loc_18000B75D
0x18000b5db  test    rsi, rsi
0x18000b5de  jnz     short loc_18000B5EA
0x18000b5e0  mov     ebx, 57h ; 'W'
0x18000b5e5  jmp     loc_18000B784
0x18000b5ea  test    rdi, rdi
0x18000b5ed  jz      short loc_18000B663
0x18000b5ef  cmp     dword ptr [rdi+4], 0
0x18000b5f3  jz      short loc_18000B5FC
0x18000b5f5  cmp     qword ptr [rdi+8], 0
0x18000b5fa  jnz     short loc_18000B5FE
0x18000b5fc  xor     edi, edi
0x18000b5fe  test    rdi, rdi
0x18000b601  jz      short loc_18000B663
0x18000b603  mov     ecx, [rdi+4]
0x18000b606  cmp     ecx, 0FEh
0x18000b60c  ja      short loc_18000B5E0
0x18000b60e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b615  jz      short loc_18000B685
0x18000b617  mov     rax, [rdi+8]
0x18000b61b  xorps   xmm0, xmm0
0x18000b61e  movups  [rsp+78h+var_28], xmm0
0x18000b623  mov     qword ptr [rsp+78h+var_28], rax
0x18000b628  test    rax, rax
0x18000b62b  jnz     short loc_18000B634
0x18000b62d  mov     word ptr [rsp+78h+var_28+8], ax
0x18000b632  jmp     short loc_18000B639
0x18000b634  mov     word ptr [rsp+78h+var_28+8], cx
0x18000b639  movaps  xmm0, [rsp+78h+var_28]
0x18000b63e  movdqa  [rsp+78h+var_28], xmm0
0x18000b644  movzx   eax, byte ptr [rdi]
0x18000b647  lea     rdx, [rsp+78h+var_28]
0x18000b64c  mov     [rsp+78h+var_48], rdx
0x18000b651  mov     dword ptr [rsp+78h+var_50], eax
0x18000b655  mov     dword ptr [rsp+78h+var_58], ecx
0x18000b659  mov     r9, rsi
0x18000b65c  call    WPP_SF_SdD_HEX_
0x18000b661  jmp     short loc_18000B685
0x18000b663  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b66a  jz      short loc_18000B685
0x18000b66c  mov     edx, 0A6h
0x18000b671  mov     ecx, 404h
0x18000b676  mov     r9, rsi
0x18000b679  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b680  call    WPP_SF_S
0x18000b685  lea     rdx, [rsp+78h+arg_10]
0x18000b68d  mov     rcx, rsi
0x18000b690  call    DhcpAdapterNameToIfId
0x18000b695  mov     ebx, eax
0x18000b697  test    eax, eax
0x18000b699  jnz     loc_18000B784
0x18000b69f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b6a6  jz      short loc_18000B6C8
0x18000b6a8  call    cs:__imp_GetCommandLineW
0x18000b6ae  mov     edx, 0A7h
0x18000b6b3  mov     [rsp+78h+var_58], rax
0x18000b6b8  mov     r9, rsi
0x18000b6bb  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b6c2  call    WPP_SF_SS
0x18000b6c7  nop
0x18000b6c8  mov     [rsp+78h+arg_18], 0
0x18000b6d4  mov     [rsp+78h+var_50], rdi
0x18000b6d9  lea     rax, [rsp+78h+arg_10]
0x18000b6e1  mov     [rsp+78h+var_58], rax
0x18000b6e6  xor     r9d, r9d
0x18000b6e9  xor     r8d, r8d; pReturnValue
0x18000b6ec  lea     edx, [r9+15h]; nProcNum
0x18000b6f0  lea     rcx, pProxyInfo; pProxyInfo
0x18000b6f7  call    cs:__imp_NdrClientCall3
0x18000b6fd  mov     rbx, rax
0x18000b700  mov     [rsp+78h+arg_18], rax
0x18000b708  mov     [rsp+78h+var_38], eax
0x18000b70c  jmp     short loc_18000B72E
0x18000b70e  mov     edi, eax
0x18000b710  mov     ebx, eax
0x18000b712  mov     [rsp+78h+var_38], eax
0x18000b716  call    cs:__imp_GetCommandLineW
0x18000b71c  mov     rdx, rax
0x18000b71f  mov     ecx, ebx
0x18000b721  call    TraceRpcException
0x18000b726  mov     rsi, [rsp+78h+arg_0]
0x18000b72e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b735  jz      short loc_18000B7AA
0x18000b737  call    cs:__imp_GetCommandLineW
0x18000b73d  mov     edx, 0A8h
0x18000b742  mov     [rsp+78h+var_50], rax
0x18000b747  mov     [rsp+78h+var_58], rsi
0x18000b74c  mov     r9d, ebx
0x18000b74f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b756  call    WPP_SF_DSS
0x18000b75b  jmp     short loc_18000B784
0x18000b75d  mov     r9d, 32h ; '2'
0x18000b763  mov     ebx, r9d
0x18000b766  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000b76d  jz      short loc_18000B784
0x18000b76f  lea     edx, [r9+72h]
0x18000b773  mov     ecx, 401h
0x18000b778  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b77f  call    WPP_SF_d
0x18000b784  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b78b  jz      short loc_18000B7AA
0x18000b78d  mov     edx, 0A9h
0x18000b792  mov     ecx, 404h
0x18000b797  mov     dword ptr [rsp+78h+var_58], ebx
0x18000b79b  mov     r9, rsi
0x18000b79e  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b7a5  call    WPP_SF_SD
0x18000b7aa  mov     eax, ebx
0x18000b7ac  add     rsp, 60h
0x18000b7b0  pop     rdi
0x18000b7b1  pop     rsi
0x18000b7b2  pop     rbx
0x18000b7b3  retn
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
