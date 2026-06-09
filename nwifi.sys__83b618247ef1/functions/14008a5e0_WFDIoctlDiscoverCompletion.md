# WFDIoctlDiscoverCompletion

- ea: `0x14008a5e0`
- end: `0x14008a777`
- name: `WFDIoctlDiscoverCompletion`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140086670`

## callees

- `0x140019314`
- `0x14008a5e0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a62a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a666`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a739`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a62a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a666`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a739`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a63b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a677`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a74a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a63b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a677`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a74a`
- `ntoskrnl!IofCompleteRequest` at `0x14008a761`
- `ntoskrnl!IofCompleteRequest` at `0x14008a761`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14008a5f8`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14008a5f8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008a687`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008a6e7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008a687`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008a6e7`

## pseudocode

```c
void __fastcall WFDIoctlDiscoverCompletion(__int64 a1, int a2, __int64 a3, __int64 a4, int a5, _QWORD *a6)
{
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  KIRQL Irql[56]; // [rsp+30h] [rbp-38h] BYREF

  Irql[0] = 0;
  IoAcquireCancelSpinLock(Irql);
  v8 = a6[3];
  v9 = *a6;
  if ( v8 )
  {
    v10 = v8 - 16;
    if ( *(_QWORD *)v10 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, (PVOID)v10);
    else
      ExFreePoolWithTag((PVOID)v10, *(_DWORD *)(v10 + 8));
    a6[3] = 0;
  }
  if ( v9 && *(_QWORD *)(v9 + 120) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, v9, a2);
    }
    *(_QWORD *)(v9 + 120) = 0;
    IoReleaseCancelSpinLock(Irql[0]);
    *(_DWORD *)(v9 + 48) = a2;
    if ( (!a2 || a2 == 261) && a3 )
    {
      v11 = a6[1];
      *(_QWORD *)v11 = *(_QWORD *)a3;
      *(_DWORD *)(v11 + 8) = *(_DWORD *)(a3 + 8);
      v12 = 12;
    }
    else
    {
      v12 = 0;
    }
    *(_QWORD *)(v9 + 56) = v12;
    if ( *(a6 - 2) )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(a6 - 2), a6 - 2);
    else
      ExFreePoolWithTag(a6 - 2, *((_DWORD *)a6 - 2));
    _InterlockedExchange64((volatile __int64 *)(v9 + 104), 0);
    IofCompleteRequest((PIRP)v9, 2);
  }
  else
  {
    if ( *(a6 - 2) )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(a6 - 2), a6 - 2);
    else
      ExFreePoolWithTag(a6 - 2, *((_DWORD *)a6 - 2));
    IoReleaseCancelSpinLock(Irql[0]);
  }
}

