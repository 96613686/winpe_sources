# PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(void)

- ea: `0x140016934`
- end: `0x140016969`
- name: `??1ImpersonateTokenThroughScope@PrnExcept@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(void **this)`
- caller_count: `10`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140010800`
- `0x140011574`
- `0x140011a00`
- `0x140011ce0`
- `0x140015800`
- `0x1400163c0`
- `0x14001ac08`
- `0x14005db37`
- `0x14005db49`
- `0x14005e867`

## callees

- `0x1400071e8`
- `0x140016934`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x14001694c`
- `ADVAPI32!SetThreadToken` at `0x14001694c`
- `KERNEL32!GetLastError` at `0x140016956`
- `KERNEL32!GetLastError` at `0x140016956`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(void **this)
{
  void *v1; // rdx

  v1 = *this;
  if ( *this == (void *)-1LL )
    v1 = 0;
  if ( !SetThreadToken(0, v1) )
    GetLastError();
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(this);
}

```

## disassembly

```asm
0x140016934  push    rbx
0x140016936  sub     rsp, 20h
0x14001693a  mov     rdx, [rcx]
0x14001693d  xor     eax, eax
0x14001693f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140016943  mov     rbx, rcx
0x140016946  cmovz   rdx, rax; Token
0x14001694a  xor     ecx, ecx; Thread
0x14001694c  call    cs:__imp_SetThreadToken
0x140016952  test    eax, eax
0x140016954  jnz     short loc_14001695C
0x140016956  call    cs:__imp_GetLastError
0x14001695c  mov     rcx, rbx
0x14001695f  add     rsp, 20h
0x140016963  pop     rbx
0x140016964  jmp     ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
```
