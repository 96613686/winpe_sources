# ndisPplDestroyPool(PPL_POOL_HANDLE__ *,ulong)

- ea: `0x140068ce0`
- end: `0x140068db9`
- name: `?ndisPplDestroyPool@@YAXPEAUPPL_POOL_HANDLE__@@K@Z`
- size: `217`
- prototype: `void __fastcall(PVOID P, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140068be0`
- `0x140083810`

## callees

- `0x140068ce0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x140068da8`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140068da8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068d40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068d40`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140068d6a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140068d91`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140068d6a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140068d91`

## pseudocode

```c
void __fastcall ndisPplDestroyPool(char *P)
{
  char *v2; // rbx
  unsigned int v3; // esi
  unsigned int i; // edi
  PSLIST_ENTRY j; // rcx

  if ( P )
  {
    v2 = P + 128;
    v3 = ndisMaxNumberOfProcessors + 1;
    if ( ndisMaxNumberOfProcessors <= 1 )
      v3 = ndisMaxNumberOfProcessors;
    for ( i = 0; i < v3; v2 += 256 )
    {
      if ( v2[216] )
      {
        for ( j = ExpInterlockedPopEntrySList((PSLIST_HEADER)v2 + 8);
              j;
              j = ExpInterlockedPopEntrySList((PSLIST_HEADER)v2 + 8) )
        {
          (*((void (__fastcall **)(PSLIST_ENTRY, char *))v2 + 7))(j, v2);
        }
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)v2);
      }
      ++i;
    }
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140068ce0  test    rcx, rcx
0x140068ce3  jz      short locret_140068D61
0x140068ce5  push    r14
0x140068ce7  sub     rsp, 20h
0x140068ceb  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x140068cf1  mov     r14, rcx
0x140068cf4  mov     [rsp+28h+arg_0], rbx
0x140068cf9  cmp     eax, 1
0x140068cfc  mov     [rsp+28h+arg_10], rsi
0x140068d01  lea     rbx, [rcx+80h]
0x140068d08  mov     [rsp+28h+arg_18], rdi
0x140068d0d  lea     esi, [rax+1]
0x140068d10  cmovbe  esi, eax
0x140068d13  xor     edi, edi
0x140068d15  test    esi, esi
0x140068d17  jz      short loc_140068D3B
0x140068d19  mov     [rsp+28h+arg_8], rbp
0x140068d1e  xchg    ax, ax
0x140068d20  cmp     byte ptr [rbx+0D8h], 0
0x140068d27  jnz     short loc_140068D63
0x140068d29  inc     edi
0x140068d2b  add     rbx, 100h
0x140068d32  cmp     edi, esi
0x140068d34  jb      short loc_140068D20
0x140068d36  mov     rbp, [rsp+28h+arg_8]
0x140068d3b  xor     edx, edx; Tag
0x140068d3d  mov     rcx, r14; P
0x140068d40  call    cs:__imp_ExFreePoolWithTag
0x140068d47  nop     dword ptr [rax+rax+00h]
0x140068d4c  mov     rdi, [rsp+28h+arg_18]
0x140068d51  mov     rsi, [rsp+28h+arg_10]
0x140068d56  mov     rbx, [rsp+28h+arg_0]
0x140068d5b  add     rsp, 20h
0x140068d5f  pop     r14
0x140068d61  retn
0x140068d63  lea     rcx, [rbx+80h]; ListHead
0x140068d6a  call    cs:__imp_ExpInterlockedPopEntrySList
0x140068d71  nop     dword ptr [rax+rax+00h]
0x140068d76  mov     rcx, rax
0x140068d79  test    rax, rax
0x140068d7c  jz      short loc_140068DA5
0x140068d7e  mov     rax, [rbx+38h]
0x140068d82  mov     rdx, rbx
0x140068d85  call    _guard_dispatch_icall
0x140068d8a  lea     rcx, [rbx+80h]; ListHead
0x140068d91  call    cs:__imp_ExpInterlockedPopEntrySList
0x140068d98  nop     dword ptr [rax+rax+00h]
0x140068d9d  mov     rcx, rax
0x140068da0  test    rax, rax
0x140068da3  jnz     short loc_140068D7E
0x140068da5  mov     rcx, rbx; Lookaside
0x140068da8  call    cs:__imp_ExDeleteLookasideListEx
0x140068daf  nop     dword ptr [rax+rax+00h]
0x140068db4  jmp     loc_140068D29
```
