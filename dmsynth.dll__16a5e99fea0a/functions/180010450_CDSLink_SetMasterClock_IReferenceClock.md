# CDSLink::SetMasterClock(IReferenceClock *)

- ea: `0x180010450`
- end: `0x1800104b8`
- name: `?SetMasterClock@CDSLink@@UEAAJPEAUIReferenceClock@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, struct IReferenceClock *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010450`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CDSLink::SetMasterClock(CDSLink *this, struct IReferenceClock *a2)
{
  __int64 v4; // rcx

  if ( !a2 || !a2->lpVtbl || !a2->lpVtbl->QueryInterface )
    return 2147500035LL;
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 7) = a2;
  ((void (__fastcall *)(struct IReferenceClock *))a2->lpVtbl->AddRef)(a2);
  return 0;
}

```

## disassembly

```asm
0x180010450  mov     [rsp+arg_0], rbx
0x180010455  push    rdi
0x180010456  sub     rsp, 20h
0x18001045a  mov     rbx, rdx
0x18001045d  mov     rdi, rcx
0x180010460  test    rdx, rdx
0x180010463  jz      short loc_1800104A8
0x180010465  mov     rax, [rdx]
0x180010468  test    rax, rax
0x18001046b  jz      short loc_1800104A8
0x18001046d  cmp     qword ptr [rax], 0
0x180010471  jz      short loc_1800104A8
0x180010473  mov     rcx, [rcx+38h]
0x180010477  test    rcx, rcx
0x18001047a  jz      short loc_180010488
0x18001047c  mov     rax, [rcx]
0x18001047f  mov     rax, [rax+10h]
0x180010483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010488  mov     [rdi+38h], rbx
0x18001048c  mov     rcx, rbx
0x18001048f  mov     rax, [rbx]
0x180010492  mov     rax, [rax+8]
0x180010496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001049b  xor     eax, eax
0x18001049d  mov     rbx, [rsp+28h+arg_0]
0x1800104a2  add     rsp, 20h
0x1800104a6  pop     rdi
0x1800104a7  retn
0x1800104a8  mov     rbx, [rsp+28h+arg_0]
0x1800104ad  mov     eax, 80004003h
0x1800104b2  add     rsp, 20h
0x1800104b6  pop     rdi
0x1800104b7  retn
```
