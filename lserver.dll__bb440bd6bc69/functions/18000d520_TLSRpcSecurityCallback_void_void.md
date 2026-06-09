# TLSRpcSecurityCallback(void *,void *)

- ea: `0x18000d520`
- end: `0x18000d850`
- name: `?TLSRpcSecurityCallback@@YAJPEAX0@Z`
- size: `816`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180005665`
- `0x18000d520`
- `0x18001ae3c`
- `0x18001aea4`
- `0x18001b0b4`
- `0x18001b128`
- `0x1800a0fb0`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000d56f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000d56f`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000d699`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000d699`
- `RPCRT4!RpcStringBindingParseW` at `0x18000d6ef`
- `RPCRT4!RpcStringBindingParseW` at `0x18000d6ef`
- `RPCRT4!RpcStringFreeW` at `0x18000d802`
- `RPCRT4!RpcStringFreeW` at `0x18000d819`
- `RPCRT4!RpcStringFreeW` at `0x18000d802`
- `RPCRT4!RpcStringFreeW` at `0x18000d819`
- `KERNEL32!CompareStringOrdinal` at `0x18000d749`
- `KERNEL32!CompareStringOrdinal` at `0x18000d776`
- `KERNEL32!CompareStringOrdinal` at `0x18000d79f`
- `KERNEL32!CompareStringOrdinal` at `0x18000d749`
- `KERNEL32!CompareStringOrdinal` at `0x18000d776`
- `KERNEL32!CompareStringOrdinal` at `0x18000d79f`

## string_xrefs

- `0x18000d5ab`: `TLSRpcSecurityCallback`
- `0x18000d63a`: `TLSRpcSecurityCallback`
- `0x18000d7d8`: `TLSRpcSecurityCallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TLSRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  int v3; // ebx
  RPC_STATUS v4; // eax
  int v5; // r9d
  _QWORD *v6; // r10
  int v7; // edx
  int v8; // r8d
  _QWORD *v9; // rax
  int v10; // edx
  RPC_WSTR Protseq; // [rsp+30h] [rbp-39h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-31h] BYREF
  int RpcCallAttributes; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v15[36]; // [rsp+44h] [rbp-25h] BYREF
  int v16; // [rsp+68h] [rbp-1h]
  int v17; // [rsp+70h] [rbp+7h]
  int v18; // [rsp+78h] [rbp+Fh]

  v3 = 0;
  memset_0(v15, 0, 0x6Cu);
  StringBinding = 0;
  Protseq = 0;
  RpcCallAttributes = 2;
  v4 = RpcServerInqCallAttributesW(Context, &RpcCallAttributes);
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v7 = 43;
LABEL_5:
      WPP_SF_SD(
        v6[2],
        v7,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"TLSRpcSecurityCallback",
        v4);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v8 = v16;
  if ( v16 != 6 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
      goto LABEL_34;
    v10 = 44;
    goto LABEL_10;
  }
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        L"TLSRpcSecurityCallback");
    goto LABEL_34;
  }
  v8 = v18;
  if ( (unsigned int)(v18 - 1) > 2 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
      goto LABEL_34;
    v10 = 46;
LABEL_10:
    WPP_SF_SL(v9[2], v10, v8, v5, v8);
    goto LABEL_34;
  }
  v4 = RpcBindingToStringBindingW(Context, &StringBinding);
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v7 = 47;
      goto LABEL_5;
    }
  }
  else
  {
    v4 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v7 = 48;
        goto LABEL_5;
      }
    }
    else if ( CompareStringOrdinal(Protseq, -1, L"ncalrpc", -1, 1) == 2
           || CompareStringOrdinal(Protseq, -1, L"ncacn_np", -1, 1) == 2
           || CompareStringOrdinal(Protseq, -1, L"ncacn_ip_tcp", -1, 1) == 2 )
    {
      v3 = 1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"TLSRpcSecurityCallback",
        (__int64)Protseq);
    }
  }
LABEL_34:
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v3 == 0 ? 5 : 0;
}

```

## disassembly

