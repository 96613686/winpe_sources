# HvSocketNotifyCleanupClientContext

- ea: `0x140023430`
- end: `0x1400234d4`
- name: `HvSocketNotifyCleanupClientContext`
- size: `164`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000a048`
- `0x14000bfe0`
- `0x140023430`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400234c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234c1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400234ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400234ab`

## pseudocode

```c
void __fastcall HvSocketNotifyCleanupClientContext(PVOID P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void (__fastcall *v5)(PVOID); // rax

  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketNotifyCleanupClientContext",
      757,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Dereference object");
  v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    v5 = (void (__fastcall *)(PVOID))*((_QWORD *)P + 10);
    if ( v5 )
      v5(P);
    if ( *((_DWORD *)P + 22) == 1 )
    {
      ExFreePoolWithTag(P, 0x69706E56u);
    }
    else if ( *((_DWORD *)P + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
    }
  }
}

```

## disassembly

```asm
0x140023430  push    rbx
0x140023432  sub     rsp, 30h
0x140023436  mov     eax, cs:dword_140013058
0x14002343c  mov     rbx, rcx
0x14002343f  cmp     eax, 5
0x140023442  jbe     short loc_140023468
0x140023444  mov     r9, [rcx+8]
0x140023448  lea     rax, aDereferenceObj; "Dereference object"
0x14002344f  mov     r8, rcx
0x140023452  mov     [rsp+38h+var_18], rax
0x140023457  lea     rcx, aHvsocketnotify_1; "HvSocketNotifyCleanupClientContext"
0x14002345e  mov     edx, 2F5h
0x140023463  call    HvsocketTraceReferenceCount
0x140023468  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002346c  lock xadd [rbx+8], rax
0x140023472  sub     rax, 1
0x140023476  jg      short loc_1400234CD
0x140023478  test    rax, rax
0x14002347b  jz      short loc_140023486
0x14002347d  mov     ecx, 0Eh
0x140023482  int     29h; Win8: RtlFailFast(ecx)
0x140023484  jmp     short loc_1400234CD
0x140023486  mov     rax, [rbx+50h]
0x14002348a  test    rax, rax
0x14002348d  jz      short loc_140023497
0x14002348f  mov     rcx, rbx
0x140023492  call    _guard_dispatch_icall
0x140023497  mov     ecx, [rbx+58h]
0x14002349a  sub     ecx, 1
0x14002349d  jz      short loc_1400234B9
0x14002349f  cmp     ecx, 1
0x1400234a2  jnz     short loc_1400234CD
0x1400234a4  mov     rcx, [rbx+60h]; Lookaside
0x1400234a8  mov     rdx, rbx; Entry
0x1400234ab  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400234b2  nop     dword ptr [rax+rax+00h]
0x1400234b7  jmp     short loc_1400234CD
0x1400234b9  mov     edx, 69706E56h; Tag
0x1400234be  mov     rcx, rbx; P
0x1400234c1  call    cs:__imp_ExFreePoolWithTag
0x1400234c8  nop     dword ptr [rax+rax+00h]
0x1400234cd  add     rsp, 30h
0x1400234d1  pop     rbx
0x1400234d2  retn
```
