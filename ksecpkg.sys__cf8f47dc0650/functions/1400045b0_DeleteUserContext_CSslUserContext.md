# DeleteUserContext(CSslUserContext *)

- ea: `0x1400045b0`
- end: `0x14000471b`
- name: `?DeleteUserContext@@YAXPEAUCSslUserContext@@@Z`
- size: `363`
- prototype: `void __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140002410`
- `0x14002f880`
- `0x14002fd60`

## callees

- `0x1400045b0`
- `0x140010240`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004626`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004626`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400046a7`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400046a7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140004705`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140004705`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000460e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000460e`
- `ntoskrnl!ExAllocatePool2` at `0x140004673`
- `ntoskrnl!ExAllocatePool2` at `0x1400046ca`
- `ntoskrnl!ExAllocatePool2` at `0x140004673`
- `ntoskrnl!ExAllocatePool2` at `0x1400046ca`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400045f1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400045f1`

## pseudocode

```c
void __fastcall DeleteUserContext(_DWORD *Entry)
{
  int v1; // esi
  struct _PAGED_LOOKASIDE_LIST *Pool2; // rdi

  v1 = Entry[106];
  (**(void (__fastcall ***)(_DWORD *, _QWORD))Entry)(Entry, 0);
  if ( !g_pSchannelPagedSlist && _InterlockedIncrement(&g_lSchannelDeserializeCount) == 10 )
  {
    g_dwLookasideLen = g_dwMaxContextLength;
    Pool2 = (struct _PAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 1131180883);
    ExInitializePagedLookasideList(Pool2, 0, 0, 0, (unsigned int)g_dwMaxContextLength, 0x436C7353u, 0);
    g_pSchannelPagedSlist = Pool2;
    g_pSchannelNonPagedSlist = (PNPAGED_LOOKASIDE_LIST)ExAllocatePool2(64, 128, 1131180883);
    ExInitializeNPagedLookasideList(
      g_pSchannelNonPagedSlist,
      0,
      0,
      0x200u,
      (unsigned int)g_dwMaxContextLength,
      0x436C7353u,
      0);
  }
  if ( v1 == 512 )
  {
    ExFreeToNPagedLookasideList(g_pSchannelNonPagedSlist, Entry);
  }
  else if ( v1 == 1 )
  {
    ExFreeToPagedLookasideList(g_pSchannelPagedSlist, Entry);
  }
  else
  {
    ExFreePoolWithTag(Entry, 0);
  }
}

