# CAepStoreAccess::~CAepStoreAccess(void)

- ea: `0x14001917c`
- end: `0x1400191e4`
- name: `??1CAepStoreAccess@@IEAA@XZ`
- size: `104`
- prototype: `void __fastcall(CAepStoreAccess *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400191ec`
- `0x1400197f0`

## callees

- `0x140009090`
- `0x14001917c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400191dd`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1400191c9`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1400191c9`
- `RPCRT4!RpcBindingFree` at `0x1400191bc`
- `RPCRT4!RpcBindingFree` at `0x1400191bc`

## pseudocode

```c
void __fastcall CAepStoreAccess::~CAepStoreAccess(CAepStoreAccess *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CAepStoreAccess::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    MIDL_user_free(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    MIDL_user_free(v3);
  if ( *((_QWORD *)this + 5) && RpcBindingFree((RPC_BINDING_HANDLE *)this + 5) )
    RpcSsDestroyClientContext((void **)this + 5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x14001917c  mov     [rsp+arg_0], rbx
0x140019181  push    rdi
0x140019182  sub     rsp, 20h
0x140019186  lea     rax, ??_7CAepStoreAccess@@6B@; const CAepStoreAccess::`vftable'
0x14001918d  mov     rbx, rcx
0x140019190  mov     [rcx], rax
0x140019193  mov     rcx, [rcx+10h]; void *
0x140019197  test    rcx, rcx
0x14001919a  jz      short loc_1400191A1
0x14001919c  call    MIDL_user_free
0x1400191a1  mov     rcx, [rbx+18h]; void *
0x1400191a5  test    rcx, rcx
0x1400191a8  jz      short loc_1400191AF
0x1400191aa  call    MIDL_user_free
0x1400191af  lea     rdi, [rbx+28h]
0x1400191b3  cmp     qword ptr [rdi], 0
0x1400191b7  jz      short loc_1400191CF
0x1400191b9  mov     rcx, rdi; Binding
0x1400191bc  call    cs:__imp_RpcBindingFree
0x1400191c2  test    eax, eax
0x1400191c4  jz      short loc_1400191CF
0x1400191c6  mov     rcx, rdi; ContextHandle
0x1400191c9  call    cs:__imp_RpcSsDestroyClientContext
0x1400191cf  lea     rcx, [rbx+30h]
0x1400191d3  mov     rbx, [rsp+28h+arg_0]
0x1400191d8  add     rsp, 20h
0x1400191dc  pop     rdi
0x1400191dd  jmp     cs:__imp_DeleteCriticalSection
```
