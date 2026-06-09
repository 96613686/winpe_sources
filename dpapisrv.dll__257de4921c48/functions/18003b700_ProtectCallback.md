# _ProtectCallback

- ea: `0x18003b700`
- end: `0x18003b807`
- name: `_ProtectCallback`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003b700`
- `0x18003baa0`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x18003b76c`
- `RPCRT4!RpcStringBindingParseW` at `0x18003b76c`
- `RPCRT4!RpcStringFreeW` at `0x18003b7d9`
- `RPCRT4!RpcStringFreeW` at `0x18003b7f2`
- `RPCRT4!RpcStringFreeW` at `0x18003b7d9`
- `RPCRT4!RpcStringFreeW` at `0x18003b7f2`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18003b720`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18003b720`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b7a7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b7a7`

## pseudocode

```c
__int64 __fastcall ProtectCallback(__int64 a1, void *a2)
{
  RPC_STATUS v2; // eax
  const char *v3; // r8
  unsigned int v4; // ebx
  unsigned int v5; // r9d
  unsigned int v6; // ecx
  RPC_WSTR Protseq; // [rsp+50h] [rbp+18h] BYREF
  RPC_WSTR StringBinding; // [rsp+58h] [rbp+20h] BYREF

  StringBinding = 0;
  Protseq = 0;
  v2 = RpcBindingToStringBindingW(a2, &StringBinding);
  v4 = v2;
  if ( v2 )
  {
    v5 = 244;
LABEL_3:
    v6 = v2;
LABEL_4:
    SidKeyDebugTraceError(v6, "Status", v3, v5);
    goto LABEL_10;
  }
  v2 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  v4 = v2;
  if ( v2 )
  {
    v5 = 258;
    goto LABEL_3;
  }
  if ( CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncalrpc", -1) != 2 )
  {
    v4 = 5;
    v5 = 271;
    v6 = 5;
    goto LABEL_4;
  }
  v4 = 0;
LABEL_10:
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v4;
}

```

## disassembly

```asm
0x18003b700  push    rbx
0x18003b702  sub     rsp, 30h
0x18003b706  mov     rcx, rdx; Binding
0x18003b709  mov     [rsp+38h+StringBinding], 0
0x18003b712  lea     rdx, [rsp+38h+StringBinding]; StringBinding
0x18003b717  mov     [rsp+38h+Protseq], 0
0x18003b720  call    cs:__imp_RpcBindingToStringBindingW
0x18003b727  nop     dword ptr [rax+rax+00h]
0x18003b72c  mov     ebx, eax
0x18003b72e  test    eax, eax
0x18003b730  jz      short loc_18003B74B
0x18003b732  mov     r9d, 0F4h; unsigned int
0x18003b738  mov     ecx, eax; unsigned int
0x18003b73a  lea     rdx, aStatus; "Status"
0x18003b741  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b746  jmp     loc_18003B7CC
0x18003b74b  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18003b750  lea     r8, [rsp+38h+Protseq]; Protseq
0x18003b755  mov     [rsp+38h+NetworkOptions], 0; NetworkOptions
0x18003b75e  xor     r9d, r9d; NetworkAddr
0x18003b761  xor     edx, edx; ObjUuid
0x18003b763  mov     [rsp+38h+Endpoint], 0; Endpoint
0x18003b76c  call    cs:__imp_RpcStringBindingParseW
0x18003b773  nop     dword ptr [rax+rax+00h]
0x18003b778  mov     ebx, eax
0x18003b77a  test    eax, eax
0x18003b77c  jz      short loc_18003B786
0x18003b77e  mov     r9d, 102h
0x18003b784  jmp     short loc_18003B738
0x18003b786  mov     r8, [rsp+38h+Protseq]; lpString1
0x18003b78b  lea     rax, Protseq; "ncalrpc"
0x18003b792  or      r9d, 0FFFFFFFFh; cchCount1
0x18003b796  mov     dword ptr [rsp+38h+NetworkOptions], r9d; cchCount2
0x18003b79b  mov     [rsp+38h+Endpoint], rax; lpString2
0x18003b7a0  lea     edx, [r9+2]; dwCmpFlags
0x18003b7a4  lea     ecx, [rdx+7Eh]; Locale
0x18003b7a7  call    cs:__imp_CompareStringW
0x18003b7ae  nop     dword ptr [rax+rax+00h]
0x18003b7b3  cmp     eax, 2
0x18003b7b6  jz      short loc_18003B7CA
0x18003b7b8  mov     ebx, 5
0x18003b7bd  mov     r9d, 10Fh
0x18003b7c3  mov     ecx, ebx
0x18003b7c5  jmp     loc_18003B73A
0x18003b7ca  xor     ebx, ebx
0x18003b7cc  cmp     [rsp+38h+Protseq], 0
0x18003b7d2  jz      short loc_18003B7E5
0x18003b7d4  lea     rcx, [rsp+38h+Protseq]; String
0x18003b7d9  call    cs:__imp_RpcStringFreeW
0x18003b7e0  nop     dword ptr [rax+rax+00h]
0x18003b7e5  cmp     [rsp+38h+StringBinding], 0
0x18003b7eb  jz      short loc_18003B7FE
0x18003b7ed  lea     rcx, [rsp+38h+StringBinding]; String
0x18003b7f2  call    cs:__imp_RpcStringFreeW
0x18003b7f9  nop     dword ptr [rax+rax+00h]
0x18003b7fe  mov     eax, ebx
0x18003b800  add     rsp, 30h
0x18003b804  pop     rbx
0x18003b805  retn
```
