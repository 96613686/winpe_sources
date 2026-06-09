# CThreadContext::~CThreadContext(void)

- ea: `0x180005558`
- end: `0x1800055c0`
- name: `??1CThreadContext@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003090`
- `0x180009770`
- `0x18000fed8`
- `0x180018a3c`
- `0x18001e710`
- `0x18001e936`
- `0x18001ed61`
- `0x18001efb4`

## callees

- `0x180005558`
- `0x1800055c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005571`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005580`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005580`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800055ad`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800055ad`
- `RPCRT4!RpcRevertToSelf` at `0x18000559a`
- `RPCRT4!RpcRevertToSelf` at `0x18000559a`

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
0x180005558  push    rbx
0x18000555a  sub     rsp, 20h
0x18000555e  mov     rbx, rcx
0x180005561  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180005566  cmp     dword ptr [rbx], 0
0x180005569  jz      short loc_180005594
0x18000556b  mov     rdx, [rbx+8]; Token
0x18000556f  xor     ecx, ecx; Thread
0x180005571  call    cs:__imp_SetThreadToken
0x180005577  mov     rcx, [rbx+8]; hObject
0x18000557b  test    rcx, rcx
0x18000557e  jz      short loc_18000558E
0x180005580  call    cs:__imp_CloseHandle
0x180005586  mov     qword ptr [rbx+8], 0
0x18000558e  mov     dword ptr [rbx], 0
0x180005594  cmp     dword ptr [rbx+14h], 0
0x180005598  jz      short loc_1800055A7
0x18000559a  call    cs:__imp_RpcRevertToSelf
0x1800055a0  mov     dword ptr [rbx+14h], 0
0x1800055a7  cmp     dword ptr [rbx+10h], 0
0x1800055ab  jz      short loc_1800055BA
0x1800055ad  call    cs:__imp_RevertToSelf
0x1800055b3  mov     dword ptr [rbx+10h], 0
0x1800055ba  add     rsp, 20h
0x1800055be  pop     rbx
0x1800055bf  retn
```
