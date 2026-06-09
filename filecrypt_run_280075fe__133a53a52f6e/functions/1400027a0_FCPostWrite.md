# FCPostWrite

- ea: `0x1400027a0`
- end: `0x1400027f4`
- name: `FCPostWrite`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140002530`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400027df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400027df`
- `FLTMGR!FltReleaseContext` at `0x1400027ac`
- `FLTMGR!FltReleaseContext` at `0x1400027bc`
- `FLTMGR!FltReleaseContext` at `0x1400027ac`
- `FLTMGR!FltReleaseContext` at `0x1400027bc`

## pseudocode

```c
__int64 __fastcall FCPostWrite(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // rcx

  FltReleaseContext(*(PFLT_CONTEXT *)a3);
  FltReleaseContext(*(PFLT_CONTEXT *)(a3 + 8));
  LOBYTE(v4) = *(_BYTE *)(a3 + 24);
  FCFreeShadowBuffer(v5, *(_QWORD *)(a3 + 16), v4);
  ExFreeToNPagedLookasideList(&gPre2PostIoContextList, (PVOID)a3);
  return 0;
}

```

## disassembly

```asm
0x1400027a0  push    rbx
0x1400027a2  sub     rsp, 20h
0x1400027a6  mov     rcx, [r8]; Context
0x1400027a9  mov     rbx, r8
0x1400027ac  call    cs:__imp_FltReleaseContext
0x1400027b3  nop     dword ptr [rax+rax+00h]
0x1400027b8  mov     rcx, [rbx+8]; Context
0x1400027bc  call    cs:__imp_FltReleaseContext
0x1400027c3  nop     dword ptr [rax+rax+00h]
0x1400027c8  mov     r8b, [rbx+18h]
0x1400027cc  mov     rdx, [rbx+10h]
0x1400027d0  call    FCFreeShadowBuffer
0x1400027d5  mov     rdx, rbx; Entry
0x1400027d8  lea     rcx, gPre2PostIoContextList; Lookaside
0x1400027df  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400027e6  nop     dword ptr [rax+rax+00h]
0x1400027eb  xor     eax, eax
0x1400027ed  add     rsp, 20h
0x1400027f1  pop     rbx
0x1400027f2  retn
```
