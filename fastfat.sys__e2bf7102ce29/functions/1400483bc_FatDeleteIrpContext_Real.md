# FatDeleteIrpContext_Real

- ea: `0x1400483bc`
- end: `0x14004841b`
- name: `FatDeleteIrpContext_Real`
- size: `95`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140038eb4`
- `0x14003960c`
- `0x14004573c`
- `0x14004af08`

## callees

- `0x1400483bc`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400483e0`
- `ntoskrnl!IoFreeMdl` at `0x1400483e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048408`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048408`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400483f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400483f2`

## pseudocode

```c
void __fastcall FatDeleteIrpContext_Real(PVOID Entry)
{
  __int64 v2; // rcx
  struct _MDL *v3; // rcx

  v2 = *((_QWORD *)Entry + 10);
  if ( v2 && (*((_DWORD *)Entry + 17) & 0x100) == 0 )
  {
    v3 = *(struct _MDL **)(v2 + 16);
    if ( v3 )
      IoFreeMdl(v3);
    ExFreePoolWithTag(*((PVOID *)Entry + 10), 0);
  }
  ExFreeToNPagedLookasideList(&FatIrpContextLookasideList, Entry);
}

```

## disassembly

```asm
0x1400483bc  push    rbx
0x1400483be  sub     rsp, 20h
0x1400483c2  mov     rbx, rcx
0x1400483c5  mov     rcx, [rcx+50h]
0x1400483c9  test    rcx, rcx
0x1400483cc  jz      short loc_1400483FE
0x1400483ce  test    dword ptr [rbx+44h], 100h
0x1400483d5  jnz     short loc_1400483FE
0x1400483d7  mov     rcx, [rcx+10h]; Mdl
0x1400483db  test    rcx, rcx
0x1400483de  jz      short loc_1400483EC
0x1400483e0  call    cs:__imp_IoFreeMdl
0x1400483e7  nop     dword ptr [rax+rax+00h]
0x1400483ec  mov     rcx, [rbx+50h]; P
0x1400483f0  xor     edx, edx; Tag
0x1400483f2  call    cs:__imp_ExFreePoolWithTag
0x1400483f9  nop     dword ptr [rax+rax+00h]
0x1400483fe  mov     rdx, rbx; Entry
0x140048401  lea     rcx, FatIrpContextLookasideList; Lookaside
0x140048408  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004840f  nop     dword ptr [rax+rax+00h]
0x140048414  add     rsp, 20h
0x140048418  pop     rbx
0x140048419  retn
```
