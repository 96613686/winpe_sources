# CThreadContext::~CThreadContext(void)

- ea: `0x18001c358`
- end: `0x18001c3dd`
- name: `??1CThreadContext@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CThreadContext *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013144`
- `0x18001aa1c`
- `0x18001afd0`
- `0x18001b250`
- `0x18001ba30`
- `0x18001bdd8`
- `0x18001d530`
- `0x18002e1dc`
- `0x18002e63c`
- `0x180038798`
- `0x18003b26c`
- `0x18004e150`
- `0x18004e3d0`
- `0x18004e5a0`

## callees

- `0x18001c358`
- `0x18001c3e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c397`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c3ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c3ac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001c3c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001c3c8`
- `RPCRT4!RpcRevertToSelf` at `0x18001c371`
- `RPCRT4!RpcRevertToSelf` at `0x18001c371`

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
0x18001c358  push    rbx
0x18001c35a  sub     rsp, 20h
0x18001c35e  mov     rbx, rcx
0x18001c361  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18001c366  cmp     dword ptr [rbx], 0
0x18001c369  jnz     short loc_18001C391
0x18001c36b  cmp     dword ptr [rbx+14h], 0
0x18001c36f  jz      short loc_18001C384
0x18001c371  call    cs:__imp_RpcRevertToSelf
0x18001c378  nop     dword ptr [rax+rax+00h]
0x18001c37d  mov     dword ptr [rbx+14h], 0
0x18001c384  cmp     dword ptr [rbx+10h], 0
0x18001c388  jnz     short loc_18001C3C8
0x18001c38a  add     rsp, 20h
0x18001c38e  pop     rbx
0x18001c38f  retn
0x18001c391  mov     rdx, [rbx+8]; Token
0x18001c395  xor     ecx, ecx; Thread
0x18001c397  call    cs:__imp_SetThreadToken
0x18001c39e  nop     dword ptr [rax+rax+00h]
0x18001c3a3  mov     rcx, [rbx+8]; hObject
0x18001c3a7  test    rcx, rcx
0x18001c3aa  jz      short loc_18001C3C0
0x18001c3ac  call    cs:__imp_CloseHandle
0x18001c3b3  nop     dword ptr [rax+rax+00h]
0x18001c3b8  mov     qword ptr [rbx+8], 0
0x18001c3c0  mov     dword ptr [rbx], 0
0x18001c3c6  jmp     short loc_18001C36B
0x18001c3c8  call    cs:__imp_RevertToSelf
0x18001c3cf  nop     dword ptr [rax+rax+00h]
0x18001c3d4  mov     dword ptr [rbx+10h], 0
0x18001c3db  jmp     short loc_18001C38A
```
