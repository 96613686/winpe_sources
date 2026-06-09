# VmbusTlContainerCleanup

- ea: `0x140019770`
- end: `0x140019830`
- name: `VmbusTlContainerCleanup`
- size: `192`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400234e0`

## callees

- `0x14000a048`
- `0x14000bfe0`
- `0x140019770`

## import_xrefs

- `ntoskrnl!PsUnregisterSiloMonitor` at `0x140019789`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x140019789`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001981d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001981d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019807`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019807`

## pseudocode

```c
void __fastcall VmbusTlContainerCleanup(PVOID P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void (__fastcall *v5)(PVOID); // rax

  if ( *((_QWORD *)P + 163) )
  {
    PsUnregisterSiloMonitor();
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlContainerCleanup",
        90,
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
}

```

## disassembly

```asm
0x140019770  push    rbx
0x140019772  sub     rsp, 30h
0x140019776  mov     rbx, rcx
0x140019779  mov     rcx, [rcx+518h]
0x140019780  test    rcx, rcx
0x140019783  jz      loc_140019829
0x140019789  call    cs:__imp_PsUnregisterSiloMonitor
0x140019790  nop     dword ptr [rax+rax+00h]
0x140019795  mov     eax, cs:dword_140013058
0x14001979b  cmp     eax, 5
0x14001979e  jbe     short loc_1400197C4
0x1400197a0  mov     r9, [rbx+8]
0x1400197a4  lea     rax, aDereferenceObj; "Dereference object"
0x1400197ab  mov     r8, rbx
0x1400197ae  mov     [rsp+38h+var_18], rax
0x1400197b3  mov     edx, 5Ah ; 'Z'
0x1400197b8  lea     rcx, aVmbustlcontain_0; "VmbusTlContainerCleanup"
0x1400197bf  call    HvsocketTraceReferenceCount
0x1400197c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400197c8  lock xadd [rbx+8], rax
0x1400197ce  sub     rax, 1
0x1400197d2  jg      short loc_140019829
0x1400197d4  test    rax, rax
0x1400197d7  jz      short loc_1400197E2
0x1400197d9  mov     ecx, 0Eh
0x1400197de  int     29h; Win8: RtlFailFast(ecx)
0x1400197e0  jmp     short loc_140019829
0x1400197e2  mov     rax, [rbx+50h]
0x1400197e6  test    rax, rax
0x1400197e9  jz      short loc_1400197F3
0x1400197eb  mov     rcx, rbx
0x1400197ee  call    _guard_dispatch_icall
0x1400197f3  mov     ecx, [rbx+58h]
0x1400197f6  sub     ecx, 1
0x1400197f9  jz      short loc_140019815
0x1400197fb  cmp     ecx, 1
0x1400197fe  jnz     short loc_140019829
0x140019800  mov     rcx, [rbx+60h]; Lookaside
0x140019804  mov     rdx, rbx; Entry
0x140019807  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001980e  nop     dword ptr [rax+rax+00h]
0x140019813  jmp     short loc_140019829
0x140019815  mov     edx, 69706E56h; Tag
0x14001981a  mov     rcx, rbx; P
0x14001981d  call    cs:__imp_ExFreePoolWithTag
0x140019824  nop     dword ptr [rax+rax+00h]
0x140019829  add     rsp, 30h
0x14001982d  pop     rbx
0x14001982e  retn
```
