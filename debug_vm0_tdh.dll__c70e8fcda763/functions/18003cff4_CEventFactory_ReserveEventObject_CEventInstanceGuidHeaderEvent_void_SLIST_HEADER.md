# CEventFactory::ReserveEventObject<CEventInstanceGuidHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x18003cff4`
- end: `0x18003d0b4`
- name: `??$ReserveEventObject@VCEventInstanceGuidHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
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
- `0x18003cff4`
- `0x18003d24c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003d00c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003d00c`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CEventInstanceGuidHeaderEvent>(
        __int64 a1,
        void *a2,
        union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  CEventInstanceGuidHeaderEvent *v8; // rax
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
    v8 = (CEventInstanceGuidHeaderEvent *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
      v8 = CEventInstanceGuidHeaderEvent::CEventInstanceGuidHeaderEvent(v8, a2, v9);
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
0x18003cff4  mov     [rsp+arg_0], rbx
0x18003cff9  mov     [rsp+arg_8], rsi
0x18003cffe  push    rdi
0x18003cfff  sub     rsp, 20h
0x18003d003  mov     rcx, r8; ListHead
0x18003d006  mov     rdi, r8
0x18003d009  mov     rsi, rdx
0x18003d00c  call    cs:__imp_InterlockedPopEntrySList
0x18003d012  mov     rbx, rax
0x18003d015  test    rax, rax
0x18003d018  jnz     short loc_18003D088
0x18003d01a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d021  lea     ecx, [rax+20h]; unsigned __int64
0x18003d024  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003d029  mov     rbx, rax
0x18003d02c  test    rax, rax
0x18003d02f  jnz     short loc_18003D035
0x18003d031  xor     eax, eax
0x18003d033  jmp     short loc_18003D0A4
0x18003d035  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d03c  mov     ecx, 0B8h; unsigned __int64
0x18003d041  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d046  test    rax, rax
0x18003d049  jz      short loc_18003D056
0x18003d04b  mov     rdx, rsi; void *
0x18003d04e  mov     rcx, rax; this
0x18003d051  call    ??0CEventInstanceGuidHeaderEvent@@QEAA@PEAX0@Z; CEventInstanceGuidHeaderEvent::CEventInstanceGuidHeaderEvent(void *,void *)
0x18003d056  lea     rcx, [rbx+18h]
0x18003d05a  mov     [rcx], rax
0x18003d05d  test    rax, rax
0x18003d060  jnz     short loc_18003D06C
0x18003d062  mov     rcx, rbx; Block
0x18003d065  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d06a  jmp     short loc_18003D031
0x18003d06c  mov     [rax+90h], rcx
0x18003d073  mov     rcx, [rcx]
0x18003d076  mov     rax, [rcx]
0x18003d079  mov     rax, [rax+8]
0x18003d07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d082  mov     [rbx+10h], rdi
0x18003d086  jmp     short loc_18003D0A0
0x18003d088  mov     rax, [rax+18h]
0x18003d08c  mov     word ptr [rax+88h], 0
0x18003d095  mov     qword ptr [rax+0A0h], 0
0x18003d0a0  mov     rax, [rbx+18h]
0x18003d0a4  mov     rbx, [rsp+28h+arg_0]
0x18003d0a9  mov     rsi, [rsp+28h+arg_8]
0x18003d0ae  add     rsp, 20h
0x18003d0b2  pop     rdi
0x18003d0b3  retn
```
