# VmbusTlXPartRootConnectRequestCompleted

- ea: `0x14000af30`
- end: `0x14000b065`
- name: `VmbusTlXPartRootConnectRequestCompleted`
- size: `309`
- prototype: `__int64 __fastcall(__int64, __int64, KSPIN_LOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025610`

## callees

- `0x1400023b0`
- `0x14000a048`
- `0x14000af30`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000af50`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000af7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000af7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b01c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b01c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b006`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b006`

## string_xrefs

- `0x14000afb7`: `VmbusTlXPartRootConnectRequestCompleted`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartRootConnectRequestCompleted(__int64 a1, __int64 a2, KSPIN_LOCK *a3)
{
  KIRQL v4; // al
  KSPIN_LOCK v5; // rdi
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(KSPIN_LOCK); // rax

  v4 = KeAcquireSpinLockRaiseToDpc(a3 + 9);
  v5 = a3[86];
  a3[86] = 0;
  KeReleaseSpinLock(a3 + 9, v4);
  if ( v5 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlXPartRootConnectRequestCompleted",
        378,
        v5,
        *(_QWORD *)(v5 + 8),
        (__int64)"Dereference object");
    v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v6 <= 1;
    v8 = v6 - 1;
    if ( v7 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = *(void (__fastcall **)(KSPIN_LOCK))(v5 + 80);
      if ( v9 )
        v9(v5);
      if ( *(_DWORD *)(v5 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v5 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
      }
    }
  }
  VmbusTlConnectComplete(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000af30  mov     [rsp+arg_0], rbx
0x14000af35  mov     [rsp+arg_10], rbp
0x14000af3a  push    rsi
0x14000af3b  push    rdi
0x14000af3c  push    r14
0x14000af3e  sub     rsp, 30h
0x14000af42  mov     esi, [rdx+30h]
0x14000af45  lea     rcx, [r8+48h]; SpinLock
0x14000af49  mov     [rsp+48h+arg_8], esi
0x14000af4d  mov     rbp, r8
0x14000af50  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000af57  nop     dword ptr [rax+rax+00h]
0x14000af5c  mov     r14b, [rbp+204h]
0x14000af63  lea     rcx, [rbp+48h]; SpinLock
0x14000af67  mov     rdi, [rbp+2B0h]
0x14000af6e  mov     dl, al; NewIrql
0x14000af70  mov     qword ptr [rbp+2B0h], 0
0x14000af7b  and     r14b, 1
0x14000af7f  call    cs:__imp_KeReleaseSpinLock
0x14000af86  nop     dword ptr [rax+rax+00h]
0x14000af8b  test    rdi, rdi
0x14000af8e  jz      loc_14000B028
0x14000af94  mov     eax, cs:dword_140013058
0x14000af9a  cmp     eax, 5
0x14000af9d  jbe     short loc_14000AFC3
0x14000af9f  mov     r9, [rdi+8]
0x14000afa3  lea     rax, aDereferenceObj; "Dereference object"
0x14000afaa  mov     r8, rdi
0x14000afad  mov     [rsp+48h+var_28], rax
0x14000afb2  mov     edx, 17Ah
0x14000afb7  lea     rcx, aVmbustlxpartro; "VmbusTlXPartRootConnectRequestCompleted"
0x14000afbe  call    HvsocketTraceReferenceCount
0x14000afc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000afc7  lock xadd [rdi+8], rax
0x14000afcd  sub     rax, 1
0x14000afd1  jg      short loc_14000B028
0x14000afd3  test    rax, rax
0x14000afd6  jz      short loc_14000AFE1
0x14000afd8  mov     ecx, 0Eh
0x14000afdd  int     29h; Win8: RtlFailFast(ecx)
0x14000afdf  jmp     short loc_14000B028
0x14000afe1  mov     rax, [rdi+50h]
0x14000afe5  test    rax, rax
0x14000afe8  jz      short loc_14000AFF2
0x14000afea  mov     rcx, rdi
0x14000afed  call    _guard_dispatch_icall
0x14000aff2  mov     ecx, [rdi+58h]
0x14000aff5  sub     ecx, 1
0x14000aff8  jz      short loc_14000B014
0x14000affa  cmp     ecx, 1
0x14000affd  jnz     short loc_14000B028
0x14000afff  mov     rcx, [rdi+60h]; Lookaside
0x14000b003  mov     rdx, rdi; Entry
0x14000b006  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b00d  nop     dword ptr [rax+rax+00h]
0x14000b012  jmp     short loc_14000B028
0x14000b014  mov     edx, 69706E56h; Tag
0x14000b019  mov     rcx, rdi; P
0x14000b01c  call    cs:__imp_ExFreePoolWithTag
0x14000b023  nop     dword ptr [rax+rax+00h]
0x14000b028  test    r14b, r14b
0x14000b02b  jz      short loc_14000B03F
0x14000b02d  cmp     esi, 0C0000120h
0x14000b033  mov     eax, 0C00000B5h
0x14000b038  cmovz   esi, eax
0x14000b03b  mov     [rsp+48h+arg_8], esi
0x14000b03f  lea     rdx, [rsp+48h+arg_8]
0x14000b044  mov     rcx, rbp; P
0x14000b047  call    VmbusTlConnectComplete
0x14000b04c  mov     rbx, [rsp+48h+arg_0]
0x14000b051  mov     eax, 0C0000016h
0x14000b056  mov     rbp, [rsp+48h+arg_10]
0x14000b05b  add     rsp, 30h
0x14000b05f  pop     r14
0x14000b061  pop     rdi
0x14000b062  pop     rsi
0x14000b063  retn
```
