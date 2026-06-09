# HvSocketPartitionExists

- ea: `0x14001df1c`
- end: `0x14001dfd0`
- name: `HvSocketPartitionExists`
- size: `180`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140018350`
- `0x140018e20`
- `0x14001d304`
- `0x140020124`

## callees

- `0x14000a048`
- `0x14000bfe0`
- `0x14001d530`
- `0x14001df1c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfbb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dfa5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dfa5`

## pseudocode

```c
char __fastcall HvSocketPartitionExists(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  signed __int64 v4; // rax
  bool v5; // cc
  signed __int64 v6; // rax
  void (__fastcall *v7)(__int64); // rax

  v2 = HvSocketFindAndReferenceAnyPartition(a1, a2);
  v3 = v2;
  if ( v2 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketPartitionExists",
        2231,
        v2,
        *(_QWORD *)(v2 + 8),
        (__int64)"Dereference object");
    v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v5 = v4 <= 1;
    v6 = v4 - 1;
    if ( v5 )
    {
      if ( v6 )
        __fastfail(0xEu);
      v7 = *(void (__fastcall **)(__int64))(v3 + 80);
      if ( v7 )
        v7(v3);
      if ( *(_DWORD *)(v3 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v3 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 96), (PVOID)v3);
      }
    }
    LOBYTE(v2) = 1;
  }
  return v2;
}

```

## disassembly

```asm
0x14001df1c  push    rbx
0x14001df1e  sub     rsp, 30h
0x14001df22  call    HvSocketFindAndReferenceAnyPartition
0x14001df27  mov     rbx, rax
0x14001df2a  test    rax, rax
0x14001df2d  jz      loc_14001DFC9
0x14001df33  mov     ecx, cs:dword_140013058
0x14001df39  cmp     ecx, 5
0x14001df3c  jbe     short loc_14001DF62
0x14001df3e  mov     r9, [rax+8]
0x14001df42  lea     rcx, aHvsocketpartit; "HvSocketPartitionExists"
0x14001df49  lea     rax, aDereferenceObj; "Dereference object"
0x14001df50  mov     r8, rbx
0x14001df53  mov     edx, 8B7h
0x14001df58  mov     [rsp+38h+var_18], rax
0x14001df5d  call    HvsocketTraceReferenceCount
0x14001df62  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001df66  lock xadd [rbx+8], rax
0x14001df6c  sub     rax, 1
0x14001df70  jg      short loc_14001DFC7
0x14001df72  test    rax, rax
0x14001df75  jz      short loc_14001DF80
0x14001df77  mov     ecx, 0Eh
0x14001df7c  int     29h; Win8: RtlFailFast(ecx)
0x14001df7e  jmp     short loc_14001DFC7
0x14001df80  mov     rax, [rbx+50h]
0x14001df84  test    rax, rax
0x14001df87  jz      short loc_14001DF91
0x14001df89  mov     rcx, rbx
0x14001df8c  call    _guard_dispatch_icall
0x14001df91  mov     ecx, [rbx+58h]
0x14001df94  sub     ecx, 1
0x14001df97  jz      short loc_14001DFB3
0x14001df99  cmp     ecx, 1
0x14001df9c  jnz     short loc_14001DFC7
0x14001df9e  mov     rcx, [rbx+60h]; Lookaside
0x14001dfa2  mov     rdx, rbx; Entry
0x14001dfa5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001dfac  nop     dword ptr [rax+rax+00h]
0x14001dfb1  jmp     short loc_14001DFC7
0x14001dfb3  mov     edx, 69706E56h; Tag
0x14001dfb8  mov     rcx, rbx; P
0x14001dfbb  call    cs:__imp_ExFreePoolWithTag
0x14001dfc2  nop     dword ptr [rax+rax+00h]
0x14001dfc7  mov     al, 1
0x14001dfc9  add     rsp, 30h
0x14001dfcd  pop     rbx
0x14001dfce  retn
```
