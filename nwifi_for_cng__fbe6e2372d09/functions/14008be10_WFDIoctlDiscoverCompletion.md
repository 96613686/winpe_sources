# WFDIoctlDiscoverCompletion

- ea: `0x14008be10`
- end: `0x14008bfa7`
- name: `WFDIoctlDiscoverCompletion`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140087ea0`

## callees

- `0x140019314`
- `0x14008be10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008be5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008be96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008bf69`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008be5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008be96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008bf69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008be6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bf7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008be6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bf7a`
- `ntoskrnl!IofCompleteRequest` at `0x14008bf91`
- `ntoskrnl!IofCompleteRequest` at `0x14008bf91`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14008be28`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14008be28`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008beb7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008bf17`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008beb7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14008bf17`

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
0x14008be10  push    rbx
0x14008be12  push    rbp
0x14008be13  push    rsi
0x14008be14  push    rdi
0x14008be15  sub     rsp, 48h
0x14008be19  lea     rcx, [rsp+68h+Irql]; Irql
0x14008be1e  mov     [rsp+68h+Irql], 0
0x14008be23  mov     rbp, r8
0x14008be26  mov     esi, edx
0x14008be28  call    cs:__imp_IoAcquireCancelSpinLock
0x14008be2f  nop     dword ptr [rax+rax+00h]
0x14008be34  mov     rdi, [rsp+68h+arg_28]
0x14008be3c  mov     rcx, [rdi+18h]
0x14008be40  mov     rbx, [rdi]
0x14008be43  test    rcx, rcx
0x14008be46  jz      short loc_14008BE7F
0x14008be48  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14008be4c  mov     rax, [rcx]
0x14008be4f  test    rax, rax
0x14008be52  jz      short loc_14008BE68
0x14008be54  mov     rdx, rcx; Entry
0x14008be57  mov     rcx, rax; Lookaside
0x14008be5a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008be61  nop     dword ptr [rax+rax+00h]
0x14008be66  jmp     short loc_14008BE77
0x14008be68  mov     edx, [rcx+8]; Tag
0x14008be6b  call    cs:__imp_ExFreePoolWithTag
0x14008be72  nop     dword ptr [rax+rax+00h]
0x14008be77  mov     qword ptr [rdi+18h], 0
0x14008be7f  test    rbx, rbx
0x14008be82  jnz     short loc_14008BEC8
0x14008be84  lea     rcx, [rdi-10h]; P
0x14008be88  mov     rax, [rcx]
0x14008be8b  test    rax, rax
0x14008be8e  jz      short loc_14008BEA4
0x14008be90  mov     rdx, rcx; Entry
0x14008be93  mov     rcx, rax; Lookaside
0x14008be96  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008be9d  nop     dword ptr [rax+rax+00h]
0x14008bea2  jmp     short loc_14008BEB3
0x14008bea4  mov     edx, [rcx+8]; Tag
0x14008bea7  call    cs:__imp_ExFreePoolWithTag
0x14008beae  nop     dword ptr [rax+rax+00h]
0x14008beb3  mov     cl, [rsp+68h+Irql]; Irql
0x14008beb7  call    cs:__imp_IoReleaseCancelSpinLock
0x14008bebe  nop     dword ptr [rax+rax+00h]
0x14008bec3  jmp     loc_14008BF9D
0x14008bec8  cmp     qword ptr [rbx+78h], 0
0x14008becd  jz      short loc_14008BE84
0x14008becf  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bed6  lea     rax, WPP_GLOBAL_Control
0x14008bedd  cmp     rcx, rax
0x14008bee0  jz      short loc_14008BF0B
0x14008bee2  cmp     byte ptr [rcx+29h], 1
0x14008bee6  jb      short loc_14008BF0B
0x14008bee8  mov     eax, [rcx+2Ch]
0x14008beeb  test    al, 10h
0x14008beed  jz      short loc_14008BF0B
0x14008beef  mov     rcx, [rcx+18h]
0x14008bef3  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008befa  mov     edx, 1Ah
0x14008beff  mov     [rsp+68h+var_48], esi
0x14008bf03  mov     r9, rbx
0x14008bf06  call    WPP_SF_qD
0x14008bf0b  mov     qword ptr [rbx+78h], 0
0x14008bf13  mov     cl, [rsp+68h+Irql]; Irql
0x14008bf17  call    cs:__imp_IoReleaseCancelSpinLock
0x14008bf1e  nop     dword ptr [rax+rax+00h]
0x14008bf23  mov     [rbx+30h], esi
0x14008bf26  test    esi, esi
0x14008bf28  jz      short loc_14008BF32
0x14008bf2a  cmp     esi, 105h
0x14008bf30  jnz     short loc_14008BF51
0x14008bf32  test    rbp, rbp
0x14008bf35  jz      short loc_14008BF51
0x14008bf37  mov     rcx, [rdi+8]
0x14008bf3b  movsd   xmm0, qword ptr [rbp+0]
0x14008bf40  movsd   qword ptr [rcx], xmm0
0x14008bf44  mov     eax, [rbp+8]
0x14008bf47  mov     [rcx+8], eax
0x14008bf4a  mov     eax, 0Ch
0x14008bf4f  jmp     short loc_14008BF53
0x14008bf51  xor     eax, eax
0x14008bf53  lea     rcx, [rdi-10h]; P
0x14008bf57  mov     [rbx+38h], rax
0x14008bf5b  mov     rax, [rcx]
0x14008bf5e  test    rax, rax
0x14008bf61  jz      short loc_14008BF77
0x14008bf63  mov     rdx, rcx; Entry
0x14008bf66  mov     rcx, rax; Lookaside
0x14008bf69  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008bf70  nop     dword ptr [rax+rax+00h]
0x14008bf75  jmp     short loc_14008BF86
0x14008bf77  mov     edx, [rcx+8]; Tag
0x14008bf7a  call    cs:__imp_ExFreePoolWithTag
0x14008bf81  nop     dword ptr [rax+rax+00h]
0x14008bf86  xor     eax, eax
0x14008bf88  mov     dl, 2; PriorityBoost
0x14008bf8a  xchg    rax, [rbx+68h]
0x14008bf8e  mov     rcx, rbx; Irp
0x14008bf91  call    cs:__imp_IofCompleteRequest
0x14008bf98  nop     dword ptr [rax+rax+00h]
0x14008bf9d  add     rsp, 48h
0x14008bfa1  pop     rdi
0x14008bfa2  pop     rsi
0x14008bfa3  pop     rbp
0x14008bfa4  pop     rbx
0x14008bfa5  retn
```
