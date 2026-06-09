# FTReleaseOpResources

- ea: `0x14000292c`
- end: `0x1400029f6`
- name: `FTReleaseOpResources`
- size: `202`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001ae0`

## callees

- `0x14000292c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400029cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400029e3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400029cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400029e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002959`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002976`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002993`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002959`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002976`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002993`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029b5`
- `FLTMGR!FltReleaseContext` at `0x14000293c`
- `FLTMGR!FltReleaseContext` at `0x14000293c`

## pseudocode

```c
void __fastcall FTReleaseOpResources(PFLT_CONTEXT *Entry)
{
  PFLT_CONTEXT v2; // rcx
  PFLT_CONTEXT v3; // rcx
  PFLT_CONTEXT v4; // rcx
  _BYTE *v5; // rax

  FltReleaseContext(Entry[24]);
  v2 = Entry[20];
  if ( v2 )
    ExFreePoolWithTag(v2, 0x72744C46u);
  v3 = Entry[18];
  if ( v3 )
    ExFreePoolWithTag(v3, 0x72744C46u);
  v4 = Entry[22];
  if ( v4 )
    ExFreePoolWithTag(v4, 0x72744C46u);
  v5 = Entry[10];
  if ( v5 )
  {
    if ( *v5 == 1 )
      ExFreePoolWithTag(Entry[10], 0x72744C46u);
    else
      ExFreeToNPagedLookasideList(&Lookaside, Entry[10]);
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved, Entry);
}

```

## disassembly

```asm
0x14000292c  push    rbx
0x14000292e  sub     rsp, 20h
0x140002932  mov     rbx, rcx
0x140002935  mov     rcx, [rcx+0C0h]; Context
0x14000293c  call    cs:__imp_FltReleaseContext
0x140002943  nop     dword ptr [rax+rax+00h]
0x140002948  mov     rcx, [rbx+0A0h]; P
0x14000294f  test    rcx, rcx
0x140002952  jz      short loc_140002965
0x140002954  mov     edx, 72744C46h; Tag
0x140002959  call    cs:__imp_ExFreePoolWithTag
0x140002960  nop     dword ptr [rax+rax+00h]
0x140002965  mov     rcx, [rbx+90h]; P
0x14000296c  test    rcx, rcx
0x14000296f  jz      short loc_140002982
0x140002971  mov     edx, 72744C46h; Tag
0x140002976  call    cs:__imp_ExFreePoolWithTag
0x14000297d  nop     dword ptr [rax+rax+00h]
0x140002982  mov     rcx, [rbx+0B0h]; P
0x140002989  test    rcx, rcx
0x14000298c  jz      short loc_14000299F
0x14000298e  mov     edx, 72744C46h; Tag
0x140002993  call    cs:__imp_ExFreePoolWithTag
0x14000299a  nop     dword ptr [rax+rax+00h]
0x14000299f  mov     rax, [rbx+50h]
0x1400029a3  test    rax, rax
0x1400029a6  jz      short loc_1400029D9
0x1400029a8  cmp     byte ptr [rax], 1
0x1400029ab  jnz     short loc_1400029C3
0x1400029ad  mov     edx, 72744C46h; Tag
0x1400029b2  mov     rcx, rax; P
0x1400029b5  call    cs:__imp_ExFreePoolWithTag
0x1400029bc  nop     dword ptr [rax+rax+00h]
0x1400029c1  jmp     short loc_1400029D9
0x1400029c3  mov     rdx, rax; Entry
0x1400029c6  lea     rcx, Lookaside; Lookaside
0x1400029cd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400029d4  nop     dword ptr [rax+rax+00h]
0x1400029d9  mov     rdx, rbx; Entry
0x1400029dc  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x1400029e3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400029ea  nop     dword ptr [rax+rax+00h]
0x1400029ef  add     rsp, 20h
0x1400029f3  pop     rbx
0x1400029f4  retn
```
