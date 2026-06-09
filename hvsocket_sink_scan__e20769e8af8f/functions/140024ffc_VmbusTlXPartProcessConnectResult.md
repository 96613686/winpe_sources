# VmbusTlXPartProcessConnectResult

- ea: `0x140024ffc`
- end: `0x1400251d9`
- name: `VmbusTlXPartProcessConnectResult`
- size: `477`
- prototype: `void __fastcall(PVOID P, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140023890`

## callees

- `0x140001ac8`
- `0x1400023b0`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001dcf8`
- `0x140024ffc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025130`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400251b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025130`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400251b9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002511a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400251a3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002511a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400251a3`

## pseudocode

```c
void __fastcall VmbusTlXPartProcessConnectResult(PVOID P, __int64 a2, __int64 a3, int a4)
{
  PVOID v7; // rdi
  __int64 v8; // rax
  void (__fastcall *v9)(PVOID); // rax
  __int64 v10; // rax
  void (__fastcall *v11)(PVOID); // rax
  PVOID Entry; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+68h] [rbp+20h]

  v13 = a4;
  Entry = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlXPartProcessConnectResult",
      1198,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)P + 1) <= 1 )
    __fastfail(0xEu);
  if ( (unsigned __int8)HvSocketGetPendingOutboundConnectionFromPartition(P, a2, a3, &Entry) )
  {
    v7 = Entry;
    if ( (unsigned __int8)HvSocketBeginProcessingConnection(Entry) )
      VmbusTlConnectComplete(v7);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlXPartProcessConnectResult",
        1214,
        (_DWORD)v7,
        *((_QWORD *)v7 + 1),
        (__int64)"Dereference object");
    v8 = _InterlockedDecrement64((volatile signed __int64 *)v7 + 1);
    if ( v8 <= 0 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = (void (__fastcall *)(PVOID))*((_QWORD *)v7 + 10);
      if ( v9 )
        v9(v7);
      if ( *((_DWORD *)v7 + 22) == 1 )
      {
        ExFreePoolWithTag(v7, 0x69706E56u);
      }
      else if ( *((_DWORD *)v7 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v7 + 12), v7);
      }
    }
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlXPartProcessConnectResult",
      1217,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Dereference object");
  v10 = _InterlockedDecrement64((volatile signed __int64 *)P + 1);
  if ( v10 <= 0 )
  {
    if ( v10 )
      __fastfail(0xEu);
    v11 = (void (__fastcall *)(PVOID))*((_QWORD *)P + 10);
    if ( v11 )
      v11(P);
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
0x140024ffc  mov     r11, rsp
0x140024fff  mov     [r11+10h], rbx
0x140025003  mov     [r11+18h], rbp
0x140025007  mov     [r11+20h], r9d
0x14002500b  push    rsi
0x14002500c  push    rdi
0x14002500d  push    r12
0x14002500f  sub     rsp, 30h
0x140025013  mov     eax, cs:dword_140013058
0x140025019  mov     rdi, r8
0x14002501c  mov     qword ptr [r11+8], 0
0x140025024  mov     rsi, rdx
0x140025027  mov     rbx, rcx
0x14002502a  cmp     eax, 5
0x14002502d  jbe     short loc_140025052
0x14002502f  mov     r9, [rcx+8]
0x140025033  lea     rax, aReferenceObjec; "Reference object"
0x14002503a  mov     r8, rcx
0x14002503d  mov     [r11-28h], rax
0x140025041  lea     rcx, aVmbustlxpartpr_0; "VmbusTlXPartProcessConnectResult"
0x140025048  mov     edx, 4AEh
0x14002504d  call    HvsocketTraceReferenceCount
0x140025052  mov     eax, 1
0x140025057  lock xadd [rbx+8], rax
0x14002505d  inc     rax
0x140025060  mov     ebp, 0Eh
0x140025065  cmp     rax, 1
0x140025069  jg      short loc_14002506F
0x14002506b  mov     ecx, ebp
0x14002506d  int     29h; Win8: RtlFailFast(ecx)
0x14002506f  lea     r9, [rsp+48h+Entry]
0x140025074  mov     r8, rdi
0x140025077  mov     rdx, rsi
0x14002507a  mov     rcx, rbx
0x14002507d  call    HvSocketGetPendingOutboundConnectionFromPartition
0x140025082  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140025086  lea     r12, aDereferenceObj; "Dereference object"
0x14002508d  test    al, al
0x14002508f  jz      loc_14002513C
0x140025095  mov     rdi, [rsp+48h+Entry]
0x14002509a  mov     rcx, rdi
0x14002509d  call    HvSocketBeginProcessingConnection
0x1400250a2  test    al, al
0x1400250a4  jz      short loc_1400250B3
0x1400250a6  lea     rdx, [rsp+48h+arg_18]
0x1400250ab  mov     rcx, rdi; P
0x1400250ae  call    VmbusTlConnectComplete
0x1400250b3  mov     eax, cs:dword_140013058
0x1400250b9  cmp     eax, 5
0x1400250bc  jbe     short loc_1400250DB
0x1400250be  mov     r9, [rdi+8]
0x1400250c2  lea     rcx, aVmbustlxpartpr_0; "VmbusTlXPartProcessConnectResult"
0x1400250c9  mov     r8, rdi
0x1400250cc  mov     [rsp+48h+var_28], r12
0x1400250d1  mov     edx, 4BEh
0x1400250d6  call    HvsocketTraceReferenceCount
0x1400250db  mov     rax, rsi
0x1400250de  lock xadd [rdi+8], rax
0x1400250e4  add     rax, rsi
0x1400250e7  test    rax, rax
0x1400250ea  jg      short loc_14002513C
0x1400250ec  jz      short loc_1400250F5
0x1400250ee  mov     rcx, rbp
0x1400250f1  int     29h; Win8: RtlFailFast(ecx)
0x1400250f3  jmp     short loc_14002513C
0x1400250f5  mov     rax, [rdi+50h]
0x1400250f9  test    rax, rax
0x1400250fc  jz      short loc_140025106
0x1400250fe  mov     rcx, rdi
0x140025101  call    _guard_dispatch_icall
0x140025106  mov     ecx, [rdi+58h]
0x140025109  sub     ecx, 1
0x14002510c  jz      short loc_140025128
0x14002510e  cmp     ecx, 1
0x140025111  jnz     short loc_14002513C
0x140025113  mov     rcx, [rdi+60h]; Lookaside
0x140025117  mov     rdx, rdi; Entry
0x14002511a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025121  nop     dword ptr [rax+rax+00h]
0x140025126  jmp     short loc_14002513C
0x140025128  mov     edx, 69706E56h; Tag
0x14002512d  mov     rcx, rdi; P
0x140025130  call    cs:__imp_ExFreePoolWithTag
0x140025137  nop     dword ptr [rax+rax+00h]
0x14002513c  mov     eax, cs:dword_140013058
0x140025142  cmp     eax, 5
0x140025145  jbe     short loc_140025164
0x140025147  mov     r9, [rbx+8]
0x14002514b  lea     rcx, aVmbustlxpartpr_0; "VmbusTlXPartProcessConnectResult"
0x140025152  mov     r8, rbx
0x140025155  mov     [rsp+48h+var_28], r12
0x14002515a  mov     edx, 4C1h
0x14002515f  call    HvsocketTraceReferenceCount
0x140025164  mov     rax, rsi
0x140025167  lock xadd [rbx+8], rax
0x14002516d  add     rax, rsi
0x140025170  test    rax, rax
0x140025173  jg      short loc_1400251C5
0x140025175  jz      short loc_14002517E
0x140025177  mov     rcx, rbp
0x14002517a  int     29h; Win8: RtlFailFast(ecx)
0x14002517c  jmp     short loc_1400251C5
0x14002517e  mov     rax, [rbx+50h]
0x140025182  test    rax, rax
0x140025185  jz      short loc_14002518F
0x140025187  mov     rcx, rbx
0x14002518a  call    _guard_dispatch_icall
0x14002518f  mov     ecx, [rbx+58h]
0x140025192  sub     ecx, 1
0x140025195  jz      short loc_1400251B1
0x140025197  cmp     ecx, 1
0x14002519a  jnz     short loc_1400251C5
0x14002519c  mov     rcx, [rbx+60h]; Lookaside
0x1400251a0  mov     rdx, rbx; Entry
0x1400251a3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400251aa  nop     dword ptr [rax+rax+00h]
0x1400251af  jmp     short loc_1400251C5
0x1400251b1  mov     edx, 69706E56h; Tag
0x1400251b6  mov     rcx, rbx; P
0x1400251b9  call    cs:__imp_ExFreePoolWithTag
0x1400251c0  nop     dword ptr [rax+rax+00h]
0x1400251c5  mov     rbx, [rsp+48h+arg_8]
0x1400251ca  mov     rbp, [rsp+48h+arg_10]
0x1400251cf  add     rsp, 30h
0x1400251d3  pop     r12
0x1400251d5  pop     rdi
0x1400251d6  pop     rsi
0x1400251d7  retn
```
