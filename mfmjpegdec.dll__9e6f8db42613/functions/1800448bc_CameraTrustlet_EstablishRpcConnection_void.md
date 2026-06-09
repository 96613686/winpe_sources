# CameraTrustlet::EstablishRpcConnection(void)

- ea: `0x1800448bc`
- end: `0x180044b11`
- name: `?EstablishRpcConnection@CameraTrustlet@@AEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ef40`

## callees

- `0x1800448bc`
- `0x180044d78`
- `0x180044db8`
- `0x180044e0c`
- `0x180045060`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180044a06`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180044a06`
- `RPCRT4!RpcStringFreeW` at `0x180044b02`
- `RPCRT4!RpcStringFreeW` at `0x180044b02`
- `RPCRT4!RpcStringBindingComposeW` at `0x180044921`
- `RPCRT4!RpcStringBindingComposeW` at `0x180044a7f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180044921`
- `RPCRT4!RpcStringBindingComposeW` at `0x180044a7f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180044937`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180044a3e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180044937`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180044a3e`
- `RPCRT4!NdrClientCall3` at `0x180044972`
- `RPCRT4!NdrClientCall3` at `0x180044972`

## pseudocode

```c
__int64 __fastcall CameraTrustlet::EstablishRpcConnection(RPC_BINDING_HANDLE *Binding)
{
  CLIENT_CALL_RETURN v2; // rax
  CLIENT_CALL_RETURN v3; // r8
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  RPC_WSTR String; // [rsp+70h] [rbp+18h] BYREF
  RPC_BINDING_HANDLE *v9; // [rsp+78h] [rbp+20h]

  if ( (unsigned __int8)byte_18009D825 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, Binding);
  String = 0;
  if ( RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)Binding + 16, 0, &String) )
  {
    v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)Binding + 16, 0, &String) | 0x80010000;
    if ( g_wppLevels )
    {
      v5 = 31;
      goto LABEL_14;
    }
LABEL_15:
    if ( !byte_18009D825 )
      goto LABEL_20;
    v6 = 36;
    goto LABEL_19;
  }
  if ( RpcBindingFromStringBindingW(String, Binding) )
  {
    v4 = RpcBindingFromStringBindingW(String, Binding) | 0x80010000;
    if ( g_wppLevels )
    {
      v5 = 32;
LABEL_14:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, Binding, v4);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  v9 = Binding;
  v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&IFsIsoRpc_ProxyInfo, 4u, 0, *Binding).Pointer;
  Binding[1] = (RPC_BINDING_HANDLE)v2.Simple;
  if ( !v2.Simple )
  {
    v4 = -2147483634;
    if ( g_wppLevels )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids,
        Binding,
        -2147483634);
    goto LABEL_15;
  }
  v4 = 0;
  if ( (unsigned __int8)byte_18009D825 >= 8u )
  {
    v6 = 37;
LABEL_19:
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qD)(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v6,
      (CLIENT_CALL_RETURN)v3.Simple,
      Binding,
      v4);
  }
LABEL_20:
  if ( String )
    RpcStringFreeW(&String);
  return v4;
}

```

## disassembly

