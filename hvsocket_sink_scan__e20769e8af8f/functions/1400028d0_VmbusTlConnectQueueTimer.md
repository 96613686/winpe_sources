# VmbusTlConnectQueueTimer

- ea: `0x1400028d0`
- end: `0x140002a30`
- name: `VmbusTlConnectQueueTimer`
- size: `352`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140001bf4`
- `0x14001960c`

## callees

- `0x1400028d0`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140002964`
- `ntoskrnl!KeSetTimer` at `0x140002964`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400028e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400028e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a00`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400029ea`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400029ea`

## pseudocode

```c
void __fastcall VmbusTlConnectQueueTimer(char *P)
{
  KIRQL v2; // si
  signed __int64 v3; // rax
  bool v4; // cc
  signed __int64 v5; // rax
  void (__fastcall *v6)(char *); // rax

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 9);
  if ( (*((_DWORD *)P + 129) & 0x200) == 0 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectQueueTimer",
        939,
        (_DWORD)P,
        *((_QWORD *)P + 1),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)P + 1) <= 1 )
      __fastfail(0xEu);
    if ( KeSetTimer((PKTIMER)(P + 336), *(LARGE_INTEGER *)(P + 176), (PKDPC)(P + 400)) )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlConnectQueueTimer",
          944,
          (_DWORD)P,
          *((_QWORD *)P + 1),
          (__int64)"Dereference object");
      v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v4 = v3 <= 1;
      v5 = v3 - 1;
      if ( v4 )
      {
        if ( v5 )
          __fastfail(0xEu);
        v6 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
        if ( v6 )
          v6(P);
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
  KeReleaseSpinLock((PKSPIN_LOCK)P + 9, v2);
}

```

## disassembly

```asm
0x1400028d0  mov     [rsp+arg_0], rbx
0x1400028d5  mov     [rsp+arg_8], rsi
0x1400028da  push    rdi
0x1400028db  sub     rsp, 30h
0x1400028df  mov     rbx, rcx
0x1400028e2  add     rcx, 48h ; 'H'; SpinLock
0x1400028e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400028ed  nop     dword ptr [rax+rax+00h]
0x1400028f2  test    dword ptr [rbx+204h], 200h
0x1400028fc  mov     sil, al
0x1400028ff  jnz     loc_140002A0C
0x140002905  mov     edx, cs:dword_140013058
0x14000290b  cmp     edx, 5
0x14000290e  jbe     short loc_140002934
0x140002910  mov     r9, [rbx+8]
0x140002914  lea     rax, aReferenceObjec; "Reference object"
0x14000291b  mov     r8, rbx
0x14000291e  mov     [rsp+38h+var_18], rax
0x140002923  mov     edx, 3ABh
0x140002928  lea     rcx, aVmbustlconnect; "VmbusTlConnectQueueTimer"
0x14000292f  call    HvsocketTraceReferenceCount
0x140002934  mov     eax, 1
0x140002939  lock xadd [rbx+8], rax
0x14000293f  inc     rax
0x140002942  cmp     rax, 1
0x140002946  jg      short loc_14000294F
0x140002948  mov     ecx, 0Eh
0x14000294d  int     29h; Win8: RtlFailFast(ecx)
0x14000294f  mov     rdx, [rbx+0B0h]; DueTime
0x140002956  lea     r8, [rbx+190h]; Dpc
0x14000295d  lea     rcx, [rbx+150h]; Timer
0x140002964  call    cs:__imp_KeSetTimer
0x14000296b  nop     dword ptr [rax+rax+00h]
0x140002970  test    al, al
0x140002972  jz      loc_140002A0C
0x140002978  mov     eax, cs:dword_140013058
0x14000297e  cmp     eax, 5
0x140002981  jbe     short loc_1400029A7
0x140002983  mov     r9, [rbx+8]
0x140002987  lea     rax, aDereferenceObj; "Dereference object"
0x14000298e  mov     r8, rbx
0x140002991  mov     [rsp+38h+var_18], rax
0x140002996  mov     edx, 3B0h
0x14000299b  lea     rcx, aVmbustlconnect; "VmbusTlConnectQueueTimer"
0x1400029a2  call    HvsocketTraceReferenceCount
0x1400029a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400029ab  lock xadd [rbx+8], rax
0x1400029b1  sub     rax, 1
0x1400029b5  jg      short loc_140002A0C
0x1400029b7  test    rax, rax
0x1400029ba  jz      short loc_1400029C5
0x1400029bc  mov     ecx, 0Eh
0x1400029c1  int     29h; Win8: RtlFailFast(ecx)
0x1400029c3  jmp     short loc_140002A0C
0x1400029c5  mov     rax, [rbx+50h]
0x1400029c9  test    rax, rax
0x1400029cc  jz      short loc_1400029D6
0x1400029ce  mov     rcx, rbx
0x1400029d1  call    _guard_dispatch_icall
0x1400029d6  mov     ecx, [rbx+58h]
0x1400029d9  sub     ecx, 1
0x1400029dc  jz      short loc_1400029F8
0x1400029de  cmp     ecx, 1
0x1400029e1  jnz     short loc_140002A0C
0x1400029e3  mov     rcx, [rbx+60h]; Lookaside
0x1400029e7  mov     rdx, rbx; Entry
0x1400029ea  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400029f1  nop     dword ptr [rax+rax+00h]
0x1400029f6  jmp     short loc_140002A0C
0x1400029f8  mov     edx, 69706E56h; Tag
0x1400029fd  mov     rcx, rbx; P
0x140002a00  call    cs:__imp_ExFreePoolWithTag
0x140002a07  nop     dword ptr [rax+rax+00h]
0x140002a0c  mov     dl, sil; NewIrql
0x140002a0f  lea     rcx, [rbx+48h]; SpinLock
0x140002a13  call    cs:__imp_KeReleaseSpinLock
0x140002a1a  nop     dword ptr [rax+rax+00h]
0x140002a1f  mov     rbx, [rsp+38h+arg_0]
0x140002a24  mov     rsi, [rsp+38h+arg_8]
0x140002a29  add     rsp, 30h
0x140002a2d  pop     rdi
0x140002a2e  retn
```
