# CEventFactory::ReserveEventObject<CMessageTraceHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x18001e6c0`
- end: `0x18001e780`
- name: `??$ReserveEventObject@VCMessageTraceHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800126d4`
- `0x180012814`

## callees

- `0x18001e6c0`
- `0x180020c74`
- `0x180020c98`
- `0x180021268`
- `0x18003d2d4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001e6d8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001e6d8`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CMessageTraceHeaderEvent>(
        __int64 a1,
        void *a2,
        union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  CMessageTraceHeaderEvent *v8; // rax
  void *v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rax

  v5 = InterlockedPopEntrySList(a3);
  p_Next = &v5->Next;
  if ( v5 )
  {
    v11 = *((_QWORD *)&v5[1].Next + 1);
    *(_WORD *)(v11 + 136) = 0;
    *(_QWORD *)(v11 + 160) = 0;
  }
  else
  {
    p_Next = operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !p_Next )
      return 0;
    v8 = (CMessageTraceHeaderEvent *)operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
      v8 = CMessageTraceHeaderEvent::CMessageTraceHeaderEvent(v8, a2, v9);
    v10 = p_Next + 3;
    p_Next[3] = v8;
    if ( !v8 )
    {
      operator delete(p_Next);
      return 0;
    }
    *((_QWORD *)v8 + 18) = v10;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    p_Next[2] = a3;
  }
  return p_Next[3];
}

```

## disassembly

```asm
0x18001e6c0  mov     [rsp+arg_0], rbx
0x18001e6c5  mov     [rsp+arg_8], rsi
0x18001e6ca  push    rdi
0x18001e6cb  sub     rsp, 20h
0x18001e6cf  mov     rcx, r8; ListHead
0x18001e6d2  mov     rdi, r8
0x18001e6d5  mov     rsi, rdx
0x18001e6d8  call    cs:__imp_InterlockedPopEntrySList
0x18001e6de  mov     rbx, rax
0x18001e6e1  test    rax, rax
0x18001e6e4  jnz     short loc_18001E754
0x18001e6e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e6ed  lea     ecx, [rax+20h]; unsigned __int64
0x18001e6f0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001e6f5  mov     rbx, rax
0x18001e6f8  test    rax, rax
0x18001e6fb  jnz     short loc_18001E701
0x18001e6fd  xor     eax, eax
0x18001e6ff  jmp     short loc_18001E770
0x18001e701  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e708  mov     ecx, 0F8h; unsigned __int64
0x18001e70d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e712  test    rax, rax
0x18001e715  jz      short loc_18001E722
0x18001e717  mov     rdx, rsi; void *
0x18001e71a  mov     rcx, rax; this
0x18001e71d  call    ??0CMessageTraceHeaderEvent@@QEAA@PEAX0@Z; CMessageTraceHeaderEvent::CMessageTraceHeaderEvent(void *,void *)
0x18001e722  lea     rcx, [rbx+18h]
0x18001e726  mov     [rcx], rax
0x18001e729  test    rax, rax
0x18001e72c  jnz     short loc_18001E738
0x18001e72e  mov     rcx, rbx; Block
0x18001e731  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e736  jmp     short loc_18001E6FD
0x18001e738  mov     [rax+90h], rcx
0x18001e73f  mov     rcx, [rcx]
0x18001e742  mov     rax, [rcx]
0x18001e745  mov     rax, [rax+8]
0x18001e749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e74e  mov     [rbx+10h], rdi
0x18001e752  jmp     short loc_18001E76C
0x18001e754  mov     rax, [rax+18h]
0x18001e758  mov     word ptr [rax+88h], 0
0x18001e761  mov     qword ptr [rax+0A0h], 0
0x18001e76c  mov     rax, [rbx+18h]
0x18001e770  mov     rbx, [rsp+28h+arg_0]
0x18001e775  mov     rsi, [rsp+28h+arg_8]
0x18001e77a  add     rsp, 20h
0x18001e77e  pop     rdi
0x18001e77f  retn
```
