# ndisPplDestroyPool(PPL_POOL_HANDLE__ *,ulong)

- ea: `0x14006e340`
- end: `0x14006e419`
- name: `?ndisPplDestroyPool@@YAXPEAUPPL_POOL_HANDLE__@@K@Z`
- size: `217`
- prototype: `void __fastcall(PVOID P, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14006e240`
- `0x140088a90`

## callees

- `0x14006e340`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14006e408`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14006e408`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e3a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e3a0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e3ca`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e3f1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e3ca`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e3f1`

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
0x14006e340  test    rcx, rcx
0x14006e343  jz      short locret_14006E3C1
0x14006e345  push    r14
0x14006e347  sub     rsp, 20h
0x14006e34b  mov     eax, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14006e351  mov     r14, rcx
0x14006e354  mov     [rsp+28h+arg_0], rbx
0x14006e359  cmp     eax, 1
0x14006e35c  mov     [rsp+28h+arg_10], rsi
0x14006e361  lea     rbx, [rcx+80h]
0x14006e368  mov     [rsp+28h+arg_18], rdi
0x14006e36d  lea     esi, [rax+1]
0x14006e370  cmovbe  esi, eax
0x14006e373  xor     edi, edi
0x14006e375  test    esi, esi
0x14006e377  jz      short loc_14006E39B
0x14006e379  mov     [rsp+28h+arg_8], rbp
0x14006e37e  xchg    ax, ax
0x14006e380  cmp     byte ptr [rbx+0D8h], 0
0x14006e387  jnz     short loc_14006E3C3
0x14006e389  inc     edi
0x14006e38b  add     rbx, 100h
0x14006e392  cmp     edi, esi
0x14006e394  jb      short loc_14006E380
0x14006e396  mov     rbp, [rsp+28h+arg_8]
0x14006e39b  xor     edx, edx; Tag
0x14006e39d  mov     rcx, r14; P
0x14006e3a0  call    cs:__imp_ExFreePoolWithTag
0x14006e3a7  nop     dword ptr [rax+rax+00h]
0x14006e3ac  mov     rdi, [rsp+28h+arg_18]
0x14006e3b1  mov     rsi, [rsp+28h+arg_10]
0x14006e3b6  mov     rbx, [rsp+28h+arg_0]
0x14006e3bb  add     rsp, 20h
0x14006e3bf  pop     r14
0x14006e3c1  retn
0x14006e3c3  lea     rcx, [rbx+80h]; ListHead
0x14006e3ca  call    cs:__imp_ExpInterlockedPopEntrySList
0x14006e3d1  nop     dword ptr [rax+rax+00h]
0x14006e3d6  mov     rcx, rax
0x14006e3d9  test    rax, rax
0x14006e3dc  jz      short loc_14006E405
0x14006e3de  mov     rax, [rbx+38h]
0x14006e3e2  mov     rdx, rbx
0x14006e3e5  call    _guard_dispatch_icall
0x14006e3ea  lea     rcx, [rbx+80h]; ListHead
0x14006e3f1  call    cs:__imp_ExpInterlockedPopEntrySList
0x14006e3f8  nop     dword ptr [rax+rax+00h]
0x14006e3fd  mov     rcx, rax
0x14006e400  test    rax, rax
0x14006e403  jnz     short loc_14006E3DE
0x14006e405  mov     rcx, rbx; Lookaside
0x14006e408  call    cs:__imp_ExDeleteLookasideListEx
0x14006e40f  nop     dword ptr [rax+rax+00h]
0x14006e414  jmp     loc_14006E389
```
