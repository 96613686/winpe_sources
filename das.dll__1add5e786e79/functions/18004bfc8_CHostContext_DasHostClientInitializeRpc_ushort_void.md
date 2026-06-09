# CHostContext::DasHostClientInitializeRpc(ushort *,void * *)

- ea: `0x18004bfc8`
- end: `0x18004c09d`
- name: `?DasHostClientInitializeRpc@CHostContext@@IEAAJPEAGPEAPEAX@Z`
- size: `213`
- prototype: `RPC_STATUS __fastcall(CHostContext *this, unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022624`

## callees

- `0x18004bfc8`
- `0x18004c38c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c069`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18004c03b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18004c03b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004c023`
- `RPCRT4!RpcStringBindingComposeW` at `0x18004c023`
- `RPCRT4!RpcStringFreeW` at `0x18004c07c`
- `RPCRT4!RpcStringFreeW` at `0x18004c07c`

## pseudocode

```c
RPC_STATUS __fastcall CHostContext::DasHostClientInitializeRpc(CHostContext *this, unsigned __int16 *a2, void **a3)
{
  RPC_STATUS result; // eax
  RPC_STATUS v5; // ebx
  HANDLE ProcessHeap; // rax
  RPC_WSTR Endpoint; // [rsp+40h] [rbp+8h] BYREF
  RPC_WSTR String; // [rsp+58h] [rbp+20h] BYREF

  String = 0;
  Endpoint = 0;
  result = CHostContext::MakeEndpointString(this, a2, a2, &Endpoint);
  if ( result >= 0 )
  {
    v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
    if ( !v5 )
    {
      v5 = RpcBindingFromStringBindingW(String, &DasHostCommandAndControl_v1_0_c_ifspec);
      if ( !v5 )
        *a3 = DasHostCommandAndControl_v1_0_c_ifspec;
    }
    if ( Endpoint )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, Endpoint);
    }
    if ( String )
      RpcStringFreeW(&String);
    if ( v5 >= 1 )
      return (unsigned __int16)v5 | 0x80010000;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18004bfc8  mov     rax, rsp
0x18004bfcb  mov     [rax+10h], rbx
0x18004bfcf  mov     [rax+8], rcx
0x18004bfd3  push    rsi
0x18004bfd4  sub     rsp, 30h
0x18004bfd8  mov     rsi, r8
0x18004bfdb  mov     qword ptr [rax+20h], 0
0x18004bfe3  mov     r8, rdx; unsigned __int16 *
0x18004bfe6  mov     qword ptr [rax+8], 0
0x18004bfee  lea     r9, [rax+8]; unsigned __int16 **
0x18004bff2  call    ?MakeEndpointString@CHostContext@@IEAAJPEAG0PEAPEAG@Z; CHostContext::MakeEndpointString(ushort *,ushort *,ushort * *)
0x18004bff7  test    eax, eax
0x18004bff9  js      loc_18004C092
0x18004bfff  mov     r9, [rsp+38h+Endpoint]; Endpoint
0x18004c004  lea     rax, [rsp+38h+String]
0x18004c009  mov     [rsp+38h+StringBinding], rax; StringBinding
0x18004c00e  lea     rdx, ProtSeq; "ncalrpc"
0x18004c015  xor     r8d, r8d; NetworkAddr
0x18004c018  mov     [rsp+38h+Options], 0; Options
0x18004c021  xor     ecx, ecx; ObjUuid
0x18004c023  call    cs:__imp_RpcStringBindingComposeW
0x18004c029  mov     ebx, eax
0x18004c02b  test    eax, eax
0x18004c02d  jnz     short loc_18004C051
0x18004c02f  mov     rcx, [rsp+38h+String]; StringBinding
0x18004c034  lea     rdx, DasHostCommandAndControl_v1_0_c_ifspec; Binding
0x18004c03b  call    cs:__imp_RpcBindingFromStringBindingW
0x18004c041  mov     ebx, eax
0x18004c043  test    eax, eax
0x18004c045  jnz     short loc_18004C051
0x18004c047  mov     rax, cs:DasHostCommandAndControl_v1_0_c_ifspec
0x18004c04e  mov     [rsi], rax
0x18004c051  cmp     [rsp+38h+Endpoint], 0
0x18004c057  jz      short loc_18004C06F
0x18004c059  call    cs:__imp_GetProcessHeap
0x18004c05f  mov     r8, [rsp+38h+Endpoint]; lpMem
0x18004c064  xor     edx, edx; dwFlags
0x18004c066  mov     rcx, rax; hHeap
0x18004c069  call    cs:__imp_HeapFree
0x18004c06f  cmp     [rsp+38h+String], 0
0x18004c075  jz      short loc_18004C082
0x18004c077  lea     rcx, [rsp+38h+String]; String
0x18004c07c  call    cs:__imp_RpcStringFreeW
0x18004c082  cmp     ebx, 1
0x18004c085  jl      short loc_18004C090
0x18004c087  movzx   ebx, bx
0x18004c08a  or      ebx, 80010000h
0x18004c090  mov     eax, ebx
0x18004c092  mov     rbx, [rsp+38h+arg_8]
0x18004c097  add     rsp, 30h
0x18004c09b  pop     rsi
0x18004c09c  retn
```
