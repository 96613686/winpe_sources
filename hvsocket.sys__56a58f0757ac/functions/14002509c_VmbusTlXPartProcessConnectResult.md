# VmbusTlXPartProcessConnectResult

- ea: `0x14002509c`
- end: `0x140025279`
- name: `VmbusTlXPartProcessConnectResult`
- size: `477`
- prototype: `void __fastcall(__int64 P, __int64, const void *, int)`
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
- `0x14002509c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400251d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025259`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400251d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025259`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400251ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025243`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400251ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025243`

## pseudocode

```c
void __fastcall VmbusTlXPartProcessConnectResult(__int64 P, __int64 a2, const void *a3, int a4)
{
  PVOID v7; // rdi
  __int64 v8; // rax
  void (__fastcall *v9)(PVOID); // rax
  __int64 v10; // rax
  void (__fastcall *v11)(__int64); // rax
  PVOID Entry; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = a4;
  Entry = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlXPartProcessConnectResult",
      1198,
      P,
      *(_QWORD *)(P + 8),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(P + 8)) <= 1 )
    __fastfail(0xEu);
  if ( HvSocketGetPendingOutboundConnectionFromPartition(P, a2, a3, (__int64)&Entry) )
  {
    v7 = Entry;
    if ( HvSocketBeginProcessingConnection((__int64)Entry) )
      VmbusTlConnectComplete((char *)v7, &v13);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlXPartProcessConnectResult",
        1214,
        (__int64)v7,
        *((_QWORD *)v7 + 1),
        (const int *)"Dereference object");
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
      (const int *)"VmbusTlXPartProcessConnectResult",
      1217,
      P,
      *(_QWORD *)(P + 8),
      (const int *)"Dereference object");
  v10 = _InterlockedDecrement64((volatile signed __int64 *)(P + 8));
  if ( v10 <= 0 )
  {
    if ( v10 )
      __fastfail(0xEu);
    v11 = *(void (__fastcall **)(__int64))(P + 80);
    if ( v11 )
      v11(P);
    if ( *(_DWORD *)(P + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)P, 0x69706E56u);
    }
    else if ( *(_DWORD *)(P + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(P + 96), (PVOID)P);
    }
  }
}

