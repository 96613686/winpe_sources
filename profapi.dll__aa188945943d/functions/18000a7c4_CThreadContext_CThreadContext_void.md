# CThreadContext::~CThreadContext(void)

- ea: `0x18000a7c4`
- end: `0x18000a7fc`
- name: `??1CThreadContext@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000a2d8`

## callees

- `0x1800061a4`
- `0x18000a7c4`
- `0x18000a804`
- `0x18000a848`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000a7ed`
- `RPCRT4!RpcRevertToSelf` at `0x18000a7ed`

## pseudocode

```c
void __fastcall CThreadContext::~CThreadContext(CThreadContext *this)
{
  CThreadContext::RevertPrivileges(this);
  CThreadContext::RevertToPreviousToken(this);
  if ( *((_DWORD *)this + 5) )
  {
    RpcRevertToSelf();
    *((_DWORD *)this + 5) = 0;
  }
  CThreadContext::RevertToSelf(this);
}

```

## disassembly

```asm
0x18000a7c4  push    rbx
0x18000a7c6  sub     rsp, 20h
0x18000a7ca  mov     rbx, rcx
0x18000a7cd  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18000a7d2  mov     rcx, rbx; this
0x18000a7d5  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x18000a7da  cmp     dword ptr [rbx+14h], 0
0x18000a7de  jnz     short loc_18000A7ED
0x18000a7e0  mov     rcx, rbx; this
0x18000a7e3  add     rsp, 20h
0x18000a7e7  pop     rbx
0x18000a7e8  jmp     ?RevertToSelf@CThreadContext@@QEAAXXZ; CThreadContext::RevertToSelf(void)
0x18000a7ed  call    cs:__imp_RpcRevertToSelf
0x18000a7f3  mov     dword ptr [rbx+14h], 0
0x18000a7fa  jmp     short loc_18000A7E0
```
