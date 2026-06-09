# DhcpEnableDhcpInternal

- ea: `0x180006b78`
- end: `0x180006c88`
- name: `DhcpEnableDhcpInternal`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006790`

## callees

- `0x180006b78`
- `0x18000f4ec`
- `0x180011010`
- `0x180011f08`
- `0x1800127f0`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006bfa`
- `RPCRT4!NdrClientCall3` at `0x180006bfa`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006bb9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006c16`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006c35`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006bb9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006c16`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006c35`

## pseudocode

```c
__int64 __fastcall DhcpEnableDhcpInternal(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  char v5; // al
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v8; // rax
  __int64 v10; // [rsp+20h] [rbp-28h]

  v3 = a2;
  v5 = xmmword_18001E1E0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_ql(a1, a2, a3, a1, a2);
    v5 = xmmword_18001E1E0;
  }
  if ( !a1 )
  {
    Pointer = 87;
    goto LABEL_9;
  }
  if ( (v5 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 43, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, 0, a1, v3).Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v8 = GetCommandLineW();
    WPP_SF_DS(1028, 44, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v8);
    v5 = xmmword_18001E1E0;
LABEL_9:
    if ( (v5 & 0x10) != 0 )
    {
      LODWORD(v10) = Pointer;
      WPP_SF_qD(a1, 45, WPP_e15037783097355a5233924022d92169_Traceguids, a1, v10);
    }
  }
  return Pointer;
}

```

## disassembly

```asm
0x180006b78  mov     [rsp+arg_8], rbx
0x180006b7d  mov     [rsp+arg_0], rcx
0x180006b82  push    rdi
0x180006b83  sub     rsp, 40h
0x180006b87  mov     ebx, edx
0x180006b89  mov     rdi, rcx
0x180006b8c  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006b92  test    al, 10h
0x180006b94  jz      short loc_180006BA8
0x180006b96  mov     dword ptr [rsp+48h+var_28], edx
0x180006b9a  mov     r9, rcx
0x180006b9d  call    WPP_SF_ql
0x180006ba2  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006ba8  test    rdi, rdi
0x180006bab  jnz     short loc_180006BB5
0x180006bad  lea     ebx, [rdi+57h]
0x180006bb0  jmp     loc_180006C5F
0x180006bb5  test    al, 10h
0x180006bb7  jz      short loc_180006BD9
0x180006bb9  call    cs:__imp_GetCommandLineW
0x180006bbf  mov     r9, rax
0x180006bc2  mov     edx, 2Bh ; '+'
0x180006bc7  mov     ecx, 404h
0x180006bcc  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006bd3  call    WPP_SF_S
0x180006bd8  nop
0x180006bd9  mov     [rsp+48h+arg_10], 0
0x180006be2  mov     [rsp+48h+var_20], ebx
0x180006be6  mov     [rsp+48h+var_28], rdi
0x180006beb  xor     r9d, r9d
0x180006bee  xor     r8d, r8d; pReturnValue
0x180006bf1  xor     edx, edx; nProcNum
0x180006bf3  lea     rcx, pProxyInfo; pProxyInfo
0x180006bfa  call    cs:__imp_NdrClientCall3
0x180006c00  mov     rbx, rax
0x180006c03  mov     [rsp+48h+arg_10], rax
0x180006c08  mov     [rsp+48h+var_18], eax
0x180006c0c  jmp     short loc_180006C2B
0x180006c0e  mov     edi, eax
0x180006c10  mov     ebx, eax
0x180006c12  mov     [rsp+48h+var_18], eax
0x180006c16  call    cs:__imp_GetCommandLineW
0x180006c1c  mov     rdx, rax
0x180006c1f  mov     ecx, ebx
0x180006c21  call    TraceRpcException
0x180006c26  mov     rdi, [rsp+48h+arg_0]
0x180006c2b  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006c31  test    al, 10h
0x180006c33  jz      short loc_180006C7B
0x180006c35  call    cs:__imp_GetCommandLineW
0x180006c3b  mov     edx, 2Ch ; ','
0x180006c40  mov     ecx, 404h
0x180006c45  mov     [rsp+48h+var_28], rax
0x180006c4a  mov     r9d, ebx
0x180006c4d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006c54  call    WPP_SF_DS
0x180006c59  mov     al, byte ptr cs:xmmword_18001E1E0
0x180006c5f  test    al, 10h
0x180006c61  jz      short loc_180006C7B
0x180006c63  mov     edx, 2Dh ; '-'
0x180006c68  mov     dword ptr [rsp+48h+var_28], ebx
0x180006c6c  mov     r9, rdi
0x180006c6f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006c76  call    WPP_SF_qD
0x180006c7b  mov     eax, ebx
0x180006c7d  mov     rbx, [rsp+48h+arg_8]
0x180006c82  add     rsp, 40h
0x180006c86  pop     rdi
0x180006c87  retn
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