```

## disassembly

```asm
0x14002509c  mov     r11, rsp
0x14002509f  mov     [r11+10h], rbx
0x1400250a3  mov     [r11+18h], rbp
0x1400250a7  mov     [r11+20h], r9d
0x1400250ab  push    rsi
0x1400250ac  push    rdi
0x1400250ad  push    r12
0x1400250af  sub     rsp, 30h
0x1400250b3  mov     eax, cs:dword_140013058
0x1400250b9  mov     rdi, r8
0x1400250bc  mov     qword ptr [r11+8], 0
0x1400250c4  mov     rsi, rdx
0x1400250c7  mov     rbx, rcx
0x1400250ca  cmp     eax, 5
0x1400250cd  jbe     short loc_1400250F2
0x1400250cf  mov     r9, [rcx+8]
0x1400250d3  lea     rax, aReferenceObjec; "Reference object"
0x1400250da  mov     r8, rcx
0x1400250dd  mov     [r11-28h], rax
0x1400250e1  lea     rcx, aVmbustlxpartpr_0; "VmbusTlXPartProcessConnectResult"
0x1400250e8  mov     edx, 4AEh
0x1400250ed  call    HvsocketTraceReferenceCount
0x1400250f2  mov     eax, 1
0x1400250f7  lock xadd [rbx+8], rax
0x1400250fd  inc     rax
0x140025100  mov     ebp, 0Eh
0x140025105  cmp     rax, 1
0x140025109  jg      short loc_14002510F
0x14002510b  mov     ecx, ebp
0x14002510d  int     29h; Win8: RtlFailFast(ecx)
0x14002510f  lea     r9, [rsp+48h+Entry]
0x140025114  mov     r8, rdi
0x140025117  mov     rdx, rsi
0x14002511a  mov     rcx, rbx
0x14002511d  call    HvSocketGetPendingOutboundConnectionFromPartition
0x140025122  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140025126  lea     r12, aDereferenceObj; "Dereference object"
0x14002512d  test    al, al
0x14002512f  jz      loc_1400251DC
0x140025135  mov     rdi, [rsp+48h+Entry]
0x14002513a  mov     rcx, rdi
0x14002513d  call    HvSocketBeginProcessingConnection
0x140025142  test    al, al
0x140025144  jz      short loc_140025153
0x140025146  lea     rdx, [rsp+48h+arg_18]
0x14002514b  mov     rcx, rdi; P
0x14002514e  call    VmbusTlConnectComplete
0x140025153  mov     eax, cs:dword_140013058
0x140025159  cmp     eax, 5
0x14002515c  jbe     short loc_14002517B
0x14002515e  mov     r9, [rdi+8]
0x140025162  lea     rcx, aVmbustlxpartpr_0; "VmbusTlXPartProcessConnectResult"
0x140025169  mov     r8, rdi
0x14002516c  mov     [rsp+48h+var_28], r12
0x140025171  mov     edx, 4BEh
0x140025176  call    HvsocketTraceReferenceCount
0x14002517b  mov     rax, rsi
0x14002517e  lock xadd [rdi+8], rax
0x140025184  add     rax, rsi
0x140025187  test    rax, rax
0x14002518a  jg      short loc_1400251DC
0x14002518c  jz      short loc_140025195
0x14002518e  mov     rcx, rbp
0x140025191  int     29h; Win8: RtlFailFast(ecx)
0x140025193  jmp     short loc_1400251DC
0x140025195  mov     rax, [rdi+50h]
0x140025199  test    rax, rax
0x14002519c  jz      short loc_1400251A6
0x14002519e  mov     rcx, rdi
0x1400251a1  call    _guard_dispatch_icall
0x1400251a6  mov     ecx, [rdi+58h]
0x1400251a9  sub     ecx, 1
0x1400251ac  jz      short loc_1400251C8
0x1400251ae  cmp     ecx, 1
0x1400251b1  jnz     short loc_1400251DC
0x1400251b3  mov     rcx, [rdi+60h]; Lookaside
0x1400251b7  mov     rdx, rdi; Entry
0x1400251ba  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400251c1  nop     dword ptr [rax+rax+00h]
0x1400251c6  jmp     short loc_1400251DC
0x1400251c8  mov     edx, 69706E56h; Tag
0x1400251cd  mov     rcx, rdi; P
0x1400251d0  call    cs:__imp_ExFreePoolWithTag
0x1400251d7  nop     dword ptr [rax+rax+00h]
0x1400251dc  mov     eax, cs:dword_140013058
0x1400251e2  cmp     eax, 5
0x1400251e5  jbe     short loc_140025204
0x1400251e7  mov     r9, [rbx+8]
0x1400251eb  lea     rcx, aVmbustlxpartpr_0; "VmbusTlXPartProcessConnectResult"
0x1400251f2  mov     r8, rbx
0x1400251f5  mov     [rsp+48h+var_28], r12
0x1400251fa  mov     edx, 4C1h
0x1400251ff  call    HvsocketTraceReferenceCount
0x140025204  mov     rax, rsi
0x140025207  lock xadd [rbx+8], rax
0x14002520d  add     rax, rsi
0x140025210  test    rax, rax
0x140025213  jg      short loc_140025265
0x140025215  jz      short loc_14002521E
0x140025217  mov     rcx, rbp
0x14002521a  int     29h; Win8: RtlFailFast(ecx)
0x14002521c  jmp     short loc_140025265
0x14002521e  mov     rax, [rbx+50h]
0x140025222  test    rax, rax
0x140025225  jz      short loc_14002522F
0x140025227  mov     rcx, rbx
0x14002522a  call    _guard_dispatch_icall
0x14002522f  mov     ecx, [rbx+58h]
0x140025232  sub     ecx, 1
0x140025235  jz      short loc_140025251
0x140025237  cmp     ecx, 1
0x14002523a  jnz     short loc_140025265
0x14002523c  mov     rcx, [rbx+60h]; Lookaside
0x140025240  mov     rdx, rbx; Entry
0x140025243  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002524a  nop     dword ptr [rax+rax+00h]
0x14002524f  jmp     short loc_140025265
0x140025251  mov     edx, 69706E56h; Tag
0x140025256  mov     rcx, rbx; P
0x140025259  call    cs:__imp_ExFreePoolWithTag
0x140025260  nop     dword ptr [rax+rax+00h]
0x140025265  mov     rbx, [rsp+48h+arg_8]
0x14002526a  mov     rbp, [rsp+48h+arg_10]
0x14002526f  add     rsp, 30h
0x140025273  pop     r12
0x140025275  pop     rdi
0x140025276  pop     rsi
0x140025277  retn
```
