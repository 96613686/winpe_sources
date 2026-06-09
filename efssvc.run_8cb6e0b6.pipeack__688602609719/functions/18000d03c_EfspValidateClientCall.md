# EfspValidateClientCall

- ea: `0x18000d03c`
- end: `0x18000d0e9`
- name: `EfspValidateClientCall`
- size: `173`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c470`
- `0x18000c530`
- `0x18000c780`
- `0x18000c7c0`
- `0x18000c930`
- `0x18000cb40`
- `0x18000cbf0`

## callees

- `0x18000d03c`
- `0x18000d192`
- `0x18000d1c0`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000d08f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000d08f`

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
0x18000d03c  mov     [rsp+arg_10], rbx
0x18000d041  push    rdi
0x18000d042  sub     rsp, 0A0h
0x18000d049  mov     rax, cs:__security_cookie
0x18000d050  xor     rax, rsp
0x18000d053  mov     [rsp+0A8h+var_18], rax
0x18000d05b  mov     rdi, rdx
0x18000d05e  mov     dword ptr [rdx], 0
0x18000d064  xor     edx, edx; Val
0x18000d066  mov     rbx, rcx
0x18000d069  lea     rcx, [rsp+0A8h+var_80]; void *
0x18000d06e  lea     r8d, [rdx+68h]; Size
0x18000d072  call    memset_0
0x18000d077  lea     rdx, [rsp+0A8h+RpcCallAttributes]; RpcCallAttributes
0x18000d07c  mov     [rsp+0A8h+RpcCallAttributes], 3
0x18000d084  mov     rcx, rbx; ClientBinding
0x18000d087  mov     [rsp+0A8h+var_84], 20h ; ' '
0x18000d08f  call    cs:__imp_RpcServerInqCallAttributesW
0x18000d096  nop     dword ptr [rax+rax+00h]
0x18000d09b  test    eax, eax
0x18000d09d  jnz     short loc_18000D0C7
0x18000d09f  cmp     [rsp+0A8h+var_50], 3
0x18000d0a4  jnz     short loc_18000D0C7
0x18000d0a6  cmp     [rsp+0A8h+var_54], eax
0x18000d0aa  jz      short loc_18000D0C7
0x18000d0ac  cmp     [rsp+0A8h+var_5C], 0Ah
0x18000d0b1  jnz     short loc_18000D0C7
0x18000d0b3  cmp     [rsp+0A8h+var_60], 6
0x18000d0b8  jnz     short loc_18000D0C7
0x18000d0ba  cmp     [rsp+0A8h+var_4C], 1
0x18000d0bf  jnz     short loc_18000D0C7
0x18000d0c1  mov     dword ptr [rdi], 1
0x18000d0c7  mov     rcx, [rsp+0A8h+var_18]
0x18000d0cf  xor     rcx, rsp; StackCookie
0x18000d0d2  call    __security_check_cookie
0x18000d0d7  mov     rbx, [rsp+0A8h+arg_10]
0x18000d0df  add     rsp, 0A0h
0x18000d0e6  pop     rdi
0x18000d0e7  retn
```
