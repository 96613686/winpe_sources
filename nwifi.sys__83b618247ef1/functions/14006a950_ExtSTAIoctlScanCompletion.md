# ExtSTAIoctlScanCompletion

- ea: `0x14006a950`
- end: `0x14006aa38`
- name: `ExtSTAIoctlScanCompletion`
- size: `232`
- prototype: `void(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e830`

## callees

- `0x14006a950`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006a991`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006a9dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006a991`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006a9dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a9a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a9ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a9a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a9ee`
- `ntoskrnl!IofCompleteRequest` at `0x14006aa20`
- `ntoskrnl!IofCompleteRequest` at `0x14006aa20`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14006a966`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14006a966`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006a9b2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006aa0f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006a9b2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006aa0f`

## pseudocode

```c
void __fastcall ExtSTAIoctlScanCompletion(
        struct _ADAPT *a1,
        int a2,
        struct _DOT11_SCAN_REQUEST_V2 *a3,
        void *a4,
        char *a5)
{
  __int64 v6; // rbx
  ULONG *v7; // rcx
  KIRQL Irql[24]; // [rsp+20h] [rbp-18h] BYREF

  Irql[0] = 0;
  IoAcquireCancelSpinLock(Irql);
  v6 = *(_QWORD *)a5;
  v7 = (ULONG *)(a5 - 16);
  if ( *(_QWORD *)a5 && *(_QWORD *)(v6 + 120) )
  {
    *(_QWORD *)(v6 + 120) = 0;
    if ( *(_QWORD *)v7 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v7, v7);
    else
      ExFreePoolWithTag(v7, v7[2]);
    *(_DWORD *)(v6 + 48) = a2;
    *(_QWORD *)(v6 + 56) = 0;
    _InterlockedExchange64((volatile __int64 *)(v6 + 104), 0);
    IoReleaseCancelSpinLock(Irql[0]);
    IofCompleteRequest((PIRP)v6, 2);
  }
  else
  {
    if ( *(_QWORD *)v7 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v7, a5 - 16);
    else
      ExFreePoolWithTag(v7, v7[2]);
    IoReleaseCancelSpinLock(Irql[0]);
  }
}

```

## disassembly

```asm
0x14006a950  mov     [rsp+arg_0], rbx
0x14006a955  push    rdi
0x14006a956  sub     rsp, 30h
0x14006a95a  lea     rcx, [rsp+38h+Irql]; Irql
0x14006a95f  mov     [rsp+38h+Irql], 0
0x14006a964  mov     edi, edx
0x14006a966  call    cs:__imp_IoAcquireCancelSpinLock
0x14006a96d  nop     dword ptr [rax+rax+00h]
0x14006a972  mov     rax, [rsp+38h+arg_20]
0x14006a977  mov     rbx, [rax]
0x14006a97a  lea     rcx, [rax-10h]; P
0x14006a97e  test    rbx, rbx
0x14006a981  jnz     short loc_14006A9C0
0x14006a983  mov     rax, [rcx]
0x14006a986  test    rax, rax
0x14006a989  jz      short loc_14006A99F
0x14006a98b  mov     rdx, rcx; Entry
0x14006a98e  mov     rcx, rax; Lookaside
0x14006a991  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006a998  nop     dword ptr [rax+rax+00h]
0x14006a99d  jmp     short loc_14006A9AE
0x14006a99f  mov     edx, [rcx+8]; Tag
0x14006a9a2  call    cs:__imp_ExFreePoolWithTag
0x14006a9a9  nop     dword ptr [rax+rax+00h]
0x14006a9ae  mov     cl, [rsp+38h+Irql]; Irql
0x14006a9b2  call    cs:__imp_IoReleaseCancelSpinLock
0x14006a9b9  nop     dword ptr [rax+rax+00h]
0x14006a9be  jmp     short loc_14006AA2C
0x14006a9c0  cmp     qword ptr [rbx+78h], 0
0x14006a9c5  jz      short loc_14006A983
0x14006a9c7  mov     qword ptr [rbx+78h], 0
0x14006a9cf  mov     rax, [rcx]
0x14006a9d2  test    rax, rax
0x14006a9d5  jz      short loc_14006A9EB
0x14006a9d7  mov     rdx, rcx; Entry
0x14006a9da  mov     rcx, rax; Lookaside
0x14006a9dd  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006a9e4  nop     dword ptr [rax+rax+00h]
0x14006a9e9  jmp     short loc_14006A9FA
0x14006a9eb  mov     edx, [rcx+8]; Tag
0x14006a9ee  call    cs:__imp_ExFreePoolWithTag
0x14006a9f5  nop     dword ptr [rax+rax+00h]
0x14006a9fa  mov     [rbx+30h], edi
0x14006a9fd  xor     eax, eax
0x14006a9ff  mov     qword ptr [rbx+38h], 0
0x14006aa07  xchg    rax, [rbx+68h]
0x14006aa0b  mov     cl, [rsp+38h+Irql]; Irql
0x14006aa0f  call    cs:__imp_IoReleaseCancelSpinLock
0x14006aa16  nop     dword ptr [rax+rax+00h]
0x14006aa1b  mov     dl, 2; PriorityBoost
0x14006aa1d  mov     rcx, rbx; Irp
0x14006aa20  call    cs:__imp_IofCompleteRequest
0x14006aa27  nop     dword ptr [rax+rax+00h]
0x14006aa2c  mov     rbx, [rsp+38h+arg_0]
0x14006aa31  add     rsp, 30h
0x14006aa35  pop     rdi
0x14006aa36  retn
```
