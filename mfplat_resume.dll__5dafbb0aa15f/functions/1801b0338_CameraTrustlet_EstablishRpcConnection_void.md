# CameraTrustlet::EstablishRpcConnection(void)

- ea: `0x1801b0338`
- end: `0x1801b05a0`
- name: `?EstablishRpcConnection@CameraTrustlet@@AEAAJXZ`
- size: `616`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1801b022c`

## callees

- `0x1800214fc`
- `0x1800afc5c`
- `0x1801250c8`
- `0x1801b0338`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801b048e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801b048e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1801b03b3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1801b04c6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1801b03b3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1801b04c6`
- `RPCRT4!RpcStringFreeW` at `0x1801b0591`
- `RPCRT4!RpcStringFreeW` at `0x1801b0591`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801b039d`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801b0507`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801b039d`
- `RPCRT4!RpcStringBindingComposeW` at `0x1801b0507`
- `RPCRT4!NdrClientCall3` at `0x1801b03ee`
- `RPCRT4!NdrClientCall3` at `0x1801b03ee`

## pseudocode

```c
__int64 __fastcall CameraTrustlet::EstablishRpcConnection(RPC_BINDING_HANDLE *Binding)
{
  CLIENT_CALL_RETURN v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  RPC_WSTR String; // [rsp+70h] [rbp+18h] BYREF
  RPC_BINDING_HANDLE *v8; // [rsp+78h] [rbp+20h]

  if ( (unsigned __int8)byte_1801FD28D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, Binding);
  String = 0;
  if ( RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)Binding + 16, 0, &String) )
  {
    v3 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)Binding + 16, 0, &String) | 0x80010000;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v4 = 31;
      goto LABEL_14;
    }
LABEL_15:
    if ( !byte_1801FD28D )
      goto LABEL_20;
    v5 = 36;
    goto LABEL_19;
  }
  if ( RpcBindingFromStringBindingW(String, Binding) )
  {
    v3 = RpcBindingFromStringBindingW(String, Binding) | 0x80010000;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v4 = 32;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, Binding, v3);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  v8 = Binding;
  v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&IFsIsoRpc_ProxyInfo, 4u, 0, *Binding).Pointer;
  Binding[1] = (RPC_BINDING_HANDLE)v2.Simple;
  if ( !v2.Simple )
  {
    v3 = -2147483634;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids,
        Binding,
        -2147483634);
    goto LABEL_15;
  }
  v3 = 0;
  if ( (unsigned __int8)byte_1801FD28D >= 8u )
  {
    v5 = 37;
LABEL_19:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v5, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, Binding, v3);
  }
LABEL_20:
  if ( String )
    RpcStringFreeW(&String);
  return v3;
}

