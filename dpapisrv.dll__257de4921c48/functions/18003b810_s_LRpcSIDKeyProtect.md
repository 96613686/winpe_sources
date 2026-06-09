# s_LRpcSIDKeyProtect

- ea: `0x18003b810`
- end: `0x18003b8ef`
- name: `s_LRpcSIDKeyProtect`
- size: `223`
- prototype: `__int64 __fastcall(void *, __int64, __int64, unsigned int, __int64, _DWORD *, _QWORD *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18003b810`
- `0x18003baa0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18003b822`
- `RPCRT4!RpcImpersonateClient` at `0x18003b822`
- `RPCRT4!RpcRevertToSelf` at `0x18003b8d7`
- `RPCRT4!RpcRevertToSelf` at `0x18003b8d7`
- `KdsCli!SIDKeyProtect` at `0x18003b8ad`
- `KdsCli!SIDKeyProtect` at `0x18003b8ad`

## pseudocode

```c
__int64 __fastcall s_LRpcSIDKeyProtect(
        void *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *a6,
        _QWORD *a7,
        int a8)
{
  RPC_STATUS v11; // eax
  const char *v12; // r8
  int v13; // ebx
  signed int v14; // eax
  const char *v15; // r8

  v11 = RpcImpersonateClient(a1);
  v13 = v11;
  if ( v11 )
  {
    SidKeyDebugTraceError(v11, "RpcStatus", v12, 0x54u);
    if ( v13 >= 0 )
      return (unsigned __int16)v13 | 0x80010000;
  }
  else
  {
    *a6 = 0;
    *a7 = 0;
    v14 = SIDKeyProtect(a2, a3, a5, a4, &qword_18004C048, a7, a6, a8);
    v13 = v14;
    if ( v14 >= 0 )
      v13 = 0;
    else
      SidKeyDebugTraceError(v14, "hr", v15, 0x6Au);
    RpcRevertToSelf();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18003b810  push    rbx
0x18003b812  push    rbp
0x18003b813  push    rsi
0x18003b814  push    rdi
0x18003b815  sub     rsp, 48h
0x18003b819  mov     edi, r9d
0x18003b81c  mov     rsi, r8
0x18003b81f  mov     rbp, rdx
0x18003b822  call    cs:__imp_RpcImpersonateClient
0x18003b829  nop     dword ptr [rax+rax+00h]
0x18003b82e  mov     ebx, eax
0x18003b830  test    eax, eax
0x18003b832  jz      short loc_18003B85E
0x18003b834  mov     r9d, 54h ; 'T'; unsigned int
0x18003b83a  lea     rdx, aRpcstatus; "RpcStatus"
0x18003b841  mov     ecx, eax; unsigned int
0x18003b843  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b848  test    ebx, ebx
0x18003b84a  js      loc_18003B8E3
0x18003b850  movzx   ebx, bx
0x18003b853  or      ebx, 80010000h
0x18003b859  jmp     loc_18003B8E3
0x18003b85e  mov     rdx, [rsp+68h+arg_28]
0x18003b866  mov     r9d, edi
0x18003b869  mov     rcx, [rsp+68h+arg_30]
0x18003b871  mov     eax, [rsp+68h+arg_38]
0x18003b878  mov     r8, [rsp+68h+arg_20]
0x18003b880  mov     [rsp+68h+var_30], eax
0x18003b884  lea     rax, qword_18004C048
0x18003b88b  mov     [rsp+68h+var_38], rdx
0x18003b890  mov     dword ptr [rdx], 0
0x18003b896  mov     rdx, rsi
0x18003b899  mov     [rsp+68h+var_40], rcx
0x18003b89e  mov     qword ptr [rcx], 0
0x18003b8a5  mov     rcx, rbp
0x18003b8a8  mov     [rsp+68h+var_48], rax
0x18003b8ad  call    cs:__imp_SIDKeyProtect
0x18003b8b4  nop     dword ptr [rax+rax+00h]
0x18003b8b9  mov     ebx, eax
0x18003b8bb  test    eax, eax
0x18003b8bd  jns     short loc_18003B8D5
0x18003b8bf  mov     r9d, 6Ah ; 'j'; unsigned int
0x18003b8c5  lea     rdx, aHr; "hr"
0x18003b8cc  mov     ecx, eax; unsigned int
0x18003b8ce  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b8d3  jmp     short loc_18003B8D7
0x18003b8d5  xor     ebx, ebx
0x18003b8d7  call    cs:__imp_RpcRevertToSelf
0x18003b8de  nop     dword ptr [rax+rax+00h]
0x18003b8e3  mov     eax, ebx
0x18003b8e5  add     rsp, 48h
0x18003b8e9  pop     rdi
0x18003b8ea  pop     rsi
0x18003b8eb  pop     rbp
0x18003b8ec  pop     rbx
0x18003b8ed  retn
```
