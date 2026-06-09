# DhcpDeRegisterConnectionStateNotification

- ea: `0x180006180`
- end: `0x18000629b`
- name: `DhcpDeRegisterConnectionStateNotification`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006180`
- `0x18000f4ec`
- `0x180011374`
- `0x1800113f8`
- `0x1800127f0`
- `0x180012a40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006213`
- `RPCRT4!NdrClientCall3` at `0x180006213`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800061d0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000622f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006252`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800061d0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000622f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006252`

## pseudocode

```c
__int64 __fastcall DhcpDeRegisterConnectionStateNotification(int a1, __int64 a2, int a3)
{
  char v5; // al
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  LPWSTR v8; // rax

  v5 = xmmword_18001E1E0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_LS(a1, 202, a3, a1, a2);
    v5 = xmmword_18001E1E0;
  }
  if ( !a2 || (a1 & 0xF) == 0 )
  {
    Pointer = 87;
    goto LABEL_10;
  }
  if ( (v5 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 203, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Cu, 0).Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v8 = GetCommandLineW();
    WPP_SF_DS(1028, 204, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, (__int64)v8);
    v5 = xmmword_18001E1E0;
LABEL_10:
    if ( (v5 & 0x10) != 0 )
      WPP_SF_LSD(a1, a2, a3, a1, a2, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180006180  mov     [rsp+arg_8], rdx
0x180006185  mov     [rsp+arg_0], ecx
0x180006189  push    rbx
0x18000618a  push    rsi
0x18000618b  push    rdi
0x18000618c  sub     rsp, 40h
0x180006190  mov     rdi, rdx
0x180006193  mov     esi, ecx
0x180006195  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000619b  test    al, 10h
0x18000619d  jz      short loc_1800061B7
0x18000619f  mov     edx, 0CAh
0x1800061a4  mov     [rsp+58h+var_38], rdi
0x1800061a9  mov     r9d, ecx
0x1800061ac  call    WPP_SF_LS
0x1800061b1  mov     al, byte ptr cs:xmmword_18001E1E0
0x1800061b7  test    rdi, rdi
0x1800061ba  jnz     short loc_1800061C6
0x1800061bc  mov     ebx, 57h ; 'W'
0x1800061c1  jmp     loc_18000627C
0x1800061c6  test    sil, 0Fh
0x1800061ca  jz      short loc_1800061BC
0x1800061cc  test    al, 10h
0x1800061ce  jz      short loc_1800061F0
0x1800061d0  call    cs:__imp_GetCommandLineW
0x1800061d6  mov     r9, rax
0x1800061d9  mov     edx, 0CBh
0x1800061de  mov     ecx, 404h
0x1800061e3  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800061ea  call    WPP_SF_S
0x1800061ef  nop
0x1800061f0  mov     [rsp+58h+arg_10], 0
0x1800061f9  mov     [rsp+58h+var_30], rdi
0x1800061fe  mov     dword ptr [rsp+58h+var_38], esi
0x180006202  xor     r9d, r9d
0x180006205  xor     r8d, r8d; pReturnValue
0x180006208  lea     edx, [r9+1Ch]; nProcNum
0x18000620c  lea     rcx, pProxyInfo; pProxyInfo
0x180006213  call    cs:__imp_NdrClientCall3
0x180006219  mov     rbx, rax
0x18000621c  mov     [rsp+58h+arg_10], rax
0x180006221  mov     [rsp+58h+var_28], eax
0x180006225  jmp     short loc_180006248
0x180006227  mov     edi, eax
0x180006229  mov     ebx, eax
0x18000622b  mov     [rsp+58h+var_28], eax
0x18000622f  call    cs:__imp_GetCommandLineW
0x180006235  mov     rdx, rax
0x180006238  mov     ecx, ebx
0x18000623a  call    TraceRpcException
0x18000623f  mov     rdi, [rsp+58h+arg_8]
0x180006244  mov     esi, [rsp+58h+arg_0]
0x180006248  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000624e  test    al, 10h
0x180006250  jz      short loc_180006291
0x180006252  call    cs:__imp_GetCommandLineW
0x180006258  mov     edx, 0CCh
0x18000625d  mov     ecx, 404h
0x180006262  mov     [rsp+58h+var_38], rax
0x180006267  mov     r9d, ebx
0x18000626a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006271  call    WPP_SF_DS
0x180006276  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000627c  test    al, 10h
0x18000627e  jz      short loc_180006291
0x180006280  mov     dword ptr [rsp+58h+var_30], ebx
0x180006284  mov     [rsp+58h+var_38], rdi
0x180006289  mov     r9d, esi
0x18000628c  call    WPP_SF_LSD
0x180006291  mov     eax, ebx
0x180006293  add     rsp, 40h
0x180006297  pop     rdi
0x180006298  pop     rsi
0x180006299  pop     rbx
0x18000629a  retn
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
