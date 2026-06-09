# MRxDAVCleanUpTheLockConflictList

- ea: `0x140001188`
- end: `0x140001288`
- name: `MRxDAVCleanUpTheLockConflictList`
- size: `256`
- prototype: `void __fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001290`
- `0x140004950`
- `0x140010168`

## callees

- `0x140001188`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000119c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000119c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000126b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000126b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001233`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000124c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001233`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000124c`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400011c2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400011c2`

## pseudocode

```c
void __fastcall MRxDAVCleanUpTheLockConflictList(int a1)
{
  PVOID **v2; // rbx
  PVOID *v3; // rdi
  ULONG TimeIncrement; // ecx
  PVOID *v5; // rax
  PVOID **v6; // rcx
  PVOID *v7; // rcx

  ExAcquireResourceExclusiveLite(&LockConflictEntryListLock, 1u);
  v2 = (PVOID **)LockConflictEntryList;
  if ( LockConflictEntryList != &LockConflictEntryList )
  {
    do
    {
      v3 = *v2;
      TimeIncrement = KeQueryTimeIncrement();
      if ( a1 || MEMORY[0xFFFFF78000000320] - (_QWORD)v2[4] > 10LL * (0x989680 / TimeIncrement) )
      {
        v5 = *v2;
        if ( (*v2)[1] != v2 || (v6 = (PVOID **)v2[1], *v6 != (PVOID *)v2) )
          __fastfail(3u);
        *v6 = v5;
        v5[1] = v6;
        ExFreePoolWithTag(v2[2], 0);
        v7 = v2[3];
        v2[2] = 0;
        ExFreePoolWithTag(v7, 0);
        v2[3] = 0;
        ExFreePoolWithTag(v2, 0);
      }
      v2 = (PVOID **)v3;
    }
    while ( v3 != &LockConflictEntryList );
  }
  ExReleaseResourceLite(&LockConflictEntryListLock);
}

```

## disassembly

```asm
0x140001188  push    rbx
0x14000118a  push    rbp
0x14000118b  push    rsi
0x14000118c  push    rdi
0x14000118d  sub     rsp, 28h
0x140001191  mov     esi, ecx
0x140001193  mov     dl, 1; Wait
0x140001195  lea     rcx, LockConflictEntryListLock; Resource
0x14000119c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400011a3  nop     dword ptr [rax+rax+00h]
0x1400011a8  mov     rbx, cs:LockConflictEntryList
0x1400011af  lea     rbp, LockConflictEntryList
0x1400011b6  cmp     rbx, rbp
0x1400011b9  jz      loc_140001264
0x1400011bf  mov     rdi, [rbx]
0x1400011c2  call    cs:__imp_KeQueryTimeIncrement
0x1400011c9  nop     dword ptr [rax+rax+00h]
0x1400011ce  mov     r8, 0FFFFF78000000320h
0x1400011d8  mov     ecx, eax
0x1400011da  mov     r8, [r8]
0x1400011dd  test    esi, esi
0x1400011df  jnz     short loc_1400011FA
0x1400011e1  sub     r8, [rbx+20h]
0x1400011e5  xor     edx, edx
0x1400011e7  mov     eax, 989680h
0x1400011ec  div     ecx
0x1400011ee  lea     rax, [rax+rax*4]
0x1400011f2  add     rax, rax
0x1400011f5  cmp     r8, rax
0x1400011f8  jle     short loc_140001258
0x1400011fa  mov     rax, [rbx]
0x1400011fd  cmp     [rax+8], rbx
0x140001201  jnz     short loc_140001281
0x140001203  mov     rcx, [rbx+8]
0x140001207  cmp     [rcx], rbx
0x14000120a  jnz     short loc_140001281
0x14000120c  mov     [rcx], rax
0x14000120f  xor     edx, edx; Tag
0x140001211  mov     [rax+8], rcx
0x140001215  mov     rcx, [rbx+10h]; P
0x140001219  call    cs:__imp_ExFreePoolWithTag
0x140001220  nop     dword ptr [rax+rax+00h]
0x140001225  mov     rcx, [rbx+18h]; P
0x140001229  xor     edx, edx; Tag
0x14000122b  mov     qword ptr [rbx+10h], 0
0x140001233  call    cs:__imp_ExFreePoolWithTag
0x14000123a  nop     dword ptr [rax+rax+00h]
0x14000123f  xor     edx, edx; Tag
0x140001241  mov     qword ptr [rbx+18h], 0
0x140001249  mov     rcx, rbx; P
0x14000124c  call    cs:__imp_ExFreePoolWithTag
0x140001253  nop     dword ptr [rax+rax+00h]
0x140001258  mov     rbx, rdi
0x14000125b  cmp     rdi, rbp
0x14000125e  jnz     loc_1400011BF
0x140001264  lea     rcx, LockConflictEntryListLock; Resource
0x14000126b  call    cs:__imp_ExReleaseResourceLite
0x140001272  nop     dword ptr [rax+rax+00h]
0x140001277  add     rsp, 28h
0x14000127b  pop     rdi
0x14000127c  pop     rsi
0x14000127d  pop     rbp
0x14000127e  pop     rbx
0x14000127f  retn
0x140001281  mov     ecx, 3
0x140001286  int     29h; Win8: RtlFailFast(ecx)
```
