# KsecDisconnectRpcConnection

- ea: `0x180001478`
- end: `0x180001505`
- name: `KsecDisconnectRpcConnection`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800272b0`

## callees

- `0x180001478`
- `0x18000150c`
- `0x180001c00`
- `0x180001cf0`
- `0x180007e38`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800014bd`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800014bd`
- `msrpc!RpcSsDestroyClientContext` at `0x1800014d2`
- `msrpc!RpcSsDestroyClientContext` at `0x1800014d2`
- `msrpc!I_RpcExceptionFilter` at `0x18001127b`
- `msrpc!I_RpcExceptionFilter` at `0x18001127b`

## pseudocode

```c
__int64 __fastcall KsecDisconnectRpcConnection(struct _EPROCESS *a1)
{
  unsigned int v2; // ebx
  void *ContextHandle; // [rsp+38h] [rbp+10h] BYREF
  struct _EPROCESS **v5; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  ContextHandle = KsecpRemoveRpcConnection(a1);
  if ( ContextHandle )
  {
    KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v5);
    if ( v5 && a1 == *v5 )
    {
      if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
        RpcSsDestroyClientContext(&ContextHandle);
    }
    else if ( a1 != WPP_MAIN_CB.DeviceExtension )
    {
      v2 = DisconnectRpcConnectionAsync(ContextHandle);
    }
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v5);
  }
  return v2;
}

```

## disassembly

```asm
0x180001478  mov     [rsp+arg_0], rbx
0x18000147d  push    rdi
0x18000147e  sub     rsp, 20h
0x180001482  mov     rdi, rcx
0x180001485  xor     ebx, ebx
0x180001487  call    ?KsecpRemoveRpcConnection@@YAPEAXPEAU_EPROCESS@@@Z; KsecpRemoveRpcConnection(_EPROCESS *)
0x18000148c  mov     [rsp+28h+ContextHandle], rax
0x180001491  test    rax, rax
0x180001494  jnz     short loc_1800014A4
0x180001496  mov     eax, ebx
0x180001498  mov     rbx, [rsp+28h+arg_0]
0x18000149d  add     rsp, 20h
0x1800014a1  pop     rdi
0x1800014a2  retn
0x1800014a4  lea     rcx, [rsp+28h+arg_10]; this
0x1800014a9  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800014ae  mov     rax, [rsp+28h+arg_10]
0x1800014b3  test    rax, rax
0x1800014b6  jz      short loc_1800014E4
0x1800014b8  cmp     rdi, [rax]
0x1800014bb  jnz     short loc_1800014E4
0x1800014bd  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800014c4  nop     dword ptr [rax+rax+00h]
0x1800014c9  test    al, al
0x1800014cb  jz      short loc_1800014F9
0x1800014cd  lea     rcx, [rsp+28h+ContextHandle]; ContextHandle
0x1800014d2  call    cs:__imp_RpcSsDestroyClientContext
0x1800014d9  nop     dword ptr [rax+rax+00h]
0x1800014de  jmp     short loc_1800014F9
0x1800014e0  mov     ebx, eax
0x1800014e2  jmp     short loc_1800014F9
0x1800014e4  cmp     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1800014eb  jz      short loc_1800014F9
0x1800014ed  mov     rcx, [rsp+28h+ContextHandle]
0x1800014f2  call    DisconnectRpcConnectionAsync
0x1800014f7  mov     ebx, eax
0x1800014f9  lea     rcx, [rsp+28h+arg_10]; this
0x1800014fe  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180001503  jmp     short loc_180001496
0x18001126d  push    rbp
0x18001126f  sub     rsp, 20h
0x180011273  mov     rbp, rdx
0x180011276  mov     rcx, [rcx]
0x180011279  mov     ecx, [rcx]; ExceptionCode
0x18001127b  call    cs:__imp_I_RpcExceptionFilter
0x180011282  nop     dword ptr [rax+rax+00h]
0x180011287  nop
0x180011288  add     rsp, 20h
0x18001128c  pop     rbp
0x18001128d  retn
```
