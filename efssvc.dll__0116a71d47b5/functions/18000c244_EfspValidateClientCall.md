# EfspValidateClientCall

- ea: `0x18000c244`
- end: `0x18000c2ea`
- name: `EfspValidateClientCall`
- size: `166`
- prototype: `RPC_STATUS __fastcall(RPC_BINDING_HANDLE ClientBinding, _DWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b7e0`
- `0x18000b880`
- `0x18000baa0`
- `0x18000bad0`
- `0x18000bc20`
- `0x18000be00`
- `0x18000bea0`

## callees

- `0x18000c244`
- `0x18000c392`
- `0x18000c3c0`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000c297`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000c297`

## pseudocode

```c
RPC_STATUS __fastcall EfspValidateClientCall(RPC_BINDING_HANDLE ClientBinding, _DWORD *a2)
{
  RPC_STATUS result; // eax
  _DWORD RpcCallAttributes[2]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v6[32]; // [rsp+28h] [rbp-80h] BYREF
  int v7; // [rsp+48h] [rbp-60h]
  int v8; // [rsp+4Ch] [rbp-5Ch]
  int v9; // [rsp+54h] [rbp-54h]
  int v10; // [rsp+58h] [rbp-50h]
  int v11; // [rsp+5Ch] [rbp-4Ch]

  *a2 = 0;
  memset_0(v6, 0, 0x68u);
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 32;
  result = RpcServerInqCallAttributesW(ClientBinding, RpcCallAttributes);
  if ( !result && v10 == 3 && v9 && v8 == 10 && v7 == 6 && v11 == 1 )
    *a2 = 1;
  return result;
}

```

## disassembly

```asm
0x18000c244  mov     [rsp+arg_10], rbx
0x18000c249  push    rdi
0x18000c24a  sub     rsp, 0A0h
0x18000c251  mov     rax, cs:__security_cookie
0x18000c258  xor     rax, rsp
0x18000c25b  mov     [rsp+0A8h+var_18], rax
0x18000c263  mov     rdi, rdx
0x18000c266  mov     dword ptr [rdx], 0
0x18000c26c  xor     edx, edx; Val
0x18000c26e  mov     rbx, rcx
0x18000c271  lea     rcx, [rsp+0A8h+var_80]; void *
0x18000c276  lea     r8d, [rdx+68h]; Size
0x18000c27a  call    memset_0
0x18000c27f  lea     rdx, [rsp+0A8h+RpcCallAttributes]; RpcCallAttributes
0x18000c284  mov     [rsp+0A8h+RpcCallAttributes], 3
0x18000c28c  mov     rcx, rbx; ClientBinding
0x18000c28f  mov     [rsp+0A8h+var_84], 20h ; ' '
0x18000c297  call    cs:__imp_RpcServerInqCallAttributesW
0x18000c29d  test    eax, eax
0x18000c29f  jnz     short loc_18000C2C9
0x18000c2a1  cmp     [rsp+0A8h+var_50], 3
0x18000c2a6  jnz     short loc_18000C2C9
0x18000c2a8  cmp     [rsp+0A8h+var_54], eax
0x18000c2ac  jz      short loc_18000C2C9
0x18000c2ae  cmp     [rsp+0A8h+var_5C], 0Ah
0x18000c2b3  jnz     short loc_18000C2C9
0x18000c2b5  cmp     [rsp+0A8h+var_60], 6
0x18000c2ba  jnz     short loc_18000C2C9
0x18000c2bc  cmp     [rsp+0A8h+var_4C], 1
0x18000c2c1  jnz     short loc_18000C2C9
0x18000c2c3  mov     dword ptr [rdi], 1
0x18000c2c9  mov     rcx, [rsp+0A8h+var_18]
0x18000c2d1  xor     rcx, rsp; StackCookie
0x18000c2d4  call    __security_check_cookie
0x18000c2d9  mov     rbx, [rsp+0A8h+arg_10]
0x18000c2e1  add     rsp, 0A0h
0x18000c2e8  pop     rdi
0x18000c2e9  retn
```
