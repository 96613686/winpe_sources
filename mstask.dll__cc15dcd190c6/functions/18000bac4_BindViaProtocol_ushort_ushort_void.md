# BindViaProtocol(ushort *,ushort *,void * *)

- ea: `0x18000bac4`
- end: `0x18000bb1a`
- name: `?BindViaProtocol@@YAJPEAG0PEAPEAX@Z`
- size: `86`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e60`
- `0x180009acc`

## callees

- `0x180008180`
- `0x18000bac4`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18000bafd`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bafd`

## pseudocode

```c
RPC_STATUS __fastcall BindViaProtocol(unsigned __int16 *a1, unsigned __int16 *a2, void **a3)
{
  RPC_STATUS result; // eax
  RPC_WSTR String[3]; // [rsp+30h] [rbp-18h] BYREF

  *a3 = 0;
  String[0] = 0;
  result = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, String);
  if ( !result )
    return BindingFromStringBinding(String, a3);
  return result;
}

```

## disassembly

```asm
0x18000bac4  mov     r11, rsp
0x18000bac7  push    rbx
0x18000bac8  sub     rsp, 40h
0x18000bacc  lea     rax, [r11-18h]
0x18000bad0  mov     qword ptr [r8], 0
0x18000bad7  mov     rbx, r8
0x18000bada  mov     [r11-20h], rax
0x18000bade  xor     r9d, r9d; Endpoint
0x18000bae1  mov     qword ptr [r11-28h], 0
0x18000bae9  xor     r8d, r8d; NetworkAddr
0x18000baec  mov     qword ptr [r11-18h], 0
0x18000baf4  lea     rdx, aNcalrpc; "ncalrpc"
0x18000bafb  xor     ecx, ecx; ObjUuid
0x18000bafd  call    cs:__imp_RpcStringBindingComposeW
0x18000bb03  test    eax, eax
0x18000bb05  jnz     short loc_18000BB14
0x18000bb07  mov     rdx, rbx; void **
0x18000bb0a  lea     rcx, [rsp+48h+String]; String
0x18000bb0f  call    ?BindingFromStringBinding@@YAJPEAPEAGPEAPEAX@Z; BindingFromStringBinding(ushort * *,void * *)
0x18000bb14  add     rsp, 40h
0x18000bb18  pop     rbx
0x18000bb19  retn
```
