# FltpFreeFrameLookasideLists

- ea: `0x18004c570`
- end: `0x18004c684`
- name: `FltpFreeFrameLookasideLists`
- size: `276`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18004c4d0`

## callees

- `0x18004c570`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18004c672`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004c672`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c5c5`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c5f0`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c632`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c641`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c5c5`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c5f0`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c632`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004c641`

## pseudocode

```c
void __fastcall FltpFreeFrameLookasideLists(__int64 a1)
{
  unsigned int v2; // ecx
  unsigned int v3; // r14d
  struct _NPAGED_LOOKASIDE_LIST *v4; // rsi
  unsigned __int64 v5; // r15
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rdi
  void *v8; // rcx

  v2 = dword_18003E760;
  v3 = 0;
  if ( dword_18003E760 )
  {
    do
    {
      v4 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1024);
      v5 = *(_QWORD *)(a1 + 680) + ((unsigned __int64)(v3 % v2) << 6);
      if ( *(_QWORD *)v5 != a1 + 1024 )
      {
        ExDeleteNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v5);
        *(_QWORD *)(v5 + 8) = 0;
        *(_QWORD *)v5 = 0;
      }
      v6 = *(struct _NPAGED_LOOKASIDE_LIST **)(v5 + 16);
      v7 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1152);
      if ( v6 != (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1152) )
      {
        ExDeleteNPagedLookasideList(v6);
        *(_QWORD *)(v5 + 24) = 0;
        *(_QWORD *)(v5 + 16) = 0;
      }
      v2 = dword_18003E760;
      ++v3;
    }
    while ( v3 < dword_18003E760 );
  }
  else
  {
    v4 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1024);
    v7 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1152);
  }
  ExDeleteNPagedLookasideList(v4);
  ExDeleteNPagedLookasideList(v7);
  v8 = *(void **)(a1 + 696);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x616C4D46u);
}

```

## disassembly

```asm
0x18004c570  sub     rsp, 28h
0x18004c574  mov     [rsp+28h+arg_0], rbx
0x18004c579  mov     rbx, rcx
0x18004c57c  mov     ecx, cs:dword_18003E760
0x18004c582  mov     [rsp+28h+arg_8], rsi
0x18004c587  mov     [rsp+28h+arg_10], rdi
0x18004c58c  mov     [rsp+28h+arg_18], r14
0x18004c591  xor     r14d, r14d
0x18004c594  test    ecx, ecx
0x18004c596  jz      loc_18004C621
0x18004c59c  mov     [rsp+28h+var_8], r15
0x18004c5a1  xor     edx, edx
0x18004c5a3  lea     rsi, [rbx+400h]
0x18004c5aa  mov     eax, r14d
0x18004c5ad  div     ecx
0x18004c5af  mov     r15d, edx
0x18004c5b2  shl     r15, 6
0x18004c5b6  add     r15, [rbx+2A8h]
0x18004c5bd  mov     rcx, [r15]; Lookaside
0x18004c5c0  cmp     rcx, rsi
0x18004c5c3  jz      short loc_18004C5E0
0x18004c5c5  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004c5cc  nop     dword ptr [rax+rax+00h]
0x18004c5d1  mov     qword ptr [r15+8], 0
0x18004c5d9  mov     qword ptr [r15], 0
0x18004c5e0  mov     rcx, [r15+10h]; Lookaside
0x18004c5e4  lea     rdi, [rbx+480h]
0x18004c5eb  cmp     rcx, rdi
0x18004c5ee  jz      short loc_18004C60C
0x18004c5f0  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004c5f7  nop     dword ptr [rax+rax+00h]
0x18004c5fc  mov     qword ptr [r15+18h], 0
0x18004c604  mov     qword ptr [r15+10h], 0
0x18004c60c  mov     ecx, cs:dword_18003E760
0x18004c612  inc     r14d
0x18004c615  cmp     r14d, ecx
0x18004c618  jb      short loc_18004C5A1
0x18004c61a  mov     r15, [rsp+28h+var_8]
0x18004c61f  jmp     short loc_18004C62F
0x18004c621  lea     rsi, [rbx+400h]
0x18004c628  lea     rdi, [rbx+480h]
0x18004c62f  mov     rcx, rsi; Lookaside
0x18004c632  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004c639  nop     dword ptr [rax+rax+00h]
0x18004c63e  mov     rcx, rdi; Lookaside
0x18004c641  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004c648  nop     dword ptr [rax+rax+00h]
0x18004c64d  mov     rcx, [rbx+2B8h]; P
0x18004c654  mov     r14, [rsp+28h+arg_18]
0x18004c659  mov     rdi, [rsp+28h+arg_10]
0x18004c65e  mov     rsi, [rsp+28h+arg_8]
0x18004c663  mov     rbx, [rsp+28h+arg_0]
0x18004c668  test    rcx, rcx
0x18004c66b  jz      short loc_18004C67E
0x18004c66d  mov     edx, 616C4D46h; Tag
0x18004c672  call    cs:__imp_ExFreePoolWithTag
0x18004c679  nop     dword ptr [rax+rax+00h]
0x18004c67e  add     rsp, 28h
0x18004c682  retn
```
