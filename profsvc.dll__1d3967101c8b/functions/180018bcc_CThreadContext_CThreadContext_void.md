# CThreadContext::~CThreadContext(void)

- ea: `0x180018bcc`
- end: `0x180018c38`
- name: `??1CThreadContext@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `13`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017bdc`
- `0x180018110`
- `0x180018c40`
- `0x1800190f4`
- `0x180019ba0`
- `0x18001a634`
- `0x18002af20`
- `0x18002b6b8`
- `0x18002bb60`
- `0x180032ce0`
- `0x18003735c`
- `0x180038a30`
- `0x180039d6c`

## callees

- `0x180018bcc`
- `0x180019048`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018c04`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180018c04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018c13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018c13`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018c29`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018c29`
- `RPCRT4!RpcRevertToSelf` at `0x180018be5`
- `RPCRT4!RpcRevertToSelf` at `0x180018be5`

## pseudocode

```c
void __fastcall CThreadContext::~CThreadContext(HANDLE *this)
{
  HANDLE v2; // rcx

  CThreadContext::RevertPrivileges((CThreadContext *)this);
  if ( *(_DWORD *)this )
  {
    SetThreadToken(0, this[1]);
    v2 = this[1];
    if ( v2 )
    {
      CloseHandle(v2);
      this[1] = 0;
    }
    *(_DWORD *)this = 0;
  }
  if ( *((_DWORD *)this + 5) )
  {
    RpcRevertToSelf();
    *((_DWORD *)this + 5) = 0;
  }
  if ( *((_DWORD *)this + 4) )
  {
    RevertToSelf();
    *((_DWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180018bcc  push    rbx
0x180018bce  sub     rsp, 20h
0x180018bd2  mov     rbx, rcx
0x180018bd5  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180018bda  cmp     dword ptr [rbx], 0
0x180018bdd  jnz     short loc_180018BFE
0x180018bdf  cmp     dword ptr [rbx+14h], 0
0x180018be3  jz      short loc_180018BF2
0x180018be5  call    cs:__imp_RpcRevertToSelf
0x180018beb  mov     dword ptr [rbx+14h], 0
0x180018bf2  cmp     dword ptr [rbx+10h], 0
0x180018bf6  jnz     short loc_180018C29
0x180018bf8  add     rsp, 20h
0x180018bfc  pop     rbx
0x180018bfd  retn
0x180018bfe  mov     rdx, [rbx+8]; Token
0x180018c02  xor     ecx, ecx; Thread
0x180018c04  call    cs:__imp_SetThreadToken
0x180018c0a  mov     rcx, [rbx+8]; hObject
0x180018c0e  test    rcx, rcx
0x180018c11  jz      short loc_180018C21
0x180018c13  call    cs:__imp_CloseHandle
0x180018c19  mov     qword ptr [rbx+8], 0
0x180018c21  mov     dword ptr [rbx], 0
0x180018c27  jmp     short loc_180018BDF
0x180018c29  call    cs:__imp_RevertToSelf
0x180018c2f  mov     dword ptr [rbx+10h], 0
0x180018c36  jmp     short loc_180018BF8
```
