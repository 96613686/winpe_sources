# CEfsClientBase::EfsFlushEfsCacheClient(ushort *)

- ea: `0x18000bc88`
- end: `0x18000bd72`
- name: `?EfsFlushEfsCacheClient@CEfsClientBase@@QEAAKPEAG@Z`
- size: `234`
- prototype: `unsigned int __fastcall(CEfsClientBase *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800079c0`

## callees

- `0x18000ade8`
- `0x18000bc88`
- `0x18000c640`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bd3e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bd3e`
- `RPCRT4!RpcBindingUnbind` at `0x18000bd11`
- `RPCRT4!RpcBindingUnbind` at `0x18000bd11`
- `RPCRT4!RpcExceptionFilter` at `0x1800124b6`
- `RPCRT4!RpcExceptionFilter` at `0x1800124b6`
- `RPCRT4!RpcBindingFree` at `0x18000bd64`
- `RPCRT4!RpcBindingFree` at `0x18000bd64`
- `RPCRT4!RpcBindingBind` at `0x18000bd29`
- `RPCRT4!RpcBindingBind` at `0x18000bd29`

## pseudocode

```c
__int64 __fastcall CEfsClientBase::EfsFlushEfsCacheClient(CEfsClientBase *this, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp+8h] BYREF
  RPC_BINDING_HANDLE v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  Binding = 0;
  v2 = CEfsClientBase::CreateLocalRpcBinding(this, &Binding);
  if ( !v2 )
  {
    LODWORD(v5) = 0;
    v2 = EfsRpcFlushEfsCache(Binding);
    v5 = Binding;
    if ( Binding )
      RpcBindingFree(&v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18000bc88  mov     rax, rsp
0x18000bc8b  mov     [rax+10h], rdx
0x18000bc8f  mov     [rax+8], rcx
0x18000bc93  push    rbx
0x18000bc94  sub     rsp, 30h
0x18000bc98  mov     qword ptr [rax+8], 0
0x18000bca0  lea     rdx, [rax+8]; void **
0x18000bca4  call    ?CreateLocalRpcBinding@CEfsClientBase@@IEAAKPEAPEAX@Z; CEfsClientBase::CreateLocalRpcBinding(void * *)
0x18000bca9  mov     ebx, eax
0x18000bcab  test    eax, eax
0x18000bcad  jnz     loc_18000BD6A
0x18000bcb3  mov     dword ptr [rsp+38h+arg_8], eax
0x18000bcb7  cmp     eax, 3
0x18000bcba  jnb     loc_18000BD50
0x18000bcc0  mov     rcx, [rsp+38h+Binding]
0x18000bcc5  call    EfsRpcFlushEfsCache
0x18000bcca  mov     ebx, eax
0x18000bccc  mov     [rsp+38h+var_18], eax
0x18000bcd0  jmp     short loc_18000BD50
0x18000bcd2  mov     ebx, eax
0x18000bcd4  mov     [rsp+38h+var_18], eax
0x18000bcd8  xor     cl, cl
0x18000bcda  add     eax, 0FFFFF954h
0x18000bcdf  cmp     eax, 2Dh ; '-'
0x18000bce2  ja      short loc_18000BCF8
0x18000bce4  mov     rdx, 2000000C4201h
0x18000bcee  bt      rdx, rax
0x18000bcf2  jnb     short loc_18000BCF8
0x18000bcf4  mov     cl, 1
0x18000bcf6  jmp     short loc_18000BD08
0x18000bcf8  cmp     ebx, 6BBh
0x18000bcfe  jz      short loc_18000BD08
0x18000bd00  cmp     ebx, 5B4h
0x18000bd06  jnz     short loc_18000BD50
0x18000bd08  test    cl, cl
0x18000bd0a  jz      short loc_18000BD39
0x18000bd0c  mov     rcx, [rsp+38h+Binding]; Binding
0x18000bd11  call    cs:__imp_RpcBindingUnbind
0x18000bd17  test    eax, eax
0x18000bd19  jnz     short loc_18000BD50
0x18000bd1b  lea     r8, qword_180016C60; IfSpec
0x18000bd22  mov     rdx, [rsp+38h+Binding]; Binding
0x18000bd27  xor     ecx, ecx; pAsync
0x18000bd29  call    cs:__imp_RpcBindingBind
0x18000bd2f  mov     ebx, eax
0x18000bd31  mov     [rsp+38h+var_18], eax
0x18000bd35  test    eax, eax
0x18000bd37  js      short loc_18000BD50
0x18000bd39  mov     ecx, 12Ch; dwMilliseconds
0x18000bd3e  call    cs:__imp_Sleep
0x18000bd44  nop
0x18000bd45  mov     eax, dword ptr [rsp+38h+arg_8]
0x18000bd49  inc     eax
0x18000bd4b  jmp     loc_18000BCB3
0x18000bd50  mov     rax, [rsp+38h+Binding]
0x18000bd55  mov     [rsp+38h+arg_8], rax
0x18000bd5a  test    rax, rax
0x18000bd5d  jz      short loc_18000BD6A
0x18000bd5f  lea     rcx, [rsp+38h+arg_8]; Binding
0x18000bd64  call    cs:__imp_RpcBindingFree
0x18000bd6a  mov     eax, ebx
0x18000bd6c  add     rsp, 30h
0x18000bd70  pop     rbx
0x18000bd71  retn
0x1800124a8  push    rbp
0x1800124aa  sub     rsp, 20h
0x1800124ae  mov     rbp, rdx
0x1800124b1  mov     rcx, [rcx]
0x1800124b4  mov     ecx, [rcx]; ExceptionCode
0x1800124b6  call    cs:__imp_RpcExceptionFilter
0x1800124bc  nop
0x1800124bd  add     rsp, 20h
0x1800124c1  pop     rbp
0x1800124c2  retn
```
