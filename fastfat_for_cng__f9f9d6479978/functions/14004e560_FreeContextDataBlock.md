# FreeContextDataBlock

- ea: `0x14004e560`
- end: `0x14004e609`
- name: `FreeContextDataBlock`
- size: `169`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140007960`
- `0x14004ee40`
- `0x14004eff0`
- `0x1400528bc`
- `0x140053c18`
- `0x140055380`

## callees

- `0x14004e560`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e5d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e5d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e5ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e5ea`
- `ksecdd!BCryptDestroyKey` at `0x14004e5ab`
- `ksecdd!BCryptDestroyKey` at `0x14004e5ab`

## pseudocode

```c
void __fastcall FreeContextDataBlock(PVOID *a1)
{
  unsigned int *v2; // rbx
  unsigned int v3; // eax
  char *v4; // rcx
  _BYTE *v5; // rcx
  __int64 v6; // rax

  v2 = *(unsigned int **)*a1;
  if ( v2 )
  {
    v3 = v2[1];
    if ( (v3 == 26126 || v3 == 26128 || v3 == 536897040 || v3 == 1073767952) && v2[20] == 1 )
    {
      v4 = (char *)*((_QWORD *)v2 + 11);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        BCryptDestroyKey(v4);
    }
    v5 = v2 + 20;
    v6 = *v2 - 87LL;
    if ( *v2 != 87 )
    {
      do
      {
        *v5++ = 0;
        --v6;
      }
      while ( v6 );
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v2 + 9), v2);
  }
  ExFreePoolWithTag(*a1, 0x6D736645u);
  *a1 = 0;
}

```

## disassembly

```asm
0x14004e560  mov     [rsp+arg_0], rbx
0x14004e565  push    rdi
0x14004e566  sub     rsp, 20h
0x14004e56a  mov     rax, [rcx]
0x14004e56d  mov     rdi, rcx
0x14004e570  mov     rbx, [rax]
0x14004e573  test    rbx, rbx
0x14004e576  jz      short loc_14004E5E2
0x14004e578  mov     eax, [rbx+4]
0x14004e57b  cmp     eax, 660Eh
0x14004e580  jz      short loc_14004E597
0x14004e582  cmp     eax, 6610h
0x14004e587  jz      short loc_14004E597
0x14004e589  cmp     eax, 20006610h
0x14004e58e  jz      short loc_14004E597
0x14004e590  cmp     eax, 40006610h
0x14004e595  jnz     short loc_14004E5B7
0x14004e597  cmp     dword ptr [rbx+50h], 1
0x14004e59b  jnz     short loc_14004E5B7
0x14004e59d  mov     rcx, [rbx+58h]; hKey
0x14004e5a1  lea     rax, [rcx-1]
0x14004e5a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004e5a9  ja      short loc_14004E5B7
0x14004e5ab  call    cs:__imp_BCryptDestroyKey
0x14004e5b2  nop     dword ptr [rax+rax+00h]
0x14004e5b7  mov     eax, [rbx]
0x14004e5b9  lea     rcx, [rbx+50h]
0x14004e5bd  sub     rax, 57h ; 'W'
0x14004e5c1  jz      short loc_14004E5CF
0x14004e5c3  mov     byte ptr [rcx], 0
0x14004e5c6  inc     rcx
0x14004e5c9  sub     rax, 1
0x14004e5cd  jnz     short loc_14004E5C3
0x14004e5cf  mov     rcx, [rbx+48h]; Lookaside
0x14004e5d3  mov     rdx, rbx; Entry
0x14004e5d6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004e5dd  nop     dword ptr [rax+rax+00h]
0x14004e5e2  mov     rcx, [rdi]; P
0x14004e5e5  mov     edx, 6D736645h; Tag
0x14004e5ea  call    cs:__imp_ExFreePoolWithTag
0x14004e5f1  nop     dword ptr [rax+rax+00h]
0x14004e5f6  mov     rbx, [rsp+28h+arg_0]
0x14004e5fb  mov     qword ptr [rdi], 0
0x14004e602  add     rsp, 20h
0x14004e606  pop     rdi
0x14004e607  retn
```
