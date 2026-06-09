# FreeSockContextCommon

- ea: `0x14001c2f0`
- end: `0x14001c3b0`
- name: `FreeSockContextCommon`
- size: `192`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001c3c0`
- `0x14001c850`

## callees

- `0x140007710`
- `0x14001c2f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c398`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c398`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001c34c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001c35f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001c34c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001c35f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c387`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c387`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c333`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c333`

## string_xrefs

- `0x14001c301`: `FreeSockContextCommon..Freeing the Socket Context`
- `0x14001c31d`: `FreeSockContextCommon..Freeing Socket Lists and locks`

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
0x14001c2f0  mov     [rsp+arg_0], rbx
0x14001c2f5  push    rdi
0x14001c2f6  sub     rsp, 20h
0x14001c2fa  mov     rax, [rcx+30h]
0x14001c2fe  mov     rdi, rcx
0x14001c301  lea     rcx, aFreesockcontex_0; "FreeSockContextCommon..Freeing the Sock"...
0x14001c308  call    _guard_dispatch_icall
0x14001c30d  test    dword ptr [rdi+188h], 800h
0x14001c317  jz      short loc_14001C393
0x14001c319  mov     rax, [rdi+30h]
0x14001c31d  lea     rcx, aFreesockcontex; "FreeSockContextCommon..Freeing Socket L"...
0x14001c324  call    _guard_dispatch_icall
0x14001c329  lea     rbx, [rdi+1C8h]
0x14001c330  mov     rcx, rbx; SpinLock
0x14001c333  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c33a  nop     dword ptr [rax+rax+00h]
0x14001c33f  lea     rcx, [rdi+80h]; Lookaside
0x14001c346  mov     [rdi+1D0h], al
0x14001c34c  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001c353  nop     dword ptr [rax+rax+00h]
0x14001c358  lea     rcx, [rdi+100h]; Lookaside
0x14001c35f  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001c366  nop     dword ptr [rax+rax+00h]
0x14001c36b  mov     dl, [rdi+1D0h]; NewIrql
0x14001c371  mov     rcx, rbx; SpinLock
0x14001c374  mov     qword ptr [rdi+180h], 0
0x14001c37f  mov     qword ptr [rdi+8], 0
0x14001c387  call    cs:__imp_KeReleaseSpinLock
0x14001c38e  nop     dword ptr [rax+rax+00h]
0x14001c393  xor     edx, edx; Tag
0x14001c395  mov     rcx, rdi; P
0x14001c398  call    cs:__imp_ExFreePoolWithTag
0x14001c39f  nop     dword ptr [rax+rax+00h]
0x14001c3a4  mov     rbx, [rsp+28h+arg_0]
0x14001c3a9  add     rsp, 20h
0x14001c3ad  pop     rdi
0x14001c3ae  retn
```
