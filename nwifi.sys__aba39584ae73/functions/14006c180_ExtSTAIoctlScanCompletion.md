# ExtSTAIoctlScanCompletion

- ea: `0x14006c180`
- end: `0x14006c268`
- name: `ExtSTAIoctlScanCompletion`
- size: `232`
- prototype: `void(struct _ADAPT *, int, struct _DOT11_SCAN_REQUEST_V2 *, void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e830`

## callees

- `0x14006c180`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c1c1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c20d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c1c1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c20d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c21e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c21e`
- `ntoskrnl!IofCompleteRequest` at `0x14006c250`
- `ntoskrnl!IofCompleteRequest` at `0x14006c250`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14006c196`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14006c196`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006c1e2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006c23f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006c1e2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14006c23f`

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
0x14006c180  mov     [rsp+arg_0], rbx
0x14006c185  push    rdi
0x14006c186  sub     rsp, 30h
0x14006c18a  lea     rcx, [rsp+38h+Irql]; Irql
0x14006c18f  mov     [rsp+38h+Irql], 0
0x14006c194  mov     edi, edx
0x14006c196  call    cs:__imp_IoAcquireCancelSpinLock
0x14006c19d  nop     dword ptr [rax+rax+00h]
0x14006c1a2  mov     rax, [rsp+38h+arg_20]
0x14006c1a7  mov     rbx, [rax]
0x14006c1aa  lea     rcx, [rax-10h]; P
0x14006c1ae  test    rbx, rbx
0x14006c1b1  jnz     short loc_14006C1F0
0x14006c1b3  mov     rax, [rcx]
0x14006c1b6  test    rax, rax
0x14006c1b9  jz      short loc_14006C1CF
0x14006c1bb  mov     rdx, rcx; Entry
0x14006c1be  mov     rcx, rax; Lookaside
0x14006c1c1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006c1c8  nop     dword ptr [rax+rax+00h]
0x14006c1cd  jmp     short loc_14006C1DE
0x14006c1cf  mov     edx, [rcx+8]; Tag
0x14006c1d2  call    cs:__imp_ExFreePoolWithTag
0x14006c1d9  nop     dword ptr [rax+rax+00h]
0x14006c1de  mov     cl, [rsp+38h+Irql]; Irql
0x14006c1e2  call    cs:__imp_IoReleaseCancelSpinLock
0x14006c1e9  nop     dword ptr [rax+rax+00h]
0x14006c1ee  jmp     short loc_14006C25C
0x14006c1f0  cmp     qword ptr [rbx+78h], 0
0x14006c1f5  jz      short loc_14006C1B3
0x14006c1f7  mov     qword ptr [rbx+78h], 0
0x14006c1ff  mov     rax, [rcx]
0x14006c202  test    rax, rax
0x14006c205  jz      short loc_14006C21B
0x14006c207  mov     rdx, rcx; Entry
0x14006c20a  mov     rcx, rax; Lookaside
0x14006c20d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006c214  nop     dword ptr [rax+rax+00h]
0x14006c219  jmp     short loc_14006C22A
0x14006c21b  mov     edx, [rcx+8]; Tag
0x14006c21e  call    cs:__imp_ExFreePoolWithTag
0x14006c225  nop     dword ptr [rax+rax+00h]
0x14006c22a  mov     [rbx+30h], edi
0x14006c22d  xor     eax, eax
0x14006c22f  mov     qword ptr [rbx+38h], 0
0x14006c237  xchg    rax, [rbx+68h]
0x14006c23b  mov     cl, [rsp+38h+Irql]; Irql
0x14006c23f  call    cs:__imp_IoReleaseCancelSpinLock
0x14006c246  nop     dword ptr [rax+rax+00h]
0x14006c24b  mov     dl, 2; PriorityBoost
0x14006c24d  mov     rcx, rbx; Irp
0x14006c250  call    cs:__imp_IofCompleteRequest
0x14006c257  nop     dword ptr [rax+rax+00h]
0x14006c25c  mov     rbx, [rsp+38h+arg_0]
0x14006c261  add     rsp, 30h
0x14006c265  pop     rdi
0x14006c266  retn
```
