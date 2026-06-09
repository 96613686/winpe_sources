# CWiGigDAFProviderAssociation::StartRemoveAssociation(void)

- ea: `0x18000b5c0`
- end: `0x18000b657`
- name: `?StartRemoveAssociation@CWiGigDAFProviderAssociation@@UEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(CWiGigDAFProviderAssociation *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001ef4`
- `0x18000b5c0`
- `0x180016f0c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::StartRemoveAssociation(CWiGigDAFProviderAssociation *this)
{
  RTL_SRWLOCK *v2; // rsi
  struct Work *v3; // rbx
  __int64 v4; // rcx

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 334);
  v3 = (struct Work *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
  {
    v4 = *((_QWORD *)this + 7);
    *(_QWORD *)v3 = &AssociationWork<IAepAssociationCallback>::`vftable';
    *((_QWORD *)v3 + 1) = v4;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *((_QWORD *)v3 + 2) = this;
    (*(void (__fastcall **)(CWiGigDAFProviderAssociation *))(*(_QWORD *)this + 8LL))(this);
    *(_QWORD *)v3 = &RemoveWork::`vftable';
  }
  else
  {
    v3 = 0;
  }
  return DockingProviders::SubmitWork(v2, v3);
}

```

## disassembly

```asm
0x18000b5c0  mov     [rsp+arg_8], rbx
0x18000b5c5  mov     [rsp+arg_10], rsi
0x18000b5ca  push    rdi
0x18000b5cb  sub     rsp, 20h
0x18000b5cf  mov     rdi, rcx
0x18000b5d2  mov     rsi, [rcx+0A70h]
0x18000b5d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b5e0  mov     ecx, 18h; unsigned __int64
0x18000b5e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b5ea  mov     rbx, rax
0x18000b5ed  mov     [rsp+28h+arg_0], rax
0x18000b5f2  test    rax, rax
0x18000b5f5  jz      short loc_18000B63B
0x18000b5f7  mov     rcx, [rdi+38h]
0x18000b5fb  lea     rax, ??_7?$AssociationWork@UIAepAssociationCallback@@@@6B@; const AssociationWork<IAepAssociationCallback>::`vftable'
0x18000b602  mov     [rbx], rax
0x18000b605  mov     [rbx+8], rcx
0x18000b609  test    rcx, rcx
0x18000b60c  jz      short loc_18000B61B
0x18000b60e  mov     rax, [rcx]
0x18000b611  mov     rax, [rax+8]
0x18000b615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b61a  nop
0x18000b61b  mov     [rbx+10h], rdi
0x18000b61f  mov     rax, [rdi]
0x18000b622  mov     rcx, rdi
0x18000b625  mov     rax, [rax+8]
0x18000b629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62e  nop
0x18000b62f  lea     rax, ??_7RemoveWork@@6B@; const RemoveWork::`vftable'
0x18000b636  mov     [rbx], rax
0x18000b639  jmp     short loc_18000B63D
0x18000b63b  xor     ebx, ebx
0x18000b63d  mov     rdx, rbx; struct Work *
0x18000b640  mov     rcx, rsi; SRWLock
0x18000b643  mov     rbx, [rsp+28h+arg_8]
0x18000b648  mov     rsi, [rsp+28h+arg_10]
0x18000b64d  add     rsp, 20h
0x18000b651  pop     rdi
0x18000b652  jmp     ?SubmitWork@DockingProviders@@QEAAJPEAVWork@@@Z; DockingProviders::SubmitWork(Work *)
```
