# CEventFactory::ReserveEventObject<CPerfInfoTraceHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x18003d184`
- end: `0x18003d244`
- name: `??$ReserveEventObject@VCPerfInfoTraceHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800126d4`
- `0x180012814`

## callees

- `0x180020c74`
- `0x180020c98`
- `0x180021268`
- `0x18003d184`
- `0x18003d334`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003d19c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003d19c`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CPerfInfoTraceHeaderEvent>(
        __int64 a1,
        void *a2,
        union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  CPerfInfoTraceHeaderEvent *v8; // rax
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
    v8 = (CPerfInfoTraceHeaderEvent *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
      v8 = CPerfInfoTraceHeaderEvent::CPerfInfoTraceHeaderEvent(v8, a2, v9);
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
0x18003d184  mov     [rsp+arg_0], rbx
0x18003d189  mov     [rsp+arg_8], rsi
0x18003d18e  push    rdi
0x18003d18f  sub     rsp, 20h
0x18003d193  mov     rcx, r8; ListHead
0x18003d196  mov     rdi, r8
0x18003d199  mov     rsi, rdx
0x18003d19c  call    cs:__imp_InterlockedPopEntrySList
0x18003d1a2  mov     rbx, rax
0x18003d1a5  test    rax, rax
0x18003d1a8  jnz     short loc_18003D218
0x18003d1aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d1b1  lea     ecx, [rax+20h]; unsigned __int64
0x18003d1b4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003d1b9  mov     rbx, rax
0x18003d1bc  test    rax, rax
0x18003d1bf  jnz     short loc_18003D1C5
0x18003d1c1  xor     eax, eax
0x18003d1c3  jmp     short loc_18003D234
0x18003d1c5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d1cc  mov     ecx, 0B8h; unsigned __int64
0x18003d1d1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d1d6  test    rax, rax
0x18003d1d9  jz      short loc_18003D1E6
0x18003d1db  mov     rdx, rsi; void *
0x18003d1de  mov     rcx, rax; this
0x18003d1e1  call    ??0CPerfInfoTraceHeaderEvent@@QEAA@PEAX0@Z; CPerfInfoTraceHeaderEvent::CPerfInfoTraceHeaderEvent(void *,void *)
0x18003d1e6  lea     rcx, [rbx+18h]
0x18003d1ea  mov     [rcx], rax
0x18003d1ed  test    rax, rax
0x18003d1f0  jnz     short loc_18003D1FC
0x18003d1f2  mov     rcx, rbx; Block
0x18003d1f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d1fa  jmp     short loc_18003D1C1
0x18003d1fc  mov     [rax+90h], rcx
0x18003d203  mov     rcx, [rcx]
0x18003d206  mov     rax, [rcx]
0x18003d209  mov     rax, [rax+8]
0x18003d20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d212  mov     [rbx+10h], rdi
0x18003d216  jmp     short loc_18003D230
0x18003d218  mov     rax, [rax+18h]
0x18003d21c  mov     word ptr [rax+88h], 0
0x18003d225  mov     qword ptr [rax+0A0h], 0
0x18003d230  mov     rax, [rbx+18h]
0x18003d234  mov     rbx, [rsp+28h+arg_0]
0x18003d239  mov     rsi, [rsp+28h+arg_8]
0x18003d23e  add     rsp, 20h
0x18003d242  pop     rdi
0x18003d243  retn
```