```

## disassembly

```asm
0x14008a5e0  push    rbx
0x14008a5e2  push    rbp
0x14008a5e3  push    rsi
0x14008a5e4  push    rdi
0x14008a5e5  sub     rsp, 48h
0x14008a5e9  lea     rcx, [rsp+68h+Irql]; Irql
0x14008a5ee  mov     [rsp+68h+Irql], 0
0x14008a5f3  mov     rbp, r8
0x14008a5f6  mov     esi, edx
0x14008a5f8  call    cs:__imp_IoAcquireCancelSpinLock
0x14008a5ff  nop     dword ptr [rax+rax+00h]
0x14008a604  mov     rdi, [rsp+68h+arg_28]
0x14008a60c  mov     rcx, [rdi+18h]
0x14008a610  mov     rbx, [rdi]
0x14008a613  test    rcx, rcx
0x14008a616  jz      short loc_14008A64F
0x14008a618  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008a61c  mov     rax, [rcx]
0x14008a61f  test    rax, rax
0x14008a622  jz      short loc_14008A638
0x14008a624  mov     rdx, rcx; Entry
0x14008a627  mov     rcx, rax; Lookaside
0x14008a62a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008a631  nop     dword ptr [rax+rax+00h]
0x14008a636  jmp     short loc_14008A647
0x14008a638  mov     edx, [rcx+8]; Tag
0x14008a63b  call    cs:__imp_ExFreePoolWithTag
0x14008a642  nop     dword ptr [rax+rax+00h]
0x14008a647  mov     qword ptr [rdi+18h], 0
0x14008a64f  test    rbx, rbx
0x14008a652  jnz     short loc_14008A698
0x14008a654  lea     rcx, [rdi-10h]; P
0x14008a658  mov     rax, [rcx]
0x14008a65b  test    rax, rax
0x14008a65e  jz      short loc_14008A674
0x14008a660  mov     rdx, rcx; Entry
0x14008a663  mov     rcx, rax; Lookaside
0x14008a666  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008a66d  nop     dword ptr [rax+rax+00h]
0x14008a672  jmp     short loc_14008A683
0x14008a674  mov     edx, [rcx+8]; Tag
0x14008a677  call    cs:__imp_ExFreePoolWithTag
0x14008a67e  nop     dword ptr [rax+rax+00h]
0x14008a683  mov     cl, [rsp+68h+Irql]; Irql
0x14008a687  call    cs:__imp_IoReleaseCancelSpinLock
0x14008a68e  nop     dword ptr [rax+rax+00h]
0x14008a693  jmp     loc_14008A76D
0x14008a698  cmp     qword ptr [rbx+78h], 0
0x14008a69d  jz      short loc_14008A654
0x14008a69f  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a6a6  lea     rax, WPP_GLOBAL_Control
0x14008a6ad  cmp     rcx, rax
0x14008a6b0  jz      short loc_14008A6DB
0x14008a6b2  cmp     byte ptr [rcx+29h], 1
0x14008a6b6  jb      short loc_14008A6DB
0x14008a6b8  mov     eax, [rcx+2Ch]
0x14008a6bb  test    al, 10h
0x14008a6bd  jz      short loc_14008A6DB
0x14008a6bf  mov     rcx, [rcx+18h]
0x14008a6c3  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a6ca  mov     edx, 1Ah
0x14008a6cf  mov     [rsp+68h+var_48], esi
0x14008a6d3  mov     r9, rbx
0x14008a6d6  call    WPP_SF_qD
0x14008a6db  mov     qword ptr [rbx+78h], 0
0x14008a6e3  mov     cl, [rsp+68h+Irql]; Irql
0x14008a6e7  call    cs:__imp_IoReleaseCancelSpinLock
0x14008a6ee  nop     dword ptr [rax+rax+00h]
0x14008a6f3  mov     [rbx+30h], esi
0x14008a6f6  test    esi, esi
0x14008a6f8  jz      short loc_14008A702
0x14008a6fa  cmp     esi, 105h
0x14008a700  jnz     short loc_14008A721
0x14008a702  test    rbp, rbp
0x14008a705  jz      short loc_14008A721
0x14008a707  mov     rcx, [rdi+8]
0x14008a70b  movsd   xmm0, qword ptr [rbp+0]
0x14008a710  movsd   qword ptr [rcx], xmm0
0x14008a714  mov     eax, [rbp+8]
0x14008a717  mov     [rcx+8], eax
0x14008a71a  mov     eax, 0Ch
0x14008a71f  jmp     short loc_14008A723
0x14008a721  xor     eax, eax
0x14008a723  lea     rcx, [rdi-10h]; P
0x14008a727  mov     [rbx+38h], rax
0x14008a72b  mov     rax, [rcx]
0x14008a72e  test    rax, rax
0x14008a731  jz      short loc_14008A747
0x14008a733  mov     rdx, rcx; Entry
0x14008a736  mov     rcx, rax; Lookaside
0x14008a739  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008a740  nop     dword ptr [rax+rax+00h]
0x14008a745  jmp     short loc_14008A756
0x14008a747  mov     edx, [rcx+8]; Tag
0x14008a74a  call    cs:__imp_ExFreePoolWithTag
0x14008a751  nop     dword ptr [rax+rax+00h]
0x14008a756  xor     eax, eax
0x14008a758  mov     dl, 2; PriorityBoost
0x14008a75a  xchg    rax, [rbx+68h]
0x14008a75e  mov     rcx, rbx; Irp
0x14008a761  call    cs:__imp_IofCompleteRequest
0x14008a768  nop     dword ptr [rax+rax+00h]
0x14008a76d  add     rsp, 48h
0x14008a771  pop     rdi
0x14008a772  pop     rsi
0x14008a773  pop     rbp
0x14008a774  pop     rbx
0x14008a775  retn
```