```

## disassembly

```asm
0x1801b0338  mov     [rsp+arg_0], rcx
0x1801b033d  push    rbx
0x1801b033e  push    rdi
0x1801b033f  sub     rsp, 48h
0x1801b0343  mov     rdi, rcx
0x1801b0346  cmp     cs:byte_1801FD28D, 8
0x1801b034d  jb      short loc_1801B0371
0x1801b034f  mov     edx, 1Eh
0x1801b0354  mov     r9, rcx
0x1801b0357  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1801b035e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b0365  mov     rcx, [rcx+0D8h]
0x1801b036c  call    WPP_SF_q
0x1801b0371  mov     [rsp+58h+String], 0
0x1801b037a  lea     rax, [rsp+58h+String]
0x1801b037f  mov     [rsp+58h+StringBinding], rax; StringBinding
0x1801b0384  mov     [rsp+58h+Options], 0; Options
0x1801b038d  lea     r9, [rdi+20h]; Endpoint
0x1801b0391  xor     r8d, r8d; NetworkAddr
0x1801b0394  lea     rdx, ProtSeq; "ncalrpc"
0x1801b039b  xor     ecx, ecx; ObjUuid
0x1801b039d  call    cs:__imp_RpcStringBindingComposeW
0x1801b03a3  test    eax, eax
0x1801b03a5  jnz     loc_1801B04E4
0x1801b03ab  mov     rdx, rdi; Binding
0x1801b03ae  mov     rcx, [rsp+58h+String]; StringBinding
0x1801b03b3  call    cs:__imp_RpcBindingFromStringBindingW
0x1801b03b9  test    eax, eax
0x1801b03bb  jnz     loc_1801B04BE
0x1801b03c1  mov     r9, rdi
0x1801b03c4  mov     [rsp+58h+arg_18], rdi
0x1801b03c9  mov     [rsp+58h+arg_8], eax
0x1801b03cd  xor     ebx, ebx
0x1801b03cf  cmp     [rsp+58h+arg_8], 0FAh
0x1801b03d7  jnb     loc_1801B04A2
0x1801b03dd  mov     r9, [r9]
0x1801b03e0  xor     r8d, r8d; pReturnValue
0x1801b03e3  lea     edx, [r8+4]; nProcNum
0x1801b03e7  lea     rcx, ?IFsIsoRpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1801b03ee  call    cs:__imp_NdrClientCall3
0x1801b03f4  mov     [rdi+8], rax
0x1801b03f8  test    rax, rax
0x1801b03fb  jnz     short loc_1801B0435
0x1801b03fd  mov     ebx, 8000000Eh
0x1801b0402  mov     [rsp+58h+var_28], ebx
0x1801b0406  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b040d  jb      short loc_1801B0430
0x1801b040f  lea     edx, [rax+21h]
0x1801b0412  mov     dword ptr [rsp+58h+Options], ebx
0x1801b0416  mov     r9, rdi
0x1801b0419  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1801b0420  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b0427  mov     rcx, [rcx+10h]
0x1801b042b  call    WPP_SF_qD
0x1801b0430  jmp     loc_1801B0541
0x1801b0435  xor     ebx, ebx
0x1801b0437  mov     [rsp+58h+var_28], ebx
0x1801b043b  jmp     short loc_1801B04A2
0x1801b043d  mov     ebx, eax
0x1801b043f  test    eax, eax
0x1801b0441  jz      short loc_1801B0449
0x1801b0443  or      ebx, 80010000h
0x1801b0449  mov     [rsp+58h+var_28], ebx
0x1801b044d  mov     rdi, [rsp+58h+arg_0]
0x1801b0452  cmp     cs:byte_1801FD28D, 8
0x1801b0459  jb      short loc_1801B0489
0x1801b045b  mov     edx, 22h ; '"'
0x1801b0460  mov     eax, [rsp+58h+arg_8]
0x1801b0464  mov     dword ptr [rsp+58h+StringBinding], eax
0x1801b0468  mov     dword ptr [rsp+58h+Options], ebx
0x1801b046c  mov     r9, rdi
0x1801b046f  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1801b0476  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b047d  mov     rcx, [rcx+0D8h]
0x1801b0484  call    WPP_SF_qDD
0x1801b0489  mov     ecx, 14h; dwMilliseconds
0x1801b048e  call    cs:__imp_Sleep
0x1801b0494  inc     [rsp+58h+arg_8]
0x1801b0498  mov     r9, [rsp+58h+arg_18]
0x1801b049d  jmp     loc_1801B03CF
0x1801b04a2  test    ebx, ebx
0x1801b04a4  jns     loc_1801B0555
0x1801b04aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b04b1  jb      loc_1801B0541
0x1801b04b7  mov     edx, 23h ; '#'
0x1801b04bc  jmp     short loc_1801B0523
0x1801b04be  mov     rdx, rdi; Binding
0x1801b04c1  mov     rcx, [rsp+58h+String]; StringBinding
0x1801b04c6  call    cs:__imp_RpcBindingFromStringBindingW
0x1801b04cc  mov     ebx, eax
0x1801b04ce  or      ebx, 80010000h
0x1801b04d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b04db  jb      short loc_1801B0541
0x1801b04dd  mov     edx, 20h ; ' '
0x1801b04e2  jmp     short loc_1801B0523
0x1801b04e4  lea     rax, [rsp+58h+String]
0x1801b04e9  mov     [rsp+58h+StringBinding], rax; StringBinding
0x1801b04ee  mov     [rsp+58h+Options], 0; Options
0x1801b04f7  lea     r9, [rdi+20h]; Endpoint
0x1801b04fb  xor     r8d, r8d; NetworkAddr
0x1801b04fe  lea     rdx, ProtSeq; "ncalrpc"
0x1801b0505  xor     ecx, ecx; ObjUuid
0x1801b0507  call    cs:__imp_RpcStringBindingComposeW
0x1801b050d  mov     ebx, eax
0x1801b050f  or      ebx, 80010000h
0x1801b0515  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b051c  jb      short loc_1801B0541
0x1801b051e  mov     edx, 1Fh
0x1801b0523  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b052a  mov     dword ptr [rsp+58h+Options], ebx
0x1801b052e  mov     r9, rdi
0x1801b0531  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1801b0538  mov     rcx, [rcx+10h]
0x1801b053c  call    WPP_SF_qD
0x1801b0541  test    ebx, ebx
0x1801b0543  jns     short loc_1801B0555
0x1801b0545  cmp     cs:byte_1801FD28D, 1
0x1801b054c  jb      short loc_1801B0584
0x1801b054e  mov     edx, 24h ; '$'
0x1801b0553  jmp     short loc_1801B0563
0x1801b0555  cmp     cs:byte_1801FD28D, 8
0x1801b055c  jb      short loc_1801B0584
0x1801b055e  mov     edx, 25h ; '%'
0x1801b0563  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b056a  mov     dword ptr [rsp+58h+Options], ebx
0x1801b056e  mov     r9, rdi
0x1801b0571  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1801b0578  mov     rcx, [rcx+0D8h]
0x1801b057f  call    WPP_SF_qD
0x1801b0584  cmp     [rsp+58h+String], 0
0x1801b058a  jz      short loc_1801B0597
0x1801b058c  lea     rcx, [rsp+58h+String]; String
0x1801b0591  call    cs:__imp_RpcStringFreeW
0x1801b0597  mov     eax, ebx
0x1801b0599  add     rsp, 48h
0x1801b059d  pop     rdi
0x1801b059e  pop     rbx
0x1801b059f  retn
```
