# _CreateBindingHandle

- ea: `0x180011864`
- end: `0x180011ab0`
- name: `_CreateBindingHandle`
- size: `588`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr, RPC_IF_HANDLE IfSpec, unsigned int AuthnLevel, RPC_BINDING_HANDLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013280`

## callees

- `0x1800049ac`
- `0x180011864`
- `0x18001353c`
- `0x1800135b0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180011915`
- `RPCRT4!RpcBindingFree` at `0x180011a1d`
- `RPCRT4!RpcBindingFree` at `0x180011a82`
- `RPCRT4!RpcBindingFree` at `0x180011915`
- `RPCRT4!RpcBindingFree` at `0x180011a1d`
- `RPCRT4!RpcBindingFree` at `0x180011a82`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800118c0`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800118c0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011966`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180011966`
- `RPCRT4!RpcStringFreeW` at `0x18001199c`
- `RPCRT4!RpcStringFreeW` at `0x18001199c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800119cb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800119cb`
- `RPCRT4!RpcEpResolveBinding` at `0x180011a30`
- `RPCRT4!RpcEpResolveBinding` at `0x180011a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateBindingHandle(
        RPC_WSTR NetworkAddr,
        RPC_IF_HANDLE IfSpec,
        unsigned int AuthnLevel,
        RPC_BINDING_HANDLE *a4)
{
  RPC_STATUS v7; // eax
  unsigned int v8; // edi
  RPC_BINDING_HANDLE v9; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  RPC_BINDING_HANDLE v13; // rax
  unsigned int v14; // eax
  RPC_BINDING_HANDLE v15; // rax
  int AuthIdentity; // [rsp+20h] [rbp-30h]
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-8h] BYREF
  RPC_BINDING_HANDLE v19; // [rsp+98h] [rbp+48h] BYREF

  v19 = 0;
  *a4 = 0;
  StringBinding = 0;
  v7 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", NetworkAddr, 0, 0, &StringBinding);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 22), AuthIdentity, v7);
    v9 = v19;
    if ( v19 )
    {
      v19 = 0;
      Binding = v9;
      RpcBindingFree(&Binding);
    }
    return v8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22));
  v11 = RpcBindingFromStringBindingW(StringBinding, &v19);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 20, &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids, v11);
  RpcStringFreeW(&StringBinding);
  v12 = RpcBindingSetAuthInfoExW(v19, 0, AuthnLevel, 9u, 0, 0, 0);
  v8 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 21, &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids, v12);
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      Binding = v13;
      RpcBindingFree(&Binding);
    }
    return v8;
  }
  v14 = RpcEpResolveBinding(v19, IfSpec);
  v8 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 22, &WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids, v14);
    v15 = v19;
    if ( v19 )
    {
      v19 = 0;
      Binding = v15;
      RpcBindingFree(&Binding);
    }
    return v8;
  }
  *a4 = v19;
  return 0;
}

```

## disassembly

