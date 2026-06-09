# DhcpSetClassId

- ea: `0x18000b360`
- end: `0x18000b585`
- name: `DhcpSetClassId`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x18000b360`
- `0x18000f4ec`
- `0x1800116d4`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b4cb`
- `RPCRT4!NdrClientCall3` at `0x18000b4cb`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b385`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b47c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b4ea`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b508`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b385`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b47c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b4ea`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000b508`

## pseudocode

```c
__int64 __fastcall DhcpSetClassId(__int64 a1, __int64 a2)
{
  LPWSTR CommandLineW; // rax
  int v5; // ecx
  int v6; // edx
  int v7; // r8d
  unsigned int Pointer; // ebx
  unsigned int v9; // ecx
  unsigned __int64 v10; // rax
  LPWSTR v11; // rax
  int v12; // ecx
  CLIENT_CALL_RETURN v13; // rax
  LPWSTR v14; // rax
  int v15; // ecx
  __int128 v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v19; // [rsp+88h] [rbp+20h]

  v18 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(v5, 152, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
  }
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 153, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
    goto LABEL_27;
  }
  if ( !a1 )
    goto LABEL_5;
  if ( a2 )
  {
    if ( *(_DWORD *)a2 )
      goto LABEL_5;
    if ( !*(_DWORD *)(a2 + 16) || !*(_QWORD *)(a2 + 8) )
      a2 = 0;
    if ( a2 )
    {
      v9 = *(_DWORD *)(a2 + 16);
      if ( v9 <= 0xFF )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v10 = *(_QWORD *)(a2 + 8);
          v17 = v10;
          if ( v10 )
            WORD4(v17) = v9;
          else
            WORD4(v17) = 0;
          WPP_SF_Sd_HEX_(v9, v6, v7, a1, v9, (__int64)&v17);
        }
        goto LABEL_20;
      }
LABEL_5:
      Pointer = 87;
      goto LABEL_27;
    }
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 155, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
LABEL_20:
  Pointer = DhcpAdapterNameToIfId(a1, &v18);
  if ( Pointer )
    goto LABEL_27;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v11 = GetCommandLineW();
    WPP_SF_SS(v12, 156, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)v11);
  }
  v19.Simple = 0;
  v13.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x13u, 0).Pointer;
  Pointer = (unsigned int)v13.Pointer;
  v19.Pointer = v13.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v14 = GetCommandLineW();
    WPP_SF_DSS(v15, 157, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v14);
LABEL_27:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 158, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000b360  mov     rax, rsp
0x18000b363  mov     [rax+8], rcx
0x18000b367  push    rbx
0x18000b368  push    rsi
0x18000b369  push    rdi
0x18000b36a  sub     rsp, 50h
0x18000b36e  mov     rdi, rdx
0x18000b371  mov     rsi, rcx
0x18000b374  mov     qword ptr [rax+18h], 0
0x18000b37c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b383  jz      short loc_18000B3A4
0x18000b385  call    cs:__imp_GetCommandLineW
0x18000b38b  mov     edx, 98h
0x18000b390  mov     [rsp+68h+var_48], rax
0x18000b395  mov     r9, rsi
0x18000b398  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b39f  call    WPP_SF_SS
0x18000b3a4  call    DhcpIsFSEGuestSystem
0x18000b3a9  test    eax, eax
0x18000b3ab  jnz     loc_18000B52E
0x18000b3b1  test    rsi, rsi
0x18000b3b4  jnz     short loc_18000B3C0
0x18000b3b6  mov     ebx, 57h ; 'W'
0x18000b3bb  jmp     loc_18000B555
0x18000b3c0  test    rdi, rdi
0x18000b3c3  jz      short loc_18000B437
0x18000b3c5  cmp     dword ptr [rdi], 0
0x18000b3c8  jnz     short loc_18000B3B6
0x18000b3ca  cmp     dword ptr [rdi+10h], 0
0x18000b3ce  jz      short loc_18000B3D7
0x18000b3d0  cmp     qword ptr [rdi+8], 0
0x18000b3d5  jnz     short loc_18000B3D9
0x18000b3d7  xor     edi, edi
0x18000b3d9  test    rdi, rdi
0x18000b3dc  jz      short loc_18000B437
0x18000b3de  mov     ecx, [rdi+10h]
0x18000b3e1  cmp     ecx, 0FFh
0x18000b3e7  ja      short loc_18000B3B6
0x18000b3e9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b3f0  jz      short loc_18000B459
0x18000b3f2  mov     rax, [rdi+8]
0x18000b3f6  xorps   xmm0, xmm0
0x18000b3f9  movups  [rsp+68h+var_28], xmm0
0x18000b3fe  mov     qword ptr [rsp+68h+var_28], rax
0x18000b403  test    rax, rax
0x18000b406  jnz     short loc_18000B40F
0x18000b408  mov     word ptr [rsp+68h+var_28+8], ax
0x18000b40d  jmp     short loc_18000B414
0x18000b40f  mov     word ptr [rsp+68h+var_28+8], cx
0x18000b414  movaps  xmm0, [rsp+68h+var_28]
0x18000b419  movdqa  [rsp+68h+var_28], xmm0
0x18000b41f  lea     rax, [rsp+68h+var_28]
0x18000b424  mov     [rsp+68h+var_40], rax
0x18000b429  mov     dword ptr [rsp+68h+var_48], ecx
0x18000b42d  mov     r9, rsi
0x18000b430  call    WPP_SF_Sd_HEX_
0x18000b435  jmp     short loc_18000B459
0x18000b437  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b43e  jz      short loc_18000B459
0x18000b440  mov     edx, 9Bh
0x18000b445  mov     ecx, 404h
0x18000b44a  mov     r9, rsi
0x18000b44d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b454  call    WPP_SF_S
0x18000b459  lea     rdx, [rsp+68h+arg_10]
0x18000b461  mov     rcx, rsi
0x18000b464  call    DhcpAdapterNameToIfId
0x18000b469  mov     ebx, eax
0x18000b46b  test    eax, eax
0x18000b46d  jnz     loc_18000B555
0x18000b473  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b47a  jz      short loc_18000B49C
0x18000b47c  call    cs:__imp_GetCommandLineW
0x18000b482  mov     edx, 9Ch
0x18000b487  mov     [rsp+68h+var_48], rax
0x18000b48c  mov     r9, rsi
0x18000b48f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b496  call    WPP_SF_SS
0x18000b49b  nop
0x18000b49c  mov     [rsp+68h+arg_18], 0
0x18000b4a8  mov     [rsp+68h+var_40], rdi
0x18000b4ad  lea     rax, [rsp+68h+arg_10]
0x18000b4b5  mov     [rsp+68h+var_48], rax
0x18000b4ba  xor     r9d, r9d
0x18000b4bd  xor     r8d, r8d; pReturnValue
0x18000b4c0  lea     edx, [r9+13h]; nProcNum
0x18000b4c4  lea     rcx, pProxyInfo; pProxyInfo
0x18000b4cb  call    cs:__imp_NdrClientCall3
0x18000b4d1  mov     rbx, rax
0x18000b4d4  mov     [rsp+68h+arg_18], rax
0x18000b4dc  mov     [rsp+68h+var_38], eax
0x18000b4e0  jmp     short loc_18000B4FF
0x18000b4e2  mov     edi, eax
0x18000b4e4  mov     ebx, eax
0x18000b4e6  mov     [rsp+68h+var_38], eax
0x18000b4ea  call    cs:__imp_GetCommandLineW
0x18000b4f0  mov     rdx, rax
0x18000b4f3  mov     ecx, ebx
0x18000b4f5  call    TraceRpcException
0x18000b4fa  mov     rsi, [rsp+68h+arg_0]
0x18000b4ff  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b506  jz      short loc_18000B57B
0x18000b508  call    cs:__imp_GetCommandLineW
0x18000b50e  mov     edx, 9Dh
0x18000b513  mov     [rsp+68h+var_40], rax
0x18000b518  mov     [rsp+68h+var_48], rsi
0x18000b51d  mov     r9d, ebx
0x18000b520  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b527  call    WPP_SF_DSS
0x18000b52c  jmp     short loc_18000B555
0x18000b52e  mov     r9d, 32h ; '2'
0x18000b534  mov     ebx, r9d
0x18000b537  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000b53e  jz      short loc_18000B555
0x18000b540  lea     edx, [r9+67h]
0x18000b544  mov     ecx, 401h
0x18000b549  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b550  call    WPP_SF_d
0x18000b555  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b55c  jz      short loc_18000B57B
0x18000b55e  mov     edx, 9Eh
0x18000b563  mov     ecx, 404h
0x18000b568  mov     dword ptr [rsp+68h+var_48], ebx
0x18000b56c  mov     r9, rsi
0x18000b56f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b576  call    WPP_SF_SD
0x18000b57b  mov     eax, ebx
0x18000b57d  add     rsp, 50h
0x18000b581  pop     rdi
0x18000b582  pop     rsi
0x18000b583  pop     rbx
0x18000b584  retn
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
