# RpcBinding::BindToRPCServerWithMutualAuth(void *,ushort const *,void * *,ulong)

- ea: `0x180004fb0`
- end: `0x18000500b`
- name: `?BindToRPCServerWithMutualAuth@RpcBinding@@AEAAJPEAXPEBGPEAPEAXK@Z`
- size: `91`
- prototype: `__int64 __fastcall(RpcBinding *this, void *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180006d94`

## callees

- `0x180004fb0`
- `0x180007820`
- `0x1800095e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004ff8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180004ff8`

## pseudocode

```c
__int64 __fastcall RpcBinding::BindToRPCServerWithMutualAuth(
        RpcBinding *this,
        void *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  void *v5; // rdx
  DevPlat::Shared *v6; // rcx
  int v7; // ebx
  const unsigned __int16 *v8; // r8
  void **v10; // [rsp+20h] [rbp-18h]
  PSID pSid; // [rsp+50h] [rbp+18h] BYREF

  pSid = 0;
  v7 = RpcBinding::RetrieveLocalSystemSid(this, &pSid);
  if ( v7 >= 0 )
    v7 = DevPlat::Shared::BindToRPCServerInSessionMutualAuth(v6, v5, v8, a4, v10, (__int64)pSid);
  if ( pSid )
    FreeSid(pSid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004fb0  mov     rax, rsp
0x180004fb3  mov     [rax+8], rbx
0x180004fb7  mov     [rax+18h], r8
0x180004fbb  push    rdi; void *
0x180004fbc  sub     rsp, 30h
0x180004fc0  lea     rdx, [rax+18h]; void **
0x180004fc4  mov     qword ptr [rax+18h], 0
0x180004fcc  mov     rdi, r9
0x180004fcf  call    ?RetrieveLocalSystemSid@RpcBinding@@AEAAJPEAPEAX@Z; RpcBinding::RetrieveLocalSystemSid(void * *)
0x180004fd4  mov     ebx, eax
0x180004fd6  test    eax, eax
0x180004fd8  js      short loc_180004FEE
0x180004fda  mov     rax, [rsp+38h+pSid]
0x180004fdf  mov     r9, rdi; unsigned int
0x180004fe2  mov     qword ptr [rsp+38h+var_10], rax; unsigned int
0x180004fe7  call    ?BindToRPCServerInSessionMutualAuth@Shared@DevPlat@@YAJPEAXPEBGKPEAPEAXK0@Z; DevPlat::Shared::BindToRPCServerInSessionMutualAuth(void *,ushort const *,ulong,void * *,ulong,void *)
0x180004fec  mov     ebx, eax
0x180004fee  mov     rcx, [rsp+38h+pSid]; pSid
0x180004ff3  test    rcx, rcx
0x180004ff6  jz      short loc_180004FFE
0x180004ff8  call    cs:__imp_FreeSid
0x180004ffe  mov     eax, ebx
0x180005000  mov     rbx, [rsp+38h+arg_0]
0x180005005  add     rsp, 30h
0x180005009  pop     rdi
0x18000500a  retn
```
