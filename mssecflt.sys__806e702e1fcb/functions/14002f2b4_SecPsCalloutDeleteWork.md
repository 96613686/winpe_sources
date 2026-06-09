# SecPsCalloutDeleteWork

- ea: `0x14002f2b4`
- end: `0x14002f355`
- name: `SecPsCalloutDeleteWork`
- size: `161`
- prototype: `__int64 __fastcall(PSLIST_ENTRY ListEntry)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140007350`

## callees

- `0x1400061dc`
- `0x140011610`
- `0x14002f2b4`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002f2f2`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002f2f2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f342`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f342`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f30b`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f30b`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002f2e4`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002f2e4`

## pseudocode

```c
void __fastcall SecPsCalloutDeleteWork(PSLIST_ENTRY ListEntry)
{
  void *v2; // rcx

  if ( ListEntry )
  {
    if ( ListEntry[2].Next )
      SecFreeNullTerminatedUnicode(&ListEntry[1].Next + 1);
    v2 = (void *)*((_QWORD *)&ListEntry[2].Next + 1);
    if ( v2 )
    {
      if ( LOBYTE(ListEntry[3].Next) )
        PsDereferenceImpersonationToken(v2);
      else
        PsDereferencePrimaryToken(v2);
    }
    ++dword_14001B39C;
    if ( ExQueryDepthSList(&Lookaside) < (unsigned __int16)word_14001B390 )
    {
      ExpInterlockedPushEntrySList(&Lookaside, ListEntry);
    }
    else
    {
      ++dword_14001B3A0;
      ((void (__fastcall *)(PSLIST_ENTRY))qword_14001B3B8)(ListEntry);
    }
  }
}

```

## disassembly

```asm
0x14002f2b4  test    rcx, rcx
0x14002f2b7  jz      locret_14002F353
0x14002f2bd  push    rbx
0x14002f2be  sub     rsp, 20h
0x14002f2c2  cmp     qword ptr [rcx+20h], 0
0x14002f2c7  mov     rbx, rcx
0x14002f2ca  jz      short loc_14002F2D5
0x14002f2cc  add     rcx, 18h
0x14002f2d0  call    SecFreeNullTerminatedUnicode
0x14002f2d5  mov     rcx, [rbx+28h]; PrimaryToken
0x14002f2d9  test    rcx, rcx
0x14002f2dc  jz      short loc_14002F2FE
0x14002f2de  cmp     byte ptr [rbx+30h], 0
0x14002f2e2  jz      short loc_14002F2F2
0x14002f2e4  call    cs:__imp_PsDereferenceImpersonationToken
0x14002f2eb  nop     dword ptr [rax+rax+00h]
0x14002f2f0  jmp     short loc_14002F2FE
0x14002f2f2  call    cs:__imp_PsDereferencePrimaryToken
0x14002f2f9  nop     dword ptr [rax+rax+00h]
0x14002f2fe  inc     cs:dword_14001B39C
0x14002f304  lea     rcx, Lookaside; SListHead
0x14002f30b  call    cs:__imp_ExQueryDepthSList
0x14002f312  nop     dword ptr [rax+rax+00h]
0x14002f317  cmp     ax, cs:word_14001B390
0x14002f31e  jb      short loc_14002F338
0x14002f320  inc     cs:dword_14001B3A0
0x14002f326  mov     rcx, rbx
0x14002f329  mov     rax, cs:qword_14001B3B8
0x14002f330  call    cs:__guard_dispatch_icall_fptr
0x14002f336  jmp     short loc_14002F34E
0x14002f338  mov     rdx, rbx; ListEntry
0x14002f33b  lea     rcx, Lookaside; ListHead
0x14002f342  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002f349  nop     dword ptr [rax+rax+00h]
0x14002f34e  add     rsp, 20h
0x14002f352  pop     rbx
0x14002f353  retn
```
