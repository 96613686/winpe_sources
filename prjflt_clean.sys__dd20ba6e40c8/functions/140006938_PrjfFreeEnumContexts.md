# PrjfFreeEnumContexts

- ea: `0x140006938`
- end: `0x14000699d`
- name: `PrjfFreeEnumContexts`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400211e0`
- `0x140024b24`
- `0x140028760`

## callees

- `0x140006938`
- `0x14003a644`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000697c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000697c`

## pseudocode

```c
void __fastcall PrjfFreeEnumContexts(void **a1)
{
  PVOID *v2; // rbx
  PVOID v3; // rcx
  void **v4; // rax

  while ( 1 )
  {
    v2 = (PVOID *)*a1;
    if ( *a1 == a1 )
      break;
    PrjfFreeEnumerationResultBuffer(v2[8]);
    v3 = *v2;
    if ( *((PVOID **)*v2 + 1) != v2 || (v4 = (void **)v2[1], *v4 != v2) )
      __fastfail(3u);
    *v4 = v3;
    *((_QWORD *)v3 + 1) = v4;
    ExFreeToPagedLookasideList(&stru_14001A8C0, v2);
  }
}

```

## disassembly

```asm
0x140006938  mov     [rsp+arg_0], rbx
0x14000693d  push    rdi
0x14000693e  sub     rsp, 20h
0x140006942  mov     rdi, rcx
0x140006945  mov     rbx, [rdi]
0x140006948  cmp     rbx, rdi
0x14000694b  jz      short loc_140006991
0x14000694d  mov     edx, [rbx+38h]
0x140006950  mov     rcx, [rbx+40h]; Entry
0x140006954  call    PrjfFreeEnumerationResultBuffer
0x140006959  mov     rcx, [rbx]
0x14000695c  cmp     [rcx+8], rbx
0x140006960  jnz     short loc_14000698A
0x140006962  mov     rax, [rbx+8]
0x140006966  cmp     [rax], rbx
0x140006969  jnz     short loc_14000698A
0x14000696b  mov     [rax], rcx
0x14000696e  mov     rdx, rbx; Entry
0x140006971  mov     [rcx+8], rax
0x140006975  lea     rcx, stru_14001A8C0; Lookaside
0x14000697c  call    cs:__imp_ExFreeToPagedLookasideList
0x140006983  nop     dword ptr [rax+rax+00h]
0x140006988  jmp     short loc_140006945
0x14000698a  mov     ecx, 3
0x14000698f  int     29h; Win8: RtlFailFast(ecx)
0x140006991  mov     rbx, [rsp+28h+arg_0]
0x140006996  add     rsp, 20h
0x14000699a  pop     rdi
0x14000699b  retn
```
