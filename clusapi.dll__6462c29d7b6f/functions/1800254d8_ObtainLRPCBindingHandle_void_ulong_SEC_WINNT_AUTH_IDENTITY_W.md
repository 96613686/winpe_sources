# ObtainLRPCBindingHandle(void * *,ulong,_SEC_WINNT_AUTH_IDENTITY_W *)

- ea: `0x1800254d8`
- end: `0x18002555a`
- name: `?ObtainLRPCBindingHandle@@YAKPEAPEAXKPEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z`
- size: `130`
- prototype: `unsigned int __fastcall(RPC_BINDING_HANDLE *Binding, unsigned int, struct _SEC_WINNT_AUTH_IDENTITY_W *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021fe0`

## callees

- `0x1800254d8`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180025547`
- `RPCRT4!RpcStringFreeW` at `0x180025547`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180025532`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180025532`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002551e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002551e`

## pseudocode

```c
__int64 __fastcall ObtainLRPCBindingHandle(
        RPC_BINDING_HANDLE *Binding,
        __int64 a2,
        struct _SEC_WINNT_AUTH_IDENTITY_W *a3)
{
  unsigned int v4; // ebx
  RPC_WSTR StringBinding; // [rsp+50h] [rbp+18h] BYREF

  *Binding = 0;
  StringBinding = 0;
  v4 = RpcStringBindingComposeW(
         (RPC_WSTR)L"b97db8b2-4c63-11cf-bff6-08002be23f2f",
         (RPC_WSTR)L"ncalrpc",
         0,
         0,
         0,
         &StringBinding);
  if ( !v4 )
    v4 = RpcBindingFromStringBindingW(StringBinding, Binding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v4;
}

```

## disassembly

```asm
0x1800254d8  mov     r11, rsp
0x1800254db  mov     [r11+8], rbx
0x1800254df  mov     [r11+18h], r8
0x1800254e3  push    rdi
0x1800254e4  sub     rsp, 30h
0x1800254e8  lea     rax, [r11+18h]
0x1800254ec  mov     qword ptr [rcx], 0
0x1800254f3  mov     rdi, rcx
0x1800254f6  mov     [r11-10h], rax
0x1800254fa  xor     r9d, r9d; Endpoint
0x1800254fd  mov     qword ptr [r11-18h], 0
0x180025505  xor     r8d, r8d; NetworkAddr
0x180025508  mov     qword ptr [r11+18h], 0
0x180025510  lea     rdx, aNcalrpc; "ncalrpc"
0x180025517  lea     rcx, ObjUuid; "b97db8b2-4c63-11cf-bff6-08002be23f2f"
0x18002551e  call    cs:__imp_RpcStringBindingComposeW
0x180025524  mov     ebx, eax
0x180025526  test    eax, eax
0x180025528  jnz     short loc_18002553A
0x18002552a  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18002552f  mov     rdx, rdi; Binding
0x180025532  call    cs:__imp_RpcBindingFromStringBindingW
0x180025538  mov     ebx, eax
0x18002553a  cmp     [rsp+38h+StringBinding], 0
0x180025540  jz      short loc_18002554D
0x180025542  lea     rcx, [rsp+38h+StringBinding]; String
0x180025547  call    cs:__imp_RpcStringFreeW
0x18002554d  mov     eax, ebx
0x18002554f  mov     rbx, [rsp+38h+arg_0]
0x180025554  add     rsp, 30h
0x180025558  pop     rdi
0x180025559  retn
```
