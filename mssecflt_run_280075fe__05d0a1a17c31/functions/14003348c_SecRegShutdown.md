# SecRegShutdown

- ea: `0x14003348c`
- end: `0x1400335b1`
- name: `SecRegShutdown`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002a5e8`

## callees

- `0x140009b80`
- `0x14003348c`
- `0x1400336b4`
- `0x140033b64`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400334b3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400334cd`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400334e7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033501`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003351b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033535`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003354f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033569`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033583`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400334b3`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400334cd`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400334e7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033501`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003351b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033535`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003354f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033569`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140033583`

## pseudocode

```c
void SecRegShutdown()
{
  if ( RegData )
  {
    SecUnregisterRegCallback();
    MpRegpFreeAllCallContextsUnsafe();
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 1);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 2);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 3);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 4);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 5);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 6);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 7);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 8);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)RegData + 9);
    SecFreePool(RegData, 0x64526353u);
    RegData = 0;
  }
}

```

## disassembly

```asm
0x14003348c  sub     rsp, 28h
0x140033490  cmp     cs:RegData, 0
0x140033498  jz      loc_1400335AB
0x14003349e  call    SecUnregisterRegCallback
0x1400334a3  call    MpRegpFreeAllCallContextsUnsafe
0x1400334a8  mov     rcx, cs:RegData
0x1400334af  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400334b3  call    cs:__imp_ExDeletePagedLookasideList
0x1400334ba  nop     dword ptr [rax+rax+00h]
0x1400334bf  mov     rcx, cs:RegData
0x1400334c6  add     rcx, 100h; Lookaside
0x1400334cd  call    cs:__imp_ExDeletePagedLookasideList
0x1400334d4  nop     dword ptr [rax+rax+00h]
0x1400334d9  mov     rcx, cs:RegData
0x1400334e0  add     rcx, 180h; Lookaside
0x1400334e7  call    cs:__imp_ExDeletePagedLookasideList
0x1400334ee  nop     dword ptr [rax+rax+00h]
0x1400334f3  mov     rcx, cs:RegData
0x1400334fa  add     rcx, 200h; Lookaside
0x140033501  call    cs:__imp_ExDeletePagedLookasideList
0x140033508  nop     dword ptr [rax+rax+00h]
0x14003350d  mov     rcx, cs:RegData
0x140033514  add     rcx, 280h; Lookaside
0x14003351b  call    cs:__imp_ExDeletePagedLookasideList
0x140033522  nop     dword ptr [rax+rax+00h]
0x140033527  mov     rcx, cs:RegData
0x14003352e  add     rcx, 300h; Lookaside
0x140033535  call    cs:__imp_ExDeletePagedLookasideList
0x14003353c  nop     dword ptr [rax+rax+00h]
0x140033541  mov     rcx, cs:RegData
0x140033548  add     rcx, 380h; Lookaside
0x14003354f  call    cs:__imp_ExDeletePagedLookasideList
0x140033556  nop     dword ptr [rax+rax+00h]
0x14003355b  mov     rcx, cs:RegData
0x140033562  add     rcx, 400h; Lookaside
0x140033569  call    cs:__imp_ExDeletePagedLookasideList
0x140033570  nop     dword ptr [rax+rax+00h]
0x140033575  mov     rcx, cs:RegData
0x14003357c  add     rcx, 480h; Lookaside
0x140033583  call    cs:__imp_ExDeletePagedLookasideList
0x14003358a  nop     dword ptr [rax+rax+00h]
0x14003358f  mov     rcx, cs:RegData; P
0x140033596  mov     edx, 64526353h; Tag
0x14003359b  call    SecFreePool
0x1400335a0  mov     cs:RegData, 0
0x1400335ab  add     rsp, 28h
0x1400335af  retn
```
