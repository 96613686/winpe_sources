# ServerGroupManager::getServersForAcctOnOff(ProxyContext *,RequestStack &)

- ea: `0x180021ec4`
- end: `0x180021f50`
- name: `?getServersForAcctOnOff@ServerGroupManager@@QEBAXPEAVProxyContext@@AEAVRequestStack@@@Z`
- size: `140`
- prototype: `void __fastcall(ServerGroupManager *__hidden this, struct ProxyContext *, struct RequestStack *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180021828`

## callees

- `0x18000e470`
- `0x180021ec4`
- `0x180027108`
- `0x180029cb4`
- `0x180029ee4`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180021ed6`
- `KERNEL32!GetCurrentThreadId` at `0x180021f38`
- `KERNEL32!GetCurrentThreadId` at `0x180021ed6`
- `KERNEL32!GetCurrentThreadId` at `0x180021f38`

## pseudocode

```c
void __fastcall ServerGroupManager::getServersForAcctOnOff(
        struct RemoteServer ***this,
        struct ProxyContext *a2,
        struct RequestStack *a3)
{
  DWORD CurrentThreadId; // eax
  struct RemoteServer **i; // rdi
  Request *v8; // rax
  Request *v9; // rcx
  DWORD v10; // eax

  CurrentThreadId = GetCurrentThreadId();
  Perimeter::Lock((Perimeter *)this, CurrentThreadId);
  for ( i = this[21]; i != this[22]; ++i )
  {
    v8 = (Request *)operator new(0x78u);
    if ( v8 )
      v9 = Request::Request(v8, a2, *i, 4u);
    else
      v9 = 0;
    *((_QWORD *)v9 + 1) = *(_QWORD *)a3;
    *(_QWORD *)a3 = v9;
    (**(void (__fastcall ***)(Request *))v9)(v9);
  }
  v10 = GetCurrentThreadId();
  Perimeter::Unlock((Perimeter *)this, v10);
}

```

## disassembly

```asm
0x180021ec4  push    rbx
0x180021ec6  push    rbp
0x180021ec7  push    rsi
0x180021ec8  push    rdi
0x180021ec9  sub     rsp, 28h
0x180021ecd  mov     rsi, r8
0x180021ed0  mov     rbp, rdx
0x180021ed3  mov     rbx, rcx
0x180021ed6  call    cs:__imp_GetCurrentThreadId
0x180021edc  mov     edx, eax; unsigned int
0x180021ede  mov     rcx, rbx; this
0x180021ee1  call    ?Lock@Perimeter@@QEAAXK@Z; Perimeter::Lock(ulong)
0x180021ee6  mov     rdi, [rbx+0A8h]
0x180021eed  jmp     short loc_180021F2F
0x180021eef  mov     ecx, 78h ; 'x'; Size
0x180021ef4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021ef9  test    rax, rax
0x180021efc  jz      short loc_180021F14
0x180021efe  mov     r8, [rdi]; struct RemoteServer *
0x180021f01  mov     r9b, 4; unsigned __int8
0x180021f04  mov     rdx, rbp; struct ProxyContext *
0x180021f07  mov     rcx, rax; this
0x180021f0a  call    ??0Request@@QEAA@PEAVProxyContext@@PEAVRemoteServer@@E@Z; Request::Request(ProxyContext *,RemoteServer *,uchar)
0x180021f0f  mov     rcx, rax
0x180021f12  jmp     short loc_180021F16
0x180021f14  xor     ecx, ecx
0x180021f16  mov     rax, [rsi]
0x180021f19  mov     [rcx+8], rax
0x180021f1d  mov     [rsi], rcx
0x180021f20  mov     rax, [rcx]
0x180021f23  mov     rax, [rax]
0x180021f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f2b  add     rdi, 8
0x180021f2f  cmp     rdi, [rbx+0B0h]
0x180021f36  jnz     short loc_180021EEF
0x180021f38  call    cs:__imp_GetCurrentThreadId
0x180021f3e  mov     edx, eax; unsigned int
0x180021f40  mov     rcx, rbx; this
0x180021f43  add     rsp, 28h
0x180021f47  pop     rdi
0x180021f48  pop     rsi
0x180021f49  pop     rbp
0x180021f4a  pop     rbx
0x180021f4b  jmp     ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
```
