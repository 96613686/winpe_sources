# WskSendCompletion

- ea: `0x14001e3f0`
- end: `0x14001e4d7`
- name: `WskSendCompletion`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140007710`
- `0x14001e3f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4b0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e458`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e458`
- `ntoskrnl!IoFreeIrp` at `0x14001e488`
- `ntoskrnl!IoFreeIrp` at `0x14001e488`
- `ntoskrnl!IoFreeMdl` at `0x14001e4a0`
- `ntoskrnl!IoFreeMdl` at `0x14001e4a0`

## pseudocode

```c
__int64 __fastcall WskSendCompletion(__int64 a1, IRP *a2, struct _NPAGED_LOOKASIDE_LIST **a3)
{
  struct _MDL *v5; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rsi

  if ( a3 )
  {
    ((void (__fastcall *)(ULONGLONG, struct _NPAGED_LOOKASIDE_LIST *, struct _NPAGED_LOOKASIDE_LIST *, _QWORD, struct _NPAGED_LOOKASIDE_LIST *, NTSTATUS))(*a3)->L.ListEntry.Flink)(
      (*a3)->L.ListHead.Region,
      a3[1],
      a3[2],
      *((unsigned int *)a3 + 6),
      a3[4],
      a2->IoStatus.Status);
    v5 = (struct _MDL *)a3[7];
    if ( v5 )
      IoFreeMdl(v5);
    v6 = a3[5];
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0);
      a3[5] = 0;
    }
    v7 = *a3;
    ExFreeToNPagedLookasideList(*a3 + 2, a3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v7[4], 0xFFFFFFFF) == 1 )
      ((void (__fastcall *)(struct _NPAGED_LOOKASIDE_LIST *))v7[4].L.ListHead.Region)(v7);
  }
  if ( a2 )
    IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001e3f0  push    rdi
0x14001e3f2  sub     rsp, 40h
0x14001e3f6  mov     [rsp+48h+arg_0], rbx
0x14001e3fb  mov     rbx, r8
0x14001e3fe  mov     rdi, rdx
0x14001e401  test    r8, r8
0x14001e404  jz      short loc_14001E47B
0x14001e406  mov     rcx, [r8]
0x14001e409  mov     r8d, [rdx+30h]
0x14001e40d  mov     r9d, [rbx+18h]
0x14001e411  mov     rdx, [rbx+8]
0x14001e415  mov     rax, [rcx+40h]
0x14001e419  mov     rcx, [rcx+8]
0x14001e41d  mov     [rsp+48h+var_20], r8d
0x14001e422  mov     r8, [rbx+20h]
0x14001e426  mov     [rsp+48h+var_28], r8
0x14001e42b  mov     r8, [rbx+10h]
0x14001e42f  mov     [rsp+48h+arg_10], rsi
0x14001e434  call    _guard_dispatch_icall
0x14001e439  mov     rcx, [rbx+38h]; Mdl
0x14001e43d  test    rcx, rcx
0x14001e440  jnz     short loc_14001E4A0
0x14001e442  mov     rcx, [rbx+28h]; P
0x14001e446  test    rcx, rcx
0x14001e449  jnz     short loc_14001E4AE
0x14001e44b  mov     rsi, [rbx]
0x14001e44e  mov     rdx, rbx; Entry
0x14001e451  lea     rcx, [rsi+100h]; Lookaside
0x14001e458  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e45f  nop     dword ptr [rax+rax+00h]
0x14001e464  mov     eax, 0FFFFFFFFh
0x14001e469  lock xadd [rsi+200h], eax
0x14001e471  cmp     eax, 1
0x14001e474  jz      short loc_14001E4C6
0x14001e476  mov     rsi, [rsp+48h+arg_10]
0x14001e47b  mov     rbx, [rsp+48h+arg_0]
0x14001e480  test    rdi, rdi
0x14001e483  jz      short loc_14001E494
0x14001e485  mov     rcx, rdi; Irp
0x14001e488  call    cs:__imp_IoFreeIrp
0x14001e48f  nop     dword ptr [rax+rax+00h]
0x14001e494  mov     eax, 0C0000016h
0x14001e499  add     rsp, 40h
0x14001e49d  pop     rdi
0x14001e49e  retn
0x14001e4a0  call    cs:__imp_IoFreeMdl
0x14001e4a7  nop     dword ptr [rax+rax+00h]
0x14001e4ac  jmp     short loc_14001E442
0x14001e4ae  xor     edx, edx; Tag
0x14001e4b0  call    cs:__imp_ExFreePoolWithTag
0x14001e4b7  nop     dword ptr [rax+rax+00h]
0x14001e4bc  mov     qword ptr [rbx+28h], 0
0x14001e4c4  jmp     short loc_14001E44B
0x14001e4c6  mov     rax, [rsi+208h]
0x14001e4cd  mov     rcx, rsi
0x14001e4d0  call    _guard_dispatch_icall
0x14001e4d5  jmp     short loc_14001E476
```
