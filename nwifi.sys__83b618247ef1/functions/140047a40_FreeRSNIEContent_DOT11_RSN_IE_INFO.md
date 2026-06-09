# FreeRSNIEContent(DOT11_RSN_IE_INFO *)

- ea: `0x140047a40`
- end: `0x140047b38`
- name: `?FreeRSNIEContent@@YAXPEAUDOT11_RSN_IE_INFO@@@Z`
- size: `248`
- prototype: `void __fastcall(struct DOT11_RSN_IE_INFO *)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003a5f4`
- `0x140040f40`
- `0x14004113c`
- `0x14004967c`
- `0x14004a0bc`
- `0x14004a7fc`
- `0x14004bd60`
- `0x140051d54`

## callees

- `0x140047a40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047a73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047ac0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047b06`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047a73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047ac0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047b06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047ad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047ad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b17`

## pseudocode

```c
void __fastcall FreeRSNIEContent(struct DOT11_RSN_IE_INFO *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  bool v4; // cc
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  if ( a1 )
  {
    if ( *((_WORD *)a1 + 12) > 1u )
    {
      v2 = *((_QWORD *)a1 + 4);
      if ( v2 )
      {
        v3 = v2 - 16;
        if ( *(_QWORD *)v3 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v3, (PVOID)v3);
        else
          ExFreePoolWithTag((PVOID)v3, *(_DWORD *)(v3 + 8));
        *((_QWORD *)a1 + 4) = 0;
      }
    }
    v4 = *((_WORD *)a1 + 4) <= 1u;
    *((_WORD *)a1 + 12) = 0;
    if ( !v4 )
    {
      v5 = *((_QWORD *)a1 + 2);
      if ( v5 )
      {
        v6 = v5 - 16;
        if ( *(_QWORD *)v6 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, (PVOID)v6);
        else
          ExFreePoolWithTag((PVOID)v6, *(_DWORD *)(v6 + 8));
        *((_QWORD *)a1 + 2) = 0;
      }
    }
    v7 = *((_QWORD *)a1 + 6);
    *((_WORD *)a1 + 4) = 0;
    if ( v7 )
    {
      v8 = v7 - 16;
      if ( *(_QWORD *)v8 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
      else
        ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
      *((_QWORD *)a1 + 6) = 0;
    }
    *((_WORD *)a1 + 21) = 0;
  }
}

```

## disassembly

```asm
0x140047a40  test    rcx, rcx
0x140047a43  jz      locret_140047B36
0x140047a49  push    rbx
0x140047a4a  sub     rsp, 20h
0x140047a4e  cmp     word ptr [rcx+18h], 1
0x140047a53  mov     rbx, rcx
0x140047a56  jbe     short loc_140047A98
0x140047a58  mov     rcx, [rcx+20h]
0x140047a5c  test    rcx, rcx
0x140047a5f  jz      short loc_140047A98
0x140047a61  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047a65  mov     rax, [rcx]
0x140047a68  test    rax, rax
0x140047a6b  jz      short loc_140047A81
0x140047a6d  mov     rdx, rcx; Entry
0x140047a70  mov     rcx, rax; Lookaside
0x140047a73  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047a7a  nop     dword ptr [rax+rax+00h]
0x140047a7f  jmp     short loc_140047A90
0x140047a81  mov     edx, [rcx+8]; Tag
0x140047a84  call    cs:__imp_ExFreePoolWithTag
0x140047a8b  nop     dword ptr [rax+rax+00h]
0x140047a90  mov     qword ptr [rbx+20h], 0
0x140047a98  xor     eax, eax
0x140047a9a  cmp     word ptr [rbx+8], 1
0x140047a9f  mov     [rbx+18h], ax
0x140047aa3  jbe     short loc_140047AE5
0x140047aa5  mov     rcx, [rbx+10h]
0x140047aa9  test    rcx, rcx
0x140047aac  jz      short loc_140047AE5
0x140047aae  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047ab2  mov     rax, [rcx]
0x140047ab5  test    rax, rax
0x140047ab8  jz      short loc_140047ACE
0x140047aba  mov     rdx, rcx; Entry
0x140047abd  mov     rcx, rax; Lookaside
0x140047ac0  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047ac7  nop     dword ptr [rax+rax+00h]
0x140047acc  jmp     short loc_140047ADD
0x140047ace  mov     edx, [rcx+8]; Tag
0x140047ad1  call    cs:__imp_ExFreePoolWithTag
0x140047ad8  nop     dword ptr [rax+rax+00h]
0x140047add  mov     qword ptr [rbx+10h], 0
0x140047ae5  mov     rcx, [rbx+30h]
0x140047ae9  xor     eax, eax
0x140047aeb  mov     [rbx+8], ax
0x140047aef  test    rcx, rcx
0x140047af2  jz      short loc_140047B2B
0x140047af4  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047af8  mov     rax, [rcx]
0x140047afb  test    rax, rax
0x140047afe  jz      short loc_140047B14
0x140047b00  mov     rdx, rcx; Entry
0x140047b03  mov     rcx, rax; Lookaside
0x140047b06  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047b0d  nop     dword ptr [rax+rax+00h]
0x140047b12  jmp     short loc_140047B23
0x140047b14  mov     edx, [rcx+8]; Tag
0x140047b17  call    cs:__imp_ExFreePoolWithTag
0x140047b1e  nop     dword ptr [rax+rax+00h]
0x140047b23  mov     qword ptr [rbx+30h], 0
0x140047b2b  xor     eax, eax
0x140047b2d  mov     [rbx+2Ah], ax
0x140047b31  add     rsp, 20h
0x140047b35  pop     rbx
0x140047b36  retn
```
