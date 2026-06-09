# CWiGigDAFProviderAssociation::StartReadCeremonyData(IAepAssociationReadCallback *)

- ea: `0x18000b520`
- end: `0x18000b5ac`
- name: `?StartReadCeremonyData@CWiGigDAFProviderAssociation@@UEAAJPEAUIAepAssociationReadCallback@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(CWiGigDAFProviderAssociation *__hidden this, struct IAepAssociationReadCallback *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001ef4`
- `0x18000b520`
- `0x180016f0c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::StartReadCeremonyData(
        CWiGigDAFProviderAssociation *this,
        struct IAepAssociationReadCallback *a2)
{
  RTL_SRWLOCK *v4; // rbp
  struct Work *v5; // rbx

  v4 = (RTL_SRWLOCK *)*((_QWORD *)this + 334);
  v5 = (struct Work *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    *(_QWORD *)v5 = &AssociationWork<IAepAssociationCallback>::`vftable';
    *((_QWORD *)v5 + 1) = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IAepAssociationReadCallback *))(*(_QWORD *)a2 + 8LL))(a2);
    *((_QWORD *)v5 + 2) = this;
    (*(void (__fastcall **)(CWiGigDAFProviderAssociation *))(*(_QWORD *)this + 8LL))(this);
    *(_QWORD *)v5 = &ReadCeremonyDataWork::`vftable';
  }
  else
  {
    v5 = 0;
  }
  return DockingProviders::SubmitWork(v4, v5);
}

```

## disassembly

```asm
0x18000b520  push    rbx
0x18000b522  push    rbp
0x18000b523  push    rsi
0x18000b524  push    rdi
0x18000b525  sub     rsp, 28h
0x18000b529  mov     rdi, rdx
0x18000b52c  mov     rsi, rcx
0x18000b52f  mov     rbp, [rcx+0A70h]
0x18000b536  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b53d  mov     ecx, 18h; unsigned __int64
0x18000b542  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b547  mov     rbx, rax
0x18000b54a  mov     [rsp+48h+arg_0], rax
0x18000b54f  test    rax, rax
0x18000b552  jz      short loc_18000B597
0x18000b554  lea     rax, ??_7?$AssociationWork@UIAepAssociationCallback@@@@6B@; const AssociationWork<IAepAssociationCallback>::`vftable'
0x18000b55b  mov     [rbx], rax
0x18000b55e  mov     [rbx+8], rdi
0x18000b562  test    rdi, rdi
0x18000b565  jz      short loc_18000B577
0x18000b567  mov     rax, [rdi]
0x18000b56a  mov     rcx, rdi
0x18000b56d  mov     rax, [rax+8]
0x18000b571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b576  nop
0x18000b577  mov     [rbx+10h], rsi
0x18000b57b  mov     rax, [rsi]
0x18000b57e  mov     rcx, rsi
0x18000b581  mov     rax, [rax+8]
0x18000b585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b58a  nop
0x18000b58b  lea     rax, ??_7ReadCeremonyDataWork@@6B@; const ReadCeremonyDataWork::`vftable'
0x18000b592  mov     [rbx], rax
0x18000b595  jmp     short loc_18000B599
0x18000b597  xor     ebx, ebx
0x18000b599  mov     rdx, rbx; struct Work *
0x18000b59c  mov     rcx, rbp; SRWLock
0x18000b59f  add     rsp, 28h
0x18000b5a3  pop     rdi
0x18000b5a4  pop     rsi
0x18000b5a5  pop     rbp
0x18000b5a6  pop     rbx
0x18000b5a7  jmp     ?SubmitWork@DockingProviders@@QEAAJPEAVWork@@@Z; DockingProviders::SubmitWork(Work *)
```
