# FreeSockContextCommon

- ea: `0x14001f454`
- end: `0x14001f514`
- name: `FreeSockContextCommon`
- size: `192`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001f520`
- `0x14001f7d0`

## callees

- `0x140004830`
- `0x14001f454`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001f4b0`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001f4c3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001f4b0`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001f4c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f4fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f4eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f4eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f497`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f497`

## string_xrefs

- `0x14001f481`: `FreeSockContextCommon..Freeing Socket Lists and locks`
- `0x14001f465`: `FreeSockContextCommon..Freeing the Socket Context`

## pseudocode

```c
void __fastcall FreeSockContextCommon(PVOID P)
{
  KIRQL v2; // dl

  (*((void (__fastcall **)(const char *))P + 6))("FreeSockContextCommon..Freeing the Socket Context");
  if ( (*((_DWORD *)P + 98) & 0x800) != 0 )
  {
    (*((void (__fastcall **)(const char *))P + 6))("FreeSockContextCommon..Freeing Socket Lists and locks");
    *((_BYTE *)P + 464) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 57);
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)P + 1);
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)P + 2);
    v2 = *((_BYTE *)P + 464);
    *((_QWORD *)P + 48) = 0;
    *((_QWORD *)P + 1) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)P + 57, v2);
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14001f454  mov     [rsp+arg_0], rbx
0x14001f459  push    rdi
0x14001f45a  sub     rsp, 20h
0x14001f45e  mov     rax, [rcx+30h]
0x14001f462  mov     rdi, rcx
0x14001f465  lea     rcx, aFreesockcontex_0; "FreeSockContextCommon..Freeing the Sock"...
0x14001f46c  call    _guard_dispatch_icall
0x14001f471  test    dword ptr [rdi+188h], 800h
0x14001f47b  jz      short loc_14001F4F7
0x14001f47d  mov     rax, [rdi+30h]
0x14001f481  lea     rcx, aFreesockcontex; "FreeSockContextCommon..Freeing Socket L"...
0x14001f488  call    _guard_dispatch_icall
0x14001f48d  lea     rbx, [rdi+1C8h]
0x14001f494  mov     rcx, rbx; SpinLock
0x14001f497  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f49e  nop     dword ptr [rax+rax+00h]
0x14001f4a3  lea     rcx, [rdi+80h]; Lookaside
0x14001f4aa  mov     [rdi+1D0h], al
0x14001f4b0  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001f4b7  nop     dword ptr [rax+rax+00h]
0x14001f4bc  lea     rcx, [rdi+100h]; Lookaside
0x14001f4c3  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001f4ca  nop     dword ptr [rax+rax+00h]
0x14001f4cf  mov     dl, [rdi+1D0h]; NewIrql
0x14001f4d5  mov     rcx, rbx; SpinLock
0x14001f4d8  mov     qword ptr [rdi+180h], 0
0x14001f4e3  mov     qword ptr [rdi+8], 0
0x14001f4eb  call    cs:__imp_KeReleaseSpinLock
0x14001f4f2  nop     dword ptr [rax+rax+00h]
0x14001f4f7  xor     edx, edx; Tag
0x14001f4f9  mov     rcx, rdi; P
0x14001f4fc  call    cs:__imp_ExFreePoolWithTag
0x14001f503  nop     dword ptr [rax+rax+00h]
0x14001f508  mov     rbx, [rsp+28h+arg_0]
0x14001f50d  add     rsp, 20h
0x14001f511  pop     rdi
0x14001f512  retn
```