```asm
0x180011864  mov     r11, rsp
0x180011867  mov     [r11+8], rbx
0x18001186b  mov     [r11+10h], rsi
0x18001186f  push    rbp
0x180011870  push    rdi
0x180011871  push    r12
0x180011873  push    r14
0x180011875  push    r15
0x180011877  mov     rbp, rsp
0x18001187a  sub     rsp, 50h
0x18001187e  mov     r14, r9
0x180011881  mov     r12d, r8d
0x180011884  mov     r15, rdx
0x180011887  mov     rsi, rcx
0x18001188a  mov     [rbp+arg_18], 0
0x180011892  mov     qword ptr [r9], 0
0x180011899  mov     [rbp+StringBinding], 0
0x1800118a1  lea     rax, [rbp+StringBinding]
0x1800118a5  mov     [r11-50h], rax
0x1800118a9  mov     qword ptr [r11-58h], 0
0x1800118b1  xor     r9d, r9d; Endpoint
0x1800118b4  mov     r8, rcx; NetworkAddr
0x1800118b7  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x1800118be  xor     ecx, ecx; ObjUuid
0x1800118c0  call    cs:__imp_RpcStringBindingComposeW
0x1800118c6  mov     edi, eax
0x1800118c8  test    eax, eax
0x1800118ca  jz      short loc_180011923
0x1800118cc  lea     rbx, WPP_GLOBAL_Control
0x1800118d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118da  cmp     rcx, rbx
0x1800118dd  jz      short loc_1800118FC
0x1800118df  test    byte ptr [rcx+0BCh], 1
0x1800118e6  jz      short loc_1800118FC
0x1800118e8  mov     [rsp+50h+AuthzSvc], eax; char
0x1800118ec  mov     r9, rsi
0x1800118ef  mov     rcx, [rcx+0B0h]; LoggerHandle
0x1800118f6  call    WPP_SF_SSd
0x1800118fb  nop
0x1800118fc  mov     rax, [rbp+arg_18]
0x180011900  test    rax, rax
0x180011903  jz      short loc_18001191C
0x180011905  mov     [rbp+arg_18], 0
0x18001190d  mov     [rbp+Binding], rax
0x180011911  lea     rcx, [rbp+Binding]; Binding
0x180011915  call    cs:__imp_RpcBindingFree
0x18001191b  nop
0x18001191c  mov     eax, edi
0x18001191e  jmp     loc_180011A97
0x180011923  lea     rbx, WPP_GLOBAL_Control
0x18001192a  lea     rsi, WPP_3c769b25e22837d0f39e918be0b143ee_Traceguids
0x180011931  mov     rcx, cs:WPP_GLOBAL_Control
0x180011938  cmp     rcx, rbx
0x18001193b  jz      short loc_18001195E
0x18001193d  test    byte ptr [rcx+0BCh], 4
0x180011944  jz      short loc_18001195E
0x180011946  mov     edx, 13h
0x18001194b  mov     r9, [rbp+StringBinding]
0x18001194f  mov     r8, rsi
0x180011952  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180011959  call    WPP_SF_S
0x18001195e  lea     rdx, [rbp+arg_18]; Binding
0x180011962  mov     rcx, [rbp+StringBinding]; StringBinding
0x180011966  call    cs:__imp_RpcBindingFromStringBindingW
0x18001196c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011973  cmp     rcx, rbx
0x180011976  jz      short loc_180011998
0x180011978  test    byte ptr [rcx+0BCh], 4
0x18001197f  jz      short loc_180011998
0x180011981  mov     edx, 14h
0x180011986  mov     r9d, eax
0x180011989  mov     r8, rsi
0x18001198c  mov     rcx, [rcx+0B0h]
0x180011993  call    WPP_SF_d
0x180011998  lea     rcx, [rbp+StringBinding]; String
0x18001199c  call    cs:__imp_RpcStringFreeW
0x1800119a2  mov     [rsp+50h+SecurityQOS], 0; SecurityQOS
0x1800119ab  mov     [rsp+50h+AuthzSvc], 0; AuthzSvc
0x1800119b3  mov     [rsp+50h+AuthIdentity], 0; AuthIdentity
0x1800119bc  mov     r9d, 9; AuthnSvc
0x1800119c2  mov     r8d, r12d; AuthnLevel
0x1800119c5  xor     edx, edx; ServerPrincName
0x1800119c7  mov     rcx, [rbp+arg_18]; Binding
0x1800119cb  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800119d1  mov     edi, eax
0x1800119d3  test    eax, eax
0x1800119d5  jz      short loc_180011A29
0x1800119d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119de  cmp     rcx, rbx
0x1800119e1  jz      short loc_180011A04
0x1800119e3  test    byte ptr [rcx+0BCh], 1
0x1800119ea  jz      short loc_180011A04
0x1800119ec  mov     edx, 15h
0x1800119f1  mov     r9d, eax
0x1800119f4  mov     r8, rsi
0x1800119f7  mov     rcx, [rcx+0B0h]
0x1800119fe  call    WPP_SF_d
0x180011a03  nop
0x180011a04  mov     rax, [rbp+arg_18]
0x180011a08  test    rax, rax
0x180011a0b  jz      short loc_180011A24
0x180011a0d  mov     [rbp+arg_18], 0
0x180011a15  mov     [rbp+Binding], rax
0x180011a19  lea     rcx, [rbp+Binding]; Binding
0x180011a1d  call    cs:__imp_RpcBindingFree
0x180011a23  nop
0x180011a24  jmp     loc_18001191C
0x180011a29  mov     rdx, r15; IfSpec
0x180011a2c  mov     rcx, [rbp+arg_18]; Binding
0x180011a30  call    cs:__imp_RpcEpResolveBinding
0x180011a36  mov     edi, eax
0x180011a38  test    eax, eax
0x180011a3a  jz      short loc_180011A8E
0x180011a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a43  cmp     rcx, rbx
0x180011a46  jz      short loc_180011A69
0x180011a48  test    byte ptr [rcx+0BCh], 1
0x180011a4f  jz      short loc_180011A69
0x180011a51  mov     edx, 16h
0x180011a56  mov     r9d, eax
0x180011a59  mov     r8, rsi
0x180011a5c  mov     rcx, [rcx+0B0h]
0x180011a63  call    WPP_SF_d
0x180011a68  nop
0x180011a69  mov     rax, [rbp+arg_18]
0x180011a6d  test    rax, rax
0x180011a70  jz      short loc_180011A89
0x180011a72  mov     [rbp+arg_18], 0
0x180011a7a  mov     [rbp+Binding], rax
0x180011a7e  lea     rcx, [rbp+Binding]; Binding
0x180011a82  call    cs:__imp_RpcBindingFree
0x180011a88  nop
0x180011a89  jmp     loc_18001191C
0x180011a8e  mov     rax, [rbp+arg_18]
0x180011a92  mov     [r14], rax
0x180011a95  xor     eax, eax
0x180011a97  lea     r11, [rsp+50h+var_s0]
0x180011a9c  mov     rbx, [r11+30h]
0x180011aa0  mov     rsi, [r11+38h]
0x180011aa4  mov     rsp, r11
0x180011aa7  pop     r15
0x180011aa9  pop     r14
0x180011aab  pop     r12
0x180011aad  pop     rdi
0x180011aae  pop     rbp
0x180011aaf  retn
```