```asm
0x1800448bc  mov     [rsp+arg_0], rcx
0x1800448c1  push    rbx
0x1800448c2  push    rdi
0x1800448c3  sub     rsp, 48h
0x1800448c7  mov     rdi, rcx
0x1800448ca  cmp     cs:byte_18009D825, 8
0x1800448d1  jb      short loc_1800448F5
0x1800448d3  mov     edx, 1Eh
0x1800448d8  mov     r9, rcx
0x1800448db  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1800448e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448e9  mov     rcx, [rcx+0D8h]
0x1800448f0  call    WPP_SF_q
0x1800448f5  mov     [rsp+58h+String], 0
0x1800448fe  lea     rax, [rsp+58h+String]
0x180044903  mov     [rsp+58h+StringBinding], rax; StringBinding
0x180044908  mov     [rsp+58h+Options], 0; Options
0x180044911  lea     r9, [rdi+20h]; Endpoint
0x180044915  xor     r8d, r8d; NetworkAddr
0x180044918  lea     rdx, ProtSeq; "ncalrpc"
0x18004491f  xor     ecx, ecx; ObjUuid
0x180044921  call    cs:__imp_RpcStringBindingComposeW
0x180044927  test    eax, eax
0x180044929  jnz     loc_180044A5C
0x18004492f  mov     rdx, rdi; Binding
0x180044932  mov     rcx, [rsp+58h+String]; StringBinding
0x180044937  call    cs:__imp_RpcBindingFromStringBindingW
0x18004493d  test    eax, eax
0x18004493f  jnz     loc_180044A36
0x180044945  mov     r9, rdi
0x180044948  mov     [rsp+58h+arg_18], rdi
0x18004494d  mov     [rsp+58h+arg_8], eax
0x180044951  xor     ebx, ebx
0x180044953  cmp     [rsp+58h+arg_8], 0FAh
0x18004495b  jnb     loc_180044A1A
0x180044961  mov     r9, [r9]
0x180044964  xor     r8d, r8d; pReturnValue
0x180044967  lea     edx, [r8+4]; nProcNum
0x18004496b  lea     rcx, ?IFsIsoRpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180044972  call    cs:__imp_NdrClientCall3
0x180044978  mov     [rdi+8], rax
0x18004497c  test    rax, rax
0x18004497f  jnz     short loc_1800449B9
0x180044981  mov     ebx, 8000000Eh
0x180044986  mov     [rsp+58h+var_28], ebx
0x18004498a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044991  jb      short loc_1800449B4
0x180044993  lea     edx, [rax+21h]
0x180044996  mov     dword ptr [rsp+58h+Options], ebx
0x18004499a  mov     r9, rdi
0x18004499d  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1800449a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449ab  mov     rcx, [rcx+10h]
0x1800449af  call    WPP_SF_qd
0x1800449b4  jmp     loc_180044AB9
0x1800449b9  xor     ebx, ebx
0x1800449bb  mov     [rsp+58h+var_28], ebx
0x1800449bf  jmp     short loc_180044A1A
0x1800449c1  mov     ebx, eax
0x1800449c3  test    eax, eax
0x1800449c5  jz      short loc_1800449CD
0x1800449c7  or      ebx, 80010000h
0x1800449cd  mov     [rsp+58h+var_28], ebx
0x1800449d1  mov     rdi, [rsp+58h+arg_0]
0x1800449d6  cmp     cs:byte_18009D825, 8
0x1800449dd  jb      short loc_180044A01
0x1800449df  mov     eax, [rsp+58h+arg_8]
0x1800449e3  mov     dword ptr [rsp+58h+StringBinding], eax
0x1800449e7  mov     dword ptr [rsp+58h+Options], ebx
0x1800449eb  mov     r9, rdi
0x1800449ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449f5  mov     rcx, [rcx+0D8h]
0x1800449fc  call    WPP_SF_qDD
0x180044a01  mov     ecx, 14h; dwMilliseconds
0x180044a06  call    cs:__imp_Sleep
0x180044a0c  inc     [rsp+58h+arg_8]
0x180044a10  mov     r9, [rsp+58h+arg_18]
0x180044a15  jmp     loc_180044953
0x180044a1a  test    ebx, ebx
0x180044a1c  jns     loc_180044ACD
0x180044a22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044a29  jb      loc_180044AB9
0x180044a2f  mov     edx, 23h ; '#'
0x180044a34  jmp     short loc_180044A9B
0x180044a36  mov     rdx, rdi; Binding
0x180044a39  mov     rcx, [rsp+58h+String]; StringBinding
0x180044a3e  call    cs:__imp_RpcBindingFromStringBindingW
0x180044a44  mov     ebx, eax
0x180044a46  or      ebx, 80010000h
0x180044a4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044a53  jb      short loc_180044AB9
0x180044a55  mov     edx, 20h ; ' '
0x180044a5a  jmp     short loc_180044A9B
0x180044a5c  lea     rax, [rsp+58h+String]
0x180044a61  mov     [rsp+58h+StringBinding], rax; StringBinding
0x180044a66  mov     [rsp+58h+Options], 0; Options
0x180044a6f  lea     r9, [rdi+20h]; Endpoint
0x180044a73  xor     r8d, r8d; NetworkAddr
0x180044a76  lea     rdx, ProtSeq; "ncalrpc"
0x180044a7d  xor     ecx, ecx; ObjUuid
0x180044a7f  call    cs:__imp_RpcStringBindingComposeW
0x180044a85  mov     ebx, eax
0x180044a87  or      ebx, 80010000h
0x180044a8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044a94  jb      short loc_180044AB9
0x180044a96  mov     edx, 1Fh
0x180044a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044aa2  mov     dword ptr [rsp+58h+Options], ebx
0x180044aa6  mov     r9, rdi
0x180044aa9  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x180044ab0  mov     rcx, [rcx+10h]
0x180044ab4  call    WPP_SF_qd
0x180044ab9  test    ebx, ebx
0x180044abb  jns     short loc_180044ACD
0x180044abd  cmp     cs:byte_18009D825, 1
0x180044ac4  jb      short loc_180044AF5
0x180044ac6  mov     edx, 24h ; '$'
0x180044acb  jmp     short loc_180044ADB
0x180044acd  cmp     cs:byte_18009D825, 8
0x180044ad4  jb      short loc_180044AF5
0x180044ad6  mov     edx, 25h ; '%'
0x180044adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ae2  mov     dword ptr [rsp+58h+Options], ebx
0x180044ae6  mov     r9, rdi
0x180044ae9  mov     rcx, [rcx+0D8h]
0x180044af0  call    WPP_SF_qD
0x180044af5  cmp     [rsp+58h+String], 0
0x180044afb  jz      short loc_180044B08
0x180044afd  lea     rcx, [rsp+58h+String]; String
0x180044b02  call    cs:__imp_RpcStringFreeW
0x180044b08  mov     eax, ebx
0x180044b0a  add     rsp, 48h
0x180044b0e  pop     rdi
0x180044b0f  pop     rbx
0x180044b10  retn
```