```asm
0x18000d520  mov     [rsp-8+arg_0], rbx
0x18000d525  mov     [rsp-8+arg_10], rdi
0x18000d52a  push    rbp
0x18000d52b  lea     rbp, [rsp-57h]
0x18000d530  sub     rsp, 0C0h
0x18000d537  mov     rax, cs:__security_cookie
0x18000d53e  xor     rax, rsp
0x18000d541  mov     [rbp+57h+var_10], rax
0x18000d545  mov     rdi, rdx
0x18000d548  lea     rcx, [rbp+57h+var_7C]; void *
0x18000d54c  xor     ebx, ebx
0x18000d54e  xor     edx, edx; Val
0x18000d550  lea     r8d, [rbx+6Ch]; Size
0x18000d554  call    memset_0
0x18000d559  and     [rbp+57h+StringBinding], rbx
0x18000d55d  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18000d561  and     [rbp+57h+Protseq], rbx
0x18000d565  mov     rcx, rdi; ClientBinding
0x18000d568  mov     [rbp+57h+RpcCallAttributes], 2
0x18000d56f  call    cs:__imp_RpcServerInqCallAttributesW
0x18000d576  nop     dword ptr [rax+rax+00h]
0x18000d57b  test    eax, eax
0x18000d57d  jz      short loc_18000D5C7
0x18000d57f  mov     r10, cs:WPP_GLOBAL_Control
0x18000d586  lea     rcx, WPP_GLOBAL_Control
0x18000d58d  cmp     r10, rcx
0x18000d590  jz      loc_18000D7F7
0x18000d596  test    dword ptr [r10+1Ch], 1000h
0x18000d59e  jz      loc_18000D7F7
0x18000d5a4  lea     edx, [rbx+2Bh]
0x18000d5a7  mov     rcx, [r10+10h]
0x18000d5ab  lea     r9, aTlsrpcsecurity; "TLSRpcSecurityCallback"
0x18000d5b2  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000d5b9  mov     [rsp+0C0h+bIgnoreCase], eax
0x18000d5bd  call    WPP_SF_SD
0x18000d5c2  jmp     loc_18000D7F7
0x18000d5c7  mov     r8d, [rbp+57h+var_58]
0x18000d5cb  cmp     r8d, 6
0x18000d5cf  jz      short loc_18000D60D
0x18000d5d1  mov     rax, cs:WPP_GLOBAL_Control
0x18000d5d8  lea     rcx, WPP_GLOBAL_Control
0x18000d5df  cmp     rax, rcx
0x18000d5e2  jz      loc_18000D7F7
0x18000d5e8  test    dword ptr [rax+1Ch], 1000h
0x18000d5ef  jz      loc_18000D7F7
0x18000d5f5  mov     edx, 2Ch ; ','
0x18000d5fa  mov     rcx, [rax+10h]
0x18000d5fe  mov     [rsp+0C0h+bIgnoreCase], r8d
0x18000d603  call    WPP_SF_SL
0x18000d608  jmp     loc_18000D7F7
0x18000d60d  cmp     [rbp+57h+var_50], ebx
0x18000d610  jz      short loc_18000D657
0x18000d612  mov     rax, cs:WPP_GLOBAL_Control
0x18000d619  lea     rcx, WPP_GLOBAL_Control
0x18000d620  cmp     rax, rcx
0x18000d623  jz      loc_18000D7F7
0x18000d629  test    dword ptr [rax+1Ch], 1000h
0x18000d630  jz      loc_18000D7F7
0x18000d636  mov     rcx, [rax+10h]
0x18000d63a  lea     r9, aTlsrpcsecurity; "TLSRpcSecurityCallback"
0x18000d641  mov     edx, 2Dh ; '-'
0x18000d646  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000d64d  call    WPP_SF_S
0x18000d652  jmp     loc_18000D7F7
0x18000d657  mov     r8d, [rbp+57h+var_48]
0x18000d65b  lea     eax, [r8-1]
0x18000d65f  cmp     eax, 2
0x18000d662  jbe     short loc_18000D692
0x18000d664  mov     rax, cs:WPP_GLOBAL_Control
0x18000d66b  lea     rcx, WPP_GLOBAL_Control
0x18000d672  cmp     rax, rcx
0x18000d675  jz      loc_18000D7F7
0x18000d67b  test    dword ptr [rax+1Ch], 1000h
0x18000d682  jz      loc_18000D7F7
0x18000d688  mov     edx, 2Eh ; '.'
0x18000d68d  jmp     loc_18000D5FA
0x18000d692  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18000d696  mov     rcx, rdi; Binding
0x18000d699  call    cs:__imp_RpcBindingToStringBindingW
0x18000d6a0  nop     dword ptr [rax+rax+00h]
0x18000d6a5  test    eax, eax
0x18000d6a7  jz      short loc_18000D6D8
0x18000d6a9  mov     r10, cs:WPP_GLOBAL_Control
0x18000d6b0  lea     rcx, WPP_GLOBAL_Control
0x18000d6b7  cmp     r10, rcx
0x18000d6ba  jz      loc_18000D7F7
0x18000d6c0  test    dword ptr [r10+1Ch], 1000h
0x18000d6c8  jz      loc_18000D7F7
0x18000d6ce  mov     edx, 2Fh ; '/'
0x18000d6d3  jmp     loc_18000D5A7
0x18000d6d8  and     [rsp+0C0h+var_98], rbx
0x18000d6dd  lea     r8, [rbp+57h+Protseq]; Protseq
0x18000d6e1  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18000d6e5  xor     r9d, r9d; NetworkAddr
0x18000d6e8  and     qword ptr [rsp+0C0h+bIgnoreCase], rbx
0x18000d6ed  xor     edx, edx; ObjUuid
0x18000d6ef  call    cs:__imp_RpcStringBindingParseW
0x18000d6f6  nop     dword ptr [rax+rax+00h]
0x18000d6fb  test    eax, eax
0x18000d6fd  jz      short loc_18000D72E
0x18000d6ff  mov     r10, cs:WPP_GLOBAL_Control
0x18000d706  lea     rcx, WPP_GLOBAL_Control
0x18000d70d  cmp     r10, rcx
0x18000d710  jz      loc_18000D7F7
0x18000d716  test    dword ptr [r10+1Ch], 1000h
0x18000d71e  jz      loc_18000D7F7
0x18000d724  mov     edx, 30h ; '0'
0x18000d729  jmp     loc_18000D5A7
0x18000d72e  mov     rcx, [rbp+57h+Protseq]; lpString1
0x18000d732  lea     r8, Protseq; "ncalrpc"
0x18000d739  or      edi, 0FFFFFFFFh
0x18000d73c  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18000d744  mov     r9d, edi; cchCount2
0x18000d747  mov     edx, edi; cchCount1
0x18000d749  call    cs:__imp_CompareStringOrdinal
0x18000d750  nop     dword ptr [rax+rax+00h]
0x18000d755  cmp     eax, 2
0x18000d758  jz      loc_18000D7F2
0x18000d75e  mov     rcx, [rbp+57h+Protseq]; lpString1
0x18000d762  lea     r8, aNcacnNp; "ncacn_np"
0x18000d769  mov     r9d, edi; cchCount2
0x18000d76c  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18000d774  mov     edx, edi; cchCount1
0x18000d776  call    cs:__imp_CompareStringOrdinal
0x18000d77d  nop     dword ptr [rax+rax+00h]
0x18000d782  cmp     eax, 2
0x18000d785  jz      short loc_18000D7F2
0x18000d787  mov     rcx, [rbp+57h+Protseq]; lpString1
0x18000d78b  lea     r8, aNcacnIpTcp; "ncacn_ip_tcp"
0x18000d792  mov     r9d, edi; cchCount2
0x18000d795  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18000d79d  mov     edx, edi; cchCount1
0x18000d79f  call    cs:__imp_CompareStringOrdinal
0x18000d7a6  nop     dword ptr [rax+rax+00h]
0x18000d7ab  cmp     eax, 2
0x18000d7ae  jz      short loc_18000D7F2
0x18000d7b0  mov     r10, cs:WPP_GLOBAL_Control
0x18000d7b7  lea     rcx, WPP_GLOBAL_Control
0x18000d7be  cmp     r10, rcx
0x18000d7c1  jz      short loc_18000D7F7
0x18000d7c3  test    dword ptr [r10+1Ch], 1000h
0x18000d7cb  jz      short loc_18000D7F7
0x18000d7cd  mov     rax, [rbp+57h+Protseq]
0x18000d7d1  lea     edx, [rdi+32h]
0x18000d7d4  mov     rcx, [r10+10h]
0x18000d7d8  lea     r9, aTlsrpcsecurity; "TLSRpcSecurityCallback"
0x18000d7df  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000d7e6  mov     qword ptr [rsp+0C0h+bIgnoreCase], rax
0x18000d7eb  call    WPP_SF_SS
0x18000d7f0  jmp     short loc_18000D7F7
0x18000d7f2  mov     ebx, 1
0x18000d7f7  cmp     [rbp+57h+Protseq], 0
0x18000d7fc  jz      short loc_18000D80E
0x18000d7fe  lea     rcx, [rbp+57h+Protseq]; String
0x18000d802  call    cs:__imp_RpcStringFreeW
0x18000d809  nop     dword ptr [rax+rax+00h]
0x18000d80e  cmp     [rbp+57h+StringBinding], 0
0x18000d813  jz      short loc_18000D825
0x18000d815  lea     rcx, [rbp+57h+StringBinding]; String
0x18000d819  call    cs:__imp_RpcStringFreeW
0x18000d820  nop     dword ptr [rax+rax+00h]
0x18000d825  neg     ebx
0x18000d827  sbb     eax, eax
0x18000d829  not     eax
0x18000d82b  and     eax, 5
0x18000d82e  mov     rcx, [rbp+57h+var_10]
0x18000d832  xor     rcx, rsp; StackCookie
0x18000d835  call    __security_check_cookie
0x18000d83a  lea     r11, [rsp+0C0h+var_s0]
0x18000d842  mov     rbx, [r11+10h]
0x18000d846  mov     rdi, [r11+20h]
0x18000d84a  mov     rsp, r11
0x18000d84d  pop     rbp
0x18000d84e  retn
```
