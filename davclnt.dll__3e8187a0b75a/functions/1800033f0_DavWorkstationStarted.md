# DavWorkstationStarted

- ea: `0x1800033f0`
- end: `0x18000352e`
- name: `DavWorkstationStarted`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001310`
- `0x180001600`
- `0x180002970`
- `0x1800036d0`
- `0x180004340`
- `0x180004bd0`
- `0x180006ff0`
- `0x180007ad0`
- `0x18000b4f0`
- `0x18000f2d0`
- `0x18000f7f0`
- `0x18000fd30`

## callees

- `0x1800033f0`
- `0x180003540`
- `0x180010be8`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180003417`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180003417`
- `RPCRT4!NdrClientCall3` at `0x180003460`
- `RPCRT4!NdrClientCall3` at `0x180003460`
- `RPCRT4!I_RpcExceptionFilter` at `0x180011ffe`
- `RPCRT4!I_RpcExceptionFilter` at `0x180011ffe`
- `RPCRT4!RpcBindingFree` at `0x1800034b0`
- `RPCRT4!RpcBindingFree` at `0x1800034b0`

## pseudocode

```c
__int64 __fastcall DavWorkstationStarted(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS v3; // eax
  ULONG v4; // eax
  ULONG v5; // ebx
  _QWORD *v6; // rcx
  CLIENT_CALL_RETURN v7; // rax
  unsigned __int8 Pointer; // bl
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp+8h] BYREF
  void *Simple; // [rsp+48h] [rbp+10h] BYREF

  Binding = 0;
  Simple = 0;
  v3 = RpcpBindRpc(a1, a2, a3, &Simple);
  v4 = RtlNtStatusToDosErrorNoTeb(v3);
  v5 = v4;
  if ( !v4 )
  {
    Binding = Simple;
LABEL_3:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v4);
    goto LABEL_3;
  }
LABEL_4:
  if ( v5 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_d(v6[2], 203, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v5);
    return 0;
  }
  else
  {
    Simple = 0;
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x11u, 0, Binding).Pointer;
    Pointer = (unsigned __int8)v7.Pointer;
    Simple = (void *)v7.Simple;
    RpcBindingFree(&Binding);
    return Pointer;
  }
}

```

## disassembly

```asm
0x1800033f0  mov     [rsp+arg_10], rbx
0x1800033f5  mov     [rsp+arg_18], rsi
0x1800033fa  push    rdi
0x1800033fb  sub     rsp, 30h
0x1800033ff  xor     esi, esi
0x180003401  mov     [rsp+38h+Binding], rsi
0x180003406  mov     [rsp+38h+arg_8], rsi
0x18000340b  lea     r9, [rsp+38h+arg_8]
0x180003410  call    RpcpBindRpc
0x180003415  mov     ecx, eax; Status
0x180003417  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000341d  mov     ebx, eax
0x18000341f  test    eax, eax
0x180003421  jnz     loc_1800034C9
0x180003427  mov     rax, [rsp+38h+arg_8]
0x18000342c  mov     [rsp+38h+Binding], rax
0x180003431  lea     rdi, WPP_GLOBAL_Control
0x180003438  mov     rcx, cs:WPP_GLOBAL_Control
0x18000343f  test    ebx, ebx
0x180003441  jnz     loc_180003507
0x180003447  mov     [rsp+38h+arg_8], rsi
0x18000344c  mov     r9, [rsp+38h+Binding]
0x180003451  xor     r8d, r8d; pReturnValue
0x180003454  mov     edx, 11h; nProcNum
0x180003459  lea     rcx, pProxyInfo; pProxyInfo
0x180003460  call    cs:__imp_NdrClientCall3
0x180003466  mov     rbx, rax
0x180003469  mov     [rsp+38h+arg_8], rax
0x18000346e  mov     [rsp+38h+var_18], al
0x180003472  jmp     short loc_1800034AB
0x180003474  lea     rdx, WPP_GLOBAL_Control
0x18000347b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003482  cmp     rcx, rdx
0x180003485  jz      short loc_1800034A5
0x180003487  test    byte ptr [rcx+1Ch], 1
0x18000348b  jz      short loc_1800034A5
0x18000348d  mov     r9d, eax
0x180003490  mov     edx, 0CCh
0x180003495  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000349c  mov     rcx, [rcx+10h]
0x1800034a0  call    WPP_SF_d
0x1800034a5  xor     bl, bl
0x1800034a7  mov     [rsp+38h+var_18], bl
0x1800034ab  lea     rcx, [rsp+38h+Binding]; Binding
0x1800034b0  call    cs:__imp_RpcBindingFree
0x1800034b6  movzx   eax, bl
0x1800034b9  mov     rbx, [rsp+38h+arg_10]
0x1800034be  mov     rsi, [rsp+38h+arg_18]
0x1800034c3  add     rsp, 30h
0x1800034c7  pop     rdi
0x1800034c8  retn
0x1800034c9  lea     rdi, WPP_GLOBAL_Control
0x1800034d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034d7  cmp     rcx, rdi
0x1800034da  jz      loc_18000343F
0x1800034e0  test    byte ptr [rcx+1Ch], 1
0x1800034e4  jz      loc_18000343F
0x1800034ea  mov     edx, 0CAh
0x1800034ef  mov     r9d, ebx
0x1800034f2  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800034f9  mov     rcx, [rcx+10h]
0x1800034fd  call    WPP_SF_d
0x180003502  jmp     loc_180003438
0x180003507  cmp     rcx, rdi
0x18000350a  jz      short loc_18000352A
0x18000350c  test    byte ptr [rcx+1Ch], 1
0x180003510  jz      short loc_18000352A
0x180003512  mov     edx, 0CBh
0x180003517  mov     r9d, ebx
0x18000351a  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003521  mov     rcx, [rcx+10h]
0x180003525  call    WPP_SF_d
0x18000352a  xor     eax, eax
0x18000352c  jmp     short loc_1800034B9
0x180011ff0  push    rbp
0x180011ff2  sub     rsp, 20h
0x180011ff6  mov     rbp, rdx
0x180011ff9  mov     rcx, [rcx]
0x180011ffc  mov     ecx, [rcx]; ExceptionCode
0x180011ffe  call    cs:__imp_I_RpcExceptionFilter
0x180012004  nop
0x180012005  add     rsp, 20h
0x180012009  pop     rbp
0x18001200a  retn
```
