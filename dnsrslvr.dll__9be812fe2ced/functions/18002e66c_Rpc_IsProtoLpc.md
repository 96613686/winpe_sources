# Rpc_IsProtoLpc

- ea: `0x18002e66c`
- end: `0x18002e777`
- name: `Rpc_IsProtoLpc`
- size: `267`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002e620`

## callees

- `0x18002e66c`
- `0x180046ec0`
- `0x180086f24`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18002e712`
- `RPCRT4!RpcStringFreeW` at `0x18002e72d`
- `RPCRT4!RpcStringFreeW` at `0x18002e712`
- `RPCRT4!RpcStringFreeW` at `0x18002e72d`
- `RPCRT4!RpcStringBindingParseW` at `0x18002e6cc`
- `RPCRT4!RpcStringBindingParseW` at `0x18002e6cc`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002e6a9`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002e6a9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e700`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e700`

## pseudocode

```c
_BOOL8 __fastcall Rpc_IsProtoLpc(RPC_BINDING_HANDLE Binding)
{
  BOOL v1; // edi
  int v3; // ebx
  int v4; // eax
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-28h] BYREF
  RPC_WSTR Protseq; // [rsp+38h] [rbp-20h] BYREF

  v1 = 0;
  StringBinding = 0;
  Protseq = 0;
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
    WPP_SF_q(1031, 10, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, Binding);
  if ( !RpcBindingToStringBindingW(Binding, &StringBinding)
    && !RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0) )
  {
    if ( Protseq )
    {
      v3 = 1;
      v4 = CompareStringW(0x409u, 1u, Protseq, -1, L"ncalrpc", -1);
      if ( v4 == 2 )
      {
        v3 = 0;
      }
      else if ( v4 == 1 )
      {
        v3 = -1;
      }
    }
    else
    {
      v3 = -1;
    }
    RpcStringFreeW(&Protseq);
    v1 = v3 == 0;
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v1;
}

```

## disassembly

```asm
0x18002e66c  mov     [rsp+arg_8], rbx
0x18002e671  push    rdi
0x18002e672  sub     rsp, 50h
0x18002e676  mov     rax, cs:__security_cookie
0x18002e67d  xor     rax, rsp
0x18002e680  mov     [rsp+58h+var_18], rax
0x18002e685  xor     edi, edi
0x18002e687  mov     rbx, rcx
0x18002e68a  mov     [rsp+58h+StringBinding], rdi
0x18002e68f  mov     [rsp+58h+Protseq], rdi
0x18002e694  cmp     byte ptr cs:xmmword_1800AB5A0, dil
0x18002e69b  jl      loc_18002E759
0x18002e6a1  lea     rdx, [rsp+58h+StringBinding]; StringBinding
0x18002e6a6  mov     rcx, rbx; Binding
0x18002e6a9  call    cs:__imp_RpcBindingToStringBindingW
0x18002e6af  test    eax, eax
0x18002e6b1  jnz     short loc_18002E720
0x18002e6b3  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x18002e6b8  lea     r8, [rsp+58h+Protseq]; Protseq
0x18002e6bd  mov     [rsp+58h+NetworkOptions], rdi; NetworkOptions
0x18002e6c2  xor     r9d, r9d; NetworkAddr
0x18002e6c5  xor     edx, edx; ObjUuid
0x18002e6c7  mov     [rsp+58h+Endpoint], rdi; Endpoint
0x18002e6cc  call    cs:__imp_RpcStringBindingParseW
0x18002e6d2  test    eax, eax
0x18002e6d4  jnz     short loc_18002E720
0x18002e6d6  mov     r8, [rsp+58h+Protseq]; lpString1
0x18002e6db  test    r8, r8
0x18002e6de  jz      short loc_18002E754
0x18002e6e0  or      edi, 0FFFFFFFFh
0x18002e6e3  lea     rax, Protseq; "ncalrpc"
0x18002e6ea  mov     dword ptr [rsp+58h+NetworkOptions], edi; cchCount2
0x18002e6ee  mov     r9d, edi; cchCount1
0x18002e6f1  mov     ecx, 409h; Locale
0x18002e6f6  mov     [rsp+58h+Endpoint], rax; lpString2
0x18002e6fb  lea     ebx, [rdi+2]
0x18002e6fe  mov     edx, ebx; dwCmpFlags
0x18002e700  call    cs:__imp_CompareStringW
0x18002e706  cmp     eax, 2
0x18002e709  jnz     short loc_18002E74D
0x18002e70b  xor     ebx, ebx
0x18002e70d  lea     rcx, [rsp+58h+Protseq]; String
0x18002e712  call    cs:__imp_RpcStringFreeW
0x18002e718  xor     edi, edi
0x18002e71a  test    ebx, ebx
0x18002e71c  setz    dil
0x18002e720  cmp     [rsp+58h+StringBinding], 0
0x18002e726  jz      short loc_18002E733
0x18002e728  lea     rcx, [rsp+58h+StringBinding]; String
0x18002e72d  call    cs:__imp_RpcStringFreeW
0x18002e733  mov     eax, edi
0x18002e735  mov     rcx, [rsp+58h+var_18]
0x18002e73a  xor     rcx, rsp; StackCookie
0x18002e73d  call    __security_check_cookie
0x18002e742  mov     rbx, [rsp+58h+arg_8]
0x18002e747  add     rsp, 50h
0x18002e74b  pop     rdi
0x18002e74c  retn
0x18002e74d  cmp     eax, ebx
0x18002e74f  cmovz   ebx, edi
0x18002e752  jmp     short loc_18002E70D
0x18002e754  or      ebx, 0FFFFFFFFh
0x18002e757  jmp     short loc_18002E70D
0x18002e759  mov     edx, 0Ah
0x18002e75e  lea     r8, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids
0x18002e765  mov     ecx, 407h
0x18002e76a  mov     r9, rbx
0x18002e76d  call    WPP_SF_q
0x18002e772  jmp     loc_18002E6A1
```