```

## disassembly

```asm
0x1400045b0  mov     [rsp+arg_8], rbx
0x1400045b5  push    rsi
0x1400045b6  sub     rsp, 40h
0x1400045ba  mov     rax, [rcx]
0x1400045bd  xor     edx, edx
0x1400045bf  mov     esi, [rcx+1A8h]
0x1400045c5  mov     rbx, rcx
0x1400045c8  mov     rax, [rax]
0x1400045cb  call    _guard_dispatch_icall
0x1400045d0  cmp     cs:?g_pSchannelPagedSlist@@3PEAU_PAGED_LOOKASIDE_LIST@@EA, 0; _PAGED_LOOKASIDE_LIST * g_pSchannelPagedSlist
0x1400045d8  jz      short loc_14000463E
0x1400045da  cmp     esi, 200h
0x1400045e0  jz      short loc_14000461C
0x1400045e2  cmp     esi, 1
0x1400045e5  jnz     short loc_140004609
0x1400045e7  mov     rcx, cs:?g_pSchannelPagedSlist@@3PEAU_PAGED_LOOKASIDE_LIST@@EA; Lookaside
0x1400045ee  mov     rdx, rbx; Entry
0x1400045f1  call    cs:__imp_ExFreeToPagedLookasideList
0x1400045f8  nop     dword ptr [rax+rax+00h]
0x1400045fd  mov     rbx, [rsp+48h+arg_8]
0x140004602  add     rsp, 40h
0x140004606  pop     rsi
0x140004607  retn
0x140004609  xor     edx, edx; Tag
0x14000460b  mov     rcx, rbx; P
0x14000460e  call    cs:__imp_ExFreePoolWithTag
0x140004615  nop     dword ptr [rax+rax+00h]
0x14000461a  jmp     short loc_1400045FD
0x14000461c  mov     rcx, cs:?g_pSchannelNonPagedSlist@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; Lookaside
0x140004623  mov     rdx, rbx; Entry
0x140004626  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000462d  nop     dword ptr [rax+rax+00h]
0x140004632  mov     rbx, [rsp+48h+arg_8]
0x140004637  add     rsp, 40h
0x14000463b  pop     rsi
0x14000463c  retn
0x14000463e  mov     eax, 1
0x140004643  lock xadd cs:?g_lSchannelDeserializeCount@@3JA, eax; long g_lSchannelDeserializeCount
0x14000464b  inc     eax
0x14000464d  cmp     eax, 0Ah
0x140004650  jnz     short loc_1400045DA
0x140004652  mov     eax, cs:?g_dwMaxContextLength@@3KA; ulong g_dwMaxContextLength
0x140004658  mov     edx, 80h
0x14000465d  mov     ecx, 40h ; '@'
0x140004662  mov     cs:?g_dwLookasideLen@@3KA, eax; ulong g_dwLookasideLen
0x140004668  mov     r8d, 436C7353h
0x14000466e  mov     [rsp+48h+arg_0], rdi
0x140004673  call    cs:__imp_ExAllocatePool2
0x14000467a  nop     dword ptr [rax+rax+00h]
0x14000467f  mov     r9d, cs:?g_dwMaxContextLength@@3KA; ulong g_dwMaxContextLength
0x140004686  xor     r8d, r8d; Free
0x140004689  mov     [rsp+48h+Depth], r8w; Depth
0x14000468f  xor     edx, edx; Allocate
0x140004691  mov     [rsp+48h+Tag], 436C7353h; Tag
0x140004699  mov     rcx, rax; Lookaside
0x14000469c  mov     [rsp+48h+Size], r9; Size
0x1400046a1  mov     rdi, rax
0x1400046a4  xor     r9d, r9d; Flags
0x1400046a7  call    cs:__imp_ExInitializePagedLookasideList
0x1400046ae  nop     dword ptr [rax+rax+00h]
0x1400046b3  mov     edx, 80h
0x1400046b8  mov     cs:?g_pSchannelPagedSlist@@3PEAU_PAGED_LOOKASIDE_LIST@@EA, rdi; _PAGED_LOOKASIDE_LIST * g_pSchannelPagedSlist
0x1400046bf  mov     ecx, 40h ; '@'
0x1400046c4  mov     r8d, 436C7353h
0x1400046ca  call    cs:__imp_ExAllocatePool2
0x1400046d1  nop     dword ptr [rax+rax+00h]
0x1400046d6  mov     edx, cs:?g_dwMaxContextLength@@3KA; ulong g_dwMaxContextLength
0x1400046dc  xor     ecx, ecx
0x1400046de  mov     [rsp+48h+Depth], cx; Depth
0x1400046e3  mov     r9d, 200h; Flags
0x1400046e9  mov     [rsp+48h+Tag], 436C7353h; Tag
0x1400046f1  xor     r8d, r8d; Free
0x1400046f4  mov     [rsp+48h+Size], rdx; Size
0x1400046f9  mov     rcx, rax; Lookaside
0x1400046fc  xor     edx, edx; Allocate
0x1400046fe  mov     cs:?g_pSchannelNonPagedSlist@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA, rax; _NPAGED_LOOKASIDE_LIST * g_pSchannelNonPagedSlist
0x140004705  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000470c  nop     dword ptr [rax+rax+00h]
0x140004711  mov     rdi, [rsp+48h+arg_0]
0x140004716  jmp     loc_1400045DA
```
