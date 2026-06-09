# DoubleList::RemoveEntry(ListEntry *)

- ea: `0x140002564`
- end: `0x1400025a5`
- name: `?RemoveEntry@DoubleList@@QEAAXPEAVListEntry@@@Z`
- size: `65`
- prototype: `void __fastcall(DoubleList *__hidden this, struct ListEntry *)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001d504`
- `0x14001dafc`
- `0x14001dcb4`
- `0x14001fbd8`
- `0x14001fd20`
- `0x14002ac20`
- `0x14002be98`
- `0x14002c940`

## callees

- `0x140002564`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000258c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000258c`

## pseudocode

```c
void __fastcall DoubleList::RemoveEntry(DoubleList *this, struct ListEntry ***a2)
{
  struct ListEntry **v2; // rcx
  struct ListEntry **v3; // rax

  v2 = *a2;
  if ( (*a2)[1] != (struct ListEntry *)a2 || (v3 = a2[1], *v3 != (struct ListEntry *)a2) )
    __fastfail(3u);
  *v3 = (struct ListEntry *)v2;
  v2[1] = (struct ListEntry *)v3;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)WPP_MAIN_CB.Dpc.SystemArgument1 + 64), a2);
}

```

## disassembly

```asm
0x140002564  sub     rsp, 28h
0x140002568  mov     rcx, [rdx]
0x14000256b  cmp     [rcx+8], rdx
0x14000256f  jnz     short loc_14000259E
0x140002571  mov     rax, [rdx+8]
0x140002575  cmp     [rax], rdx
0x140002578  jnz     short loc_14000259E
0x14000257a  mov     [rax], rcx
0x14000257d  mov     [rcx+8], rax
0x140002581  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x140002588  add     rcx, 40h ; '@'; Lookaside
0x14000258c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002593  nop     dword ptr [rax+rax+00h]
0x140002598  add     rsp, 28h
0x14000259c  retn
0x14000259e  mov     ecx, 3
0x1400025a3  int     29h; Win8: RtlFailFast(ecx)
```
