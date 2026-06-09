# VmbusTlConnectCancelTimer

- ea: `0x1400022e4`
- end: `0x1400023a9`
- name: `VmbusTlConnectCancelTimer`
- size: `197`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140001ba0`
- `0x1400023b0`

## callees

- `0x1400022e4`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400022f4`
- `ntoskrnl!KeCancelTimer` at `0x1400022f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002390`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002390`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000237a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000237a`

## pseudocode

```c
char __fastcall VmbusTlConnectCancelTimer(char *P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void (__fastcall *v5)(char *); // rax

  if ( !KeCancelTimer((PKTIMER)(P + 336)) )
    return 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectCancelTimer",
      967,
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
    v5 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
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
  return 1;
}

```

## disassembly

```asm
0x1400022e4  push    rbx
0x1400022e6  sub     rsp, 30h
0x1400022ea  mov     rbx, rcx
0x1400022ed  add     rcx, 150h; PKTIMER
0x1400022f4  call    cs:__imp_KeCancelTimer
0x1400022fb  nop     dword ptr [rax+rax+00h]
0x140002300  test    al, al
0x140002302  jz      loc_1400023A0
0x140002308  mov     eax, cs:dword_140013058
0x14000230e  cmp     eax, 5
0x140002311  jbe     short loc_140002337
0x140002313  mov     r9, [rbx+8]
0x140002317  lea     rax, aDereferenceObj; "Dereference object"
0x14000231e  mov     r8, rbx
0x140002321  mov     [rsp+38h+var_18], rax
0x140002326  mov     edx, 3C7h
0x14000232b  lea     rcx, aVmbustlconnect_5; "VmbusTlConnectCancelTimer"
0x140002332  call    HvsocketTraceReferenceCount
0x140002337  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000233b  lock xadd [rbx+8], rax
0x140002341  sub     rax, 1
0x140002345  jg      short loc_14000239C
0x140002347  test    rax, rax
0x14000234a  jz      short loc_140002355
0x14000234c  mov     ecx, 0Eh
0x140002351  int     29h; Win8: RtlFailFast(ecx)
0x140002353  jmp     short loc_14000239C
0x140002355  mov     rax, [rbx+50h]
0x140002359  test    rax, rax
0x14000235c  jz      short loc_140002366
0x14000235e  mov     rcx, rbx
0x140002361  call    _guard_dispatch_icall
0x140002366  mov     ecx, [rbx+58h]
0x140002369  sub     ecx, 1
0x14000236c  jz      short loc_140002388
0x14000236e  cmp     ecx, 1
0x140002371  jnz     short loc_14000239C
0x140002373  mov     rcx, [rbx+60h]; Lookaside
0x140002377  mov     rdx, rbx; Entry
0x14000237a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002381  nop     dword ptr [rax+rax+00h]
0x140002386  jmp     short loc_14000239C
0x140002388  mov     edx, 69706E56h; Tag
0x14000238d  mov     rcx, rbx; P
0x140002390  call    cs:__imp_ExFreePoolWithTag
0x140002397  nop     dword ptr [rax+rax+00h]
0x14000239c  mov     al, 1
0x14000239e  jmp     short loc_1400023A2
0x1400023a0  xor     al, al
0x1400023a2  add     rsp, 30h
0x1400023a6  pop     rbx
0x1400023a7  retn
```
