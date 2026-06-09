# GetDasRpcBinding(void * *)

- ea: `0x18000b320`
- end: `0x18000b454`
- name: `?GetDasRpcBinding@@YAJPEAPEAX@Z`
- size: `308`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b460`
- `0x18000b6b0`
- `0x18000b8f0`

## callees

- `0x180002f10`
- `0x18000b320`

## import_xrefs

- `RPCRT4!RpcSsDestroyClientContext` at `0x18000b406`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000b406`
- `RPCRT4!RpcBindingFree` at `0x18000b3f8`
- `RPCRT4!RpcBindingFree` at `0x18000b3f8`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000b39e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000b39e`
- `RPCRT4!RpcBindingSetOption` at `0x18000b3d6`
- `RPCRT4!RpcBindingSetOption` at `0x18000b3d6`
- `RPCRT4!RpcStringFreeW` at `0x18000b417`
- `RPCRT4!RpcStringFreeW` at `0x18000b417`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000b3bf`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000b3bf`

## pseudocode

```c
__int64 __fastcall GetDasRpcBinding(void **a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // sf
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp+20h] BYREF
  RPC_WSTR String; // [rsp+58h] [rbp+28h] BYREF

  String = 0;
  Binding = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a57375a075f03242dafadbc95279287d_Traceguids);
  *a1 = 0;
  v2 = RpcStringBindingComposeW(
         (RPC_WSTR)L"6319e220-2fd5-48bc-a92f-ba70384e4d24",
         (RPC_WSTR)L"ncalrpc",
         0,
         0,
         0,
         &String);
  v3 = v2;
  v4 = v2 < 0;
  if ( v2
    || (v2 = RpcBindingFromStringBindingW(String, &Binding), v3 = v2, v4 = v2 < 0, v2)
    || (v2 = RpcBindingSetOption(Binding, 0xDu, 1u), v3 = v2, v4 = v2 < 0, v2) )
  {
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80010000;
  }
  else
  {
    *a1 = Binding;
    Binding = (RPC_BINDING_HANDLE)(unsigned int)v2;
  }
  if ( Binding && RpcBindingFree(&Binding) )
    RpcSsDestroyClientContext(&Binding);
  if ( String )
    RpcStringFreeW(&String);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a57375a075f03242dafadbc95279287d_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x18000b320  mov     [rsp-18h+arg_10], rbx
0x18000b325  push    rbp
0x18000b326  push    rdi
0x18000b327  push    r14
0x18000b329  mov     rbp, rsp
0x18000b32c  sub     rsp, 30h
0x18000b330  mov     rdi, rcx
0x18000b333  mov     [rbp+String], 0
0x18000b33b  mov     [rbp+Binding], 0
0x18000b343  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b34a  lea     r14, WPP_GLOBAL_Control
0x18000b351  cmp     rcx, r14
0x18000b354  jz      short loc_18000B371
0x18000b356  cmp     byte ptr [rcx+19h], 4
0x18000b35a  jb      short loc_18000B371
0x18000b35c  mov     rcx, [rcx+10h]
0x18000b360  lea     r8, WPP_a57375a075f03242dafadbc95279287d_Traceguids
0x18000b367  mov     edx, 0Ah
0x18000b36c  call    WPP_SF_s
0x18000b371  lea     rax, [rbp+String]
0x18000b375  mov     qword ptr [rdi], 0
0x18000b37c  mov     [rsp+30h+StringBinding], rax; StringBinding
0x18000b381  lea     rdx, ProtSeq; "ncalrpc"
0x18000b388  xor     r9d, r9d; Endpoint
0x18000b38b  mov     [rsp+30h+Options], 0; Options
0x18000b394  xor     r8d, r8d; NetworkAddr
0x18000b397  lea     rcx, a6319e2202fd548; "6319e220-2fd5-48bc-a92f-ba70384e4d24"
0x18000b39e  call    cs:__imp_RpcStringBindingComposeW
0x18000b3a4  mov     ebx, eax
0x18000b3a6  test    eax, eax
0x18000b3a8  jz      short loc_18000B3B7
0x18000b3aa  js      short loc_18000B3ED
0x18000b3ac  movzx   ebx, ax
0x18000b3af  or      ebx, 80010000h
0x18000b3b5  jmp     short loc_18000B3ED
0x18000b3b7  mov     rcx, [rbp+String]; StringBinding
0x18000b3bb  lea     rdx, [rbp+Binding]; Binding
0x18000b3bf  call    cs:__imp_RpcBindingFromStringBindingW
0x18000b3c5  mov     ebx, eax
0x18000b3c7  test    eax, eax
0x18000b3c9  jnz     short loc_18000B3AA
0x18000b3cb  mov     rcx, [rbp+Binding]; hBinding
0x18000b3cf  lea     edx, [rax+0Dh]; option
0x18000b3d2  lea     r8d, [rax+1]; optionValue
0x18000b3d6  call    cs:__imp_RpcBindingSetOption
0x18000b3dc  mov     ebx, eax
0x18000b3de  test    eax, eax
0x18000b3e0  jnz     short loc_18000B3AA
0x18000b3e2  mov     rax, [rbp+Binding]
0x18000b3e6  mov     [rdi], rax
0x18000b3e9  mov     [rbp+Binding], rbx
0x18000b3ed  cmp     [rbp+Binding], 0
0x18000b3f2  jz      short loc_18000B40C
0x18000b3f4  lea     rcx, [rbp+Binding]; Binding
0x18000b3f8  call    cs:__imp_RpcBindingFree
0x18000b3fe  test    eax, eax
0x18000b400  jz      short loc_18000B40C
0x18000b402  lea     rcx, [rbp+Binding]; ContextHandle
0x18000b406  call    cs:__imp_RpcSsDestroyClientContext
0x18000b40c  cmp     [rbp+String], 0
0x18000b411  jz      short loc_18000B41D
0x18000b413  lea     rcx, [rbp+String]; String
0x18000b417  call    cs:__imp_RpcStringFreeW
0x18000b41d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b424  cmp     rcx, r14
0x18000b427  jz      short loc_18000B444
0x18000b429  cmp     byte ptr [rcx+19h], 4
0x18000b42d  jb      short loc_18000B444
0x18000b42f  mov     rcx, [rcx+10h]
0x18000b433  lea     r8, WPP_a57375a075f03242dafadbc95279287d_Traceguids
0x18000b43a  mov     edx, 0Bh
0x18000b43f  call    WPP_SF_s
0x18000b444  mov     eax, ebx
0x18000b446  mov     rbx, [rsp+30h+arg_10]
0x18000b44b  add     rsp, 30h
0x18000b44f  pop     r14
0x18000b451  pop     rdi
0x18000b452  pop     rbp
0x18000b453  retn
```
