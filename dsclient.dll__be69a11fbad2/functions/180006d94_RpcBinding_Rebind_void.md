# RpcBinding::Rebind(void)

- ea: `0x180006d94`
- end: `0x180006dfc`
- name: `?Rebind@RpcBinding@@QEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001400`
- `0x180001500`
- `0x180001b20`
- `0x180001be0`
- `0x1800039c0`
- `0x180003a7c`
- `0x180003b38`
- `0x180003c20`

## callees

- `0x180002420`
- `0x180004fb0`
- `0x180006d94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006daf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006daf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006de4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006de4`
- `RPCRT4!RpcBindingFree` at `0x180006dbd`
- `RPCRT4!RpcBindingFree` at `0x180006dbd`

## pseudocode

```c
__int64 __fastcall RpcBinding::Rebind(void **this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  int v3; // esi
  void *v4; // rdx
  RpcBinding *v5; // rcx
  const unsigned __int16 *v6; // r8

  v1 = (struct _RTL_CRITICAL_SECTION *)(this + 1);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 1));
  if ( *this )
  {
    RpcBindingFree(this);
    *this = 0;
    v3 = RpcBinding::BindToRPCServerWithMutualAuth(v5, v4, v6, this);
    if ( v3 < 0 )
      RpcBinding::Unbind(this);
  }
  if ( v1 )
    LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006d94  mov     [rsp+arg_0], rbx
0x180006d99  mov     [rsp+arg_8], rsi
0x180006d9e  push    rdi
0x180006d9f  sub     rsp, 30h
0x180006da3  lea     rdi, [rcx+8]
0x180006da7  mov     rbx, rcx
0x180006daa  mov     rcx, rdi; lpCriticalSection
0x180006dad  xor     esi, esi
0x180006daf  call    cs:__imp_EnterCriticalSection
0x180006db5  cmp     [rbx], rsi
0x180006db8  jz      short loc_180006DDC
0x180006dba  mov     rcx, rbx; Binding
0x180006dbd  call    cs:__imp_RpcBindingFree
0x180006dc3  mov     [rbx], rsi
0x180006dc6  mov     r9, rbx; void **
0x180006dc9  call    ?BindToRPCServerWithMutualAuth@RpcBinding@@AEAAJPEAXPEBGPEAPEAXK@Z; RpcBinding::BindToRPCServerWithMutualAuth(void *,ushort const *,void * *,ulong)
0x180006dce  mov     esi, eax
0x180006dd0  test    eax, eax
0x180006dd2  jns     short loc_180006DDC
0x180006dd4  mov     rcx, rbx; Binding
0x180006dd7  call    ?Unbind@RpcBinding@@QEAAXXZ; RpcBinding::Unbind(void)
0x180006ddc  test    rdi, rdi
0x180006ddf  jz      short loc_180006DEA
0x180006de1  mov     rcx, rdi; lpCriticalSection
0x180006de4  call    cs:__imp_LeaveCriticalSection
0x180006dea  mov     rbx, [rsp+38h+arg_0]
0x180006def  mov     eax, esi
0x180006df1  mov     rsi, [rsp+38h+arg_8]
0x180006df6  add     rsp, 30h
0x180006dfa  pop     rdi
0x180006dfb  retn
```
